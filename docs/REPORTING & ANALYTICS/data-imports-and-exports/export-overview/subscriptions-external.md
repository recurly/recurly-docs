---
title: Subscriptions — external - export
excerpt: Track and manage Subscriptions - External export effortlessly.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

The "Subscriptions - External" export function allows you to identify and gather detailed information on external subscriptions stored on third-party platforms like the Apple App Store or Google Play Store. It aims to provide Recurly users with comprehensive data regarding the statuses and details of external subscriptions tied to different accounts.

# Filters

To help you focus on the relevant data, several filters are available for use with the "Subscriptions - External" export, which include:

### Subscription Status Filter

- **All**: Displays all external subscriptions, irrespective of their status or state.

### Date Range Filters

- **Activated**: Filters external subscriptions activated within a selected time range, using data from the "activated_at" column in the export.
- **Modified**: Highlights the subscriptions altered within a chosen timeframe based on the "modified_at" column. Note that only the modified entries will appear, excluding the original data.
- **Created**: Shows subscriptions created within a selected period, referencing the "created_at" column, including those with a future activation date.

# Exports table

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #1C2833FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"
}
[/block]


To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

[block:parameters]
{
  "data": {
    "h-0": "Id",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "",
    "h-4": "",
    "0-0": "<span id=\"account_code\">account_code</span>",
    "0-1": "123456789, [test@example.com](mailto:test@example.com)",
    "0-2": "Account associated with the External Subscription.",
    "0-3": "",
    "0-4": "",
    "1-0": "<span id=\"external_product_reference_code\">external_product_reference_code</span>",
    "1-1": "string",
    "1-2": "A code linking the external product to a relevant entity in platforms like the Apple App Store or Google Play Store.",
    "1-3": "",
    "1-4": "",
    "2-0": "<span id=\"external_product_reference_source\">external_product_reference_source</span>",
    "2-1": "string",
    "2-2": "Platform where the external product is sourced (e.g., Apple App Store, Google Play).",
    "2-3": "",
    "2-4": "",
    "3-0": "<span id=\"app_identifier\">app_identifier</span>",
    "3-1": "string",
    "3-2": "ID of the app responsible for the external subscription.",
    "3-3": "",
    "3-4": "",
    "4-0": "<span id=\"plan_code\">plan_code</span>",
    "4-1": "basic",
    "4-2": "The external subscription’s plan.",
    "4-3": "",
    "4-4": "",
    "5-0": "<span id=\"state\">state</span>",
    "5-1": "active, canceled, expired, or future",
    "5-2": "Current status of the subscription.",
    "5-3": "",
    "5-4": "",
    "6-0": "<span id=\"auto_renew\">auto_renew</span>",
    "6-1": "TRUE, FALSE",
    "6-2": "Indicates if the subscription will auto-renew; defaults to TRUE.",
    "6-3": "",
    "6-4": "",
    "7-0": "<span id=\"quantity\">quantity</span>",
    "7-1": "1",
    "7-2": "The quantity of the subscribed items.",
    "7-3": "",
    "7-4": "",
    "8-0": "<span id=\"activated_at\">activated_at</span>",
    "8-1": "2010-03-24 17:18:46 PDT",
    "8-2": "External platform’s activation date and time for the subscription.",
    "8-3": "",
    "8-4": "",
    "9-0": "<span id=\"modified_at\">modified_at</span>",
    "9-1": "2010-03-24 17:18:44 PDT",
    "9-2": "The date and time when the subscription was last updated in Recurly.",
    "9-3": "",
    "9-4": "",
    "10-0": "<span id=\"created_at\">created_at</span>",
    "10-1": "2010-03-24 17:18:44 PDT",
    "10-2": "Recurly’s creation date and time for the subscription.",
    "10-3": "",
    "10-4": "",
    "11-0": "<span id=\"expires_at\">expires_at</span>",
    "11-1": "2010-04-23 22:51:53 PDT",
    "11-2": "The expiration date and time for the subscription on the external platform.",
    "11-3": "",
    "11-4": "",
    "12-0": "<span id=\"last_purchased\">last_purchased</span>",
    "12-1": "2010-04-23 22:51:53 PDT",
    "12-2": "The most recent billing event’s date and time on the external subscription, corresponding to a new billing period, reactivation, or upgrade/downgrade.",
    "12-3": "",
    "12-4": "",
    "13-0": "<span id=\"external_product_reference_deleted_at\">external_product_reference_deleted_at</span>",
    "13-1": "2010-04-23 22:51:53 PDT",
    "13-2": "The date and time when the external product link was removed from the external subscription.",
    "13-3": "",
    "13-4": "",
    "14-0": "<span id=\"external_product_name\">external_product_name</span>",
    "14-1": "string",
    "14-2": "Name of the external product linked to the external subscription.",
    "14-3": "",
    "14-4": "",
    "15-0": "<span id=\"external_product_deleted_at\">external_product_deleted_at</span>",
    "15-1": "2010-04-23 22:51:53 PDT",
    "15-2": "When the external product association was removed from the external subscription.",
    "15-3": "",
    "15-4": "",
    "16-0": "<span id=\"app_identifier\">app_identifier</span>",
    "16-1": "external_app",
    "16-2": "External application identifier.",
    "16-3": "",
    "16-4": "",
    "17-0": "<span id=\"auto_renew\">auto_renew</span>",
    "17-1": "false",
    "17-2": "Auto renew flag for external subscription.",
    "17-3": "",
    "17-4": "",
    "18-0": "<span id=\"last_purchased\">last_purchased</span>",
    "18-1": "2010-04-23 22:51:53 PDT",
    "18-2": "Last purchase timestamp.",
    "18-3": "",
    "18-4": "",
    "19-0": "<span id=\"external_id\">external_id</span>",
    "19-1": "my_id_123456",
    "19-2": "External identifier. For Apple, it is originalTransactionId. For Google, it is purchaseToken.",
    "19-3": "",
    "19-4": "",
    "20-0": "<span id=\"quantity\">quantity</span>",
    "20-1": "1",
    "20-2": "Quantity.",
    "20-3": "",
    "20-4": "",
    "21-0": "<span id=\"in_grace_period\">in_grace_period</span>",
    "21-1": "false",
    "21-2": "Flag to indicate whether subscription is in grace period.",
    "21-3": "",
    "21-4": "",
    "22-0": "<span id=\"canceled_at\">canceled_at</span>",
    "22-1": "2010-04-23 22:51:53 PDT",
    "22-2": "When the external subscription was canceled.",
    "22-3": "",
    "22-4": "",
    "23-0": "<span id=\"trial_ends_at\">trial_ends_at</span>",
    "23-1": "2010-04-23 22:51:53 PDT",
    "23-2": "When the external subscription’s trial ended.",
    "23-3": "",
    "23-4": "",
    "24-0": "<span id=\"trial_started_at\">trial_started_at</span>",
    "24-1": "2010-04-23 22:51:53 PDT",
    "24-2": "When the external subscription’s trial started.",
    "24-3": "",
    "24-4": "",
    "25-0": "<span id=\"state\">state</span>",
    "25-1": "active",
    "25-2": "Current state of the external subscription.",
    "25-3": "",
    "25-4": "",
    "26-0": "external_subscription_api_id",
    "26-1": "e28zov4fw0v2",
    "26-2": "External Subscription API ID",
    "26-3": "",
    "26-4": ""
  },
  "cols": 5,
  "rows": 27,
  "align": [
    null,
    null,
    null,
    "left",
    "left"
  ]
}
[/block]


# Version changelog

### Version 5 - 2/5/2025

- Addition of `external_subscription_api_id`.

### Version 3 - 7/6/2023

- Column added for state 
- Column added for trial_started_at
- Column added for trial_ends_at
- Column added for canceled_at
- Column added for in_grace_period

### Version 3 - 5/19/2023

- Column added for quantity 
- Column added for external_id

### Version 2 - 9/23/2022

- Column added for last_purchased
- Column added for auto_renew
- Column added for app_identifier