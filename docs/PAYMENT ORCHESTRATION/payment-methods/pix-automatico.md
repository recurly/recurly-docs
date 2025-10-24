---
title: Pix Automático
excerpt: >-
  Integrate Pix Automático, the favored payment platform of the next-gen
  Brazilian subscriber base, into your Recurly payment gateway and offer a
  frictionless subscription payment experience leveraging a platform with over
  168 million registered users.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

Recurly currently supports Pix Automático transactions on Ebanx gateway.

### Use cases

* **Seamless subscriptions:** Pix Automatic (Automático) enables effortless sign-ups for subscriptions, by allowing customers to pay merchants by scanning a QR code through the checkout flow.
* **Efficient checkout:** Pix Automático ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/) gateway.
* The ability to work with APIs and QR Code rendering. This integration will demand technical proficiency with Base64 encoded values.
* Your site must support transactions in  **BRL**.

### Limitations

* Supports transactions in _BRL_ currency only as specified by Pix Automático.
* The integration process requires setting up with Ebanx  and Recurly's APIs and demands technical proficiency.
* One-time customer or merchant initiated Pix transactions are not supported. Only subscription signup and automatic renewals are supported.
* Flexible Schedules and Net Terms / Modifying the Renewal Date are not supported by this payment method. PIX demands date of renewal remain consistent with the original signup and that there are no more than one (1) successful transaction attempt within the billing period. If renewal dates are changed without signing up again, the renewals will fail.
* Manual or forced conversion of trials is not supported by this payment method as Pix demands a static start date for the first renewal which is decided based on plan data associated with the subscription. Conversion attempts prior to this date are not supported and will fail.
* PIX requires subscription frequencies be one of:
  * Weekly, Monthly, Quarterly, Half-yearly, or Yearly. This can translate into other customizable Billing frequencies such as 7 Days, 30 Days, every 4 Weeks, Every 3 Months, Every 180 Days, and so on. Schedules that fall out of this pattern will be met with a validation error and the subscription signup will be unsuccessful.
* Other limitations include:
  * Invoice / Calendar Aggregation
  * Parent/Child Accounts
  * Multiple Subscriptions per Account is not supported
  * Proration during a Subscription Upgrade or change is not supported
  * Funds verification and Wallet payment instrument visibility are not supported

# Description

PIX Automático is a recurring payment feature within Brazil's PIX instant payment system, allowing users to set up and authorize automatic, scheduled payments directly from their bank accounts for services like subscriptions, utility bills, and memberships. It functions similarly to a traditional direct debit but is processed through the instant, automated PIX network, eliminating the need for credit cards or manual actions for every payment. This system provides users with control over their recurring payments and helps businesses manage subscriptions more efficiently.

Pix Automático revolutionizes how consumers sign up for subscriptions on your site and beyond.
Available for use with Recurly.js for subscription signups for Recurly merchants, this secure payment method is fast, easy, and simple.

# Key details

## Supported features

* **Subscriptions** Customers can use their Pix wallet to sign up for subscriptions. If one-time transactions are necessary, Pix is not supported.

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

## Customer Bank interactions 

**What customers can do within their bank apps:** Customers can cancel enrollments (subscription agreements) and individual renewal transactions from within their banking application. 

* When a Pix automatic transaction is submitted, consumers have a 2 full days before the official processing date to cancel the pending request. When this happens, Recurly will consume a webhook and mark the scheduled transaction as declined. You will need to reach out to your customer to discuss payment options, or you have the option to cancel the subscription, or expire the subscription through dunning if you wish.
* Users can cancel the entire subscription by revoking their enrollment for that subscription. This will cause a complete cancellation of the active subscription within Recurly. 

**What can you do with Pix Subscriptions in Recurly:** When expiring a subscription, either manually or through dunning, Recurly will send a revocation request to the gateway to expire the mandate within the customer's bank app.

# FAQs

#### **Q: Which gateways support Pix Automático?**

**A**: Pix Automático is directly supported through the below gateway offering. Refer to the associated documentation for setup and troubleshooting guidance:

* [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/)

#### **Q: Does Pix Automático use Recurly.js?**

**A**: Pix Automático requires rendering of an **on-page QR code** during signup. You will receive a Base64 QR code in the initial payload response. See our Integration guide for more details.

#### **Q: How can I integrate my checkout solution to use Pix Automático?**

**A**: Pix Automático is supported our V3 APIs. You can find links to our API guide below:

* [Pix Automatico API Guide](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico-integration-guide#/)

<br />
