# Buildpacks PMC Meeting 2015-06-15

## Agenda

1. Update on Java Buildpack (Ryan Morgan)
2. Update on core Buildpacks (Mike Dalessio)
3. Open Discussion


## Attendees

* Chip Childers, Cloud Foundry Foundation
* Alex Tarpinian, IBM
* Michael Fraenkel, IBM
* Ruben Koster, Stark and Wayne
* Ryan Morgan, Pivotal
* Mike Dalessio, Pivotal
* "call-in user 2"


## Update on Java Buildpack (Ryan Morgan)
* Investigation on an OOM issue raised on cf-dev: https://www.pivotaltracker.com/story/show/94381284
* Spike on Lunk SDK integration (Hardware security device from SafeNet): https://www.pivotaltracker.com/story/show/96530962
* Next release will be 3.1, likely by the end of June.

## Update on core Buildpacks (Mike Dalessio)

__Tracks__

* Started taking over maintenance of [rootfs][stacks]
* Working on building CF-specific binaries.
* Moved to Concourse. Will be made public shortly.
* [upcoming] Will soon be removing support for lucid64 rootfs.

Some discussion with Michael Fraenkel about the timing of removal of
lucid64 from `cf-release`, and whether this impacts the buildpacks
work. We'll loop up with Dieu in the Runtime PMC tomorrow.


__Releases__

* Released [staticfile-buildpack][static] which eliminates the static linking of libpcre3 in the expectation of an upstream patch for CVE-2015-3210 to rootfs.
* Released [python-buildpack][python] which updates to [python 2.7.10][pyrelease]
* Released [php-buildpack][php] which includes some security improvements and updates to PHP interpreters.
* Released [nodejs-buildpack][nodejs] which updates to nodejs 0.12.4.

  [stacks]: https://github.com/cloudfoundry/stacks
  [static]: https://github.com/cloudfoundry/staticfile-buildpack/releases
  [python]: https://github.com/cloudfoundry/python-buildpack/releases
  [pyrelease]: https://hg.python.org/cpython/raw-file/15c95b7d81dc/Misc/NEWS
  [php]: https://github.com/cloudfoundry/php-buildpack/releases
  [nodejs]: https://github.com/cloudfoundry/nodejs-buildpack/releases

Michael Fraenkel noted that he submitted a small PR to
`binary-buidpack`, which Mike Dalessio will review ASAP.


## Open Discussion

No additional topics were covered.
