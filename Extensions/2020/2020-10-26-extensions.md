# CF Extensions PMC Notes

*Chat room:* go to [slack.cloudfoundry.org](https://slack.cloudfoundry.org) and then join the `#cf-extensions` channel

## Zoom info

https://zoom.us/j/656963476

Meeting ID: 656 963 476

One tap mobile
+16699006833,,656963476# US (San Jose)
+16465588656,,656963476# US (New York)

Dial by your location
        +1 669 900 6833 US (San Jose)
        +1 646 558 8656 US (New York)
        855 880 1246 US Toll-free
        877 369 0926 US Toll-free
        +1 647 558 0588 Canada
        855 703 8985 Canada Toll-free
Meeting ID: 656 963 476
Find your local number: https://zoom.us/u/abSAPsJbM

## New business

None.

## Updates

### Stratos 

### MultiApps 

#### New Features

- You can deploy multiple instances of one and the same MTA in a single cloud foundry space. To do so, specify an MTA namespace when starting the deployment and observe the results. Try out the example to get a hands-on experience.
- Use service-broker parameter to specify which broker to use for service creation. Dedicated for use when two brokers provide matching service offerings and plans.
 
#### Changes

- MTA detection is done from CF Metadata. Previous mechanism to read app env is retired completely. This is a major optimization for spaces with many apps and spaces.
- Service bindings/unbindings are now done in parallel.  Again major optimization for overloaded spaces with applications with many bindings
- New approach for blue-green deployment using strategy flag is not experimental anymore. Legacy blue-green deployment approach will be deprecated soon.
 
#### Bugfixes

- Improved error message when attempt to create service instance with external configuration file that is not valid JSON format. See the exact error, not the ugly one: `Error while converting JSON input stream to map`
- Fixed error handling when empty (0 bytes) extension descriptor is used
- Fixed issue during application upload: `CF-ResourceNotFound(10010): Package not found`
- Running a partial deployment with blue-green strategy led to renaming all applications to <name>-live regardless they were selected for deployment
- Fix deployments failing with “Couldn't deserialize object in variable 'logsOffset'”
- Fix failing MTA operations when a service instance is manually deleted and its corresponding resource is removed from the MTA `Error: Controller operation failed: 404 Not Found: Service instance <SERVICE_NAME> not found.`

#### Migration to Java 11 and adoption of new dependency versions

- Adopt JPMS and other new features coming with Java 11
- Replace deprecated Spring Cloud libraries. Used for data source creation (connection pooling, etc.). This includes the introduction of a new, more performant, connection pool (HikariCP)
- Fix code coverage report mechanism for SonarCloud
- Replace deprecated Spring client (RestTemplate)
