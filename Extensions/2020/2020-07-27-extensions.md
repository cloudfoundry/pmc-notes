# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## Zoom info

Zoom meeting cancelled in favor of asynchronous updates on #cf-extensions

## New business

- Which projects are still active? (added a number to the Status Updates Needed section)

# Projects

## _Incubating_

### [Service Fabrik](https://github.com/cloudfoundry-incubator/service-fabrik-broker)
### [MultiApps](https://github.com/cloudfoundry-incubator/multiapps-cli-plugin)

## _Under Review_

## _Graduated_

### [App AutoScaler](https://github.com/cloudfoundry/app-autoscaler)
### [BBR](https://github.com/cloudfoundry-incubator/bosh-backup-and-restore)
### [Buildpacks](https://buildpacks.io/)
### [CredHub & CLI](https://github.com/cloudfoundry-incubator/credhub)
### [CFCR (aka Kubo)](https://github.com/cloudfoundry-incubator/cfcr-home) - Stuart Charlton

* CFCR 0.43 and 0.44 with Kubernetes 1.16 and 1.17 support both shipped in early-mid July after some COVID-impacted resourcing delays.
* Kubernetes 1.18 likely will follow in August, along with support for:
  * new CNIs (Antrea and Calico),
  * CSI drivers (VMware), and 
  * Containerd as a Docker CE alternative.

### [Stratos](https://github.com/cloudfoundry/stratos)

* 4.0.0 RC 
  * refactoring for extensions
  * lots of usability improvements
  * bug fixes
  * Changelog: https://github.com/cloudfoundry/stratos/blob/master/CHANGELOG.md

## _Status Updates Needed_

### [Brooklyn Broker](https://github.com/cloudfoundry-incubator/apache-brooklyn-service-broker) - Robert Moss
### [SQL Server](https://github.com/cloudfoundry-incubator/mssql-server-broker) - Jared Gordon
### [cfdev](https://github.com/cloudfoundry-incubator/cfdev) - Anthony Emengo 

* Inactive. Consider moving to the Attic?

### [cflocal](https://github.com/cloudfoundry-incubator/cflocal) - Steven Levine

* on hiatus, as it will eventually be replaced or re-instrumented to use the pack CLI from the CNB
  project. But cflinuxfs3 support did get added recently.

### [Java Tools](https://github.com/cloudfoundry/cf-java-client) - Ben Hale
### [CF Swagger](https://github.com/cloudfoundry-incubator/cf-swagger) - Dr. Max
### [Notifications](https://github.com/cloudfoundry-incubator/notifications) - Nadja Conklin(?) or Dwayne Forde

## _Retired_

### [CF Abacus](https://github.com/cloudfoundry-incubator/cf-abacus)
### [Project Blockheads](https://github.com/cloudfoundry-incubator/blockhead)

