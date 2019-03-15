# Hub.Infrastructure

## State of PLay
* 14/03/2019
  *
* 13/03/2019
  * Created GitHub
  * Created PUML of current state
  * 3 unused NSG's 
    * James to document

## Description
The HUB infrastructure project is a single repository, so we can address a group of essential requirements which govern the deployment and running of the HUB aspplication.
If we took each requirement separately then we may leave holes or cause other requirements to take non ideal flows.

## Build and Deployment
* principcals
  * The build and deployment phases of the application should be consistent and idempotent. 
  * Scripts should be environment agnostic

## Git
* Whenever a new feature is needed to be developed.
  * Create a feature branch from the current develop branch
    * The feature should be named  
      * {entity}_{shortdescription}
      * {area}_{shortdescription}
      * {spike}_{area}_{shortdescription}
      * {bugfix}_{shortdescription}_{#TfsId}
  * When Feature branches are pulled into the Develop branch a build should be instigated.
    * On Successful Build
      * Unit Tests should be run
        * Unit Test Fail 
          * Failing feature should be rejected
          * Repeat Build
        * Unit Test Pass
          * Proceed to the DEV release Process
      * On Failed Build
        * The merge is rejected
  * When Develop is pulled into the Release branch a build and the release process should be started.
    * If the build fails (It Shouldn't) the relese is rejected.
    * If the build is sucessful.
      * Proceed to the Production release process

![aah2](/assets/gitprocess.png)

## Release Processes
### DEV 
* On a successful develop build
  * Tear down the DEV environment
  * Deploy the Infrastructure
  * Deploy the Application
  * Load Test data into databases
  * Load ES Indices
  * Perform Integration Tests
    * Tests Fail
      * Reject Build
    * Tests Pass
      * Create a Pull request for Release

### Production

## Environments
* Local
  * Dev Sandbox
* Non-Prod
  * Merge
  * UAT
  * PreProd
* Prod
  * Prod
### Secrets

### IaaS
* Deploy Servers
* Patch Upgrades

### Application
#### Initial
#### Incremental

### Data Schema
#### Initial
#### Incremental

### Data
##### Static Data
##### Migrated Data
#### Incremental

## FailOver vs Active/Active
### Cost

## Disaster 
### Definition
### Impact
### Recovery



![DEMO](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.github.com/Kf-GaryNewport/Hub.Infrastructure/master/puml/HubInfraNe.puml)