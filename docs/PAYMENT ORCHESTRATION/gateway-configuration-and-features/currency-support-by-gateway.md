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
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
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

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Not all gateways support all currencies. Check the individual gateway documentation for a specific gateway's supported currencies. If "All available" is listed, the gateway supports all Recurly currencies shown below.</div>
</div>

# Key details

## Gateways with full currency support

- **Adyen** \[TODO: add link] — Supports most currencies, with special handling for Icelandic Króna (ISK) and Chilean Peso (CLP). Does not support Indonesian Rupiah (IDR) or Cape Verdean Escudo (CVE).
- **Braintree** \[TODO: add link] — Accepts every currency that PayPal supports, limited to PayPal's own currency list.
- **Commerce Hub by Fiserv** \[TODO: add link] — Supports all currencies.
- **CyberSource** \[TODO: add link] — Supports all currencies.
- **FreedomPay** \[TODO: add link] — Supports all currencies.
- **Stripe** \[TODO: add link] — Supports all currencies. When using Gateway Failover, confirm the currency is enabled in both Stripe and Recurly.
- **Worldpay Global eCommerce** \[TODO: add link] — Supports all currencies. Does not support Dominican Peso (DOP) or Nicaraguan Córdoba (NIO).

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

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Currencies marked with an asterisk (*) are zero decimal currencies supported by Recurly.</div>
</div>

# Zero decimal currencies

Zero decimal currencies do not use decimal places in their monetary values. These are common in regions where fractional currency units aren't used in everyday transactions. For example, Japanese Yen (JPY) prices are expressed as whole numbers — an item costs 1,000 JPY, not 1,000.00 JPY.

When processing zero decimal currencies in Recurly, amounts are handled as whole numbers with no fractional component.

## Zero decimal currencies supported by Recurly

| Currency |         |         |         |         |         |
| -------- | ------- | ------- | ------- | ------- | ------- |
| **BIF**  | **CLP** | **DJF** | **GNF** | **JPY** | **KMF** |
| **KRW**  | **PYG** | **RWF** | **UGX** | **VND** | **VUV** |
| **XAF**  | **XOF** | **XPF** |         |         |         |

<br />
