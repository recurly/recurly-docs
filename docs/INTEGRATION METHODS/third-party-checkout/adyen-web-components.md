---
title: Adyen Web Components
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Adyen offers powerful tools to support quick and dynamic consumer checkout solutions including their Web Components for various payment methods. Recurly supports accepting the Adyen state component data into Recurly.js so that you can submit the r.js token ID to us via API.

## Supported Features

Adyen Web Components Payment  is currently supported when used in conjunction with Recurly.js and our supported API suite. Visit our [developer hub](https://recurly.com/developers/guides/) for more information:

<Image align="center" className="border" border={true} width="300px" src="https://files.readme.io/bd6ee4314c74650eada8d5e8a62c0318b14857d22b69644925b570645a5a4e61-Stripe_Payment_element.png" />

* When using Adyen Web Components, you can build a custom checkout solution and pass the Adyen "state data" to Recurly.js and then use the resulting token ID via API. Recurly will pass unpack the token ID and pass the state data to Adyen to obtain reusable payment details for recurring and one-time payments.
* If customers wish to update their billing information, they can do so through Adyen Components, or through an existing Recurly solution such as Checkout, HPP, or Recurly.js. What you choose to offer is up to you!

Read more about enabling Adyen Web Components in the [Developer Hub guide](https://recurly.com/developers/guides/third-party-checkout-adyen-components.html).

### Supported Payment Methods

* **Adyen gateway**: Recurly does not support all Adyen payment methods at this time. Presently, the below options are available:
  * Cards, Apple Pay, Google Pay, Cash App Pay

### Limitations

* **Adyen gateway**: We do not support Adyen's app components or React/Native options.