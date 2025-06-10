---
title: 'Third Party Checkout: Stripe and Adyen'
excerpt: >-
  Enable a broad array of payment methods from Stripe and Adyen without leaving
  your Recurly-powered storefront.
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

By using the massive wealth of APMs built by our most trusted and well-established partners, you will be able to quickly and easily enable a wide range of payment options, catering to diverse customer preferences and expanding their potential market reach.

The ecommerce checkout options from our trusted gateway partners are designed to be user-friendly and highly customizable, allowing you to maintain a consistent brand experience while ensuring secure and reliable payment processing.

### Prerequisites & limitations

* Using Adyen Web Components will require a working Recurly V3 API integration and Recurly.js setup. Stripe Elements does not require Recurly.js, but will require a V3 API implementation.
* Third Party Checkout uses gateway tokens—migrating payment instruments to a different gateway requires coordination with the original gateway provider.
* Some APMs are country-restricted. If a method isn’t visible in your Stripe or Adyen dashboard, your merchant country of origin may not qualify for it (e.g. Revolut is available only to UK/EU merchants).

# Definition

Third Party Checkout: Stripe and Adyen lets you plug Stripe Payment Elements or Adyen Web Components into your Recurly checkout flow, unlocking local payment methods, wallets, and co-branded cards in a single integration.

# Key benefits

* **Broaden payment acceptance**: Offer cards, wallets, and regional APMs without building separate integrations.
* **Seamless brand consistency**: Widgets inherit your storefront styling for a cohesive experience.
* **Reliable security & compliance**: Leverage proven, PCI-compliant components from Stripe and Adyen under Recurly’s unified API.

# Key details

## Supported Gateways and Features

#### Stripe Gateway

* **Stripe Payment Elements** or **Express Checkout Elements** via Recurly V3 API.
* Read more about enabling Stripe Payment Elements in our [Third Party Checkout: Stripe Elements guide](https://docs.recurly.com/v1.1/docs/third-party-checkout-guide-adyen-components#/).

#### Adyen Gateway

* **Adyen Web Components** used alongside Recurly.js.
* Read more about enabling Adyen Web Components in our [Developer Hub guide](https://recurly.com/developers/guides/).