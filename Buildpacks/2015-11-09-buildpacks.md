# Buildpacks PMC Notes as of 2015-11-09

The last set of notes were sent out on 2015-10-12

## Table of Contents

1. Update on Stacks
2. Update on Buildpacks
  1. General
  2. go-buildpack
  3. java-buildpack
  4. nodejs-buildpack
  5. php-buildpack
  6. ruby-buildpack
  7. staticfile-buildpack


## Stacks

We've been continuing to make updates to the cflinuxfs2 rootfs at least weekly, with additional turnaround of CVE updates within 48 hours.

### Releases

Released cflinuxfs2 versions [1.10.0][], [1.11.0][], [1.12.0][], [1.13.0][], [1.14.0][], and [1.15.0][], addressing:

[USN-2788-1](http://www.ubuntu.com/usn/usn-2788-1) "unzip vulnerabilities", which is related to:

* CVE-2015-7696 "Heap buffer overflow when extracting password-protected archive"
* CVE-2015-7697 "Infinite loop when extracting password-protected archive"

[USN-2787-1](http://www.ubuntu.com/usn/usn-2787-1), "audiofile vulnerability", which is related to:

* CVE-2015-7747 "made to crash or run programs as your login if it opened a specially crafted file"

[USN-2767-1](http://www.ubuntu.com/usn/usn-2767-1), "GDK-PixBuf vulnerabilities", which is related to:

* [CVE-2015-7673](http://people.canonical.com/~ubuntu-security/cve/2015/CVE-2015-7673.html) "Heap overflow and DoS with a tga file in gdk-pixbuf < 2.32.1"
* [CVE-2015-7674](http://people.canonical.com/~ubuntu-security/cve/2015/CVE-2015-7674.html) "Heap overflow with a gif file in gdk-pixbuf < 2.32.1"


  [1.15.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.15.0
  [1.14.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.14.0
  [1.13.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.13.0
  [1.12.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.12.0
  [1.11.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.11.0
  [1.10.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.10.0


## Buildpacks

### General

Continuing on the track of work to provide a ["chain of custody"][] for everything shipped in the buildpacks, each buildpack released is now published with a SHA256 checksum in the release notes.

  ["chain of custody"]: https://www.pivotaltracker.com/epic/show/2077742


### go-buildpack

#### Releases

Released [v1.6.3](https://github.com/cloudfoundry/go-buildpack/releases/tag/v1.6.3) adding support for Go 1.4.1 for upgrade paths, adding a Godep binary to the manifest, and supporting the linker's -X option format for go1.5.


#### Proposals

In the last set of PMC notes, a proposal to drop golang v1.2.x and v1.3.x was proposed and no objections were raised. We'll be scheduling work on this over the next few weeks.


#### Notes

We're also in the process of sending pull requests back upstream to `godep` and to the `go-buildpack` to allow "wildcarding" of golang versions, meaning that "1.4.*" would use the most recent matching golang version. This would make more palatable the "skinny buildpack" policy of only providing the two most-recent supported versions on a major/minor branch. See [GH#22][] for details.

  [GH#22]: https://github.com/cloudfoundry/go-buildpack/issues/22



### java-buildpack

#### Releases

Released [v3.3.1](https://github.com/cloudfoundry/java-buildpack/releases/tag/v3.3.1). This release contains a new debug framework and ensures that the dependencies contained in the `offline` buildpack are up to date.



### nodejs-buildpack

#### Releases

Released [v1.5.1](https://github.com/cloudfoundry/nodejs-buildpack/releases/tag/v1.5.1), which adds support for Node 4.2.x LTS, emits buildpack details from `bin/detect`, and merges many commits from upstream.


#### Proposals

In the last PMC notes, it was proposed to [add node.js 4.x support](https://github.com/cloudfoundry/nodejs-buildpack/issues/32) via static linking of dependencies. This work was completed and shipped in nodejs-buildpack v1.5.1 as noted above.


### php-buildpack

#### Releases

Released [v4.2.1](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.2.1), [v4.2.0](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.2.0), and [v4.1.5](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.1.5), which collectively update nginx to v1.9.6, update httpd to 2.4.17, add support for PHP 5.6.16 and 5.5.30, and drop support for PHP 5.4.x (which has been EOLed).


#### Proposals

In the last PMC notes, it was proposed to [remove nginx 1.6](https://github.com/cloudfoundry/php-buildpack/issues/109) from the buildpack, but continuing to support nginx 1.8 and 1.9, and no objections were raised. We'll schedule work on this change.


### ruby-buildpack

#### Releases

Released [v1.6.8](https://github.com/cloudfoundry/ruby-buildpack/releases/tag/v1.6.8), which updates JRuby to 9.0.3.0, and updates OpenJDK to 1.8.0_65.


### staticfile-buildpack

#### Releases

Released [v1.2.2](https://github.com/cloudfoundry/staticfile-buildpack/releases/tag/v1.2.2), which improves error messages and log messages, and emits buildpack details from `bin/detect`.


#### Notes

Some performance analysis was done of the staticfile-buildpack after cf-release v221's increase to `ip_conntrack_max`, and the results may be interesting to readers. Details are [in this tracker story](https://www.pivotaltracker.com/story/show/105014548), but the TL;DR is that we saturated the testing network before we hit any nginx bottlenecks. Peak performance for 1KB payloads was in excess of 1400 requests/second.
