---
title: Adyen Web Components
excerpt: >-
  Accept and tokenize Adyen Web Components in Recurly for a seamless, branded
  checkout experience powered by Recurly.js.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Adyen offers powerful tools to support quick and dynamic consumer checkout solutions via their Web Components. Recurly supports accepting the Adyen component state data into Recurly.js so you can submit the resulting token ID to our V3 API for secure payment processing.

### Prerequisites & limitations

* Requires a working Recurly.js integration and V3 API integration.
* Does **not** support Adyen’s app (iOS/Android) components or React/Native SDKs—only the Web Components for the listed payment methods are supported.

# Definition

Adyen Web Components are customizable UI elements for various payment methods. When paired with Recurly.js, you collect an Adyen “state data” on your site, pass it into Recurly.js to generate a Recurly.js `token_id`and then submit that to Recurly via API to complete one-time or recurring charges.

# Key benefits

* **Branded checkout**: Use Adyen’s Web Components to deliver a consistent, on-brand payment UI within your own site.
* **Seamless tokenization**: Leverage Recurly.js to turn Adyen state data into a reusable payment token for future renewals and one time charges (where supported).
* **Flexible billing updates**: Let customers update payment details via Adyen Components or any other Recurly payment solution (Checkout, HPP, Recurly.js).

# Key details

## Supported Features

* Build a custom checkout flow with Adyen Web Components and pass the component’s state data into Recurly.js.
* Recurly.js generates a token ID you submit to the V3 API—Recurly unpacks the encrypted Adyen data and sends the state data to Adyen to authorize and store payment details.
* Customers may update billing info through Adyen Components or via Recurly’s other payment solutions (Checkout, HPP, Recurly.js).
* Explore Adyen’s live demo: [Adyen Web Components Demo](https://www.mystoredemo.io/#/checkout)

<Image align="center" className="border" border={true} width="300px" src="https://files.readme.io/2e5c1d8c261f4d9d718ee6da88a975fdb279a0b8d951aa48112cbc179c42c1ba-Screenshot_2025-05-13_at_3.55.51_PM.png" />

Read more in our [Developer Hub guide](https://docs.recurly.com/recurly-subscriptions/v1.1/docs/third-party-checkout-guide-adyen-components#/).

## Supported payment methods

* **Cards**, **Apple Pay**, **Google Pay**, **Cash App Pay** (via Adyen Web Components).
* Note: Not all Adyen methods are supported—contact Recurly support for availability.