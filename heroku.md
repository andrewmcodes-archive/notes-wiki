# Heroku

## Backfill releases on GH

```ruby
app = "YOUR_HEROKU_APPNAME"
key = `heroku auth:token`.strip

require "base64"
require "net/http"
require "json"

def http_get(url, headers)
  uri = URI.parse(url)
  Net::HTTP.start(uri.host, uri.port, { use_ssl: uri.scheme == "https" }) do |http|
    return http.request_get(uri.path, headers)
  end
end

response = http_get("https://api.heroku.com/apps/#{app}/releases", {
  "Authorization" => "Basic #{Base64.encode64(':'+key).strip}",
  "Accept" => "application/vnd.heroku+json; version=3",
  "Range" => "; max=1000",
})

data = JSON.parse(response.body)
deploys = data.select { |r| r["description"].start_with?("Deploy ") }
puts deploys.map { |r| "GIT_COMMITTER_DATE='#{r["created_at"]}' git tag heroku/v#{r["version"]} " + r["description"][/[0-9a-f]{7}/] }.join("\n")
```

Source: [github-release-party](https://github.com/stefansundin/github-release-party)
