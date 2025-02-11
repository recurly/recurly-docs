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

Shows all gift cards purchased during the selected time range. Uses the "created\_at" field from this export.

#### Modified

Shows all gift cards changed during the selected time range. Changes could be triggered by a resent email, edited delivery information, regenerated redemption code, cancelation, redemption, or change in balance. Uses the "updated\_at" field from this export.

#### Redeemed

Shows all gift cards redeemed on an account during the selected time range. Uses the "redeemed\_at" field from this export.

#### Delivered

Shows all gift cards delivered during the selected time range. Delivery indicates the last time Recurly sent the Gift Card Delivery email to the delivery email address. Uses the "delivered\_at" field from this export.

#### Canceled

Show all gift cards canceled during the selected time range. Uses the "canceled\_at" field from this export.

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

<Table align={[null,null,null,"left"]}>
  <thead>
    <tr>
      <th>
        ID
      </th>

      <th>
        **Example**
      </th>

      <th>
        **Description**
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="id">id</span>
      </td>

      <td>
        2003020297591186183
      </td>

      <td>
        The unique ID of the gift card.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="redemption_code">redemption\_code</span>
      </td>

      <td>
        518822D87268C142
      </td>

      <td>
        The redemption code, which the recipient uses to redeem the gift card credit.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="amount">amount</span>
      </td>

      <td>
        50.00
      </td>

      <td>
        The amount of the gift card.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="balance">balance</span>
      </td>

      <td>
        40.00
      </td>

      <td>
        The remaining balance of the gift card. Will be empty if `redeemed_at` is null. Will be 0.00 if gift card credit has been completely used up.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="currency">currency</span>
      </td>

      <td>
        USD
      </td>

      <td>
        The currency of the `amount` and `balance`.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="gifter_account_code">gifter\_account\_code</span>
      </td>

      <td>
        3345634
      </td>

      <td>
        The account code of the gifter's account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="purchase_invoice_number">purchase\_invoice\_number</span>
      </td>

      <td>
        1001
      </td>

      <td>
        The invoice number of the gift card purchase on the gifter's account.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="purchase_adjustment_uuid">purchase\_adjustment\_uuid</span>
      </td>

      <td>
        385a6a380e8228b298d8d7414183a8e1
      </td>

      <td>
        The unique id of the gift card charge on the purchase invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td>
        <span id="recipient_account_code">recipient\_account\_code</span>
      </td>

      <td>
        3345700
      </td>

      <td>
        The account code of the recipient's account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="recipient_adjustment_uuid">recipient\_adjustment\_uuid</span>
      </td>

      <td>
        387fbbdcdbd2473d4f6a3e480cb6f966
      </td>

      <td>
        The unique id of the gift card redemption credit. This is the original gift card credit.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        The date the gift card was purchased by the gifter.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="updated_at">updated\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        The date the gift card was last modified. Will equal `created_at` at initial creation.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivered_at">delivered\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        The last date Recurly sent the Gift Card Delivery email to the email address in the gift card's delivery information.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="redeemed_at">redeemed\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        The date the gift card was redeemed on the recipient's account.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="canceled_at">canceled\_at</span>
      </td>

      <td>
        2016-09-02 15:53:18 UTC
      </td>

      <td>
        The date the gift card was canceled. If empty, the gift card has not been canceled.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_method">delivery\_method</span>
      </td>

      <td>
        email, post
      </td>

      <td>
        The method of delivery, either `email` or `post`.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_first_name">delivery\_first\_name</span>
      </td>

      <td>
        John
      </td>

      <td>
        The first name of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_last_name">delivery\_last\_name</span>
      </td>

      <td>
        Smith
      </td>

      <td>
        The last name of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_email_address">delivery\_email\_address</span>
      </td>

      <td>
        [john@example.com](mailto:john@example.com)
      </td>

      <td>
        The email address of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_deliver_at">delivery\_deliver\_at</span>
      </td>

      <td>
        12/05/2020
      </td>

      <td>
        Will have a value if a future delivery date was specified. This feature is not yet supported, so it will be empty always.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_address1">delivery\_address1</span>
      </td>

      <td>
        123 Main Street
      </td>

      <td>
        The first street address of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_address2">delivery\_address2</span>
      </td>

      <td>
        Apt 100
      </td>

      <td>
        The second street address of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_city">delivery\_city</span>
      </td>

      <td>
        San Francisco
      </td>

      <td>
        The city of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_state">delivery\_state</span>
      </td>

      <td>
        CA
      </td>

      <td>
        The state/province of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_zip">delivery\_zip</span>
      </td>

      <td>
        94110
      </td>

      <td>
        The zip/postal code of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_country">delivery\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The country of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_phone">delivery\_phone</span>
      </td>

      <td>
        8003334444
      </td>

      <td>
        The phone number of the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_gifter_name">delivery\_gifter\_name</span>
      </td>

      <td>
        Sally
      </td>

      <td>
        The gifter's name, if provided.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="delivery_personal_message">delivery\_personal\_message</span>
      </td>

      <td>
        Hi John, Happy Birthday! I hope you have a great day! Love, Sally
      </td>

      <td>
        The personal message from the gifter to the recipient.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="redemption_invoice_number">redemption\_invoice\_number</span>
      </td>

      <td>
        1001
      </td>

      <td>
        If the Credit Invoices feature is enabled, this is the credit invoice issued when the gift card was redeemed. Credit Invoices is currently in beta. Contact Recurly Support to learn more.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        gift\_card\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Gift Card API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Changelog

### Version 2

* Addition of `gift_card_api_id`.
