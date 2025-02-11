---
title: Coupons redemption - export
excerpt: Dive into detailed insights with the Coupon Redemptions export section.
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

### Prerequisites

To access this export feature, ensure that the "Multiple Coupons Per Account" option is activated in your Coupon Settings; otherwise, it won't appear on the Exports page.

# Definition

The "Coupon Redemptions" export in Recurly provides a comprehensive list of all coupon redemptions that have taken place in your account. This export function is a vital tool for tracking the utilization of coupons on your platform. Understanding when and how coupons were redeemed can offer deep insights into customer behavior and the effectiveness of your discount strategies.

# Filters

As of now, the export does not offer filters to isolate data based on specific coupons before downloading. Users can only filter the data by the time range, focusing on the '**applied_at**' column to understand when the redemption occurred.

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
    "h-0": "Id",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Data Type (max size)",
    "0-0": "<span id=\"coupon_code\">coupon_code</span>",
    "0-1": "5off",
    "0-2": "The code used by the customer to redeem the coupon.",
    "0-3": "String",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)",
    "1-2": "Identifies the account on which the coupon was redeemed.",
    "1-3": "String",
    "2-0": "<span id=\"discount\">discount</span>",
    "2-1": "5",
    "2-2": "The fixed amount discounted by the coupon, reflected in the corresponding currency column. A value of 0 indicates a percentage discount coupon.",
    "2-3": "Numeric",
    "3-0": "<span id=\"discount_percent\">discount_percent</span>",
    "3-1": "5",
    "3-2": "The percentage amount discounted by the coupon; will be 0 for fixed amount discount coupons.",
    "3-3": "Numeric",
    "4-0": "<span id=\"total_discount\">total_discount</span>",
    "4-1": "100.50",
    "4-2": "Total amount discounted to date from the coupon redemption.",
    "4-3": "Numeric",
    "5-0": "<span id=\"applied_at\">applied_at</span>",
    "5-1": "2013-01-02 06:21:14 PST",
    "5-2": "The exact date and time the coupon was redeemed; vital for date range filters.",
    "5-3": "Timestamp",
    "6-0": "<span id=\"expires_at\">expires_at</span>",
    "6-1": "2014-01-02 06:21:14 PST",
    "6-2": "Date and time the redemption expires post its valid duration.",
    "6-3": "Timestamp",
    "7-0": "<span id=\"timeframe\">timeframe</span>",
    "7-1": "forever",
    "7-2": "The validity duration of the coupon.",
    "7-3": "String",
    "8-0": "<span id=\"uuid\">uuid</span>",
    "8-1": "306f7937d86f088f046dd945a1a24df2",
    "8-2": "Unique identifier for each coupon redemption.",
    "8-3": "Varchar (32)",
    "9-0": "<span id=\"currency\">currency</span>",
    "9-1": "USD",
    "9-2": "Currency applicable to the total_discount and discount columns.",
    "9-3": "Varchar (3)",
    "10-0": "<span id=\"coupon_id\">coupon_id</span>",
    "10-1": "1313528357303980000",
    "10-2": "Unique identifier for the coupon, beneficial when correlating data from the Coupons export.",
    "10-3": "String",
    "11-0": "<span id=\"subscription_id\">subscription_id</span>",
    "11-1": "306f7937d86f088f046dd945a1a24df2",
    "11-2": "Unique identifier for the subscription linked to the redemption; only available for subscription-level coupons.",
    "11-3": "Varchar (32)",
    "12-0": "<span id=\"coupon_type\">coupon_type</span>",
    "12-1": "single code, bulk",
    "12-2": "Distinguishes between single code coupons and bulk coupons with multiple unique codes.",
    "12-3": "String",
    "13-0": "<span id=\"discount_type\">discount_type</span>",
    "13-1": "percent, fixed_amount, free_trial",
    "13-2": "The coupon's discount nature – percentage, fixed amount, or a custom trial period.",
    "13-3": "String",
    "14-0": "<span id=\"free_trial_coupon_amount\">free_trial_coupon_amount</span>",
    "14-1": "14",
    "14-2": "For free_trial discount types, it represents the number correlated with the trial period unit.",
    "14-3": "Numeric",
    "15-0": "<span id=\"free_trial_coupon_unit\">free_trial_coupon_unit</span>",
    "15-1": "day, week, month",
    "15-2": "Specifies the unit period for free_trial type coupons.",
    "15-3": "String",
    "16-0": "coupon_redemption_api_id",
    "16-1": "e28zov4fw0v2",
    "16-2": "Coupon Redemption API ID",
    "16-3": "String"
  },
  "cols": 4,
  "rows": 17,
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

- Addition of `coupon_redemption_api_id`.