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

### Invoice line items

Every invoice line item displays these columns:

* **Date**
* **Description**
* **Quantity**
* **Price**
* **Discount** (when applied)
* **Subtotal**
* **Tax** (including rate, when applicable)
* **Total** (only shown if tax is applied)

> **Note:** Invoices in the Admin Console, the Hosted Invoice page, and PDF format will show only the first 500 line items. However, the **Subtotal**, **Tax**, and **Total** always reflect the full set of line items, even those beyond the first 500.
>
> To download all line items, use the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports).

***

### Description and naming guidelines

* **Be specific.** Use clear, descriptive names rather than generic labels like “Item 1” or “Charge.”
* **Match the product.** If you sell fruit, list “Apple,” “Orange,” and “Banana” rather than a single line called “Fruits.”
* **Avoid business names.** Don’t repeat your company name in item names or descriptions (e.g., “Fruit Shop Items”).
* **Skip single-character or symbol-only names.** These can confuse customers and run afoul of compliance rules.
* **Where descriptions appear:**

  * Subscriber invoices
  * Hosted Account Management pages
  * Hosted Invoice PDFs
* **Character limit:** Descriptions must be 255 characters or fewer.
* **Tip:** Check with your payment gateway about any restrictions on special characters.