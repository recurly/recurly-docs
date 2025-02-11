---
title: Amazon Pay
excerpt: >-
  Integrate Amazon Pay, the trusted payment solution from Amazon, into your
  Recurly payment gateway to provide a smooth subscription payment experience
  leveraging a platform utilized by millions of Amazon customers worldwide.
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

### Use cases

* Seamless subscriptions: Amazon Pay enables effortless sign-ups for subscriptions, appealing to Amazon's vast user base.
* Efficient checkout: Amazon Pay ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with Amazon Pay gateway - Integration via Recurly.JS.
* Your site must support transactions in multiple currencies, including USD, EUR, and GBP.

### Limitations

* Supports transactions in multiple currencies as specified by Amazon Pay.
* The integration process requires setting up with Amazon Pay and Recurly.js and demands technical proficiency.

# Description

Amazon Pay simplifies how consumers use their Amazon account to pay for goods and services on your site and beyond. With billions in annual transactions, Amazon Pay offers not just a payment platform but a secure and streamlined payment experience directly through Amazon. With continuous updates, Amazon Pay easily integrates into your array of payment methods, ensuring a straightforward subscription payment journey.

Amazon Pay offers two versions: Amazon Pay V1 and V2 with the newest offering a redirect option versus widgets. Amazon Pay widgets are not supported in V2.

# Key details

## Supported features

* **Asynchronous and Synchronous transactions:** Amazon Pay supports both asynchronous and synchronous payment methods, facilitating purchases, refunds, authorizations, and captures.

* **R.js Token utilization:** Use Amazon Pay Recurly.js tokens to carry out transactions via V2 or V3 Recurly endpoints. Only supported via Amazon Pay V2.

* **Platform support:** Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

# FAQs

#### Which gateways support Amazon Pay?

Amazon Pay is directly supported through its own gateway offerings in two different versions. Please consult the Amazon Pay documentation for setup and troubleshooting details.

* [Amazon Pay V1](https://docs.recurly.com/docs/amazon-payments)
* [Amazon Pay V2](https://docs.recurly.com/docs/amazon-pay-v2)
