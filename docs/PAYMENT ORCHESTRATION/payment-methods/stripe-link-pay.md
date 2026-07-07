---
title: Link Pay by Stripe
excerpt: >-
  Enable Link Pay by Stripe on Recurly to let customers auto-fill saved cards
  and US bank accounts at checkout — available exclusively via Stripe Payment
  Elements.
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
  <div class="rp-overview">Link Pay by Stripe is a proprietary Stripe wallet that auto-fills saved payment details at checkout, reducing cart abandonment and improving authorization rates. Customers can pay with saved cards, debit cards, or US bank accounts across any Link-enabled merchant. Link is available exclusively via Stripe Payment Elements.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">3</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A Stripe gateway connection.</li>
  <li>A Stripe Elements integration on your site.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>See <a href="https://docs.stripe.com/payments/link" target="_blank">Stripe's Link documentation</a> for full country availability and limitations. Link is not available in India. In Brazil and Thailand, Payment Elements do not support Link.</li>
  <li>Link with Direct Debit is limited to USD and US-based customers.</li>
  <li>Link customers cannot update their billing method through Recurly — they must visit <a href="https://link.com" target="_blank">link.com</a> to update their details.</li>
  <li>Link Pay is a Stripe-only offering and will not be available on other gateways.</li>
  <li>100% coupons during signup are not supported — token creation is required for this payment method. Use a free trial instead. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">Link Pay by Stripe is a proprietary wallet that auto-fills saved payment details across Link-enabled merchants, speeding up checkout for returning customers. Customers can select saved credit cards, debit cards, or US bank accounts at checkout. Link also supports Instant Bank Payments, with all transactions confirming immediately and settling to your Stripe balance on the same timeline as card payments. Customers can manage their Link account, view purchase history, or contact support at <a href="https://link.com" target="_blank">link.com</a>.</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Link Pay is supported only via Third Party Checkout through Stripe Payment Elements.</div>
</div>

# Key details

<div class="rp-card">

### Use cases

**Subscriptions** — Link enables sign-ups for customers globally, supporting cards and US bank accounts as payment methods.

**Faster checkout** — Saved payment details auto-fill at checkout for both mobile and desktop users, reducing friction and improving conversion.

</div>

## Supported features

- **Auto-fill at checkout** — Link auto-fills saved payment details when customers return to any Link-enabled merchant, eliminating re-entry of card or bank account information.
- **Stripe Payment Elements integration** — Uses Stripe Payment Elements and the V3 API for token handling and compatibility with this payment method.
- **Mobile and desktop support** — Fully supports transaction flows on both mobile and desktop.

# FAQs

<Accordion title="Which gateways support Link by Stripe?">
  Link by Stripe is available through Stripe Payment Elements (Third Party Checkout). See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/third-party-checkout#third-party-checkout" target="_blank">Third Party Checkout documentation</a> for setup details.
</Accordion>

<br />
