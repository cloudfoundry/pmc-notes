# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## Zoom info

https://zoom.us/j/656963476

Meeting ID: 656 963 476

One tap mobile
+16699006833,,656963476# US (San Jose)
+16465588656,,656963476# US (New York)

Dial by your location
        +1 669 900 6833 US (San Jose)
        +1 646 558 8656 US (New York)
        855 880 1246 US Toll-free
        877 369 0926 US Toll-free
        +1 647 558 0588 Canada
        855 703 8985 Canada Toll-free
Meeting ID: 656 963 476
Find your local number: https://zoom.us/u/abSAPsJbM

## New business

- Welcome omniauth-uaa-oauth2 and cf-uaa-lib! Dr. Nic
- Still using the [cf-extensions bot](https://github.com/cloudfoundry-incubator/cf-extensions)?
  - not in use - we should retire this to the Attic

## Updates

### Stratos 

- 4.1.0 just released
- bug fixes & API key support (will be very useful in 4.2)
- 4.2.0 scheduled for CF Summit - will include the Kubernetes & Helm extensions

### cflocal

- added cflinuxfs3 support recently 
- v2 buildpack users still use it
- we will move it to the attic when we end support for v2 buildpacks

### BOSH Backup & Restore (BBR)

- just shipped v. 1.8.0 with a validator for S3 configuration
- will ship soon 1.9.0 with some SSH refactoring and improvements
- looking into some potential future changes 
- re. ongoing maintenance: will maintain BBR as CVE and bug free


# Projects

## _Incubating_

- [Service Fabrik](https://github.com/cloudfoundry-incubator/service-fabrik-broker) - SAP
- [MultiApps](https://github.com/cloudfoundry-incubator/multiapps-cli-plugin)

## _Under Review_

- [cfdev](https://github.com/cloudfoundry-incubator/cfdev) - Anthony Emengo 
  - Inactive. Consider moving to the Attic?
- [cflocal](https://github.com/cloudfoundry-incubator/cflocal) - Stephen Levine 

## _Graduated_

- [App AutoScaler](https://github.com/cloudfoundry/app-autoscaler)
- [BBR](https://github.com/cloudfoundry-incubator/bosh-backup-and-restore) - Yaran Parasol
- [Buildpacks](https://buildpacks.io/)
- [CredHub & CLI](https://github.com/cloudfoundry-incubator/credhub)
- [CFCR (aka Kubo)](https://github.com/cloudfoundry-incubator/cfcr-home) - Stuart Charlton
- [Stratos](https://github.com/cloudfoundry/stratos) - Neil MacDougall
- [omniauth-uaa-oauth2](https://github.com/cloudfoundry/omniauth-uaa-oauth2) - Dr. Nic
- [cf-uaa-lib](https://github.com/cloudfoundry/cf-uaa-lib) - Dr. Nic

## _Status Updates Needed_

- [CF Swagger](https://github.com/cloudfoundry-incubator/cf-swagger) - was Dr. Max
  - needs a new owner
  - potentially useful tool, but needs to support CF v3 API

- [Java Tools](https://github.com/cloudfoundry/cf-java-client) - Ben Hale
- [Notifications](https://github.com/cloudfoundry-incubator/notifications) - Nadja Conklin(?) or Dwayne Forde

## _Retired_

- [CF Abacus](https://github.com/cloudfoundry-incubator/cf-abacus)
- [Project Blockheads](https://github.com/cloudfoundry-incubator/blockhead)

## _To Be Retired_

- [Brooklyn Broker](https://github.com/cloudfoundry-incubator/apache-brooklyn-service-broker) - Robert Moss
- [SQL Server](https://github.com/cloudfoundry-incubator/mssql-server-broker) - Jared Gordon

