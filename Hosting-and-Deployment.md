# Welcome to our hosting and deployment page

Here you'll learn most of what you need to understand how and where Runaterra is deployed. Also: 
 - How services are distributed between hosts.
 - How they should behave in relation to external services that are managed by other teams. 
 - How is the project's codebase organized. 

 > NOTE: This page contains an overview of the mentioned subjects. For more details on how every part of the project is organized visit our [Standards and Guidelines](Standards-and-Guidelines) page.

If you have not read about Runaterra's architecture we recommend you to do it [here](Architecture).


## Services groups

Services running in runnaterra can be divided into 2 logical groups:
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
To improve the deployment process, continuous integration with [Jenkins](https://jenkins.io/) is setup for each service's QA and production environment. (for more information about jenkins in Runaterra go [here](https://github.com/intellisys/Runaterra/wiki))

---
To start setting your environment and get into work visit out [initial Setup](Initial-Setup) page.
