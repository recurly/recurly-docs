---
title: Google Pay™
excerpt: >-
  Leverage Google Pay™ with Recurly to offer a seamless and simplified checkout
  experience for your customers, facilitating transactions through payment
  details stored in their Google accounts.
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

Google Pay is a payment method that allows customers to pay with preferred payment methods stored in their Google account. Google Pay provides a simpler checkout flow whether customers are buying from using Google Chrome on web or using Android devices without having to enter their payment details each time.

### Prerequisites & supported gateways

* Before integrating Google Pay™ into your Recurly account, ensure you have a Google Merchant ID. Recurly currently supports Google Pay™ transactions through [Stripe](https://docs.recurly.com/docs/stripe), [Adyen](https://docs.recurly.com/docs/adyen), [Braintree](https://docs.recurly.com/docs/braintree),  [Worldpay](https://docs.recurly.com/docs/worldpaydlocal-latam-support), [Cybersource](https://docs.recurly.com/docs/cybersource#/), and [Chase Orbital](https://docs.recurly.com/docs/chase-paymentech-orbital) gateways.
* This payment method allows using [Zero Dollar Authorizations](https://docs.recurly.com/docs/payment-gateways#/zero-dollar-authorizations-zda).

### Definitions

* **FPAN**: An acronym for "Funding Primary Account Number". This is referencing the actual credit card number that is physically printed on the card itself. This is also referred to as just 'PAN' as well.
* **DPAN**: The acronym for "Device Primary Account Number". Some may also use 'Digital' in place of 'Device'. A DPAN is referring to the tokenized credit card number created by adding a consumer credit card to a Phone or Device "Wallet" system (such as Google Wallet) and is sent to gateways and processors in place of an actual FPAN. It is usually only functional when sent from that specific device, for example, the specific iPhone or iPad and typically is accompanied by a Cryptogram when a customer is in session.
  * The DPAN is tied to that specific device, for example, the specific Android Phone or Tablet and is accompanied by a Cryptogram when a customer is in session.
  * DPANs are full card numbers that have different set of numbers from the FPAN which can be exposed on receipts and other UI elements.
  * DPANs are invalidated when a consumer removes the card from their device, and a new DPAN is created if they re-add the same card, or add a new card to their device. Subscriptions using a DPAN can fail due to this consumer-driven behavior and are non-recoverable. 
* **Cryptogram**: A one-time use authentication value that is created in the processing of using Google Pay to authorize a transaction. Cryptograms are not stored and must be sent on all customer-initiated transactions.

### Limitations

* **This feature works only in Google Chrome**. Other search engines/browsers are not supported.

### Best Practices and Compliance

* For return customers, please use Recurly.js even if an existing account code or billing info exists, as Recurly.js handles collecting device-related data necessary for customer-initiated transactions through Google Pay.

### Limitations

Currently, Google Pay™ is not supported on Recurly Checkout or Hosted Payment Pages.

> 📘 Google Pay App was deprecated by Google on June 4, 2024.
>
> This does not extend to the Payment Method itself. Users can continue to enjoy payments with Google Pay through the Google Wallet app.

# Description

Google Pay™ is a prominent payment method, allowing customers to perform transactions with their preferred payment options readily available in their Google account. It ensures a simplified checkout process whether buying through Google Chrome on the web or Android devices.

### Use cases

* Web Purchases: Customers can utilize Google Pay™ for straightforward transactions while shopping on web browsers such as Google Chrome.
* Android Transactions: Enable swift and secure purchases for customers using Android devices without the need for entering payment details every time.

# Checkout Flow

#### Recurly.js Integration

To integrate Google Pay™, refer to the [Recurly.js documentation](https://developers.recurly.com/reference/recurly-js/index.html#google-pay) which guides through adding Google Pay™ as a payment method.

* **Note**: for return customers, please use Recurly.js even if an existing account code or billing info exists, as Recurly.js handles collecting device-related data necessary for customer-initiated transactions through Google Pay.
