# Buildpacks PMC Notes as of 2015-09-09

## Table of Contents

1. Update on "Offline" PMC Discussion
2. Update on Stacks
3. Update on Buildpacks
  1. General
  2. go-buildpack
  3. php-buildpack
  4. ruby-buildpack
  5. java-buildpack
4. Post-mortem on java-buildpack Certificate Expiration Incident


## Update on "Offline" PMC Discussions

In the previous PMC meeting, held on 2015-07-27, the Buildpacks PMC agreed to tentatively stop conducting regular synchronous meetings, and instead move to an "offline" model where discussions and, if necessary, voting would be conducted on the public cf-dev@ mailing list.

As part of this change, the PMC Lead (that's me!) committed to sending regular status updates to the mailing list in lieu of meeting notes. In this aspect, I failed over the last month, and I apologize for the resulting lack of transparency.

Going forward, I'll return to a two-week cycle of email updates for this PMC.

Please reach out to me or Chip if you have concerns over continuing the "offline" model for the Buildpacks PMC.


## Update on Stacks

[cflinuxfs2 v1.2.0][] through [cflinuxfs2 v1.7.0][] were released ([all cflinuxfs2 releases][]), reflecting the team's focus on regular releases and short turnaround times for CVEs.

  [cflinuxfs2 v1.2.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.2.0
  [cflinuxfs2 v1.7.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.7.0
  [all cflinuxfs2 releases]: https://github.com/cloudfoundry/stacks/releases

One notable addition to the rootfs is the utility [jq][]. `jq` is commonly vendored in custom buildpacks to parse CF environment variables (such as `VCAP_SERVICES`). It's also used in the `go` buildpack to parse `Godeps.json`. Adding `jq` to the rootfs is intended for use by future buildpacks, to obviate the need to vendor a binary version of it.

  [jq]: https://stedolan.github.io/jq/

Another notable change was introduced in [cflinuxfs2 v1.4.0][], which makes it incompatible with Warden from cf212 and earlier. This change was unfortunately necessary to support Garden and Diego. The release notes contain instructions on how to modify Warden and cf-release if you need to backport later rootfses into earlier cf-releases.

  [cflinuxfs2 v1.4.0]: https://github.com/cloudfoundry/stacks/releases/tag/1.4.0


## Update on Buildpacks

### General

Research continues on how to improve the state of extensibility for Buildpacks. Tracker stories and their results are available in the ["architecture" epic][].

  ["architecture" epic]: https://www.pivotaltracker.com/epic/show/1898760


### go-buildpack

[go-buildpack v1.6.0][] and [go-buildpack v1.5.0][] were released. These versions notably add support for golang 1.5.0, remove support for golang 1.1.x, update [godep][], and remove the vendored python interpreter.

  [go-buildpack v1.6.0]: https://github.com/cloudfoundry/go-buildpack/releases/tag/v1.6.0
  [go-buildpack v1.5.0]: https://github.com/cloudfoundry/go-buildpack/releases/tag/v1.5.0
  [godep]: https://github.com/tools/godep


### php-buildpack

[php-buildpack 4.1.2][] was released. This version notably makes a non-backwards compatible change to composer detection, updates nginx to 1.9.3, and bumps the supported PHP versions to 5.6.12, 5.5.28 and 5.4.44.

  [php-buildpack 4.1.2]: https://github.com/cloudfoundry/php-buildpack/releases/tag/v4.1.2

We expect to release 4.1.3 this week with further updates to supported PHP versions and nginx version.

A short survey was sent to cf-dev@ this week to evaluate whether, and how, to support HHVM going forward. Please respond if you're a PHP user. ([survey link][])

  [survey link]: https://docs.google.com/forms/d/1WBupympWFRMQnoGZAgQLKmUZugreVldj3xDhyn9kpWM/viewform?usp=send_form

Finally, a note that PHP 5.4.x will reach End Of Life on 2015-09-14 (that's next week). Beginning with php-buildpack v4.1.3, deprecation warnings will be emitted upon staging apps that use PHP 5.4. We intend to remove PHP 5.4.x support from the php-buildpack within a month after EOL.


### ruby-buildpack

[ruby-buildpack v1.6.2][] through [ruby-buildpack v1.6.7][] were released. Notably, these versions add support for JRuby 9.0.1.0 and 1.7.22, Ruby 2.2.3, 2.1.7 and 2.0.0-p647, openjdk 1.8.0_51, and sets the default Ruby version to 2.2.3.

  [ruby-buildpack v1.6.7]: https://github.com/cloudfoundry/ruby-buildpack/releases/tag/v1.6.7
  [ruby-buildpack v1.6.2]: https://github.com/cloudfoundry/ruby-buildpack/releases/tag/v1.6.2



### java-buildpack

[java-buildpack v3.1.1][] was released on July 30th, which updates dependencies.

The java-buildpack team has also committed changes to `master` to add zero-touch support for Safenet Luna HSMs, and to make a number of improvements to the Java memory calculator.

  [java-buildpack v3.1.1]: https://github.com/cloudfoundry/java-buildpack/releases/tag/v3.1.1


## Post-mortem on java-buildpack Certificate Expiration Incident

On 2015-08-31, between 1300 UTC and 1554 UTC, applications failed to stage that rely on an "online" (or "uncached") version of the java-buildpack, or an "online" version of the ruby-buildpack who are using JRuby.

The root cause of this incident was the expiration of the SSL certificate for `download.run.pivotal.io`, which is a domain used to front the artifacts downloaded by the java-buildpack.

Two aspects of this incident were focused on during a post-mortem on 2015-09-09, to which Chip and Sam were invited.

 1. __The certificate was allowed to expire__
 2. __An open-source buildpack is relying on a Pivotal-managed domain and SSL certificate__

The first aspect resulted in Pivotal-internal action items to centralize cert management and to require an escalation policy for each cert. These are perhaps uninteresting to most readers, but I'm happy to provide more detail on request.

The second aspect is being addressed in part by [this Tracker story][] to move to a Foundation-managed domain and cert.

  [this Tracker story]: https://www.pivotaltracker.com/n/projects/788065/stories/102935172

Ben Hale and I will be working with Chip and the Foundation to remove the dependency on this domain as quickly as we can; and Pivotal is committing to maintaining that domain and cert so existing buildpacks will continue to work until users are migrated to updated versions.

One open question that was raised during the post-mortem: How can we better communicate urgent issues like this to the CF community? The cf-dev@ list tends to be a bit noisy, and isn't commonly used for urgent communications. If anyone has ideas for how we can better respond as a community, I'd love to hear your ideas.
