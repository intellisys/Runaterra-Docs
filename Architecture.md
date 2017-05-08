Welcome to Runaterra's project architecture page.

In here you'll find information about Runaterra's [service oriented architecture](https://en.wikipedia.org/wiki/Service-oriented_architecture).

## Overview 
Runaterra is divided into the following services:

 - [Dashboard](#dashboard-ekko) (**Ekko**)
 - [Human Resources](#human-resources-taric) (**Taric**)
 - [Accounting](#accounting-teemo) (**Teemo**)
 - [Notifications](#notifications-karma) (**Karma**)
 - [User Authentication](#user-authentication) (**Nami**)

![Architecture-diagram](https://i.imgsafe.org/e3cb9c883a.png)

### Dashboard (**Ekko**)
Provides an unified web-based user interface for all Runaterra's services.

### Human Resources (**Taric**)
Provides all functionalities relating to human resources department.

More specifically:
 - Employee's management (Registration, deletion, etc...).
 - Vacations management.

### Accounting (**Teemo**)
Provides all functionalities relating to the accounting department.

More specifically:
 - Payroll processing.
 - Accounting files processing (606, TSS, etc...) 

### Notifications (**Karma**)
Provides a single point of integration for email notification scheduling processes. This is intended to be used by all services who don't wish to handle email notifications to be sent within the company by themselves.

More specifically it provides an interface to:
 - Send an email at the moment when the request is made.
 - Schedule an email to be sent in the future.
 - Schedule an email to be send recurrently.

### User Authentication (**Nami**)
Provides client services with a single point of integration for managing user authentication. 

---

All communication between services its done through [REST](http://www.restapitutorial.com/lessons/whatisrest.html) APIs using [JSON](http://www.json.org/) formatted requests and responses.

---

To learn how and where Runaterra is running services and codebase are hosted. Visit our [Hosting and Deployment](hosting-and-deployment) page.
