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
* Your business must be B2C in order to accept Klarna payments (e.g. you are selling your goods and services to a consumer).
* Leverage Third Party Checkout with: <a href="https://docs.recurly.com/docs/third-party-checkout/" target="_blank">Third Party Checkout: Stripe Elements</a> and <a href="https://docs.recurly.com/docs/overview-recurlyjs/" target="_blank">Recurly.js Overview</a> via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html" target="_blank">V3 API</a>.

### Limitations

* Klarna BNPL is not available for monthly subscriptions and is only supported for subscriptions longer than 2 months. Refer to the table below for available payment options and consumer countries.
* Presently, tokenized Klarna payment details cannot be used when paired with a Trial Plan and a separate add-on line item that is not associated with the Plan itself.
* Coupons are supported however, **100% coupons during signup cannot be supported** as credit checks are requirement for this payment method. Please use a free trial option instead.

# Definition

Klarna is a global payment method popular for its buy now, pay later (BNPL) service and other flexible payment options. It allows customers to split purchases into 3 or 4 installments, pay in 30 days, or pay in full, offering a variety of interest-free options for managing online shopping costs.

Klarna is liable for consumer credit risk and has the authority to request additional credit checks for new subscriptions.

# Checkout flow

#### Consumer authentication

Klarna payments are offered by Klarna Bank AB, a Swedish bank that provides payment services, including BNPL and traditional banking. Customers must provide certain details to Klarna and, in some cases, undergo a credit check to use options like Pay in 4 (Installments).

#### Completing the order

To pay with Klarna, customers are redirected to Klarna’s site to select their preferred payment option, then returned to your website to complete the order. Klarna presents options based on the customer’s currency, subscription interval (monthly, weekly, yearly, etc.), and transaction amount.

Once approved, Stripe immediately makes the full order amount (minus fees) available in your account, and Klarna collects payment from the customer.

# Key details

## Payment options

### Customer Initiated / In-Session Payment Options

Depending on the subscription or transaction type, customers can be presented with three options:

* **Pay in Full (Pay Now):** Immediate capture using Klarna as a “wallet” payment method with the instrument stored in the customer’s Klarna account.
  * Available on all subscription lengths.
* **Pay Later:** Deferred payment option where the customer pays the full order amount on a set day of the week or month, bundled together with any other Pay Later purchases — with no interest or fees when paid on time.
  * Available on all subscription lengths.
* **Pay in Installments (Pay in 3 or 4):** Splits the purchase into 3 or 4 installments; merchants receive full funds upfront.
  * Only available for subscriptions greater than 2 months (quarterly, annual, etc.)

### Merchant Initiated / Off-Session Payment Options

When a merchant is initiating a payment, such as a renewal, a force collection, or one-time invoice where the consumer is not directly in the checkout session, Klarna / Stripe's offerings are regional specific. Check their website for additional details:

* [Stripe / Klarna Recurring Payment support](https://docs.stripe.com/payments/klarna#recurring-payment-support)

Stripe / Klarna handle refunds for partially collected BNPL payments.

#### Customer locations and presentment currencies

Stripe Elements dynamically presents Klarna options based on customer location and transaction currency, as different regions have varying rules around Pay Later and BNPL. For example, Pay Later isn’t supported in Montana, New Mexico, or Hawaii, and Pay in Installments isn’t supported in New Mexico or Hawaii. For the latest restrictions, refer to Stripe’s documentation: <a href="https://docs.stripe.com/payments/klarna#payment-options" target="_blank">Klarna payments | Stripe Documentation</a>.

### Klarna prohibited businesses and Ethics messaging

Klarna maintains a list of prohibited and restricted business categories: <a href="https://docs.klarna.com/resources/legal-and-compliance/policies-and-term-of-service/prohibited-and-restricted-businesses/" target="_blank">Klarna Docs – Prohibited and restricted businesses</a>.

Boost conversion by using Stripe’s Messaging Element to let buyers know that Klarna is available ahead of checking out. Stripe handles displaying relevant payment options in a legally and brand compliant way: <a href="https://docs.stripe.com/payments/payment-method-messaging" target="_blank">Payment Method Messaging Element | Stripe Documentation</a>.

For advertising guidelines, see: <a href="https://docs.klarna.com/resources/legal-and-compliance/more-solutions-guidelines/ad-policies-for-klarna-advertisers/" target="_blank">Ad policies for Klarna advertisers</a>.

#### Sandbox testing

Before going live, test Klarna Recurring through Payment Elements on your Recurly sandbox site to confirm correct functionality.

> **Tip:** BNPL and Pay Later options appear only on plans with billing intervals of at least 2–3 months; shorter cycles will display only “Pay Now.”

### Subscription Recommendations

* Since all customer "off-session" transactions occur as 'Pay Now', if you are using BNPL for Annual Plans, it is recommended to set the Plan End of Subscription Term behavior as 'Expire subscription' so that the consumer can come back into session and make a selection for their next term renewal (BNPL, Pay Later, etc) for their next subscription term.
