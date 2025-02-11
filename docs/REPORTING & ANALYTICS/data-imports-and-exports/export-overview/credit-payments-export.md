---
title: Credit payments - export
excerpt: >-
  Dive into the world of credit payments with the Credit Payments Export,
  tracking every credit payment action and its details.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Definition

The Credit Payments Export section provides insights into credit payments, encompassing the use of outstanding credit balances to pay invoices. This export not only covers standard credit payments but also records write-offs, credit balance removals, and credit payments subsequently refunded as cash transactions. It becomes visible and populated if you have enabled the [Credit Invoices](https://docs.recurly.com/docs/credit-invoices-release) feature on your Recurly site.

# Filters

### **Action Filter**

The Credit Payments export can be pre-filtered in the Admin Console based on the **Action** taken. The available credit payment actions include:

| **Action**       | **Description**                                                                                                                                                                                                                                                                                                                                      |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| All of the below | All descriptions below.                                                                                                                                                                                                                                                                                                                              |
| Gift Card        | Similar to a normal credit payment, but the credit invoice's amount originates from a "gift_card." Useful for tracking invoices paid with gift card credit.                                                                                                                                                                                          |
| Payment          | A normal credit payment that utilizes all or a portion of a credit invoice balance to pay a charge invoice.                                                                                                                                                                                                                                          |
| Reduction        | Removes a credit balance from a credit invoice. Use this action to identify all credits "deleted" from an account and check the corresponding original invoice status to see if it resulted in a [voided credit invoice or a closed credit invoice](https://docs.recurly.com/docs/credit-invoices-release#section-void-a-credit-invoice-or-balance). |
| Refund           | Applied when a [credit payment is refunded as a refund transaction](https://docs.recurly.com/docs/credit-invoices-release#section-refund-credit-payment-to-original-payment-method). This event generates a new credit payment that records the original credit payment's ID and the new refund transaction's ID.                                    |
| Write-Off        | Used to transfer the balance of a write-off invoice to a failed invoice, reducing the latter's balance to zero.                                                                                                                                                                                                                                      |

### Date Range Filters

#### **Created**

Lists all credit payments created within the selected timeframe.

#### **Modified**

Lists all credit payments modified during the selected timeframe. A credit payment's modified_at value is set upon creation and only updates when the credit payment is voided (voided_at value set) due to the invoice it was applied to being failed.

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
    "h-3": "Data type (size)",
    "0-0": "<span id=\"id\">id</span>",
    "0-1": "41872c1bf4bcfcd5658d86401194f63b",
    "0-2": "The unique id of the credit payment.",
    "0-3": "varchar(32)",
    "1-0": "<span id=\"created_at\">created_at</span>",
    "1-1": "2017-12-02 17:58:09 UTC",
    "1-2": "The date and time the credit payment was created.",
    "1-3": "timestamp",
    "2-0": "<span id=\"modified_at\">modified_at</span>",
    "2-1": "2017-12-02 17:58:09 UTC",
    "2-2": "The date and time the credit payment was modified, which would be when it was created or voided.",
    "2-3": "timestamp",
    "3-0": "<span id=\"voided_at\">voided_at</span>",
    "3-1": "2017-12-02 17:58:09 UTC",
    "3-2": "The date and time the credit payment was voided due to the applied invoice being failed.",
    "3-3": "timestamp",
    "4-0": "<span id=\"action\">action</span>",
    "4-1": "payment, gift_card, write_off, reduction, refund",
    "4-2": "The action that resulted in the credit payment being created. See action filter table above for details.",
    "4-3": "string",
    "5-0": "<span id=\"currency\">currency</span>",
    "5-1": "USD",
    "5-2": "The currency of the credit payment amount.",
    "5-3": "varchar(3)",
    "6-0": "<span id=\"amount\">amount</span>",
    "6-1": "54.38",
    "6-2": "The amount of the credit payment, which will always be positive.",
    "6-3": "numeric",
    "7-0": "<span id=\"original_invoice_billed_date\">original_invoice_billed_date</span>",
    "7-1": "2017-12-02 17:58:09 UTC",
    "7-2": "The date the credit invoice the credit payment came from was issued.",
    "7-3": "timestamp",
    "8-0": "<span id=\"original_invoice_status\">original_invoice_status</span>",
    "8-1": "open, processing, closed, voided",
    "8-2": "The current status of the credit invoice the credit payment came from. This is helpful to identify voided vs. closed credit invoices for reduction action credit payments.",
    "8-3": "varchar(20)",
    "9-0": "<span id=\"original_invoice_number\">original_invoice_number</span>",
    "9-1": "-",
    "9-2": "-",
    "9-3": "string",
    "10-0": "<span id=\"applied_to_invoice_number\">applied_to_invoice_number</span>",
    "10-1": "-",
    "10-2": "-",
    "10-3": "string",
    "11-0": "<span id=\"original_credit_payment_it\">original_credit_payment_id</span>",
    "11-1": "-",
    "11-2": "-",
    "11-3": "varchar(32)",
    "12-0": "refund_transaction_id",
    "12-1": "-",
    "12-2": "-",
    "12-3": "varchar(32)",
    "13-0": "credit_payment_api_id",
    "13-1": "e28zov4fw0v2",
    "13-2": "Credit Payment API ID",
    "13-3": "string"
  },
  "cols": 4,
  "rows": 14,
  "align": [
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


# Version Changelog

### Version 2 - 2/5/2025

- Addition of `credit_payment_api_id`.