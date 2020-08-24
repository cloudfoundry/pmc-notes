# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## Zoom info

Zoom meeting cancelled in favor of asynchronous updates on #cf-extensions

# Projects

## _Incubating_

### [MultiApps](https://github.com/cloudfoundry-incubator/multiapps-cli-plugin)

#### New Features
* We provide new MTA module hook deploy.application.before-start to enable more agile application lifecycle. Try out the simple example.
* You can use new system parameters org-guid or space-guid at your convenience. They are read-only and can be used everywhere in your descriptor
 
#### Bugfixes
* We did not update existing applications based on docker images when docker image or credentials are changed
* Improved error handling when user provided service has a parameter defined with a null value. We will not fail anymore with that strange error: `Error creating or updating application "my-app": credentials value`
* `${app-name}` was resolved wrongly and ended with -idle suffix when using --strategy blue-green
* Deployments failed when default domain is not present. For example, default domain could not exist but service creation is possible. Now we 