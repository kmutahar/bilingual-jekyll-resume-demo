# frozen_string_literal: true

source "https://rubygems.org"

# Prefer the parent theme when this is its demo submodule, then a sibling checkout.
# Resolve checks relative to this Gemfile, regardless of the shell's working directory.
local_theme_path = ["..", "../jekyll-theme-resume"].find do |path|
  File.file?(File.expand_path("#{path}/jekyll-theme-resume.gemspec", __dir__))
end

# Must be in the :jekyll_plugins group: Jekyll only auto-requires gems in this group
# (via Bundler.require(:jekyll_plugins)), which is what registers the theme's build-time
# resume validator, page generators, and HTTP error page generator.
group :jekyll_plugins do
  if local_theme_path
    gem "jekyll-theme-resume", path: local_theme_path
  else
    gem "jekyll-theme-resume", "~> 1.0"
  end
end

gem "jekyll", "~> 4.4"
gem "webrick", "~> 1.8"

# Plugins required by the theme
gem "jekyll-feed", "~> 0.17"
gem "jekyll-seo-tag", "~> 2.9"
gem "jekyll-sitemap", "~> 1.4"
gem "jekyll-redirect-from", "~> 0.16"
