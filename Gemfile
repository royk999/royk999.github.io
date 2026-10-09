source "https://rubygems.org"

# Pins the same Jekyll and plugin versions that GitHub Pages builds with,
# so a local preview matches the live site.
gem "github-pages", group: :jekyll_plugins

# Required by `jekyll serve` on Ruby 3 and newer.
gem "webrick", "~> 1.8"

# Windows: time zone data is not bundled with Ruby.
platforms :mingw, :x64_mingw, :mswin do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end
