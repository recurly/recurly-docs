---
title: UPI AutoPay
excerpt: >-
  Unlock Subscriptions in India by integrating Recurly with Ebanx, thus enabling
  UPI AutoPay, a secure and popular payment method in India, specifically built
  for subscriptions, for your business needs.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Supported gateways

Recurly currently supports UPI AutoPay transactions through [Ebanx](https://docs.recurly.com/docs/ebanx-gateway#/) gateway.

# Definition

Integrating Recurly with Ebanx enables merchants to leverage UPI payment methods, including UPI AutoPay. This powerful combination aligns Recurly's subscription management with Ebanx’s gateway capabilities for seamless payments in India.

# Key details

## What is UPI

**UPI (Unified Payments Interface)** is a real-time payment system in India that consolidates multiple bank accounts into a single mobile app. Users can pay using a **VPA (Virtual Payment Address)**—for example, `payer@bankname`—which masks their bank details for increased security.

There are several apps that end-users / consumers to use that involves 'UPI' such as Google Pay, Amazon, Paytm, WhatsApp. They will all have their own specific 'handle' (the @bankname in a given VPA). You can read more about [third party UPI applications on the NPCI website](https://www.npci.org.in/what-we-do/upi/3rd-party-apps).

### What is UPI AutoPay?

**UPI AutoPay** facilitates compliant recurring payments from an Indian bank account. Consumers can schedule recurring payments for subscriptions, bills, and more through their UPI app. UPI is set up initially with an enrollment into a mandate. Consumers need to authorize this enrollment, and subscriptions cannot be activated without this step.

### What is a VPA?

A **Virtual Payment Address (VPA)**, such as `payer@bankname`, uniquely identifies a consumer’s bank account in a UPI app. It conceals direct bank information; therefore, Recurly does not see the underlying payment method.

<Callout icon="📘" theme="warn">
  ### RBI Update on VPA Usage

  RBI (Reserve Bank of India) is going to mandate QR Code and App Authentication in the future. It is recommended to use those methods instead of VPA for new integrations.
</Callout>

### What is are QR or App Authentications?

A **QR Code** will allow a consumer to scan a code and authenticate on their desktop. **App Intents** allows merchants to let mobile users authenticate in mobile if they don't have access to scan a code.

### UPI AutoPay Limitations

UPI AutoPay is specifically designed for subscriptions, and subscriptions only. It is not flexible like a credit card and does not support many of the functions available in Recurly where credit cards and some other payment methods are available. Some notable limitations include:

- One-time transactions, including force collections and purchases, are not supported.
- Subscription trial conversions (forcing trials to convert) are not supported at this time due to subscription-specific mandate creation and pre-notification requirements with UPI. You can read more about our specific [mandate tolerances](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/how-are-mandates-set-up) below. Similarly, upgrades are not supported if they create an immediate charge.
- Adding a subscription through the UI: Since UPI requires a customer in session to confirm the subscription, this is not recommended.
- **When using any authentication method**: If you are using VPA, Recurly will store the consumer's VPA for future subscriptions, but the billing information is stored within the UPI App itself, not with the gateway or Recurly. If you are already using QR Code or App Authentication, we do not store billing information on file, and modifying billing info must be done in the UPI app itself.
  - If a customer changes their bank, or has a major financial change, they must resubscribe.
- Changing the renewal date defined by the mandate: If a customer wants to change their renewal date, they need to resubscribe and confirm a new mandate. UPI mandates are strict about the date we can charge the consumer, and so modifications of the date after enrollment are not recommended as declines will occur. This includes using Calendar billing / aggregation features.
- Coupons are supported however, **100% coupons during signup cannot be supported** as e-mandate creation is a requirement for this payment method. Please use a free trial option instead.

## What can users do within the UPI App?

Consumers will be required to **confirm their signup enrollment** via the UPI app whenever they are subscribing to a plan. As a result, all UPI transactions begin life as a scheduled transaction. If the consumer does not confirm the subscription enrollment, the scheduled transaction will fail and the subscription will be expired.

Consumers can **pause** or **cancel** subscriptions directly from their UPI app and must **confirm** transactions of **15000 INR or higher** within one hour of receiving a push notification.

They also receive a **pre-debit push notification** within their UPI application 48 hours prior to their next charge date, giving them another opportunity to pause or cancel the subscription prior to charging. This push notification occurs for every charge for the lifetime of their subscription. Please note, this is not a Recurly pre-renewal **email**, it is a push notification to the UPI App controlled by Recurly's integration to the gateway, and is not customizable.

<Callout icon="📘" theme="info">
  ###

  **Pre-Debit Push Notification and Transaction Timing**

  The pre-debit notification will be sent on invoice creation, so the transaction will remain in a scheduled state for several days before the payment is sent to allow for RBI mandate timeframes to pass.
</Callout>

They can also receive 2FA requests for amounts higher than 15k INR, which will appear as a push notification for confirmation and authorization per the specific UPI App's design.

Since each bank maintains it's own consumer-facing UPI flow, this is not customizable. For example, Amazon maintains a UPI interface for consumers, and individual integrators cannot modify the Amazon app.

# Recommended integration

Currently, UPI AutoCollect is not supported on Recurly Checkout or Hosted Payment Pages.

Integration Guide: [UPI AutoPay Guide](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide#/)

### Use cases

- Subscription Plans: Simplify UPI AutoPay transactions by merging the Recurly subscription platform with Ebanx.
- Trial Subscriptions: Allow your customer to authorize their enrollment and enjoy a free trial before their first charge.

### How are mandates set up?

Since all UPI AutoPay transactions requires an associated mandate, the mandate data has information in it that should be known. Mandates include information such as the expiration date of the mandate, maximum amounts, and other important details.

- **Mandate amounts** are dynamically generated based on three factors.
  - Base Plan Amount (fixed plan amount or highest ramp price)
  - Taxes, if any. For free trials, we will use the effective tax rate for the consumer, since the trial has no amount associated with it.
  - 18% tolerance in addition to the base plan + taxes.
  - Mandate amounts exclude any discounts used to ensure future payments go through, even if the first payment is discounted.
- **Mandate expiration dates** will be generated based off the plan billing term end date + 2 years. If you have a rolling monthly billing term (such as: billing periods of **1** and auto-renew), then the mandate expiry will be your billing term plus 2 years to allow for pay as you go monthly plans. In the example, the mandate would last for 2 years and 1 month.

### Required Fields

UPI AutoPay together require a minimum of fields to create a mandate for a recurring subscription. The minimum required fields to submit a UPI AutoPay transaction are as follows:

- VPA (if using Legacy)
- Type / Authentication Mode: QR or App Intent&#x20;
- Email Address
- Customer First and Last Name
- Customer Billing Address (Street Address, City, Region/State, Country, Postal Code / PIN Code)
  - Regional Mapping:
    - Street Address is the House/Street Name and Number (EX: HOUSE NO. 32, MG ROAD)
    - City is the Locality and City in India (Ex: VILLAGE OF AMARPUR, NEW DELHI)
    - State is the State or Union Territory in India (ex: MAHARASHTRA)
    - Postal Code is the PIN Code (ex: 110019)
    - Country is the Country (ex: IN)
- Phone Number

### Creating Subscriptions

Use the **subscription** or **purchase** endpoints to create subscriptions with UPI AutoPay.&#x20;

- **VPA usage:&#x20;**&#x50;rovide the VPA in Recurly’s `payment_gateway_references` object and specify `upi_vpa` as the reference type. See Recurly documentation for more details.
- **QR / App Intent usage:&#x20;**&#x50;rovide the `type` of `upi-autopay`, and the `authentication_method` you wish to use. See our developer guide for more details on authentication methods.

### Billing information updates

UPI AutoPay **doesn’t support direct updates** to billing info on Recurly's systems. Customers must update their banking information in the UPI app directly.

If a customer’s VPA changes, **cancel the existing subscription** and have them re-enroll with the new VPA to create a new mandate, or use QR / App Intent depending on what is supported by RBI.

### Enrollments and Charges

When creating a subscription, ensure you are listening to the following webhooks. UPI AutoPay is an asynchronous payment method as transactions initially begin in a scheduled state until the consumer authenticates in-app.

Signup transactions will begin in a **scheduled** state before moving to failed or approved.

Listen for the following webhooks:

- payment.scheduled
- subscription.created

Once the consumer authenticates in-app (UPI App), listen for the following webhooks:

- payment.transaction\_status\_updated
- payment.success
- charge\_invoice.paid

You can Fetch a transaction, invoice, or subscription status to update your records. When the invoice moves into a paid state, this indicates a successful consumer authentication from the UPI Application.

### Unconfirmed or Rejected Enrollments

If, when signing up, the consumer rejects the enrollment or fails to respond to the in-app push notification, the subscription will move into an expired state, and the invoice/transaction will fail. Listen for the following events.

- subscription.expired
- charge\_invoice.failed

These indicate the enrollment or charge was rejected upon signup.

### Cancellations

If a customer cancels via the UPI app, Recurly webhooks will notify you. Subscriptions are automatically canceled in Recurly. You can read more on [automatic subscription cancellations ](https://docs.recurly.com/recurly-subscriptions/docs/expire-subscription#/auto-cancellation-of-a-subscription)in our Subscription management documentation.

Listen for the following webhook:

- subscription.canceled

### Paused subscriptions

If a customer pauses via the UPI app, Recurly webhooks notify you. Subscriptions are automatically paused in Recurly. Listen for the following webhook:

- subscription.paused

### Resumed Subscriptions

A customer may resume a paused subscription directly in the UPI app. Recurly sends a webhook, and the subscription is automatically resumed. If you prefer not to allow customers to resume after pausing, you can **cancel** the subscription in Recurly when you receive the pause webhook. Listen for the following webhook:

- subscription.resumed

### Net terms and subscription updates

- **Use Net Terms = 0** to avoid failed payments due to limited UPI charge windows.
- **Avoid changing subscription prices** for a fixed-price UPI mandate. If the price changes, the subscription must be canceled and re-created with new customer consent.

#### Testing

Refer to the **Ebanx gateway documentation** for testing procedures.

### Retries

UPI AutoPay payments retries are enabled within UPI timeframes (12am - 7am IST) on the same day as the initial failure. Read more about our retry strategy for UPI on our [Static Retries documentation.](https://docs.recurly.com/recurly-subscriptions/docs/static-retries#upi-autopay)

# Checkout flow

## Initial Signup

1. During the checkout, allow your consumer to provide their VPA (Virtual Payment Address) and pass it to Recurly using documented gateway token parameters.
   1. If you are using QR Code authentication, they will be presented with a QR code they need to scan.&#x20;
   2. If you are using App Intents, you will need to present them with links to launch their respective UPI app of choice.
2. This will create an enrollment request to the gateway, and if accepted by the customer within their UPI app, will set up a subscription and, if the plan is not set up for a trial, charge the first amount according to the plan currency/amount settings. **Ensure you have INR currency and applicable pricing set up properly.**

## Renewals

Renewals will occur according to plan settings, unless the customer interrupts the subscription from the UPI Application on their phone by cancelling or pausing the subscription.

1. 24-48 hours pre-renewal, a notification is set to the gateway to initiate the pre-renewal / pre-debit notification.
2. As long as the customer does not pause or cancel their subscription via the UPI App, Recurly will make a payment attempt after the pre-notification period has ended. This will align with the subscription due date.

We recommend enabling specific webhooks so that you can act on these cases to pause, resume, or cancel the subscription based on the customer’s request.

## Recommended Webhooks

Since UPI - Recurring customer actions are outside of Recurly's view, our Ebanx integration supports notifying Recurly when a customer has cancelled or paused their UPI mandate. It is recommended to listen for certain Recurly webhooks if you have selected 'Manual' in your Mandate Preferences settings.

- [Cancelled Subscription](https://recurly.com/developers/reference/webhooks/#canceled-subscription): Will be sent if the customer cancels their UPI mandate externally.
- [Paused Subscription](https://recurly.com/developers/reference/webhooks/#paused-subscription) Will be sent if the customer pauses their UPI mandate externally.
- [Resumed Subscription](https://recurly.com/developers/reference/webhooks/#resumed-subscription) Will be sent if the customer unpauses their UPI mandate externally.

Other good webhooks to listen for are:

- charge\_invoice.created: Will be sent when a customer initially signs up for a subscription with no trial.
- charge\_invoice.processing: Will be sent when a customer signs up for a subscription with no trial, and the enrollment has not been confirmed.
- charge\_invoice.paid: Will be sent when a customer signs up for a subscription with no trial, and the enrollment has been confirmed.
- charge\_invoice.failed: Will be sent when a customer signs up for a subscription with no trial, and the enrollment has been rejected by the customer.
- payment.transaction\_status\_updated: Will be sent when a customer signs up for a subscription with no trial, and the enrollment has been confirmed.
- payment.scheduled:  Will be sent when a customer signs up for a subscription with no trial, and the enrollment has not been confirmed.
- subscription.created:  Will be sent when a customer signs up for a subscription with or without a trial.
- subscription.expired: Will be sent when a customer signs up for a subscription with or without a trial and does not confirm the enrollment.

**Note:** Subscriptions with a plan inclusive of a trial are not initially invoices. You will only receive subscription and payment webhooks, and not invoice webhooks. Look for payment.scheduled and updates accordingly when using Trials.

# FAQs

### Q: Do you support UPI QR Code or One-Time transactions?

- We now support QR Code authentication when signing up for Subscriptions. See our integration guide for UPI AutoPay for more details.&#x20;
- We do NOT support one time UPI transactions at this time.&#x20;

### Q: My UPI Subscription is failing, how can I fix this?

- Ensure the subscription price has not changed without customer-engagement to re-subscribe.
- Ensure your Mandate Management settings are set properly. If they are set to manual, you may have missed a webhook that requires a change to the subscription status.
- Ensure your customer is responding to the UPI application push notifications when pre-renewal notifications are sent or on charges that are above 100000 INR.
- Ensure you have not ignored a webhook to pause or cancel a subscription. Your customer may have requested such, and you will need to act on the specific subscription via API or within the UI.

### **Q: I updated my customer's VPA on an existing subscription, but the original bank account was charged. How do I fix this?**

- Billing Info Updates are not supported when using UPI AutoPay. Cancel the current subscription and have your customer resubscribe with their new VPA.

<br />
