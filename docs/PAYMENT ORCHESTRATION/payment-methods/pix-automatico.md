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

* A connection with Ebanx gateway if your Integration is via Recurly.JS.
* Your site must support transactions in one of **CURRENCIES**.

### Limitations

* Supports transactions in **CURRENCIES** currency only as specified by Pix Automático.
* The integration process requires setting up with Ebanx  and Recurly.js and demands technical proficiency.
* One-time customer or merchant initiated Pix transactions are not supported. Only subscription signup and automatic renewals are supported.

# Description

PIX Automático is a recurring payment feature within Brazil's PIX instant payment system, allowing users to set up and authorize automatic, scheduled payments directly from their bank accounts for services like subscriptions, utility bills, and memberships. It functions similarly to a traditional direct debit but is processed through the instant, automated PIX network, eliminating the need for credit cards or manual actions for every payment. This system provides users with control over their recurring payments and helps businesses manage subscriptions more efficiently.

Pix Automático revolutionizes how consumers sign up for subscriptions on your site and beyond.
Available for use with Recurly.js for subscription signups for Recurly merchants, this secure payment method is fast, easy, and simple.

# Key details

### Supported features

* **Subscriptions** Customers can use their Pix wallet to sign up for subscriptions. If one-time transactions are necessary, Pix is not supported.

* **R.js Token utilization:** Use Pix Automático Recurly.js tokens to carry out transactions via V3 Recurly endpoints.

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

# FAQs

#### **Q: Which gateways support Pix Automático?**

**A**: Pix Automático is directly supported through the below gateway offering. Refer to the associated documentation for setup and troubleshooting guidance:

* Ebanx

#### **Q: How can I integrate my checkout solution to use Pix Automático?**

**A**: Pix Automático is supported through Recurly.js and our V3 APIs. You can find links to our API guide and Recurly.js guides below:

* API Guide:
* Recurly.js guide

<br />
