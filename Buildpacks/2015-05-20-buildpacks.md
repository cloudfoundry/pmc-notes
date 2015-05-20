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

The [binary buildpack][binary] was added into `cf-release` last week
([PR here][binary-pr]), and moved into the `cloudfoundry` github
org. This is the same idea as what's commonly called a "null"
buildpack, where developers can simply execute a binary at runtime.

The [staticfile buildpack][static] was added into `cf-release` last
week ([PR here][static-pr]), and moved into the `cloudfoundry` github
org. Originally created by Dr. Nic, this buildpacks allows a static
website to be published behind nginx, and for nginx to be configured
in a few interesting ways.

At long last, [skinny buildpacks][skinny] made it into `cf-release`
([PRs here][skinny-pr]). There was also some interesting discussion on
the mailing lists, both [old][skinny-thread1] and
[new][skinny-thread2].

Notable near-term goals:

* ability to generate and test CF rootfs-specific binaries; and tooling for CF operators to do the same
* work more closely with the java-buildpacks team

  [binary]: https://github.com/cloudfoundry/binary-buildpack
  [binary-pr]: https://github.com/cloudfoundry/cf-release/pull/677
  [static]: https://github.com/cloudfoundry/staticfile-buildpack
  [static-pr]: https://github.com/cloudfoundry/cf-release/pull/668
  [skinny]: https://github.com/cloudfoundry-incubator/buildpack-packager/issues/4
  [skinny-pr]: https://github.com/cloudfoundry/cf-release/pulls?utf8=%E2%9C%93&q=is%3Apr+buildpack+skinny+
  [skinny-thread1]: https://groups.google.com/a/cloudfoundry.org/forum/#!searchin/vcap-dev/addressing$20buildpack/vcap-dev/1HmGK4wU3Rc/lk186OOtdbMJ
  [skinny-thread2]: http://lists.cloudfoundry.org/pipermail/cf-dev/2015-May/000005.html


## Open Discussion

Mike D: Would someone from IBM like to talk about the ASP.NET/Mono buildpack?
