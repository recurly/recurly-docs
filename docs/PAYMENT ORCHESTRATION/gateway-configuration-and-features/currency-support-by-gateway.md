---
title: Currency support
excerpt: >-
  An overview of currencies supported by Recurly — including gateway-specific
  currency availability, ISO standard currencies, and zero decimal currency
  handling.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Recurly supports a wide range of currencies to help merchants accept payments in customers' local currency. The specific currencies available depend on your payment gateway — some gateways support all Recurly currencies, while others have a more limited set.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#gateway-currency-support"><span class="rp-toc-num">2</span>Gateway currency support</a>
    <a class="rp-toc-pill" href="#iso-standard-currencies"><span class="rp-toc-num">3</span>ISO standard currencies</a>
    <a class="rp-toc-pill" href="#zero-decimal-currencies"><span class="rp-toc-num">4</span>Zero decimal currencies</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Access to one or more supported payment gateways.</li>
  <li>Gateway(s) set up and configured in Recurly.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Supported currencies depend on the payment gateway(s) you have configured.</li>
</ul>

# Definition

<div class="rp-definition">Recurly's currency support lets merchants manage transactions in a wide range of currencies — essential for businesses operating across multiple countries or targeting customers in different regions. Offering prices in local currency can improve customer satisfaction and conversion rates.</div>

<div class="rp-callout rp-callout-note"><div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Not all gateways support all currencies. Check the individual gateway's documentation for its supported currencies. When "All available" is listed below, the gateway supports every Recurly currency in the ISO standard list.</div></div>

# Gateway currency support

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Gateway</td><td>Supported currencies</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen" target="_blank">Adyen</a></td><td>Most currencies, with special handling for Icelandic Króna (ISK) and Chilean Peso (CLP). Does not support Indonesian Rupiah (IDR) or Cape Verdean Escudo (CVE).</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd" target="_blank">Braintree</a></td><td>Every currency PayPal supports — limited to PayPal's own currency list.</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub" target="_blank">Commerce Hub by Fiserv</a></td><td>All available.</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/cybersource" target="_blank">CyberSource</a></td><td>All available.</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/freedompay" target="_blank">FreedomPay</a></td><td>All available.</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe" target="_blank">Stripe</a></td><td>All available. When using Gateway Failover, confirm the currency is enabled in both Stripe and Recurly.</td></tr>
  <tr><td><a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support" target="_blank">Worldpay Global eCommerce</a></td><td>All available, except Dominican Peso (DOP) and Nicaraguan Córdoba (NIO).</td></tr>
</table>

# ISO standard currencies

Recurly supports the following ISO 4217 currency codes across its gateways. Codes marked with an asterisk (\*) are zero decimal currencies.

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

<div class="rp-callout rp-callout-note"><div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Currencies marked with an asterisk (*) are <a href="#zero-decimal-currencies">zero decimal currencies</a> supported by Recurly.</div></div>

# Zero decimal currencies

Zero decimal currencies do not use decimal places in their monetary values. These are common in regions where fractional currency units aren't used in everyday transactions. For example, Japanese Yen (JPY) prices are expressed as whole numbers — an item costs 1,000 JPY, not 1,000.00 JPY.

When processing zero decimal currencies in Recurly, amounts are handled as whole numbers with no fractional component.

## Zero decimal currencies supported by Recurly

| Currency |         |         |         |         |         |
| -------- | ------- | ------- | ------- | ------- | ------- |
| **BIF**  | **CLP** | **DJF** | **GNF** | **JPY** | **KMF** |
| **KRW**  | **PYG** | **RWF** | **UGX** | **VND** | **VUV** |
| **XAF**  | **XOF** | **XPF** |         |         |         |
