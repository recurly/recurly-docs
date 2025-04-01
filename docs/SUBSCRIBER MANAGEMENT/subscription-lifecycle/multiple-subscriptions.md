---
title: Multiple subscription support
excerpt: >-
  Leverage the power of choice. Offer your customers a rich and flexible array
  of subscription options all managed efficiently in one place.
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

With Recurly, businesses can provide their customers with the flexibility to have multiple subscriptions. This feature allows subscribers to enjoy varied plans simultaneously, and for businesses, it simplifies the invoicing process by consolidating multiple plan details into one.

# Key benefits

* **Streamlined management**: Manage all your subscriptions under one roof, making administration and customer management easier.
* **Enhanced customer experience**: Offer your customers greater choice and flexibility in how they engage with your services.
* **Flexible billing**: Combine various subscriptions into a single invoice or maintain separate billing for each, as per your business needs.
* **Unified communication**: Single consolidated emails for new subscription notifications, even with multiple subscriptions.
* **Data insights**: Track, analyze, and leverage data from multiple subscriptions for improved business decisions.

# Key details

In today's fast-paced digital economy, flexibility is key. With Recurly's Multiple Subscriptions feature, businesses can offer a range of subscription options tailored to the unique needs of their customers.

## The power of the API

The API forms the backbone of managing multiple subscriptions. By harnessing the capabilities of the [purchase endpoint](https://developers.recurly.com/api/latest.html#operation/create_purchase), businesses can seamlessly create an array of subscriptions for both new and existing accounts. This endpoint facilitates the amalgamation of various subscriptions and even one-time charges as a part of the [Hybrid](https://docs.recurly.com/docs/billing-models#section-hybrid) billing model.

* **Uniform payment:** All subscriptions in a purchase must utilize a shared payment method.
* **Consistent collection method:** Subscriptions in a purchase must have the same collection method, ensuring uniformity in processing.

### Unpacking the purchase invoice

Purchases that encompass more than one subscription will culminate in an invoice that lists all the individual subscriptions and charges. This consolidated approach simplifies the invoicing process, displaying each charge distinctly, ensuring clarity for customers.

> 📘 **Consolidating multiple subscriptions into a single invoice**
>
> Combining multiple subscriptions into one invoice is a streamlined process, but it requires the subscriptions to meet certain criteria. Utilize either the "Aggregate Invoice" or "Alignment" features to achieve this. These tools are designed to simplify billing by grouping eligible subscriptions on a single invoice. For an efficient way to merge various subscription charges into one convenient bill, explore our [Calendar Billing](https://docs.recurly.com/v1.0/docs/calendar-billing) feature. This method not only enhances administrative efficiency but also provides a more cohesive billing experience for your customers.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/17cdebe-Screenshot_2.png" />

# Communication and notifications

Maintain a consistent communication strategy even with multiple subscriptions in play:

### Emails

The following email templates also support multiple subscription purchases:

* [New Subscription](https://docs.recurly.com/v1.0/docs/email-templates#section-new-subscription)
* [New Invoice](https://docs.recurly.com/v1.0/docs/email-templates#section-new-invoice)
* [Payment Confirmation](https://docs.recurly.com/v1.0/docs/email-templates#section-payment-confirmation)

When creating multiple subscriptions in purchase, a *single* New Subscription email will be sent that will contain all subscriptions purchased.

To update your email templates to support multiple subscription purchases, see [Subscription](https://docs.recurly.com/v1.0/docs/email-templates#section-subscriptions) fields.

### Webhooks

If the multiple subscriptions feature is turned on your site, the following webhooks will include a subscriptions xml tag with a list of subscriptions.

* new\_invoice
* closed\_invoice
* successful payment
* failed\_payment
* past\_due\_invoice
* new\_dunning\_event
* successful\_refund

This is new behavior based on if the feature is enabled. If multiple subscriptions is not enabled on your site, we will maintain  the original subscription xml tag.

### Exports

When the multiple subscriptions feature is active on your site, any export containing a `subscription_id` will now include a new column listing `subscription_ids` in a comma-separated format.

### Coupon Redemption in Multiple Subscription Purchase

For detailed information on how coupons are applied in multiple subscription purchases, please visit <a href="https://docs.recurly.com/docs/multiple-coupons-per-account#section-multiple-coupons-in-a-multiple-subscription-purchase" target="_blank">Multiple Coupons in a Multiple Subscription Purchase</a>.

### Custom Notes

Recurly offers customizable default terms and notes for your invoices, including Terms & Conditions, Customer Notes, and VAT Reverse Charge Notes (see <a href="https://docs.recurly.com/docs/invoice-settings" target="_blank">Invoice Settings</a>). When using custom notes with multiple subscriptions, each invoice will include one set of each note type, defaulting to site-level settings. To customize notes for a specific invoice, they must be specified in the purchase API request. It's not possible to assign different custom notes for each subscription in a single invoice.

For <a href="https://docs.recurly.com/docs/invoice-settings#section-vat-reverse-charge-notes" target="_blank">VAT Reverse Charge Notes</a> to be included on an invoice, the following conditions must be met:

* Your Recurly site has EU VAT enabled or uses an Avalara AvaTax account.
* The customer is in the EU, has a VAT number, and is based in a different country than your company.

If these conditions are met, the invoice will display the VAT Reverse Charge Notes from the Tax Settings page in Recurly admin, unless custom VAT notes are specified for the invoice.

## Admin UI or Subscriptions Endpoint

To add multiple subscriptions to an account, one option is through the Admin UI. Here, you can increase the number of subscriptions using the Quantity field for a plan, with each subscription invoiced and billed separately upon payment.

Alternatively, the <a href="https://developers.recurly.com/api/latest.html#operation/create_subscription" target="_blank">create subscription</a> endpoint allows adding individual subscriptions to an account, with separate invoicing and billing for each upon successful payment.

If using Recurly's New Subscription or New Invoice email notifications, an email will be sent for each subscription added.

> **Note:** Multiple subscriptions cannot be created when a subscription start date in the past is provided.