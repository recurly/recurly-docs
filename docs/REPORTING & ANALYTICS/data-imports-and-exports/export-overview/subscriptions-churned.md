---
title: Subscriptions — churned - export
excerpt: Track and export data on churned Recurly subscriptions with ease.
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

In the Recurly platform, a "Churned Subscription" refers to subscriptions that have churned and are no longer active. This information is vital in understanding subscription lifecycles and trends in user retention.

# Filters

### Time Range Filter

To get specific data, use the Time Range Filter which exports all the subscriptions that expired during a selected time frame. This filter uses the "expired_at" column in the export. Note that a subscription does not churn until it has expired, and the "canceled_at" and "expired_at" dates are not the same.

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
    "0-0": "<span id=\"uuid\">uuid</span>",
    "0-1": "5eg5bcc7ef8211e0a908005056b00005",
    "0-2": "Unique identifier for a specific subscription plan.",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "123456789, [test@example.com](mailto:test@example.com)",
    "1-2": "Account associated with a given subscription UUID.",
    "2-0": "<span id=\"email\">email</span>",
    "2-1": "[test@example.com](mailto:test@example.com)",
    "2-2": "Email address associated with a given subscription UUID.",
    "3-0": "<span id=\"plan_code\">plan_code</span>",
    "3-1": "basic",
    "3-2": "Plan that the customer is subscribed to with this UUID.",
    "4-0": "<span id=\"state\">state</span>",
    "4-1": "pending, modified, converted, active, canceled, expired",
    "4-2": "Current state of the subscription. Modified and converted are depreciated states",
    "5-0": "<span id=\"auto_renew\">auto_renew</span>",
    "5-1": "TRUE",
    "5-2": "Defaults to TRUE for auto-renewing subscriptions. FALSE if subscription set to expire at end of current term.",
    "6-0": "<span id=\"currency\">currency</span>",
    "6-1": "USD",
    "6-2": "Identifies the currency being charged with this subscription.",
    "7-0": "<span id=\"quantity\">quantity</span>",
    "7-1": "1",
    "7-2": "Identifies the quantity of the subscription purchase.",
    "8-0": "<span id=\"unit_amount\">unit_amount</span>",
    "8-1": "99",
    "8-2": "Identifies the base price of 1 quantity of the subscription.",
    "9-0": "<span id=\"add_on_amount\">add_on_amount</span>",
    "9-1": "15",
    "9-2": "Identifies any additional charges to the subscription base fee from add_ons.",
    "10-0": "<span id=\"total_recurring_amount\">total_recurring_amount</span>",
    "10-1": "114",
    "10-2": "Identifies total recurring charges - unit_amount x quantity + add_on_amount.",
    "11-0": "<span id=\"current_period_started_at\">current_period_started_at</span>",
    "11-1": "2009-12-04 00:46:59 PST",
    "11-2": "Date and time that the current billing period started. \\*",
    "12-0": "<span id=\"current_period_ends_at\">current_period_ends_at</span>",
    "12-1": "2009-12-04 00:46:59 PST",
    "12-2": "Date and time that the current billing period ends at.",
    "13-0": "<span id=\"trial_started_at\">trial_started_at</span>",
    "13-1": "2010-03-24 17:18:46 PDT",
    "13-2": "Date and time that a trial period began on the subscription.",
    "14-0": "<span id=\"trial_ends_at\">trial_ends_at</span>",
    "14-1": "2010-04-23 17:18:46 PDT",
    "14-2": "Date and time that a trial period ends on the subscription.",
    "15-0": "<span id=\"total_billing_cycles\">total_billing_cycles</span>",
    "15-1": "1",
    "15-2": "This is the total number billing periods in the subscription term.",
    "16-0": "<span id=\"remaining_billing_cycles\">remaining_billing_cycles</span>",
    "16-1": "0",
    "16-2": "Number of remaining billing periods in the subscription’s current term. Will always be 0 if subscription term has 1 billing period",
    "17-0": "<span id=\"renewal_billing_cycles\">renewal_billing_cycles</span>",
    "17-1": "1",
    "17-2": "Number of billing periods in the subscription’s next term. Will default to plan’s total_billing_cycles unless customized. Nil if auto_renew = false",
    "18-0": "<span id=\"current_term_started_at\">current_term_started_at</span>",
    "18-1": "2018-09-02 15:53:18 UTC",
    "18-2": "Start date of the subscription’s current term",
    "19-0": "<span id=\"current_term_ends_at\">current_term_ends_at</span>",
    "19-1": "2018-10-02 15:53:18 UTC",
    "19-2": "End date of the subscription’s current term.",
    "20-0": "<span id=\"activated_at\">activated_at</span>",
    "20-1": "2010-03-24 17:18:46 PDT",
    "20-2": "Date and time the subscription was added to the account.",
    "21-0": "<span id=\"modified_at\">modified_at</span>",
    "21-1": "2010-03-24 17:18:44 PDT",
    "21-2": "Date and time the subscription was last updated.",
    "22-0": "<span id=\"canceled_at\">canceled_at</span>",
    "22-1": "2010-03-28 22:54:46 PDT",
    "22-2": "Date and time the subscription was canceled.",
    "23-0": "<span id=\"expires_at\">expires_at</span>",
    "23-1": "2010-04-23 22:51:53 PDT",
    "23-2": "Date and time the subscription was terminated. **Used for date range filter** ",
    "24-0": "<span id=\"maintenance_url\">maintenance_url</span>",
    "24-1": "app.recurly.com/account/sdasdasdad213525asdad",
    "24-2": "Link to the customer's hosted account maintenance URL.",
    "25-0": "<span id=\"net_terms\">net_terms</span>",
    "25-1": "on-receipt",
    "25-2": "Identifies the net_terms agreement associated with the subscription.",
    "26-0": "<span id=\"po_number\">po_number</span>",
    "26-1": "213123",
    "26-2": "For manual invoicing, this identifies the PO number associated with the subscription.",
    "27-0": "<span id=\"collection_method\">collection_method</span>",
    "27-1": "automatic/manual",
    "27-2": "Identifies whether the subscription fees are collected via manual or automatic invoicing",
    "28-0": "<span id=\"plan_name\">plan_name</span>",
    "28-1": "Basic Plan",
    "28-2": "The plan name of the subscription at the time the subscription expired",
    "29-0": "<span id=\"expiration_reason\">expiration_reason</span>",
    "29-1": "Canceled, Non-payment, Fixed billing cycles, Tax Location Invalid, Nonpayment_gift, Nonpayment_trial",
    "29-2": "The reason that the subscription expired. Note that nonpayment_Trial only relates to cardless subscriptions trials",
    "30-0": "<span id=\"ship_address_id\">ship_address_id</span>",
    "30-1": "2019760433389770000",
    "30-2": "The unique ID assigned to the shipping address",
    "31-0": "<span id=\"ship_address_nickname\">ship_address_nickname</span>",
    "31-1": "Julie",
    "31-2": "The nickname given to the shipping address",
    "32-0": "<span id=\"ship_address_firstname\">ship_address_firstname</span>",
    "32-1": "Julie",
    "32-2": "The first name associated with the shipping address",
    "33-0": "<span id=\"ship_address_lastname\">ship_address_lastname</span>",
    "33-1": "Smith",
    "33-2": "The last name associated with the shipping address",
    "34-0": "<span id=\"ship_address_company_name\">ship_address_company_name</span>",
    "34-1": "Big Company",
    "34-2": "The company name associated with the shipping address",
    "35-0": "<span id=\"ship_address_street1\">ship_address_street1</span>",
    "35-1": "321 Michigan Street",
    "35-2": "The first line of the street address for the shipping address",
    "36-0": "<span id=\"ship_address_street2\">ship_address_street2</span>",
    "36-1": "Apt 1",
    "36-2": "The second line of the street address for the shipping address",
    "37-0": "<span id=\"ship_address_city\">ship_address_city</span>",
    "37-1": "West Bloomfield",
    "37-2": "The city for the shipping address",
    "38-0": "<span id=\"ship_address_state\">ship_address_state</span>",
    "38-1": "MI",
    "38-2": "The state for the shipping address",
    "39-0": "<span id=\"ship_address_zip\">ship_address_zip</span>",
    "39-1": "48322",
    "39-2": "The zip or postal code for the shipping address",
    "40-0": "<span id=\"ship_address_country\">ship_address_country</span>",
    "40-1": "US",
    "40-2": "The country for the shipping address",
    "41-0": "<span id=\"ship_address_vat\">ship_address_vat</span>",
    "41-1": "123456789",
    "41-2": "The VAT number associated with the shipping address",
    "42-0": "<span id=\"ship_address_email\">ship_address_email</span>",
    "42-1": "[jsmith@example.com](mailto:jsmith@example.com)",
    "42-2": "The email address associated with the shipping address",
    "43-0": "<span id=\"ship_address_phone\">ship_address_phone</span>",
    "43-1": "248-555-1212",
    "43-2": "The phone number associated with the shipping address",
    "44-0": "<span id=\"started_with_gift\">started_with_gift</span>",
    "44-1": "TRUE, FALSE",
    "44-2": "`TRUE` if the subscription was started with a gift card, whether or not billing information was collected.",
    "45-0": "<span id=\"converted_at\">converted_at</span>",
    "45-1": "2016-09-02 15:53:18 UTC",
    "45-2": "Date of the first successful transaction for the subscription.  \nThis field is only used for gifts cards and cardless free trial conversions.  \nIn other words, it will only have a value if started_with_gift is `TRUE` OR no_billing_info_reason is \"plan_free\"trial.\" Converted_at compared to the subscription's activated_at will give you the time to conversion.",
    "46-0": "<span id=\"no_billing_info_reason\">no_billing_info_reason</span>",
    "46-1": "plan_free_trial",
    "46-2": "Identifies the reason why a subscription did not have billing information at time of renewal/activation.",
    "47-0": "<span id=\"shipping_amount_in_cents\">shipping_amount_in_cents</span>",
    "47-1": "500",
    "47-2": "The amount of the shipping fee on the subscription, in cents.",
    "48-0": "<span id=\"shipping_method_code\">shipping_method_code</span>",
    "48-1": "usps_overnight",
    "48-2": "The code of the Shipping Method from configuration.",
    "49-0": "<span id=\"pricing_model\">pricing_model</span>",
    "49-1": "ramp",
    "49-2": "Pricing model of the subscription. Will be either fixed or ramp.",
    "50-0": "<span id=\"current_ramp_id\">current_ramp_id</span>",
    "50-1": "pz82514rbd3s",
    "50-2": "The id of the current ramp interval.",
    "51-0": "subscription_api_id",
    "51-1": "e28zov4fw0v2",
    "51-2": "Subscription API ID"
  },
  "cols": 3,
  "rows": 52,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version changelog

### Version 4 - 2/5/2025

- Addition of `subscription_api_id`.

### Version 3 - 12/7/2021

- Column added for pricing_model 
- Column added for current_ramp_id

### Version 2 - 5/2/2019

- Column added for Shipping Cost
- Column added for Shipping Method