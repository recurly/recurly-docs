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

* **Open**: Active and operational accounts.
* **Non-subscribers**: Active accounts that currently hold no active subscriptions.
* **Active Subscribers**: Active accounts with one or more active subscriptions.
* **In Trial**: Accounts with at least one subscription undergoing a trial period.
* **Past Due**: Subscribers having at least one invoice past its due date.
* **Non-Renewing**: Subscribers not renewing after the ongoing term concludes.
* **Future**: Accounts holding a subscription set to activate in the future.
* **Closed**: Accounts that are not active.

### Date range filters

* **Created**: Filter accounts based on their creation date within a selected range.
* **Modified**: Filter accounts based on the modification date within the specified range.

# Exports table

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Button</title>
    <style>
        .download-button {
            display: inline-block;
            padding: 5px 10px;
            text-align: center;
            text-decoration: none;
            color: #1C2833FF; 
            background-color: #F8F8F8FF; 
            border-radius: 5px;
            font-weight: normal;
            transition: background-color 0.5s ease, transform 0.3s ease;
          	transition: 0.4s !important;
            font-family: 'Proxima-nova', Arial, sans-serif;
            max-width: 100%; 
        }

        .download-button:hover {
            background-color: #FFFFFFFF; 
            transform: scale(1.02); 
        }
      	a:hover {
          	color: #1C2833FF;
          	text-decoration: underline !important;
        }
      </style>
</head>
<body>
    <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
