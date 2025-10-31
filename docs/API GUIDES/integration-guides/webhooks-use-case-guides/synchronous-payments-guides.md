---
title: Synchronous payments webhook guide
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide helps you understand which webhooks you need to consume if you are using payment methods that return immediate authorization responses, thus ensuring a smoother, more transparent integration.

### Prerequisites 

* Familiarity with Recurly Webhooks
* Basic understanding of RESTful APIs and JSON
* Access to Recurly with valid API credentials

***

# Definition

In the context of webhooks, a **synchronous payment method** is one where the final status of the transaction (success, declined, or error) is returned immediately in the direct API response to the payment request. While a webhook event (like payment.succeeded) might still be sent afterward for backend reconciliation or to trigger fulfillment, your checkout system does not need to wait for this webhook to confirm the payment's outcome to the consumer. 

**Supported Payment Methods**

* Credit Cards
* Cash App
* PayPal (when the instrument is a card or PayPal balance)
* Apple Pay
* Google Pay
* Amazon Pay (when the instrument is a card or balance)
* Klarna 
* iDeal 
* Sofort / Klarna Debit Risk 
* Venmo
* Link Pay by Stripe (when the instrument is a card)

***

## Events to listen for

### Payment Notifications

Specific to [Payments notifications](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#/), you will want to listen for the following events. See the events list for all Payments event notifications and their descriptions. 

* [payment.succeeded ](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#/successful-payment): Sent when a Purchase payment is successfully approved immediately. This will also apply to status updates for Asynchronous methods. 
* [payment.failed](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#/failed-payment): Sent when a payment fails or is declined immediately. This will also apply to status updates to Asynchronous methods.
* [payment.authorized](https://docs.recurly.com/recurly-subscriptions/docs/payment-notifications#/transaction-authorized): Sent when using separate Auth and Capture, when the Authorization is successfully approved.

### Invoice Notifications

Invoices for synchronous payment methods will immediately move to a Paid or Past Due state in most cases. They are also automatically created 

<br />
