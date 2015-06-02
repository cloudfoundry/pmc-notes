# Utilities PMC Meeting 2015-05-19

## Agenda

1. Update on CI tools (Mike Dalessio)
2. Update on CLI (Greg Oehmen)
3. Update on Eclipse plugin and Java tools (Ryan Morgan)
4. Open Discussion


## Attendees


## Update on CI tools (Mike Dalessio)

- The Toolsmiths team will be shutting down the OSS GoCD pipeline,
  which was only servicing the CLI team (and they are moving to
  Concourse).

- The Buildpacks team has moved to concourse, and will be
  open-sourcing their pipeline configurations once the environment has
  been secured and it's not leaking credentials

- The Concourse team has started to put together some security
  recommendations for setting up a secure Concourse deployment, with
  particular attention to AWS configuration.



## Update on CLI (Greg Oehman)
* Ongoing work on service keys with Services team
* Finishing last details of Concourse migration
* Ongoing work on Plugin API (vetted plan/implementation with community at CF Summit CLI Open House - great experience)
* Reviving `cfhelp` refactoring work with Mike Long, IBM Designers.  Will be next feature after Plugin API

## Update on Eclipse plugin and Java tools (Ryan Morgan)
* Work on 1.8.3 progressing, mostly bug fixes.
* Completed a spike on Debugging a Java application via SSH.  Requires Diego and currently only works in bosh-lite.  Will be included in 1.8.3.  Story for this feature: https://www.pivotaltracker.com/story/show/94617426.

## Open Discussion
