# Gemspec

My `.gemspec` template for [[Gems]].

```ruby
# frozen_string_literal: true

require_relative "lib/CHANGEME/version"

Gem::Specification.new do |spec|
  spec.name = "CHANGEME"
  spec.version = Gem::Release::Demo::VERSION
  spec.authors = ["Andrew Mason"]
  spec.email = ["andrewmcodes@protonmail.com"]
  spec.summary = "CHANGEME"
  spec.description = "CHANGEME"
  spec.homepage = "https://github.com/andrewmcodes/#{spec.name}"
  spec.license = "MIT"
  spec.required_ruby_version = Gem::Requirement.new(">= 2.4.0")
  spec.metadata = {
    "bug_tracker_uri" => "#{spec.homepage}/issues",
    "changelog_uri" => "#{spec.homepage}/blob/main/CHANGELOG.md",
    "documentation_uri" => spec.homepage.to_s,
    "homepage_uri" => spec.homepage.to_s,
    "source_code_uri" => spec.homepage.to_s
  }

  # Specify which files should be added to the gem when it is released.
  # The `git ls-files -z` loads the files in the RubyGem that have been added into git.
  spec.files = Dir.chdir(File.expand_path(__dir__)) do
    `git ls-files -z`.split("\x0").reject { |f| f.match(%r{\A(?:test|spec|features)/}) }
  end
  spec.bindir = "exe"
  spec.executables = spec.files.grep(%r{\Aexe/}) { |f| File.basename(f) }
  spec.require_paths = ["lib"]

  # Uncomment to register a new dependency of your gem
  # spec.add_dependency "example-gem", "~> 1.0"

  # For more information and examples about making a new gem, checkout our
  # guide at: https://bundler.io/guides/creating_gem.html
end
```
