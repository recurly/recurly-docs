---
title: NACHA verification
excerpt: >-
  Meet NACHA bank account verification requirements for ACH in Recurly — with
  built-in support via Adyen (Giact), Stripe (Financial Connections), and
  Worldpay, plus guidance for external verification with GoCardless and Check
  Commerce.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">NACHA requires merchants accepting ACH web (online) debits to verify consumer bank account details before processing. Recurly supports this through built-in verification flows on Adyen, Stripe, and Worldpay, and provides guidance for external verification on other ACH gateways.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Access to one or more supported ACH payment gateways, or</li>
  <li>A direct integration with an ACH verification provider such as Plaid or Giact.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Only new bank accounts are subject to pre-verification. Bank accounts already on file are not re-verified.</li>
  <li>Adyen requires Giact for NACHA verification.</li>
  <li>Stripe requires Financial Connections and does not support externally verified bank accounts.</li>
</ul>

# Definition

<div class="rp-definition">Recurly's bank account verification support lets merchants verify consumer ACH bank details in the United States before processing a transaction or setting up a subscription — specifically when a new bank account is being provided. This is required for US merchants accepting ACH transactions under NACHA regulations. See <a href="https://www.nacha.org/system/files/2023-04/Account-Validation-FAQs-Oct-19-2020.pdf" target="_blank">NACHA.org</a> and their <a href="https://www.nacha.org/content/account-validation-resource-center" target="_blank">Account Validation best practices guide</a> for the full regulatory requirements.</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Not all gateways support built-in pre-verification. For ACH gateways without built-in support, external verification must be completed before sending bank details to Recurly for processing.</div>
</div>

# Key details

## Gateways with built-in NACHA verification

### Adyen

Enable **Giact** with your Adyen account and enable the feature in your Adyen gateway configuration in Recurly.


<Image src="https://files.readme.io/6fb1bfb995b6d992d1869d03bc8d0de195bf3b3e64418cc208a097abb5b0fafb-Screenshot_2025-07-29_at_4.11.19_PM.png" align="center" width="75%" border={true} />


See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen" target="_blank">Adyen documentation</a> for setup details.

### Stripe

Use **Stripe Elements** with Stripe's **Financial Connections** platform to pre-verify bank account details. External verification is not supported on the Stripe gateway.

See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe" target="_blank">Stripe documentation</a> for setup details.

### Worldpay

Worldpay's integration automatically supports pre-verification when a new bank account is provided to Recurly via Recurly.js, the API, or any other supported ACH mechanism. Bank accounts already stored on the same Recurly site are not re-verified. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/" target="_blank">Worldpay documentation</a> for setup details.

## Gateways requiring external pre-verification

The following gateways require you to verify bank accounts using an external provider before adding billing information to Recurly:

- <a href="https://docs.recurly.com/docs/gocardless" target="_blank">GoCardless</a>
- <a href="https://docs.recurly.com/docs/check-commerce" target="_blank">Check Commerce</a>

## Suggested flow for external verification

You may use an external provider (e.g., Plaid or micro-transaction verification) for any Recurly-supported ACH gateway — excluding Stripe — to verify bank accounts before adding billing information to Recurly.

Best practice is to verify any new bank account provided by a consumer to confirm it can be used for a WEB (online) debit transaction. The direct language from the NACHA mandate (effective March 2021) is:

> Validate first-use consumer account information for consumer debit payments authorized or initiated over an online channel (often called WEB Debits).

If your external integration confirms a consumer's bank account is valid for online processing and can be debited, you may proceed with your existing Recurly billing flow.
