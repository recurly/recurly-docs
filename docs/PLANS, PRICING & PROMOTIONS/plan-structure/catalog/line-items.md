---
title: Line items
excerpt: >-
  Learn how line items are displayed on invoices and how they impact totals,
  taxes, and hosted page displays.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

#### Prerequisites & Limitations

* Line items can be named freely but should avoid special characters unless confirmed with your payment gateway.
* Invoices only display the **first 500 line items** in the Admin Console, Hosted Invoice, and PDF views.
* Full line item details (beyond 500) must be accessed via the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports).

## Definition

Line items are individual charges or components listed on an invoice, each representing a product, service, or adjustment applied to a transaction. These can be associated with subscriptions or stand-alone charges.

## Key benefits

* **Clear billing breakdown**: Provides transparency to subscribers by itemizing all charges.
* **Supports stand-alone items**: Line items don't need to be tied to a subscription to be invoiced.
* **Displayed across channels**: Visible in Admin Console, PDFs, Hosted Invoice, and Hosted Account Management.

## Key details

### Invoice line item table columns

Each invoice line item includes the following columns:

* **Date**
* **Description**
* **Quantity**
* **Price**
* **Discount** (if applicable)
* **Subtotal**
* **Tax** (if applicable, including rate)
* **Total** (only shown if tax is applicable)

> **Note:** Invoices displayed in the Admin Console, Hosted Invoice, and PDF will truncate after the first 500 line items. Subtotal, tax, and total will still reflect the **sum of all line items**, including those not displayed.

To access line items beyond the first 500, use the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports).

### Description field guidance

* Avoid generic descriptions like "Charge" or "Item 1"—these may disqualify transactions from proper reporting or customer understanding.
* The **Description** is shown on:

  * Subscriber invoices
  * [Hosted Account Management Pages](https://docs.recurly.com/docs/hosted-pages)
  * Hosted Invoice PDFs
* **Limit**: 255 characters
* **Tip**: Always validate special characters with your gateway provider, as some may impose restrictions.