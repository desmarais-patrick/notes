# Google Cloud App Engine with Node.js

## Structuring the app

A `app.yaml` file at the root is necessary for an App Engine service.
This file describes the *default* service.
Optional files are:

 - `service1.yaml` when additional service is in same directory.
 - `dispatch.yaml` when special routing.
 - `cron.yaml`
 - `index.yaml`

Tips for robust service:

 - Fast to start
 - Stateless
 - Checkpoints for long computations (maybe not Node.js 😅)
 - Use queues when asynchronous

An app engine's service responsibility is to start a server and handle requests. It must listen to the port given by `process.env.PORT`.

Limitations:

 - Maximum number of requests
 - Maximum request and response sizes (32MB)
 - No piping (only one HTTP response)
 - 60 seconds to reply


## Inter-Service Communication

When there are multiple services, one can use various URLs to create target HTTP requests:

```
http://[VERSION_ID].[SERVICE_ID].[MY_PROJECT_ID].appspot.com
https://[VERSION_ID]-dot-[SERVICE_ID]-dot-[MY_PROJECT_ID].appspot.com
```

An alternative is to use *Cloud Pub/Sub*.


## Routing

Soft routing is applied to the default service when no custom domain is set.
`dispatch.yaml` tells how to send requests with custom domain, or just to a specific version (see [Versions page](https://console.cloud.google.com/appengine/versions?project=_&serviceId=default&_ga=2.228443805.-1864672417.1555958817&_gac=1.254420602.1557936691.CjwKCAjw8e7mBRBsEiwAPVxxiJoS9pnv8hPJyGsaagApuhx46NxOQeLOmtGuYDd7ljCIrszvJHKdhRoCfvsQAvD_BwE) in Google Cloud Console).

Dispatch file is deployed separately.

More information about [mapping custom domains](https://cloud.google.com/appengine/docs/standard/python/mapping-custom-domains).


## Runtime

While many web services can be deployed from multiple app.yaml file names, Node.js applications generally use the following line:

```
runtime: nodejs10
```

More information about [runtime settings](https://cloud.google.com/appengine/docs/standard/nodejs/configuring-your-app-with-app-yaml) and [difference between flexible and standard environment](https://cloud.google.com/appengine/docs/flexible/go/flexible-for-standard-users).

## Dependencies

Node.js dependencies are treated with `yarn` and automatically installed when deploying.

Packages are cached to avoid re-installs, but this cache can be avoided when deploying.


## Deployment

To deploy an app using the Admin API, one must upload the source code to a Cloud Storage bucket.


## References

### Getting Started

 * [Hello-world](https://cloud.google.com/nodejs/getting-started/hello-world)
 * Node.js Bookshelf App
   * [Intro & setup](https://cloud.google.com/nodejs/getting-started/tutorial-app)
   * [Datastore](https://cloud.google.com/nodejs/getting-started/using-cloud-datastore)

### Examples

 * Run Express.js on Google App Engine Flexible Environment - 
   Good example for a simple hello-world app. - 
   https://cloud.google.com/community/tutorials/run-expressjs-on-google-app-engine
 * Source code the GCP with Node.js - https://github.com/GoogleCloudPlatform/nodejs-docs-samples
   * Node.js with standard App Engine starter - https://github.com/GoogleCloudPlatform/nodejs-docs-samples/tree/master/appengine/building-an-app/build
 * Source code for the CodeLabs - https://github.com/googlecodelabs/cloud-nodejs

### Documentation

 * `app.yaml` and [runtime settings](https://cloud.google.com/appengine/docs/standard/nodejs/configuring-your-app-with-app-yaml)
 * Beta commands and datastore emulator [flags](https://cloud.google.com/sdk/gcloud/reference/beta/emulators/datastore/)
