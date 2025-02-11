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

Utilize the Time Range Filter to view all active subscription add-ons that were activated within a chosen time frame. This feature relies on the "subscription activated_at" date mentioned in the export details.

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
    "0-0": "<span id=\"subscription_uuid\">subscription_uuid</span>",
    "0-1": "5eg5bcc7ef8211e0a908005056b00005",
    "0-2": "Unique identifier for a specific subscription plan.",
    "0-3": "string",
    "1-0": "<span id=\"add_on_add_on_code\">add_on_add_on_code</span>",
    "1-1": "extra",
    "1-2": "Code used to identify the add-on.",
    "1-3": "varchar(50)",
    "2-0": "<span id=\"subscription_add_on_quantity\">subscription_add_on_quantity</span>",
    "2-1": "1",
    "2-2": "Number of add-ons added to the subscription.",
    "2-3": "numeric",
    "3-0": "<span id=\"subscription_add_on_unit_amount_in_cents\">subscription_add_on_unit_amount_in_cents</span>",
    "3-1": "500",
    "3-2": "Cost (in cents) of a unit of the add-on.",
    "3-3": "numeric",
    "4-0": "<span id=\"subscription_add_on_created_at\">subscription_add_on_created_at</span>",
    "4-1": "2014-01-07 23:54:41 PST",
    "4-2": "The date and time the add-on was created, utilized for the date range filter.",
    "4-3": "timestamp",
    "5-0": "<span id=\"subscription_add_on_modified_at\">subscription_add_on_modified_at</span>",
    "5-1": "2014-01-07 23:54:41 PST",
    "5-2": "The date and time the add-on was last modified.",
    "5-3": "timestamp",
    "6-0": "<span id=\"subscription_add_on_deleted_at\">subscription_add_on_deleted_at</span>",
    "6-1": "2014-01-07 23:54:41 PST",
    "6-2": "Deprecated column; it no longer populates due to filtering out add-ons with a deleted_at date.",
    "6-3": "timestamp",
    "7-0": "<span id=\"account_code\">account_code</span>",
    "7-1": "239485723046981734",
    "7-2": "Customer's account code to whom the subscription add-on belongs.",
    "7-3": "varchar(50)",
    "8-0": "<span id=\"add_on_name\">add_on_name</span>",
    "8-1": "Video Streaming",
    "8-2": "Name of the add-on that appears on the customer's invoice.",
    "8-3": "varchar(255)",
    "9-0": "<span id=\"add_on_type\">add_on_type</span>",
    "9-1": "fixed, usage",
    "9-2": "Indicates whether the add-on is fixed-price or usage-based.",
    "9-3": "string",
    "10-0": "<span id=\"subscription_currency\">subscription_currency</span>",
    "10-1": "USD",
    "10-2": "Currency of the subscription and the unit amount in cents.",
    "10-3": "varchar(3)",
    "11-0": "<span id=\"subscription_add_on_percentage\">subscription_add_on_percentage</span>",
    "11-1": "4.5",
    "11-2": "If usage-based, indicates the percentage of the subscription add-on.",
    "11-3": "numeric",
    "12-0": "<span id=\"measured_unit_internal_name\">measured_unit_internal_name</span>",
    "12-1": "Bandwidth Units",
    "12-2": "For usage-based add-ons, the internal name of the associated measured unit.",
    "12-3": "varchar(255)",
    "13-0": "<span id=\"measured_unit_display_name\">measured_unit_display_name</span>",
    "13-1": "GB",
    "13-2": "For usage-based add-ons, the display name of the associated measured unit.",
    "13-3": "varchar(50)",
    "14-0": "<span id=\"external_sku\">external_sku</span>",
    "14-1": "abc123",
    "14-2": "SKU of the sold item associated with this add-on, specified by the user.",
    "14-3": "varchar(50)",
    "15-0": "<span id=\"subscription_add_on_tier_type\">subscription_add_on_tier_type</span>",
    "15-1": "flat, tiered, volume, stairstep",
    "15-2": "Pricing model used to calculate costs based on purchased quantity.",
    "15-3": "string",
    "16-0": "<span id=\"subscription_add_on_total_amount_in_cents\">subscription_add_on_total_amount_in_cents</span>",
    "16-1": "1000",
    "16-2": "Total amount for a subscription add-on, excluding usage add-ons.",
    "16-3": "numeric",
    "17-0": "<span id=\"subscription_add_on_source\">subscription_add_on_source</span>",
    "17-1": "source",
    "17-2": "Subscription add-on source.",
    "17-3": "string",
    "18-0": "<span id=\"subscription_add_on_unit_amount_in_decimal_cents\">subscription_add_on_unit_amount_in_decimal_cents</span>",
    "18-1": "1000",
    "18-2": "Total amount for a subscription add-on, excluding usage add-ons.",
    "18-3": "numeric",
    "19-0": "<span id=\"subscription_add_on_billing_model\">subscription_add_on_billing_model</span>",
    "19-1": "1000",
    "19-2": "Total amount for a subscription add-on, excluding usage add-ons.",
    "19-3": "string",
    "20-0": "subscription_add_on_api_id",
    "20-1": "e28zov4fw0v2",
    "20-2": "Add On API ID",
    "20-3": "string",
    "21-0": "subscription_api_id",
    "21-1": "e28zov4fw0v2",
    "21-2": "Subscription API ID",
    "21-3": "string"
  },
  "cols": 4,
  "rows": 22,
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

- Addition of `subscription_add_on_api_id` and `subscription_api_id`.

### Version 5 - 3/9/2023

The addition of subscription_add_on_billing_model to indicate whether it’s term or period based billing.

### Version 4 - 1/14/2021

The addition of subscription_add_on_unit_amount_in_decimal_cents to indicate add on unit amount in decimal cents.

### Version 3 - 7/23/2020

The addition of column subscription_add_on_source to indicate add on source.

### Version 2 - 4/2/2020

The addition of a column for External SKU for item add-ons Inclusion of columns for Add-On Tier Type and Add-On Total Amount