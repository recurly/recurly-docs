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

Email addresses are locked to the contract and power the one-time-password portal. If you need to update a subscriber’s email, our support team can guide you through the process.

> **Note**: Email changes require support assistance. Contact [support@recurly.com](mailto:support@recurly.com).

***

## Set delivery / renewal date

Adjust when this subscriber’s payment method is charged—and all future renewals follow.

1. **Click** **Set Delivery**.

![](https://files.readme.io/61803eae4434fadd437f9dc14b0a618e728e2c477154f486f49c9ac17fa25049-image.png)

2. **Select** your new billing date.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/7259ddf8ee27f3bbaa4f49daffa6d0dd8d1f12f5eaf8fab59aef194dd341aa45-image.png" />

3. **Click** **Update** to apply.

***

## Process now

Charge the subscriber immediately—no waiting for the next scheduled date.

1. **Click** **Process Now** to trigger an on-demand payment.

![](https://files.readme.io/92b011924d257926ba60fb8cefac655dc9b58423708c1a1df11f4e710b411444-image.png)

***

## Edit frequency

Change how often this subscriber is billed going forward.

1. **Click** **Edit Frequency**.

![](https://files.readme.io/f0729cd660a0ff7c669868be2ba46717e3bcfaae933a0ca3d4843be81a060dbb-image.png)

2. **Choose** a new cadence from the list of your configured options.

<Image align="center" width="60% " src="https://files.readme.io/ec3a998f6e8a30bdf5522e4ed496394bf33e8a9e684ce2fb3aef5dbe0b58205d-image.png" />

3. **Click** **Update** to save—it applies to all upcoming renewals.

***

## Change price

Update the per-renewal cost for this subscriber’s contract—future renewals will charge the new amount without affecting any other subscribers.

1. **Click** **Change Price**.

![](https://files.readme.io/66dccf75868d9cfbdadeb6b6b0b2d8815344bbfb6bddd1a1e817bd7ef71104dd-image.png)

2. **Enter** the new subscription price for this contract only.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/fe50ad810dc5fbf937a342df8c10e821d6df2153ac97849401f1566abf5cd8fa-image.png" />

3. **Click** **Apply** to confirm the new price.

***

## Pause contract

Temporarily halt a subscriber’s renewals—either indefinitely or for a predefined number of deliveries.

1. **Click** **Pause**.

![](https://files.readme.io/ba39e69e836b3f2ec5cbd8111890d03b648ec99a34df3b52bb21a18729c8b914-image.png)

1. **Choose** between pausing indefinitely or specifying a number of upcoming deliveries (if your plan supports it).

***

## Skip next

Skip one or more upcoming orders without cancelling the subscription; the schedule will pick up after the skipped delivery.

1. **Click** **Skip Next**.

![](https://files.readme.io/00bfc039d87d36923442af5752dcee8753ee4e8047a2c44907ad6a08217b0c17-image.png)

2. **Select** the orders you want to skip.
3. **Click** **Confirm**—all future renewals resume once those orders have been skipped.

***

## Update quantity

Adjust the number of items your subscriber receives on each renewal.

1. **Click** **Update Quantity**.

![](https://files.readme.io/5738bf05f51b78bdaf844980df316ea58e44511abfd7c7198b3e5b81c586957b-image.png)

2. **Enter** the new quantity for all future deliveries.

<Image align="center" width="80% " src="https://files.readme.io/c32aa566d8bdffa6d126c8215782eb99100e3b08214349767312b9ed429aedfd-image.png" />

3. **Click** **Apply** to save the updated quantity.

***

## Apply coupon / discount code

Attach a Shopify coupon code directly to a subscriber’s contract to apply promotional pricing on all future renewals.

1. **Click** **Coupon Code**.

![](https://files.readme.io/b78fd515467a4eb3b15ec8f1dbf2f2f15ebe855f74996bd37c7e2feb05903309-image.png)

2. **Enter** a valid Shopify coupon code.

<Image align="center" width="80% " src="https://files.readme.io/3d27a32157260922d8e6b844fb81e6a7ddf0f86bf0096860c03b4c990a9be836-image.png" />

3. **Click** **Apply** to activate the discount for this subscription contract.

***

## Swap product

Replace the current subscription item with a different SKU you’ve pre-configured in your plan’s swap list.

1. **Click** **Swap Product**.

![](https://files.readme.io/6fe491aacae79f89409287b6d2a317c872fe801c04072de41b2a7c44e68775d6-image.png)

2. **Select** a replacement SKU from the enabled swap list.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6f7585a8dd52437d4f1b2785960e99b7aa9178db28cd74584ad48016dc43cf7b-image.png" />

3. **Click** **Swap & Save** to update the contract.

***

## Add-on subscription product

Include an extra product on every delivery to boost order value and subscriber satisfaction.

1. **Click** **Add-on Subscription Product to all Deliveries**.

![](https://files.readme.io/1b83551dc32b5ad2c958886d115fec4b2aecb8ac741b6d6591e762815a333e36-image.png)

2. **Choose** the add-on SKU to include on each renewal.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/cf71f14540e667cd3dff6dfdd61e66be3996e0b8d7767e3152389d2172e5220c-image.png" />

3. **Save** your changes to lock in the add-on for all future deliveries.

***

## One-time add-on product

A subscription product will be added once to a specific renewal/delivery of choice.

1. **Click** **Select One-Time Add-On**.

![](https://files.readme.io/d51f0e48131a349e29a271bb85fade171d8d1750a38490accbe11dc154141d21-image.png)

2. **Select** the SKU and specify which upcoming renewal.

![](https://files.readme.io/ad267487bf391edaebfbd9b362b11fb01fd835b5c482844b1a154e0aa126ab1e-image.png)

3. **Save** your changes.

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