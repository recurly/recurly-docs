---
title: Calendar billing
excerpt: >-
  Streamline your invoicing process by consolidating multi-product invoicing
  charges into a single invoice with Calendar Billing.
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

This feature is only available to customers on the Professional or Elite subscription plan.

### Prerequisites

- Calendar Billing must be enabled by Recurly Support before use. Contact [support@recurly.com](mailto:support@recurly.com) to request activation
- A valid payment method must be on file for subscriptions that will be consolidated into aggregate invoices

### Limitations

- Aggregate Invoices are only supported for monthly (minimum 30 days), quarterly, or annual billing cycles
- Subscriptions activated within 24 hours of an aggregate renewal date will be invoiced separately
- Changing the business entity on a subscription is not available for immediate subscription changes
- The Account Bill Date is read-only and cannot be changed directly — adjustments must be made at the subscription level via API
- Calendar billing and renewal alignment are not supported on annual plans with a 1-year billing period. They are supported if a 1-year plan has its billing period broken into 12 months
- Subscription-level entity assignment is not available for purchase calls made through Recurly Checkout
- Payment Methods that are mandate-driven will not be calendar aligned if they do not share a mandate. Shared mandates will only occur of the subscription was created in the same customer session, for example, signing up for multiple subscriptions within a single invoice. Otherwise, these types of subscriptions will be excluded.

***

# Definition

Calendar Billing is a Recurly feature that consolidates multiple subscription invoices for a customer into a single, unified invoice. It's especially useful for businesses whose customers hold multiple subscriptions at the same time.

Recurly offers two approaches depending on your business model:

- **Aggregate Invoices** — merges subscriptions with the same bill date into one invoice, without enforcing proration. Best for physical goods merchants.
- **Aligning Renewals** — prorates new subscriptions to synchronize with a shared account bill date, so all subscriptions renew together. Best for digital goods and services.

***

# Key benefits

- **Simplified invoicing:** Reduce the number of invoices generated, making payment management easier for you and your customers.
- **Enhanced customer experience:** Customers receive one clear, consolidated invoice instead of multiple separate ones.
- **Flexible options:** Choose Aggregate Invoices, Aligning Renewals, or both — depending on what fits your business model.

***

> **About proration**
>
> When active coupon redemptions are applied to new charges, Recurly prorates any fixed-amount discounts at the same rate as the charge. For example, if a customer is 50% through their billing cycle and being charged 50% of the plan price, they'll also receive 50% of the fixed discount amount. Percentage discounts are automatically prorated because they're calculated as a percentage of an already-prorated amount.
>
>
> <Image src="https://files.readme.io/736422361c55f851bdda94ecfb515c19003bad390b37346e06c97ee3bb63316c-image.png" align="center" width="75%" border={true} />
>
>
> It's not possible to apply a fixed-amount coupon redemption without proration in an immediate change. If you need this, consider using custom credits instead — and contact [Recurly Support](https://support.recurly.com/) to express your interest in this capability.

***

# Key details

## Aggregate invoices

Aggregate Invoices merges subscriptions that share the same bill date into a single invoice. It's ideal for customers who have multiple subscriptions billed on the same day.

### Eligible subscriptions

For subscriptions to be combined into one renewal invoice, they must:

- **Share the same bill date** — down to the second. The best way to achieve this is by purchasing [multiple subscriptions](doc:multiple-subscriptions) together
- **Use one payment method** — since the invoice merges all charges, it must be paid with a single method
- **Use the same collection method** — all subscriptions must be either manual or automatic billing. Subscriptions with different methods will be invoiced separately
- **Follow a supported billing cadence** — monthly (minimum 30 days), quarterly, or annual
- **Have the same shipping address** — subscriptions with different shipping addresses result in separate invoices

> **Note:** Subscriptions activated within 24 hours of an aggregate renewal date will be invoiced separately. Future-start-date subscriptions that activate on the same day as an aggregate renewal will activate simultaneously with other subscriptions and bill together.

### Editing the account bill date

Once Aggregate Invoices is activated, Recurly combines all subscriptions sharing a bill date onto one invoice. Manual overrides of the site default aren't possible within a group of aggregated subscriptions. To invoice a subscription separately, adjust its bill date to differ from the account's.

