# Utilities PMC Meeting 2015-06-16

## Agenda

1. Update on CI tools (Mike Dalessio)
2. Update on CLI (Greg Oehmen)
3. Update on Eclipse plugin and Java tools (Ryan Morgan)
4. Open Discussion


## Attendees

* Chip Childers, Cloud Foundry Foundation
* Mike Dalessio, Pivotal (PMC lead)
* Ryan Morgan, Pivotal
* Greg Oehman, Pivotal
* Alex Tarpinian, IBM
* Michael Fraenkel, IBM


## Update on CI tools (Mike Dalessio)

- Greenhouse team started moving their builds to Concourse. Runtime
  and BOSH are also in progress.

- Toolsmiths team taking over Krafa, which is a project (to-be-OSSed)
  to manage a pool of CI environments. Currently being used internally
  at Pivotal, but totally applicable to OSS as well.

- A pair is working for the next month on License Finder, which is an
  OSS tool to examine a project's declared dependencies (via a package
  manager) and discover licenses and changes in licensing. This should
  be useful for the Foundation as well.


## Update on CLI (Greg Oehman)

- New pair rolled on from IBM, who ramped up quickly and are contributing; team velocity is up.
  - There is ongoing track of work around the plugin API.
  - Another track of work on PRs and Issues was successful at cleaning up some old stories.

- Next release will be 6.12.0.
  - Deprecate "codegangsta" library which is used for feature flags

- Working with IBM designers on user testing "help" with a mock
  terminal emulator. Community members have offered to be a part of
  that user testing

- Upcoming tracks:
  - Syntax change from "verb noun" to "noun verb" (e.g., "create-service" to "service-create")
  - Improving CLI installers


## Update on Eclipse plugin and Java tools (Ryan Morgan)

* Push to move to the Eclipse Foundation continues.


## Open Discussion

* Proposal to accept receptor-client into incubation.  See: http://cf-dev.70369.x6.nabble.com/cf-dev-Proposal-for-incubation-of-receptor-client-Java-client-for-receptor-td440.html
