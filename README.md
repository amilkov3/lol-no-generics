# macOS

```bash
xcode-select --install
gem install --user-install bundler jekyll
# Update PATH to $HOME/.gem/ruby/2.3.0/bin
bundle install
git clone git@github.com:amilkov3/lol-no-generics.git
cd lol-no-generics
git checkout gh-pages
bundle exec jekyll serve
```
