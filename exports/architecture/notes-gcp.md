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


## Billing and Budgets

GCP allows management of payments through their console.
One can set soft limits, alerts to warn of excessive use based on budget.
However, it doesn't stop the service! 😬


## Questions

 - How can we have continuous integration with Github (or Google's code repository)?

 - Should the client app be stored on Google Storage or CDN solution?
   - What is a CND?
   - What are caching considerations?
   - Linked articles: [Understanding Data and File Storage](https://cloud.google.com/appengine/docs/standard/nodejs/using-third-party-databases), [Serving Static Files](https://cloud.google.com/appengine/docs/standard/nodejs/serving-static-files)


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
