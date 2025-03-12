---
title: UPI AutoPay
excerpt: >-
  Unlock Subscriptions in India by integrating Recurly with Ebanx, thus enabling
  UPI AutoPay, a secure and popular payment method in India, specifically built
  for subscriptions, for your business needs.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Supported gateways

Recurly currently supports UPI AutoPay transactions through Ebanx gateway.

# Definition

Integrating Recurly with Ebanx enables merchants to leverage UPI payment methods, including UPI AutoPay. This powerful combination aligns Recurly's subscription management with Ebanx’s gateway capabilities for seamless payments in India.

# Key details

## What is UPI?

**UPI (Unified Payments Interface)** is a real-time payment system in India that consolidates multiple bank accounts into a single mobile app. Users can pay using a **VPA (Virtual Payment Address)**—for example, `payer@bankname`—which masks their bank details for increased security.

### What is UPI AutoPay?

**UPI AutoPay** facilitates compliant recurring payments from an Indian bank account. Consumers can schedule recurring payments for subscriptions, bills, and more through their UPI app.

## What is a VPA?

A **Virtual Payment Address (VPA)**, such as `payer@bankname`, uniquely identifies a consumer’s bank account in a UPI app. It conceals direct bank information; therefore, Recurly does not see the underlying payment method.

## What can users do within the UPI App?

Consumers can **pause** or **cancel** subscriptions directly from their UPI app and must **confirm** transactions of **15 INR or higher** within one hour of receiving a push notification. They also receive a **pre-renewal push notification** 24–48 hours prior to their next billing date, giving them another opportunity to pause or cancel.

# Recommended integration

### Use cases

* Recurly Subscription Plans: Simplify UPI AutoPay transactions by merging the Recurly subscription platform with Ebanx.

### Creating Subscriptions

Use the **subscription** or **purchase** endpoints to create subscriptions with UPI AutoPay. Provide the VPA in Recurly’s `payment_gateway_references` object and specify `upi_vpa` as the reference type. See Recurly documentation for more details.

### Billing information updates

UPI AutoPay **doesn’t support direct updates** to a VPA. Customers must update their banking information in the UPI app directly.

If a customer’s VPA changes, **cancel the existing subscription** and have them re-enroll with the new VPA to create a new mandate.

### Cancellations

If a customer cancels via the UPI app, Recurly webhooks will notify you. Subscriptions are automatically canceled in Recurly.

### Paused subscriptions

If a customer pauses via the UPI app, Recurly webhooks notify you. Subscriptions are automatically paused in Recurly.

### Resumed Subscriptions

A customer may resume a paused subscription directly in the UPI app. Recurly sends a webhook, and the subscription is automatically resumed.

If you prefer not to allow this flow, you can **cancel** the subscription in Recurly when you receive the pause webhook.

### Gateway tokens

UPI requires Recurly's **gateway token** approach, as each consumer’s VPA functions like a virtual account identifier (`payer@bankname`). Your integration must pass the VPA through `payment_gateway_references` object and ensure you are setting the reference type as `upi_vpa`  and `gateway_code` parameters. Refer to Recurly’s API documentation for details.

### Net terms and subscription updates

* **Use Net Terms = 0** to avoid failed payments due to limited UPI charge windows.
* **Avoid changing subscription prices** for a fixed-price UPI mandate. If the price changes, the subscription must be canceled and re-created with new customer consent.

#### Testing

Refer to the **Ebanx gateway documentation** for testing procedures.

# Checkout flow

During the checkout, allow your consumer to provide their VPA (Virtual Payment Address) and pass it to Recurly using documented gateway token parameters. This will create an enrollment request to the gateway, and if accepted by the customer within their UPI app, will set up a subscription and, if the plan is not set up for a trial, charge the first amount according to the plan settings.

Renewals will occur according to plan settings, unless the customer interrupts the subscription from the UPI Application on their phone. We recommend enabling specific webhooks so that you can act on these cases to pause, resume, or cancel the subscription based on the customer’s request.

## Recommended Webhooks

Since UPI - Recurring customer actions are outside of Recurly's view, our Ebanx integration supports notifying Recurly when a customer has cancelled or paused their UPI mandate. It is recommended to listen for certain Recurly webhooks if you have selected 'Manual' in your Mandate Preferences settings.

* [Cancelled Subscription](https://recurly.com/developers/reference/webhooks/#canceled-subscription): Will be sent if the customer cancels their UPI mandate externally.
* [Paused Subscription](https://recurly.com/developers/reference/webhooks/#paused-subscription) Will be sent if the customer pauses their UPI mandate externally.
* [Resumed Subscription](https://recurly.com/developers/reference/webhooks/#resumed-subscription) Will be sent if the customer unpauses their UPI mandate externally.

Use the V3 API endpoints listed below to take action in these cases:\
Pause a Subscription: [Recurly V3 API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/pause_subscription) (v2021-02-25)
Resume a Subscription: [Recurly V3 API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/resume_subscription) (v2021-02-25)
Cancel a Subscription: [Recurly V3 API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/cancel_subscription) (v2021-02-25)

# FAQs

### Q: Do you support UPI QR Code or One-Time transactions?

* No. Our integration with Ebanx only supports recurring transactions.

### Q: My UPI Subscription is failing, how can I fix this?

* Ensure the subscription price has not changed without customer-engagement to re-subscribe.
* Ensure your Mandate Management settings are set properly. If they are set to manual, you may have missed a webhook that requires a change to the subscription status.
* Ensure your customer is responding to the UPI application push notifications when pre-renewal notifications are sent or on charges that are above 15 INR.
* Ensure you have not ignored a webhook to pause or cancel a subscription. Your customer may have requested such, and you will need to act on the specific subscription via API or within the UI.

### **Q: I updated my customer's VPA on an existing subscription, but the original bank account was charged. How do I fix this?**

* Billing Info Updates are not supported when using UPI AutoPay. Cancel the current subscription and have your customer resubscribe with their new VPA.