# Utilities PMC Notes 2015-09-09

## Table of Contents

1. Update on "Offline" PMC Discussion
2. CLI
3. Java Utilities


## Update on "Offline" PMC Discussions

In the previous PMC meeting, held on 2015-07-28, the Buildpacks PMC agreed to tentatively stop conducting regular synchronous meetings, and instead move to an "offline" model where discussions and, if necessary, voting would be conducted on the public cf-dev@ mailing list.

As part of this change, the PMC Lead (that's me!) committed to sending regular status updates to the mailing list in lieu of meeting notes. In this aspect, I failed over the last month, and I apologize for the resulting lack of transparency.

Going forward, I'll return to a two-week cycle of email updates for this PMC.

Please reach out to me or Chip if you have concerns over continuing the "offline" model for the Buildpacks PMC.


## CLI

[CLI v6.12.3][] was released on August 31st, which notably includes many community PRs and remove of codegangsta in preparation for an epic to revamp `cf help`.

  [CLI v6.12.3]: https://github.com/cloudfoundry/cli/releases/tag/v6.12.3

CLI has scheduled an inception on 2015-09-09 in San Francisco, Greg Oehmen will be sending out details later this week.


## Java Utilities

Work continues on moving the Eclipse tools for Cloud Foundry to the Eclipse Foundation. Immediate goal is inclusion in the Luna SR1 release.

The team is planning an inception for "v2" of `cf-java-client`. Immediate goals will include support for CCv3 and to improve upon decisions made during the initial implementation. We expect the inception planning process to take some time, while some high-level design work is done to build abstractions on top of a large number of API endpoints.
