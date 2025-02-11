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

* **Authorization**: A $1 or $0 transaction created to validate payment information usability after billing updates.  
* **Purchase**: A positive charge sent to the processor for fund collection and transfer to your merchant bank.  
* **Refund**: A negative charge sent to the processor to reimburse and transfer funds back to the customer’s bank.  

#### Transaction Statuses

* **Success**: The transaction was accepted by the gateway for processing.  
* **Declined**: The transaction was rejected by the gateway and will not be processed.  
* **Void**: Processing was stopped before settlement (e.g., when issuing full refunds before a purchase is fully settled).  
* **Processing**: The payment is in progress with the gateway, commonly seen with direct debit transactions.

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

<Table>
  <thead>
    <tr>
      <th>
        Column Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123sd341
      </td>

      <td>
        The specific account code charged during the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="name">name</span>
      </td>

      <td>
        JJ Smith
      </td>

      <td>
        Customer name as stated in their billing data.
      </td>
    </tr>

    <tr>
      <td>
        <span id="transaction_id">transaction\_id</span>
      </td>

      <td>
        6c17ba39e8734ebaa5bf98fff6d91bb9
      </td>

      <td>
        Unique identifier for the transaction within Recurly.
      </td>
    </tr>

    <tr>
      <td>
        <span id="type">type</span>
      </td>

      <td>
        authorization, purchase, refund
      </td>

      <td>
        Specifies the type of transaction reported to the gateway.
      </td>
    </tr>

    <tr>
      <td>
        <span id="amount">amount</span>
      </td>

      <td>
        9.95
      </td>

      <td>
        The total amount of the transaction sent to the payment gateway.
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_amount">tax\_amount</span>
      </td>

      <td>
        15.00
      </td>

      <td>
        The tax charges associated with the transaction.
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
        The currency reported to the payment gateway for transaction processing.
      </td>
    </tr>

    <tr>
      <td>
        <span id="date">date</span>
      </td>

      <td>
        2012-01-19 11:16:41 PST
      </td>

      <td>
        The date and time the transaction took place. Used for "created" date range filter.
      </td>
    </tr>

    <tr>
      <td>
        <span id="status">status</span>
      </td>

      <td>
        declined, void, success, processing
      </td>

      <td>
        The response received from the payment gateway concerning the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="message">message</span>
      </td>

      <td>
        This transaction has been approved
      </td>

      <td>
        Message received from the payment gateway regarding the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="test">test</span>
      </td>

      <td>
        TRUE, FALSE
      </td>

      <td>
        Indicates if the transaction was carried out on a production gateway.
      </td>
    </tr>

    <tr>
      <td>
        <span id="cc_type">cc\_type</span>
      </td>

      <td>
        visa, master, discover, amex, jcb, diners
      </td>

      <td>
        The type of credit card utilized for the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="cvv_result">cvv\_result</span>
      </td>

      <td>
        M, N
      </td>

      <td>
        The result from checking the CVV/CVC value on the transaction when it was processed.
      </td>
    </tr>

    <tr>
      <td>
        <span id="avs_result">avs\_result</span>
      </td>

      <td>
        N, P, D
      </td>

      <td>
        The overall AVS result from checking the transaction when it was processed.
      </td>
    </tr>

    <tr>
      <td>
        <span id="avs_result_postal">avs\_result\_postal</span>
      </td>

      <td>
        N, Y
      </td>

      <td>
        The result from verifying the zip code on the transaction when it was processed.
      </td>
    </tr>

    <tr>
      <td>
        <span id="avs_result_street">avs\_result\_street</span>
      </td>

      <td>
        N, Y
      </td>

      <td>
        The result from verifying the address 1 value on the transaction when it was processed.
      </td>
    </tr>

    <tr>
      <td>
        <span id="reference">reference</span>
      </td>

      <td>
        4119385445
      </td>

      <td>
        The identifier for the transaction from the payment gateway.
      </td>
    </tr>

    <tr>
      <td>
        <span id="approval_code">approval\_code</span>
      </td>

      <td>
        varies by gateway
      </td>

      <td>
        The approval code for the transaction from the payment gateway.
      </td>
    </tr>

    <tr>
      <td>
        <span id="description">description</span>
      </td>

      <td>
        varies by gateway
      </td>

      <td>
        The description sent to the payment gateway for the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="state">state</span>
      </td>

      <td>
        CA
      </td>

      <td>
        The state value from the customer's billing information on the account.
      </td>
    </tr>

    <tr>
      <td>
        <span id="country">country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The country value from the customer's billing information on the account.
      </td>
    </tr>

    <tr>
      <td>
        <span id="ip_address_country">ip\_address\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The country associated with the IP address of the customer's location when the transaction was processed.
      </td>
    </tr>

    <tr>
      <td>
        <span id="original_transaction_id">original\_transaction\_id</span>
      </td>

      <td>
        6b9fc18e2497498b9e3700cd55e2ea84
      </td>

      <td>
        For refunds, this field identifies the payment being refunded.
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_id">invoice\_id</span>
      </td>

      <td>
        4bdb2171cebe4ecfb0cb129bd1a65746
      </td>

      <td>
        References the invoice that generated this transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="subscription_id">subscription\_id</span>
      </td>

      <td>
        3252sdasdbe4ecfb0cb129bd1a65746
      </td>

      <td>
        References the subscription or list of subscriptions that instigated this transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="po_number">po\_number</span>
      </td>

      <td>
        AE12523
      </td>

      <td>
        The purchase order number for the invoice.
      </td>
    </tr>

    <tr>
      <td>
        <span id="collection_method">collection\_method</span>
      </td>

      <td>
        automatic, manual
      </td>

      <td>
        The type of collection method used for the invoice.
      </td>
    </tr>

    <tr>
      <td>
        <span id="transaction_gateway_type">transaction\_gateway\_type</span>
      </td>

      <td>
        test, wirecard, authorize, etc
      </td>

      <td>
        The payment gateway utilized to process the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2014-01-01 10:00:00 PST
      </td>

      <td>
        The date/time the transaction was last updated. Used for the "modified" date range filter.
      </td>
    </tr>

    <tr>
      <td>
        <span id="origin">origin</span>
      </td>

      <td>
        recurring, API, hpp
      </td>

      <td>
        Identifies what initiated the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="gateway_error_codes">gateway\_error\_codes</span>
      </td>

      <td>
        500
      </td>

      <td>
        Lists the gateway error code for declined transactions, if applicable.
      </td>
    </tr>

    <tr>
      <td>
        <span id="payment_method">payment\_method</span>
      </td>

      <td>
        PayPal, Amazon Payment, Credit Card, etc
      </td>

      <td>
        Specifies the method used for payment.
      </td>
    </tr>

    <tr>
      <td>
        <span id="collected_at">collected\_at</span>
      </td>

      <td>
        2014-01-01 10:00:00 PST
      </td>

      <td>
        For manually recorded payments, this reflects the specified date when recording the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="fraud_decision">fraud\_decision</span>
      </td>

      <td>
        DECLINE, REVIEW, APPROVE
      </td>

      <td>
        Contains the decision returned by the Kount risk check service for this transaction.  This data mirrors the fraud info api object.
      </td>
    </tr>

    <tr>
      <td>
        <span id="fraud_score">fraud\_score</span>
      </td>

      <td>
        36 (between 1 and 99)
      </td>

      <td>
        The risk score assigned by Kount's risk check service for this transaction. This data mirrors the fraud info api object.
      </td>
    </tr>

    <tr>
      <td>
        <span id="fraud_message">fraud\_message</span>
      </td>

      <td>
        "848742"=>"BIN \<> Billing Country"
      </td>

      <td>
        Contains all the rules triggered during the Kount's risk check service. Each number is the fraud\_risk\_rule code and the text that follows is the fraud\_risk\_rule message. This data mirrors the fraud info api object.
      </td>
    </tr>

    <tr>
      <td>
        <span id="failure_type">failure\_type</span>
      </td>

      <td>
        invalid\_payment\_method\_hard
      </td>

      <td>
        Provides additional information regarding the failure type of a transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="gateway_code">gateway\_code</span>
      </td>

      <td>
        ih06u98jfoto
      </td>

      <td>
        The gateway used for each transaction is denoted here.
      </td>
    </tr>

    <tr>
      <td>
        <span id="cc_first_6">cc\_first\_6</span>
      </td>

      <td>
        111111
      </td>

      <td>
        The first six digits of the credit card used for processing the transaction.
      </td>
    </tr>

    <tr>
      <td>
        <span id="vat_number">vat\_number</span>
      </td>

      <td>
        EU12345678
      </td>

      <td>
        The VAT or Tax ID number of the customer during the transaction in the export.
      </td>
    </tr>

    <tr>
      <td>
        <span id="backup_payment_method_used">backup\_payment\_method\_used</span>
      </td>

      <td>
        TRUE, FALSE
      </td>

      <td>
        Indicates whether a backup payment method was used in the transaction attempt.
      </td>
    </tr>

    <tr>
      <td>
        <span id="vat_number">vat\_number</span>
      </td>

      <td>
        123456
      </td>

      <td>
        Indicates vat number.
      </td>
    </tr>

    <tr>
      <td>
        <span id="card_brand">card\_brand</span>
      </td>

      <td>
        Mastercard
      </td>

      <td>
        Card brand
      </td>
    </tr>

    <tr>
      <td>
        <span id="card_type">card\_type</span>
      </td>

      <td>
        credit
      </td>

      <td>
        Card type
      </td>
    </tr>

    <tr>
      <td>
        <span id="card_level">card\_level</span>
      </td>

      <td>
        prepaid
      </td>

      <td>
        Card level
      </td>
    </tr>

    <tr>
      <td>
        <span id="card_issuer">card\_issuer</span>
      </td>

      <td>
        JP Morgan Chase Bank NA
      </td>

      <td>
        Card issuer
      </td>
    </tr>

    <tr>
      <td>
        <span id="card_issuing_country">card\_issuing\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        Card issuing country
      </td>
    </tr>

    <tr>
      <td>
        <span id="transaction_api_id">transaction\_api\_id</span>
      </td>

      <td>
        gyqgg0d3v9n1
      </td>

      <td>
        v3 API identifier for the transaction within Recurly.
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 8 - 10/5/2024

* **Column Additions**: Addition of transaction\_api\_id.

### Version 7 - 9/24/2024

* **Column Additions**: Addition of card\_brand, card\_type, card\_level, card\_issuer, card\_issuing\_country columns.

### Version 6 - 8/1/2023

* **Column Changes**: Introduced "vat\_number" column for merchants to capture customer's VAT or Tax ID number during a transaction in the export.

### Version 5 - 4/20/21

* **Column Changes**: The 'backup\_payment\_method\_used' column was added at the end of the export to identify transactions initiated through a backup payment method attempt.

### Version 4 - 5/23/2019

* **Column Changes**: 'cc\_first\_6' column incorporated at the end of the export.

### Version 3 - 4/25/2019

* **Column Additions**: Addition of "cc\_first\_6" column.

### Version 2 - 1/15/2019

* **Mapping**: New payment gateway mappings included for Adyen, Qiwi, SEPA, SOFORT, and iDeal.
