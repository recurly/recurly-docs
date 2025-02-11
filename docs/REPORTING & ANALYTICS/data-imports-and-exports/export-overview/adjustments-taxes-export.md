---
title: Adjustments — taxes - export
excerpt: >-
  Maximize your reporting efficiency with the Adjustments - Taxes export
  section.
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

The Adjustments - Taxes export is designed for reporting on taxes calculated through Vertex. It is pertinent to note that for reporting on taxes calculated through Avalara, you should utilize the Adjustments export. This CSV file contains a row for each tax jurisdiction that is returned for a line item. Even line items without taxes will be included but as a single row in the export.

# Filters

### Time Range Filter

This export showcases adjustments alongside their respective taxes created during a predefined time range. It is important to note that the creation date of an adjustment coincides with the invoice issuance date unless the adjustment was initiated on the account uninvoiced, awaiting processing in the upcoming billing event.

**Note**: Adjustments are immutable; hence, a 'modified' time range option is non-existent.

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
    "0-0": "<span id=\"adjustment_uuid\">adjustment_uuid</span>",
    "0-1": "34a302b4ed87c4eebeee4942b98b932f",
    "0-2": "The unique id for the line item.",
    "0-3": "varchar(32)",
    "1-0": "<span id=\"account_code\">account_code</span>",
    "1-1": "1234568",
    "1-2": "The unique code for the account.",
    "1-3": "varchar(50)",
    "2-0": "<span id=\"subscription_id\">subscription_id</span>",
    "2-1": "2f1f711a62b424391a690e4895a3f2a5",
    "2-2": "The unique id for the subscription associated with the line item.",
    "2-3": "varchar(32)",
    "3-0": "<span id=\"invoice_id\">invoice_id</span>",
    "3-1": "34a27fd20e668a389c064e43c183bcf1",
    "3-2": "The unique id for the invoice.",
    "3-3": "varchar(32)",
    "4-0": "<span id=\"invoice_number\">invoice_number</span>",
    "4-1": "1001",
    "4-2": "The invoice number displayed on the invoice.",
    "4-3": "string",
    "5-0": "<span id=\"invoice_billed_date\">invoice_billed_date</span>",
    "5-1": "2016-08-03 16:26:26 UTC",
    "5-2": "The date the invoice was posted.",
    "5-3": "timestamp",
    "6-0": "<span id=\"invoice_state\">invoice_state</span>",
    "6-1": "pending, past_due, paid, failed, open, closed, voided, processing",
    "6-2": "The current state of the invoice.",
    "6-3": "varchar(32)",
    "7-0": "<span id=\"refund_tax_date\">refund_tax_date</span>",
    "7-1": "2016-08-03 16:26:26 UTC",
    "7-2": "Date of the original purchase invoice if the invoice is a refund or subscription change.",
    "7-3": "timestamp",
    "8-0": "<span id=\"refund_geo_code\">refund_geo_code</span>",
    "8-1": "123456789",
    "8-2": "Not applicable for Vertex O Series or Vertex Cloud integrations.",
    "8-3": "string",
    "9-0": "<span id=\"adjustment_description\">adjustment_description</span>",
    "9-1": "Gold Plan",
    "9-2": "The line item description on the invoice.",
    "9-3": "varchar(255)",
    "10-0": "<span id=\"adjustment_product_code\">adjustment_product_code</span>",
    "10-1": "gold_plan",
    "10-2": "The plan code, add-on code, or one-off charge product code for the line item’s product.",
    "10-3": "varchar(50)",
    "11-0": "<span id=\"adjustment_currency\">adjustment_currency</span>",
    "11-1": "USD",
    "11-2": "The currency of the line item.",
    "11-3": "varchar(3)",
    "12-0": "<span id=\"adjustment_amount\">adjustment_amount</span>",
    "12-1": "74.97",
    "12-2": "Pre-discount, pre-tax amount of the line item. If negative, it reflects a credit from a downgrade or refund.",
    "12-3": "numeric",
    "13-0": "<span id=\"adjustment_discount\">adjustment_discount</span>",
    "13-1": "49.99",
    "13-2": "The discount amount on the line item.",
    "13-3": "numeric",
    "14-0": "<span id=\"adjustment_coupon_code\">adjustment_coupon_code</span>",
    "14-1": "5dollars_off",
    "14-2": "The coupon code applied to the line item for the discount.",
    "14-3": "string",
    "15-0": "<span id=\"tax_type\">tax_type</span>",
    "15-1": "vat",
    "15-2": "The tax type represented in the row for the line item.",
    "15-3": "varchar(6)",
    "16-0": "<span id=\"jurisdiction\">jurisdiction</span>",
    "16-1": "country, province, state, city, county, federal, district",
    "16-2": "The tax jurisdiction represented in the row for the line item.",
    "16-3": "string",
    "17-0": "<span id=\"jurisdiction_amount\">jurisdiction_amount</span>",
    "17-1": "1.31",
    "17-2": "The tax amount for the jurisdiction.",
    "17-3": "numeric",
    "18-0": "<span id=\"jurisdiction_rate\">jurisdiction_rate</span>",
    "18-1": "0.01744",
    "18-2": "The tax rate for the jurisdiction.",
    "18-3": "numeric",
    "19-0": "<span id=\"jurisdiction_description\">jurisdiction_description</span>",
    "19-1": "Florida Communications Tax",
    "19-2": "The name of the imposition in the jurisdiction.",
    "19-3": "string",
    "20-0": "<span id=\"jurisdiction_name\">jurisdiction_name</span>",
    "20-1": "france, united kingdom",
    "20-2": "The identifying name for the jurisdiction.",
    "20-3": "string",
    "21-0": "<span id=\"geo_code\">geo_code</span>",
    "21-1": "123456789",
    "21-2": "Not applicable for Vertex O Series or Vertex Cloud integrations.",
    "21-3": "string",
    "22-0": "<span id=\"adjustment_tax_code\">adjustment_tax_code</span>",
    "22-1": "digital_product",
    "22-2": "The tax code of the product represented by the line item. Available from version 2.",
    "22-3": "string",
    "23-0": "<span id=\"classification\">classification</span>",
    "23-1": "product_1",
    "23-2": "-",
    "23-3": "string",
    "24-0": "<span id=\"item_code\">item_code</span>",
    "24-1": "item123",
    "24-2": "The user-specified unique ID of the sold item on this adjustment. More details on [this page](https://docs.recurly.com/docs/catalog).",
    "24-3": "varchar(50)",
    "25-0": "<span id=\"item_id\">item_id</span>",
    "25-1": "1234567890",
    "25-2": "The system-generated unique ID of the sold item on this adjustment.",
    "25-3": "string",
    "26-0": "<span id=\"external_sku\">external_sku</span>",
    "26-1": "abc123",
    "26-2": "The user-specified SKU of the sold item on this adjustment.",
    "26-3": "varchar(50)",
    "27-0": "<span id=\"tax_region\">tax_region</span>",
    "27-1": "US",
    "27-2": "Indicates the tax region.",
    "27-3": "string",
    "28-0": "<span id=\"tax_inclusive\">tax_inclusive</span>",
    "28-1": "true",
    "28-2": "Indicates whether the price includes tax.",
    "28-3": "boolean",
    "29-0": "<span id=\"business_entity_code\">business_entity_code</span>",
    "29-1": "123456789",
    "29-2": "Indicates business entity code.",
    "29-3": "string",
    "30-0": "adjustment_api_id",
    "30-1": "e28zov4fw0v2",
    "30-2": "Adjustment API ID",
    "30-3": "string"
  },
  "cols": 4,
  "rows": 31,
  "align": [
    null,
    null,
    null,
    "left"
  ]
}
[/block]


# Version changelog

### Version 8 - Feb 5, 2025

- Addition of `adjustment_api_id`.

### Version 7 - May 15, 2023

- **Update to export made 8/20/2024:** Merchants integrated directly with Vertex will now see the corresponding geocode values passed from Vertex populated in the "geo_code" field within this export.  The "geocode" identifier passed serves as a specific way to pinpoint the location/address that was used for tax calculation on the invoice. This field provides accurate reporting for tax to state and local tax authorities. This field is also queryable via V2/V3 API.
- Added business_entity_code column.

### Version 6 - March 3, 2022

- Added tax_inclusive column.

### Version 5 - August 11, 2021

- Added tax_region column.

### Version 4 - February 13, 2020

- Added a column for external_sku pertaining to Item Charges.

### Version 3 - November 21, 2019

- Addeditem_code and item_id columns for Item Charges.

### Version 2 - September 20, 2018

- Addedadjustment_tax_code column.
- Added classification column. (Conditional on Vertex tax integration)