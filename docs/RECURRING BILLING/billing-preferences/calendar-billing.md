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

# Definition

Calendar Billing is a feature in Recurly that allows businesses to consolidate multiple invoicing charges for a customer into one unified invoice. This is especially beneficial for businesses whose customers have multiple subscriptions.

# Key benefits

* **Simplified invoicing**: Reduce the number of invoices generated, making it easier for both businesses and customers to manage payments.
* **Enhanced customer experience**: Customers receive a single, consolidated invoice, leading to clearer communication and fewer queries.
* **Flexible options**: Choose between aggregate invoices for physical goods or aligning renewals for digital goods, depending on your business model.

> 📘 About proration
>
> When active coupon redemptions are applied to new charges, Recurly will prorate any fixed amount discounts following the same proration rate of the charge. Recurly prorates fixed amount discounts in an immediate subscription change because the discount represents the time of the cycle. If the customer is 50% through their cycle and only going to be charged 50% of the plan price, we want to ensure that they only get 50% of the discount amount. Percentage discounts automatically represent a prorated portion because they are a percentage of an already prorated amount.
>
> <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/736422361c55f851bdda94ecfb515c19003bad390b37346e06c97ee3bb63316c-image.png" />
>
> It is not possible to have a fixed amount coupon redemption not prorate when applied in an immediate change. If you require this use case, please look at custom credits as an alternative and write in to <a href="https://support.recurly.com/" target="_blank">Recurly Support</a> to express your interest in this feature.

# Background

For businesses offering multiple subscriptions, it's often desirable to bill these subscriptions together. Depending on your business model, Recurly provides tailored solutions:

