---
title: Subscriptions — usage records - export
excerpt: >-
  Unveil your customer's usage details with the Subscriptions Usage Records
  Export.
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

The Subscriptions Usage Records Export allows you to acquire individual usage records associated with your customer’s usage-based subscription add-ons. This data is crucial for your finance team to report on pre-billed revenue and enables product and marketing teams to scrutinize customer usage patterns. Note that for an accurate revenue reflection, discounts applied at the invoice level should be reviewed in the Adjustments export as they are not depicted here.

Access the detailed usage records through the <a href="http://app.recurly.com/go/exports">Exports</a> page found under the "Reports" section on your Recurly site.

# Filters

### Plan Filter

#### All Plans

Get data on all plans with usage-based add-ons.

#### Monthly Usage Plan

Choose to export usage details of a specific plan’s usage-based add-ons.

### Usage-Based Add-On Filter

#### All Usage-Based Add-Ons

Export records for all associated usage-based add-ons for a chosen plan.

#### Specific Add-On

Refine your export to records of a singular usage-based add-on in a selected plan.

### Date Range Filters

* **Created**: Extract records created in Recurly in your preferred time span.
* **Modified**: Attain records of updates done in Recurly in a chosen time window.
* **Usage Timestamp**: To understand the utilization in a period, pull records based on usage timestamps.
* **Recording Timestamp**: Retrieve records documented in your system within a selected time frame.
* **Billed**: Gain insights into the usage records billed in a particular duration.

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

      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="usage_id">usage\_id</span>
      </td>

      <td>
        400527199884543703
      </td>

      <td>
        Unique ID of the usage record.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        239485723046981734
      </td>

      <td>
        Account code of the associated customer.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_id">subscription\_id</span>
      </td>

      <td>
        3598f5c395fc7e2f4a4eaa4888b9784b
      </td>

      <td>
        ID representing the relevant usage-based add-on subscription.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="plan_code">plan\_code</span>
      </td>

      <td>
        mega\_video
      </td>

      <td>
        Code of the associated subscription plan.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_code">add\_on\_code</span>
      </td>

      <td>
        video\_streaming
      </td>

      <td>
        Code identifying the subscription add-on that the usage record belongs to.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_currency">subscription\_currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        Currency used in the subscription and for denoting the unit\_amount\_in\_cents for the add-on.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="usage_type">usage\_type</span>
      </td>

      <td>
        price, percentage
      </td>

      <td>
        The pricing model of the usage-based add-on: either "price per unit" or "percentage of an amount".
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="unit_amount_in_cents">unit\_amount\_in\_cents</span>
      </td>

      <td>
        60
      </td>

      <td>
        For "price" usage type, indicates the price per usage unit in cents.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="usage_percentage">usage\_percentage</span>
      </td>

      <td>
        4.5
      </td>

      <td>
        For "percentage" usage type, shows the percentage of the billed monetary amount.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="measured_unit_internal_name">measured\_unit\_internal\_name</span>
      </td>

      <td>
        bandwith\_streaming
      </td>

      <td>
        Internal name of the applicable measured unit.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="measured_unit_display_name">measured\_unit\_display\_name</span>
      </td>

      <td>
        GB
      </td>

      <td>
        Display name of the applicable measured unit, describing the "amount" column value.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="amount">amount</span>
      </td>

      <td>
        5
      </td>

      <td>
        Units used, represented in cents for "percentage" usage type.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="merchant_tag">merchant\_tag</span>
      </td>

      <td>
        "Rate Lookup ID: 45768456845683435"
      </td>

      <td>
        Custom field to store any relevant information for the usage record.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="usage_timestamp">usage\_timestamp</span>
      </td>

      <td>
        2016-04-18 17:00:08 UTC
      </td>

      <td>
        Timestamp of when the units were used, crucial for revenue recognition as it determines the line item date range on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="recording_timestamp">recording\_timestamp</span>
      </td>

      <td>
        2016-04-18 17:00:08 UTC
      </td>

      <td>
        The time the usage was recorded in your system; defaults to the usage timestamp if not specified differently.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2016-04-18 17:00:08 UTC
      </td>

      <td>
        The creation time of the usage record in Recurly.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2016-04-18 17:00:08 UTC
      </td>

      <td>
        The modification time in Recurly, possibly when the record was billed or updated before billing.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="billed_at">billed\_at</span>
      </td>

      <td>
        2016-04-18 17:00:08 UTC
      </td>

      <td>
        When the usage was billed in an invoice.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="tier_type">tier\_type</span>
      </td>

      <td>
        flat
      </td>

      <td>
        Subscription tier type.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        <span id="unit_amount_in_decimal_cents">unit\_amount\_in\_decimal\_cents</span>
      </td>

      <td>
        12345
      </td>

      <td>
        Unit amount in decimal cents.
      </td>

      <td style={{ textAlign: "left" }}>

      </td>
    </tr>

    <tr>
      <td>
        sub\_usage\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Subscription Usage API ID
      </td>

      <td style={{ textAlign: "left" }}>
        String
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 4 - 2/5/2025

Addition of `sub_usage_api_id`.

### Version 3 - 1/22/2022

The addition of column unit\_amount\_in\_decimal\_cents.

### Version 2 - 1/19/2020

Addition of column tier\_type.
