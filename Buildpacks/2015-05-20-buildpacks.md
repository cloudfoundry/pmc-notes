# Buildpacks PMC Meeting 2015-05-20

## Agenda

1. Update on Java Buildpack (Ryan Morgan)
2. Update on core Buildpacks (Mike Dalessio)
3. Open Discussion


## Attendees


## Update on Java Buildpack (Ryan Morgan)

* Added support for Wily Introscope.
* Memory calculator re-written in Go and supports java memory
  configuration at startup time rather than staging time. Some details
  on this feature were posted to cf-dev by Chris Frost last week.
* Team currently discussing how to 'pin' buildpack dependency versions
  to allow for repeatable offline buildpack creation.
* Team also discussing moving from Jenkins to Concourse for CI.

Mike will follow up with the team to discuss how `buildpack-packager`
might be used to pin cached dependencies.


## Update on core Buildpacks (Mike Dalessio)


## Open Discussion
