---
title: Transactions - export
excerpt: >-
  Maximize your understanding of every payment interaction with the
  comprehensive Transactions export.
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

The Transactions export section provides a detailed report of all interactions communicated to and received from the payment gateway while processing a transaction. This data gives you a deeper understanding of every payment interaction to help you manage your financial transactions better.

# Filters

Recurly transactions can be categorized into three types and four statuses, providing detailed insights into payment flows.  

#### Transaction types

- **Authorization**: A $1 or $0 transaction created to validate payment information usability after billing updates.  
- **Purchase**: A positive charge sent to the processor for fund collection and transfer to your merchant bank.  
- **Refund**: A negative charge sent to the processor to reimburse and transfer funds back to the customer’s bank.  

#### Transaction Statuses

- **Success**: The transaction was accepted by the gateway for processing.  
- **Declined**: The transaction was rejected by the gateway and will not be processed.  
- **Void**: Processing was stopped before settlement (e.g., when issuing full refunds before a purchase is fully settled).  
- **Processing**: The payment is in progress with the gateway, commonly seen with direct debit transactions.

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
    "0-0": "<span id=\"account_code\">account_code</span>",
    "0-1": "123sd341",
    "0-2": "The specific account code charged during the transaction.",
    "1-0": "<span id=\"name\">name</span>",
    "1-1": "JJ Smith",
    "1-2": "Customer name as stated in their billing data.",
    "2-0": "<span id=\"transaction_id\">transaction_id</span>",
    "2-1": "6c17ba39e8734ebaa5bf98fff6d91bb9",
    "2-2": "Unique identifier for the transaction within Recurly.",
    "3-0": "<span id=\"type\">type</span>",
    "3-1": "authorization, purchase, refund",
    "3-2": "Specifies the type of transaction reported to the gateway.",
    "4-0": "<span id=\"amount\">amount</span>",
    "4-1": "9.95",
    "4-2": "The total amount of the transaction sent to the payment gateway.",
    "5-0": "<span id=\"tax_amount\">tax_amount</span>",
    "5-1": "15.00",
    "5-2": "The tax charges associated with the transaction.",
    "6-0": "<span id=\"currency\">currency</span>",
    "6-1": "USD",
    "6-2": "The currency reported to the payment gateway for transaction processing.",
    "7-0": "<span id=\"date\">date</span>",
    "7-1": "2012-01-19 11:16:41 PST",
    "7-2": "The date and time the transaction took place. Used for \"created\" date range filter.",
    "8-0": "<span id=\"status\">status</span>",
    "8-1": "declined, void, success, processing",
    "8-2": "The response received from the payment gateway concerning the transaction.",
    "9-0": "<span id=\"message\">message</span>",
    "9-1": "This transaction has been approved",
    "9-2": "Message received from the payment gateway regarding the transaction.",
    "10-0": "<span id=\"test\">test</span>",
    "10-1": "TRUE, FALSE",
    "10-2": "Indicates if the transaction was carried out on a production gateway.",
    "11-0": "<span id=\"cc_type\">cc_type</span>",
    "11-1": "visa, master, discover, amex, jcb, diners",
    "11-2": "The type of credit card utilized for the transaction.",
    "12-0": "<span id=\"cvv_result\">cvv_result</span>",
    "12-1": "M, N",
    "12-2": "The result from checking the CVV/CVC value on the transaction when it was processed.",
    "13-0": "<span id=\"avs_result\">avs_result</span>",
    "13-1": "N, P, D",
    "13-2": "The overall AVS result from checking the transaction when it was processed.",
    "14-0": "<span id=\"avs_result_postal\">avs_result_postal</span>",
    "14-1": "N, Y",
    "14-2": "The result from verifying the zip code on the transaction when it was processed.",
    "15-0": "<span id=\"avs_result_street\">avs_result_street</span>",
    "15-1": "N, Y",
    "15-2": "The result from verifying the address 1 value on the transaction when it was processed.",
    "16-0": "<span id=\"reference\">reference</span>",
    "16-1": "4119385445",
    "16-2": "The identifier for the transaction from the payment gateway.",
    "17-0": "<span id=\"approval_code\">approval_code</span>",
    "17-1": "varies by gateway",
    "17-2": "The approval code for the transaction from the payment gateway.",
    "18-0": "<span id=\"description\">description</span>",
    "18-1": "varies by gateway",
    "18-2": "The description sent to the payment gateway for the transaction.",
    "19-0": "<span id=\"state\">state</span>",
    "19-1": "CA",
    "19-2": "The state value from the customer's billing information on the account.",
    "20-0": "<span id=\"country\">country</span>",
    "20-1": "US",
    "20-2": "The country value from the customer's billing information on the account.",
    "21-0": "<span id=\"ip_address_country\">ip_address_country</span>",
    "21-1": "US",
    "21-2": "The country associated with the IP address of the customer's location when the transaction was processed.",
    "22-0": "<span id=\"original_transaction_id\">original_transaction_id</span>",
    "22-1": "6b9fc18e2497498b9e3700cd55e2ea84",
    "22-2": "For refunds, this field identifies the payment being refunded.",
    "23-0": "<span id=\"invoice_id\">invoice_id</span>",
    "23-1": "4bdb2171cebe4ecfb0cb129bd1a65746",
    "23-2": "References the invoice that generated this transaction.",
    "24-0": "<span id=\"subscription_id\">subscription_id</span>",
    "24-1": "3252sdasdbe4ecfb0cb129bd1a65746",
    "24-2": "References the subscription or list of subscriptions that instigated this transaction.",
    "25-0": "<span id=\"po_number\">po_number</span>",
    "25-1": "AE12523",
    "25-2": "The purchase order number for the invoice.",
    "26-0": "<span id=\"collection_method\">collection_method</span>",
    "26-1": "automatic, manual",
    "26-2": "The type of collection method used for the invoice.",
    "27-0": "<span id=\"transaction_gateway_type\">transaction_gateway_type</span>",
    "27-1": "test, wirecard, authorize, etc",
    "27-2": "The payment gateway utilized to process the transaction.",
    "28-0": "<span id=\"modified_at\">modified_at</span>",
    "28-1": "2014-01-01 10:00:00 PST",
    "28-2": "The date/time the transaction was last updated. Used for the \"modified\" date range filter.",
    "29-0": "<span id=\"origin\">origin</span>",
    "29-1": "recurring, API, hpp",
    "29-2": "Identifies what initiated the transaction.",
    "30-0": "<span id=\"gateway_error_codes\">gateway_error_codes</span>",
    "30-1": "500",
    "30-2": "Lists the gateway error code for declined transactions, if applicable.",
    "31-0": "<span id=\"payment_method\">payment_method</span>",
    "31-1": "PayPal, Amazon Payment, Credit Card, etc",
    "31-2": "Specifies the method used for payment.",
    "32-0": "<span id=\"collected_at\">collected_at</span>",
    "32-1": "2014-01-01 10:00:00 PST",
    "32-2": "For manually recorded payments, this reflects the specified date when recording the transaction.",
    "33-0": "<span id=\"fraud_decision\">fraud_decision</span>",
    "33-1": "DECLINE, REVIEW, APPROVE",
    "33-2": "Contains the decision returned by the Kount risk check service for this transaction.  This data mirrors the fraud info api object.",
    "34-0": "<span id=\"fraud_score\">fraud_score</span>",
    "34-1": "36 (between 1 and 99)",
    "34-2": "The risk score assigned by Kount's risk check service for this transaction. This data mirrors the fraud info api object.",
    "35-0": "<span id=\"fraud_message\">fraud_message</span>",
    "35-1": "\"848742\"=>\"BIN \\<> Billing Country\"",
    "35-2": "Contains all the rules triggered during the Kount's risk check service. Each number is the fraud_risk_rule code and the text that follows is the fraud_risk_rule message. This data mirrors the fraud info api object.",
    "36-0": "<span id=\"failure_type\">failure_type</span>",
    "36-1": "invalid_payment_method_hard",
    "36-2": "Provides additional information regarding the failure type of a transaction.",
    "37-0": "<span id=\"gateway_code\">gateway_code</span>",
    "37-1": "ih06u98jfoto",
    "37-2": "The gateway used for each transaction is denoted here.",
    "38-0": "<span id=\"cc_first_6\">cc_first_6</span>",
    "38-1": "111111",
    "38-2": "The first six digits of the credit card used for processing the transaction.",
    "39-0": "<span id=\"vat_number\">vat_number</span>",
    "39-1": "EU12345678",
    "39-2": "The VAT or Tax ID number of the customer during the transaction in the export.",
    "40-0": "<span id=\"backup_payment_method_used\">backup_payment_method_used</span>",
    "40-1": "TRUE, FALSE",
    "40-2": "Indicates whether a backup payment method was used in the transaction attempt.",
    "41-0": "<span id=\"vat_number\">vat_number</span>",
    "41-1": "123456",
    "41-2": "Indicates vat number.",
    "42-0": "<span id=\"card_brand\">card_brand</span>",
    "42-1": "Mastercard",
    "42-2": "Card brand",
    "43-0": "<span id=\"card_type\">card_type</span>",
    "43-1": "credit",
    "43-2": "Card type",
    "44-0": "<span id=\"card_level\">card_level</span>",
    "44-1": "prepaid",
    "44-2": "Card level",
    "45-0": "<span id=\"card_issuer\">card_issuer</span>",
    "45-1": "JP Morgan Chase Bank NA",
    "45-2": "Card issuer",
    "46-0": "<span id=\"card_issuing_country\">card_issuing_country</span>",
    "46-1": "US",
    "46-2": "Card issuing country",
    "47-0": "<span id=\"transaction_api_id\">transaction_api_id</span>",
    "47-1": "gyqgg0d3v9n1",
    "47-2": "v3 API identifier for the transaction within Recurly."
  },
  "cols": 3,
  "rows": 48,
  "align": [
    null,
    null,
    null
  ]
}
[/block]


# Version changelog

### Version 8 - 10/5/2024

- **Column Additions**: Addition of transaction_api_id.

### Version 7 - 9/24/2024

- **Column Additions**: Addition of card_brand, card_type, card_level, card_issuer, card_issuing_country columns.

### Version 6 - 8/1/2023

- **Column Changes**: Introduced "vat_number" column for merchants to capture customer's VAT or Tax ID number during a transaction in the export.

### Version 5 - 4/20/21

- **Column Changes**: The 'backup_payment_method_used' column was added at the end of the export to identify transactions initiated through a backup payment method attempt.

### Version 4 - 5/23/2019

- **Column Changes**: 'cc_first_6' column incorporated at the end of the export.

### Version 3 - 4/25/2019

- **Column Additions**: Addition of "cc_first_6" column.

### Version 2 - 1/15/2019

- **Mapping**: New payment gateway mappings included for Adyen, Qiwi, SEPA, SOFORT, and iDeal.