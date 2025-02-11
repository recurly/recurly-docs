---
title: Cash App Pay
excerpt: >-
  Integrate Cash App Pay, a trusted peer-to-peer wallet option, into your
  Recurly payment gateway to provide a smooth subscription payment experience
  leveraging a platform utilized by millions of Cash App customers worldwide.
deprecated: false
hidden: true
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

### Use cases

* **Seamless subscriptions:** Cash App Pay enables effortless sign-ups for subscriptions, by allowing customers to pay merchants by scanning a QR code.
* **Efficient checkout:** Cash App Pay ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with Adyen  gateway if your Integration is via Recurly.JS.
* A connection with Stripe gateway if your integration is via Stripe Elements.
* Your site must support transactions in USD.

### Limitations

* Supports transactions in USD currency only as specified by Cash App.
* The integration process requires setting up with Adyen  and Recurly.js or Stripe and Stripe Payment Elements and demands technical proficiency.

# Description

Cash App Pay simplifies how consumers pay for goods and services on your site and beyond.\
Available for use with Recurly.js for subscription signups for ecommerce Merchants, this contactless payment method is fast, easy, and simple.

# Key details

### Supported features

* **Cash App balance and linked debit card purchases:** Customers are not required to have a linked bank account, and can use their Cash App balance or a linked Debit Card to pay for purchases and subscriptions. If the Cash balance is not sufficient, the customer’s linked card will be used for the purchase.

* **R.js Token utilization:** Use Cash App Pay Recurly.js tokens to carry out transactions via V2 or V3 Recurly endpoints. 

* **Stripe Elements ctoken utilization:** Use Stripe Payment Element, and V3 API to support this payment method. 

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

# FAQs

#### **Q: Which gateways support Cash App Pay?**

**A**: Cash App Pay is directly supported through the below gateway offerings in two different versions. Refer to the associated documentation for setup and troubleshooting guidance:

* Adyen (Recurly.js)
* [Stripe (Stripe Elements - Third Party Checkout)](https://recurly.com/developers/guides/3rd-party-checkout.html#third-party-checkout)
