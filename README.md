# kisonhe.github.io
Or, blog.kisonhe.xyz

```bash
# install bundler
gem update
gem install bundler

# If you need to add PATH
PATH=$PATH:/home/username/.local/share/gem/ruby/version/bin
# Fish
set PATH $PATH:/home/username/.local/share/gem/ruby/version/bin/

# install (in folder)
bundle config set --local path 'vendor/bundle'
bundle install

# test locally
#bundle exec jekyll serve --host 0.0.0.0
bundle exec jekyll serve

# build locally
bundle exec jekyll build

# build dat
asset/config/dat/build-dat.sh
```