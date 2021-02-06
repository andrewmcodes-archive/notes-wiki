# Gems

## Rubygems

- Sign in: `gem signin`
- Sign out: `gem signout`


## Must Haves for [[Rails]] Devs

- [GitHub - ivantsepp/annotate_gem: Add comments to your Gemfile with each dependency's description](https://github.com/ivantsepp/annotate_gem/)

## Performance

- [GitHub - igorkasyanchuk/rails_performance: Monitor performance of you Rails applications](https://github.com/igorkasyanchuk/rails_performance)

## Notes

### Loading

If you have a gem with a `lib/` folder structured like:

```md
├── lib
│   ├── foobar
│   │   ├── version.rb
│   │   ├── foo.rb
│   │   ├── bar
│   │   │   └── baz.rb
```

Then you can make this change in your gemspec:

```diff
# foobar.gemspec
lib = File.expand_path("../lib", __FILE__)
$LOAD_PATH.unshift(lib) unless $LOAD_PATH.include?(lib)
require "foobar/version"

Gem::Specification.new do |spec|
  # ...
-  spec.require_paths = ["lib"]
+  spec.require_paths = ["lib", "lib/foobar"]
  # ...
end
```

Setting your require paths from `lib` to `lib` and `lib/foobar` allows you to leave off `foobar/` when requiring files.

```diff
# lib/foobar.rb

- require "foobar/version"
- require "foobar/foo"
- require "foobar/bar/baz"
+ require "version"
+ require "foo"
+ require "bar/baz"
```

Get version number from external file:

```rb
VERSION = File.open("version.toml", File::RDONLY).read.strip
```
