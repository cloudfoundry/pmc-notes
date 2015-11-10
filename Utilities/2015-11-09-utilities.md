# Utilities PMC Notes as of 2015-11-09

The last set of notes were sent out on 2015-10-14


## Table of Contents

1. CLI
2. Java Utilities
3. CI Tooling


## CLI

Dies Köper, of Fujitsu, has taken over the PM responsibilities for the CLI team after completing a "PM Dojo" on October 29.

Dies has embarked on cleaning up the icebox (evaluating around 300 old stories) as well as going through open Github Issues and PRs.

Congratulations, and thank you, Dies!


### Releases

CLI v6.13.0 was released, which pulls Diego support into the main tool (i.e., the Diego plugin is no longer needed).


### Ongoing / Upcoming work

* Started implementing stories around [Organization and Space RBAC](https://www.pivotaltracker.com/epic/show/1991856).
* Started fleshing out stories upcoming around [CC v3 API](https://www.pivotaltracker.com/epic/show/2088038).
* Implemented a number of First Impressions stories:
- Simplification of the [Download page](https://github.com/cloudfoundry/cli#downloads) (making 64 bit installers and binaries more prominent than the edge and 32 bit releases)
- Examples on how to download them with curl
- Improved filenames (added release version in filename, etc.)


### Risks

* Team resource levels unstable, with one engineer added and two rolled off. This brings up the risk of loss of knowledge and context.
* Many days this fortnight we had only 1 engineer working (others were sick, on vacation, had jury duty calls). Low staffing to continue with anchor visiting upcoming CF Summits.



## Java Utilities

The CF Java client work has slowed down as the team ramps up on Concourse, but is continuing to proceed. Interested parties are invited to follow progress in [the Java Client backlog][jcbacklog].

  [jcbacklog]: https://www.pivotaltracker.com/n/projects/816799


## CI Tooling

No updates.
