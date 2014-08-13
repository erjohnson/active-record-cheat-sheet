:gem: Active Record Cheatsheet :gem:
======
&nbsp;
### Contents

* [About](#about)
* [Install](#install)
* [Connecting](#connect-to-a-database)

&nbsp;
### About

This repo intends to be a quick-reference for [Active Record](http://guides.rubyonrails.org/active_record_querying.html) and related tasks. It's still a work-in-progress.

&nbsp;
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

&nbsp;
### Connect to a database
```
ActiveRecord::Base.establish_connection(YAML::load(File.open('./db/config.yml'))["db_name"])
```

&nbsp;
### Clearing the test database between specs
```
RSpec.configure do |config|
  config.after(:each) do
    Task.all.each { |task| task.destroy }
  end
end
```
