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

This filter allows you to select invoices based on their current statuses which include:\
-**All**: All invoices including credit and charge.\
-**Charge**: Only charge invoices.\
-**Credit**: Only credit invoices.

#### Date Range Filters

##### Created

Involves invoices created within a chosen time span.

##### Modified

Entails invoices modified in a selected time range.

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
        <span id="id">id</span>
      </td>

      <td>
        b964b5439c2548a489b3a136e75aee9f
      </td>

      <td>
        Unique internal identifier for the invoice. This is also called the 'invoice\_id' or 'uuid' for the invoice in the API.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(32)
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_number">invoice\_number</span>
      </td>

      <td>
        1291
      </td>

      <td>
        External invoice identifier.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="billed_date">billed\_date</span>
      </td>

      <td>
        2012-02-19 12:01:33 PST
      </td>

      <td>
        Creation date of the invoice. Equivalent to date in the deprecated Invoices export. Used for Created date range filter.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="due_on">due\_on</span>
      </td>

      <td>
        2012-02-19 12:01:33 PST
      </td>

      <td>
        Date invoice is due. This is the date the net terms is reached.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="closed_at">closed\_at</span>
      </td>

      <td>
        2012-02-19 12:01:33 PST
      </td>

      <td>
        Date invoice was closed (paid) or failed.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="status">status</span>
      </td>

      <td>
        pending, processing, past\_due, paid, failed, voided
      </td>

      <td>
        Current status of the invoice. Equivalent to invoice\_state in the Adjustments export. See filter notes above for details on what each status means.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td>
        <span id="net_terms">net\_terms</span>
      </td>

      <td>
        on-receipt, net-10, net-30, net-60
      </td>

      <td>
        Identifies the net\_terms agreement associated with the invoice. All automatic collection invoices are due 'on-receipt'. Manual collection invoices can have terms of net-10, net-30, net-60, or a custom net day amount.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="collection_method">collection\_method</span>
      </td>

      <td>
        automatic or manual
      </td>

      <td>
        Identifies whether the invoice fees are collected via manual or automatic invoicing. An automatic invoice means a corresponding transaction is run using the account's billing information at the same time the invoice is created. Manual invoices are created without a corresponding transaction.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_code">account\_code</span>
      </td>

      <td>
        123122E
      </td>

      <td>
        Account code being charged for this invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_name">account\_name</span>
      </td>

      <td>
        JJ Smith
      </td>

      <td>
        First and last name from account associated with that invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_company">account\_company</span>
      </td>

      <td>
        Company, Inc.
      </td>

      <td>
        Company name from account. This field is from the Account Info and is displayed on the invoice if it exists.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(225)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_line1">account\_line1</span>
      </td>

      <td>
        1 Main Street
      </td>

      <td>
        Address line 1 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_line2">account\_line2</span>
      </td>

      <td>
        Suite 100
      </td>

      <td>
        Address line 2 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_city">account\_city</span>
      </td>

      <td>
        San Francisco
      </td>

      <td>
        City of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_state">account\_state</span>
      </td>

      <td>
        CA
      </td>

      <td>
        State or province of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_zip">account\_zip</span>
      </td>

      <td>
        94107
      </td>

      <td>
        ZIP/postal code of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_country">account\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The 2 letter country code for the country of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="vat_number">vat\_number</span>
      </td>

      <td>
        IE124211145
      </td>

      <td>
        VAT registration number for the customer on the invoice. This will come from the VAT Number field in the Billing Info or the Account Info depending on your tax settings and the invoice collection method.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
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
        For manual invoicing, this identifies the Purchase Order number associated with the invoice. This value must be entered by the merchant at the time the invoice is created or it will not exist.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="coupon_code">coupon\_code</span>
      </td>

      <td>
        50off
      </td>

      <td>
        The code for the coupon associated with any discounts on the invoice. This value will only exist if a coupon was applied to the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        string
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
        The currency of the amounts on the invoice. We do not allow mixed currency invoices.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_total">invoice\_total</span>
      </td>

      <td>
        100
      </td>

      <td>
        The final total on the invoice. The summation of invoice charges, discounts, credits, and tax. Equivalent to the total in the deprecated Invoices export.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_subtotal">invoice\_subtotal</span>
      </td>

      <td>
        50
      </td>

      <td>
        The Subtotal on the invoice. The summation of charges, discounts, and credits, before tax.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
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
        The total tax amount on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_type">tax\_type</span>
      </td>

      <td>
        usst, vat, ca, au, nz
      </td>

      <td>
        Provides the tax type as "vat" for EU VAT, "usst" for U.S. Sales Tax, or the 2 letter country code for country level tax types like Canada, Australia, New Zealand, Israel, and all non-EU European countries.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(6)
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_region">tax\_region</span>
      </td>

      <td>
        NY, FR, GST, VAT
      </td>

      <td>
        Provides the tax region applied on an invoice. For U.S. Sales Tax, this will be the 2 letter state code. For EU VAT this will be the 2 letter country code. For all country level tax types, this will display the regional tax, like VAT, GST, or PST.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(15)
      </td>
    </tr>

    <tr>
      <td>
        <span id="tax_rate">tax\_rate</span>
      </td>

      <td>
        0.1
      </td>

      <td>
        Tax rate applied on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="credit_to_account">credit\_to\_account</span>
      </td>

      <td>
        0
      </td>

      <td>
        Amount of credit applied back to the account. This amount is a charge with adjustment\_origin of 'carryforward' on the invoice. This charge is what zeros out the invoice and should be filtered out of your reports. Credit to Account also maps to the uninvoiced credit that is created for the same amount and left on the account for payment of a future invoice. That credit will have an adjustment\_origin that matches the original charge's origin.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="recovery_reason">recovery\_reason</span>
      </td>

      <td>
        exp\_date, retry, account\_updater, prior\_recovery, customer\_updates
      </td>

      <td>
        If the initial transaction failed but a subsequent one succeeded, this field indicates why. See the details of what each reason means in our blog "[Revenue Recovery: What Has Recurly Recovered for Me Lately?](https://blog.recurly.com/what-has-recurly-recovered-revenue)".
      </td>

      <td style={{ textAlign: "left" }}>
        varchar
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_country">invoice\_country</span>
      </td>

      <td>
        FR
      </td>

      <td>
        This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the EU or NZ country code of the customer's address on the invoice. The country refers to the evidence\_matched.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(2)
      </td>
    </tr>

    <tr>
      <td>
        <span id="evidence_matched">evidence\_matched</span>
      </td>

      <td>
        Account Info Country, Billing Info Country, IP Address Country, Credit Card BIN Country
      </td>

      <td>
        This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the two pieces of evidence that matched when the invoice was created. The corresponding country is the invoice\_country.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2014-12-26 08:23:34 PST
      </td>

      <td>
        The date the invoice was last modified. An invoice is only modified if the status changes. Used for Modified date range filter.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_type">invoice\_type</span>
      </td>

      <td>
        purchase, refund, renewal, immediate\_change, termination, credit, gift\_card, write\_off, external\_refund, carryforward\_credit, carryforward\_gift\_credit, usage\_correction, import
      </td>

      <td>
        This is the invoice origin. The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'. All other invoice types are unlocked only when the Credit Invoices feature is enabled. See the full table of [invoice origins](/docs/invoices#section-origins) for descriptions.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="original_invoice_number">original\_invoice\_number</span>
      </td>

      <td>
        1002
      </td>

      <td>
        If the row is a refund invoice, this value will exist and show the invoice number of the purchase invoice the refund was created from.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_name">ship\_address\_name</span>
      </td>

      <td>
        Julie Smith
      </td>

      <td>
        The first and last name associated with the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_line1">ship\_address\_line1</span>
      </td>

      <td>
        ship\_address\_line1
      </td>

      <td>
        ship\_address\_line1
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_line2">ship\_address\_line2</span>
      </td>

      <td>
        Apt 1
      </td>

      <td>
        The second line of the street address for the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_city">ship\_address\_city</span>
      </td>

      <td>
        West Bloomfield
      </td>

      <td>
        The city for the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_state">ship\_address\_state</span>
      </td>

      <td>
        MI
      </td>

      <td>
        The state for the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_zip">ship\_address\_zip</span>
      </td>

      <td>
        48322
      </td>

      <td>
        The zip or postal code for the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_country">ship\_address\_country</span>
      </td>

      <td>
        US
      </td>

      <td>
        The country for the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="ship_address_phone">ship\_address\_phone</span>
      </td>

      <td>
        248-555-1212
      </td>

      <td>
        The phone number associated with the shipping address
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_doc_type">invoice\_doc\_type</span>
      </td>

      <td>
        legacy, charge, credit
      </td>

      <td>
        This is the invoice document type. All invoices created before the Credit Invoices feature is enabled will have a type of ‘legacy’. Once Credit Invoices is enabled, new invoices will be either ‘charge’ or ‘credit’.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_balance">invoice\_balance</span>
      </td>

      <td>
        50.25
      </td>

      <td>
        The balance of the invoice. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_balance_modified_at">invoice\_balance\_modified\_at</span>
      </td>

      <td>
        2016-01-01 10:17:02 UTC
      </td>

      <td>
        The datetime the invoice\_balance last changed due to a transaction or credit payment. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_discount">invoice\_discount</span>
      </td>

      <td>
        50.25
      </td>

      <td>
        Total of all discounts on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_subtotal_before_discounts">invoice\_subtotal\_before\_discounts</span>
      </td>

      <td>
        50.25
      </td>

      <td>
        The total of all adjustments on the invoice, before discounts and taxes.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_refundable_amount">invoice\_refundable\_amount</span>
      </td>

      <td>
        50.25
      </td>

      <td>
        The refundable amount of the invoice, which is the invoice total, including discounts and tax, minus all credit invoices issued against it. **This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="shipping_address_count">shipping\_address\_count</span>
      </td>

      <td>
        1
      </td>

      <td>
        Number of shipping addresses if multiple shipping addresses per invoice is enabled.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="dunning_campaign_code">dunning\_campaign\_code</span>
      </td>

      <td>
        12345678
      </td>

      <td>
        Dunning Campaign Code.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="dunning_campaign_id">dunning\_campaign\_id</span>
      </td>

      <td>
        23456789
      </td>

      <td>
        Dunning Campaign ID.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="dunning_campaign_version">dunning\_campaign\_version</span>
      </td>

      <td>
        1234
      </td>

      <td>
        Dunning Campaign Version.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="used_tax_service">used\_tax\_service</span>
      </td>

      <td>
        TRUE
      </td>

      <td>
        TRUE/FALSE boolean column indicating whether the invoice has used Recurly tax services.
      </td>

      <td style={{ textAlign: "left" }}>
        boolean
      </td>
    </tr>

    <tr>
      <td>
        <span id="business_entity_code">business\_entity\_code</span>
      </td>

      <td>
        123456789
      </td>

      <td>
        Business Entity Code.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="parent_account_code">parent\_account\_code</span>
      </td>

      <td>
        123122E
      </td>

      <td>
        Parent account code being charged for this invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        invoice\_api\_id
      </td>

      <td>
        e28zov4fw0v2
      </td>

      <td>
        Invoice API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 7 - 2/5/25

* Addition of `invoice_api_id`

### Version 5 - 12/12/23

* Addition of parent\_account\_code column.

### Version 4 - 5/15/23

* Addition of business\_entity\_code column.

### Version 3 - 3/21/23

* Addition of used\_tax\_service column.

### Version 2 - 6/23/21

* Addition of dunning\_campaign\_code, dunning\_campain\_id and dunning\_campaign version columns.
