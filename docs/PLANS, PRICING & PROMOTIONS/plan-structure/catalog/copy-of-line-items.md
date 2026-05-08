---
title: Copy of Line items
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
* **Payments compliance**: Sent to gateways in various cases, such as Klarna usage, and lower interchange rates in certain cases. Ensure what you are creating for line items is descriptive and accurate.

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

Make use of the best practices below for proper tracking of line items as well as Commercial Enhanced Data Program (CEPD) compliance for L2 and L3 data. CEDP is a program from Visa that validates transaction data under a new (as of 2025) set of standards and merchants can be rewarded for compliant transactions with a reduction in interchange rates.

Ensure your line items and other descriptive elements included in your invoices are compliant, as line items are sent to gateways in certain cases. This can also be applied to HIPAA compliance -- do not include PHI data for your customers in Invoice descriptions, product codes, plan names, or line item product data if the gateway you use is not also HIPAA compliant.

<Cards columns={4}>
  <Card title="Be specific" icon="fa-check-circle">
    Use clear, descriptive names rather than generic labels like “Item 1” or “Charge.”
  </Card>

  <Card title="Match the product" icon="fa-apple-alt">
    If you sell fruit, list “Apple,” “Orange,” and “Banana” rather than “Fruits.”
  </Card>

  <Card title="Avoid business names" icon="fa-building">
    Don’t repeat your company name in item names or descriptions (e.g., “Fruit Shop Items”).
  </Card>

  <Card title="Skip single-character names" icon="fa-font">
    Avoid names that are a single character or all symbols—they confuse customers.
  </Card>

  <Card title="Where descriptions appear" icon="fa-file-invoice">
    Subscriber invoices, Hosted Account Management pages, and Hosted Invoice PDFs.
  </Card>

  <Card title="Character limit" icon="fa-text-width">
    Descriptions must be 255 characters or fewer.
  </Card>

  <Card title="Special character tip" icon="fa-info-circle">
    Check with your payment gateway about any restrictions on special characters.
  </Card>
</Cards>