* **Aggregate Invoices**: This feature consolidates all subscriptions on an account with the same billing date into one invoice. It's particularly beneficial for merchants selling physical goods as it doesn't enforce proration like the Aligning Renewals feature. Learn more about [Aggregate Invoices](https://docs.recurly.com/docs/calendar-billing#section-aggregate-invoices).

* **Aligning Renewals**: Aligning subscriptions involves prorating for those starting immediately or transitioning from a trial period to synchronize with a unified account billing date. This ensures that all subscriptions renew simultaneously on a single invoice, making it a preferred option for digital goods and services companies. Dive deeper into [Aligning Renewals](https://docs.recurly.com/docs/calendar-billing#section-alignment).

# Aggregate Invoices

Aggregate Invoices is a feature that merges subscriptions with the same billing date into one invoice. It's ideal for businesses whose customers frequently have multiple subscriptions billed on the same day.

#### Eligible subscriptions

For subscriptions to be combined into one renewal invoice, they must:

* **Share the same bill date**: Precisely down to the second. Achieve this optimally by purchasing [Multiple Subscriptions](doc:multiple-subscriptions) together.
* **Use one payment method**: As the invoice merges all charges, it must be paid using a single method, like a credit card.
* **Have one collection method**: All subscriptions in an aggregate invoice should have the same collection method (either manual or automatic). Those with different methods will be invoiced separately.
* **Follow a specific billing cadence**: Supported only for monthly (minimum 30 days), quarterly, or annual subscription billing cycles.
* **Same Shipping Address**: Subscriptions with different shipping addresses will result in separate invoices.

> 🚧 **Note**:
>
> Subscriptions activated within 24 hours of an aggregate invoice's renewal date will be invoiced separately. If future start date subscriptions activate on the same day as an aggregate renewal invoice, they will activate simultaneously with other subscriptions to bill together. In addition, differing shipping addresses will result in separate invoices.

#### Editing Account Bill Date

Once Aggregate Invoice is activated, Recurly will try to combine all subscriptions with the same bill date onto one invoice. Manual overrides of your site default aren't possible within a group of aggregated subscriptions. However, you can cause separate invoices by adjusting the subscription's bill date to be different from the account's and it will be invoiced separately. Adjusting all account subscriptions to a new bill date can be done via the [postpone](https://dev.recurly.com/docs/postpone-subscription) feature in the API.

#### Expiring or canceled subscriptions

Subscriptions in their last billing cycle or those canceled before the bill date won't be included in the renewal invoice.

#### Promotional subscriptions renewing or expiring

Promotional subscriptions, like those bought with a [gift card](https://docs.recurly.com/v1.0/docs/gift-cards#section-billing-information) or [cardless free trials](https://docs.recurly.com/v1.0/docs/plans#section-cardless-free-trials), will expire if there's no payment method or enough credit/coupons to cover the total cost of all promotional subscriptions.

If promotional and non-promotional subscriptions are set to bill together and there's no payment method, subscriptions initiated with a gift card will expire, and the cardless trial subscription will enter dunning.

> 📘 **To Enable Aggregate Invoices**:
>
> Reach out to [support@recurly.com](mailto:support@recurly.com) to check eligibility for this feature on your site. Once activated, subscriptions with the same renewal date will be combined into a single invoice.

# Alignment

Alignment, like Aggregate Invoices, consolidates subscriptions into one invoice. However, it aligns a subscription's bill date if purchased or exiting a trial on a different day from the account's **[bill date](https://docs.recurly.com/v1.0/docs/calendar-billing#section-bill-date)**. This results in a one-time prorated invoice, ensuring the new subscription bills with existing ones on the next bill date.

> 📘 **To Enable Alignment**:
>
> Contact [support@recurly.com](mailto:support@recurly.com) to check eligibility for this feature on your site. Once activated, purchased subscriptions will align to a bill date or set the account bill date if it's a new account.

#### Bill date

Alignment introduces the concept of an account bill date, determining when subscriptions on an account bill together. If there are existing subscriptions when the feature is activated, the oldest subscription's bill date becomes the account's bill date. This means subsequent subscription purchases will align to this date. For new customers purchasing subscriptions after activation, their account bill date is set by their first non-trial invoice.

Once an account has a bill date, future subscription purchases, upgrades, or downgrades will prorate to align with the account's bill date.

The Bill Date can be viewed on the Accounts page, showing the subscription timestamp information down to the second.

![Account Bill Date](https://files.readme.io/2ab1b11-Account_Bill_Date.png "Account Bill Date.png")

#### Assigning a bill date

The account bill date is when an account's subscription(s) are billed. This date is determined by an account's first non-trial invoice, and is set by the date of the first renewal invoice. For instance, if a subscription starts on January 20th, the account's bill date will always be the 20th of the month. A $0 invoice is still considered a non-trial invoice. If a gift card or promotional credit covers the full cost of the non-trial invoice, this date will still be the account's bill date.

For subscriptions with a bill date on the last day of the month, if the day doesn't exist for the next bill date, the last day of the month will be used (e.g., January 31st, next bill date will be February 28th).

For subscriptions bought on the last day of the month, and the bill date on the account is the first day of the month, the invoice amount will be smaller than usual. For instance, a bill date of the 1st and a subscription bought on the 30th will result in a prorated invoice for the 30th-1st. The table below indicates the bill date based on the subscription start date

| Subscription Started | First Renewal | Bill Date |
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

#### Editing a bill date

The **Bill Date** on an account is **read-only** and cannot be changed directly. However, you can adjust the bill date of a **specific subscription** or a **group of subscriptions** via the **API**.

Once all subscriptions on an account share the same bill date, they will bill on a **single invoice**. If you adjust a subscription’s bill date, it will **not automatically re-align** to the account’s original Bill Date and will renew **separately** unless the **Subscription Alignment** setting is enabled.

When **Subscription Alignment** is turned on, the **Account Bill Date** is cleared once the **last active subscription** on an account expires. If a **new subscription** is later created and **no other active subscriptions exist**, the **Account Bill Date** will be updated to match the **new subscription’s created date**.

> **Note:** The **Subscription Alignment** setting is only available if your site has the **Aligning Renewals** feature enabled.

#### Clearing a bill date

An account will always have a permanent bill date. Neither the API nor Admin UI permits changing or clearing the account's bill date.

#### Aligning logic

This section discusses subscription alignment scenarios based on whether there's an established bill date on an account and/or if purchased subscriptions are in trial. When a new subscription is bought on an account with a bill date, we first identify its regular billing cycle start and end dates and then adjust its bill date to match the account's bill date.

#### Non-trial subscriptions

When a non-trial subscription is purchased, its bill date will either prorate to the account's bill date or, if there's no bill date, the non-trial subscription's bill date will be set as the account's bill date.

If a subscription is created with a date in the past and there is calendar alignment on the account with a Bill Date set, the new subscription will use the Bill Date on the invoice for the Due On date and the invoice will be prorated for the Bill Date.

##### Monthly and monthly subscription example

An **existing** customer is subscribed to a monthly Silver subscription ($5) billing on the first of every month. The customer buys a monthly Gold subscription ($10) on March 15th.

* The account bill date is the first of the month, set by Silver's bill date.
* Gold subscription's regular billing cycle would be March 15th - April 15th.
* Gold subscription's bill date of April 15th is adjusted to April 1st to align with the account's bill date.
* A prorated invoice of $5 for Gold is created for the billing period of March 15th - April 1st.
* The next month's invoice on April 1st will include **both** Silver and Gold ($5+$10=$15).

##### Monthly and annual subscription example

An **existing** customer is subscribed to a monthly Silver subscription billing on the 15th of every month. The customer buys an annual subscription to the Gold plan on January 10th, 2017.

* The account bill date is set as the 15th of each month by the Silver subscription.
* Gold annual subscription's regular billing cycle would be January 10th, 2017 - January 10th, 2018.
* Gold annual subscription's bill date of January 10th, 2018 is adjusted to December 15th, 2017 to align with the account's bill date.
* The Gold annual subscription will prorate for the period of January 10th, 2017 - December 15th, 2017.
* The next invoice that will include **both** subscriptions will be on December 15th, 2017.

##### Annual and annual subscription example

An **existing** customer subscribed to an annual Gold subscription on January 10th, 2017 with a bill date of the 10th.

* If the customer buys a second annual subscription **before** February 10th, 2017, it will end up on the same invoice as the existing subscription on January 10th, 2018.
* If the customer buys a second subscription **after** February 10th, despite the subscription being aligned to the correct day of the month, the new annual subscription won't be on the same invoice and will renew one year after its start date.

> 🚧 **Note**:
>
> When a customer is currently subscribed to an annual subscription and buys another annual subscription, the new subscription will only align to the existing subscription if it's bought within one month of the start date for the first annual subscription. To enable a subscription to align after the one-month window, you can use the [postpone](https://docs.recurly.com/docs/postpone-subscription) feature.
>
> Calendar billing/aligning your customers' renewals is not supported on annual plans where the billing period is 1 year. However, it is supported if you have a 1 year plan where the billing period is broken out into 12 months.

#### Upgrades and downgrades

Customers sometimes upgrade or downgrade their subscription plans. If an immediate subscription change includes a change of billing period, the subscription will need to be aligned since it resets to the current date. As long as this feature is active, any immediate subscription change will consider the account's bill date, ensuring the subscription maintains alignment.

##### Monthly upgrade to annual example

An **existing** customer is subscribed to monthly Bronze and Silver plans with a bill date of the 1st of the month. The customer upgrades their Silver monthly plan to the annual Gold plan on January 15th.

* Gold annual subscription's regular billing cycle would be from January 15th to January 15th of the following year.
* Gold annual subscription's bill date of January 15th is adjusted to January 1st to align with the bill date of the 1st.
* A prorated invoice for Gold is created for the billing period from January 15th to January 1st.
* The next invoice that will include **both** subscriptions will be on January 1st.

Other immediate subscription changes that don't involve a plan change won't require proration or adjustment since they'll maintain the current billing period and subscription alignment.

#### Expiring or canceled subscriptions

Subscriptions in their last billing cycle or those canceled before the bill date won't be included in the next invoice. This logic is the same as the Aggregate Invoice feature.

#### Promotional Subscriptions Renewing or Expiring

Promotional subscriptions, defined as subscriptions purchased with a gift card or using cardless free trials, will expire if there's no payment method or sufficient credit/coupons to cover the total cost of all promotional subscriptions.

If promotional and non-promotional subscriptions are set to bill together and there's no payment method, subscriptions initiated with a gift card will expire, and the cardless trial subscription will enter dunning. This logic is the same as the Aggregate Invoice feature.

# Trial subscriptions

When dealing with trial subscriptions, it's essential to remember:

* If an account doesn't have a bill date (new customer) and they buy a trial subscription, the account's bill date won't be set until the trial ends (when the first non-trial invoice occurs).
* If an account doesn't have a bill date (new customer) and they buy trial subscriptions of varying lengths, the trial subscription that ends first will set the account bill date (e.g., a 7-day trial subscription will have its first non-trial invoice before a 30-day trial subscription).

#### Trial Subscription without Bill Date

If a customer doesn't have an account bill date, it means they either have a subscription(s) currently in trial or they're a new subscriber.

##### Example

A **new** customer buys a 7-day trial subscription on January 15th.

* The trial ends on January 22nd, and the subscription activates into its regular billing cycle.
* The account's bill date is set to January 22nd.
* Any subsequent non-trial subscription purchases or activations will align to this date.

#### Trial subscription with bill date

If a customer already has an account bill date and buys a new trial subscription, when the subscription finishes its trial, we'll adjust the bill date to match the account bill date. This results in a one-time prorated invoice. At the next bill date, the subscriptions will bill together.

##### Example

An **existing** the customer has an account bill date of the 10th. The customer buys a subscription to the monthly Gold plan with a 7-day trial on February 15th.

* When the trial subscription ends on February 22nd, the first non-trial invoice occurs.
* Gold subscription's regular billing cycle is February 22nd - March 22nd.
* Gold subscription's bill date of March 22nd is adjusted to March 10th, to align with the bill date.
* A prorated invoice for Gold is created for the billing period of February 22nd - March 10th.
* The next month's invoice on March 10th will include **both** subscriptions.

# Emails

If you've enabled automatic email templates on your site or plans, the following email templates will support renewal-related emails. These emails will be sent, one email per subscription, if the template is enabled at the site level and if at least one of the subscription plans has the automatic email enabled:

* Renewal Reminder
* Payment Confirmation
* Invoice Past Due

If you're interested in any of these features included in Calendar Billing, please contact Support at [support@recurly.com](mailto:support@recurly.com).

# Enabling calendar billing

Before you can use Calendar Billing, you need to have it enabled for your Recurly account.

* **Step 1**: Contact Recurly Support at [support@recurly.com](mailto:support@recurly.com) to request the activation of the Calendar Billing feature.
* **Calendar Billing options:** You have a few options for how to enable Calendar Billing across your site.
  * Request to have Calendar Billing provide _both_ aggregate invoices as well as renewal alignment
    * Once enabled, all customers' subscriptions with equal billing period intervals (months) created moving forward will be adopt the same bill date and invoice cadence of the very first subscription created on a given customer's account. All subscriptions will appear on a single invoice
      > 👍 Choosing to enable Calendar Billing with both renewal alignment and aggregate invoices will ensure all monthly subscriptions across your site moving forward will assume the new behavior
  * Request to have Calendar Billing provide either aggregate invoices _or_ renewal alignment
    * Once _only_ renewal alignment is enabled, all customer's subscriptions with equal billing period intervals (months) will be billed on the same date of the very first subscription created on a given customer's account but will not aggregated on a single invoice
    * Once _only_ aggregate invoices is enabled, all customer's subscriptions that have the exact same period end date down to the second will be displayed on a single invoice.
      > 👍 Choosing to only enable "aggregate invoices" allows you as the merchant to own which subscriptions you would like to align for customer accounts

## Aligning Renewals

* **Step 1**: Review the account's current bill date. If the account doesn't have a bill date, it will be set based on the first non-trial invoice.
* **Step 2**: For any new subscriptions or those coming out of trial, ensure they align with the account's bill date.
* **Step 3**: Save your settings.

## Managing Bill Dates

* **Step 1**: Navigate to the 'Accounts' page.
* **Step 2**: Locate the 'Bill Date' section. Here you can view the bill date for each account.
* **Step 3**: If you need to adjust the bill date for specific subscriptions, use the [Postpone](https://dev.recurly.com/docs/postpone-subscription) feature via the API.

## Handling Promotional and Trial Subscriptions

* **Step 1**: For promotional subscriptions, ensure there's a valid payment method or sufficient credits/coupons to cover the costs.
* **Step 2**: For trial subscriptions, monitor the end date. Once the trial ends, the subscription will either align with the account's bill date or set a new bill date if none exists.

## Setting Up Renewal Emails

* **Step 1**: Navigate to the 'Email Templates' section in your Recurly dashboard.
* **Step 2**: Enable the 'Renewal Reminder', 'Payment Confirmation', and 'Invoice Past Due' email templates.
* **Step 3**: Customize the email content if necessary and save your settings.

## Review and Monitor

* **Step 1**: Monitor your aggregated invoices and aligned renewals to ensure they're functioning correctly.
* **Step 2**: Address any issues or discrepancies by contacting Recurly Support.
