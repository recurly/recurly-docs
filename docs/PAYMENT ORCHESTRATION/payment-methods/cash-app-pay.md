---
title: Cash App Pay
excerpt: >-
  Accept Cash App Pay on Recurly via Adyen (Recurly.js) or Stripe (Payment
  Elements) — supporting USD subscription sign-ups and QR code–based contactless
  payments.
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
  <div class="rp-overview">Cash App Pay is a contactless payment method that lets customers pay by scanning a QR code using their Cash App balance or linked debit card. Recurly supports Cash App Pay via Adyen (Recurly.js) and Stripe (Stripe Payment Elements via Third Party Checkout).</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">3</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An <a href="https://docs.recurly.com/docs/adyen#/" target="_blank">Adyen</a> gateway connection if integrating via Recurly.js.</li>
  <li>A <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> gateway connection if integrating via Stripe Elements.</li>
  <li>USD currency support on your site.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Supports transactions in USD only.</li>
  <li>Integration requires either Adyen + Recurly.js or Stripe + Stripe Payment Elements.</li>
  <li>100% coupons during signup are not supported — token creation is required for this payment method. Use a free trial instead. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">Cash App Pay is a contactless payment method available for subscription sign-ups and ecommerce purchases on Recurly. Customers pay by scanning a QR code using their Cash App balance or linked debit card — no bank account required. If the Cash App balance is insufficient, the customer's linked card is used automatically. Recurly supports Cash App Pay via <a href="https://docs.recurly.com/docs/adyen#/" target="_blank">Adyen</a> (Recurly.js) and <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>).</div>

# Key details

<div class="rp-card">

### Use cases

**Subscriptions** — Cash App Pay supports subscription sign-ups by letting customers pay with their Cash App balance or linked debit card via QR code.

**Checkout** — Customers on mobile and desktop can complete purchases without entering card details, using their existing Cash App account.

</div>

## Supported features

- **Cash App balance and linked debit card** — Customers can pay using their Cash App balance or a linked debit card. A linked bank account is not required. If the balance is insufficient, the linked card is charged automatically.
- **Recurly.js token support** — Use Cash App Pay Recurly.js tokens to process transactions via V2 or V3 Recurly endpoints (Adyen integration).
- **Stripe Elements token support** — Use Stripe Payment Elements and the V3 API to process transactions (Stripe integration).
- **Mobile and desktop support** — Supports transaction flows on both mobile and desktop platforms.

# FAQs

<Accordion title="Which gateways support Cash App Pay?">
  Cash App Pay is available through two gateway integrations:

  - <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen" target="_blank">Adyen (Recurly.js)</a>
  - <a href="https://docs.recurly.com/recurly-subscriptions/docs/third-party-checkout" target="_blank">Stripe (Stripe Elements — Third Party Checkout)</a>
</Accordion>

<br />
