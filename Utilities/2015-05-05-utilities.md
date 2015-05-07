# Utilities PMC Meeting 2015-05-05

## Agenda

1. Update on CI tools (Mike Dalessio)
2. Update on CLI (Greg Oehman)
3. Update on Eclipse plugin and Java tools (Ryan Morgan)
4. Open Discussion


## Attendees

* Chip Childers, Cloud Foundry Foundation
* Mike Dalessio, Pivotal (PMC lead)
* Christopher Ferriss, IBM
* Michael Fraenkel, IBM
* James Bayer, Pivotal
* Greg Oehmen, Pivotal
* Ryan Morgan, Pivotal


## Update on CI tools (Mike Dalessio)

[GoCD][gocd] still in use for some projects, but there’s movement
towards [Concourse][concourse] and teams are enthusiastic about
it. Currently Diego, Garden, BOSH-lite, Loggregator, and CLI have
converted to Concourse; and BOSH, Services API, and Buildpacks are in
progress.

Timeline is open for individual teams to move to Concourse; some teams
may decide not to. Having a heterogenous CI environment is OK, as both
GoCD and Concourse can integrate via S3 buckets, which is where
generated artifacts are generally kept.


## Update on CLI (Greg Oehmen)

* Released 6.11.0 - 4/17
* Released 6.11.1 - 4/20
* Released 6.11.2 - 4/28

Big uptick in issues/PRs

Plugin API feature

Look Ahead:

1. help refactor work, 
  - refactor help
  - invert syntax (object - action)
  - tab/bash completion

2. support the move to cc API 3.0 and services api changes

3. the user security work (pwd expiration, inactivity-based session timeout, RBAC maturation, etc.) 

4. installer emphasis
  - Auto-update within CLI
  - signed mac installer
  - signed windows installer
  - etc

5. APM integration - something like blessed-contrib:  https://github.com/yaronn/blessed-contrib


## Update on Eclipse plugin and Java tools (Ryan Morgan)

### CF Eclipse Tooling: (1 dev at Pivotal, 4 splitting time at IBM)

* 1.8.0 (Released Feb 13th)
  * New Service wizard allowing for multiple service creation
  * Remote debug support via ngrok.com
* 1.8.1 (Released March 25th)
  * Map/Unmap project feature to map an existing eclipse workspace to an app
  * Update password fixes
  * Free service plans now marked in the UI and preferred over paid plans
* 1.8.2 (Release imminent)
  * JRebel support
  * Working on some last minute UI changes
* Working on a proposal to move the Eclipse tooling to the Eclipse Foundation
  * Should have a proposal for review mid-late May.  Targeting Eclipse
    4.5 SR1 update in the fall.  Lots of work to be done to make that
    deadline.

### CF Java Client: (1 dev at Pivotal, splitting time)

* 1.1.2 Released April 13th
* No active development, PRs and Issues reviewed on-demand
  * Support of CC v3
  * Removal of Spring dependencies (v2.0 item)


## Open Discussion

Please add any other suggested agenda topics for discussion here:

### Imminent additions to the Utilities PMC from HP (Chip).

Voting took place via email on 2015-05-05 with unanimous consent to
add the following to the Utilities PMC as incubating projects:

* CF .NET SDK https://github.com/hpcloud/cf-dotnet-sdk
* CF Visual Studio Extension
  https://github.com/hpcloud/cf-vs-extension-wpf (will be renamed to
  https://github.com/hpcloud/cf-vs-extension)
* CF MSBuild Tasks https://github.com/hpcloud/cf-msbuild-tasks


---

  [gocd]: http://www.go.cd/
  [concourse]: http://concourse.ci/
