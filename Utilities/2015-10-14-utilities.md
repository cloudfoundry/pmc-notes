# Utilities PMC Notes 2015-10-14

## Table of Contents

1. CLI
2. Java Utilities
3. CI Tooling


## CLI

* Nearly done with [Diego support](https://www.pivotaltracker.com/epic/show/1995122).
* Upcoming work around [Organization and Space RBAC](https://www.pivotaltracker.com/epic/show/1991856).
* Upcoming work around [CC v3 API](https://www.pivotaltracker.com/epic/show/2088038).


## Java Utilities

* Work has started in earnest on [cf-java-client v2](https://www.pivotaltracker.com/n/projects/816799). Official announcement will go out to cf-dev@ soon.

* Eclipse Tools for Cloud Foundry ("CFT") repo is now avilable at [github.com/eclipse/cft](https://github.com/eclipse/cft). The transition is fully explained [here](https://github.com/cloudfoundry/eclipse-integration-cloudfoundry#important-breaking-changes---october-2015).


## CI Tooling

* CF-Dreddbot and CF-Gitbot ("the bots") are now being continuously deployed via a Concourse pipeline. Making these pipelines public is pending on making sure credentials aren't being leaked.
* The Bots are also hooked into papertrail to make sure that if any webhooks are missed, the Toolsmiths will receive an alert.
* Nearly done with an OSS release of a "cron" concourse resource.
