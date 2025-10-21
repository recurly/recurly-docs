---
title: LATAM Payment Methods
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This document provides detailed API instructions for processing payments via Boleto, Pix Automático, Mercado Pago, and traditional Cards, with a critical focus on navigating the region's mandatory Tax ID requirements. You'll find the specific parameters and validation logic required to correctly collect country-specific identifiers—such as Brazil's CPF/CNPJ, Argentina's CUIT, and Chile's RUT—ensuring your integration is fully compliant, reduces transaction declines, and provides a seamless checkout experience for your customers across LATAM.

## Key Details 

There are several gateways and payment methods that support the LATAM region including Adyen, Ebanx, WorldPay, and Braintree. 

**Payment Methods and Gateways:**

* **Boleto**: Supported on Adyen
* **Mercado Pago**: Supported on Ebanx
* **Pix Automatico**: Supported on Ebanx
* **Cards with Tax ID requirements**: Supported on WorldPay and Braintree 

Additionally, some LATAM card integrations will require 3DS in certain cases. Both WorldPay and Braintree support 3DS. You can find this information separately in our 3DS Integration Guide.

<br />
