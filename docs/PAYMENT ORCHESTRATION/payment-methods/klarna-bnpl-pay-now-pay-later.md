---
title: Klarna (BNPL, Pay Now, Pay Later)
excerpt: >-
  Klarna allows customers to choose from Klarna's flexible payment options.
  Choose to pay in 4 interest-free payments, pay the full amount immediately, or
  pay later on their pay day. 
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites & supported gateways

* Recurly currently supports Klarna BNPL, Pay Now, and Pay Later transactions through Stripe, via Payment Elements (Third Party Checkout).

### Limitations

* The Klarna Recurring feature is available exclusively for merchants enrolled in the Stripe Klarna Recurring BETA, using Stripe via Payment Elements.
* Klarna BNPL is not available for monthly subscriptions.

# Definition

Klarna is a global payment solutions provider offering flexible payment options at checkout, popular for its buy now, pay later (BNPL) service. It allows customers to split purchases into installments, pay in 30 days, or pay in full, offering a variety of options for managing online shopping costs.

Presently, Klarna is only supported on Stripe.

# Checkout flow

#### Consumer authentication

Klarna payments are offered by Klarna Bank AB, a Swedish bank that provides payment services, including BNPL and traditional banking. Customers must provide certain details to Klarna and, in some cases, undergo a credit check to use options like Pay in 4 (Installments).

#### Completing the order

To pay with Klarna, customers are redirected to Klarna’s site to select their preferred payment option, then returned to your website to complete the order. Klarna presents options based on the customer’s currency, subscription interval (monthly, weekly, yearly, etc.), and transaction amount.

Once approved, Stripe immediately makes the full order amount (minus fees) available in your account, and Klarna collects payment from the customer.

# Key details

#### Payment options

Depending on the subscription or transaction type, customers can be presented with three options:

* **Pay in Full (Pay Now):** Immediate capture using Klarna as a “wallet” payment method with the instrument stored in the customer’s Klarna account.
* **Pay Later:** Full payment collected within a specified timeframe (e.g., 30 days), using the Klarna payment method on file.
* **Pay in Installments (Pay in 3 or 4):** Splits the purchase into 3 or 4 installments; merchants receive full funds upfront.

#### Customer locations and presentment currencies

Stripe Elements dynamically presents Klarna options based on customer location and transaction currency, as different regions have varying rules around Pay Later and BNPL. For example, Pay Later isn’t supported in Montana, New Mexico, or Hawaii, and Pay in Installments isn’t supported in New Mexico or Hawaii. For the latest restrictions, refer to Stripe’s documentation: <a href="https://docs.stripe.com/payments/klarna#payment-options" target="_blank">Klarna payments | Stripe Documentation</a>.

### Klarna prohibited businesses and ethics messaging

Klarna maintains a list of prohibited and restricted business categories: <a href="https://docs.klarna.com/resources/legal-and-compliance/policies-and-term-of-service/prohibited-and-restricted-businesses/" target="_blank">Klarna Docs – Prohibited and restricted businesses</a>.

Use Stripe’s Messaging Element to surface ethical considerations and payment method details: <a href="https://docs.stripe.com/payments/payment-method-messaging" target="_blank">Payment Method Messaging Element | Stripe Documentation</a>.

For advertising guidelines, see: <a href="https://docs.klarna.com/resources/legal-and-compliance/more-solutions-guidelines/ad-policies-for-klarna-advertisers/" target="_blank">Ad policies for Klarna advertisers</a>.

#### API, Stripe Elements, and Recurly.js

Leverage Third Party Checkout with: <a href="https://docs.recurly.com/v1.1/docs/third-party-checkout#/" target="_blank">Third Party Checkout: Stripe Elements</a> and <a href="https://docs.recurly.com/v1.2/docs/overview" target="_blank">Recurly.js Overview</a> via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html" target="_blank">V3 API</a>.

#### Sandbox testing

Before going live, test Klarna Recurring through Payment Elements on your Recurly sandbox site to confirm correct functionality.

> **Tip:** BNPL and Pay Later options appear only on plans with billing intervals of at least 2–3 months; shorter cycles will display only “Pay Now.”