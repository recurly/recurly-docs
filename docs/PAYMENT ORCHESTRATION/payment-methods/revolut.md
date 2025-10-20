---
title: Revolut
excerpt: >-
  Revolut Pay, developed by Revolut, a global finance app, is a digital wallet
  payment method. Revolut Pay uses the customer’s stored balance or cards to
  fund the payment, and offers the option for non-Revolut customers to save
  their details after their first purchase.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Use cases

* Seamless subscriptions: Revolut enables effortless sign-ups for UK and EU merchants to offer subscriptions to UK/EU customers, by allowing customers to pay merchants by confirming their payment with the Revolut app.
* Efficient checkout: Revolut ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

* A connection with Stripe gateway if your integration is via Stripe Elements.
* Your site must support transactions in GBP or EUR.

### Limitations

* Supports transactions in GBP currency for UK-based Merchants, and EUR currency for EU-based Merchants.
* The integration process requires setting up with Stripe and Stripe Payment Elements, as well as Recurly.js, and demands technical proficiency.

# Definition

Revolut Pay, developed by Revolut, a global finance app, is a digital wallet payment method. Revolut Pay uses the customer’s stored balance or cards to fund the payment, and offers the option for non-Revolut customers to save their details after their first purchase.

Revolut is supported via Third Party Checkout through Stripe Payment Elements only.

# Key details

### Supported features

* When customers select Revolut Pay as their payment method, they are redirected to Revolut Pay’s website, where customers must authenticate with their account details or checkout as a first time user. After authenticating, Revolut Pay redirects customers back to your website.

* Stripe Elements ctoken utilization: Use Stripe Payment Element, and V3 API to support this payment method.

* Platform support: Supports transaction flows on both mobile and desktop platforms, offering flexibility for users.

# FAQs

#### Which gateways support Revolut?

Revolut is directly supported through the below gateway offerings. Refer to the associated documentation for setup and troubleshooting guidance:

* [Stripe](https://docs.recurly.com/recurly-subscriptions/update/docs/stripe-payment-elements#/) (Stripe Elements - Third Party Checkout)

<br />
