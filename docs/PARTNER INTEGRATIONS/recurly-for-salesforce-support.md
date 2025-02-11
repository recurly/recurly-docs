---
title: Recurly for Salesforce support
excerpt: >-
  If you are having any issues with your Salesforce integration, the first place
  to investigate is the "Recurly Logs" object within the Salesforce managed
  package. This section includes information about which API calls were made to
  Recurly, whether they were successful or unsuccessful, and more detailed
  information about failed calls.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Recurly to Salesforce Sync Errors

When there are errors with the Recurly to Salesforce sync, the API will attempt to re-sync the failed data automatically. For example, if an invoice is unable to be synced, the integration will attempt to re-sync when it runs next. These messages will appear in the **Recurly Logs** tab in the Recurly for Salesforce application.

To run a report about these errors, a folder called "Recurly Reports" has been created in Reports and Dashboards within Salesforce. The report called "Recurly Error Logs" within this folder provides reporting on errors from Recurly to Salesforce. This is the first place to check when you find errors in your sync process.

## Recurly Logs - Sync Stats Record

As of version 2.39, the progress of each sync batch is recorded in a log. The Recurly Log captures how many records of each type were successfully created or failed.

**NOTE**: If you installed a previous version of the package and were upgraded to 2.39, you may need to alter the layout of the Recurly Logs object to see the data which is passed in the Sync Stats Record.

## Salesforce to Recurly Sync Errors

When data fails to sync between Salesforce and Recurly, the user who edited the record inside of Salesforce will receive an email with information on why the sync failed.

## Workflow, Triggers, and Force.com Customization

You are able to add Force.com customization on top of Recurly custom objects within Salesforce. However, these customizations will not be supported by Recurly as every merchant will require different triggers, workflows, and customizations in order to integrate Recurly data into their business process.

## Troubleshooting

Below you will find some common issues and the solutions for them:
[block:parameters]
{
  "data": {
    "h-0": "Issue",
    "h-1": "Troubleshooting Steps",
    "0-0": "Recurly accounts are not being linked to Salesforce standard accounts.",
    "0-1": "Check the Recurly Admin tab and make sure that you have linking to Salesforce accounts enabled.\n\nIf you are still experiencing issues, ensure that the field on which you link Salesforce and Recurly accounts is populating correctly on Recurly accounts.",
    "2-0": "Salesforce accounts are not being created in my org when Recurly accounts are created.",
    "2-1": "Check the Recurly Admin tab to make sure that you have the option to create Salesforce accounts enabled.",
    "3-0": "I am missing Recurly data in my Salesforce org.",
    "3-1": "There could be a number of reasons for this. Follow these steps:\n1. Check the Recurly Logs tab and ensure that there are no errors being experienced.\n2. If there are no logs, navigate to Setup > Apex Jobs and ensure that there are no Apex jobs which experienced an error.\n3. Check your email to ensure that your Recurly API key has not errored. If there is an API key failure, Recurly for Salesforce will send you an email.\n4. Ensure that the user the integration is running as has the permission necessary to insert records.",
    "4-0": "My users can't see data.",
    "4-1": "This is either due to:\n1. Page layouts\n2. Permissions",
    "5-0": "I can't uninstall the package.",
    "5-1": "1. Deactivate the sync by going to the admin page and hitting the \"Deactivate sync\" button.\n\n2. Ensure there are no custom fields, workflow rules, or apex code referencing any objects/fields in the package. Due to the amount of potential complexity in Salesforce complexity, the easiest way to see if there are **custom** fields or rules referencing the package is to attempt to uninstall and see if there is an error.",
    "1-0": "I can't add my Recurly API keys to the API Settings tab in Salesforce.",
    "1-1": "Check the character length of your Recurly subdomain (subdomain.recurly.com). The Salesforce character limit for a Recurly subdomain is 25 characters. An error will occur when trying to connect Salesforce to Recurly via the API keys if your subdomain exceeds this length."
  },
  "cols": 2,
  "rows": 6
}
[/block]
## Data.com Duplicate Management and Recurly for Salesforce

Salesforce offers duplicate management through data.com functionality.  While the ability to report on and block duplicates is great for your users, it can cause issues for API integrations.  In order to ensure that your data can sync and update properly from Recurly, we urge you to take the following steps:

1. Fully exclude the user running the sync, including the "Recurly for Salesforce" user and any updates from our system, from triggering the data.com rules
2. Manually exclude any updates to fields related to the Recurly sync
3. For your initial sync, deactivate your data.com rules completely. Since Recurly needs to access your standard accounts for linking, deactivating your data.com rules is the best way to ensure that all of the data is synchronized properly. 

If you do not follow these steps, Recurly cannot guarantee that all of your data will be synced to Salesforce or linked correctly to your Salesforce accounts.

## Further Support

If you require further support, please contact [Recurly Support](https://support.recurly.com/) and we will be happy to assist you. 

Please be sure to mention which version of the package you are using (this is available on the Recurly Admin screen).