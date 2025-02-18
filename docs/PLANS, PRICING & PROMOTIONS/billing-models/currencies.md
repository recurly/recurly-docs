---
title: Currencies
excerpt: >-
  Boost your global reach with Recurly's multi-currency support. Simplify
  transactions, appeal to a broader customer base, and enhance your business
  growth.
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

### Prerequisites

Features 'Credit Invoices' and 'Only Bill What Changed' must be enabled to use the prepaid account balance.

# Definition

The ability to accept payments in a customer's local currency can significantly boost the performance of companies serving diverse geographic regions. Recurly simplifies the process of offering your plans in multiple currencies, giving customers the flexibility to choose their preferred payment denomination. With Recurly, the currency amount specified by you is presented to the customer and processed in the same currency via your payment gateway. Please note that Recurly does not perform currency conversions and that your merchant account might settle the transaction in a different currency.

# Key benefits

* **Broaden your customer base:** Support for 141 currencies opens up your business to a global audience, allowing you to cater to customers in their preferred local currency.
* **Simplified financial management:** With all charges and credits in the same currency on a single invoice, financial management becomes streamlined, saving you time and reducing complexity.
* **Enhanced customer experience:** Automatic selection of the most appropriate currency based on customer's geo-location improves user experience and boosts conversion rates.
* **Flexible pricing models:** The ability to define prices independently by currency provides you with the flexibility to optimize pricing strategies in different markets.

# Setting up multiple currencies

1. Following the activation of Multi Currency support on your Recurly account, you will need to define the currencies you wish to accept. Upon enabling a currency to your accepted list, you can set up pricing for your subscription plans and coupons in the new currency.

2. Once the currencies you accept are established, you need to update \[your existing subscription plans with prices in all your currencies. This setup permits independent price definitions for each currency.

3. It is essential to confirm that the currencies you accept are compatible with your configured payment gateways. The Currencies Configuration page shows the currencies that can be handled by your current gateway configuration.

4. Recurly recommends the activation of support for zero-dollar authorizations across all gateway accounts used to process non-USD currencies. This practice mitigates invalid amount errors that may result from exchange rate differences. For enabling zero-dollar verifications, refer to [this section](https://docs.recurly.com/docs/payment-gateways#section-zero-dollar-authorizations-zda) in our documentation.

# Specifying a currency

### Checkout

For Checkout's hosted page, when multiple currencies are accepted, you have a couple options. To learn more about currencies on Checkout, refer to [Currencies on Checkout](https://docs.recurly.com/docs/checkout#currencies).

### Hosted Payment Pages

Legacy hosted payment pages will default to the most suitable currency for your customer based on their country (identified through an automatic geo-IP address lookup).  To learn more, refer to [Currencies on Hosted Payment Pages](https://docs.recurly.com/docs/hosted-payment-pages#multi-currency).

### Recurly.js

Recurly.js forms allow a currency parameter, enabling currency specification when creating a new subscription or transaction. For additional details, refer to the [Recurly.js documentation](https://docs.recurly.com/js/).

## Invoices

All charges and credits on an invoice will be in the same currency. As Recurly does not perform currency conversion, *charges in different currencies cannot be combined on the same invoice*.

## Subscriptions

At the commencement of a new subscription, the currency is stored at the subscription level. *The currency of a subscription cannot be changed* once the subscription has begun. For a change of currency, the current subscription must be terminated, and a new one must be initiated.

## Payment gateway support for multiple currencies

Certain gateways may necessitate the creation of additional accounts to collect different currencies. For a list of currencies supported by each of our gateway integrations, visit [here](https://docs.recurly.com/docs/currency-support-by-gateway). Please contact your gateway for information tailored to your account.

| Payment Gateway                                                                                                                                                                                                                                                       |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Authorize.Net** accepts one currency per gateway account. To accept more than one currency with this gateway, you will need to open multiple accounts with the payment gateway. Please contact your payment gateway to enquire about accepting multiple currencies. |
| **Braintree** supports multiple currencies. Each currency requires a separate merchant account ID.                                                                                                                                                                    |
| **CyberSource** supports multiple currencies with a single account. Please contact CyberSource to enable additional currencies.                                                                                                                                       |
| **PayPal Payments Pro** and **PayFlow Pro** currencies are automatically configured for US, CA, and UK merchants based on the settings in your PayPal account (with the exception of the Japanese yen, which Recurly does not currently support).                     |
| **Stripe** supports multiple currencies with a single Stripe account, however, you will need to add an instance of the gateway (same credentials) for each currency you are approved to accept.                                                                       |
| **Vantiv** supports multiple currencies. Each currency requires a separate account.                                                                                                                                                                                   |

## Tax support

Tax region support is enabled independently of currency enablement. For more information on the tax regions presently supported on Recurly, please refer to our [tax documentation](https://docs.recurly.com/docs/tax).