---
title: Invoices — external - export
excerpt: Simplify external invoice tracking with the Invoices - External export.
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

### Prerequisite

You must have external invoices to view this export.

# Definition

The "Invoices - External" export function allows Recurly users to identify and manage details pertaining to external invoices that are generated for accounts with subscriptions created on third-party platforms such as the Apple App Store or Google Play Store. By utilizing this export function, you can seamlessly organize and maintain a record of all external invoices, thereby enhancing your revenue tracking and customer service capabilities.

# Filters

### **Date Range Filters**

* **Created**: External Invoices created within the chosen timeframe.
* **Modified**: External Invoices modified within the chosen timeframe.

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
          	color: #888888FF;
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
        Id
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
        <span id="id">id</span>
      </td>

      <td>
        101
      </td>

      <td>
        Unique code or identifier.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)
      </td>

      <td>
        Unique identifier for Recurly customers, defaulting to email if not specified. Links multiple exports as a primary, unchangeable ID.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="external_subscription_id">external\_subscription\_id</span>
      </td>

      <td>
        ext001s
      </td>

      <td>
        Identifier for the subscription on the external platform.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="external_id">external\_id</span>
      </td>

      <td>
        ex001id
      </td>

      <td>
        Unique ID representing the invoice on the external platform.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        pending, active, canceled, expired
      </td>

      <td>
        Current subscription state.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="total">total</span>
      </td>

      <td>
        60
      </td>

      <td>
        The total amount charged in the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="currency">currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        Currency used to denote amount and balance in the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="source">source</span>
      </td>

      <td>
        Apple
      </td>

      <td>
        The source or platform where the subscription was initiated.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="purchased_at">purchased\_at</span>
      </td>

      <td>
        2014-01-01 10:00:00 PST
      </td>

      <td>
        Where the purchase associated with the invoice was made.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2014-01-01 10:00:00 PST
      </td>

      <td>
        The creation date and time of the invoice, used in the time range filter for sorting based on creation dates.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2014-01-01 10:00:00 PST
      </td>

      <td>
        The last modification date and time of the invoice, useful for tracking recent updates.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        external\_invoice\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        External Invoice API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 2 - 2/5/2025

* Addition of `external_invoice_api_id`.
