---
title: Currency support
excerpt: >-
  The Currency Support feature in Recurly is designed to help merchants manage
  and process transactions in multiple currencies. This capability ensures that
  businesses can accommodate various local currencies, enhancing their ability
  to serve a global customer base.
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

### Prerequisites

* Access to one or more supported payment gateways.
* Setup and configuration of the desired payment gateway(s) within Recurly.

### Limitations

* The range of supported currencies is dependent on the selected payment gateway(s).

# Definition

Recurly’s Currency Support feature provides merchants with the flexibility to manage transactions in a wide range of currencies. This capability is essential for businesses that operate in multiple countries or target customers in different regions, allowing them to offer prices in the local currency, which can improve customer satisfaction and conversion rates.

> **Note:** Not all gateways support all currencies. For a specific gateway's supported currencies, check our dedicated gateway pages. If "All available" is listed, the gateway supports all Recurly currencies listed below.

## Gateways with full currency support

These gateways allow you to accept payments in any currency within Recurly Commerce:

* **[Adyen](adyen)**: Supports most currencies, with special handling for Icelandic Króna (ISK) and Chilean Peso (CLP). **Does not support Indonesian Rupiah (IDR) or Cape Verdean Escudo (CVE).**

* **[Braintree](braintree-rd)**: Accepts every currency that PayPal supports—limited to PayPal’s own currency list.

* **[Commerce Hub](commerce-hub)** by Fiserv: Supports all.

* **[Cybersource](cybersource)**: Supports all.

* **[FreedomPay](freedompay)**: Supports all.

* **[Stripe](stripe)**: Supports all currencies; when using Gateway Failover, ensure the currency is enabled in both Stripe and Recurly.

* **[WorldPay Global E-Commerce](worldpaydlocal-latam-support)**: Seamless support for every currency. **Does not support Dominican Peso (DOP) or Nicaraguan Córdoba (NIO).**

# ISO standard currencies

| Currency |     |       |     |     |       |
| -------- | --- | ----- | --- | --- | ----- |
| AED      | BZD | GIP   | LRD | PEN | TJS   |
| AMD      | CAD | GMD   | LSL | PGK | TOP   |
| AOA      | CHF | GNF   | MAD | PHP | TRY   |
| ARS      | CLP | GTQ   | MDL | PKR | TTD   |
| AUD      | CNY | GYD   | MKD | PLN | TWD   |
| AWG      | COP | HKD   | MNT | PYG | TZS   |
| AZN      | CRC | HNL   | MOP | QAR | UAH   |
| BAM      | CVE | HRK   | MUR | RON | UGX   |
| BBD      | CZK | HTG   | MVR | RSD | USD   |
| BDT      | DJF | HUF   | MWK | RUB | UYU   |
| BGN      | DKK | IDR   | MXN | RWF | UZS   |
| \*BIF    | DOP | ILS   | MYR | SAR | VEF   |
| BMD      | DZD | INR   | MZN | SBD | \*VND |
| BND      | EGP | JMD   | NAD | SCR | \*VUV |
| BOB      | ETB | \*JPY | NGN | SEK | WST   |
| BRL      | EUR | KES   | NIO | SGD | \*XAF |
| BSD      | FJD | KGS   | NOK | SHP | XCD   |
| BWP      | FKP | \*KMF | NPR | SLL | \*XOF |
| BZD      | GBP | \*KRW | NZD | SOS | \*XPF |
| CAD      | GEL | KYD   | PAB | SRD | YER   |
| CHF      | GHS | KZT   | PEN | SVC | ZAR   |

> **Note**: \*Zero decimal currencies supported by Recurly.

## Definition for zero decimal currencies

Zero decimal currencies are those that do not require decimal places in their monetary value. These currencies are often used in regions where smaller units of currency are not commonly utilized in everyday transactions. Examples include the Japanese Yen (**JPY**), where prices are typically expressed as whole numbers without decimals.

#### Example with Japanese Yen (JPY)

In Japan, prices are expressed in whole numbers without any decimal places. For instance, an item might be priced at 1,000 JPY rather than 1,000.00 JPY. This practice simplifies transactions and is a key characteristic of zero decimal currencies. When dealing with these currencies in Recurly, merchants should be mindful that the system will process amounts as whole numbers, without any fractional currency.

## Zero decimal currencies supported by Recurly

| Currency |         |         |         |         |         |
| -------- | ------- | ------- | ------- | ------- | ------- |
| **BIF**  | **CLP** | **DJF** | **GNF** | **JPY** | **KMF** |
| **KRW**  | **PYG** | **RWF** | **UGX** | **VND** | **VUV** |
| **XAF**  | **XOF** | **XPF** |         |         |         |