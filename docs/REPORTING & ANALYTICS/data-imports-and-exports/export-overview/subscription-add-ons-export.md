---
title: Subscription add-ons - export
excerpt: >-
  Explore the comprehensive details of your current subscription add-ons with
  the Subscription Add-ons export feature.
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

The Subscription Add-on export tool helps you to gather detailed information about all the subscription add-ons created within a specific timeframe. It is important to note that this export only includes details of the add-ons that are currently active and attached to subscriptions. Add-ons that have been removed will not feature in this export.

# Filters

### Time Range Filter

Utilize the Time Range Filter to view all active subscription add-ons that were activated within a chosen time frame. This feature relies on the "subscription activated\_at" date mentioned in the export details.

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
        <span id="subscription_uuid">subscription\_uuid</span>
      </td>

      <td>
        5eg5bcc7ef8211e0a908005056b00005
      </td>

      <td>
        Unique identifier for a specific subscription plan.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_add_on_code">add\_on\_add\_on\_code</span>
      </td>

      <td>
        extra
      </td>

      <td>
        Code used to identify the add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
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
        Number of add-ons added to the subscription.
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
        500
      </td>

      <td>
        Cost (in cents) of a unit of the add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_created_at">subscription\_add\_on\_created\_at</span>
      </td>

      <td>
        2014-01-07 23:54:41 PST
      </td>

      <td>
        The date and time the add-on was created, utilized for the date range filter.
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
        2014-01-07 23:54:41 PST
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
        <span id="subscription_add_on_deleted_at">subscription\_add\_on\_deleted\_at</span>
      </td>

      <td>
        2014-01-07 23:54:41 PST
      </td>

      <td>
        Deprecated column; it no longer populates due to filtering out add-ons with a deleted\_at date.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
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
        Customer's account code to whom the subscription add-on belongs.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_name">add\_on\_name</span>
      </td>

      <td>
        Video Streaming
      </td>

      <td>
        Name of the add-on that appears on the customer's invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="add_on_type">add\_on\_type</span>
      </td>

      <td>
        fixed, usage
      </td>

      <td>
        Indicates whether the add-on is fixed-price or usage-based.
      </td>

      <td style={{ textAlign: "left" }}>
        string
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
        Currency of the subscription and the unit amount in cents.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_percentage">subscription\_add\_on\_percentage</span>
      </td>

      <td>
        4.5
      </td>

      <td>
        If usage-based, indicates the percentage of the subscription add-on.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="measured_unit_internal_name">measured\_unit\_internal\_name</span>
      </td>

      <td>
        Bandwidth Units
      </td>

      <td>
        For usage-based add-ons, the internal name of the associated measured unit.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
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
        For usage-based add-ons, the display name of the associated measured unit.
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
        abc123
      </td>

      <td>
        SKU of the sold item associated with this add-on, specified by the user.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_tier_type">subscription\_add\_on\_tier\_type</span>
      </td>

      <td>
        flat, tiered, volume, stairstep
      </td>

      <td>
        Pricing model used to calculate costs based on purchased quantity.
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
        1000
      </td>

      <td>
        Total amount for a subscription add-on, excluding usage add-ons.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_source">subscription\_add\_on\_source</span>
      </td>

      <td>
        source
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
        <span id="subscription_add_on_unit_amount_in_decimal_cents">subscription\_add\_on\_unit\_amount\_in\_decimal\_cents</span>
      </td>

      <td>
        1000
      </td>

      <td>
        Total amount for a subscription add-on, excluding usage add-ons.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_add_on_billing_model">subscription\_add\_on\_billing\_model</span>
      </td>

      <td>
        1000
      </td>

      <td>
        Total amount for a subscription add-on, excluding usage add-ons.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        subscription\_add\_on\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Add On API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        subscription\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Subscription API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 6 - 2/5/2025

* Addition of `subscription_add_on_api_id` and `subscription_api_id`.

### Version 5 - 3/9/2023

The addition of subscription\_add\_on\_billing\_model to indicate whether it’s term or period based billing.

### Version 4 - 1/14/2021

The addition of subscription\_add\_on\_unit\_amount\_in\_decimal\_cents to indicate add on unit amount in decimal cents.

### Version 3 - 7/23/2020

The addition of column subscription\_add\_on\_source to indicate add on source.

### Version 2 - 4/2/2020

The addition of a column for External SKU for item add-ons Inclusion of columns for Add-On Tier Type and Add-On Total Amount