To move all subscriptions on an account to a new bill date, use the [postpone](https://dev.recurly.com/docs/postpone-subscription) feature via API.

### Expiring or canceled subscriptions

Subscriptions in their last billing cycle, or those canceled before the bill date, won't be included in the renewal invoice.

### Promotional subscriptions renewing or expiring

Promotional subscriptions — those purchased with a [gift card](https://docs.recurly.com/v1.0/docs/gift-cards#section-billing-information) or using [cardless free trials](https://docs.recurly.com/v1.0/docs/plans#section-cardless-free-trials) — will expire if there's no valid payment method or sufficient credit/coupons to cover the total cost.

If promotional and non-promotional subscriptions are set to bill together and there's no payment method, gift card subscriptions will expire and cardless trial subscriptions will enter dunning.

> **To enable Aggregate Invoices:** Contact [support@recurly.com](mailto:support@recurly.com) to check eligibility. Once activated, subscriptions with the same renewal date will be combined into a single invoice.

***

## Aligning renewals

Aligning Renewals also consolidates subscriptions into one invoice, but does so by adjusting a new subscription's bill date to match the account's established [bill date](#bill-date). This results in a one-time prorated invoice, after which all subscriptions renew together.

> **To enable Aligning Renewals:** Contact [support@recurly.com](mailto:support@recurly.com) to check eligibility. Once activated, new subscriptions will align to the account's bill date, or set the bill date if the account is new.

### Bill date

The account bill date determines when all subscriptions on an account renew together. It's set by the account's first non-trial invoice.

- For existing accounts when the feature is activated, the oldest subscription's bill date becomes the account bill date
- For new customers, the bill date is set by the first non-trial invoice after activation
- A $0 invoice still counts as a non-trial invoice
- If a gift card or promotional credit covers the full cost, that invoice date still sets the bill date

The bill date is visible on the Accounts page and displays down to the second.


<Image src="https://files.readme.io/2bc895e89d3072a1a3a527716dd432bcf813ff9acd0699f170dd75b3b8ad3afa-image.png" align="center" width="75%" border={true} />


For subscriptions billed on the last day of the month, if that day doesn't exist in the following month, the last day of that month is used (e.g., January 31st → February 28th).

The table below shows how bill dates are determined based on subscription start dates:

| Subscription started | First renewal | Bill date |
| :------------------- | :------------ | :-------- |
| Jan 31               | Feb 29        | 29        |
| Feb 29               | March 31      | 31        |
| March 31             | April 30      | 30        |
| April 30             | May 31        | 31        |
| May 31               | June 30       | 30        |
| June 30              | July 31       | 31        |
| July 31              | Aug 31        | 31        |
| Aug 31               | September 30  | 30        |
| September 30         | October 31    | 31        |
| October 31           | November 30   | 30        |
| November 30          | December 31   | 31        |
| December 31          | Jan 31        | 31        |

### Editing a bill date

The account bill date is read-only and can't be changed directly. However, you can adjust the bill date of a specific subscription or group of subscriptions via API using the [postpone](https://dev.recurly.com/docs/postpone-subscription) feature.

Once all subscriptions share the same bill date, they'll renew on a single invoice. If you adjust a subscription's bill date, it won't automatically re-align to the account's original bill date — it will renew separately unless Subscription Alignment is enabled.

When Subscription Alignment is on, the account bill date is cleared once the last active subscription expires. If a new subscription is created with no other active subscriptions, the account bill date is updated to match the new subscription's creation date.

> **Note:** The Subscription Alignment setting is only available if your site has Aligning Renewals enabled.

### Clearing a bill date

An account will always have a bill date while subscriptions are active. To clear it, use the [Subscription Alignment](https://docs.recurly.com/recurly-subscriptions/docs/invoice-settings#subscription-alignment) feature when there are no active subscriptions.

### How alignment works

When a new subscription is purchased on an account with a bill date, Recurly identifies the subscription's regular billing cycle start and end dates, then adjusts the bill date to match the account's.

#### Non-trial subscriptions

A new non-trial subscription will either prorate to the account's existing bill date, or set the account's bill date if none exists. If a subscription is created with a past date and the account has a bill date set, the invoice will use the account's bill date as the due date and prorate accordingly.

**Example: Monthly + monthly**

An existing customer has a monthly Silver plan ($5) billing on the first of each month. They buy a monthly Gold plan ($10) on March 15th.

- Gold's regular billing cycle would be March 15th – April 15th
- Gold's bill date is adjusted to April 1st to match the account's bill date
- A prorated Gold invoice of $5 is generated for March 15th – April 1st
- The April 1st invoice will include both Silver and Gold ($15 total)

**Example: Monthly + annual**

An existing customer has a monthly Silver plan billing on the 15th. They buy an annual Gold plan on January 10th, 2017.

- Gold's regular billing cycle would be January 10th, 2017 – January 10th, 2018
- Gold's bill date is adjusted to December 15th, 2017 to align with the account's bill date
- Gold prorates for January 10th, 2017 – December 15th, 2017
- Both subscriptions will appear on the December 15th, 2017 invoice

**Example: Annual + annual**

An existing customer has an annual Gold subscription starting January 10th, 2017.

- If they buy a second annual subscription **before** February 10th, 2017, it will align to the same January 10th, 2018 renewal
- If they buy a second subscription **after** February 10th, it will renew one year after its own start date and won't align to the existing subscription

> **Note:** A new annual subscription only aligns with an existing annual subscription if purchased within one month of the original subscription's start date. To align after that window, use the [postpone](https://docs.recurly.com/docs/postpone-subscription) feature.

### Upgrades and downgrades

When an immediate subscription change includes a billing period change, the subscription resets to the current date and must realign. As long as Aligning Renewals is active, any immediate subscription change will consider the account's bill date and maintain alignment.

**Example: Monthly upgrade to annual**

An existing customer has monthly Bronze and Silver plans billing on the first of each month. They upgrade Silver to an annual Gold plan on January 15th.

- Gold's regular billing cycle would be January 15th – January 15th of the following year
- Gold's bill date is adjusted to January 1st to align with the account's bill date
- A prorated Gold invoice is generated for January 15th – January 1st
- Both subscriptions will appear on the January 1st invoice

Immediate changes that don't involve a billing period change won't require proration, since the current billing period and alignment are maintained.

### Expiring or canceled subscriptions

Subscriptions in their last billing cycle, or those canceled before the bill date, won't be included in the next invoice — the same behavior as Aggregate Invoices.

### Promotional subscriptions renewing or expiring

The same logic applies as with Aggregate Invoices. Promotional subscriptions expire if there's no valid payment method or sufficient credit. If promotional and non-promotional subscriptions are set to bill together without a payment method, gift card subscriptions will expire and cardless trial subscriptions will enter dunning.

***

## Trial subscriptions

A few important rules apply when trial subscriptions are involved:

- If an account has no bill date (new customer) and they buy a trial subscription, the bill date won't be set until the trial ends and the first non-trial invoice is generated
- If a new customer buys multiple trial subscriptions of different lengths, the one that ends first sets the account bill date

### Trial subscription without a bill date

**Example:**

A new customer buys a 7-day trial subscription on January 15th.

- The trial ends January 22nd and the subscription enters its regular billing cycle
- The account bill date is set to January 22nd
- All subsequent non-trial subscription purchases or activations will align to this date

### Trial subscription with an existing bill date

When a customer with an existing bill date purchases a new trial subscription, the subscription aligns to the account's bill date once the trial ends — resulting in a one-time prorated invoice. At the next bill date, all subscriptions renew together.

**Example:**

An existing customer has a bill date of the 10th. They buy a monthly Gold plan with a 7-day trial on February 15th.

- The trial ends February 22nd and the first non-trial invoice is generated
- Gold's regular billing cycle would be February 22nd – March 22nd
- Gold's bill date is adjusted to March 10th to align with the account's bill date
- A prorated Gold invoice is generated for February 22nd – March 10th
- The March 10th invoice will include both subscriptions

***

## Renewal emails

When automatic email templates are enabled on your site or plans, the following templates support renewal-related emails. Each email is sent once per subscription if the template is enabled at the site level and at least one subscription plan has the automatic email enabled:

- Renewal Reminder
- Payment Confirmation
- Invoice Past Due

***

# Enabling calendar billing

Contact [support@recurly.com](mailto:support@recurly.com) to request activation. You have three configuration options:

**Option 1 — Both Aggregate Invoices and Aligning Renewals (recommended)**
All monthly subscriptions created going forward will adopt the same bill date and invoice cadence as the first subscription on a given account. All subscriptions will appear on a single invoice.

**Option 2 — Aligning Renewals only**
All subscriptions with matching billing intervals will be billed on the same date as the account's first subscription, but won't be consolidated onto a single invoice.

**Option 3 — Aggregate Invoices only**
Subscriptions with the exact same period end date (down to the second) will appear on a single invoice. This gives you full control over which subscriptions align for each customer account.

### Aligning renewals setup

1. Review the account's current bill date. If none exists, it will be set by the first non-trial invoice
2. Ensure new subscriptions or those exiting a trial align with the account's bill date
3. Save your settings

### Managing bill dates

1. Navigate to the **Accounts** page
2. Locate the **Bill Date** section to view each account's bill date
3. To adjust the bill date for specific subscriptions, use the [postpone](https://dev.recurly.com/docs/postpone-subscription) feature via API

### Handling promotional and trial subscriptions

1. For promotional subscriptions, confirm there's a valid payment method or sufficient credits/coupons on file
2. For trial subscriptions, monitor the trial end date — the subscription will align to the account's bill date or set a new one when the trial ends

### Setting up renewal emails

1. Navigate to **Email Templates** in your Recurly dashboard
2. Enable the **Renewal Reminder**, **Payment Confirmation**, and **Invoice Past Due** templates
3. Customize the content as needed and save

### Review and monitor

After enabling Calendar Billing, monitor your aggregated invoices and aligned renewals to confirm everything is working as expected. For any issues or discrepancies, contact [support@recurly.com](mailto:support@recurly.com).
