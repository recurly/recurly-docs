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

- **Created**: Extract records created in Recurly in your preferred time span.
- **Modified**: Attain records of updates done in Recurly in a chosen time window.
- **Usage Timestamp**: To understand the utilization in a period, pull records based on usage timestamps.
- **Recording Timestamp**: Retrieve records documented in your system within a selected time frame.
- **Billed**: Gain insights into the usage records billed in a particular duration.

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
    "h-3": "",
    "0-0": "<span id=\"usage_id\">usage_id</span>",
    "0-1": "400527199884543703",
    "0-2": "Unique ID of the usage record.",
    "0-3": "",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "239485723046981734",
    "1-2": "Account code of the associated customer.",
    "1-3": "",
    "2-0": "<span id=\"subscription_id\">subscription_id</span>",
    "2-1": "3598f5c395fc7e2f4a4eaa4888b9784b",
    "2-2": "ID representing the relevant usage-based add-on subscription.",
    "2-3": "",
    "3-0": "<span id=\"plan_code\">plan_code</span>",
    "3-1": "mega_video",
    "3-2": "Code of the associated subscription plan.",
    "3-3": "",
    "4-0": "<span id=\"add_on_code\">add_on_code</span>",
    "4-1": "video_streaming",
    "4-2": "Code identifying the subscription add-on that the usage record belongs to.",
    "4-3": "",
    "5-0": "<span id=\"subscription_currency\">subscription_currency</span>",
    "5-1": "USD",
    "5-2": "Currency used in the subscription and for denoting the unit_amount_in_cents for the add-on.",
    "5-3": "",
    "6-0": "<span id=\"usage_type\">usage_type</span>",
    "6-1": "price, percentage",
    "6-2": "The pricing model of the usage-based add-on: either \"price per unit\" or \"percentage of an amount\".",
    "6-3": "",
    "7-0": "<span id=\"unit_amount_in_cents\">unit_amount_in_cents</span>",
    "7-1": "60",
    "7-2": "For \"price\" usage type, indicates the price per usage unit in cents.",
    "7-3": "",
    "8-0": "<span id=\"usage_percentage\">usage_percentage</span>",
    "8-1": "4.5",
    "8-2": "For \"percentage\" usage type, shows the percentage of the billed monetary amount.",
    "8-3": "",
    "9-0": "<span id=\"measured_unit_internal_name\">measured_unit_internal_name</span>",
    "9-1": "bandwith_streaming",
    "9-2": "Internal name of the applicable measured unit.",
    "9-3": "",
    "10-0": "<span id=\"measured_unit_display_name\">measured_unit_display_name</span>",
    "10-1": "GB",
    "10-2": "Display name of the applicable measured unit, describing the \"amount\" column value.",
    "10-3": "",
    "11-0": "<span id=\"amount\">amount</span>",
    "11-1": "5",
    "11-2": "Units used, represented in cents for \"percentage\" usage type.",
    "11-3": "",
    "12-0": "<span id=\"merchant_tag\">merchant_tag</span>",
    "12-1": "\"Rate Lookup ID: 45768456845683435\"",
    "12-2": "Custom field to store any relevant information for the usage record.",
    "12-3": "",
    "13-0": "<span id=\"usage_timestamp\">usage_timestamp</span>",
    "13-1": "2016-04-18 17:00:08 UTC",
    "13-2": "Timestamp of when the units were used, crucial for revenue recognition as it determines the line item date range on the invoice.",
    "13-3": "",
    "14-0": "<span id=\"recording_timestamp\">recording_timestamp</span>",
    "14-1": "2016-04-18 17:00:08 UTC",
    "14-2": "The time the usage was recorded in your system; defaults to the usage timestamp if not specified differently.",
    "14-3": "",
    "15-0": "<span id=\"created_at\">created_at</span>",
    "15-1": "2016-04-18 17:00:08 UTC",
    "15-2": "The creation time of the usage record in Recurly.",
    "15-3": "",
    "16-0": "<span id=\"modified_at\">modified_at</span>",
    "16-1": "2016-04-18 17:00:08 UTC",
    "16-2": "The modification time in Recurly, possibly when the record was billed or updated before billing.",
    "16-3": "",
    "17-0": "<span id=\"billed_at\">billed_at</span>",
    "17-1": "2016-04-18 17:00:08 UTC",
    "17-2": "When the usage was billed in an invoice.",
    "17-3": "",
    "18-0": "<span id=\"tier_type\">tier_type</span>",
    "18-1": "flat",
    "18-2": "Subscription tier type.",
    "18-3": "",
    "19-0": "<span id=\"unit_amount_in_decimal_cents\">unit_amount_in_decimal_cents</span>",
    "19-1": "12345",
    "19-2": "Unit amount in decimal cents.",
    "19-3": "",
    "20-0": "sub_usage_api_id",
    "20-1": "e28zov4fw0v2",
    "20-2": "Subscription Usage API ID",
    "20-3": "String"
  },
  "cols": 4,
  "rows": 21,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 4 - 2/5/2025

Addition of `sub_usage_api_id`.

### Version 3 - 1/22/2022

The addition of column unit_amount_in_decimal_cents.

### Version 2 - 1/19/2020

Addition of column tier_type.