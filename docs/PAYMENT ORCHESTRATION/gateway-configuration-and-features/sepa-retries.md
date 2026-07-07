---
title: Direct debit retries
excerpt: >-
  Enable Recurly's automatic Direct Debit retry feature for ACH, BACS, BECS, and
  SEPA payments — retrying failed insufficient funds transactions up to twice,
  per NACHA, SEPA, and EU/AU regulations.
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
  <div class="rp-overview">Direct Debit retries automatically re-attempts ACH, BACS, BECS, and SEPA payments that fail due to insufficient funds — up to twice, in compliance with NACHA, SEPA, and EU/AU bank debit regulations. Available on Adyen, Stripe, GoCardless, and Worldpay (SEPA only).</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#setup"><span class="rp-toc-num">4</span>Setup</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">5</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An active Recurly account with one or more of the following payment methods enabled: SEPA Direct Debit, BACS, BECS, or ACH. Gateway support by method:
    <ul>
      <li>SEPA: Adyen, Stripe, GoCardless, Worldpay</li>
      <li>BACS: Adyen, Stripe, GoCardless</li>
      <li>ACH: Adyen, Stripe, GoCardless</li>
      <li>BECS: Stripe, GoCardless</li>
    </ul>
  </li>
  <li>Integration with <a href="https://docs.recurly.com/docs/adyen#/" target="_blank">Adyen</a>, <a href="https://docs.recurly.com/docs/stripe#/" target="_blank">Stripe</a> (via <a href="https://docs.recurly.com/docs/stripe-payment-elements#/" target="_blank">Stripe Payment Elements</a>), <a href="https://docs.recurly.com/docs/gocardless#/" target="_blank">GoCardless</a>, or <a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/" target="_blank">Worldpay</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Only retries transactions declined for insufficient funds — other failure reasons are not retried.</li>
  <li>Gateway-level retry services must be disabled to avoid double-charging customers. This includes Adyen's Auto Rescue and GoCardless Success+.</li>
  <li>Supported Direct Debit payments can only be retried twice, per NACHA, SEPA, and EU/AU regulations.</li>
  <li>Retry timing is fixed at 24 hours after a late failure notification — customization is not available.</li>
  <li>Retries do not occur if your dunning settings are configured to immediately expire subscriptions on failed payments.</li>
  <li>Check Commerce is not supported.</li>
  <li>ACH support is limited on Worldpay — the gateway does not return proper RX ACH Return codes.</li>
</ul>

# Definition

<div class="rp-definition">Direct Debit retries automatically re-attempts ACH, BACS, BECS, and SEPA payments that fail due to insufficient funds. Recurly schedules a retry 24 hours after the failure notification and allows up to two retries per invoice, in compliance with NACHA, SEPA, and EU/AU bank debit regulations. Retries are triggered by specific failure codes (SEPA: AM04 and MS03; ACH: R01). For more on the underlying payment methods, see: <a href="https://docs.recurly.com/docs/sepa-direct-debit#/" target="_blank">SEPA</a>, <a href="https://docs.recurly.com/docs/ach-bank-payments#/" target="_blank">ACH</a>, <a href="https://docs.recurly.com/docs/bacs#/" target="_blank">BACS</a>, <a href="https://docs.recurly.com/docs/becs#/" target="_blank">BECS</a>.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-clock" aria-hidden="true"></i></div>
    <strong>Reduced manual effort</strong>
    <span>Recurly retries failed bank payments automatically — no need to manually re-attempt or track failed invoices.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Minimized involuntary churn</strong>
    <span>Automatic retries recover more failed payments, retaining customers who would otherwise lapse due to a temporary funds issue.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-scale-balanced" aria-hidden="true"></i></div>
    <strong>Regulatory compliance</strong>
    <span>Retry limits are enforced in accordance with NACHA, SEPA, and other bank debit regulations — no manual counting required.</span>
  </div>
</div>

# Key details

## Retry behavior

- Recurly schedules a retry automatically 24 hours after a late failure notification for insufficient funds.
- Up to two retries are allowed per invoice after the initial failure, per regulatory limits.
- Invoices are marked Processing or Paid as payments progress, and Past Due if payment fails due to insufficient funds.
- Updating billing info to a new bank account resets the retry counter. If the customer switches to a different payment method after a failure, queued retries are canceled.

## Billing info updates

Updating billing information with a new bank account number resets the retry counter and process. If a customer switches to a different payment method after a failed bank payment, any scheduled retries are canceled and the new payment method is used for future transactions.

# Setup

## Enable Direct Debit retries

Navigate to **Configuration → Payment Settings** in Recurly. Check the appropriate checkbox for each gateway and payment method combination you want to enable retries for. The feature is off by default to avoid conflicts with any existing retry mechanisms.


<Image src="https://files.readme.io/75288e00f3469a1dd81db2cd3fd7565b260bd63ef94ba9c7385b26c04e1805bf-Screenshot_2025-06-26_at_1.55.21_PM.png" align="center" width="75%" border={true} />


## Invoice details with retries enabled

When Direct Debit retries are active, each invoice shows additional retry information:

- **Next attempt** — When the next retry will occur, if retries remain.
- **Remaining attempts** — Count of retries left (from 2 down to 0).

These fields are not visible before a payment fails. After a failure, the next scheduled attempt (24 hours post-failure) becomes visible, along with the **Attempt Collection** option for manual retry.


<Image src="https://files.readme.io/f4bccb6-image.png" align="center" width="75%" border={true} />


## Manual retry

Using **Attempt Collection** manually cancels any queued automatic retry. If this is the final allowed attempt, no further automated retries will be scheduled. After all attempts are exhausted, the invoice shows **Retry schedule completed** — no further attempts will be made against that bank account.


<Image src="https://files.readme.io/ef6ee5a-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/f98f733-image.png" align="center" width="75%" border={true} />


## Behavior when retries are disabled


<Image src="https://files.readme.io/83ffed4-Collection_Disabled.png" align="center" width="75%" border={true} />


When Direct Debit retries are turned off:

- **Remaining attempts** — Not shown in the Collection Info section. Merchants can still manually trigger Attempt Collection but should not exceed the mandated 2 retries.
- **Next attempt** — Shows "Retry schedule completed," indicating Recurly will not automatically retry. Original behavior is preserved — no automatic retries without explicit activation.

# FAQs

<Accordion title="Will I get webhooks for failed bank payments?">
  Yes — webhook events for failed bank account payments work the same way as other payment method failures. See the <a href="https://recurly.com/developers/reference/webhooks/#failed-payment" target="_blank">Recurly Webhooks documentation on Failed Payments</a> for details.
</Accordion>

<Accordion title="Will automatic retries start again if my customer updates to a new payment method?">
  Yes, if the new payment method supports retries. If the customer updates to a different bank account, retries resume where applicable. If they switch to a credit card, retries apply where card retries are supported.
</Accordion>

<Accordion title="Will automatic retries work on old failed invoices?">
  Only in certain cases. Retries apply to invoices that have not yet received a late failure for insufficient funds. If an invoice is already in a failed or past-due state when the feature is enabled, it will not be retried automatically. However, if the invoice returns to a Paid state (via a billing info update or manual attempt) and then fails again for insufficient funds, automatic retries will apply if attempts remain.
</Accordion>

<Accordion title="Do I need AutoRescue or Success+ to use this feature?">
  No. Recurly's Direct Debit retries are independent of gateway retry services. In fact, gateway-level retry services (Adyen's Auto Rescue, GoCardless Success+) must be disabled to avoid double-charging customers when this feature is enabled.
</Accordion>

<br />
