---
title: Mercado Pago
excerpt: >-
  Mercado Pago is Latin America's largest digital payment platform and wallet,
  valued for offering secure, versatile payment methods such as subscriptions,
  which promotes financial inclusion for millions.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

Recurly currently supports Mercado Pago transactions on [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway) gateway.

### Use cases

* **Seamless subscriptions:** Mercado Pago enables effortless sign-ups for subscriptions, by allowing customers to pay merchants by interacting with their bank app through the checkout flow.
* **Efficient checkout:** Mercado Pago ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with Ebanx gateway if your Integration is via Recurly.JS.
* Your site must support transactions in one of **BRL**, **ARS**, **CPL**, **MXN**, or **UYU**.
* Mercado Pago is supported on Ebanx in the following countries: Brazil, Argentina, Chile, Mexico, and Uruguay.

### Limitations

* Supports transactions in **BRL**, **ARS**, **CPL**, **MXN**, or **UYU** currencies only as specified by Mercado Pago.
* The integration process requires setting up with Ebanx  and Recurly.js and demands technical proficiency.
* One-time customer or merchant initiated MercadoPago transactions (including force collections) are not supported. Only subscription signup and automatic renewals are supported.
* Other limitations include:
  * Invoice / Calendar Aggregation
  * Parent/Child Accounts
  * Multiple Subscriptions per Account is not supported
  * Proration during a Subscription Upgrade or change is not supported
  * Funds verification and Wallet payment instrument visibility are not supported
  * Coupons are supported however, **100% coupons during signup cannot be supported** as e-mandate creation is a requirement for this payment method. Please use a free trial option instead.

# Description

Mercado Pago is a leading digital payment platform and fintech ecosystem in Latin America, owned by the e-commerce giant Mercado Libre. It provides a wide range of services for both consumers and businesses, including online and in-person payments, money transfers, a digital wallet, and access to credit and investment options. The platform supports various payment methods such as credit cards, debit cards, bank transfers, and cash vouchers, and has a large user base across countries like Argentina, Brazil, and Mexico.

Available for use with Recurly.js for subscription signups for Recurly Merchants, this secure payment method is fast, easy, and simple.

# Key details

### Supported features

* **Subscriptions** Customers can use their Mercado Pago wallet to sign up for subscriptions. If one-time transactions are necessary, MercadoPago is not supported.

* **R.js Token utilization:** Use Mercado Pago Recurly.js tokens to carry out transactions via V3 Recurly endpoints.

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

* **Automatic Retries**: Supports up to 3 reattempts after a renewal failure automatically, when the payment method response indicates an insufficient funds or a payment cancellation. Read more about retries in our [Static Retry documentation.](https://docs.recurly.com/recurly-subscriptions/docs/static-retries#/specialized-retry-strategies)

## Customer bank interactions

**What customers can do within their bank apps:** Customers can cancel enrollments (subscription agreements)  from within their banking application.

* Users can cancel the entire subscription by revoking their enrollment for that subscription. This will cause a complete cancellation of the active subscription within Recurly.

## Required fields

Mercado Pago will require you always send certain data:

* Customer Billing Address
* Customer Email Address
* Customer Phone Number
* Tax ID / Tax ID Type when the Region requires it (Brazil)

# FAQs

#### **Q: Which gateways support Mercado Pago?**

**A**: Mercado Pago is directly supported through the below gateway offering. Refer to the associated documentation for setup and troubleshooting guidance:

* [Ebanx](https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway)

#### **Q: I am trying to make a line item purchase with this payment method. Why isn't it working?**

**A**: Mercado Pago is specifically built to support Recurring subscriptions via Mercado Pago Connect. This version of the payment method does not support one time transactions or force collection actions.

#### **Q: How can I integrate my checkout solution to use Mercado Pago?**

**A**: Mercado Pago is supported through Recurly.js and our V3 APIs. You can find links to our API guide and Recurly.js guides below:

* <Anchor label="V3 API Guide" target="_blank" href="https://recurly.com/developers/api/v2021-02-25/index.html">V3 API Guide</Anchor>
* <Anchor label="Recurly.js Overview " target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/overview-recurlyjs#/">Recurly.js Overview </Anchor>
* <Anchor label="Mercado Pago Integration Guide" target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/mercado-pago-integration-guide">Mercado Pago Integration Guide</Anchor>
