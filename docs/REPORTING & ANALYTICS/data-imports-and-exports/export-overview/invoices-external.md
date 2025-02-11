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

- **Created**: External Invoices created within the chosen timeframe.
- **Modified**: External Invoices modified within the chosen timeframe.

# Exports table

[block:html]
{
  "html": "<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #888888FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"
}
[/block]


To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

[block:parameters]
{
  "data": {
    "h-0": "Id",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"id\">id</span>",
    "0-1": "101",
    "0-2": "Unique code or identifier.",
    "0-3": "string",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)",
    "1-2": "Unique identifier for Recurly customers, defaulting to email if not specified. Links multiple exports as a primary, unchangeable ID.",
    "1-3": "varchar(50)",
    "2-0": "<span id=\"external_subscription_id\">external_subscription_id</span>",
    "2-1": "ext001s",
    "2-2": "Identifier for the subscription on the external platform.",
    "2-3": "string",
    "3-0": "<span id=\"external_id\">external_id</span>",
    "3-1": "ex001id",
    "3-2": "Unique ID representing the invoice on the external platform.",
    "3-3": "varchar(255)",
    "4-0": "<span id=\"state\">state</span>",
    "4-1": "pending, active, canceled, expired",
    "4-2": "Current subscription state.",
    "4-3": "string",
    "5-0": "<span id=\"total\">total</span>",
    "5-1": "60",
    "5-2": "The total amount charged in the invoice.",
    "5-3": "numeric",
    "6-0": "<span id=\"currency\">currency</span>",
    "6-1": "USD",
    "6-2": "Currency used to denote amount and balance in the invoice.",
    "6-3": "varchar(3)",
    "7-0": "<span id=\"source\">source</span>",
    "7-1": "Apple",
    "7-2": "The source or platform where the subscription was initiated.",
    "7-3": "string",
    "8-0": "<span id=\"purchased_at\">purchased_at</span>",
    "8-1": "2014-01-01 10:00:00 PST",
    "8-2": "Where the purchase associated with the invoice was made.",
    "8-3": "timestamp",
    "9-0": "<span id=\"created_at\">created_at</span>",
    "9-1": "2014-01-01 10:00:00 PST",
    "9-2": "The creation date and time of the invoice, used in the time range filter for sorting based on creation dates.",
    "9-3": "timestamp",
    "10-0": "<span id=\"modified_at\">modified_at</span>",
    "10-1": "2014-01-01 10:00:00 PST",
    "10-2": "The last modification date and time of the invoice, useful for tracking recent updates.",
    "10-3": "timestamp",
    "11-0": "external_invoice_api_id",
    "11-1": "e28zov4fw0v2",
    "11-2": "External Invoice API ID",
    "11-3": "string"
  },
  "cols": 4,
  "rows": 12,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 2 - 2/5/2025

- Addition of `external_invoice_api_id`.