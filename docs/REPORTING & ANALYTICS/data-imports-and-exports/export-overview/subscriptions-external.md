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

<Table align={[null,null,null,"left","left"]}>
  <thead>
    <tr>
      <th>
        Id
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>

      </th>

      <th style={{ textAlign: "left" }}>

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123456789, [test@example.com](mailto:test@example.com)
      </td>

      <td>
        Account associated with the External Subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_product_reference_code">external\_product\_reference\_code</span>
      </td>

      <td>
        string
      </td>

      <td>
        A code linking the external product to a relevant entity in platforms like the Apple App Store or Google Play Store.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_product_reference_source">external\_product\_reference\_source</span>
      </td>

      <td>
        string
      </td>

      <td>
        Platform where the external product is sourced (e.g., Apple App Store, Google Play).
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="app_identifier">app\_identifier</span>
      </td>

      <td>
        string
      </td>

      <td>
        ID of the app responsible for the external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan\_code</span>
      </td>

      <td>
        basic
      </td>

      <td>
        The external subscription’s plan.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        active, canceled, expired, or future
      </td>

      <td>
        Current status of the subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="auto_renew">auto\_renew</span>
      </td>

      <td>
        TRUE, FALSE
      </td>

      <td>
        Indicates if the subscription will auto-renew; defaults to TRUE.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="quantity">quantity</span>
      </td>

      <td>
        1
      </td>

      <td>
        The quantity of the subscribed items.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="activated_at">activated\_at</span>
      </td>

      <td>
        2010-03-24 17:18:46 PDT
      </td>

      <td>
        External platform’s activation date and time for the subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2010-03-24 17:18:44 PDT
      </td>

      <td>
        The date and time when the subscription was last updated in Recurly.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2010-03-24 17:18:44 PDT
      </td>

      <td>
        Recurly’s creation date and time for the subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="expires_at">expires\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        The expiration date and time for the subscription on the external platform.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="last_purchased">last\_purchased</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        The most recent billing event’s date and time on the external subscription, corresponding to a new billing period, reactivation, or upgrade/downgrade.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_product_reference_deleted_at">external\_product\_reference\_deleted\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        The date and time when the external product link was removed from the external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_product_name">external\_product\_name</span>
      </td>

      <td>
        string
      </td>

      <td>
        Name of the external product linked to the external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_product_deleted_at">external\_product\_deleted\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        When the external product association was removed from the external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="app_identifier">app\_identifier</span>
      </td>

      <td>
        external\_app
      </td>

      <td>
        External application identifier.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="auto_renew">auto\_renew</span>
      </td>

      <td>
        false
      </td>

      <td>
        Auto renew flag for external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="last_purchased">last\_purchased</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        Last purchase timestamp.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="external_id">external\_id</span>
      </td>

      <td>
        my\_id\_123456
      </td>

      <td>
        External identifier. For Apple, it is originalTransactionId. For Google, it is purchaseToken.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="quantity">quantity</span>
      </td>

      <td>
        1
      </td>

      <td>
        Quantity.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="in_grace_period">in\_grace\_period</span>
      </td>

      <td>
        false
      </td>

      <td>
        Flag to indicate whether subscription is in grace period.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="canceled_at">canceled\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        When the external subscription was canceled.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="trial_ends_at">trial\_ends\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        When the external subscription’s trial ended.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="trial_started_at">trial\_started\_at</span>
      </td>

      <td>
        2010-04-23 22:51:53 PDT
      </td>

      <td>
        When the external subscription’s trial started.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        active
      </td>

      <td>
        Current state of the external subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        external\_subscription\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        External Subscription API ID
      </td>

      <td style={{ textAlign: "left" }}>

      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>
  </tbody>
</Table>

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
