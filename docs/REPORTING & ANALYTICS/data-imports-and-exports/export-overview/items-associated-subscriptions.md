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

Customize your export to focus on renewing, future start, last billing period, and paused subscriptions formed during a selected period, leveraging the "subscription_add_on_created_at" date in the export to narrow down your data.

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
    "h-0": "Column Name",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"item_id\">item_id</span>",
    "0-1": "l20fl6bek3mp",
    "0-2": "The system-generated unique identifier of the saved item utilized in creating this add-on.",
    "0-3": "string",
    "1-0": "<span id=\"item_name\">item_name</span>",
    "1-1": "Pink Sweater",
    "1-2": "The name of the saved item, mirrored in the add-on name on the customer's invoice.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"item_code\">item_code</span>",
    "2-1": "pink_sweater",
    "2-2": "The Recurly unique identifier for the saved item, also denoting the add-on code.",
    "2-3": "varchar(50)",
    "3-0": "<span id=\"external_sku\">external_sku</span>",
    "3-1": "PS1234",
    "3-2": "Optional external SKU of the saved item used in creating this add-on.",
    "3-3": "varchar(50)",
    "4-0": "<span id=\"item_status\">item_status</span>",
    "4-1": "enabled",
    "4-2": "The status of the item in your Recurly catalog, being either \"enabled\" or \"disabled\".",
    "4-3": "string",
    "5-0": "<span id=\"plan_code\">plan_code</span>",
    "5-1": "platinum",
    "5-2": "The Recurly unique identifier for the plan affiliated with this subscription.",
    "5-3": "varchar(50)",
    "6-0": "<span id=\"plan_name\">plan_name</span>",
    "6-1": "Platinum Plan",
    "6-2": "The contemporary name of the plan corresponding to this subscription.",
    "6-3": "varchar(255)",
    "7-0": "<span id=\"subscription_id\">subscription_id</span>",
    "7-1": "3c42a34d1442f840",
    "7-2": "Unique system-generated identifier for the subscription housing this item as an add-on.",
    "7-3": "varchar(32)",
    "8-0": "<span id=\"subscription_add_on_quantity\">subscription_add_on_quantity</span>",
    "8-1": "1",
    "8-2": "The count of add-ons integrated into the subscription for this item.",
    "8-3": "numeric",
    "9-0": "<span id=\"subscription_add_on_unit_amount_in_cents\">subscription_add_on_unit_amount_in_cents</span>",
    "9-1": "600",
    "9-2": "The unit cost of the add-on in the subscription, denominated in cents; it may differ from the plan's or item's default pricing.",
    "9-3": "numeric",
    "10-0": "<span id=\"subscription_add_on_currency\">subscription_add_on_currency</span>",
    "10-1": "USD",
    "10-2": "The currency utilized for billing in this subscription.",
    "10-3": "varchar(3)",
    "11-0": "<span id=\"subscription_add_on_created_at\">subscription_add_on_created_at</span>",
    "11-1": "2020-02-07 10:18:34 MST",
    "11-2": "The date and time when the add-on was created, a critical filter for defining the date range.",
    "11-3": "timestamp",
    "12-0": "<span id=\"subscription_add_on_modified_at\">subscription_add_on_modified_at</span>",
    "12-1": "2020-02-07 10:18:34 MST",
    "12-2": "The latest modification date and time for the add-on.",
    "12-3": "timestamp",
    "13-0": "<span id=\"subscription_add_on_tier_type\">subscription_add_on_tier_type</span>",
    "13-1": "flat",
    "13-2": "The subscription add-on tier type.",
    "13-3": "string",
    "14-0": "<span id=\"subscription_add_on_total_amount_in_cents\">subscription_add_on_total_amount_in_cents</span>",
    "14-1": "12345",
    "14-2": "Subscription add-on total amount in cents.",
    "14-3": "numeric",
    "15-0": "<span id=\"subscription_add_on_source\">subscription_add_on_modified_at</span>",
    "15-1": "source1",
    "15-2": "Subscription add-on source.",
    "15-3": "string",
    "16-0": "<span id=\"subscription_add_on_tax_inclusive\">subscription_add_on_tax_inclusive</span>",
    "16-1": "false",
    "16-2": "Boolean flag to indicate whether the subscription add-on is tax inclusive.",
    "16-3": "boolean",
    "17-0": "item_api_id",
    "17-1": "e28zov4fw0v2",
    "17-2": "Item API ID",
    "17-3": "string"
  },
  "cols": 4,
  "rows": 18,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 5 - 2/5/2025

Addition of `item_api_id`.

### Version 4 - 1/13/2022

Addition of subscription_add_on_tax_inclusive column.

### Version 3 - 7/23/2020

Addition of subscription_add_on_source column.

### Version 2 - 4/29/2020

Addition of subscription_add_on_tier_type, subscription_add_on_total_amount_in_cents columns.