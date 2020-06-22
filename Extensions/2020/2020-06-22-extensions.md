# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## Zoom info

Join Zoom Meeting

- *Meeting ID:* 922 2840 3930
- *PC, Mac, Linux, iOS or Android:* [https://zoom.us/j/92228403930](https://zoom.us/j/92228403930)
- *iPhone one-tap: US:* +16699006833,,92228403930#  or +16465588656,,92228403930# 
- *Telephone:* US: +1 669 900 6833  or +1 646 558 8656 
- *International numbers:* https://zoom.us/zoomconference?m=92A2yi2UMG55h6OWMvp7GsxQKIou0L3E

## New business

- Where should the Extensions PMC go from here?
- Which projects are still active? (added a number to the Status Updates Needed section)
- @troytop will follow up with project leads 

# Projects

## _Incubating_

### CF Dev and Local (Scott, Stephen)

[add here]

### [Service Fabrik](https://github.com/cloudfoundry-incubator/service-fabrik-broker)

### [MultiApps](https://github.com/cloudfoundry-incubator/multiapps-cli-plugin)

#### Usability improvements

* multiapps CLI plugin will skip automatic retry of MTA content related errors. It was not very smart from our side to retry deployments where MTA was not modelled correctly
* Receive improved error messages in case of Cloud Controller related errors

#### Performance Improvements

* Eliminated potentially thousands of unnecessary calls to the Cloud Controller API, thus reducing the chance of exceeding the rate limit for the user

#### Bugfixes & other 

* As a result of multiple aborted processes, some deployments could end up with nasty errors, such as “Broken pipe”
* Disk leak on the application container led to failing operations with “No space left on device”
* After migration of MTA metadata from env to CF metadata, first attempt of blue green deployment of existing MTA failed when tried to delete routes
* Command line option --abort-on-error is now working regardless the moment of failure in your deployment
* The handling of async service creation had a regression! Service creation was not complete but the deployments continued, that led to similar failures in next steps:
“CF-AsyncServiceInstanceOperationInProgress(60016): An operation for service instance my-hana-service is in progress”
* Deploy from directory did not work for Windows because MANIFEST.MF had been generated with OS specific file separator. If you want the fix get the latest multiapps CLI plugin

## _Under Review_

## _Graduated_

### [App AutoScaler](https://github.com/cloudfoundry/app-autoscaler)
### [BBR](https://github.com/cloudfoundry-incubator/bosh-backup-and-restore)
### [Buildpacks](https://buildpacks.io/)
### [CredHub & CLI](https://github.com/cloudfoundry-incubator/credhub)
### [CFCR (aka Kubo)](https://github.com/cloudfoundry-incubator/cfcr-home)
### [Stratos](https://github.com/cloudfoundry/stratos)

* Nothing to report

## _Status Updates Needed_

### [Brooklyn Broker]() - Robert Moss
### [SQL Server]() - Jared Gordon
### [cf-dev]() - Sam Dawson / Steven Levine
### [cf-local]() - Steven Levine
### [Java Tools]() - Ben Hale
### [CF Swagger]() - Dr. Max
### [Notifications]() - Nadja Conklin(?)

## _Retired_

### [CF Abacus](https://github.com/cloudfoundry-incubator/cf-abacus)
### [Project Blockheads](https://github.com/cloudfoundry-incubator/blockhead)

