# Utilities PMC Meeting 2015-05-19

## Agenda

1. Update on CI tools (Mike Dalessio)
2. Update on CLI (Greg Oehman)
3. Update on Eclipse plugin and Java tools (Ryan Morgan)
4. Proposal to move `pivotal-cf-experimental/jibber_jabber` into `cloudfoundry-incubator`
5. Incubating HP projects: Next steps
6. Open Discussion


## Attendees

- Chip Childers, Cloud Foundry Foundation
- Mike Dalessio, Pivotal (PMC lead)
- Gert Drapers, HP
- Ryan Morgan, Pivotal


## Update on CI tools (Mike Dalessio)

The Toolsmiths team is considering two new tracks of work:

__"krafa"__ is a simple web server and CLI tool used to manage a pool
of CF environments. Pipelines can "reserve" an environment for the
duration of its build, and then release it back into the
pool. Environments can have tags that can be filtered against in a
reservation query.

We're also considering a track of work that would examine a project's
source tree, discover dependencies (and locked versions of those
dependencies), and then check a NIST database for vulnerabilities in
those dependencies. This may end up as a docker image that can be
added to a Concourse pipeline, and may be extended to include other
security checks.

Chip suggested that we should talk to Intel about their tools as
well. Chip will try to find the right contact there for a
conversation.

Gert asked about code-style enforcement tools on C# projects. He will
send some information on what HP is using.


## Update on CLI (Greg Oehman)

Agenda item skipped, as both Greg and Michael Fraenkel are traveling.


## Update on Eclipse plugin and Java tools (Ryan Morgan)

* Eclipse tooling 1.8.2 released last week, enabling JRebel remoting. Was demoed at summit.
  - Video is being made to explain how to use JRebel with a CF app. URL forthcoming when it's done.

* Proposal for moving the plugin to the Eclipse Foundation has been completed, awaiting input from Chip.

* Started work on what will be the 1.8.3 release
  - Exploring using Diego SSH access to debug without a sidecar process.


## Proposal to move `pivotal-cf-experimental/jibber_jabber` into `cloudfoundry-incubator`

`jibber_jabber` provides i18n support to the CLI. It's being proposed to incubate it.

Chip weighed in that we're still unwinding things from the Foundation
spinout, so let's just move it in and move on.

Action item:

- [ ] Mike will move this repo into `cloudfoundry-incubator`


## Incubating HP projects: Next steps

Several repositories are being incubated as of CF Summit:

* [Visual Studio plugin][vsp]
* [MSBuild tasks][msbuild]
* [.NET SDK][sdk]

After some discussion, it was decided to put all three repos under a single umbrella project.

  [vsp]: https://github.com/cloudfoundry-incubator/cf-vs-extension
  [msbuild]: https://github.com/cloudfoundry-incubator/cf-msbuild-tasks
  [sdk]: https://github.com/cloudfoundry-incubator/cf-dotnet-sdk

Chip provided some context around what a "project" is, in that he
views it as a backlog of work, and not necessarily a 1-to-1
relationship with a code repository.

HP's team will work via a distributed committer model for the time
being. Gert will provide details around who is the PM, and who the
approved committers are. Mike will create a public Pivotal Tracker
project, and Chip will create a Github team for the repositories.

HP will maintain downstream forks of the incubating repositories for
now, so that they can sign their binaries for their product.

Action Items:

- [ ] Gert to provide a list of approved committers
- [ ] Mike Dalessio to create a public Tracker project and add people
- [ ] Chip to create a Github team to commit to the cf-incubator org repositories


## Open Discussion

No other topics raised.
