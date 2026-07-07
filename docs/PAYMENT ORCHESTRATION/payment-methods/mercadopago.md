---
title: Mercado Pago
excerpt: >-
  Accept Mercado Pago payments on Recurly via Ebanx for subscription sign-ups in
  Brazil, Argentina, Chile, Mexico, and Uruguay — with automatic retries and
  Recurly.js integration.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Mercado Pago is Latin America's leading digital payment platform, available on Recurly via Ebanx for subscription sign-ups across Brazil, Argentina, Chile, Mexico, and Uruguay. It supports BRL, ARS, CLP, MXN, and UYU, with customers authorizing payments through their bank app or Mercado Pago wallet.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">3</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An <a href="https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway" target="_blank">Ebanx</a> gateway connection with Recurly.js integration.</li>
  <li>One of the following currencies enabled on your site: BRL, ARS, CLP, MXN, or UYU.</li>
  <li>Supported countries: Brazil, Argentina, Chile, Mexico, and Uruguay.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Supported currencies: BRL, ARS, CLP, MXN, and UYU only.</li>
  <li>One-time transactions and force collections are not supported — only subscription sign-ups and automatic renewals.</li>
  <li>The following features are not supported: invoice/calendar aggregation, parent/child accounts, multiple subscriptions per account, proration during subscription upgrades or changes, and funds verification/wallet payment instrument visibility.</li>
  <li>100% coupons during signup are not supported — e-mandate creation is required for this payment method. Use a free trial instead. Standard coupons are supported.</li>
</ul>

# Definition

<div class="rp-definition">Mercado Pago is a digital payment platform and fintech ecosystem owned by Mercado Libre, widely used across Latin America. It supports credit cards, debit cards, bank transfers, cash vouchers, and digital wallet payments. On Recurly, Mercado Pago is available exclusively for subscription sign-ups via Recurly.js and the Ebanx gateway — one-time transactions are not supported.</div>

# Key details

<div class="rp-card">

### Use cases

**Subscriptions** — Mercado Pago supports subscription sign-ups and automatic renewals for customers in Brazil, Argentina, Chile, Mexico, and Uruguay.

**Multi-currency LATAM checkout** — Accept payments in five local currencies with customers authorizing through their bank app or Mercado Pago wallet, on mobile or desktop.

</div>

## Supported features

- **Subscription sign-ups** — Customers use their Mercado Pago wallet to subscribe. One-time transactions are not supported.
- **Recurly.js token support** — Use Mercado Pago Recurly.js tokens to process transactions via V3 Recurly endpoints.
- **Mobile and desktop support** — Supports transaction flows on both mobile and desktop.
- **Automatic retries** — Up to 3 retry attempts after a renewal failure, triggered automatically when the payment method response indicates insufficient funds or a payment cancellation. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/static-retries#/specialized-retry-strategies" target="_blank">Static Retry documentation</a> for details.

## Customer bank interactions

Customers can cancel their subscription enrollment directly from within their banking app. Revoking an enrollment cancels the active subscription in Recurly immediately.

## Required fields

Always send the following customer data with Mercado Pago transactions:

- Customer billing address
- Customer email address
- Customer phone number
- Tax ID and Tax ID type (required for Brazil)

# FAQs

<Accordion title="Which gateways support Mercado Pago?">
  Mercado Pago is supported through <a href="https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway" target="_blank">Ebanx</a>. See the Ebanx documentation for setup and troubleshooting details.
</Accordion>

<Accordion title="I'm trying to make a one-time purchase with Mercado Pago. Why isn't it working?">
  Mercado Pago on Recurly is built specifically for recurring subscriptions via Mercado Pago Connect. One-time transactions and force collections are not supported.
</Accordion>

<Accordion title="How do I integrate Mercado Pago into my checkout?">
  Mercado Pago is supported through Recurly.js and the V3 API. See the following resources:

  - <a href="https://recurly.com/developers/api/v2021-02-25/index.html" target="_blank">V3 API Guide</a>
  - <a href="https://docs.recurly.com/recurly-subscriptions/docs/overview-recurlyjs#/" target="_blank">Recurly.js Overview</a>
  - <a href="https://docs.recurly.com/recurly-subscriptions/docs/mercado-pago-integration-guide" target="_blank">Mercado Pago Integration Guide</a>
</Accordion>

<br />
