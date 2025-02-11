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

This export can be filtered based on a specified time range using the "plan_add_on_created_at" date in the export.

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
    "0-2": "The system-generated unique internal identifier of the saved item used to create this add-on.",
    "0-3": "string",
    "1-0": "<span id=\"item_name\">item_name</span>",
    "1-1": "Pink Sweater",
    "1-2": "The name of the saved item used to create this add-on. This is also the add-on name on the invoice.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"item_code\">item_code</span>",
    "2-1": "pink_sweater",
    "2-2": "The unique Recurly identifier of the saved item used to create this add-on. This is also the add-on code.",
    "2-3": "varchar(50)",
    "3-0": "<span id=\"external_sku\">external_sku</span>",
    "3-1": "PS1234",
    "3-2": "The optional external SKU of the saved item used to create this add-on.",
    "3-3": "varchar(50)",
    "4-0": "<span id=\"item_status\">item_status</span>",
    "4-1": "enabled",
    "4-2": "The status of the item in your Recurly catalog, which can be \"enabled\" or \"disabled\".",
    "4-3": "string",
    "5-0": "<span id=\"plan_code\">plan_code</span>",
    "5-1": "platinum",
    "5-2": "The unique Recurly identifier of the plan that offers this item as an add-on.",
    "5-3": "varchar(50)",
    "6-0": "<span id=\"plan_name\">plan_name</span>",
    "6-1": "Platinum Plan",
    "6-2": "The current name of the plan that offers this item as an add-on.",
    "6-3": "varchar(255)",
    "7-0": "<span id=\"plan_add_on_unit_amount_in_cents\">plan_add_on_unit_amount_in_cents</span>",
    "7-1": "1599",
    "7-2": "The cost (in cents) of a unit of the add-on.",
    "7-3": "numeric",
    "8-0": "<span id=\"plan_add_on_currency\">plan_add_on_currency</span>",
    "8-1": "USD",
    "8-2": "The currency of the plan, which is the currency of the plan_add_on_unit_amount_in_cents.",
    "8-3": "varchar(3)",
    "9-0": "<span id=\"plan_add_on_created_at\">plan_add_on_created_at</span>",
    "9-1": "2020-02-05 15:52:46 MST",
    "9-2": "The date and time the add-on was created, used for date range filtering.",
    "9-3": "timestamp",
    "10-0": "<span id=\"plan_add_on_modified_at\">plan_add_on_modified_at</span>",
    "10-1": "2020-02-05 15:52:46 MST",
    "10-2": "The date and time the add-on was last modified.",
    "10-3": "timestamp",
    "11-0": "<span id=\"plan_add_on_tier_type\">plan_add_on_tier_type</span>",
    "11-1": "flat",
    "11-2": "Add on Tier Type.",
    "11-3": "string",
    "12-0": "<span id=\"plan_allow_any_item_on_subscriptions\">plan_allow_any_item_on_subscriptions</span>",
    "12-1": "false",
    "12-2": "Whether the plan allows any item on subscriptions",
    "12-3": "boolean",
    "13-0": "item_api_id",
    "13-1": "e28zov4fw0v2",
    "13-2": "Item API ID",
    "13-3": "string"
  },
  "cols": 4,
  "rows": 14,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 6 - 2/5/2025

Addition of `item_api_id`.

### Version 5 - 5/31/2022

Removal of plan_add_on_tax_inclusive column.

### Version 4 - 1/13/2022

Addition of plan_add_on_tax_inclusive column.

### Version 3 - 7/23/2020

Addition of plan_allow_any_item_on_subscriptions column.

### Version 2 - 4/29/2020

Addition of plan_add_on_tier_type column.