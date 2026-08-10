---
title: Credit cards
excerpt: >-
  Process credit and debit card payments through Recurly across 14 supported
  gateways — with Level II data support, dual/co-badged card compliance, and
  MOTO processing.
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
  <div class="rp-overview">Recurly's credit card solution lets you process credit and debit card payments across a wide range of supported gateways. It supports subscriptions, one-time payments, and MOTO transactions, with optional Level II card data for lower interchange rates and dual/co-badged card compliance for EU merchants.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A merchant bank account and a Recurly-supported payment gateway for your business location — see <a href="#supported-gateways">Supported gateways</a> below.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Maestro cards are not supported for recurring transactions.</li>
  <li>One-time transactions where the card is not stored for future use are not supported.</li>
</ul>

# Definition

<div class="rp-definition">Recurly's credit card solution enables secure processing of credit and debit card payments across a broad range of gateways. When a customer reaches checkout, they enter their card details — including Level II data if applicable — and Recurly routes the transaction to the configured gateway. For gateway-specific checkout flows, refer to the individual gateway guides.</div>

# Key details

<div class="rp-card">

### Use cases

**Subscriptions** — Recurly's credit card support covers subscription billing, upgrades, and recurring charges across all supported gateways.

**One-time payments** — Credit cards can be used for one-time purchases of goods or services.

**MOTO / Back office** — For call center environments, Recurly supports MOTO (Mail Order / Telephone Order) transactions. See [MOTO Processing](https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/) for details, and check your gateway for specific MOTO support.

</div>

## Supported gateways

Recurly supports credit card processing through the following gateways. Visit each gateway's documentation for setup details.

- <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen</a>
- <a href="https://docs.recurly.com/docs/authorizenet" target="_blank">Authorize.Net</a>
- <a href="https://docs.recurly.com/docs/braintree" target="_blank">Braintree</a>
- <a href="https://docs.recurly.com/docs/cardconnect" target="_blank">CardConnect</a>
- <a href="https://docs.recurly.com/docs/chase-paymentech-orbital" target="_blank">Chase Paymentech Orbital</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub#/" target="_blank">Commerce Hub by Fiserv</a>
- <a href="https://docs.recurly.com/docs/cybersource" target="_blank">CyberSource</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/freedompay#/" target="_blank">FreedomPay</a>
- <a href="https://docs.recurly.com/docs/additional" target="_blank">Merchant eSolutions</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete#/" target="_blank">PayPal Complete</a>
- <a href="https://docs.recurly.com/docs/additional" target="_blank">Stripe</a>
- <a href="https://docs.recurly.com/docs/tsys" target="_blank">TSYS</a>
- <a href="https://docs.recurly.com/docs/additional" target="_blank">Vantiv</a>
- <a href="https://docs.recurly.com/docs/worldpaydlocal-latam-support" target="_blank">Worldpay</a>

For a full list of gateways by country, visit <a href="http://recurly.com/gateways" target="_blank">recurly.com/gateways</a>.

## Accepted payment types

Recurly supports most card types approved by your merchant bank account and payment gateway. Maestro cards are not supported for recurring transactions.

## Level II card data support

All transactions process at Level I rates by default. For US merchants, Recurly supports Level II card data on most gateways, which can qualify transactions for lower interchange rates.

To enable Level II processing, ensure the following data is present:

<ul class="rp-list">
  <li>Sales tax amount — enable taxes in your Recurly site</li>
  <li>Customer code / PO number — pass via the <code>po_number</code> API field</li>
  <li>Merchant zip code — keep your Business Entity and Site settings current</li>
</ul>

## Dual / co-badged card support

Under <a href="https://eur-lex.europa.eu/eli/reg/2015/751/oj" target="_blank">Article 8 of EU IFR Regulation 2015/751</a>, when a cardholder in the EEA uses a co-badged card and your system supports both card brands, you must give them the option to select their preferred brand at checkout.

Recurly provides dual/co-badged card compliance on the following gateways:

- <a href="https://docs.recurly.com/docs/adyen#adyen-codual-badged-cards" target="_blank">Adyen</a> — Cartes Bancaires, Bancontact, Dankort
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe#/" target="_blank">Stripe</a> — Cartes Bancaires, Bancontact

### New MasterCard and ELO Customer Authentication Compliance

MasterCard is implementing additional customer authentication requirements that will require merchants to enforce supplying customer data including:&#x20;

- **At least one contact detail**: cardholder name, email address or phone number
- **At least one address**: billing address or shipping address
- The **customer’s IP address**

Additionally, ELO in Brazil is implementing requirements to pass along the following:&#x20;

- Customer **Email address**, **Telephone number**, and **Address** information
- **Browser/device** information

For both card brand requirements, Recurly supports sending the required customer data via several integration paths, and Recurly.js is specifically built to capture customer IP and browser data by design. Consider a move to Recurly.js if you are under the jurisdiction of the above card brand compliance mandates.

<br />
