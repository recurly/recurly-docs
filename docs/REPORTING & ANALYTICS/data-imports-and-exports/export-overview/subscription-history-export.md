---
title: Subscriptions — history - export
excerpt: >-
  Unlock a detailed record of subscription alterations with the Subscriptions -
  History export.
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

Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) to have this feature activated in your account.

# Definition

The “Subscriptions - History” section enables users to view the history of each subscription including all versions created following any change to a subscription. This includes monitoring various movements such as upgrades, downgrades, cancellations, trial conversions, and more, facilitating in-depth tracking of a subscriber's lifecycle. It is essential to note that the subscription history export only tracks the changes post the activation of a subscription.

# Filters

### Subscription Status Filter

- **All**: Displays all subscription history status.
- **Trial**: Displays all subscription history respective to trial status.
- **Open**: Displays all subscription history respective to open status.
- **Canceled**: Displays all subscription history respective to canceled status.
- **Expired**: Displays all subscription history respective to expired status.

### Date Range Filters

#### **Activated**

Use this filter to view past versions of activated or reactivated subscriptions within a specified timeframe, utilizing the _subscription_activated_at_ column.

#### **Created**

View recent creations to all subscriptions within a chosen time range, referring to the _version_created_at_ column.

#### **Modified**

View recent alterations to all subscriptions within a chosen time range, referring to a combination of _version_state_ and _version_created_at_ columns.

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
    "0-0": "<span id=\"subscription_uuid\">subscription_uuid</span>",
    "0-1": "434f11do8b297982eb",
    "0-2": "Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.",
    "0-3": "",
    "1-0": "<span id=\"version_uuid\">version_uuid</span>",
    "1-1": "43509049eb30fb",
    "1-2": "Unique internal identifier for the version of a subscription_uuid. A new version is created when a change is made to a subscription.",
    "1-3": "",
    "2-0": "<span id=\"account_code\">account_code</span>",
    "2-1": "123456789, [test@example.com](mailto:test@example.com)",
    "2-2": "Account associated with a given subscription_uuid.",
    "2-3": "",
    "3-0": "<span id=\"subscription_activated_at\">subscription_activated_at</span>",
    "3-1": "2018-03-24 17:18:46 PDT",
    "3-2": "Date and time the subscription became active (or reactivated) on an account.",
    "3-3": "",
    "4-0": "<span id=\"subscription_expires_at\">subscription_expires_at</span>",
    "4-1": "2018-09-24 17:18:46 PDT",
    "4-2": "Date and time the subscription was/will churn. This field is populated when a subscription cancels with the expected expiration date.",
    "4-3": "",
    "5-0": "<span id=\"subscription_state\">subscription_state</span>",
    "5-1": "active, canceled, paused, expired",
    "5-2": "State of the subscription at the time the version was active.",
    "5-3": "",
    "6-0": "<span id=\"version_started_at\">version_started_at</span>",
    "6-1": "2018-03-20 03:22:25 EST",
    "6-2": "The date a change was made to the subscription and thus the new version was created.",
    "6-3": "",
    "7-0": "<span id=\"version_ended_at\">version_ended_at</span>",
    "7-1": "2018-07-20 03:22:25 EST",
    "7-2": "The date a version is no longer active because another change to the subscription is made and a newer version is created.",
    "7-3": "",
    "8-0": "<span id=\"version_state\">version_state</span>",
    "8-1": "inactive or active",
    "8-2": "Versions reflecting the current attributes of the subscription (i.e., are currently in use) are \"active.\" All expired versions are \"inactive\".",
    "8-3": "",
    "9-0": "<span id=\"plan_code\">plan_code</span>",
    "9-1": "bronze_1",
    "9-2": "The plan that the subscription was actively on while that version was active. Codes are used internally only.",
    "9-3": "",
    "10-0": "<span id=\"plan_name\">plan_name</span>",
    "10-1": "Bronze Plan # 1",
    "10-2": "The name of the plan the subscriber was actively on while that version was active.",
    "10-3": "",
    "11-0": "<span id=\"subscription_currency\">subscription_currency</span>",
    "11-1": "USD, GBP, CAD",
    "11-2": "The currency associated with that subscription at the time that version was active.",
    "11-3": "",
    "12-0": "<span id=\"version_plan_interval_unit\">version_plan_interval_unit</span>",
    "12-1": "months, weeks, days, years",
    "12-2": "The interval type at which that subscription is billed while that version was active.",
    "12-3": "",
    "13-0": "<span id=\"version_plan_interval_length\">version_plan_interval_length</span>",
    "13-1": "any number",
    "13-2": "The length of the interval type at which the subscription is billed at while the version was active.",
    "13-3": "",
    "14-0": "<span id=\"version_collection_method\">version_collection_method</span>",
    "14-1": "automatic, manual",
    "14-2": "Identifies whether the subscription fees are collected via manual or automatic invoicing.",
    "14-3": "",
    "15-0": "<span id=\"version_total_billing_cycles\">version_total_billing_cycles</span>",
    "15-1": "1",
    "15-2": "The total number of bill cycles that the subscription will bill at the time the version was active.",
    "15-3": "",
    "16-0": "<span id=\"version_subscription_quantity\">version_subscription_quantity</span>",
    "16-1": "1, 2",
    "16-2": "Identifies the quantity of the subscription purchase at the time the version was active.",
    "16-3": "",
    "17-0": "<span id=\"version_subscription_unit_amount\">version_subscription_unit_amount</span>",
    "17-1": "100",
    "17-2": "Identifies the base price of 1 quantity of the subscription at the time the version was active.",
    "17-3": "",
    "18-0": "<span id=\"version_add_on_codes\">version_add_on_codes</span>",
    "18-1": "add_on1, add_on1, add_on2",
    "18-2": "A list of add-ons that were active on the subscription at the time the version was active.",
    "18-3": "",
    "19-0": "<span id=\"version_add_on_types\">version_add_on_types</span>",
    "19-1": "fixed, fixed, usage",
    "19-2": "Lists the type of add-on in corresponding order to the listed add_on_codes on the subscription at the time the version was active.",
    "19-3": "",
    "20-0": "<span id=\"version_add_on_unit_amounts\">version_add_on_unit_amounts</span>",
    "20-1": "10, 10, 5%",
    "20-2": "Lists the unit amount of the add-on in corresponding order to the listed add_on_codes and listed add_on_types.",
    "20-3": "",
    "21-0": "<span id=\"version_add_ons_total\">version_add_ons_total</span>",
    "21-1": "20",
    "21-2": "Sums the add_on_unit_amounts on the subscription at the time the version was active. Does not include usage-based add-ons.",
    "21-3": "",
    "22-0": "<span id=\"version_total_recurring_amount\">version_total_recurring_amount</span>",
    "22-1": "120",
    "22-2": "(version_unit_amount) \\* (version_subscription_quantity) + version_add_on_total",
    "22-3": "",
    "23-0": "<span id=\"version_in_trial\">version_in_trial</span>",
    "23-1": "Y, N",
    "23-2": "Indicates whether or not the subscription was in trial while the version was active.",
    "23-3": "",
    "24-0": "<span id=\"version_auto_renew\">version_auto_renew</span>",
    "24-1": "Y, N",
    "24-2": "Indicates whether or not the subscription was set to auto renew while the version was active.",
    "24-3": "",
    "25-0": "<span id=\"version_renewal_billing_cycles\">version_renewal_billing_cycles</span>",
    "25-1": "1",
    "25-2": "",
    "25-3": "",
    "26-0": "<span id=\"version_shipping_method_name\">version_shipping_method_name</span>",
    "26-1": "USPS Overnight",
    "26-2": "The shipping method name used at the time when the version was active.",
    "26-3": "",
    "27-0": "<span id=\"version_shipping_amount\">version_shipping_amount</span>",
    "27-1": "5",
    "27-2": "Identifies the shipping price on the subscription at the time the version was active.",
    "27-3": "",
    "28-0": "<span id=\"pricing_model\">pricing_model</span>",
    "28-1": "ramp",
    "28-2": "Pricing model of the subscription. Will be either fixed or ramp.",
    "28-3": "",
    "29-0": "<span id=\"current_ramp_id\">current_ramp_id</span>",
    "29-1": "pz82514rbd3s",
    "29-2": "The id of the current ramp interval.",
    "29-3": "",
    "30-0": "<span id=\"tax_inclusive\">tax_inclusive</span>",
    "30-1": "false",
    "30-2": "Boolean (TRUE/FALSE) flag to indicate whether subscription is tax inclusive.",
    "30-3": "",
    "31-0": "subscription_api_id",
    "31-1": "e28zov4fw0v2",
    "31-2": "Subscription API ID",
    "31-3": "string"
  },
  "cols": 4,
  "rows": 32,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 7 - 2/5/2025

- Addition of `subscription_api_id`.

### Version 6 - 1/28/2022

- Added columns for tax_inclusive.

### Version 5 - 12/7/2021

- Added columns for pricing_model and current_ramp_id.

### Version 4 - 5/12/2021

- Removed concatenation in columns: version_add_on_codes, version_add_on_types, version_add_on_unit_amounts.

### Version 3 - 3/25/2020

- Introduced a new column: version_add_on_tier_types.

### Version 2 - 1/9/2020

- Incorporated columns for shipping method and amount.