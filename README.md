:gem: Active Record Cheatsheet :gem:
======


### About

This repo intends to be a quick-reference for [Active Record](http://guides.rubyonrails.org/active_record_querying.html) and related tasks. It's still a work-in-progress.


### Install

#### via terminal / cmd
```
$ gem install activerecord
```


#### via GEMFILE
```
gem ‘activerecord’
```


#### then require
```
require 'active_record'
```


### Connect to a database
```
ActiveRecord::Base.establish_connection(YAML::load(File.open('./db/config.yml'))["db_name"])
```


### Clearing the test database between specs
```
RSpec.configure do |config|
  config.after(:each) do
    Task.all.each { |task| task.destroy }
  end
end
```
