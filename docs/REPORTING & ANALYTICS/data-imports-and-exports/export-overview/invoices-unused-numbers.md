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

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Column Name
      </th>

      <th style={{ textAlign: "left" }}>
        Example
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Data type (max size)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_number">invoice\_number</span>
      </td>

      <td style={{ textAlign: "left" }}>
        1291
      </td>

      <td style={{ textAlign: "left" }}>
        External invoice identifier.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_type">invoice\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        purchase, refund, renewal, immediate\_change, termination, credit, gift\_card, write\_off, external\_refund, carryforward\_credit, carryforward\_gift\_credit, usage\_correction, import
      </td>

      <td style={{ textAlign: "left" }}>
        This refers to the origin of the invoice. The primary invoice possesses a 'purchase' type. Negative invoices generated due to refunds or voids to offset the initial one have a 'refund' type. Other invoice types become accessible when the Credit Invoices feature is activated. Detailed descriptions can be found in the [invoice origins section](/docs/invoices#section-origins).
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_doc_type">invoice\_doc\_type</span>
      </td>

      <td style={{ textAlign: "left" }}>
        legacy, charge, credit
      </td>

      <td style={{ textAlign: "left" }}>
        This column indicates the document type of the invoice. Before activating the Credit Invoices feature, all invoices bear the 'legacy' type. Post activation, the invoices are categorized as either 'charge' or 'credit'.
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        <span id="invoice_date">invoice\_date</span>
      </td>

      <td style={{ textAlign: "left" }}>
        2019-07-19 12:01:33 PST
      </td>

      <td style={{ textAlign: "left" }}>
        The date and time the invoice creation was attempted. The inception date for this export is July 1, 2019.
      </td>

      <td style={{ textAlign: "left" }}>
        timestamp
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        invoice\_api\_id
      </td>

      <td style={{ textAlign: "left" }}>
        e28zov4fw0v2
      </td>

      <td style={{ textAlign: "left" }}>
        Invoice API ID
      </td>

      <td style={{ textAlign: "left" }}>
        string
      </td>
    </tr>
  </tbody>
</Table>

# Version changelog

### Version 2 - 2/5/2025

* Addition of `invoice_api_id`
