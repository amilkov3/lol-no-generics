# macOS

```bash
xcode-select --install
gem install --user-install bundler jekyll
# Update PATH to $HOME/.gem/ruby/2.3.0/bin
git clone git@github.com:amilkov3/lol-no-generics.git
cd lol-no-generics
git checkout gh-pages
bundle install
bundle exec jekyll serve
```
