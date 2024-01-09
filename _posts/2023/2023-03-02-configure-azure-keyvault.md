---
title: How to create and configure Azure KeyVault for a SWA
author: matt
categories: [public]
tags: [technology]
date: 2023-02-03 12:00:00
updatedBy: jeny
updated: 2023-05-08 06:09:18
likes: 0
---

## Create the Azure KeyVault

First ensure all sensitive configuration data is identified and added to Azure KeyVault. This is an encrypted store which can be referenced from the Azure Static Web App settings.

As well as creating the KeyVault, it will need to have access policies configured so values can be read from the SWA itself.

* Create the Keyvault (use a naming convention appropriate for the application, e.g. 'kv-dev-portal')
* Ensure Region is Australia Southeast, Pricing tier is Standard.
* Open the KeyVault properties in Azure
* Under "Settings", click on "Access policies"
* Check "Azure Resource Manager for template deployment"
* Under Permission model leave "Vault access policy" as default.

### Add an Access policy for the SWA

* Browse to your SWA in the Azure Portal.
* From the left menu, click "Identity"
* Under system-assigned tab, toggle the Status field on as shown below. This should show a GUID and button below. Then click the Save button to save the newly generated identity.
* Copy the newly created Object Id.
* Browse back to the Key Vault.
* Click "+ Add Access Policy"
* Search for the Object Id and select it.
* Select Key permissions "Get, List"
* Select Secret permissions "Get, List"
* Save changes.

### Adding secrets to KeyVault

Now all is in readiness for adding the following values to Azure KeyVault.

* On the left hand menu, click on "Secrets"
* On the top menu, click "Generate/Import"
* Enter the name and value of the secret, click "Create"

Generated secrets/passwords using a Node.js command prompt:
Secrets:
```
node -e "console.log(require('crypto').randomBytes(256).toString('base64'));"
```
Passwords: 
```
node -e "console.log(require('crypto').randomBytes(64).toString('base64'));"
```
