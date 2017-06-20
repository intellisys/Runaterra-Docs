Welcome to our hosting and deployment page

Here you'll learn most of what you need to understand how and where Runaterra is deployed. Also:
 - How services are distributed between hosts.
 - How they should behave in relation to external services that are managed by other teams.
 - How is the project's codebase organized.

 > NOTE: This page contains an overview of the mentioned subjects. For more details on how every part of the project is organized visit our [Standards and Guidelines](Standards-and-Guidelines) page.

If you have not read about Runaterra's architecture we recommend you to do it [here](Architecture).


## Services groups

Services running in runaterra can be divided into 2 logical groups:
 - **Application Front-end**
     - [Dashboard](Architecture#dashboard-ekko) (Ekko)
 - **Application Back-end**
     - [Human Resources](Architecture#human-resources-taric) (Taric)
     - [Accounting](Architecture#accounting-teemo) (Teemo)
     - [Notifications](Architecture#notifications-karma) (Karma)
     - [Authentication](Architecture#authentication-nami) (Nami)

![Services-groups](/img/hosting-1.PNG)

## Codebase and deployment

### Code Version Control  (Git and Github)
Every service is deployed independently of all others and counts with its own repository in which it **must** contain the following files :

 - `/`
    - `Dockerfile` (see [Docker](https://www.docker.com) documentation)
 - `/scripts/`
    - `start-SERVICENAME-dev.sh`
    - `start-SERVICENAME-qa.sh`
    - `start-SERVICENAME-prod.sh`

### Environment Isolation (Docker)
In order to ensure that every service is executed optimally each one of them runs in one or more containers that are handled using [Docker](https://www.docker.com). Each container exposes a port for the end user:

 | Port | Service|
 | ---  | ---   |
 | 80   | ekko  |
 | 5010 | teemo |
 | 5020 | nami  |
 | 5030 | taric |
 | 5040 | karma |

 > For details of services ip go [here](https://github.com/intellisys/Runaterra/wiki).

### Continuous integration (Jenkins)
To improve the deployment process, continuous integration with [Jenkins](https://jenkins.io/) is setup for deployment of QA services, production services and other maintenance jobs. (Links to access to Runaterra's Jenkins can be found [here](https://github.com/intellisys/Runaterra/wiki)).

Runaterra's jenkins service is running on a docker container named **jens** which is configured using Docker's `--restart unless-stopped` option  to ensure that its container is kept running. 

#### Jobs:

 - `SERVICE-NAME` (ekko, taric, etc...): Manually executed, these jobs make a pull the most recent changes from its respective repository's `master` branch and preform the build and st art process of its docker container/s.

 - `SERVICE-NAME-qa` (ekko-qa, taric-qa, etc...): To ensure that the QA server reflects up to date changes made in development, executed periodically, these jobs make a pull the most recent changes from its respective repository's `develop` branch and preform the build and start process of its docker container/s.                                                      

 - `Prune docker images - PROD/QA`: To avoid keeping old docker images unnecessarily both of these jobs run periodically to execute the command `docker image prune` on each server.

### Docker Container dashboard-ekko
if you want to manage the docker instance without having to access the server via SSH, you can access the Portainer service on port 9000, there you can run commands inside the container, view logs, status, server load among other things.

### Hardware

The server running all production services is described by the following table

 | Data  | Description|
 | ---  | ---   |
 | Model | Lenovo K450e |
 | CPU | Intel(R) Core(TM) i7-4790 CPU @ 3.60GHz  |
 | Memory size(RAM) | 16Gib |
 | Hard drive size(Storage) | 1863Gib |
 | 64 bits system    | Yes  |
 | Serial Number | ES13881325 |

---
