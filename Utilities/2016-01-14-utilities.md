# Utilities PMC Notes as of 2016-01-14

The last set of notes were sent out on ??


## Table of Contents

1. CLI
2. Java Utilities
3. CI Tooling


## CLI

### Releases

CLI v6.14.1 was released just before the Christmas & New Year's break. It mainly consists of a number of issues reported by the community.
Also, the Mac OS X installer is now digitally signed, allowing the CLI to be installed in corporate environments with policies that prevent users from installing unsigned programs.
CLI v6.15.0 is the latest release, adding management of Routing's routes with path feature, and includes IBM contributed language files for 9 languages (de_DE, es_ES, fr_FR, it_IT, ja_JP, ko_KR, pt_BR, zh_Hans and zh_Hant).

### Ongoing / Upcoming work

* Continuing to review CLI UX for new Routing features with Shannon, reviewing PRs and implementing CLI stories from Routing team.
* About to discuss CLI documentation on docs.cloudfoundry.org with Kim, will propose to integrate a cf CLI command reference guide (generated from cf help output).
* About to discuss new CAPI features to expose in CLI with Dieu.
* Need to work out a strategy on how to keep the CLI translations up to date (ask IBM again, ask users on CF Dev ML for PRs, ask CFF sponsors to adopt a language, look into other crowd-sourced methods?).
* Working on a proposal for a cli command to check if it's the latest, potentially update itself.

### Team developments

* The team had 1-2 weeks off during the Christmas & New Year's break.
* Anchor rolled off the team (moved to CAPI). Remaining CLI developer confident he knows enough to figure out any context we lost.
* Remaining CLI developer visiting Sydney this month to ramp up new team member from Fujitsu.
* Pivotal Labs Sydney lending out a Pivot to CLI team; he is remote cross-pairing with SF based Routing team on exposing Routing features through the CLI. He's being lent out to us while on the bench, expecting to remain on the CLI team next month but unclear how long until Labs needs him back.


## Java Utilities

...

## CI Tooling

...
