---
title: Invoices — unused numbers - export
excerpt: >-
  Discover your Recurly invoice data effortlessly with the Invoices -  Unused
  numbers feature.
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

The unused invoice number export showcases the fundamental details of all the invoice numbers that have not been utilized in successfully generated invoices. Situations such as failed sign-ups could result in an unused invoice number. 

This log aids significantly in audit procedures, supplementing the numbers provided in the Invoices - Summary export to furnish a detailed account for every number in your sequence.

# Filters

### Date Range Filters

List all unused invoice numbers that could have been created within the selected timeframe.

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
    "0-0": "<span id=\"invoice_number\">invoice_number</span>",
    "0-1": "1291",
    "0-2": "External invoice identifier.",
    "0-3": "string",
    "1-0": "<span id=\"invoice_type\">invoice_type</span>",
    "1-1": "purchase, refund, renewal, immediate_change, termination, credit, gift_card, write_off, external_refund, carryforward_credit, carryforward_gift_credit, usage_correction, import",
    "1-2": "This refers to the origin of the invoice. The primary invoice possesses a 'purchase' type. Negative invoices generated due to refunds or voids to offset the initial one have a 'refund' type. Other invoice types become accessible when the Credit Invoices feature is activated. Detailed descriptions can be found in the [invoice origins section](/docs/invoices#section-origins).",
    "1-3": "string",
    "2-0": "<span id=\"invoice_doc_type\">invoice_doc_type</span>",
    "2-1": "legacy, charge, credit",
    "2-2": "This column indicates the document type of the invoice. Before activating the Credit Invoices feature, all invoices bear the 'legacy' type. Post activation, the invoices are categorized as either 'charge' or 'credit'.",
    "2-3": "string",
    "3-0": "<span id=\"invoice_date\">invoice_date</span>",
    "3-1": "2019-07-19 12:01:33 PST",
    "3-2": "The date and time the invoice creation was attempted. The inception date for this export is July 1, 2019.",
    "3-3": "timestamp",
    "4-0": "invoice_api_id",
    "4-1": "e28zov4fw0v2",
    "4-2": "Invoice API ID",
    "4-3": "string"
  },
  "cols": 4,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version changelog

### Version 2 - 2/5/2025

- Addition of `invoice_api_id`