# Buildpacks PMC Meeting 2015-06-15

## Agenda

1. Update on Java Buildpack (Ryan Morgan)
2. Update on core Buildpacks (Mike Dalessio)
3. Open Discussion


## Attendees


## Update on Java Buildpack (Ryan Morgan)


## Update on core Buildpacks (Mike Dalessio)

__Tracks__

* Started taking over maintenance of [rootfs][stacks]
* Working on building CF-specific binaries.
* Moved to Concourse. Will be made public shortly.
* [upcoming] Will soon be removing support for lucid64 rootfs.


__Releases__

* Released [staticfile-buildpack][static] which eliminates the static linking of libpcre3 in the expectation of an upstream patch for CVE-2015-3210 to rootfs.
* Released [python-buildpack][python] which updates to [python 2.7.10][pyrelease]
* Released [php-buildpack][php] which includes some security improvements and updates to PHP interpreters.
* Released [nodejs-buildpack][nodejs] which updates to nodejs 0.12.4.

  [stacks]: https://github.com/cloudfoundry/stacks
  [static]: https://github.com/cloudfoundry/staticfile-buildpack/releases
  [pyrelease]: https://hg.python.org/cpython/raw-file/15c95b7d81dc/Misc/NEWS
  [php]: https://github.com/cloudfoundry/php-buildpack/releases


## Open Discussion
