---
title: Coupons - export
excerpt: Master your promotions with the detailed Coupons export section.
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

The "Coupons" export section is designed to offer comprehensive details on all the coupons created on your site, facilitating a streamlined analysis and management of your promotional strategies. Coupons with a fixed amount discount that support multiple currencies will be displayed in separate rows for each currency. 

# Filters

### **Date Range Filters**

#### **Created**

Filter the data to only include the coupons that were created within a selected time frame.

#### **Modified**

This filter allows you to zero in on the coupons modified within a chosen time range. A modification occurs due to an increment in redemption_count, when a coupon hits its max_redemptions limit, or is deactivated prematurely, which is reflected in the "deactivated_at" column.

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
    "h-0": "<span id=\"id\">Id</span>",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"coupon_code\">coupon_code</span>",
    "0-1": "5off",
    "0-2": "The code to be inputted by customers to avail the discount.",
    "0-3": "varchar(50)",
    "1-0": "<span id=\"name\">name</span>",
    "1-1": "5% Off",
    "1-2": "Internal nomenclature for the coupon.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"discount\">discount</span>",
    "2-1": "5",
    "2-2": "Value of the fixed amount discount, depicted in the currency column; 0 for percentage discounts.",
    "2-3": "numeric",
    "3-0": "<span id=\"currency\">currency</span>",
    "3-1": "USD",
    "3-2": "Denotes the currency for the fixed discount amount; blank for percentage discounts.",
    "3-3": "varchar(3)",
    "4-0": "<span id=\"discount_percent\">discount_percent</span>",
    "4-1": "5",
    "4-2": "Indicates the percentage discount; blank for fixed amount discounts.",
    "4-3": "numeric",
    "5-0": "<span id=\"redeem_by_date\">redeem_by_date</span>",
    "5-1": "2015-10-10 11:59:59 PST",
    "5-2": "The expiration date and time post which the coupon cannot be redeemed.",
    "5-3": "timestamp",
    "6-0": "<span id=\"redemptions_count\">redemptions_count</span>",
    "6-1": "7",
    "6-2": "The total number of redemptions to date.",
    "6-3": "numeric",
    "7-0": "<span id=\"max_redemptions\">max_redemptions</span>",
    "7-1": "100",
    "7-2": "The upper limit on the allowable number of redemptions.",
    "7-3": "numeric",
    "8-0": "<span id=\"applies_to_plans\">applies_to_plans</span>",
    "8-1": "all plans",
    "8-2": "Specifies the plans that can be discounted through the coupon redemptions.",
    "8-3": "string",
    "9-0": "<span id=\"timeframe\">timeframe</span>",
    "9-1": "forever",
    "9-2": "The lifespan of the coupon.",
    "9-3": "string",
    "10-0": "<span id=\"created_at\">created_at</span>",
    "10-1": "2012-01-02 06:20:41 PST",
    "10-2": "Date and time of coupon creation; employed in created date range filter.",
    "10-3": "timestamp",
    "11-0": "<span id=\"deactivated_at\">deactivated_at</span>",
    "11-1": "2013-02-02 06:20:41 PST",
    "11-2": "Marks the date and time when the coupon was either expired early or when the max_redemptions were achieved.",
    "11-3": "timestamp",
    "12-0": "<span id=\"modified\">modified</span>",
    "12-1": "2012-01-02 06:20:41 PST",
    "12-2": "Records the most recent modification time, relevant for the modified date range filter.",
    "12-3": "timestamp",
    "13-0": "<span id=\"applies_to_non_plan_charges\">applies_to_non_plan_charges</span>",
    "13-1": "TRUE",
    "13-2": "Dictates whether the coupon redemptions can offer discounts on one-time charges on customer invoices.",
    "13-3": "boolean",
    "14-0": "<span id=\"redemptions_per_account\">redemptions_per_account</span>",
    "14-1": "1",
    "14-2": "The maximum redemption limit per account; \"unlimited\" if left blank.",
    "14-3": "numeric",
    "15-0": "<span id=\"redemption_resource\">redemption_resource</span>",
    "15-1": "account, subscription",
    "15-2": "The scope of the discount, whether at the account or subscription level.",
    "15-3": "string",
    "16-0": "<span id=\"coupon_type\">coupon_type</span>",
    "16-1": "single code, bulk",
    "16-2": "Categorizes the coupon as a single code or a bulk code with several unique codes.",
    "16-3": "string",
    "17-0": "<span id=\"discount_type\">discount_type</span>",
    "17-1": "percent, fixed_amount, free_trial",
    "17-2": "Specifies the nature of the discount — percentage, fixed amount, or free trial.",
    "17-3": "string",
    "18-0": "<span id=\"free_trial_coupon_amount\">free_trial_coupon_amount</span>",
    "18-1": "14",
    "18-2": "For \"free_trial\" discount types, it signifies the number associated with the trial period unit.",
    "18-3": "numeric",
    "19-0": "<span id=\"free_trial_coupon_unit\">free_trial_coupon_unit</span>",
    "19-1": "day, week, month",
    "19-2": "Relates to the \"free_trial\" discount type, indicating the period of the trial.",
    "19-3": "string",
    "20-0": "<span id=\"applies_to_items\">applies_to_items</span>",
    "20-1": "item1, item2",
    "20-2": "Identifies whether a coupon is applicable to all items or specific items.",
    "20-3": "string",
    "21-0": "coupon_api_id",
    "21-1": "e28zov4fw0v2",
    "21-2": "Coupon API ID",
    "21-3": "String"
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


# Version Changelog

### Version 3 - 2/5/2025

- Addition of `coupon_api_id`.

### Version 2 - 10/15/20

- Introduction of the applies_to_items column to highlight if a coupon is applicable to all items or select items. In case a given coupon is only applicable to select items, the item code will be aggregated with a comma as delimiter.

Recurly offers 3 exports relevant to coupons: Coupons, Coupon Redemptions, and Coupons- Bulk Unique Coupons