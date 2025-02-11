---
title: Link Pay by Stripe
excerpt: >-
  Link allows your customers to select a saved payment method at checkout
  instead of entering payment information every time they check out. Your
  customers can save their credit cards, debit cards, or US bank accounts for
  faster checkout at any Link-enabled business.
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

- **Seamless subscriptions:** Link  enables effortless sign-ups for customers globally, and allows  merchants to offer subscriptions to customers using cards or a US bank account.
- **Efficient checkout: **Link by Stripe ensures a quick and secure checkout process, catering to both mobile and desktop users.

### Prerequisites & supported gateways

- A connection with Stripe gateway if your integration is via Stripe Elements.
- Your site must support a Stripe Elements integration.

### Limitations

- See Stripe’s website for Link Pay limitations and country availability: <https://docs.stripe.com/payments/link> (Link is not available in India. Also, in Brazil and Thailand, Payment Elements do not support Link.)
- Link with Direct Debit is limited to USD, US-based customers.
- Link Customers cannot update their billing method through Recurly. They must visit link.com to update details.
- Link by Stripe is a proprietary Stripe offering. It will not be available on other gateways.

# Description

Link Pay by Stripe is a proprietary wallet that streamlines checkout by auto-filling payment details across merchant environments. This reduces cart abandonment and improves authorization rates.

With Link, your customers can select saved payment methods—credit cards, debit cards, or US bank accounts—at checkout for a faster, more convenient experience. Saved payment methods are available across any Link-enabled business.

Link also supports Instant Bank Payments, with all transactions confirming immediately. Successful payments settle to your Stripe balance on the same timeline as card payments, regardless of the payment method used.

To manage accounts, view purchase history, or contact customer support, customers can visit **link.com**.

> **Note: **Link Pay is supported only via Third Party Checkout through Stripe Payment Elements.

# Key details

### Supported features

- **Customer redirection**: When customers select Revolut Pay, they are redirected to Revolut Pay’s website to authenticate with their account details or proceed as a first-time user. After authentication, they are redirected back to your website.
- **Stripe integration**: Leverages Stripe Payment Element and V3 API for seamless ctoken utilization and compatibility with this payment method.
- **Platform compatibility**: Fully supports transaction flows on both mobile and desktop, offering flexibility for your customers.

# FAQs

#### **Q: Which gateways support Link by Stripe?**

**A:** Link by Stripe is supported through the following gateway offerings. Refer to the associated documentation for setup and troubleshooting guidance:

- [Stripe (Stripe Elements - Third Party Checkout)](https://recurly.com/developers/guides/3rd-party-checkout.html#third-party-checkout)