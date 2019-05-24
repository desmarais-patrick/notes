# Deployment Process

This process uses *Google Cloud* to deploy instances using a standard *App Engine* configuration.

## Pre-requisites

**Google Cloud setup**

Before installing software locally, set up a [Google Cloud](link-to-console-to-add-here/) account (with billing enabled).

You may enable the *Datastore* API after creating *App Engine* project.
Take note of `PROJECT-ID`.

**Installed locally**

 * [Google Cloud SDK](https://cloud.google.com/sdk/docs/)
 * [Node.js](https://nodejs.org/en/download/)

**Google Cloud SDK setup**

To login to GCP services, from terminal, you may run:

```
gcloud auth application-default login
```

> P.S. If you're working with *Google Cloud Shell*, you may make sure that you're account is active and current project is set. The *Shell* is useful to run deployment steps with security, right into the Google Cloud infrastructure. However, similar steps can be completed locally using the *Google Cloud SDK*.

Useful commands:

 * `gcloud auth list`, to see which account is active.
 * `gcloud config list project`, to see which project is current.
 * `gcloud config set project <PROJECT_ID>`, to set current project.

**Code setup**

To install dependencies, from terminal, you may run:

```
npm install
```


**Code environment setup**

<!-- Not sure this config.json setup is necessary for now.
     I don't use specific account credentials.
     Unless I use this for documenting environment configurations. 
     config-dev.json, config-prod.json, config-test-empty.json config-test-prod-copy.json, config-test-random.json.
     Then in the npm scripts, I'd have a run with any of these configs. -->

Create and adapt your `config.json` file in order to set:

 * `projectId`
 * 

<!-- To set the environment you want to run in... -->

To start the app locally, from terminal, you may run:

```
npm start
```

To deploy the app into production, from terminal, you may run:

```
gcloud app deploy
```


<!-- TODO Development environment: Add note for Datastore emulator.
          https://cloud.google.com/datastore/docs/tools/datastore-emulator -->
<!-- TODO Development environment: Add section on initializing fixtures with emulator.
          https://cloud.google.com/datastore/docs/tools/emulator-export-import -->
<!-- TODO Add section on Cloud Scheduler for resetting database. -->
<!-- TODO Investigate usage of Google Cloud Repositories vs. Github. -->

<!-- Don't go into too much detail, as this will likely change in the future. Basically, use these steps to practice documentation and help digest information and process at a good level of abstraction. -->



## Steps

In [Google Cloud Console](link-to-console-to-add-here), create a project to get your `PROJECT_ID`.

 - Datastore
 - 