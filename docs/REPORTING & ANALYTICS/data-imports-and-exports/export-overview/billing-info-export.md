---
title: Billing info - export
excerpt: Explore the detailed guide on Billing Info export in Recurly's user guide.
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

The “Billing Info” export section in Recurly's user guide helps you identify and understand the billing information and payment methods associated with various accounts. It offers data that aids in distinguishing primary from backup payment methods, along with comprehensive billing details to keep track of each account’s status and payment preferences.

# Filters

### Account Status Filter

You can filter the billing information export data based on the account status. Here is how different statuses are defined:

* **Open**: Accounts that are currently not closed.
* **Non-subscribers**: Open accounts that do not have any active subscriptions.
* **Active Subscribers**: Open accounts holding at least one active subscription.
* **In Trial**: Accounts holding one or more subscriptions in the trial phase.
* **Past Due**: Accounts having at least one invoice in the past-due state.
* **Non-Renewing**: Accounts with subscriptions that will not renew post the current billing cycle; recently canceled.
* **Future**: Accounts with a subscription that hasn't yet begun.

### Time Range Filter

Utilize the "created\_at" field to filter data showcasing the accounts that had billing information added within a selected timeframe.

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
        Column Name
      </th>

      <th>
        Example
      </th>

      <th>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123456789, [janedoe@gmail.com](mailto:janedoe@gmail.com)
      </td>

      <td>
        Uniquely identifies your customers in Recurly, mainly using the email address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_first_name">billing\_first\_name</span>
      </td>

      <td>
        JJ
      </td>

      <td>
        The first name provided in the customer's billing details.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_last_name">billing\_last\_name</span>
      </td>

      <td>
        Smith
      </td>

      <td>
        The last name provided in the customer's billing details.
      </td>

      <td style={{ textAlign: "left" }}>
        varhcar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_company_name">account\_company\_name</span>
      </td>

      <td>
        Bluth Industries, Inc.
      </td>

      <td>
        Company name as per the billing details.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_address1">billing\_address1</span>
      </td>

      <td>
        123 Main Street
      </td>

      <td>
        The first line of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(60)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_address2">billing\_address2</span>
      </td>

      <td>
        Suite 300
      </td>

      <td>
        The second line of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(60)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_city">billing\_city</span>
      </td>

      <td>
        San Francisco
      </td>

      <td>
        The city component of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(60)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_state">billing\_state</span>
      </td>

      <td>
        CA
      </td>

      <td>
        The state component of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(60)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_postal_code">billing\_postal\_code</span>
      </td>

      <td>
        94107
      </td>

      <td>
        The postal code component of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_country">billing\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The country component of the customer's billing address.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(30)
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_phone">billing\_phone</span>
      </td>

      <td>
        555-2368
      </td>

      <td>
        The phone number provided in the customer's billing details.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(30)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_email">account\_email</span>
      </td>

      <td>
        [test@example.com](mailto:test@example.com)
      </td>

      <td>
        The email address associated with the customer's account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="cc_type">cc\_type</span>
      </td>

      <td>
        visa/master/discover/jcb/amex/diners
      </td>

      <td>
        Indicates the type of credit card associated with the customer's account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td>
        <span id="cc_last_four">cc\_last\_four</span>
      </td>

      <td>
        1111
      </td>

      <td>
        The last four digits of the customer's credit card number.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(4)
      </td>
    </tr>

    <tr>
      <td>
        <span id="expire_month">expire\_month</span>
      </td>

      <td>
        4
      </td>

      <td>
        The month when the customer's credit card expires.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="expire_year">expire\_year</span>
      </td>

      <td>
        2014
      </td>

      <td>
        The year when the customer's credit card expires.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_vat_number">billing\_vat\_number</span>
      </td>

      <td>
        IE213123123
      </td>

      <td>
        VAT number provided by EU customers.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="created_at">created\_at</span>
      </td>

      <td>
        2011-08-15
      </td>

      <td>
        The date when the billing information was added to the account.
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
        2013-09-12
      </td>

      <td>
        The last date when the billing information was updated on the account.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="Payment_method">Payment\_method</span>
      </td>

      <td>
        CreditCard / PayPal/ Roku/ Amazon / Bank Account / paypal\_braintree, jcb, qiwiwallet, etc.
      </td>

      <td>
        The payment method chosen by the customer for transactions.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="maintenance_url">maintenance\_url</span>
      </td>

      <td>
        app.recurly.com/account/sdasdasd
      </td>

      <td>
        The URL directing to the customer's hosted account maintenance.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="geo_code">geo\_code</span>
      </td>

      <td>
        *
      </td>

      <td>
        *
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ip_address">ip\_address</span>
      </td>

      <td>
        99.89.1010.0101
      </td>

      <td>
        The IP address noted at the time of entering the billing information.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
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
        The country associated with the IP address noted during billing information entry.
      </td>

      <td style={{ textAlign: "left" }}>
        Varchar(2)
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
        The initial six digits of the credit card used for the transaction.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(6)
      </td>
    </tr>

    <tr>
      <td>
        <span id="primary_payment_method">primary\_payment\_method</span>
      </td>

      <td>
        true, false
      </td>

      <td>
        Indicates whether the billing info should be used as a primary payment method.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="billing_info_id">billing\_info\_id</span>
      </td>

      <td>
        123456789
      </td>

      <td>
        Unique identifier for billing info.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="backup_payment_method">backup\_payment\_method</span>
      </td>

      <td>
        true, false
      </td>

      <td>
        Indicates whether the billing info should be used as a backup for invoice failures.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        billing\_info\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Billing Info API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 7 - 02/5/24

* Addition of `billing_info_api_id`.

### Version 6 - 03/29/21

* Introduction of the backup\_payment\_method column to highlight if the billing info is the backup payment method (TRUE/FALSE).

### Version 5 - 12/3/20

* Introduction of the “primary\_payment\_method” column to indicate if the billing info is the main payment method (TRUE/FALSE).
* Addition of billing\_info\_id displaying the ID of the billing info.

### Version 4 - 5/23/2019

* 'cc\_first\_6' column was moved to the end of the export.

### Version 3 - 4/25/2019

* Addition of "cc\_first\_6" to the export.

### Version 2 - 5/24/2018

* Column names were refined to differentiate clearly between billing and account info.
* Addition of "ip\_address" and "ip\_address\_country" columns to the export.
* Addition of “geo\_code” column. (Applicable only if Vertex tax integration is enabled)
