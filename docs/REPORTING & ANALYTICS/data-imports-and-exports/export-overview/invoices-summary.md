---
title: Invoices — summary - export
excerpt: >-
  Discover your Recurly invoice data effortlessly with the Invoices - External
  export feature.
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

The Invoices Summary export provides a detailed report for every invoice. This data gives you a deeper understanding of every invoice to help you manage your invoices better.

# Filters

#### Invoice Status Filter

This filter allows you to select invoices based on their current statuses which include:  
-**All**: All invoices including credit and charge.  
-**Charge**: Only charge invoices.  
-**Credit**: Only credit invoices.

#### Date Range Filters

##### Created

Involves invoices created within a chosen time span.

##### Modified

Entails invoices modified in a selected time range.

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
    "0-0": "<span id=\"id\">id</span>",
    "0-1": "b964b5439c2548a489b3a136e75aee9f",
    "0-2": "Unique internal identifier for the invoice. This is also called the 'invoice_id' or 'uuid' for the invoice in the API.",
    "0-3": "varchar(32)",
    "1-0": "<span id=\"invoice_number\">invoice_number</span>",
    "1-1": "1291",
    "1-2": "External invoice identifier.",
    "1-3": "string",
    "2-0": "<span id=\"billed_date\">billed_date</span>",
    "2-1": "2012-02-19 12:01:33 PST",
    "2-2": "Creation date of the invoice. Equivalent to date in the deprecated Invoices export. Used for Created date range filter.",
    "2-3": "timestamp",
    "3-0": "<span id=\"due_on\">due_on</span>",
    "3-1": "2012-02-19 12:01:33 PST",
    "3-2": "Date invoice is due. This is the date the net terms is reached.",
    "3-3": "timestamp",
    "4-0": "<span id=\"closed_at\">closed_at</span>",
    "4-1": "2012-02-19 12:01:33 PST",
    "4-2": "Date invoice was closed (paid) or failed.",
    "4-3": "timestamp",
    "5-0": "<span id=\"status\">status</span>",
    "5-1": "pending, processing, past_due, paid, failed, voided",
    "5-2": "Current status of the invoice. Equivalent to invoice_state in the Adjustments export. See filter notes above for details on what each status means.",
    "5-3": "varchar(20)",
    "6-0": "<span id=\"net_terms\">net_terms</span>",
    "6-1": "on-receipt, net-10, net-30, net-60",
    "6-2": "Identifies the net_terms agreement associated with the invoice. All automatic collection invoices are due 'on-receipt'. Manual collection invoices can have terms of net-10, net-30, net-60, or a custom net day amount.",
    "6-3": "string",
    "7-0": "<span id=\"collection_method\">collection_method</span>",
    "7-1": "automatic or manual",
    "7-2": "Identifies whether the invoice fees are collected via manual or automatic invoicing. An automatic invoice means a corresponding transaction is run using the account's billing information at the same time the invoice is created. Manual invoices are created without a corresponding transaction.",
    "7-3": "string",
    "8-0": "<span id=\"account_code\">account_code</span>",
    "8-1": "123122E",
    "8-2": "Account code being charged for this invoice.",
    "8-3": "varchar(50)",
    "9-0": "<span id=\"account_name\">account_name</span>",
    "9-1": "JJ Smith",
    "9-2": "First and last name from account associated with that invoice.",
    "9-3": "string",
    "10-0": "<span id=\"account_company\">account_company</span>",
    "10-1": "Company, Inc.",
    "10-2": "Company name from account. This field is from the Account Info and is displayed on the invoice if it exists.",
    "10-3": "varchar(225)",
    "11-0": "<span id=\"account_line1\">account_line1</span>",
    "11-1": "1 Main Street",
    "11-2": "Address line 1 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "11-3": "string",
    "12-0": "<span id=\"account_line2\">account_line2</span>",
    "12-1": "Suite 100",
    "12-2": "Address line 2 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "12-3": "string",
    "13-0": "<span id=\"account_city\">account_city</span>",
    "13-1": "San Francisco",
    "13-2": "City of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "13-3": "string",
    "14-0": "<span id=\"account_state\">account_state</span>",
    "14-1": "CA",
    "14-2": "State or province of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "14-3": "string",
    "15-0": "<span id=\"account_zip\">account_zip</span>",
    "15-1": "94107",
    "15-2": "ZIP/postal code of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "15-3": "string",
    "16-0": "<span id=\"account_country\">account_country</span>",
    "16-1": "US",
    "16-2": "The 2 letter country code for the country of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "16-3": "string",
    "17-0": "<span id=\"vat_number\">vat_number</span>",
    "17-1": "IE124211145",
    "17-2": "VAT registration number for the customer on the invoice. This will come from the VAT Number field in the Billing Info or the Account Info depending on your tax settings and the invoice collection method.",
    "17-3": "varchar(20)",
    "18-0": "<span id=\"po_number\">po_number</span>",
    "18-1": "AE12523",
    "18-2": "For manual invoicing, this identifies the Purchase Order number associated with the invoice. This value must be entered by the merchant at the time the invoice is created or it will not exist.",
    "18-3": "varchar(50)",
    "19-0": "<span id=\"coupon_code\">coupon_code</span>",
    "19-1": "50off",
    "19-2": "The code for the coupon associated with any discounts on the invoice. This value will only exist if a coupon was applied to the invoice.",
    "19-3": "string",
    "20-0": "<span id=\"currency\">currency</span>",
    "20-1": "USD",
    "20-2": "The currency of the amounts on the invoice. We do not allow mixed currency invoices.",
    "20-3": "varchar(3)",
    "21-0": "<span id=\"invoice_total\">invoice_total</span>",
    "21-1": "100",
    "21-2": "The final total on the invoice. The summation of invoice charges, discounts, credits, and tax. Equivalent to the total in the deprecated Invoices export.",
    "21-3": "numeric",
    "22-0": "<span id=\"invoice_subtotal\">invoice_subtotal</span>",
    "22-1": "50",
    "22-2": "The Subtotal on the invoice. The summation of charges, discounts, and credits, before tax.",
    "22-3": "numeric",
    "23-0": "<span id=\"tax_amount\">tax_amount</span>",
    "23-1": "15.00",
    "23-2": "The total tax amount on the invoice.",
    "23-3": "numeric",
    "24-0": "<span id=\"tax_type\">tax_type</span>",
    "24-1": "usst, vat, ca, au, nz",
    "24-2": "Provides the tax type as \"vat\" for EU VAT, \"usst\" for U.S. Sales Tax, or the 2 letter country code for country level tax types like Canada, Australia, New Zealand, Israel, and all non-EU European countries.",
    "24-3": "varchar(6)",
    "25-0": "<span id=\"tax_region\">tax_region</span>",
    "25-1": "NY, FR, GST, VAT",
    "25-2": "Provides the tax region applied on an invoice. For U.S. Sales Tax, this will be the 2 letter state code. For EU VAT this will be the 2 letter country code. For all country level tax types, this will display the regional tax, like VAT, GST, or PST.",
    "25-3": "varchar(15)",
    "26-0": "<span id=\"tax_rate\">tax_rate</span>",
    "26-1": "0.1",
    "26-2": "Tax rate applied on the invoice.",
    "26-3": "numeric",
    "27-0": "<span id=\"credit_to_account\">credit_to_account</span>",
    "27-1": "0",
    "27-2": "Amount of credit applied back to the account. This amount is a charge with adjustment_origin of 'carryforward' on the invoice. This charge is what zeros out the invoice and should be filtered out of your reports. Credit to Account also maps to the uninvoiced credit that is created for the same amount and left on the account for payment of a future invoice. That credit will have an adjustment_origin that matches the original charge's origin.",
    "27-3": "numeric",
    "28-0": "<span id=\"recovery_reason\">recovery_reason</span>",
    "28-1": "exp_date, retry, account_updater, prior_recovery, customer_updates",
    "28-2": "If the initial transaction failed but a subsequent one succeeded, this field indicates why. See the details of what each reason means in our blog \"[Revenue Recovery: What Has Recurly Recovered for Me Lately?](https://blog.recurly.com/what-has-recurly-recovered-revenue)\".",
    "28-3": "varchar",
    "29-0": "<span id=\"invoice_country\">invoice_country</span>",
    "29-1": "FR",
    "29-2": "This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the EU or NZ country code of the customer's address on the invoice. The country refers to the evidence_matched.",
    "29-3": "varchar(2)",
    "30-0": "<span id=\"evidence_matched\">evidence_matched</span>",
    "30-1": "Account Info Country, Billing Info Country, IP Address Country, Credit Card BIN Country",
    "30-2": "This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the two pieces of evidence that matched when the invoice was created. The corresponding country is the invoice_country.",
    "30-3": "string",
    "31-0": "<span id=\"modified_at\">modified_at</span>",
    "31-1": "2014-12-26 08:23:34 PST",
    "31-2": "The date the invoice was last modified. An invoice is only modified if the status changes. Used for Modified date range filter.",
    "31-3": "timestamp",
    "32-0": "<span id=\"invoice_type\">invoice_type</span>",
    "32-1": "purchase, refund, renewal, immediate_change, termination, credit, gift_card, write_off, external_refund, carryforward_credit, carryforward_gift_credit, usage_correction, import",
    "32-2": "This is the invoice origin. The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'. All other invoice types are unlocked only when the Credit Invoices feature is enabled. See the full table of [invoice origins](/docs/invoices#section-origins) for descriptions.",
    "32-3": "string",
    "33-0": "<span id=\"original_invoice_number\">original_invoice_number</span>",
    "33-1": "1002",
    "33-2": "If the row is a refund invoice, this value will exist and show the invoice number of the purchase invoice the refund was created from.",
    "33-3": "string",
    "34-0": "<span id=\"ship_address_name\">ship_address_name</span>",
    "34-1": "Julie Smith",
    "34-2": "The first and last name associated with the shipping address",
    "34-3": "string",
    "35-0": "<span id=\"ship_address_line1\">ship_address_line1</span>",
    "35-1": "ship_address_line1",
    "35-2": "ship_address_line1",
    "35-3": "string",
    "36-0": "<span id=\"ship_address_line2\">ship_address_line2</span>",
    "36-1": "Apt 1",
    "36-2": "The second line of the street address for the shipping address",
    "36-3": "string",
    "37-0": "<span id=\"ship_address_city\">ship_address_city</span>",
    "37-1": "West Bloomfield",
    "37-2": "The city for the shipping address",
    "37-3": "string",
    "38-0": "<span id=\"ship_address_state\">ship_address_state</span>",
    "38-1": "MI",
    "38-2": "The state for the shipping address",
    "38-3": "string",
    "39-0": "<span id=\"ship_address_zip\">ship_address_zip</span>",
    "39-1": "48322",
    "39-2": "The zip or postal code for the shipping address",
    "39-3": "string",
    "40-0": "<span id=\"ship_address_country\">ship_address_country</span>",
    "40-1": "US",
    "40-2": "The country for the shipping address",
    "40-3": "string",
    "41-0": "<span id=\"ship_address_phone\">ship_address_phone</span>",
    "41-1": "248-555-1212",
    "41-2": "The phone number associated with the shipping address",
    "41-3": "string",
    "42-0": "<span id=\"invoice_doc_type\">invoice_doc_type</span>",
    "42-1": "legacy, charge, credit",
    "42-2": "This is the invoice document type. All invoices created before the Credit Invoices feature is enabled will have a type of ‘legacy’. Once Credit Invoices is enabled, new invoices will be either ‘charge’ or ‘credit’.",
    "42-3": "string",
    "43-0": "<span id=\"invoice_balance\">invoice_balance</span>",
    "43-1": "50.25",
    "43-2": "The balance of the invoice. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "43-3": "numeric",
    "44-0": "<span id=\"invoice_balance_modified_at\">invoice_balance_modified_at</span>",
    "44-1": "2016-01-01 10:17:02 UTC",
    "44-2": "The datetime the invoice_balance last changed due to a transaction or credit payment. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "44-3": "timestamp",
    "45-0": "<span id=\"invoice_discount\">invoice_discount</span>",
    "45-1": "50.25",
    "45-2": "Total of all discounts on the invoice.",
    "45-3": "numeric",
    "46-0": "<span id=\"invoice_subtotal_before_discounts\">invoice_subtotal_before_discounts</span>",
    "46-1": "50.25",
    "46-2": "The total of all adjustments on the invoice, before discounts and taxes.",
    "46-3": "numeric",
    "47-0": "<span id=\"invoice_refundable_amount\">invoice_refundable_amount</span>",
    "47-1": "50.25",
    "47-2": "The refundable amount of the invoice, which is the invoice total, including discounts and tax, minus all credit invoices issued against it. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "47-3": "numeric",
    "48-0": "<span id=\"shipping_address_count\">shipping_address_count</span>",
    "48-1": "1",
    "48-2": "Number of shipping addresses if multiple shipping addresses per invoice is enabled.",
    "48-3": "numeric",
    "49-0": "<span id=\"dunning_campaign_code\">dunning_campaign_code</span>",
    "49-1": "12345678",
    "49-2": "Dunning Campaign Code.",
    "49-3": "varchar(50)",
    "50-0": "<span id=\"dunning_campaign_id\">dunning_campaign_id</span>",
    "50-1": "23456789",
    "50-2": "Dunning Campaign ID.",
    "50-3": "string",
    "51-0": "<span id=\"dunning_campaign_version\">dunning_campaign_version</span>",
    "51-1": "1234",
    "51-2": "Dunning Campaign Version.",
    "51-3": "string",
    "52-0": "<span id=\"used_tax_service\">used_tax_service</span>",
    "52-1": "TRUE",
    "52-2": "TRUE/FALSE boolean column indicating whether the invoice has used Recurly tax services.",
    "52-3": "boolean",
    "53-0": "<span id=\"business_entity_code\">business_entity_code</span>",
    "53-1": "123456789",
    "53-2": "Business Entity Code.",
    "53-3": "string",
    "54-0": "<span id=\"parent_account_code\">parent_account_code</span>",
    "54-1": "123122E",
    "54-2": "Parent account code being charged for this invoice.",
    "54-3": "varchar(50)",
    "55-0": "invoice_api_id",
    "55-1": "e28zov4fw0v2",
    "55-2": "Invoice API ID",
    "55-3": "string"
  },
  "cols": 4,
  "rows": 56,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 7 - 2/5/25

- Addition of `invoice_api_id`

### Version 5 - 12/12/23

- Addition of parent_account_code column.

### Version 4 - 5/15/23

- Addition of business_entity_code column.

### Version 3 - 3/21/23

- Addition of used_tax_service column.

### Version 2 - 6/23/21

- Addition of dunning_campaign_code, dunning_campain_id and dunning_campaign version columns.