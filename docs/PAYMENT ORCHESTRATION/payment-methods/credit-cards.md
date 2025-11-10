---
title: Credit cards
excerpt: >-
  Harness the power and flexibility of Recurly's credit card processing
  solutions. Securely and efficiently handle your recurring transactions with
  support for a range of credit and debit card types, backed by the most popular
  gateways worldwide.
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

To use Recurly's credit card solutions, you'll need a merchant bank account and a payment gateway supported in your business location. Make sure to check the detailed gateway support section below.

### Supported credit card gateways

Explore detailed documentation for each gateway to ensure seamless integration with Recurly:

* [Adyen](https://docs.recurly.com/docs/adyen)
* [Authorize.net](https://docs.recurly.com/docs/authorizenet)
* [Braintree](https://docs.recurly.com/docs/braintree)
* [CardConnect](https://docs.recurly.com/docs/cardconnect)
* [Chase Paymentech Orbital](https://docs.recurly.com/docs/chase-paymentech-orbital)
* [CyberSource](https://docs.recurly.com/docs/cybersource)
* [First Data GGe4](https://docs.recurly.com/docs/additional)
* [Merchant eSolutions](https://docs.recurly.com/docs/additional)
* [Payeezy](https://docs.recurly.com/docs/additional)
* [PayPal Payflow Pro](https://docs.recurly.com/docs/additional)
* [PayPal Payments Pro](https://docs.recurly.com/docs/additional)
* [Stripe](https://docs.recurly.com/docs/additional)
* [TSYS](https://docs.recurly.com/docs/tsys)
* [Vantiv](https://docs.recurly.com/docs/additional)
* [Worldpay](https://docs.recurly.com/docs/worldpaydlocal-latam-support)

Refer to the above guides to ensure a successful setup and leverage the full potential of Recurly’s supported gateways for credit card transactions.

### Limitations

Recurly does not support Maestro cards for recurring transactions. Also, note that the availability of certain features may depend on your gateway and merchant account configurations.

# Definition

Recurly's credit card solution allows businesses to securely process credit and debit card payments with a seamless integration into an array of well-established gateways. This feature not only ensures the safety of transactions but also allows for the support of level II card data, facilitating lower interchange rates for US merchants.

# Checkout Flow

When a customer reaches the checkout stage, they will be prompted to enter their credit card details, including any relevant level II data if applicable. This information is used by Recurly to facilitate a safe and secure transaction process, with a direct link to the supported gateways. Refer to the gateway-specific guides for a step-by-step breakdown of the process.

# Use cases

**Subscriptions**: Whether you are a subscription service looking to streamline billing processes, or a retailer seeking to secure and facilitate your payment processes, Recurly's credit card solutions are designed to fit a myriad of business needs with ease and precision.

**One Time Payments**: If you're looking for a way to provide goods and services on a one-time payments basis, credit cards are a perfect avenue. 

**MOTO / Back office**: If you have a call center and would like to offer payments to customers calling in, you can do so with Recurly's MOTO support. See [MOTO](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/)  Processing for more details and check your gateway for specific support of this use case.

## Supported Credit Card

### Gateway Support

Your Recurly site supports various gateways based on your business location. For details on the gateways supported in your country, visit [our gateway page](http://recurly.com/gateways).

### Accepted Payment Types

Understand the importance of [offering alternative payment methods](https://recurly.com/blog/why-offering-alternative-payment-methods-is-important-for-subscription-businesses/) for your subscription business. Recurly backs most card types approved by your merchant bank account and payment gateway, except Maestro cards due to their lack of support for recurring transactions.

### Level II Card Data Support

All transactions process at level I rates by default. However, Recurly facilitates level II card data support for most gateways, granting lower interchange rates for qualified transactions for US merchants. To benefit from this, ensure your sales tax is calculated through Recurly. The necessary data fields included are:

* Sales tax amount (Enable taxes in your Recurly site!)
* Customer code / PO number (`po_number` via API)
* Merchant zip code (ensure your Business Entity and Site settings are up to date)

### Dual / Co-Badged Card Support

In compliance with [Article 8 of EU IFR Regulation 2015/751](https://eur-lex.europa.eu/eli/reg/2015/751/oj) pertaining to co-badged cards within the European Economic Area (EEA), it is mandated that when a cardholder utilizes a co-badged card and your system accommodates both brands, they must be given the option to select the preferred brand for payment.

Recurly offers dual-badged compliance on the following gateways:

* [Adyen](https://docs.recurly.com/docs/adyen#adyen-codual-badged-cards) (Cartes Bancaires, Bancontact, Dankort)
* [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe#/) (Cartes Bancaires, Bancontact)
