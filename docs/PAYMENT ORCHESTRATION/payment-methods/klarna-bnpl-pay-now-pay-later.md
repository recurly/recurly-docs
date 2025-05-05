---
title: Klarna (BNPL, Pay Now, Pay Later)
excerpt: >-
  Klarna allows customers to choose from Klarna's flexible payment options.
  Choose to pay in 4 interest-free payments, pay the full amount immediately, or
  pay later on their pay day. 
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites and supported gateways

* Recurly currently supports Klarna BNPL, Pay Now, and Pay Later transactions through Stripe, and via Payment Elements (Third Party Checkout).

### Limitations

* The Klarna Recurring feature is available exclusively for merchants enrolled in the Stripe Klarna Recurring BETA, using Stripe via Payment Elements.
* Klarna BNPL is not available for monthly subscriptions.

# Definition

Klarna is a global payment solutions provider offering flexible payment options at checkout, popular for its buy now, pay later (BNPL) service. It allows customers to split purchases into installments, pay in 30 days, or pay in full, offering a variety of options for managing online shopping costs.

Presently, Klarna is only supported on Stripe.

# Checkout flow

#### Consumer authentication

Klarna payments are offered by Klarna Bank AB is a Swedish bank that provides payment services, including buy now, pay later options and traditional banking services. Customers must provide certain details to Klarna and in some cases, undergo a credit check, to use Klarna services such as Pay in 4 (Installments):

#### Completing the order

To pay with Klarna, Klarna redirects customers to their site, where consumers select their preferred payment option, then return to your website to complete the order. Klarna presents payment options based on the customer’s currency, subscription intervals (monthly, weekly, yearly, etc.)  and transaction amount.

After payment acceptance, the full amount of the order (minus fees) is made available to your Stripe account up front, and Klarna collects the purchase amount from your customer.

# Key details

#### Payment options

Depending on the subscription or transaction type, customers can be presented with three options:

* Pay in Full (Pay Now), where the payment will be made immediately, using Klarna as a “wallet” payment method and using the payment instrument stored within the customer’s Klarna account.
* Pay Later, where the payment will be collected later in full within a specific timeframe (30 days), and also use the payment method on file with Klarna.
* Pay in Installments (Pay in 3 or 4), where customers can choose to split their payment into 3 or 4 installments, while merchants are funded for the entirety of the purchase up front.

#### Customer locations and presentment currencies

Stripe Elements will dynamically present options to customers depending on their location and the currency configured because countries / currencies have different rules about both Pay Later and Buy Now/Pay Later.

Stripe’s website will also list the current restrictions around acceptance in certain countries, and US states. For example, as of right now, Pay Later is not supported if a customer is located in Montana, New Mexico, or Hawaii. Pay in Installments is similarly not supported in New Mexico and Hawaii. Stripe and Klarna’s documentation will have the most dynamic, up to date information on current acceptance.

Learn more about which states, countries, and currencies are supported for customers on Stripe’s website: [Klarna payments | Stripe Documentation](https://docs.stripe.com/payments/klarna#payment-options)

### Klarna prohibited businesses and ethics messaging

Klarna maintains a list of prohibited categories for Klarna usage on their website. You can find these businesses at this link: [Klarna Docs - Prohibited and restricted businesses](https://docs.klarna.com/resources/legal-and-compliance/policies-and-term-of-service/prohibited-and-restricted-businesses/)

You will also want to ensure you’re using the Messaging Element when using Klarna to explain ethical considerations and payment methods to consumers. See that information here: [Payment Method Messaging Element | Stripe Documentation](https://docs.stripe.com/payments/payment-method-messaging)

For Advertising Ethics and regulations, see Klarna’s website: [Ad policies for Klarna advertisers](https://docs.klarna.com/resources/legal-and-compliance/more-solutions-guidelines/ad-policies-for-klarna-advertisers/)

#### API, Stripe Elements, and Recurly.js

Leverage the functionality built by Recurly and Stripe via Third Party Checkout: [Third Party Checkout: Stripe Elements](https://docs.recurly.com/v1.1/docs/third-party-checkout#/) and [Recurly.js](https://docs.recurly.com/v1.2/docs/overview#/versions) via the [V3 API](https://recurly.com/developers/api/v2021-02-25/index.html).

#### Sandbox testing

Before going live, test Klarna Recurring through Payment Elements on your Recurly sandbox site to ensure that everything is functioning correctly.

When testing out BNPL and Pay Later, ensure you are testing with a plan with at least 2-3 month cycles (quarterly to be safe), otherwise the payment options will not appear and only ‘Pay Now’ will be an option for shorter billing cycles.