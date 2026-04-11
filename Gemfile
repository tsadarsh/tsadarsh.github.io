source "https://rubygems.org"

# This will help with testing your site locally and ensure it matches
# what GitHub Pages will render. If you have any plugins, this line
# should reflect the latest version of the github-pages gem and its dependencies.
gem "github-pages", group: :jekyll_plugins

# If you have any other dependencies, put them here
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-seo-tag", "~> 2.8"
  gem "jekyll-sitemap", "~> 1.4"
end

# Windows and JRuby compatibility
require 'rbconfig'
gem 'wdm', '~> 0.1.0' if RbConfig::CONFIG['target_os'] =~ /mswin|mingw|cygwin/i
