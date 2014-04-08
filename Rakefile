require 'rake'
require 'rspec/core/rake_task'
require 'bundler'
require './app.rb'
require 'sinatra/activerecord/rake'

RSpec::Core::RakeTask.new(:test)

task :default do
    puts "Default task"
end

desc "runs unit tests"
task :test do
    `rspec` 
end

desc "Installs requirements"
task :install do
    system %Q(bundle install)
end

desc "Starts app using shotgun"
task :shotgun => :install do
    `bundle exec shotgun -p 4567 config.ru`
end

desc "migrate test database"
task :mtdb do
    `RACK_ENV=test rake db:migrate`
end
