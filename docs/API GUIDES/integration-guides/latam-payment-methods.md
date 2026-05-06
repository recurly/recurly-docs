---
title: LATAM Payment Methods
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This document provides detailed API instructions for processing payments via Boleto, Pix Automático, Mercado Pago, and traditional Cards, with a critical focus on navigating the region's mandatory Tax ID requirements. You'll find the specific parameters and validation logic required to correctly collect country-specific identifiers—such as Brazil's CPF/CNPJ, Argentina's CUIT, and Chile's RUT—ensuring your integration is fully compliant, reduces transaction declines, and provides a seamless checkout experience for your customers across LATAM.

# Key Details

There are several gateways and payment methods that support the LATAM region including Adyen, Ebanx, WorldPay, and Braintree.

**Payment Methods and Gateways:**

* **Boleto**: Supported on Adyen (Pending Deprecation)
* **Mercado Pago**: Supported on Ebanx
* **Pix Automatico**: Supported on Ebanx
* **Cards with Tax ID requirements**: Supported on WorldPay and Braintree

Additionally, some LATAM card integrations will require 3DS in certain cases. Both WorldPay and Braintree support 3DS. You can find this information separately in our 3DS Integration Guide.

# Payment Methods

## Credit Cards

Generally speaking, when processing cards in the LATAM region, you can follow standard guides (see below), however most LATAM countries require sending the Tax ID of the consumer. We offer a way to collect this data, and store it for future reference on renewals and stored details.

You can find API documentation for sending Tax IDs and Tax ID Types in our V3 API in several endpoints.

* Documentation

**Fields to look for:**

* `tax_identifier`: This is the Tax ID Number for the consumer. It is required when servicing LATAM customers.
* `tax_identifier_type`: This is the Tax ID Type for the specific tax ID being sent in the payload. You only need to send this when the value is `cpf` or `cnpj`. Otherwise, only send the Tax ID.

Certain LATAM regions also require 3D Secure when processing with cards. Ensure you are following new customer and stored billing info 3DS guides appropriately given your situation:

* [3DS for New Customers](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/)
* [3DS for Returning Customers (Stored billing info)](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information#/)

## Wallets

Recurly supports two Wallet payment methods on Ebanx including Mercado Pago and Pix Automatico. Certain wallets also require Tax ID collection, like credit cards (see params above), in addition to customer address, name, email information.

### Mercado Pago

Mercado Pago is supported on Ebanx, and requires the integrator to handling the Recurly.js token and 3DS Action token in their checkout flow for a customer to interact with the pop up modal. Keep in mind, sandbox behavior differs from production. 

Mercado Pago requires usage of our V3 APIs and Recurly.js. See our dedicated Mercado Pago integration guide for details. 

* [Mercado Pago integration guide](https://docs.recurly.com/recurly-subscriptions/docs/mercado-pago-integration-guide)

### Pix Automatico

Pix Automatico is supported on Ebanx, and requires the integrator to render the returned QR code in their checkout flow for a customer to scan. You may do this in any fashion you like, such as an on-page view. However, sandbox behavior differs from production.

Pix Automatico requires usage of our V3 APIs, and specifying the `type` field with an enum of `pix_automatico`. The initial response to a subscription integration will be a QR code that your system will need to render. Read more on the dedicated integration guide.

* [Pix Automatico Integration guide](https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico-integration-guide)

## Boleto

Boleto, supported on Adyen only presently, uses a special Email Template to deliver the Boleto Voucher QR code to customers via email. Due to the emailed communications, ensure you have your customer's real email on file.

You can follow specific instructions available in our Adyen documentation below:

* [Adyen | Boleto on Recurly](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-boleto)
* [Boleto via Recurly.js](https://docs.recurly.com/recurly-subscriptions/docs/boleto-ideal-sofort-and-cashapp#/boleto)

# Recommended Webhooks

In the LATAM region, some payment methods are synchronous and some are Asynchronous. You can find our dedicated webhooks recommendations using the Best Practices guide below:

It is recommended to listen for all webhooks given that some payment methods are asynchronous (they update hours or days later with an official status), and some are synchronous (the payment status is known immediately).

* [Webhooks Best Practices](https://docs.recurly.com/recurly-subscriptions/docs/best-practices#/)

<br />
