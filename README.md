:gem: Active Record Cheatsheet :gem:
======


## About

This repo intends to be a quick-reference for [Active Record](http://guides.rubyonrails.org/active_record_querying.html) and related tasks. It's still a work-in-progress.


## Install

### via terminal / cmd
```ruby
$ gem install activerecord
```


### via GEMFILE
```ruby
gem ‘activerecord’
```


### then require
```ruby
require 'active_record'
```


## Connect to a database
```ruby
ActiveRecord::Base.establish_connection(YAML::load(File.open('./db/config.yml'))["db_name"])
```


## Clearing the test database between specs
```ruby
RSpec.configure do |config|
  config.after(:each) do
    Task.all.each { |task| task.destroy }
  end
end
```
