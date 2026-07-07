---
title: PayPal on Adyen
excerpt: >-
  Enable PayPal payments through your Adyen gateway in Recurly for consolidated
  reporting and recurring payment support — requires explicit approval from both
  Adyen and PayPal.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">PayPal on Adyen lets you process PayPal payments through your existing Adyen gateway, consolidating payment reporting without needing a separate PayPal gateway. This integration requires explicit approval from both Adyen and PayPal before it can be enabled in Recurly.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Requires approval from both Adyen and PayPal — contact Recurly Support to request access</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#implementation-guide"><span class="rp-toc-num">4</span>Implementation guide</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">5</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An active PayPal business account and an active Adyen account.</li>
  <li>Adyen gateway already configured in Recurly. See the <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen gateway documentation</a> for setup details.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><strong>Migration to direct PayPal integrations is not supported</strong> — This integration uses Adyen tokens, which cannot be migrated to PayPal Business or PayPal Complete. Customers would need to re-enroll in subscriptions to switch gateways.</li>
  <li><strong>No access to PayPal BAID or Vault ID</strong> — Recurly does not have visibility into the underlying PayPal billing agreement ID or Vault ID.</li>
  <li><strong>Transaction amount restriction</strong> — PayPal does not allow transaction amounts between $0.01 and $0.48. Send transaction amounts of $0.50 or above when not offering free trials.</li>
</ul>

# Definition

<div class="rp-definition">PayPal on Adyen enables PayPal payments to be processed through the Adyen gateway, with aggregated reporting at the gateway level. It requires Adyen tokens and permissions granted directly to Adyen — not Recurly — to process on behalf of you and your customers. For more on the individual components, see the <a href="https://docs.recurly.com/docs/paypal-payments" target="_blank">PayPal payment method</a> and <a href="https://docs.recurly.com/docs/adyen" target="_blank">Adyen gateway</a> documentation.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-bar" aria-hidden="true"></i></div>
    <strong>Consolidated reporting</strong>
    <span>View PayPal and Adyen transaction data in one place — no need to cross-reference separate reporting dashboards.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Trusted processing</strong>
    <span>Payments are processed by both Adyen and PayPal, giving customers and merchants confidence in payment accuracy.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Fewer gateway configurations</strong>
    <span>Handle PayPal through your existing Adyen setup rather than maintaining a separate PayPal gateway in Recurly.</span>
  </div>
</div>

# Key details

You'll need your Adyen gateway already configured for PayPal payments and an active PayPal business account ready to connect. Granting Adyen permissions to your PayPal account happens outside of Recurly — follow the steps in <a href="https://docs.adyen.com/payment-methods/paypal/setup-paypal-direct-merchants/" target="_blank">Adyen's PayPal setup documentation</a>.

# Implementation guide

## Set up PayPal on Adyen

### Grant Adyen permissions

Follow all steps in <a href="https://docs.adyen.com/payment-methods/paypal/setup-paypal-direct-merchants/#permission" target="_blank">Adyen's permissions documentation</a> to authorize Adyen to process PayPal payments on your behalf (live and test environments).

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> PayPal's sandbox does not send email activation emails. To verify your PayPal email in sandbox, navigate within your PayPal sandbox account to locate and confirm the verification email manually. If you're having trouble enabling PayPal on Adyen, contact Adyen Support directly — there is an alternative method that is not publicly documented.</div>
</div>

### Enable PayPal on Adyen in Recurly

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Request the feature flag</h4><p>Contact Recurly Support to enable the PayPal on Adyen feature flag for your account. Proof of approval from both Adyen and PayPal will be required.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enable PayPal in gateway settings</h4><p>Once the feature flag is enabled, navigate to your Adyen gateway settings in Recurly and check the box to enable PayPal as an Alternative Payment Method.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/10a6f1b-image.png" align="center" width="75%" border={true} />


## Enable PayPal on Adyen via Recurly.js

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Integrate via the Alternative Payment Methods route</h4><p>Follow the <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank">Alternative Payment Methods documentation</a> for Recurly.js. Use the <strong>Purchase</strong> route — the Billing Info Update route is not supported and results in a poor customer experience.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Capture the customer's email address</h4><p>The customer's email address is required for all PayPal transactions processed via Adyen. Ensure your integration collects and passes this field.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Resolve permission errors with Adyen or PayPal</h4><p>If you encounter permission errors during testing or live processing, contact Adyen and/or PayPal directly. Recurly Support does not have access to permission settings in those systems.</p></div>
  </div>
</div>

# FAQs

<Accordion title="Does PayPal on Adyen support one-time and recurring payments?">
  Yes — merchants can process customer-initiated one-time transactions and set up recurring payments through PayPal on Adyen.
</Accordion>

<Accordion title="Can I migrate from PayPal on Adyen to a different PayPal gateway?">
  No. PayPal on Adyen uses gateway-specific Adyen tokens. Recurly does not have access to the underlying payment instrument or PayPal billing agreement ID / Vault ID. Migrations would require customers to re-enroll in their subscriptions.
</Accordion>

<Accordion title="Can I use a direct PayPal integration alongside PayPal on Adyen?">
  You can use any other gateway integration alongside Adyen regardless of payment method. However, PayPal on Adyen is not compatible with other PayPal gateway offerings in Recurly.
</Accordion>

<Accordion title="Which currencies are supported with PayPal on Adyen?">
  Recurly supports all PayPal-supported currencies within this integration. See <a href="https://developer.paypal.com/docs/reports/reference/paypal-supported-currencies/" target="_blank">PayPal's supported currencies list</a> for the full reference.
</Accordion>

<br />
