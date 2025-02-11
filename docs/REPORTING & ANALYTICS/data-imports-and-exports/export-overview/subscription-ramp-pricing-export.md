---
title: Subscriptions — ramp pricing - export
excerpt: >-
  Explore the detailed ramp interval data with the Subscriptions - Ramp Pricing
  export.
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

The ramp pricing export function returns comprehensive data on each subscription operating under a ramp priced billing model. This allows for detailed tracking and analysis of various subscription attributes and statuses at different intervals of the ramp pricing lifecycle.

# Filters

### Subscription Status Filter

This filter helps in sorting the subscriptions based on their current status. The different statuses are explained below:

- **Live**: All active subscriptions.
- **Open**: **Live** subscriptions that will renew after the current term.
- **Trial**: **Live** subscriptions that are in a trial period.
- **Paused**: **Live** subscriptions that are currently paused.
- **Canceled**: **Live** subscriptions that will not renew after the current term.
- **Past Due**: **Live** subscriptions with a past-due invoice.
- **Future**: Subscriptions that will become active when the start date arrives.
- **Expired**: Inactive subscriptions.

### Date Range Filters

Under this filter, the subscriptions can be filtered based on the modifications and creations in a selected date range. The details are as follows:

- **Modified**: It includes the subscriptions that were modified in the selected time range. This utilizes the "modified_at" column in the export, showing only the modified subscriptions while the original ones do not appear.
- **Created**: This includes the subscriptions that were created within the selected timeframe, referring to the "created_at" column in the export. It also includes those created with a future activation date.

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
    "h-3": "Type",
    "0-0": "<span id=\"uuid\">uuid</span>",
    "0-1": "b964b5439c2548a489",
    "0-2": "Unique identifier for each subscription, retained despite modifications and aligns with identifiers in other exports like the Subscriptions export.",
    "0-3": "",
    "1-0": "<span id=\"ramp_id\">ramp_id</span>",
    "1-1": "101112",
    "1-2": "Unique identifier for ramp pricing, aligning with the current_ramp_id value in the subscriptions export.",
    "1-3": "",
    "2-0": "<span id=\"unit_amount\">unit_amount</span>",
    "2-1": "14.99",
    "2-2": "Unit amount charged at each ramp interval.",
    "2-3": "",
    "3-0": "<span id=\"starting_billing_cycle\">starting_billing_cycle</span>",
    "3-1": "2",
    "3-2": "The billing cycle at which the ramp interval initiates.",
    "3-3": "",
    "4-0": "<span id=\"elapsed_billing_cycles\">elapsed_billing_cycles</span>",
    "4-1": "2",
    "4-2": "The count of completed billing cycles in the current ramp interval.",
    "4-3": "",
    "5-0": "<span id=\"total_billing_cycles\">total_billing_cycles</span>",
    "5-1": "3",
    "5-2": "The overall billing cycles that a ramp interval encompasses.",
    "5-3": "",
    "6-0": "<span id=\"started_at\">started_at</span>",
    "6-1": "2021-05-08 12:53:10 MDT",
    "6-2": "Marks the initiation date of the ramp interval.",
    "6-3": "",
    "7-0": "<span id=\"ended_at\">ended_at</span>",
    "7-1": "2021-05-09 12:53:10 MDT",
    "7-2": "Denotes the closure date of the ramp interval.",
    "7-3": "",
    "8-0": "<span id=\"estimated_start_date\">estimated_start_date</span>",
    "8-1": "2021-05-11 12:53:10 MDT",
    "8-2": "The anticipated commencement date for the forthcoming ramp interval.",
    "8-3": "",
    "9-0": "subscription_ramp_api_id",
    "9-1": "e28zov4fw0v2",
    "9-2": "Ramp API ID",
    "9-3": "String",
    "10-0": "subscription_api_id",
    "10-1": "e28zov4fw0v2",
    "10-2": "Subscription API ID",
    "10-3": "String"
  },
  "cols": 4,
  "rows": 11,
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

- Addition of `subscription_ramp_api_id` and `subscription_api_id`.