# Overview

Taric is the service in charge of managing all human resources related processes.

These include employees:

* Basic information
* Vacation days calculations
* Salary increase
* Medical insurance


## Setup

Currently you can setup and run the service for development by executing the file `scripts/start-taric-dev.sh`

**WARNING**: This script execution will re-create the database, **DO NOT** run in production


# Notes

Here you can find some of the dependencies(gems) used in the HR service.

## Ruby on Rails

This app is setup as a rails-5-api-only configuration, so if you are used to working with regular rails, you have to take in count some things:
* View will not be generate by "_`rails generate`_" command, only api's
* The only views currently used are for emails.

## [Rspec](http://rspec.info/)
Rspec is the tool used for making tests. Behaviour Driven Development for Ruby. Making TDD Productive and Fun.
