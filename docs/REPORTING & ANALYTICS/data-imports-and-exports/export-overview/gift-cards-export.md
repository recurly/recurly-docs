---
title: Gift cards - export
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Gift Cards export includes a row for every purchased gift card on your site. Here you can see what gift card amounts are most popular, who is purchasing the most gift cards, who is redeeming gift cards, and what gift cards haven't been redeemed or still have remaining balances. To access the Gift Cards export, visit the <a href="http://app.recurly.com/go/exports">Exports</a> page under Reports in your Recurly site.

### Date Range Filters

#### Created

Shows all gift cards purchased during the selected time range. Uses the "created_at" field from this export.

#### Modified

Shows all gift cards changed during the selected time range. Changes could be triggered by a resent email, edited delivery information, regenerated redemption code, cancelation, redemption, or change in balance. Uses the "updated_at" field from this export.

#### Redeemed

Shows all gift cards redeemed on an account during the selected time range. Uses the "redeemed_at" field from this export.

#### Delivered

Shows all gift cards delivered during the selected time range. Delivery indicates the last time Recurly sent the Gift Card Delivery email to the delivery email address. Uses the "delivered_at" field from this export.

#### Canceled

Show all gift cards canceled during the selected time range. Uses the "canceled_at" field from this export.

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
    "h-0": "ID",
    "h-1": "**Example**",
    "h-2": "**Description**",
    "h-3": "Data type (max size)",
    "0-0": "<span id=\"id\">id</span>",
    "0-1": "2003020297591186183",
    "0-2": "The unique ID of the gift card.",
    "0-3": "string",
    "1-0": "<span id=\"redemption_code\">redemption_code</span>",
    "1-1": "518822D87268C142",
    "1-2": "The redemption code, which the recipient uses to redeem the gift card credit.",
    "1-3": "varchar(255)",
    "2-0": "<span id=\"amount\">amount</span>",
    "2-1": "50.00",
    "2-2": "The amount of the gift card.",
    "2-3": "numeric",
    "3-0": "<span id=\"balance\">balance</span>",
    "3-1": "40.00",
    "3-2": "The remaining balance of the gift card. Will be empty if `redeemed_at` is null. Will be 0.00 if gift card credit has been completely used up.",
    "3-3": "numeric",
    "4-0": "<span id=\"currency\">currency</span>",
    "4-1": "USD",
    "4-2": "The currency of the `amount` and `balance`.",
    "4-3": "varchar(3)",
    "5-0": "<span id=\"gifter_account_code\">gifter_account_code</span>",
    "5-1": "3345634",
    "5-2": "The account code of the gifter's account.",
    "5-3": "varchar(50)",
    "6-0": "<span id=\"purchase_invoice_number\">purchase_invoice_number</span>",
    "6-1": "1001",
    "6-2": "The invoice number of the gift card purchase on the gifter's account.",
    "6-3": "string",
    "7-0": "<span id=\"purchase_adjustment_uuid\">purchase_adjustment_uuid</span>",
    "7-1": "385a6a380e8228b298d8d7414183a8e1",
    "7-2": "The unique id of the gift card charge on the purchase invoice.",
    "7-3": "varchar(32)",
    "8-0": "<span id=\"recipient_account_code\">recipient_account_code</span>",
    "8-1": "3345700",
    "8-2": "The account code of the recipient's account.",
    "8-3": "varchar(50)",
    "9-0": "<span id=\"recipient_adjustment_uuid\">recipient_adjustment_uuid</span>",
    "9-1": "387fbbdcdbd2473d4f6a3e480cb6f966",
    "9-2": "The unique id of the gift card redemption credit. This is the original gift card credit.",
    "9-3": "varchar(32)",
    "10-0": "<span id=\"created_at\">created_at</span>",
    "10-1": "2016-09-02 15:53:18 UTC",
    "10-2": "The date the gift card was purchased by the gifter.",
    "10-3": "timestamp",
    "11-0": "<span id=\"updated_at\">updated_at</span>",
    "11-1": "2016-09-02 15:53:18 UTC",
    "11-2": "The date the gift card was last modified. Will equal `created_at` at initial creation.",
    "11-3": "timestamp",
    "12-0": "<span id=\"delivered_at\">delivered_at</span>",
    "12-1": "2016-09-02 15:53:18 UTC",
    "12-2": "The last date Recurly sent the Gift Card Delivery email to the email address in the gift card's delivery information.",
    "12-3": "timestamp",
    "13-0": "<span id=\"redeemed_at\">redeemed_at</span>",
    "13-1": "2016-09-02 15:53:18 UTC",
    "13-2": "The date the gift card was redeemed on the recipient's account.",
    "13-3": "timestamp",
    "14-0": "<span id=\"canceled_at\">canceled_at</span>",
    "14-1": "2016-09-02 15:53:18 UTC",
    "14-2": "The date the gift card was canceled. If empty, the gift card has not been canceled.",
    "14-3": "timestamp",
    "15-0": "<span id=\"delivery_method\">delivery_method</span>",
    "15-1": "email, post",
    "15-2": "The method of delivery, either `email` or `post`.",
    "15-3": "varchar(255)",
    "16-0": "<span id=\"delivery_first_name\">delivery_first_name</span>",
    "16-1": "John",
    "16-2": "The first name of the recipient.",
    "16-3": "varchar(255)",
    "17-0": "<span id=\"delivery_last_name\">delivery_last_name</span>",
    "17-1": "Smith",
    "17-2": "The last name of the recipient.",
    "17-3": "varchar(255)",
    "18-0": "<span id=\"delivery_email_address\">delivery_email_address</span>",
    "18-1": "[john@example.com](mailto:john@example.com)",
    "18-2": "The email address of the recipient.",
    "18-3": "varchar(255)",
    "19-0": "<span id=\"delivery_deliver_at\">delivery_deliver_at</span>",
    "19-1": "12/05/2020",
    "19-2": "Will have a value if a future delivery date was specified. This feature is not yet supported, so it will be empty always.",
    "19-3": "timestamp",
    "20-0": "<span id=\"delivery_address1\">delivery_address1</span>",
    "20-1": "123 Main Street",
    "20-2": "The first street address of the recipient.",
    "20-3": "string",
    "21-0": "<span id=\"delivery_address2\">delivery_address2</span>",
    "21-1": "Apt 100",
    "21-2": "The second street address of the recipient.",
    "21-3": "string",
    "22-0": "<span id=\"delivery_city\">delivery_city</span>",
    "22-1": "San Francisco",
    "22-2": "The city of the recipient.",
    "22-3": "string",
    "23-0": "<span id=\"delivery_state\">delivery_state</span>",
    "23-1": "CA",
    "23-2": "The state/province of the recipient.",
    "23-3": "string",
    "24-0": "<span id=\"delivery_zip\">delivery_zip</span>",
    "24-1": "94110",
    "24-2": "The zip/postal code of the recipient.",
    "24-3": "string",
    "25-0": "<span id=\"delivery_country\">delivery_country</span>",
    "25-1": "US",
    "25-2": "The country of the recipient.",
    "25-3": "string",
    "26-0": "<span id=\"delivery_phone\">delivery_phone</span>",
    "26-1": "8003334444",
    "26-2": "The phone number of the recipient.",
    "26-3": "string",
    "27-0": "<span id=\"delivery_gifter_name\">delivery_gifter_name</span>",
    "27-1": "Sally",
    "27-2": "The gifter's name, if provided.",
    "27-3": "varchar(255)",
    "28-0": "<span id=\"delivery_personal_message\">delivery_personal_message</span>",
    "28-1": "Hi John, Happy Birthday! I hope you have a great day! Love, Sally",
    "28-2": "The personal message from the gifter to the recipient.",
    "28-3": "string",
    "29-0": "<span id=\"redemption_invoice_number\">redemption_invoice_number</span>",
    "29-1": "1001",
    "29-2": "If the Credit Invoices feature is enabled, this is the credit invoice issued when the gift card was redeemed. Credit Invoices is currently in beta. Contact Recurly Support to learn more.",
    "29-3": "string",
    "30-0": "gift_card_api_id",
    "30-1": "e28zov4fw0v2",
    "30-2": "Gift Card API ID",
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


# Changelog

### Version 2

- Addition of `gift_card_api_id`.