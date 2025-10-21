---
title: MercadoPago
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

Recurly currently supports Mercado Pago transactions on Ebanx gateway.

### Use cases

* **Seamless subscriptions:** Mercado Pago enables effortless sign-ups for subscriptions, by allowing customers to pay merchants by scanning a QR code through the checkout flow.
* **Efficient checkout:** Mercado Pago ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with Ebanx gateway if your Integration is via Recurly.JS.
* Your site must support transactions in one of **CURRENCIES**.

### Limitations

* Supports transactions in **CURRENCIES** currency only as specified by Mercado Pago.
* The integration process requires setting up with Ebanx  and Recurly.js and demands technical proficiency.
* One-time customer or merchant initiated MercadoPago are not supported. Only subscription signup and automatic renewals are supported.

# Description

Mercado Pago is a leading digital payment platform and fintech ecosystem in Latin America, owned by the e-commerce giant Mercado Libre. It provides a wide range of services for both consumers and businesses, including online and in-person payments, money transfers, a digital wallet, and access to credit and investment options. The platform supports various payment methods such as credit cards, debit cards, bank transfers, and cash vouchers, and has a large user base across countries like Argentina, Brazil, and Mexico.

Mercado Pago revolutionizes how consumers sign up for subscriptions on your site and beyond.
Available for use with Recurly.js for subscription signups for Recurly Merchants, this secure payment method is fast, easy, and simple.

# Key details

### Supported features

* **Subscriptions** Customers can use their Mercado Pago wallet to sign up for subscriptions. If one-time transactions are necessary, MercadoPago is not supported.

* **R.js Token utilization:** Use Mercado Pago Recurly.js tokens to carry out transactions via V3 Recurly endpoints.

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

# FAQs

#### **Q: Which gateways support Mercado Pago?**

**A**: Mercado Pago is directly supported through the below gateway offering. Refer to the associated documentation for setup and troubleshooting guidance:

* Ebanx

#### **Q: How can I integrate my checkout solution to use Mercado Pago?**

**A**: Mercado Pago is supported through Recurly.js and our V3 APIs. You can find links to our API guide and Recurly.js guides below:

* API Guide:
* Recurly.js guide
