# Welcome to Runaterra's Standards and Guidelines page.

Here you'll find information about the **Do's** and **Don'ts** when working on this project. These rules exists to keep the code base and project history manageable while still allowing contributors to be productive.

> This document's intention is to provide maximal guidance while providing reasonable restrictions. Nevertheless, common sense should always prevail and each individual situations should be handled accordingly.

# Git and Github

> The following rules and conventions should be followed across all Runaterra's repositories.

## Branching model

Runaterra's basically uses the [GitFlow](https://datasift.github.io/gitflow/IntroducingGitFlow.html) branching model (created by Vincent Driessen) with a couple of additional adjustments.

### **Major Feature vs Minor Feature**
Each service's major functionalities are considered **major features** which are composed of several **minor features** that work together.
> - Major features are usually accessed by final users or client services.
> - Minor features are usually used within its own service in the form of modules or methods.

Lets take as an example the **Accounting** service, some of its features are:
 - **Processing of TSS files.**
 - **Processing of 606 files.**

In order to provide this functionalities some internal tasks need to be executed.

 - **Processing of TSS files.**
    - Upload the file to server
    - Process the file as TSS
    - Retrieve desired information
    - Output result file.

 - **Processing of 606 files.**
    - Upload the file to server
    - Process the file as 606
    - Retrieve desired information
    - Output result file.
 
Each of these small tasks correspond to **minor features** in its service. 

Next, some of these minor features are *common* to both processes and should be treated as such. Therefore a resulting distribution would look like this:


 - **Common (Major)**
    - Upload the file to server (minor)
    - Output result file (minor)

 - **Processing of TSS files (Major)**
    - Process the file as TSS (minor)
    - Retrieve desired information (minor)

 - **Processing of 606 files (Major)**
    - Process the file as 606 (minor)
    - Retrieve desired information (minor)

### **Naming**:

To improve organization branch naming should follow the next standard.
 - `MAJOR-FEATURE_brief-change-description`
    
Example: 
 - `TSS-FILE_fixed-error-with-total-invoice-field`

## Pull Requests and Merging to develop

## Merging to master (Releases)

# Docker containers

# Jenkins 

# Documentation
