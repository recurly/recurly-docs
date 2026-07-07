---
title: Prepaid and gift cards
excerpt: >-
  Accept prepaid Visa, Mastercard, and other network-branded cards on Recurly
  using any card-supporting gateway — with guidance on AVS limitations, free
  trial risk, and blocking prepaid cards.
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
  <div class="rp-overview">Prepaid cards — both reloadable and non-reloadable — work like standard credit or debit cards on Recurly. No special checkout flow is required. This page covers how prepaid cards behave, their limitations, and how to block them if needed. For Recurly-issued gift cards, see the <a href="https://docs.recurly.com/docs/gift-cards" target="_blank">Gift Cards documentation</a>.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#enable-prepaid-card-acceptance"><span class="rp-toc-num">3</span>Enable prepaid card acceptance</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">4</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Any Recurly-supported payment gateway that processes credit or debit cards. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/credit-cards" target="_blank">Credit cards</a> for the full list of supported gateways.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><strong>AVS checks often fail on prepaid cards</strong> — Prepaid cards are typically not linked to a specific bank account or the cardholder's address, and few consumers register their prepaid cards with an address. This means AVS verification will frequently fail for these cards.</li>
  <li><strong>Non-reloadable cards deplete</strong> — Non-reloadable prepaid cards have a fixed balance. Once depleted, customers need a different payment method to keep their subscription active. Initial approval when adding a card does not guarantee future approvals.</li>
  <li><strong>Increased free trial abuse risk</strong> — Accepting prepaid cards can lead to free trial abuse. Some gateways offer the option to block prepaid cards by BIN if this is a concern.</li>
</ul>

# Definition

<div class="rp-definition">Prepaid cards are network-branded payment cards — issued by Visa, Mastercard, and other major networks — that come in two forms: reloadable (funds can be added) and non-reloadable (fixed balance). Unlike store gift cards, prepaid cards are not restricted to a specific retailer and can be used anywhere the card network is accepted. On Recurly, prepaid cards function identically to standard credit or debit cards — no special checkout configuration is required.</div>

# Key details

<div class="rp-card">

### Use cases

**Non-reloadable prepaid cards** — These cards, often in Visa or Mastercard Debit form, are commonly used as gift money for birthdays and holidays. Recipients can use them to purchase items or services at retailers and online, including subscriptions.

**Reloadable prepaid cards** — Reloadable cards function like debit cards but don't require a US bank account. Customers can add funds at a retailer using cash and then use the balance for online purchases and subscriptions — making them useful for customers without traditional bank accounts.

</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Checkout flow</strong> There is no special checkout flow for prepaid cards — they process identically to standard credit or debit cards. For Recurly-issued gift cards with a dedicated checkout flow, see the <a href="https://docs.recurly.com/docs/gift-cards" target="_blank">Gift Cards documentation</a>.</div>
</div>

# Enable prepaid card acceptance

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Enable a card-supporting gateway</h4><p>Select any Recurly-supported gateway that processes credit or debit cards. Ensure prepaid card blocking is not enabled at the gateway level (where that setting is available) if you want to accept prepaid cards.</p></div>
  </div>
</div>

# FAQs

<Accordion title="Can I block prepaid cards if I don't want to accept them?">
  Yes — two options are available. The simplest is to activate <a href="https://docs.recurly.com/docs/fraud-management#kount-enterprise" target="_blank">Kount</a>, a fraud management service that can block prepaid cards on your site. Contact Recurly Support to set up Kount.

  Alternatively, consult your payment gateway provider directly — many gateways have settings to block prepaid cards by identifying and refusing cards issued by prepaid card BINs (Bank Identification Numbers).
</Accordion>

<br />
