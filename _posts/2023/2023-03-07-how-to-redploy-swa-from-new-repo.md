---
title: How to deploy to a new SWA from a GitHub repository
author: matt
categories: [public]
tags: [technology]
date: 2023-08-02 14:00:00 
updatedBy: jeny
updated: 2023-04-17 22:35:44 
likes: 8
---

## Create new SWA from GitHub repository

Create a new Azure Static Web App as described [here](https://learn.microsoft.com/en-us/azure/static-web-apps/publish-jekyll).

## Configure callback url on App Registration

- Navigate to the Azure portal
- Select "Azure AD B2C"
- On the left hand menu under "Manage", select "App Registrations"
- Select the App Registration configured for the previous SWA
- On the left hand menu under "Manage", select "Authentication"
- Change the "Redirect URIs" url to refere to the url of the new SWA's url.

## Ensure the configuration from the existing GitHub action is moved across to the new Github action

It took some time to craft our initial Action to suit all our needs so ensure this information is not lost. Creating the new SWA and linking it to the new repository will ensure a new Action yaml file will get created under the .github/workflows folder. Move the content from the original file across to the new one.

## SWA: Upgrade tier, then configure identity

In order to configure authentcation the SWA has to be upgraded from a Free tier to a Standard tier.

- Navigate to the Azure portal
- Select the new SWA
- On the left hand menu under "Settings", select "Hosting Plan"
- Select "Standard" tier and click "Save"

Once this has been done refer to this [post](/technology/configure-azure-keyvault/) and follow the instructions under "Add an Access policy for the SWA"

## Ensure App configuration values are copied across.

-- Ensure all Application Settings are copied across from one SWA to the other. 

## Ensure swa-cli.config.json has he correct SWA name in it.

Ensure the value in the file "swa-cli.config.json" under he node "configurations" matches the name of the repository.