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

* **All**: Includes all invoices that remain unpaid.
* **Pending**: Consists of invoices not yet due and only encompasses manual invoices.
* **Past Due**: Involves all invoices that have surpassed their due date without being settled.
* **Failed**: Pertains to invoices labeled as failed or not collected within the Dunning period.
* **Processing**: Concerns ACH transactions presently undergoing processing.

#### **Date Range Filters**

* **Created**: Invoices formulated within the chosen timeframe.
* **Modified**: Invoices altered in the specified period.
* **Due**: Invoices due in the specified period.

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
        Data type
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <span id="invoice_id">invoice\_id</span>
      </td>

      <td>
        336e028b12345b00b60b7845438d18b1
      </td>

      <td>
        Unique identifier for invoices within Recurly. This ID is also used in Invoices - Summary and Adjustments exports.
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
        1001
      </td>

      <td>
        Number used on the invoice through the admin console.
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
        smith
      </td>

      <td>
        Uniquely identifies your customers in Recurly. Defaults to the email address if no specific value is provided and cannot be modified. It is the main Recurly identifier for joining multiple exports.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_first_name">account\_first\_name</span>
      </td>

      <td>
        Eric
      </td>

      <td>
        First name of the customer from the associated account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_last_name">account\_last\_name</span>
      </td>

      <td>
        Schmidt
      </td>

      <td>
        Last name of the customer from the associated account.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_company">account\_company</span>
      </td>

      <td>
        Bluth Industries, Inc.
      </td>

      <td>
        Optionally identifies the company name provided.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
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
        Optional. Email address provided by the customer during signup, used for all customer communications. If absent, the site's billing contact will receive emails.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(255)
      </td>
    </tr>

    <tr>
      <td>
        <span id="account_phone">account\_phone</span>
      </td>

      <td>
        123-456-7890
      </td>

      <td>
        Optional. The phone number of the customer.
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
        2016-01-01 10:17:02 UTC
      </td>

      <td>
        Date of invoice creation.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="net_terms">net\_terms</span>
      </td>

      <td>
        on-receipt
      </td>

      <td>
        Specifies the terms of the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="due_on">due\_on</span>
      </td>

      <td>
        2016-01-01 10:17:02 UTC
      </td>

      <td>
        Due date of the invoice.
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
        failed
      </td>

      <td>
        Current status of the invoice, equivalent to "invoice\_state" in the Adjustments export.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(20)
      </td>
    </tr>

    <tr>
      <td>
        <span id="collection_method">collection\_method</span>
      </td>

      <td>
        automatic
      </td>

      <td>
        Indicates the collection method for the invoice - either "automatic" or "manual".
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="days_overdue">days\_overdue</span>
      </td>

      <td>
        12
      </td>

      <td>
        The number of days the invoice is overdue; will be zero if not overdue.
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
        The 3-character ISO code representing the invoice's currency.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(3)
      </td>
    </tr>

    <tr>
      <td>
        <span id="po_number">po\_number</span>
      </td>

      <td>
        1234
      </td>

      <td>
        The Purchase Order (PO) number associated with the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        varchar(50)
      </td>
    </tr>

    <tr>
      <td>
        <span id="closed_date">closed\_date</span>
      </td>

      <td>
        2016-05-18 11:17:07 UTC
      </td>

      <td>
        The date when the invoice was closed, applicable if failed or paid.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="modified_at">modified\_at</span>
      </td>

      <td>
        2016-05-18 11:17:07 UTC
      </td>

      <td>
        The date the invoice last underwent modification, including payment status updates.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_subtotal">invoice\_subtotal</span>
      </td>

      <td>
        136.78
      </td>

      <td>
        Subtotal amount of the invoice, prior to the addition of tax, discounts, and credits to compute the total amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_total">invoice\_total</span>
      </td>

      <td>
        345.67
      </td>

      <td>
        The total invoice amount.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_tax_amount">invoice\_tax\_amount</span>
      </td>

      <td>
        123.45
      </td>

      <td>
        The total tax amount levied on the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_discount_amount">invoice\_discount\_amount</span>
      </td>

      <td>
        144.58
      </td>

      <td>
        The total discount amount applied to the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
      </td>
    </tr>

    <tr>
      <td>
        <span id="category">category</span>
      </td>

      <td>
        31-60 days overdue
      </td>

      <td>
        Bucketed system for aging receivables and past-due invoices. "Current" for non-due invoices, with past-due invoices grouped based on overdue duration.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td>
        <span id="invoice_credits">invoice\_credits</span>
      </td>

      <td>
        144.58
      </td>

      <td>
        The amount of credits applied to the invoice.
      </td>

      <td style={{ textAlign: "left" }}>
        numeric
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
        The invoice's outstanding balance. **This column will be null until the Recurly's Credit Invoices feature is enabled on your site.**
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
        2016-05-18 11:17:07 UTC
      </td>

      <td>
        The last change date of the invoice balance due to a transaction or credit payment. **This column will be null until the Recurly's Credit Invoices feature is enabled on your site.**
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
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
        Identifier for business entity code.
      </td>

      <td style={{ textAlign: "left" }}>
        string
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

# Version Changelog

### Version 3 - 2/5/25

Addition of `invoice_api_id` column.

### Version 2 - 3/15/2023

Addition of `business_entity_code` column.

The Accounts Receivable export identifies customers who have not paid their invoices, as well as the aging of all outstanding receivables.
