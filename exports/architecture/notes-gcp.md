# Notes on Google Cloud Platform

Google Cloud Platform is sometimes abbreviated *GCP*.

Products:

 * App Engine
 * Compute Engine
 * Datastore
 * Cloud Storage
 * Cloud Scheduler
 * Google Domains and Cloud DNS

Tools and APIs:

 * Google Cloud SDK
 * Google Cloud Console
 * Google Identity Platform
 * StackDriver Trace
 * Cloud Pub/Sub
 * Cloud Source Repositories
 * Cloud Endpoints


## Billing and Budgets

GCP allows management of payments through their console.
One can set soft limits, alerts to warn of excessive use based on budget.
However, it doesn't stop the service! 😬


## Questions

 - How can we have continuous integration with Github (or Google's code repository)?

 - Should the client app be stored on Google Storage or CDN solution?
   - What is a CDN?
   - What are caching considerations?
   - Linked articles: [Understanding Data and File Storage](https://cloud.google.com/appengine/docs/standard/nodejs/using-third-party-databases), [Serving Static Files](https://cloud.google.com/appengine/docs/standard/nodejs/serving-static-files)

 - When should one move to *Compute Engine* or *Kubernetes*?
   - Are scaling and load-balancing required?
   - Dockerization seems to save a lot of Bash scripts.
   - Is clusterization required?

## Further Study Considerations

*Google Cloud SDK* and *Google Cloud Console*

This SDK and console have many options.
A tour could help use them better to boost deployment productivity.

*Google Identity Platform* 

It enables authentication with OAuth 2.0.
Using the Datastore, user sessions can be recorded.
Google user information can be used to complement information.

This tool could provide a good first authentication method.

*StackDriver Trace*

It enables tracing, logging, debugging and monitoring tools.
Critical issues and trends can be tracked from the Google Cloud Console.
Logs are sent as JSON to this API.

This tool could provide really useful information when deploying versions.

*Cloud Pub/Sub*

Workers can be created to handle topics and execute asynchronous tasks.
Workers can implement an `health/` endpoint to see how they are doing.

This tool could help process notes, and eventually augment them with attachments.

*Cloud Source Repositories*

It stores source code. It seems similar to a regular Git server repository.

*Cloud Endpoints*

API management software to secure, monitor, analyze, and set quotas.
It supports gRPC, OpenAPI and frameworks in AppEngine standard environment.

*Cloud Scheduler*

Frequency is configured with a unix-cron format (`* * * * *`).
The Getting-Started example used a Pub/Sub topic to drive scheduler tasks.
Other examples include hitting an endpoint using HTTP, such as for creating reports.

It offers 3 free jobs per month, with any additional job at 0.10$ each.

*Cloud DNS*

This service translates domain names to IP addresses.
It manages public and private zones.

It seems to be a solution for those providers of a SAAS product for example,
or to handle various servers across different regions.

*Google Domains*

In the Google Console, under Google App Engine, custom domains redirect to 
Google Domains.
Domains start at CA$13-17 per year for many domains.

An SSL certificate is automatically assigned and renewed for the instance.
There is also a tab for setting our own certificates.
