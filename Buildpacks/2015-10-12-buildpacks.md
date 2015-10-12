# Buildpacks PMC Notes as of 2015-10-08

The last set of notes were sent out on 2015-09-09

## Table of Contents

1. Update on Stacks
2. Update on Buildpacks
  1. General
  2. java-buildpack
  3. go-buildpack
  4. php-buildpack
  5. python-buildpack


## Stacks

### Releases

Released cflinuxfs2 [1.9.0](https://github.com/cloudfoundry/stacks/releases/tag/1.9.0) and [1.8.0](https://github.com/cloudfoundry/stacks/releases/tag/1.8.0), which address [USN-2740-1](http://www.ubuntu.com/usn/usn-2740-1), "ICU vulnerabilities" and [USN-2739-1](http://www.ubuntu.com/usn/usn-2739-1), "FreeType vulnerabilities".


## Buildpacks


### General

The Buildpacks team has been doing further experimentation with __extensibility__ for both developers and operators. Results can be seen in the public Tracker under the ["architecture" epic](https://www.pivotaltracker.com/epic/show/1898760).

The Buildpacks team has also been working on a feature track to allow end users of the core buildpacks to __verify the origin__ of all binaries vendored in the buildpack. This "chain of custody" track is intended to allow security-minded CF operators to trust the buildpack binaries being run in their deployment (and to regenerate the binaries themselves as needed). This work can be viewed in the public Tracker under the ["chain of custody" epic](https://www.pivotaltracker.com/epic/show/2077742).


### java-buildpack

#### Releases

Released java-buildpack [3.2](https://github.com/cloudfoundry/java-buildpack/releases/tag/v3.2) and [3.3](https://github.com/cloudfoundry/java-buildpack/releases/tag/v3.3).

These buildpacks add Luna HA support, as well as deliver improvements to the memory calculator.

Please view the [release notes](https://github.com/cloudfoundry/java-buildpack/releases) for full details.


### go-buildpack

#### Releases

Released go-buildpack [v1.6.1](https://github.com/cloudfoundry/go-buildpack/releases/tag/v1.6.1) and [v1.6.2](https://github.com/cloudfoundry/go-buildpack/releases/tag/v1.6.2).

These releases add support for golang 1.5.1 and golang 1.4.3, which addresses a number of CVEs in 1.4.2 and earlier. Support for golang 1.4.1 was dropped.

Please view the [release notes](https://github.com/cloudfoundry/go-buildpack/releases) for full details.


#### Proposals

__Proposal:__ It is being proposed to drop support for golang 1.2.x and 1.3.x. We're using a Github Issue as an RFC, so please comment here:

> https://github.com/cloudfoundry/go-buildpack/issues/22


### php-buildpack

#### Releases

Released [v4.1.5](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.1.5), [v4.1.4](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.1.4), and [v4.1.3](https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.1.3) which:

* updates to nginx 1.9.5,
* updates to PHP 5.6.14, 5.6.13, 5.5.30, 5.5.29, and 5.4.45.
* addresses USN-2740-1 "ICU vulnerabilities" (in combination with rootfs 1.9.0)

Please view the [release notes](https://github.com/cloudfoundry/php-buildpack/releases) for full details.


#### End of Life

__Please note that PHP 5.4 reached "End of Life" on 2015-09-14__. We intend to remove support for this version of PHP in the next release of the php-buildpack.


#### Proposals

__Proposal:__ It is being proposed to drop support for nginx 1.6 (but keeping support for nginx 1.8 and 1.9). We're using a Github Issue as an RFC, so please comment here:

> https://github.com/cloudfoundry/php-buildpack/issues/109


### python-buildpack

#### Releases

Released [v1.5.1](https://github.com/cloudfoundry/python-buildpack/releases/tag/v1.5.1) which adds support for Python 3.5.0.

Please view the [release notes](https://github.com/cloudfoundry/python-buildpack/releases) for full details.


### nodejs-buildpack

#### Proposals

__Proposal:__ It is being proposed to add Node 4.x support by statically linking against openssl 1.0.2. This introduces a requirement to restage applications running Node 4.x to address openssl CVEs. (Currently, only a rootfs update is needed for this scenario.) We're using a Github Issue as an RFC, so please comment here:

> https://github.com/cloudfoundry/nodejs-buildpack/issues/32
