# Welcome to runaterra's initial setup page. 

This page is divided in three sections:

 - [Development environment setup](#development-environment-setup)
 - [QA environment setup](#QA-environment-setup)
 - [Production environment setup](#production-environment-setup)

### Development environment setup

> It is recommended to use [Vagrant](https://www.vagrantup.com/) in order to avoid possible errors at the moment of setting up your environment.

Because of Runaterra's [architecture](Architecture) each service lives in its own repository and all development related to that specific service should be done on it. This makes the process of setting a development environment a tedious task. Luckily, git counts with [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) to help us in this kind of situations.

Each service can be set up and executed independently of the others, but in most cases this is not needed. Instead, if you wish to setup all services at once you have the following options:

 - Use Vagrant ([Download](https://www.vagrantup.com/downloads.html))
    1. Execute this in your command line `git clone --recursive https://github.com/intellisys/runaterra`
    2. Execute `vagrant up`
    5. All set! Now you should be able to access runaterra's web dashboard on `http://192.168.33.100`

 - Manual setup
    1. Execute this in your command line `git clone --recursive https://github.com/intellisys/intranet`
    2. Install `docker` and `docker-compose` (If you are using windows installing docker-toolbox should be enough)
    3. Start each service by executing its respective script:`/runaterra-SERVICENAME/scripts/start-SERVICENAME-dev.sh`
    5. All set! Now you should be able to access runaterra's web dashboard on `http://localhost`


### QA environment setup
 > Each deployment to the QA server should be done by **jenkins** therefore needs to be able to communicate with the server through ssh.

Initial set up:

 1. Execute this in your command line `git clone --recursive git@github.com:intellisys/runaterra`
 2. Run the script located in the project's root`/bootstrap.sh`
 3. Checkout every submodule to its `develop` branch. This can be done running the following command `git submodule foreach git checkout develop`
 4. Connect to github using ssh (help [here](https://help.github.com/articles/connecting-to-github-with-ssh/))
 5. Start each service by executing its respective script:`/runaterra-SERVICENAME/scripts/start-SERVICENAME-qa.sh` or running its respective jenkins job.

### Production environment setup

 > Each deployment to the production server should be done by **jenkins** therefore needs to be able to communicate with the server through ssh.

 > The instance of jenkins that handles jobs for both QA and production environments is executed as a docker container in the production server.

Initial set up:

 1. Execute this in your command line `git clone --recursive git@github.com:intellisys/runaterra`
 2. Run the script located in the project's root`/bootstrap.sh`
 3. Checkout every submodule to its `develop` branch. This can be done running the following command `git submodule foreach git checkout develop`
 4. Connect to github using ssh (help [here](https://help.github.com/articles/connecting-to-github-with-ssh/))
 5. Start each service by executing its respective script:`/runaterra-SERVICENAME/scripts/start-SERVICENAME-prod.sh` or running its respective jenkins job.
