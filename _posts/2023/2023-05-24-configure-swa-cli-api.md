---
title: Configuring local Azure Function Apis for Azure SWA
author: matt
categories: [public]
tags: [getting-started,cloud,api]
date: 2023-05-24 12:30:00 
likes: 14
---

When running your SWA site in a local development environment, you may be incorporating Apis using Azure serverless functions under the covers, and getting these running locally can be a challenge. In a lot of cases authentication relies on local Apis to work as well.

Here is how to get up and running.

## Install and configure SWA CLI

To run your frontend app and API together locally, Azure Static Web Apps provides a CLI that emulates the cloud environment. The CLI uses the Azure Functions Core Tools to run the API.

### Install command line tools

```
npm install -g @azure/static-web-apps-cli
```

### Start the API server

Open a new Node console, browse to your projects Api folder and run the following:

```
func host start --csharp
```

### Start the CLI

Then in your VS Code terminal window, browse to the root of your project and run the following:

```
swa start http://localhost:4000 --run "jekyll serve" --api-location ./api --api-devserver-url http://localhost:7071
```

Allow the local servers to fire up and then browse to http://localhost:7071 to test your SWA!

## Authenticate locally using SWA Auth

If you have configured authenticaion using Azure B2C then clicking on your "Sign in" button or link will take you to a local sign in test page:

![Azure B2C test authentication page](/images/azure-b2c-test-page.png)

Here you can edit some default values including:

* User ID
* Username
* User's roles
* User's claims

Click "Login" and happy testing!