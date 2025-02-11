---
title: Items — associated subscriptions - export
excerpt: >-
  Unlock detailed insights into your subscription add-ons with the Items -
  Associated Subscriptions export.
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

The "Items - Associated Subscriptions" export provides comprehensive details of all subscription add-ons generated from a saved item in your catalog over a certain period. It focuses on add-ons linked to renewing, future start, last billing period, and paused subscriptions, omitting details from canceled or expired subscriptions.

# Filters

### **Date Range Filter**

Customize your export to focus on renewing, future start, last billing period, and paused subscriptions formed during a selected period, leveraging the "subscription\_add\_on\_created\_at" date in the export to narrow down your data.

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

<Table align={[null,null,null,"left"]}>
  <thead>
    <tr>
      <th>
        Column Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="item_id">item\_id</span>
      </td>

      <td>
        l20fl6bek3mp
      </td>

      <td>
        The system-generated unique identifier of the saved item utilized in creating this add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="item_name">item\_name</span>
      </td>

      <td>
        Pink Sweater
      </td>

      <td>
        The name of the saved item, mirrored in the add-on name on the customer's invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="item_code">item\_code</span>
      </td>

      <td>
        pink\_sweater
      </td>

      <td>
        The Recurly unique identifier for the saved item, also denoting the add-on code.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="external_sku">external\_sku</span>
      </td>

      <td>
        PS1234
      </td>

      <td>
        Optional external SKU of the saved item used in creating this add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="item_status">item\_status</span>
      </td>

      <td>
        enabled
      </td>

      <td>
        The status of the item in your Recurly catalog, being either "enabled" or "disabled".
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan\_code</span>
      </td>

      <td>
        platinum
      </td>

      <td>
        The Recurly unique identifier for the plan affiliated with this subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_name">plan\_name</span>
      </td>

      <td>
        Platinum Plan
      </td>

      <td>
        The contemporary name of the plan corresponding to this subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_id">subscription\_id</span>
      </td>

      <td>
        3c42a34d1442f840
      </td>

      <td>
        Unique system-generated identifier for the subscription housing this item as an add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_quantity">subscription\_add\_on\_quantity</span>
      </td>

      <td>
        1
      </td>

      <td>
        The count of add-ons integrated into the subscription for this item.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_unit_amount_in_cents">subscription\_add\_on\_unit\_amount\_in\_cents</span>
      </td>

      <td>
        600
      </td>

      <td>
        The unit cost of the add-on in the subscription, denominated in cents; it may differ from the plan's or item's default pricing.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_currency">subscription\_add\_on\_currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        The currency utilized for billing in this subscription.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_created_at">subscription\_add\_on\_created\_at</span>
      </td>

      <td>
        2020-02-07 10:18:34 MST
      </td>

      <td>
        The date and time when the add-on was created, a critical filter for defining the date range.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_modified_at">subscription\_add\_on\_modified\_at</span>
      </td>

      <td>
        2020-02-07 10:18:34 MST
      </td>

      <td>
        The latest modification date and time for the add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_tier_type">subscription\_add\_on\_tier\_type</span>
      </td>

      <td>
        flat
      </td>

      <td>
        The subscription add-on tier type.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_total_amount_in_cents">subscription\_add\_on\_total\_amount\_in\_cents</span>
      </td>

      <td>
        12345
      </td>

      <td>
        Subscription add-on total amount in cents.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_source">subscription\_add\_on\_modified\_at</span>
      </td>

      <td>
        source1
      </td>

      <td>
        Subscription add-on source.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_tax_inclusive">subscription\_add\_on\_tax\_inclusive</span>
      </td>

      <td>
        false
      </td>

      <td>
        Boolean flag to indicate whether the subscription add-on is tax inclusive.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        item\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Item API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 5 - 2/5/2025

Addition of `item_api_id`.

### Version 4 - 1/13/2022

Addition of subscription\_add\_on\_tax\_inclusive column.

### Version 3 - 7/23/2020

Addition of subscription\_add\_on\_source column.

### Version 2 - 4/29/2020

Addition of subscription\_add\_on\_tier\_type, subscription\_add\_on\_total\_amount\_in\_cents columns.
