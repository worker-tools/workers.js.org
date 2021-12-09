source "https://rubygems.org"

gem "jekyll", "~> 4.1"

gem "duktape"
gem "kramdown-math-katex"

group :jekyll_plugins do
  gem "jekyll-default-layout"
  gem "jekyll-feed"
  gem "jekyll-optional-front-matter"
  gem "jekyll-paginate"
  gem "jekyll-readme-index"
  gem "jekyll-redirect-from"
  gem "jekyll-relative-links"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
  gem "jekyll-titles-from-headings"
  gem "jekyll-include-cache"
  gem "jekyll-last-modified-at"
  gem "jekyll-compose"
end

if ENV['JEKYLL_ENV'] == 'development'
  gem "jekyll-theme-hydejack", path: "~/GitHub/hydecorp/hydejack-site/#jekyll-theme-hydejack"
else
  gem "jekyll-theme-hydejack", git: "https://github.com/hydecorp/hydejack-dev", tag: "pro/v9.1.0-hysenberg.14"
end

gem 'wdm' if Gem.win_platform?
gem "tzinfo-data" if Gem.win_platform?