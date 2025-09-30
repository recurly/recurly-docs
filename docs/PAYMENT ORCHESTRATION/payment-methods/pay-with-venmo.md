---
title: Venmo
excerpt: >-
  Integrate Venmo™, the favored payment platform of the next-gen subscriber
  base, into your Recurly payment gateway and offer a frictionless subscription
  payment experience leveraging a platform with over 52 million active users.
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

### Prerequisites & supported gateways

* A connection with the [Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd#/) gateway.
* Integration via Recurly.JS.
* Your site must support USD transactions, as it is the only currency supported.

### Limitations

* Only supports USD as the transaction currency.
* The integration process involves setting up with Braintree and Recurly.js, and requires technical know-how.

# Description

Venmo™ stands at the forefront of payment technology, catering to a massive user base with over 159 billion in annual transactions. It's not just a payment platform; it's a social experience, with emojis playing a fun part in the transaction narratives. With new enhancements, Venmo™ smoothly integrates into your payment method assortment, allowing for a seamless subscription payment process.

#### Supported Features

* Synchronous transactions: Venmo™ supports synchronous payment methods, including purchases, refunds, and manual captures.

* Token utilization: Utilize Venmo Recurly.js tokens to execute transactions via V2 or V3 Recurly endpoints.

* Platform support: Facilitates both mobile and desktop transaction flows.

* Multi-Use Funding Sources: This enables consumers to change their funding source while the subscription is active without having to resubscribe.

## Use cases

* Easy subscriptions: Venmo™ makes subscriptions easy, attracting a younger, tech-savvy demographic.
* Quick transactions: With Venmo™, offer a speedy checkout process, both on mobile and desktop platforms.

## Checkout flow

#### Implementation with Recurly.JS

To facilitate the Venmo™ payment method on your platform, integrate it using Recurly.JS. Find the developer documentation [here](https://developers.recurly.com/reference/recurly-js/#venmo) to get started with the integration.

There are two authentication methods for Venmo using R.js: QR Code Authentication, which was initially rolled out with R.js, and the Desktop Web Authentication method, which launches a web modal to allow users to log in.

Per Braintree’s own documentation, they highly recommend using the Desktop Web Authentication, which requires an additional argument passed in the R.js instantiation for Venmo.

## Recurly settings

#### Currency and gateway setup

Ensure that your site is set up to handle USD transactions, as it is the only supported currency for Venmo™. In addition, verify that the Braintree gateway is active; no further configurations are needed on the Recurly side.

#### Feature Flag Enablement

In order to take advantage of addresses provided directly from the Venmo SDK when using R.js, talk to Support about enabling two feature flags on your site: Save Braintree Venmo Shipping and Billing Address. With this setting enabled, you will not be required to provide an Address via V2 or V3 APIs, however, if an address _is_ provided via API, that data will override any Venmo SDK-sourced information.

## Gateway settings

#### Configuring Venmo™ on Braintree

Before initiating Venmo™ payments, you must set the method up through your Braintree account.

Additionally, for Venmo payments, In order to take advantage of User Billing and Shipping Addresses access through R.js, you will need a setting enabled in your Braintree account to supply Enriched Data to Recurly.

Detailed guidance can be found [here](https://articles.braintreepayments.com/guides/payment-methods/venmo?_ga=1.96363612.1166429227.1614967182#testing).
