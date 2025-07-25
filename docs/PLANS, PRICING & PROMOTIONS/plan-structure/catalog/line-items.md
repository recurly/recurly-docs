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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Line items can be named freely but should avoid special characters unless confirmed with your payment gateway.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Invoices only display the <strong>first 500 line items</strong> in the Admin Console, Hosted Invoice, and PDF views.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Full line item details (beyond 500) must be accessed via the <a className="text-blue-500! dark:text-blue-300!" href="https://docs.recurly.com/docs/adjustments-exports" target="_blank">Adjustments Export</a>.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

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

### Description and Naming field guidance

* Avoid generic item names and descriptions like "Charge" or "Item 1"—these will disqualify transactions from proper regulatory compliance or customer understanding. The recommendation is to explicitly name the item that is being purchased. Instead of a single line item named 'Fruits', offer three items named 'Apple', 'Orange', and 'Banana'.
* Avoid item names that are similar or exactly the name of your business name. If you are a Fruit Shop, do not name items 'Fruit Items', or provide item descriptions such as 'Fruit Shop Items' or 'Fruit Products'.
* Avoid item names or descriptions that are single characters or are all special characters.
* The **Description** is displayed on:

  * Subscriber invoices
  * [Hosted Account Management Pages](https://docs.recurly.com/docs/hosted-pages)
  * Hosted Invoice PDFs
* **Limit**: 255 characters
* **Tip**: Always validate special characters with your gateway provider, as some may impose restrictions.