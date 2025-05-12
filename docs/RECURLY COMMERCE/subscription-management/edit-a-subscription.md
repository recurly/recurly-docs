---
title: Edit a customer subscription
excerpt: >-
  Step-by-step instructions for merchants to modify any aspect of an active
  subscriber’s contract—from status and contact info to billing cadence,
  pricing, add-ons, shipping, and cancellation—while preserving continuity.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The **Edit a Customer Subscription** screen in Recurly Commerce empowers you to manage every facet of an individual subscriber’s contract in real time: update their status, contact details, next-billing date, frequency, pricing, discounts, add-ons, shipping and more, or pause, skip, cancel, and even re-activate—all without code.

### Prerequisites & limitations

* The subscriber must already have an active contract.
* Email address changes require Recurly support intervention.

# Definition

Editing a subscription contract lets you tailor an individual customer’s upcoming renewals and deliveries—updating their billing schedule, quantities, product selections, pricing, discounts, shipping, and status—while existing subscribers continue uninterrupted.

# Key benefits

* **Immediate adjustments**: Apply changes on the spot for any single subscriber’s contract.
* **Subscriber retention**: Pause, skip, or modify schedules to keep customers engaged and satisfied.
* **Personalized service**: Offer one-off add-ons, custom discounts, and gifting directly on their contract.

# Key detail

## Accessing a subscriber’s contract

1. **Go** to **Customers** → **Active** (or **Inactive**) tab.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2465e345e7995b90ec60b3bea0fef15c2ca88a23c915655eef7adc34934d5667-image.png" />

2. **Find** the subscriber in the list and click anywhere on their row.
3. The contract detail page opens, showing name, email, phone and status badge.

**Statuses**:

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e80e529203b09b3af6e8d56445a200a4773351f95fcdb6b8ffb7ffecb7f332ef-image.png" />

* **Active:** This means the contract is active with no issues found.
* **Inactive:** This means the contract is cancelled.
  * (**Click** the “Reactivate” button to reactivate a subscription contract)
* **Failed (in dunning):** This means the contract’s payment method is currently being re-tried through a process called dunning.
  * (Pause and unpause the contract to stop dunning and bring the contract back to an active state)

***

## Edit Phone Number

1. In the contract header, click the ✎ icon beside **Phone**.

<Image align="center" src="https://files.readme.io/43753f0a143cc6e1a870512991dfa6e3a98fd54bba777aad5cca057c7ea4e48b-image.png" />

2. Enter the new number and click **Save**.

***

<br />

## Edit Email

> **Note**: Email changes require support assistance. Contact [support@recurly.com](mailto:support@recurly.com).

Email addresses are locked to the contract and power the one-time-password portal. If you need to update a subscriber’s email, our support team can guide you through the process.

***

## Set Delivery / Renewal Date

Adjust when this subscriber’s payment method is charged—and all future renewals follow.

1. **Click** **Set Delivery**.\
   ![](https://files.readme.io/61803eae4434fadd437f9dc14b0a618e728e2c477154f486f49c9ac17fa25049-image.png)
2. **Select** your new billing date.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/7259ddf8ee27f3bbaa4f49daffa6d0dd8d1f12f5eaf8fab59aef194dd341aa45-image.png" />

3. **Click** **Update** to apply.

***

## Process Now

Charge the subscriber immediately—no waiting for the next scheduled date.

1. **Click** **Process Now** to trigger an on-demand payment.\
   ![](https://files.readme.io/92b011924d257926ba60fb8cefac655dc9b58423708c1a1df11f4e710b411444-image.png)

***

## Edit Frequency

Change how often this subscriber is billed going forward.

1. **Click** **Edit Frequency**.\
   ![](https://files.readme.io/f0729cd660a0ff7c669868be2ba46717e3bcfaae933a0ca3d4843be81a060dbb-image.png)
2. **Choose** a new cadence from the list of your configured options. ![](https://files.readme.io/ec3a998f6e8a30bdf5522e4ed496394bf33e8a9e684ce2fb3aef5dbe0b58205d-image.png)
3. **Click** **Update** to save—it applies to all upcoming renewals.

***

## Change Price

1. Click the pencil icon beside **Price**.
2. Enter a new subscription price (this contract only).
3. Click **Save**.

***

## Pause Contract

1. Click **Pause**.
2. Choose indefinite or a set number of deliveries (if configured).
3. Click **Confirm**.

***

## Skip Next

1. Click **Skip Next**.
2. Select one or more upcoming orders to skip.
3. Click **Confirm**—renewals resume afterward.

***

## Update Quantity

1. Click the quantity field.
2. Enter the new quantity for future renewals.
3. Click **Save**.

***

## Apply Coupon / Discount Code

1. In the **Discounts** section, click **Add Coupon**.
2. Enter a valid Shopify coupon code.
3. Click **Apply**.

***

## Swap Product

1. In the **Products** section, click **Swap** next to the SKU.
2. Select a replacement SKU from your configured swap list.
3. Click **Swap & Save**.

***

## Add-On Subscription Product

1. Click **Add Subscription Add-On**.
2. Choose an add-on SKU to include on every renewal.
3. Click **Add & Save**.

***

## One-Time Add-On Product

1. Click **Add One-Time Add-On**.
2. Select the SKU and specify which upcoming renewal.
3. Click **Add & Save**.

***

## Cancel Subscription

1. Click **Cancel Subscription**.
2. Confirm in the pop-up to stop all future renewals and set status to **Inactive**.

> **Note**: Cancellation is immediate and irreversible; active subscribers will no longer renew.

***

## Reactivate a Subscription

1. Switch to the **Inactive** tab and locate the subscriber.
2. Click **Reactivate** next to their contract.
3. Confirm in the pop-up—status reverts to **Active** and it returns to the **Active** list.

***

## Update Shipping Information

1. In **Shipping Information**, click ✎ **Edit**.
2. Modify name, address, city, state, postal code, country.
3. Click **Update**.

***

## Update Billing Information

1. Click **Send reset email** in the **Billing Information** section.
2. Subscriber receives a link to update their payment details via Shopify Payments.
3. Once updated, Recurly Commerce syncs the new billing info automatically.

> **Note**: Merchants cannot directly edit payment details for security and compliance.

***

## Create a New Subscription Contract

1. Go to **Subscriptions** → **Create Contract** (top right).
2. Only available for customers who already have a contract under that email.
3. Complete the form and click **Create**.

> **Note**: Shopify merges all subscriptions by email; to create a separate contract, the customer must use a different email.

***

Still need help? Contact [support@recurly.com](mailto:support@recurly.com).