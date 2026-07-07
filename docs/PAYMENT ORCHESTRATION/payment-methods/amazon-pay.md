---
title: Amazon Pay
excerpt: >-
  Let customers pay using their Amazon account on your Recurly site — available
  in V1 (widgets) and V2 (redirect), with support for subscriptions,
  multi-currency, and Recurly.js integration.
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
  <div class="rp-overview">Amazon Pay lets customers pay using their existing Amazon account, providing a familiar checkout experience across your site. Recurly supports two versions: Amazon Pay V1 (inline widgets) and Amazon Pay V2 (redirect-based). Both integrate via Recurly.js and support subscriptions and multi-currency transactions.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">3</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An Amazon Pay gateway connection in Recurly, integrated via Recurly.js.</li>
  <li>Multi-currency support on your site, including USD, EUR, and GBP.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Supported currencies are determined by Amazon Pay — see Amazon Pay documentation for the full list.</li>
  <li>Integration requires Recurly.js and Amazon Pay gateway setup.</li>
  <li>100% coupons during signup are not supported — billing agreement creation is required for this payment method. Use a free trial instead. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">Amazon Pay lets customers use their Amazon account to pay for goods and services on your site. Recurly supports two versions: <strong>Amazon Pay V1</strong>, which uses inline widgets, and <strong>Amazon Pay V2</strong>, which uses a redirect-based flow. Amazon Pay widgets are not supported in V2. Both versions integrate via Recurly.js and support purchases, subscriptions, refunds, authorizations, and captures.</div>

# Key details

<div class="rp-card">

### Use cases

**Subscriptions** — Amazon Pay enables subscription sign-ups for customers who prefer paying with their Amazon account, including multi-currency support.

**Checkout** — Customers on mobile and desktop can complete purchases without re-entering payment details, using credentials already stored in their Amazon account.

</div>

## Supported features

- **Async and sync transactions** — Amazon Pay supports both asynchronous and synchronous payment flows, including purchases, refunds, authorizations, and captures.
- **Recurly.js token support** — Use Amazon Pay Recurly.js tokens to process transactions via V2 or V3 Recurly endpoints. Supported on Amazon Pay V2 only.
- **Mobile and desktop support** — Supports transaction flows on both mobile and desktop platforms.

# FAQs

<Accordion title="Which gateways support Amazon Pay?">
  Amazon Pay is available through its own gateway in two versions. See the individual gateway documentation for setup and troubleshooting:

  - <a href="https://docs.recurly.com/docs/amazon-payments" target="_blank">Amazon Pay V1</a>
  - <a href="https://docs.recurly.com/docs/amazon-pay-v2" target="_blank">Amazon Pay V2</a>
</Accordion>

<br />
