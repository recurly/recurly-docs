---
title: Subscriptions  - export
excerpt: >-
  Discover the ins and outs of your subscriptions with the detailed
  Subscriptions export section in Recurly's user guide.
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

The Subscriptions export helps you identify accounts that have stored subscriptions along with all the pertinent details of those subscriptions.

# Filters

Distinguish between different subscription statuses using these filters:

- **Live**: All active subscriptions
- **Renewing**: Live subscriptions set to renew post the present term 
- **Trial**: Subscriptions currently in a trial phase
- **Paused**: Subscriptions that are presently on a pause 
- **Canceled**: Subscriptions that will not renew after the present term concludes 
- **Past Due**: Live subscriptions associated with a past-due invoice 
- **Future**: Subscriptions that will activate on reaching the start date 
- **Expired**: Inactive subscriptions 
- **Last Billing**: Refers to subscription is in its last billing period within the selected timeframe. 

### Date Range Filters

Understand your subscriptions' timelines with the following filters:

- **Activated**: Focuses on subscriptions activated in a chosen time range 
- **Modified**: Shows subscriptions altered in the chosen time frame, excluding the original subscription 
- **Created**: Displays subscriptions created within a selected time frame, including those with future activation dates.

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
    "h-0": "<span id=\"Column Name\">Column Name</span>",
    "h-1": "Example",
    "h-2": "Description",
    "h-3": "Datatype (max size)",
    "0-0": "<span id=\"uuid\">uuid</span>",
    "0-1": "b964b5439c2548a489",
    "0-2": "Unique internal identifier for the subscription. Even if a subscription is modified, this identifier is maintained.",
    "0-3": "varchar(32)",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "123456789, [test@example.com](mailto:test@example.com)",
    "1-2": "Account associated with a given subscription UUID.",
    "1-3": "varchar(50)",
    "2-0": "<span id=\"email\">email</span>",
    "2-1": "[test@example.com](mailto:test@example.com)",
    "2-2": "Email address associated with a given subscription UUID.",
    "2-3": "varchar(255)",
    "3-0": "<span id=\"plan_code\">plan_code</span>",
    "3-1": "basic",
    "3-2": "Plan that the customer is subscribed to with this UUID.",
    "3-3": "varchar(50)",
    "4-0": "<span id=\"state\">state</span>",
    "4-1": "pending,  active, canceled, expired",
    "4-2": "Current state of the subscription.",
    "4-3": "string",
    "5-0": "<span id=\"auto_renew\">auto_renew</span>",
    "5-1": "TRUE, FALSE",
    "5-2": "Defaults to TRUE for auto-renewing subscriptions. FALSE if subscription configured to expire at the end of the current term.",
    "5-3": "boolean",
    "6-0": "<span id=\"currency\">currency</span>",
    "6-1": "USD",
    "6-2": "Identifies the currency being charged with this subscription.",
    "6-3": "varchar(3)",
    "7-0": "<span id=\"quantity\">quantity</span>",
    "7-1": "1",
    "7-2": "Identifies the quantity of the subscription purchase.",
    "7-3": "numeric",
    "8-0": "<span id=\"unit_amount\">unit_amount</span>",
    "8-1": "99",
    "8-2": "Identifies the base price of 1 quantity of the subscription",
    "8-3": "numeric",
    "9-0": "<span id=\"add_on_amount\">add_on_amount</span>",
    "9-1": "15",
    "9-2": "Identifies any additional charges to the subscription base fee from add_ons.",
    "9-3": "numeric",
    "10-0": "<span id=\"total_recurring_amount\">total_recurring_amount</span>",
    "10-1": "114",
    "10-2": "Identifies total recurring charges - unit_amount x quantity + add_on_amount.",
    "10-3": "numeric",
    "11-0": "<span id=\"current_period_started_at\">current_period_started_at</span>",
    "11-1": "2009-12-04 00:46:59 PST",
    "11-2": "Date and time that the current billing period starts at.",
    "11-3": "timestamp",
    "12-0": "<span id=\"current_period_ends_at\">current_period_ends_at</span>",
    "12-1": "2009-01-04 00:46:59 PST",
    "12-2": "Date and time that the current billing period ends at",
    "12-3": "timestamp",
    "13-0": "<span id=\"trial_started_at\">trial_started_at</span>",
    "13-1": "2010-03-24 17:18:46 PDT",
    "13-2": "Date and time that a trial period began on the subscription.",
    "13-3": "timestamp",
    "14-0": "<span id=\"trial_ends_at\">trial_ends_at</span>",
    "14-1": "2010-04-23 17:18:46 PDT",
    "14-2": "Date and time that a trial period ends on the subscription.",
    "14-3": "timestamp",
    "15-0": "<span id=\"total_billing_cycles\">total_billing_cycles</span>",
    "15-1": "1",
    "15-2": "This is the total number of billing periods in the current term.",
    "15-3": "numeric",
    "16-0": "<span id=\"remaining_billing_cycles\">remaining_billing_cycles</span>",
    "16-1": "0",
    "16-2": "This is the remaining number of billing periods remaining in the subscription term that will bill. Always 0 for subscriptions with a single billing period term set to auto_renew=true",
    "16-3": "numeric",
    "17-0": "<span id=\"activated_at\">activated_at</span>",
    "17-1": "2010-03-24 17:18:46 PDT",
    "17-2": "Date and time the subscription became active on an account. This might not match to the subscription_created_at date if the subscription is added with a future start date.",
    "17-3": "timestamp",
    "18-0": "<span id=\"modified_at\">modified_at</span>",
    "18-1": "2010-03-24 17:18:44 PDT",
    "18-2": "Date and time the subscription was last updated.",
    "18-3": "timestamp",
    "19-0": "<span id=\"canceled_at\">canceled_at</span>",
    "19-1": "2010-03-28 22:54:46 PDT",
    "19-2": "Date and time the subscription was canceled.",
    "19-3": "timestamp",
    "20-0": "<span id=\"expires_at\">expires_at</span>",
    "20-1": "2010-04-23 22:51:53 PDT",
    "20-2": "Date and time the subscription was/ will churn. This field is populated when a subscription cancels with the expected expiration date.",
    "20-3": "timestamp",
    "21-0": "<span id=\"maintenance_url\">maintenance_url</span>",
    "21-1": "app.recurly.com/account/test",
    "21-2": "Link to the customer's hosted account maintenance URL.",
    "21-3": "string",
    "22-0": "<span id=\"net_terms\">net_terms</span>",
    "22-1": "102",
    "22-2": "Identifies the net_terms agreement associated with the subscription.",
    "22-3": "numeric",
    "23-0": "<span id=\"po_number\">po_number</span>",
    "23-1": "213123",
    "23-2": "For manual invoicing, this identifies the PO number associated with the subscription.",
    "23-3": "varchar(50)",
    "24-0": "<span id=\"collection_method\">collection_method</span>",
    "24-1": "automatic/manual",
    "24-2": "Identifies whether the subscription fees are collected via manual or automatic invoicing.",
    "24-3": "string",
    "25-0": "<span id=\"plan_name\">plan_name</span>",
    "25-1": "Gold",
    "25-2": "The name of the plan associated with the subscription. This is the current name of the plan.",
    "25-3": "varchar(255)",
    "26-0": "<span id=\"started_with_gift\">started_with_gift</span>",
    "26-1": "TRUE, FALSE",
    "26-2": "TRUE if the subscription was started with a gift card, whether or not billing information was collected.",
    "26-3": "boolean",
    "27-0": "<span id=\"no_billing_info_reason\">no_billing_info_reason</span>",
    "27-1": "plan_free_trial",
    "27-2": "Identifies the reason why a subscription did not have billing information at time of renewal/activation.",
    "27-3": "string",
    "28-0": "<span id=\"converted_at\">converted_at</span>",
    "28-1": "2016-09-02 15:53:18 UTC",
    "28-2": "Date of the first successful transaction for the subscription. This field is only used for gifts cards and cardless free trial conversions. In other words, it will only have a value if started_with_gift is `TRUE` OR no_billing_info_reason is \"plan_free\" trial. \" Converted_at compared to the subscription's activated_at will give you the time to conversion.",
    "28-3": "timestamp",
    "29-0": "<span id=\"paused_at\">paused_at</span>",
    "29-1": "2018-05-13 00:00:12 MDT",
    "29-2": "Date of subscription pause initiation.",
    "29-3": "timestamp",
    "30-0": "<span id=\"remaining_pause_cycles\">remaining_pause_cycles</span>",
    "30-1": "9",
    "30-2": "Identifies the number of remaining billing cycles for the subscription that is either currently paused or scheduled to pause.",
    "30-3": "numeric",
    "31-0": "<span id=\"current_term_started_at\">current_term_started_at</span>",
    "31-1": "2018-12-04 00:46:59 PST",
    "31-2": "Date and time that the current term started at.  This currently is an unpopulated field relating to an upcoming feature which will be released later this year.",
    "31-3": "timestamp",
    "32-0": "<span id=\"current_term_ends_at\">current_term_ends_at</span>",
    "32-1": "2019-12-04 00:46:59 PST",
    "32-2": "Date and time that the current term ends at.  This currently is an unpopulated field relating to an upcoming feature which will be released later this year.",
    "32-3": "timestamp",
    "33-0": "<span id=\"renewal_billing_cycles\">renewal_billing_cycles</span>",
    "33-1": "1",
    "33-2": "The length of a subscription's next term, if auto_renew = true,  NIL if subscription auto_renew = false",
    "33-3": "numeric",
    "34-0": "<span id=\"shipping_amount_in_cents\">shipping_amount_in_cents</span>",
    "34-1": "500",
    "34-2": "The shipping fee on the subscription, in cents.",
    "34-3": "numeric",
    "35-0": "<span id=\"shipping_method_code\">shipping_method_code</span>",
    "35-1": "usps-overnight",
    "35-2": "The code from the shipping method (created through the UI).",
    "35-3": "varchar(50)",
    "36-0": "<span id=\"pricing_model\">pricing_model</span>",
    "36-1": "ramp",
    "36-2": "Pricing model of the subscription. Will be either fixed or ramp.",
    "36-3": "string",
    "37-0": "<span id=\"current_ramp_id\">current_ramp_id</span>",
    "37-1": "pz82514rbd3s",
    "37-2": "The id of the current ramp interval.",
    "37-3": "string",
    "38-0": "<span id=\"tax_inclusive\">tax_inclusive</span>",
    "38-1": "true",
    "38-2": "Indicates whether the subscription is billed inclusively or exclusively of tax.",
    "38-3": "boolean",
    "39-0": "subscription_api_id",
    "39-1": "e28zov4fw0v2",
    "39-2": "Subscription API ID",
    "39-3": "string",
    "40-0": "gateway_code",
    "40-1": "e28zov4fw0v2",
    "40-2": "Gateway Code",
    "40-3": "string"
  },
  "cols": 4,
  "rows": 41,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

#### Version 6 - 2/5/2025

- Addition of `subscription_api_id` and `gateway_code`.

#### Version 5 - 1/10/2022

- Added a column to indicate tax inclusive. 

#### Version 4 - 12/7/2021

- Added a column for the pricing model
- Introduced a column for current_ramp_id

#### Version 3 - 5/2/2019

- A new column was added to show the Shipping Cost
- Added a column for indicating the Shipping Method

#### Version 2 - 9/6/2018

- Introduced column additions for Custom Fields 
- Custom fields will now be the last column in the export and will only appear if exports are enabled in the custom field definition