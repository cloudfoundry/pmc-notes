# Buildpacks PMC Meeting 2015-05-04

## Agenda

1. Recent Inception Report; Stated Goals and Risks
2. Current Backlog and Priorities
3. Proposal: Buildpack Incubation Process
4. Open Discussion


## Attendees

* Chip Childers, Cloud Foundry Foundation
* Mike Dalessio, Pivotal (PMC lead)
* Christopher Ferriss, IBM
* Michael Fraenkel, IBM
* Mark Kropf, Pivotal


## Recent Inception Report and Stated Goals

The Buildpacks core development team held a project inception on 2015-04-20, to gain a shared understanding of upcoming goals and tracks of work.

### Goals

* Expand supported ecosystem to include more languages & frameworks
* Cloud Foundry ownership of Buildpacks
* Leverage new primitives in Diego (“app lifecycle”)
* Enable 3rd party extensions to the Developer experience
* Enable application developer extensions to the Developer experience
* Set patterns for creating new buildpacks and for extending the Developer experience
* Generate clearer diagnostics during staging
* Enable Operator ease of updating common dependencies
* Keep the `bin/detect` experience: buildpacks should Just Work™
* Exert more ownership over the rootfs
* Binary buildpack support

### Risks

* java-buildpack is diverging quickly from the core buildpacks
* Lack of deep experience in some ecosystems
* Wide variety in implementations across buildpacks
* rootfs: with great power comes great responsibility (e.g., security response)
* tight coupling between buildpacks and rootfs
* versioning between buildpacks and rootfs


## Current Backlog and Priorities

See the Tracker backlog here: https://www.pivotaltracker.com/n/projects/1042066

Notable near-term goals:

* staticfile-buildpack support in `cf-release`
* binary buildpack (a.k.a. “null buildpack”) support in `cf-release`
* ability to generate and test CF rootfs-specific binaries; and tooling for CF operators to do the same


## Proposal: Buildpack Incubation Process

Discussion today for PMC input; a draft document will be circulated
for comment to cf-dev@ mailing list after the meeting, in a separate
thread.
