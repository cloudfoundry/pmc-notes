# Buildpacks PMC Meeting 2015-06-15

## Agenda

1. Update on Java Buildpack (Ryan Morgan)
2. Update on core Buildpacks and rootfs (Mike Dalessio)
3. Open Discussion


## Attendees

* Chip Childers, Cloud Foundry Foundation
* Mike Dalessio, Pivotal (PMC lead)
* Ryan Morgan, Pivotal
* ...


## Update on Java Buildpack (Ryan Morgan)

...


## Update on core Buildpacks and rootfs (Mike Dalessio)

__Recent work__

Released ruby-buildpack v1.6.0, php-buildpack v4.0.0, python-buildpack v1.5.0, nodejs-buildpack v1.5.0 and staticfile-buildpack v1.2.1, which all contain CF-specific precompiled binaries. (The go-buildpack uses Google-built binaries and we're OK with this.)

Released binary-buildpack v1.0.1 which contains Michael Fraenkel's PR for Diego compatibility.

Updates to all buildpacks to remove lucid64 binaries from manifests. Operators can use the buildpack tooling to generate these binaries and package their own buildpacks as they deem necessary. Note that as part of this effort, the [binary builder][] tooling was open-sourced.

Open-sourced [concourse CI pipelines][].

[Rootfs 1.1.0][] released. Note that rootfs releases are now given version numbers and have release notes, and the corresponding docker images are tagged with that version number.

The team has been working on a series of spikes intended to drive towards a technical solution for implementing shared behaviors (across buildpacks) into shared code. This work can be followed in the Tracker backlog in the [architecture epic][].


  [binary builder]: https://github.com/cloudfoundry/binary-builder
  [concourse CI pipelines]: https://github.com/cloudfoundry/buildpacks-ci
  [Rootfs 1.1.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.1.0
  [architecture label]: https://www.pivotaltracker.com/epic/show/1898760


__Upcoming work__

The team will be experimenting with extension points to the buildpack life cycle, for both operators and developers. Among the goals:

* allow extension of buildpack behavior by application developers without having to fork the buildpack
* allow extension of buildpack behavior by operators which is currently not possible

We'll also be trying focused sprints on individual buildpacks.


## Open Discussion

...

