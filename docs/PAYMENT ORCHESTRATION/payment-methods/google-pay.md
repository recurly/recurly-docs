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

### Limitations

* **This feature works only in Google Chrome**. Other search engines/browsers are not supported.

### Best Practices and Compliance

* For return customers, please use Recurly.js even if an existing account code or billing info exists, as Recurly.js handles collecting device-related data necessary for customer-initiated transactions through Google Pay.
* Always request Merchant-level tokens (**MPANS**) for Google Pay, to comply with upcoming Visa MPAN requirement regulations. After July, 2025, Merchants should request MPANs in their Google Pay implementations to avoid declines. DPANs are grandfathered in, but are not guaranteed to continue functioning forever.

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