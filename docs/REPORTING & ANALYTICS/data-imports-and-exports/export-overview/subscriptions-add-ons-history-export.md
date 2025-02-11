---
title: Subscription add-ons — history  - export
excerpt: >-
  Delve into the rich history of your subscription add-ons and leverage valuable
  insights with our detailed export feature in the "Subscription Add-ons —
  History" section.
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

Explore the subscription add-on history feature that allows tracking all the changes made to a subscription add-on over time. Every time a change or multiple changes are made simultaneously, a new version of the subscription add-on history is created. This feature is vital for keeping historical versions of add-ons that change on subscriptions.

# Filters

### Subscription Status Filter

- **All**: Displays all subscription history status.
- **Trial**: Displays all subscription history respective to trial status.
- **Open**: Displays all subscription history respective to open status.
- **Canceled**: Displays all subscription history respective to canceled status.
- **Expired**: Displays all subscription history respective to expired status.

### Date Range Filters

#### **Activated**

Showcases the past versions of subscription add-ons that were activated or reactivated within the chosen time frame. It utilizes the `subscription_activated_at` column for data representation.

#### **Created**

Depicts the past versions of subscription add-ons generated during a specified time range, utilizing data from the `version_started_at` column.

#### **Modified**

View recent alterations to all subscriptions within a chosen time range, referring to a combination of _version_state_ and version_started_at columns.

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
    "0-0": "subscription_uuid",
    "0-1": "434f11do8b297982eb",
    "0-2": "Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.",
    "0-3": "varchar(32)",
    "1-0": "version_uuid",
    "1-1": "43509049eb30fb",
    "1-2": "Unique internal identifier for the version of a subscription_uuid.  \nA new version if created when a change is made to a subscription. If multiple different changes are made at the same time,  all will be captured in the same new version.",
    "1-3": "string",
    "2-0": "account_code",
    "2-1": "123456789,  \n[test@example.com](mailto:test@example.com)",
    "2-2": "Account associated with a given subscription_uuid.",
    "2-3": "varchar(50)",
    "3-0": "subscription_activated_at",
    "3-1": "2018-03-24 17:18:46 PDT",
    "3-2": "Date and time the subscription became active (or reactivated) on an account. Note that this might not always match exactly with the subscription_created_At date if a subscription is created with a future start date.",
    "3-3": "timestamp",
    "4-0": "subscription_expires_at",
    "4-1": "2018-09-24 17:18:46 PDT",
    "4-2": "Date and time the subscription was/ will churn.  \n  \nThis field is populated when a subscription cancels with the expected expiration date.",
    "4-3": "timestamp",
    "5-0": "subscription_state",
    "5-1": "active, canceled, paused,  \nexpired",
    "5-2": "State of the subscription at the time the version was active.",
    "5-3": "string",
    "6-0": "version_started_at",
    "6-1": "2018-03-20 03:22:25 EST",
    "6-2": "The date a change was made to the subscription and thus the new version was created.",
    "6-3": "timestamp",
    "7-0": "version_ended_at",
    "7-1": "2018-07-20 03:22:25 EST",
    "7-2": "The date a version is no longer active because another change to the subscription is a made and a newer version is created.  \nAll versions with the version_state of \"inactive\" will have a version_expired_at date.",
    "7-3": "timestamp",
    "8-0": "version_state",
    "8-1": "inactive or active",
    "8-2": "the versions of a subscription that reflect the current attributes of that subscription (i.e are currently in use) are \"active.\" All expired versions are \"inactive\"",
    "8-3": "string",
    "9-0": "plan_code",
    "9-1": "bronze_1",
    "9-2": "the plan that the subscription was actively on while that version was active. Codes are used internally only.",
    "9-3": "varchar(50)",
    "10-0": "plan_name",
    "10-1": "Bronze Plan # 1",
    "10-2": "The name of the plan the subscriber was actively on while that version was active.",
    "10-3": "varchar(25)",
    "11-0": "subscription_currency",
    "11-1": "USD, GBP, CAD",
    "11-2": "The currency associated with that subscription at the time that version was active",
    "11-3": "varchar(3)",
    "12-0": "version_plan_interval_unit",
    "12-1": "months, weeks, days, years",
    "12-2": "The interval type at which that subscription is billed while that version was active.  Combined with the version_plan_internval_length, you can understand how often your customer is billed  \nexample: 1 month, 2 months, 1 year, etc.",
    "12-3": "varchar(10)",
    "13-0": "version_plan_interval_length",
    "13-1": "any number",
    "13-2": "The length of the interval type at which the subscription is billed at while the version was active.  \nExample: 1 month, 2 months, 1 year ,etc",
    "13-3": "numeric(10)",
    "14-0": "version_collection_method",
    "14-1": "automatic, manual",
    "14-2": "Identifies whether the subscription fees are collected via manual or automatic invoicing.",
    "14-3": "string",
    "15-0": "version_total_billing_cycles",
    "15-1": "1",
    "15-2": "If configured on the plan, the total number of bill cycles that the subscription will bill at the time the version was active.  \n If not specifically configured, the subscription will auto renew and this field will be blank.",
    "15-3": "numeric",
    "16-0": "version_subscription_quantity",
    "16-1": "1, 2",
    "16-2": "Identifies the quantity of the subscription purchase at the time the version was active.",
    "16-3": "numeric",
    "17-0": "version_subscription_unit_amount",
    "17-1": "100",
    "17-2": "Identifies the base price of 1 quantity of the subscription at the time the version was active.",
    "17-3": "numeric",
    "18-0": "version_add_on_code",
    "18-1": "add_on1, add_on1,  add_on2",
    "18-2": "A list of add ons that were active on the subscription at the time the version was active.  \nIf there is more than one of the same add_on, it will be listed the same number of times as the quantity.",
    "18-3": "varchar(50)",
    "19-0": "version_add_on_quantity",
    "19-1": "1",
    "19-2": "Identifies the quantity of the add-on at the time the version was active.",
    "19-3": "numeric",
    "20-0": "version_add_on_type",
    "20-1": "fixed, fixed, usage",
    "20-2": "Lists the type of add_on in corresponding order to the listed add_on_codes on the subscription at the time the version was active.",
    "20-3": "string",
    "21-0": "version_add_on_unit_amount",
    "21-1": "10, 10, 5%",
    "21-2": "Lists the unit amount of the add_on in corresponding order to the listed add_on_codes and listed add_on_types.  \nIf the add_on_type is \"usage\" the \"%\" will be listed",
    "21-3": "numeric",
    "22-0": "version_add_ons_total",
    "22-1": "20",
    "22-2": "Sums the add_on_unit_amounts on the subscription at the time the version was active.  \nDoes not include usage based add ons.",
    "22-3": "numeric",
    "23-0": "version_total_recurring_amount",
    "23-1": "120",
    "23-2": "(version_unit_amount) \\* (version_subscription_quantity) + version_add_on_total",
    "23-3": "numeric",
    "24-0": "version_in_trial",
    "24-1": "Y, N",
    "24-2": "Indicates whether or not the subscription was in trial while the version was active.",
    "24-3": "boolean",
    "25-0": "version_auto_renew",
    "25-1": "Y, N",
    "25-2": "Indicates whether or not the subscription was set to auto renew while the version was active.",
    "25-3": "boolean",
    "26-0": "version_renewal_billing_cycles",
    "26-1": "1",
    "26-2": "Indicated the number of billing cycles a subscription will have after the end of the subscription term.",
    "26-3": "numeric",
    "27-0": "external_sku",
    "27-1": "093094f0420",
    "27-2": "-",
    "27-3": "varchar(50)",
    "28-0": "version_add_on_tier_type",
    "28-1": "flat, tiered, volume, stairstep",
    "28-2": "The pricing model used to calculate the costs for the subscriptions based on the quantity purchased.",
    "28-3": "string",
    "29-0": "version_add_on_source",
    "29-1": "-",
    "29-2": "-",
    "29-3": "string",
    "30-0": "version_add_on_unit_amount_decimal",
    "30-1": "-",
    "30-2": "-",
    "30-3": "numeric",
    "31-0": "version_add_on_billing_model",
    "31-1": "-",
    "31-2": "-",
    "31-3": "string",
    "32-0": "subscription_api_id",
    "32-1": "e28zov4fw0v2",
    "32-2": "Subscription API ID",
    "32-3": "string",
    "33-0": "subscription_add_on_api_id",
    "33-1": "e28zov4fw0v2",
    "33-2": "Add on API ID",
    "33-3": "string"
  },
  "cols": 4,
  "rows": 34,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version changelog

### Version 6 - 2/5/2025

- Addition of `subscription_api_id` and `subscription_add_on_api_id`.

### **Version 5 - 3/9/2022**

- Introduced a new column version_add_on_billing_model.

### **Version 4 - 1/22/2021**

- Introduced a new column version_add_on_unit_amount_decimal.

### **Version 3 - 6/23/2020**

- Introduced a new column version_add_on_source.

### **Version 2 - 4/2/2020**

- Introduced a new column for external SKU concerning saved item add-ons.
- Introduced a new column version_add_on_tier_type.