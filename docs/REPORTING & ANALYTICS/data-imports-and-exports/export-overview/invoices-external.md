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

<Image border={false} src="https://files.readme.io/a3f3a3ec7861bd5d279d8cba5a3bf2d08f2014c2479f68081cb2fd89e28c961b-image.png" />

# Filters

### Versions Filter

* The Versions filter allows you to select the version that is most appropriate for your needs. This is based on the version changelog at the bottom of this page.

### **Export On Filters**

* **Created**: External Invoices created within the chosen timeframe.
* **Modified**: External Invoices modified within the chosen timeframe.

### Time range filters

* The Time range filter (dropdown) allows you to view data within a specific period such as last month, year to date or a custom date range. The Start Date and End Date will automatically update based on the value selected in the Time range filter. You can also choose "Between..." in the dropdown, which will allow you to enter a customized date range.

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

| Id                                                                  | Example                                                  | Description                                                                                                                          | Data type (max size) |
| ------------------------------------------------------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | :------------------- |
| <span id="id">id</span>                                             | 101                                                      | Unique code or identifier.                                                                                                           | string               |
| <span id="account_code">account_code</span>                         | 123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com) | Unique identifier for Recurly customers, defaulting to email if not specified. Links multiple exports as a primary, unchangeable ID. | varchar(50)          |
| <span id="external_subscription_id">external_subscription_id</span> | ext001s                                                  | Identifier for the subscription on the external platform.                                                                            | string               |
| <span id="external_id">external_id</span>                           | ex001id                                                  | Unique ID representing the invoice on the external platform.                                                                         | varchar(255)         |
| <span id="state">state</span>                                       | pending, active, canceled, expired                       | Current subscription state.                                                                                                          | string               |
| <span id="total">total</span>                                       | 60                                                       | The total amount charged in the invoice.                                                                                             | numeric              |
| <span id="currency">currency</span>                                 | USD                                                      | Currency used to denote amount and balance in the invoice.                                                                           | varchar(3)           |
| <span id="source">source</span>                                     | Apple                                                    | The source or platform where the subscription was initiated.                                                                         | string               |
| <span id="purchased_at">purchased_at</span>                         | 2014-01-01 10:00:00 PST                                  | Where the purchase associated with the invoice was made.                                                                             | timestamp            |
| <span id="created_at">created_at</span>                             | 2014-01-01 10:00:00 PST                                  | The creation date and time of the invoice, used in the time range filter for sorting based on creation dates.                        | timestamp            |
| <span id="modified_at">modified_at</span>                           | 2014-01-01 10:00:00 PST                                  | The last modification date and time of the invoice, useful for tracking recent updates.                                              | timestamp            |
| external_invoice_api_id                                             | e28zov4fw0v2                                             | External Invoice API ID                                                                                                              | string               |

# Version changelog

### Version 2 - 2/5/2025

* Addition of `external_invoice_api_id`.
