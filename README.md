# Ruby-Standard-2 (Bash Uploader Edition)

[![Build Status](https://travis-ci.org/codecov/Ruby-Standard-2.svg?branch=master)](https://travis-ci.org/codecov/Ruby-Standard-2) [![codecov](https://codecov.io/gh/codecov/Ruby-Standard-2/branch/master/graph/badge.svg)](https://codecov.io/gh/codecov/Ruby-Standard-2)

### Last Updated: 07/23/19 16:32:55

## What is this?

This is a **Ruby on Rails** application, with basic unit tests, for which coverage is uploaded to Codecov on a daily basis via the Codecov Bash uploader. It can also serve as an example for how to integrate Codecov into your Ruby project. If the build is passing for this project, then Codecov's Ruby report processing is functional and correct on codecov.io.

## What's the difference between `Ruby-Standard-1` and `Ruby-Standard-2`?

[Ruby-Standard-1](https://github.com/codecov/Ruby-Standard-1) uses the Codecov gem to process coverage reports, while this repository, Ruby-Standard-2, uses Codecov's bash uploader to process reports. Otherwise, everything is the same between these two repos.

## Configuration

This project is written in `Ruby 2.6.3` using `Rails 5.2.3`. Unit tests are written in the [RSpec Rails](https://github.com/rspec/rspec-rails) framework. Coverage reports are generated through the [SimpleCov](https://github.com/colszowka/simplecov) gem and formatted via the [SimpleCov-Cobertura](https://github.com/dashingrocket/simplecov-cobertura) gem which converts the SimpleCov report into a `coverage.xml` file that is easily consumed by Codecov.

Unit tests: `spec/index_spec.rb` which tests `lib/index.rb`

Gemfile configuration:
```
gem 'simplecov', require: false
gem 'simplecov-cobertura'
```
RSpec configuration (top of `spec/spec_helper.rb`):
```
require 'simplecov'
SimpleCov.start

require 'simplecov-cobertura'
SimpleCov.formatter = SimpleCov::Formatter::CoberturaFormatter
```
> `spec_helper.rb` is a file that contains settings specific to RSpec. If you're using another testing framework, you'll need to put this information in some other helper Ruby file. For example, if you're using Minitest, which is prepackaged with all Rails applications, you'll need to put the above lines of code inside `test/test_helper.rb`

## Reporting Issues

If you've discovered an issue with this repository or with Ruby processing in general, it is recommended to email support@codecov.io rather than post an issue here. This repository will not be checked regularly for open issues.

## Contributing

If you would like to contribute your own language specific standard to Codecov you can do so as follows:

1. Write a sample repository that contains Docker and docker-compose based orchestration for running your project easily locally
2. Your project should be as simple as possible while providing and testing the following functions:
   - A function that is fully tested and covered by tests
   - A function that is not tested at all
   - A function that contains a conditional with a tested if and/or else condition.
3. A TravisCI configuration that will run the tests and upload coverage to Codecov.

If your standard is accepted by Codecov you can transfer ownership to the Codecov Organization and will be accepted in our current [List of Standards](https://github.com/codecov/standards-scripts#list-of-standards) with credit given to the repository's original author. You can review the List of Standards to see which languages and frameworks currently need a standard submitted. If you create a standard please, email support@codecov.io with the subject line "New <Language> Standard Submission" and the team will review it for acceptance.
