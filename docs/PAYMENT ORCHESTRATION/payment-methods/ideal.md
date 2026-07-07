---
title: iDEAL
excerpt: >-
  Accept iDEAL payments on Recurly for initial subscription payments from
  Netherlands customers — via Adyen or Stripe, with SEPA Direct Debit handling
  recurring renewals.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> iDEAL | Wero logo update</strong> Prior to March 31, 2026, Recurly will update all visible logos in the platform to display iDEAL's new combined branding — "iDEAL | Wero." Integrations on Adyen and Stripe will update automatically, as will logos in the Recurly Admin portal for billing infos, Recurly Wallet, and transaction details. No integration changes are required on your end.</div>
</div>

<div class="rp-page">
  <div class="rp-overview">iDEAL is the Netherlands' leading online payment method, used for over half of all online transactions in the region. It handles initial subscription payments by redirecting customers to their bank's site. Recurring renewals are managed through SEPA Direct Debit — make sure SEPA is enabled before integrating iDEAL.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">3</span>Checkout flow</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A supported iDEAL gateway: <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen</a> or <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://recurly.com/developers/guides/3rd-party-checkout.html" target="_blank">Third Party Checkout</a>).</li>
  <li><a href="https://docs.recurly.com/docs/sepa-1" target="_blank">SEPA Direct Debit</a> enabled with EUR currency configured — required for recurring renewals.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><strong>No free trials</strong> — iDEAL cannot facilitate free trials. Use SEPA Direct Debit for trial scenarios instead.</li>
  <li><strong>No future start dates</strong> — Subscriptions initiated via iDEAL cannot have a future commencement date.</li>
  <li><strong>No chargebacks</strong> — Chargeback handling is not supported by iDEAL.</li>
  <li><strong>Not available on Recurly Checkout or Hosted Payment Pages</strong>.</li>
  <li><strong>Payments cannot be reversed</strong>.</li>
</ul>

# Definition

<div class="rp-definition">iDEAL is the Netherlands' leading online payment method, handling the majority of online transactions in the country. Customers select their bank from a list of iDEAL-supported banks and complete payment on their bank's site. While iDEAL facilitates the initial payment, recurring transactions are managed through SEPA Direct Debit — iDEAL itself does not support recurring billing. See <a href="https://www.ideal.nl" target="_blank">ideal.nl</a> for a demo of the payment flow.</div>

# Key details

<div class="rp-card">

### Use cases

**Initial subscription payments** — iDEAL is well-suited for collecting the first payment of a subscription before handing recurring renewals to SEPA Direct Debit.

**Netherlands market** — Offering iDEAL gives you access to the most-used payment method in the Netherlands, reaching customers who prefer bank-based payments.

</div>

# Checkout flow

Add iDEAL as a payment option in your checkout and direct customers to select their bank from the available list. Customers are redirected to their bank's official site to authenticate and complete the payment, then returned to your site.
