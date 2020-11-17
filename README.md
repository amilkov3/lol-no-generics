# macOS

```bash
xcode-select --install
gem install --user-install bundler jekyll
# Update PATH to $HOME/.gem/ruby/2.3.0/bin
git clone git@github.com:amilkov3/lol-no-generics.git
cd lol-no-generics
git checkout gh-pages
bundle install
# getting the following error now
# Conversion error: Jekyll::Converters::Scss encountered an error while converting 'assets/css/main.scss': Invalid US-ASCII character "\xE2" on line 54
# so instead of:
# bundle exec jekyll serve
# do
rake build
```
