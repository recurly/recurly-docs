---
title: Items — associated plans - export
excerpt: >-
  Explore the Items - Associated Plans export to manage and track your catalog
  efficiently.
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

The "Items - Associated Plans" export function in Recurly permits users to generate a report containing detailed information on all plan add-ons created from a saved item in your catalog during a specified period. It focuses exclusively on add-ons that are presently linked to active plans, ensuring that your report only contains the most pertinent and up-to-date data.

# Filters

### **Date Range Filter**

This export can be filtered based on a specified time range using the "plan\_add\_on\_created\_at" date in the export.

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
        The system-generated unique internal identifier of the saved item used to create this add-on.
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
        The name of the saved item used to create this add-on. This is also the add-on name on the invoice.
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
        The unique Recurly identifier of the saved item used to create this add-on. This is also the add-on code.
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
        The optional external SKU of the saved item used to create this add-on.
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
        The status of the item in your Recurly catalog, which can be "enabled" or "disabled".
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
        The unique Recurly identifier of the plan that offers this item as an add-on.
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
        The current name of the plan that offers this item as an add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_add_on_unit_amount_in_cents">plan\_add\_on\_unit\_amount\_in\_cents</span>
      </td>

      <td>
        1599
      </td>

      <td>
        The cost (in cents) of a unit of the add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_add_on_currency">plan\_add\_on\_currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        The currency of the plan, which is the currency of the plan\_add\_on\_unit\_amount\_in\_cents.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_add_on_created_at">plan\_add\_on\_created\_at</span>
      </td>

      <td>
        2020-02-05 15:52:46 MST
      </td>

      <td>
        The date and time the add-on was created, used for date range filtering.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_add_on_modified_at">plan\_add\_on\_modified\_at</span>
      </td>

      <td>
        2020-02-05 15:52:46 MST
      </td>

      <td>
        The date and time the add-on was last modified.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_add_on_tier_type">plan\_add\_on\_tier\_type</span>
      </td>

      <td>
        flat
      </td>

      <td>
        Add on Tier Type.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_allow_any_item_on_subscriptions">plan\_allow\_any\_item\_on\_subscriptions</span>
      </td>

      <td>
        false
      </td>

      <td>
        Whether the plan allows any item on subscriptions
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

### Version 6 - 2/5/2025

Addition of `item_api_id`.

### Version 5 - 5/31/2022

Removal of plan\_add\_on\_tax\_inclusive column.

### Version 4 - 1/13/2022

Addition of plan\_add\_on\_tax\_inclusive column.

### Version 3 - 7/23/2020

Addition of plan\_allow\_any\_item\_on\_subscriptions column.

### Version 2 - 4/29/2020

Addition of plan\_add\_on\_tier\_type column.
