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

* **All**: Displays all external subscriptions, irrespective of their status or state.

### Date Range Filters

* **Activated**: Filters external subscriptions activated within a selected time range, using data from the "activated\_at" column in the export.
* **Modified**: Highlights the subscriptions altered within a chosen timeframe based on the "modified\_at" column. Note that only the modified entries will appear, excluding the original data.
* **Created**: Shows subscriptions created within a selected period, referencing the "created\_at" column, including those with a future activation date.

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF; 
            background-color: #F8F8F8FF; 
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
          	transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%; 
        }

        .download-button:hover {
            background-color: #FFFFFFFF; 
            transform: scale(1.02); 
        }
      	a:hover {
          	color: #1C2833FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Id                                                                                                | Example                                                | Description                                                                                                                                            |    |    |
| ------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :- | :- |
| uuid                                                                                              | 72b6ba44eab2a94e8830414d7e8c2747                       | Universally Unique Identifier created automatically.                                                                                                   |    |    |
| <span id="account_code">account\_code</span>                                                      | 123456789, [test@example.com](mailto:test@example.com) | Account associated with the External Subscription.                                                                                                     |    |    |
| <span id="external_product_reference_code">external\_product\_reference\_code</span>              | string                                                 | A code linking the external product to a relevant entity in platforms like the Apple App Store or Google Play Store.                                   |    |    |
| <span id="external_product_reference_source">external\_product\_reference\_source</span>          | string                                                 | Platform where the external product is sourced (e.g., Apple App Store, Google Play).                                                                   |    |    |
| <span id="app_identifier">app\_identifier</span>                                                  | string                                                 | ID of the app responsible for the external subscription.                                                                                               |    |    |
| <span id="plan_code">plan\_code</span>                                                            | basic                                                  | The external subscription’s plan.                                                                                                                      |    |    |
| <span id="state">state</span>                                                                     | active, canceled, expired, or future                   | Current status of the subscription.                                                                                                                    |    |    |
| <span id="auto_renew">auto\_renew</span>                                                          | TRUE, FALSE                                            | Indicates if the subscription will auto-renew; defaults to TRUE.                                                                                       |    |    |
| <span id="quantity">quantity</span>                                                               | 1                                                      | The quantity of the subscribed items.                                                                                                                  |    |    |
| <span id="activated_at">activated\_at</span>                                                      | 2010-03-24 17:18:46 PDT                                | External platform’s activation date and time for the subscription.                                                                                     |    |    |
| <span id="modified_at">modified\_at</span>                                                        | 2010-03-24 17:18:44 PDT                                | The date and time when the subscription was last updated in Recurly.                                                                                   |    |    |
| <span id="created_at">created\_at</span>                                                          | 2010-03-24 17:18:44 PDT                                | Recurly’s creation date and time for the subscription.                                                                                                 |    |    |
| <span id="expires_at">expires\_at</span>                                                          | 2010-04-23 22:51:53 PDT                                | The expiration date and time for the subscription on the external platform.                                                                            |    |    |
| <span id="last_purchased">last\_purchased</span>                                                  | 2010-04-23 22:51:53 PDT                                | The most recent billing event’s date and time on the external subscription, corresponding to a new billing period, reactivation, or upgrade/downgrade. |    |    |
| <span id="external_product_reference_deleted_at">external\_product\_reference\_deleted\_at</span> | 2010-04-23 22:51:53 PDT                                | The date and time when the external product link was removed from the external subscription.                                                           |    |    |
| <span id="external_product_name">external\_product\_name</span>                                   | string                                                 | Name of the external product linked to the external subscription.                                                                                      |    |    |
| <span id="external_product_deleted_at">external\_product\_deleted\_at</span>                      | 2010-04-23 22:51:53 PDT                                | When the external product association was removed from the external subscription.                                                                      |    |    |
| <span id="app_identifier">app\_identifier</span>                                                  | external\_app                                          | External application identifier.                                                                                                                       |    |    |
| <span id="auto_renew">auto\_renew</span>                                                          | false                                                  | Auto renew flag for external subscription.                                                                                                             |    |    |
| <span id="last_purchased">last\_purchased</span>                                                  | 2010-04-23 22:51:53 PDT                                | Last purchase timestamp.                                                                                                                               |    |    |
| <span id="external_id">external\_id</span>                                                        | my\_id\_123456                                         | External identifier. For Apple, it is originalTransactionId. For Google, it is purchaseToken.                                                          |    |    |
| <span id="quantity">quantity</span>                                                               | 1                                                      | Quantity.                                                                                                                                              |    |    |
| <span id="in_grace_period">in\_grace\_period</span>                                               | false                                                  | Flag to indicate whether subscription is in grace period.                                                                                              |    |    |
| <span id="canceled_at">canceled\_at</span>                                                        | 2010-04-23 22:51:53 PDT                                | When the external subscription was canceled.                                                                                                           |    |    |
| <span id="trial_ends_at">trial\_ends\_at</span>                                                   | 2010-04-23 22:51:53 PDT                                | When the external subscription’s trial ended.                                                                                                          |    |    |
| <span id="trial_started_at">trial\_started\_at</span>                                             | 2010-04-23 22:51:53 PDT                                | When the external subscription’s trial started.                                                                                                        |    |    |
| <span id="state">state</span>                                                                     | active                                                 | Current state of the external subscription.                                                                                                            |    |    |
| external\_subscription\_api\_id                                                                   | e28zov4fw0v2                                           | External Subscription API ID                                                                                                                           |    |    |

# Version changelog

### Version 5 - 2/5/2025

* Addition of `external_subscription_api_id`.

### Version 3 - 7/6/2023

* Column added for state
* Column added for trial\_started\_at
* Column added for trial\_ends\_at
* Column added for canceled\_at
* Column added for in\_grace\_period

### Version 3 - 5/19/2023

* Column added for quantity
* Column added for external\_id

### Version 2 - 9/23/2022

* Column added for last\_purchased
* Column added for auto\_renew
* Column added for app\_identifier