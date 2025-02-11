---
title: Coupons — bulk unique codes - export
excerpt: >-
  Uncover intricate details of your bulk unique coupons with this exclusive
  Coupons - Bulk Unique Codes export.
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

This export will only appear on the Exports page if you have created a bulk coupon on your site.

# Definition

The Coupons - Bulk Unique Codes export section allows users to export and analyze all the unique codes pertaining to a specific bulk coupon. This includes redemption details for each code. This export option becomes available on the Exports page once a bulk coupon is created on your site. It enables a meticulous breakdown of each code's performance and status, providing insights that can aid in optimizing coupon strategies.

# Filters

### **Coupon Filter**

To utilize this export, select all or the desired bulk coupon from a dropdown menu that enumerates the internal name of the coupon and the prefix of the codes, enclosed in parentheses. This list is alphabetically arranged according to the internal names of the coupons.

### **Date Range Filters**

#### **Created**

Defines the date range according to the 'created_at' column in the export. Leveraging the "All Time" option with "Created" will showcase the entire compilation of your unique codes. To zero in on a subset of codes crafted during a specific span of the campaign, simply filter the dates accordingly.

#### **Modified**

Establishes the date range based on the most recent modification date, aligned with the 'modified_at' column in the export. A unique code experiences modification upon its redemption (tracked in 'applied_at') or premature expiration (noted in 'deactivated_at'). The expiration date ('expired_at') does not constitute a modification event.

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
    "h-0": "**<span id=\"Id\">Id</span>**",
    "h-1": "**Example**",
    "h-2": "**Description**",
    "h-3": "",
    "0-0": "<span id=\"bulk_coupon_id\">bulk_coupon_id</span>",
    "0-1": "769158967603640335",
    "0-2": "UUID identifying the bulk coupon campaign, referential to the id in the Coupons export.",
    "0-3": "",
    "1-0": "<span id=\"bulk_coupon_prefix\">bulk_coupon_prefix</span>",
    "1-1": "save",
    "1-2": "Prefix common to all unique codes, mapped to the coupon_code of the bulk coupon in the Coupons export.",
    "1-3": "",
    "2-0": "<span id=\"unique_coupon_code\">unique_coupon_code</span>",
    "2-1": "save-012478",
    "2-2": "Specific code for the bulk coupon, displayed as the coupon_code in the Coupon Redemptions export where the customer applied it at redemption.",
    "2-3": "",
    "3-0": "<span id=\"discount\">discount</span>",
    "3-1": "5",
    "3-2": "Details of the fixed amount discount, which is applicable post-redemption, with the associated currency being showcased in the currency column. Maintains a null value for percentage discounts.",
    "3-3": "",
    "4-0": "<span id=\"discount_percent\">discount_percent</span>",
    "4-1": "5",
    "4-2": "Represents the percentage discount, remaining visible irrespective of the redemption status. Assumes a null value for fixed amount discounts.",
    "4-3": "",
    "5-0": "<span id=\"timeframe\">timeframe</span>",
    "5-1": "forever",
    "5-2": "Stipulates the active duration of the coupon.",
    "5-3": "",
    "6-0": "<span id=\"redeem_by_date\">redeem_by_date</span>",
    "6-1": "2015-10-10 11:59:59 PST",
    "6-2": "Defines the expiration date and time post which the code becomes non-redeemable. Always set at 11:59:59 PST of the designated day.",
    "6-3": "",
    "7-0": "<span id=\"created_at\">created_at</span>",
    "7-1": "2015-09-07 19:23:03 PST",
    "7-2": "Marks the creation date and time of the unique code.",
    "7-3": "",
    "8-0": "<span id=\"modified_at\">modified_at</span>",
    "8-1": "2015-09-07 19:23:03 PST",
    "8-2": "Logs the most recent modification date and time, aligning with redemption ('applied_at') or early expiration ('deactivated_at').",
    "8-3": "",
    "9-0": "<span id=\"deactivated_at\">deactivated_at</span>",
    "9-1": "2015-09-07 19:23:03 PST",
    "9-2": "Registers the early expiration date and time, if applicable.",
    "9-3": "",
    "10-0": "<span id=\"applied_at\">applied_at</span>",
    "10-1": "2013-01-02 06:21:14 PST",
    "10-2": "Records the date and time of the code's redemption on an account.",
    "10-3": "",
    "11-0": "<span id=\"expires_at\">expires_at</span>",
    "11-1": "2014-01-02 06:21:14 PST",
    "11-2": "Signifies the automatic expiration date and time of the code after the preset duration concludes.",
    "11-3": "",
    "12-0": "<span id=\"redemption_uuid\">redemption_uuid</span>",
    "12-1": "306f7937d86f088f046dd945a1a24df2",
    "12-2": "The unique ID representing each unique code's redemption.",
    "12-3": "",
    "13-0": "<span id=\"account_code\">account_code</span>",
    "13-1": "306f7937d86f088f046dd945a1a24df2",
    "13-2": "The unique identifier for the account where the code was redeemed.",
    "13-3": "",
    "14-0": "<span id=\"subscription_id\">subscription_id</span>",
    "14-1": "306f7937d86f088f046dd945a1a24df2",
    "14-2": "UUID of the subscription linked to the unique code's redemption on a customer account, displayed only for subscription-level redemptions.",
    "14-3": "",
    "15-0": "<span id=\"total_discount\">total_discount</span>",
    "15-1": "100.50",
    "15-2": "The aggregated discount applied on the account from the unique code's redemption till date.",
    "15-3": "",
    "16-0": "<span id=\"currency\">currency</span>",
    "16-1": "USD",
    "16-2": "The currency assigned to the 'total_discount' and 'discount' columns.",
    "16-3": "",
    "17-0": "<span id=\"discount_type\">discount_type</span>",
    "17-1": "percent, fixed_amount, free_trial",
    "17-2": "The category of the coupon — percentage discount, fixed amount discount, or a custom trial period.",
    "17-3": "",
    "18-0": "<span id=\"free_trial_coupon_amount\">free_trial_coupon_amount</span>",
    "18-1": "14",
    "18-2": "For 'free_trial' discount type, it defines the period number corresponding to the unit period (like 14 for a 14-day trial).",
    "18-3": "",
    "19-0": "<span id=\"free_trial_coupon_unit\">free_trial_coupon_unit</span>",
    "19-1": "day, week, month",
    "19-2": "For 'free_trial' discount type, it specifies the unit of the trial period (day/week/month corresponding to the trial period).",
    "19-3": "",
    "20-0": "unique_coupon_code_api_id",
    "20-1": "e28zov4fw0v2",
    "20-2": "Unique Coupon Code API ID",
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

### Version 2 - 2/5/2025

- Addition of `unique_coupon_code_api_id`.