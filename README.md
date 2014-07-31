# Colour Coded Site
## Deploy Instructions
Set up Capistrano
```shell
echo "source 'https://rubygems.org'
gem 'capistrano', '~> 3.2.0'" > Gemfile
bundle install
cap install
```
After Capistrano is all set up, configure `/config/deploy.rb` and `/config/deploy/development.rb`.

* Create a user to deploy with
* Set apache vhost document root to `/current/`
* Upload a file to `/shared/` and use `:linked_files` and `:linked_dirs` to symlink the app files

To deploy the develop branch
* `bundle exec cap development deploy`

To deploy a specific branch
* `BRANCH=branch_name bundle exec cap development deploy`