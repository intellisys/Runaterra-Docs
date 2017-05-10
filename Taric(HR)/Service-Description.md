# Taric (HR)

Taric is the service in charge of managing all the employee proceses and human resources things.

These include things like

* Medical insurance
* Employee vacation days calculations
* Employee salary increase
* Handling basic employee information


## Docker Support
Currently you can use docker to setup the enviroment running this:


run docker-compose up -d db
run docker-compose build app
run docker-compose run --rm app rake db:setup
run docker-compose up -d app

**WARNING**: This will re-create the database, DO NOT run in production


## Rails information

This app is setup as a rails-5-api-only configuration, so if you are used to working with regular rails, you have to take in count some things:
* View will not be generate by "_`rails generate`_" command, only api's
* The only views currently used are for emails.