</body>
</html>
`}</HTMLBlock>

To help you identify and organize information effectively, the export provides a structured table that contains the following columns:

| Id                                                                                   | Example                                                                                                        | Description                                                                                                                                            | Data type (max size) |
| :----------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------- |
| <span id="account_code">account\_code</span>                                         | 123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)                                                       | Unique identifier for your customers in Recurly, defaulting to the email address if unspecified. Unmodifiable and central to linking multiple exports. | varchar(50)          |
| <span id="account_email">account\_email</span>                                       | [test@example.com](mailto:test@example.com)                                                                    | The email given by the customer at signup, utilized for all customer communications.                                                                   | varchar(255)         |
| <span id="account_username">account\_username</span>                                 | jjsmith                                                                                                        | Optional field for importing usernames associated with your product.                                                                                   | varchar(255)         |
| <span id="account_company_name">account\_company\_name</span>                        | Bluth Industries, Inc.                                                                                         | Optional field for recording the company name provided.                                                                                                | varchar(255)         |
| <span id="account_first_name">account\_first\_name</span>                            | JJ                                                                                                             | The first name of the customer.                                                                                                                        | varchar(255)         |
| <span id="account_last_name">account\_last\_name</span>                              | Smith                                                                                                          | The last name of the customer.                                                                                                                         | varchar(255)         |
| <span id="account_has_billing_info">account\_has\_billing\_info</span>               | TRUE, FALSE                                                                                                    | Denotes the existence of billing information on the account.                                                                                           | boolean              |
| <span id="account_created_at">account\_created\_at</span>                            | 2012-06-27 03:47:28 PDT                                                                                        | Date and time when the account was created, used in "created" date range filter.                                                                       | timestamp            |
| <span id="account_address1">account\_address1</span>                                 | 1234 Main St                                                                                                   | The primary address line for the account.                                                                                                              | string               |
| <span id="account_address2">account\_address2</span>                                 | Suite #123                                                                                                     | The secondary address line for the account.                                                                                                            | string               |
| <span id="account_city">account\_city</span>                                         | San Francisco                                                                                                  | The city related to the account's address.                                                                                                             | string               |
| <span id="account_state">account\_state</span>                                       | CA                                                                                                             | The state pertaining to the account's address.                                                                                                         | string               |
| <span id="account_postal_code">account\_postal\_code</span>                          | 94105                                                                                                          | The postal code of the account's address.                                                                                                              | string               |
| <span id="account_country">account\_country</span>                                   | US                                                                                                             | The country associated with the account's address.                                                                                                     | string               |
| <span id="account_phone">account\_phone</span>                                       | 4155559876                                                                                                     | The phone number associated with the account.                                                                                                          | string               |
| <span id="account_vat_number">account\_vat\_number</span>                            | US1234567890                                                                                                   | The account's verified VAT number (applicable in production sites).                                                                                    | varchar(20)          |
| <span id="account_tax_exempt">account\_tax\_exempt</span>                            | TRUE, FALSE                                                                                                    | Indicates whether the account is exempt from tax collection.                                                                                           | boolean              |
| <span id="modified_at">modified\_at</span>                                           | 2014-01-01 10:00:00 PST                                                                                        | The date and time the account was last modified, utilized in "modified" date range filter.                                                             | timestamp            |
| <span id="closed_at">closed\_at</span>                                               | 2014-01-01 10:00:00 PST                                                                                        | Indicates the most recent closure date for the account.                                                                                                | timestamp            |
| <span id="account_acquisition_cost">account\_acquisition\_cost</span>                | 360                                                                                                            | Captures the cost to acquire a customer, can be fed data from marketing or CRM systems.                                                                | numeric              |
| <span id="account_acquisition_currency">account\_acquisition\_currency</span>        | USD                                                                                                            | Records the currency used for noting down Customer Acquisition Cost.                                                                                   | varchar(3)           |
| <span id="account_acquisition_channel">account\_acquisition\_channel</span>          | Referral                                                                                                       | Denotes the marketing channel that facilitated customer acquisition.                                                                                   | numeric              |
| <span id="account_acquisition_subchannel">account\_acquisition\_subchannel</span>    | Facebook                                                                                                       | A field noting the detailed acquisition channel.                                                                                                       | varchar(50)          |
| <span id="account_acquisition_campaign">account\_acquisition\_campaign</span>        | 12345                                                                                                          | Tracks the specific marketing campaign ID from your tools.                                                                                             | varchar(50)          |
| <span id="account_acquisition_created_at">account\_acquisition\_created\_at</span>   | 2014-01-01 10:00:00 PST                                                                                        | Marks when the acquisition data was first added to the account.                                                                                        | timestamp            |
| <span id="account_acquisition_modified_at">account\_acquisition\_modified\_at</span> | 2014-01-01 10:00:00 PST                                                                                        | Notes the last update timestamp for acquisition data on the account.                                                                                   | timestamp            |
| <span id="location_validation_tax_type">location\_validation\_tax\_type</span>       | eu, nz                                                                                                         | Identifies the region for tax location validation run on the account, visible based on specific enabled regional settings.                             | varchar(2)           |
| <span id="account_geo_code">account\_geo\_code</span>                                | 123456789                                                                                                      | Identifies account geo code.                                                                                                                           | numeric              |
| <span id="parent_account_code">parent\_account\_code</span>                          | 123456789                                                                                                      | Identifies parent account code.                                                                                                                        | varchar(50)          |
| <span id="primary_payment_method">primary\_payment\_method</span>                    | TRUE/FALSE                                                                                                     | Identifies whether the billing info is either primary payment method or not.                                                                           | boolean              |
| <span id="billing_info_id">billing\_info\_id</span>                                  | 1234                                                                                                           | Unique identifier for billing info.                                                                                                                    | string               |
| <span id="dunning_campaign_code">dunning\_campaign\_code</span>                      | 123456                                                                                                         | Identifies dunning campaign code.                                                                                                                      | varchar(50)          |
| <span id="dunning_campaign_id">dunning\_campaign\_id</span>                          | 1234567                                                                                                        | Identifies dunning campaign id.                                                                                                                        | string               |
| <span id="preferred_locale">preferred\_locale</span>                                 | en-US                                                                                                          | Identifies account's preferred locale.                                                                                                                 | varchar(50)          |
| account\_api\_id                                                                     | e28zov4fw0v2                                                                                                   | Account API ID                                                                                                                                         | string               |
| cc\_emails                                                                           | [cc\_email1@recurly.com](mailto:cc_email1@recurly.com) ,[cc\_email2@recurly.com](mailto:cc_email2@recurly.com) | Additional email address that should receive account correspondence. These should be separated only by commas.                                         | string               |

# Version Changelog

#### Version 8 - 08/05/2025

Addition of cc\_emails.

#### Version 7 - 2/5/2025

Addition of `account_api_id`

#### Version 6 - 06/14/23

Added account’s preferred locale column\
`preferred_locale`

#### Version 5 - 07/23/21

Added Dunning campaign columns\
`dunning_campaign_code`
`dunning_campaign_id`

#### Version 4 - 12/10/20

* The `tax_location_valid` column now relates to the specific billing info in each row.
* Introduced `primary_payment_method` column displaying TRUE or FALSE based on the primary payment method status of the billing info.
* New `billing_info_id` column showcasing the ID of the particular billing info.

#### Version 3 - 9/13/18

* Added `parent_account_code` column for the Account Hierarchy feature, helping in identifying an account's parent if applicable, though it will only hold a value if the feature is active.

#### Version 2 - 9/6/18

* Introduction of columns for custom fields, placed at the end of the export.