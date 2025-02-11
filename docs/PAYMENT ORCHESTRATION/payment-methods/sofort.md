---
title: Sofort (Klarna Debit Risk)
excerpt: >-
  Seamlessly integrate Sofort (Klarna Debit Risk), a dominant online banking
  payment method in regions including Germany and Austria, into your Recurly
  system, allowing for secure and efficient transactions in multiple currencies
  including EUR, CHF, and GBP.
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

> 📘 Sofort has been deprecated and migrated to Klarna Debit Risk as of Sept 30th, 2024.
>
> Ensure you are passing the customer's country in your integrations to Recurly.js before this date. No other changes are necessary.
>
> As a result of this deprecation, only merchants who had existing Sofort accounts with Adyen can continue to use this product. New merchant signups are not supported.

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites & supported gateways

* Recurly currently supports Sofort (Klarna Debit Risk) transactions through [Adyen](https://docs.recurly.com/docs/adyen).

* To incorporate Sofort (Klarna Debit Risk) into your payment method lineup, initiate with setting up the Adyen gateway, followed by configuring SEPA for recurring payments and enabling the necessary currencies in both Recurly and Adyen settings.

### Limitations

* Free trials: Sofort (Klarna Debit Risk) cannot be employed for free trials; SEPA Direct Debit is recommended in such cases.
* Recurly Checkout and Hosted Payment Pages: Sofort (Klarna Debit Risk) is incompatible with these pages. 
* Additional limitations can be found [here](https://docs.recurly.com/docs/adyen#limitations).

# Description

Sofort stands as a popular online banking payment solution in regions like Germany, Austria, Switzerland, and Belgium, supporting transactions in EUR, CHF, and GBP currencies. The payment process with Sofort is streamlined; customers simply select their country, provide their bank details, and finalize the payment through their bank. A demonstration of this payment method can be viewed [here](https://www.klarna.com/sofort/).

It should be noted that while Sofort can facilitate the initial payment, recurring payments are managed through SEPA, owing to Sofort’s inability to support recurring transactions.

# Use cases

* Initial Payments: Ideal for processing initial payments in subscriptions.
* European Market: Sofort opens up avenues in major European markets like Germany, Austria, Switzerland, and Belgium.

# Checkout flow

To enable Sofort in your checkout flow, ensure that your customers have the option to choose their country and enter their bank details to authorize the payment through their bank's platform, thereby enhancing the user experience.

### FAQs

### Which gateways support Sofort?

Adyen supports Sofort. Please see Adyen documentation for setup instructions for Sofort.
