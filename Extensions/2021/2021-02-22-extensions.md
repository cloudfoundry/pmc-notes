# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## New business

Updates via Slack this month. No live meeting.

## Updates

### MultiApps 

Since the last one, we did some improvements both functionality & non-functional:

Capabilities:

* Service bindings to applications are now processed in parallel. This should be a substantial performance improvement for apps consuming multiple service instances, especially if some of their borkers are taking their time to provision credentials
* A flag for controlling the bindings parallelisation is available - if you need bindings created in a particular order, you can use it
* You can use empty host for application routes. To achieve this, specify option no-hostname: true for every route under the routes parameter. Checkout the example
* When MTA is deployed in a namespace, the namespace is used for default hostname generation. If you want to disable that behavior use apply-namespaceflag on route level. Try out it and other examples for deployment in namespace
* Deploy MTA directly from URL without the need to have it locally. The feature can be used with command “cf deploy” and directly by calling our REST API. Check out the simple CLI example

Non-functional improvements:

* migrated codebase to java11
* replaced some deprecated spring cloud libs ( RestTemplate, the DB connection pool etc.)
* Implemented Cloud Foundry Java client integration test that will grant smooth adoption of new CF Controller API (v3) without breaking changes
* Introduced response timeout for HTTP requests to Cloud Controller. It will mitigate the problem with the failures of Cloud Controller VMs and never-ending HTTP calls. The main advantage of that is the mitigation of increasing DB locks and eventual service down.
* Introduced new custom metric in Dynatrace which will track the interactions with the Cloud Controller. It will reveal heavy and timely consuming operations with Cloud Controller. The potential advantages will be detection of Controller delay and optimized logic on our side
* Optimized performance for commands mtas and mta. The delay in MTA detection was sensible in overloaded spaces with multiple services, like CPI
* Several performance improvements around service binding lifecycle operations
* Improved network resilience in the latest version of multiapps CLI plugin
* mics

BugFixes:

* Fix deployments failing with: Couldn’t deserialize object in variable ‘logsOffset’
* Fix failing MTA operations when a service instance is manually deleted and its corresponding resource is removed from the MTA: Controller operation failed: 404 Not Found: Service instance <SERVICE_NAME> not found.
* Fix deployments failing with: org.flowable.job.api.JobNotFoundException: No job found with id ‘xxx’
* Fix failing MTA operations witwhich delete high number of services. There problem occurs sometimes when there were 50 services to delete and always when they were 100
* Service binding parameters that are defined in the MTA descriptor were not considered during deployment. Now all available methods for defining service binding parameters are working
* Resolved rare Out of Memory of JVM Metaspace
* Parameters keep-existing and keep-existing-routes did not take effect in the new blue green deployment approach, provided by --strategy option



