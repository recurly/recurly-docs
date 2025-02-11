---
title: Billing info - export
excerpt: Explore the detailed guide on Billing Info export in Recurly's user guide.
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

The “Billing Info” export section in Recurly's user guide helps you identify and understand the billing information and payment methods associated with various accounts. It offers data that aids in distinguishing primary from backup payment methods, along with comprehensive billing details to keep track of each account’s status and payment preferences.

# Filters

### Account Status Filter

You can filter the billing information export data based on the account status. Here is how different statuses are defined:

- **Open**: Accounts that are currently not closed.
- **Non-subscribers**: Open accounts that do not have any active subscriptions.
- **Active Subscribers**: Open accounts holding at least one active subscription.
- **In Trial**: Accounts holding one or more subscriptions in the trial phase.
- **Past Due**: Accounts having at least one invoice in the past-due state.
- **Non-Renewing**: Accounts with subscriptions that will not renew post the current billing cycle; recently canceled.
- **Future**: Accounts with a subscription that hasn't yet begun.

### Time Range Filter

Utilize the "created_at" field to filter data showcasing the accounts that had billing information added within a selected timeframe.

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
    "0-0": "<span id=\"account_code\">account_code</span>",
    "0-1": "123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)",
    "0-2": "Uniquely identifies your customers in Recurly, mainly using the email address.",
    "0-3": "varchar(50)",
    "1-0": "<span id=\"billing_first_name\">billing_first_name</span>",
    "1-1": "JJ",
    "1-2": "The first name provided in the customer's billing details.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"billing_last_name\">billing_last_name</span>",
    "2-1": "Smith",
    "2-2": "The last name provided in the customer's billing details.",
    "2-3": "varhcar(255)",
    "3-0": "<span id=\"account_company_name\">account_company_name</span>",
    "3-1": "Bluth Industries, Inc.",
    "3-2": "Company name as per the billing details.",
    "3-3": "varchar(255)",
    "4-0": "<span id=\"billing_address1\">billing_address1</span>",
    "4-1": "123 Main Street",
    "4-2": "The first line of the customer's billing address.",
    "4-3": "varchar(60)",
    "5-0": "<span id=\"billing_address2\">billing_address2</span>",
    "5-1": "Suite 300",
    "5-2": "The second line of the customer's billing address.",
    "5-3": "varchar(60)",
    "6-0": "<span id=\"billing_city\">billing_city</span>",
    "6-1": "San Francisco",
    "6-2": "The city component of the customer's billing address.",
    "6-3": "varchar(60)",
    "7-0": "<span id=\"billing_state\">billing_state</span>",
    "7-1": "CA",
    "7-2": "The state component of the customer's billing address.",
    "7-3": "varchar(60)",
    "8-0": "<span id=\"billing_postal_code\">billing_postal_code</span>",
    "8-1": "94107",
    "8-2": "The postal code component of the customer's billing address.",
    "8-3": "varchar(20)",
    "9-0": "<span id=\"billing_country\">billing_country</span>",
    "9-1": "US",
    "9-2": "The country component of the customer's billing address.",
    "9-3": "varchar(30)",
    "10-0": "<span id=\"billing_phone\">billing_phone</span>",
    "10-1": "555-2368",
    "10-2": "The phone number provided in the customer's billing details.",
    "10-3": "varchar(30)",
    "11-0": "<span id=\"account_email\">account_email</span>",
    "11-1": "[test@example.com](mailto:test@example.com)",
    "11-2": "The email address associated with the customer's account.",
    "11-3": "varchar(255)",
    "12-0": "<span id=\"cc_type\">cc_type</span>",
    "12-1": "visa/master/discover/jcb/amex/diners",
    "12-2": "Indicates the type of credit card associated with the customer's account.",
    "12-3": "varchar(20)",
    "13-0": "<span id=\"cc_last_four\">cc_last_four</span>",
    "13-1": "1111",
    "13-2": "The last four digits of the customer's credit card number.",
    "13-3": "varchar(4)",
    "14-0": "<span id=\"expire_month\">expire_month</span>",
    "14-1": "4",
    "14-2": "The month when the customer's credit card expires.",
    "14-3": "numeric",
    "15-0": "<span id=\"expire_year\">expire_year</span>",
    "15-1": "2014",
    "15-2": "The year when the customer's credit card expires.",
    "15-3": "numeric",
    "16-0": "<span id=\"billing_vat_number\">billing_vat_number</span>",
    "16-1": "IE213123123",
    "16-2": "VAT number provided by EU customers.",
    "16-3": "string",
    "17-0": "<span id=\"created_at\">created_at</span>",
    "17-1": "2011-08-15",
    "17-2": "The date when the billing information was added to the account.",
    "17-3": "timestamp",
    "18-0": "<span id=\"updated_at\">updated_at</span>",
    "18-1": "2013-09-12",
    "18-2": "The last date when the billing information was updated on the account.",
    "18-3": "timestamp",
    "19-0": "<span id=\"Payment_method\">Payment_method</span>",
    "19-1": "CreditCard / PayPal/ Roku/ Amazon / Bank Account / paypal_braintree, jcb, qiwiwallet, etc.",
    "19-2": "The payment method chosen by the customer for transactions.",
    "19-3": "string",
    "20-0": "<span id=\"maintenance_url\">maintenance_url</span>",
    "20-1": "app.recurly.com/account/sdasdasd",
    "20-2": "The URL directing to the customer's hosted account maintenance.",
    "20-3": "string",
    "21-0": "<span id=\"geo_code\">geo_code</span>",
    "21-1": "-",
    "21-2": "-",
    "21-3": "string",
    "22-0": "<span id=\"ip_address\">ip_address</span>",
    "22-1": "99.89.1010.0101",
    "22-2": "The IP address noted at the time of entering the billing information.",
    "22-3": "varchar(20)",
    "23-0": "<span id=\"ip_address_country\">ip_address_country</span>",
    "23-1": "US",
    "23-2": "The country associated with the IP address noted during billing information entry.",
    "23-3": "Varchar(2)",
    "24-0": "<span id=\"cc_first_6\">cc_first_6</span>",
    "24-1": "111111",
    "24-2": "The initial six digits of the credit card used for the transaction.",
    "24-3": "varchar(6)",
    "25-0": "<span id=\"primary_payment_method\">primary_payment_method</span>",
    "25-1": "true, false",
    "25-2": "Indicates whether the billing info should be used as a primary payment method.",
    "25-3": "boolean",
    "26-0": "<span id=\"billing_info_id\">billing_info_id</span>",
    "26-1": "123456789",
    "26-2": "Unique identifier for billing info.",
    "26-3": "string",
    "27-0": "<span id=\"backup_payment_method\">backup_payment_method</span>",
    "27-1": "true, false",
    "27-2": "Indicates whether the billing info should be used as a backup for invoice failures.",
    "27-3": "boolean",
    "28-0": "billing_info_api_id",
    "28-1": "e28zov4fw0v2",
    "28-2": "Billing Info API ID",
    "28-3": "string"
  },
  "cols": 4,
  "rows": 29,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 7 - 02/5/24

- Addition of `billing_info_api_id`.

### Version 6 - 03/29/21

- Introduction of the backup_payment_method column to highlight if the billing info is the backup payment method (TRUE/FALSE).

### Version 5 - 12/3/20

- Introduction of the “primary_payment_method” column to indicate if the billing info is the main payment method (TRUE/FALSE).
- Addition of billing_info_id displaying the ID of the billing info.

### Version 4 - 5/23/2019

- 'cc_first_6' column was moved to the end of the export.

### Version 3 - 4/25/2019

- Addition of "cc_first_6" to the export.

### Version 2 - 5/24/2018

- Column names were refined to differentiate clearly between billing and account info.
- Addition of "ip_address" and "ip_address_country" columns to the export.
- Addition of “geo_code” column. (Applicable only if Vertex tax integration is enabled)