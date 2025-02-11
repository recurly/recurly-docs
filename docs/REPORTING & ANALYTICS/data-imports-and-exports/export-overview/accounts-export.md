---
title: Accounts - export
excerpt: Explore detailed account insights with Recurly's Accounts Export feature.
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

The "Accounts Export" section in the Recurly user guide helps users grasp comprehensive insights about individual accounts. This data-rich section assists in efficiently managing and understanding account specifics with a myriad of filters and detailed export content.

# Filters

### Account status filter

- **Open**: Active and operational accounts.
- **Non-subscribers**: Active accounts that currently hold no active subscriptions.
- **Active Subscribers**: Active accounts with one or more active subscriptions.
- **In Trial**: Accounts with at least one subscription undergoing a trial period.
- **Past Due**: Subscribers having at least one invoice past its due date.
- **Non-Renewing**: Subscribers not renewing after the ongoing term concludes.
- **Future**: Accounts holding a subscription set to activate in the future.
- **Closed**: Accounts that are not active.

### Date range filters

- **Created**: Filter accounts based on their creation date within a selected range.
- **Modified**: Filter accounts based on the modification date within the specified range.

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
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"account_code\">account_code</span>",
    "0-1": "123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)",
    "0-2": "Unique identifier for your customers in Recurly, defaulting to the email address if unspecified. Unmodifiable and central to linking multiple exports.",
    "0-3": "varchar(50)",
    "1-0": "<span id=\"account_email\">account_email</span>",
    "1-1": "[test@example.com](mailto:test@example.com)",
    "1-2": "The email given by the customer at signup, utilized for all customer communications.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"account_username\">account_username</span>",
    "2-1": "jjsmith",
    "2-2": "Optional field for importing usernames associated with your product.",
    "2-3": "varchar(255)",
    "3-0": "<span id=\"account_company_name\">account_company_name</span>",
    "3-1": "Bluth Industries, Inc.",
    "3-2": "Optional field for recording the company name provided.",
    "3-3": "varchar(255)",
    "4-0": "<span id=\"account_first_name\">account_first_name</span>",
    "4-1": "JJ",
    "4-2": "The first name of the customer.",
    "4-3": "varchar(255)",
    "5-0": "<span id=\"account_last_name\">account_last_name</span>",
    "5-1": "Smith",
    "5-2": "The last name of the customer.",
    "5-3": "varchar(255)",
    "6-0": "<span id=\"account_has_billing_info\">account_has_billing_info</span>",
    "6-1": "TRUE, FALSE",
    "6-2": "Denotes the existence of billing information on the account.",
    "6-3": "boolean",
    "7-0": "<span id=\"account_created_at\">account_created_at</span>",
    "7-1": "2012-06-27 03:47:28 PDT",
    "7-2": "Date and time when the account was created, used in \"created\" date range filter.",
    "7-3": "timestamp",
    "8-0": "<span id=\"account_address1\">account_address1</span>",
    "8-1": "1234 Main St",
    "8-2": "The primary address line for the account.",
    "8-3": "string",
    "9-0": "<span id=\"account_address2\">account_address2</span>",
    "9-1": "Suite #123",
    "9-2": "The secondary address line for the account.",
    "9-3": "string",
    "10-0": "<span id=\"account_city\">account_city</span>",
    "10-1": "San Francisco",
    "10-2": "The city related to the account's address.",
    "10-3": "string",
    "11-0": "<span id=\"account_state\">account_state</span>",
    "11-1": "CA",
    "11-2": "The state pertaining to the account's address.",
    "11-3": "string",
    "12-0": "<span id=\"account_postal_code\">account_postal_code</span>",
    "12-1": "94105",
    "12-2": "The postal code of the account's address.",
    "12-3": "string",
    "13-0": "<span id=\"account_country\">account_country</span>",
    "13-1": "US",
    "13-2": "The country associated with the account's address.",
    "13-3": "string",
    "14-0": "<span id=\"account_phone\">account_phone</span>",
    "14-1": "4155559876",
    "14-2": "The phone number associated with the account.",
    "14-3": "string",
    "15-0": "<span id=\"account_vat_number\">account_vat_number</span>",
    "15-1": "US1234567890",
    "15-2": "The account's verified VAT number (applicable in production sites).",
    "15-3": "varchar(20)",
    "16-0": "<span id=\"account_tax_exempt\">account_tax_exempt</span>",
    "16-1": "TRUE, FALSE",
    "16-2": "Indicates whether the account is exempt from tax collection.",
    "16-3": "boolean",
    "17-0": "<span id=\"modified_at\">modified_at</span>",
    "17-1": "2014-01-01 10:00:00 PST",
    "17-2": "The date and time the account was last modified, utilized in \"modified\" date range filter.",
    "17-3": "timestamp",
    "18-0": "<span id=\"closed_at\">closed_at</span>",
    "18-1": "2014-01-01 10:00:00 PST",
    "18-2": "Indicates the most recent closure date for the account.",
    "18-3": "timestamp",
    "19-0": "<span id=\"account_acquisition_cost\">account_acquisition_cost</span>",
    "19-1": "360",
    "19-2": "Captures the cost to acquire a customer, can be fed data from marketing or CRM systems.",
    "19-3": "numeric",
    "20-0": "<span id=\"account_acquisition_currency\">account_acquisition_currency</span>",
    "20-1": "USD",
    "20-2": "Records the currency used for noting down Customer Acquisition Cost.",
    "20-3": "varchar(3)",
    "21-0": "<span id=\"account_acquisition_channel\">account_acquisition_channel</span>",
    "21-1": "Referral",
    "21-2": "Denotes the marketing channel that facilitated customer acquisition.",
    "21-3": "numeric",
    "22-0": "<span id=\"account_acquisition_subchannel\">account_acquisition_subchannel</span>",
    "22-1": "Facebook",
    "22-2": "A field noting the detailed acquisition channel.",
    "22-3": "varchar(50)",
    "23-0": "<span id=\"account_acquisition_campaign\">account_acquisition_campaign</span>",
    "23-1": "12345",
    "23-2": "Tracks the specific marketing campaign ID from your tools.",
    "23-3": "varchar(50)",
    "24-0": "<span id=\"account_acquisition_created_at\">account_acquisition_created_at</span>",
    "24-1": "2014-01-01 10:00:00 PST",
    "24-2": "Marks when the acquisition data was first added to the account.",
    "24-3": "timestamp",
    "25-0": "<span id=\"account_acquisition_modified_at\">account_acquisition_modified_at</span>",
    "25-1": "2014-01-01 10:00:00 PST",
    "25-2": "Notes the last update timestamp for acquisition data on the account.",
    "25-3": "timestamp",
    "26-0": "<span id=\"location_validation_tax_type\">location_validation_tax_type</span>",
    "26-1": "eu, nz",
    "26-2": "Identifies the region for tax location validation run on the account, visible based on specific enabled regional settings.",
    "26-3": "varchar(2)",
    "27-0": "<span id=\"account_geo_code\">account_geo_code</span>",
    "27-1": "123456789",
    "27-2": "Identifies account geo code.",
    "27-3": "numeric",
    "28-0": "<span id=\"parent_account_code\">parent_account_code</span>",
    "28-1": "123456789",
    "28-2": "Identifies parent account code.",
    "28-3": "varchar(50)",
    "29-0": "<span id=\"primary_payment_method\">primary_payment_method</span>",
    "29-1": "TRUE/FALSE",
    "29-2": "Identifies whether the billing info is either primary payment method or not.",
    "29-3": "boolean",
    "30-0": "<span id=\"billing_info_id\">billing_info_id</span>",
    "30-1": "1234",
    "30-2": "Unique identifier for billing info.",
    "30-3": "string",
    "31-0": "<span id=\"dunning_campaign_code\">dunning_campaign_code</span>",
    "31-1": "123456",
    "31-2": "Identifies dunning campaign code.",
    "31-3": "varchar(50)",
    "32-0": "<span id=\"dunning_campaign_id\">dunning_campaign_id</span>",
    "32-1": "1234567",
    "32-2": "Identifies dunning campaign id.",
    "32-3": "string",
    "33-0": "<span id=\"preferred_locale\">preferred_locale</span>",
    "33-1": "en-US",
    "33-2": "Identifies account's preferred locale.",
    "33-3": "varchar(50)",
    "34-0": "account_api_id",
    "34-1": "e28zov4fw0v2",
    "34-2": "Account API ID",
    "34-3": "string"
  },
  "cols": 4,
  "rows": 35,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version Changelog

#### Version 7 - 2/5/2025

Addition of `account_api_id`

#### Version 6 - 06/14/23

Added account’s preferred locale column  
`preferred_locale`

#### Version 5 - 07/23/21

Added Dunning campaign columns  
`dunning_campaign_code`  
`dunning_campaign_id`

#### Version 4 - 12/10/20

- The `tax_location_valid` column now relates to the specific billing info in each row.
- Introduced `primary_payment_method` column displaying TRUE or FALSE based on the primary payment method status of the billing info.
- New `billing_info_id` column showcasing the ID of the particular billing info.

#### Version 3 - 9/13/18

- Added `parent_account_code` column for the Account Hierarchy feature, helping in identifying an account's parent if applicable, though it will only hold a value if the feature is active.

#### Version 2 - 9/6/18

- Introduction of columns for custom fields, placed at the end of the export.