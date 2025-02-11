---
title: Invoices — accounts receivable - export
excerpt: >-
  Unlock insights into outstanding receivables and unpaid invoices with the
  Account Receivable export section.
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

The Invoices - Accounts Receivable export helps you to pinpoint customers who have yet to settle their invoices and gives a detailed report on the aging of all unsettled receivables.

# Filters

#### **Invoice Status Filter**

- **All**: Includes all invoices that remain unpaid.
- **Pending**: Consists of invoices not yet due and only encompasses manual invoices.
- **Past Due**: Involves all invoices that have surpassed their due date without being settled.
- **Failed**: Pertains to invoices labeled as failed or not collected within the Dunning period.
- **Processing**: Concerns ACH transactions presently undergoing processing.

#### **Date Range Filters**

- **Created**: Invoices formulated within the chosen timeframe.
- **Modified**: Invoices altered in the specified period.
- **Due**: Invoices due in the specified period.

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
    "h-3": "Data type",
    "0-0": "<span id=\"invoice_id\">invoice_id</span>",
    "0-1": "336e028b12345b00b60b7845438d18b1",
    "0-2": "Unique identifier for invoices within Recurly. This ID is also used in Invoices - Summary and Adjustments exports.",
    "0-3": "varchar(32)",
    "1-0": "<span id=\"invoice_number\">invoice_number</span>",
    "1-1": "1001",
    "1-2": "Number used on the invoice through the admin console.",
    "1-3": "string",
    "2-0": "<span id=\"account_code\">account_code</span>",
    "2-1": "smith",
    "2-2": "Uniquely identifies your customers in Recurly. Defaults to the email address if no specific value is provided and cannot be modified. It is the main Recurly identifier for joining multiple exports.",
    "2-3": "varchar(50)",
    "3-0": "<span id=\"account_first_name\">account_first_name</span>",
    "3-1": "Eric",
    "3-2": "First name of the customer from the associated account.",
    "3-3": "varchar(255)",
    "4-0": "<span id=\"account_last_name\">account_last_name</span>",
    "4-1": "Schmidt",
    "4-2": "Last name of the customer from the associated account.",
    "4-3": "varchar(255)",
    "5-0": "<span id=\"account_company\">account_company</span>",
    "5-1": "Bluth Industries, Inc.",
    "5-2": "Optionally identifies the company name provided.",
    "5-3": "varchar(255)",
    "6-0": "<span id=\"account_email\">account_email</span>",
    "6-1": "[test@example.com](mailto:test@example.com)",
    "6-2": "Optional. Email address provided by the customer during signup, used for all customer communications. If absent, the site's billing contact will receive emails.",
    "6-3": "varchar(255)",
    "7-0": "<span id=\"account_phone\">account_phone</span>",
    "7-1": "123-456-7890",
    "7-2": "Optional. The phone number of the customer.",
    "7-3": "string",
    "8-0": "<span id=\"billed_date\">billed_date</span>",
    "8-1": "2016-01-01 10:17:02 UTC",
    "8-2": "Date of invoice creation.",
    "8-3": "timestamp",
    "9-0": "<span id=\"net_terms\">net_terms</span>",
    "9-1": "on-receipt",
    "9-2": "Specifies the terms of the invoice.",
    "9-3": "string",
    "10-0": "<span id=\"due_on\">due_on</span>",
    "10-1": "2016-01-01 10:17:02 UTC",
    "10-2": "Due date of the invoice.",
    "10-3": "timestamp",
    "11-0": "<span id=\"status\">status</span>",
    "11-1": "failed",
    "11-2": "Current status of the invoice, equivalent to \"invoice_state\" in the Adjustments export.",
    "11-3": "varchar(20)",
    "12-0": "<span id=\"collection_method\">collection_method</span>",
    "12-1": "automatic",
    "12-2": "Indicates the collection method for the invoice - either \"automatic\" or \"manual\".",
    "12-3": "string",
    "13-0": "<span id=\"days_overdue\">days_overdue</span>",
    "13-1": "12",
    "13-2": "The number of days the invoice is overdue; will be zero if not overdue.",
    "13-3": "numeric",
    "14-0": "<span id=\"currency\">currency</span>",
    "14-1": "USD",
    "14-2": "The 3-character ISO code representing the invoice's currency.",
    "14-3": "varchar(3)",
    "15-0": "<span id=\"po_number\">po_number</span>",
    "15-1": "1234",
    "15-2": "The Purchase Order (PO) number associated with the invoice.",
    "15-3": "varchar(50)",
    "16-0": "<span id=\"closed_date\">closed_date</span>",
    "16-1": "2016-05-18 11:17:07 UTC",
    "16-2": "The date when the invoice was closed, applicable if failed or paid.",
    "16-3": "timestamp",
    "17-0": "<span id=\"modified_at\">modified_at</span>",
    "17-1": "2016-05-18 11:17:07 UTC",
    "17-2": "The date the invoice last underwent modification, including payment status updates.",
    "17-3": "timestamp",
    "18-0": "<span id=\"invoice_subtotal\">invoice_subtotal</span>",
    "18-1": "136.78",
    "18-2": "Subtotal amount of the invoice, prior to the addition of tax, discounts, and credits to compute the total amount.",
    "18-3": "numeric",
    "19-0": "<span id=\"invoice_total\">invoice_total</span>",
    "19-1": "345.67",
    "19-2": "The total invoice amount.",
    "19-3": "numeric",
    "20-0": "<span id=\"invoice_tax_amount\">invoice_tax_amount</span>",
    "20-1": "123.45",
    "20-2": "The total tax amount levied on the invoice.",
    "20-3": "numeric",
    "21-0": "<span id=\"invoice_discount_amount\">invoice_discount_amount</span>",
    "21-1": "144.58",
    "21-2": "The total discount amount applied to the invoice.",
    "21-3": "numeric",
    "22-0": "<span id=\"category\">category</span>",
    "22-1": "31-60 days overdue",
    "22-2": "Bucketed system for aging receivables and past-due invoices. \"Current\" for non-due invoices, with past-due invoices grouped based on overdue duration.",
    "22-3": "string",
    "23-0": "<span id=\"invoice_credits\">invoice_credits</span>",
    "23-1": "144.58",
    "23-2": "The amount of credits applied to the invoice.",
    "23-3": "numeric",
    "24-0": "<span id=\"invoice_balance\">invoice_balance</span>",
    "24-1": "50.25",
    "24-2": "The invoice's outstanding balance. **This column will be null until the Recurly's Credit Invoices feature is enabled on your site.**",
    "24-3": "numeric",
    "25-0": "<span id=\"invoice_balance_modified_at\">invoice_balance_modified_at</span>",
    "25-1": "2016-05-18 11:17:07 UTC",
    "25-2": "The last change date of the invoice balance due to a transaction or credit payment. **This column will be null until the Recurly's Credit Invoices feature is enabled on your site.**",
    "25-3": "timestamp",
    "26-0": "<span id=\"business_entity_code\">business_entity_code</span>",
    "26-1": "123456789",
    "26-2": "Identifier for business entity code.",
    "26-3": "string",
    "27-0": "invoice_api_id",
    "27-1": "e28zov4fw0v2",
    "27-2": "Invoice API ID",
    "27-3": "string"
  },
  "cols": 4,
  "rows": 28,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version Changelog

### Version 3 - 2/5/25

Addition of `invoice_api_id` column.

### Version 2 - 3/15/2023

Addition of `business_entity_code` column.

The Accounts Receivable export identifies customers who have not paid their invoices, as well as the aging of all outstanding receivables.