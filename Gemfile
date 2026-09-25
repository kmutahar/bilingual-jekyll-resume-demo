# frozen_string_literal: true

source "https://rubygems.org"

# When developing alongside the theme locally, use local path; otherwise use published gem.
# Must be in the :jekyll_plugins group: Jekyll only auto-requires gems in this group
# (via Bundler.require(:jekyll_plugins)), which is what registers the theme's build-time
# resume validator and HTTP error page generator.
group :jekyll_plugins do
  if File.directory?("../bilingual-jekyll-resume-theme")
    gem "bilingual-jekyll-resume-theme", path: "../bilingual-jekyll-resume-theme"
  else
    gem "bilingual-jekyll-resume-theme", "~> 1.0"
  end
end

gem "jekyll", "~> 4.4"
gem "webrick", "~> 1.8"

# Plugins required by the theme
gem "jekyll-feed", "~> 0.17"
gem "jekyll-seo-tag", "~> 2.9"
gem "jekyll-sitemap", "~> 1.4"
gem "jekyll-redirect-from", "~> 0.16"
