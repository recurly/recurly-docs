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

* **Boleto**: Supported on Adyen
* **Mercado Pago**: Supported on Ebanx
* **Pix Automatico**: Supported on Ebanx
* **Cards with Tax ID requirements**: Supported on WorldPay and Braintree

Additionally, some LATAM card integrations will require 3DS in certain cases. Both WorldPay and Braintree support 3DS. You can find this information separately in our 3DS Integration Guide.

# Payment Methods

## Credit Cards

Generally speaking, when processing cards in the LATAM region, you can follow standard guides (see below), however most LATAM countries require sending the Tax ID of the consumer. We offer a way to collect this data, and store it for future reference on renewals and stored details.

You can find API documentation for sending Tax IDs and Tax ID Types in our V3 API in several endpoints.

* Documentation

**Fields to look for: **

* `tax_identifier`: This is the Tax ID Number for the consumer. It is required when servicing LATAM customers.
* `tax_identifier_type`: This is the Tax ID Type for the specific tax ID being sent in the payload. You only need to send this when the value is `cpf` or `cnpj`. Otherwise, only send the Tax ID.

Certain LATAM regions also require 3D Secure when processing with cards. Ensure you are following new customer and stored billing info 3DS guides appropriately given your situation: 

* [3DS for New Customers](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/)
* [3DS for Returning Customers (Stored billing info)](https://docs.recurly.com/recurly-subscriptions/docs/using-3d-secure-with-stored-billing-information#/)

## Wallets

Recurly supports two Wallet payment methods on Ebanx including Mercado Pago and Pix Automatico.

### Mercado Pago

<br />

### Pix Automatico

<br />

## Boleto

Boleto, supported on Adyen only presently, uses a special Email Template to deliver the Boleto Voucher QR code to customers via email. Due to the emailed communications, ensure you have your customer's real email on file.

You can follow specific instructions available in our Adyen documentation below:

* [Adyen | Boleto on Recurly](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-boleto)
* [Boleto via Recurly.js](https://docs.recurly.com/recurly-subscriptions/docs/boleto-ideal-sofort-and-cashapp#/boleto) 

# Recommended Webhooks 

In the LATAM region, some payment methods are synchronous and some are Asynchronous. You can find our dedicated webhooks recommendations using the payment method / type guide below:  

* Asynchronous Webhooks guide: for supporting Wallet and Boleto payment methods 
* Synchronous Webhooks guide: for supporting Card payment methods
