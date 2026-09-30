---
title: dLocal (Philippines)
excerpt: >-
  Configure the dLocal payment gateway in Recurly to process one-time and
  recurring subscription payments with the GCash wallet in the Philippines.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">dLocal is a gateway platform focused on emerging markets in Asia, Africa, the Middle East, and Latin America (LATAM). Integrating it with Recurly lets you process one-time and recurring subscription payments via the GCash wallet payment method used in the Philippines. An existing dLocal relationship is required to enable this integration.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">3</span>FAQs</a>
  </div>
</div>

### Limitations

<ul class="rp-list">
  <li><strong>GCash billing info updates not supported</strong> — If a customer needs to update their wallet funding source, they must do so in the app itself.</li>
  <li><strong>No ad-hoc or one-time purchases using stored billing info</strong> — Customer-initiated one-time purchases using stored billing info and merchant-initiated force collections are not supported.</li>
  <li><strong>Chargebacks not reflected</strong> — Chargebacks are not currently supported or reflected in Recurly.</li>
  <li><strong>GCash one-time payments don't store billing info by design</strong> — Customers must reauthenticate via Recurly.js every time.</li>
  <li><strong>Free trials</strong> — Free trials are not yet supported with this wallet.</li
</ul>

# Definition

<div class="rp-definition">dLocal is a full-service payment management platform built for emerging markets in APAC, specifically the Philippines. It supports subscription enrollment, recurring transactions, one-time payments, and refunds for GCash. You'll need an existing dLocal relationship and a valid Integration Key to connect dLocal with Recurly.</div>

# Key details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
  <tr><td>Services that work with Recurly</td><td>Payment processing, subscriptions, one-time / ecommerce payments with GCash</td></tr>
  <tr><td>Supported operations</td><td>Subscription signups, recurring transactions, refunds, one-time purchases</td></tr>
  <tr><td>Supported payment types</td><td>GCash</td></tr>
  <tr><td>Supported card brands</td><td>N/A</td></tr>
  <tr><td>Gateway-specific 3DS2 supported</td><td>No</td></tr>
  <tr><td>Card on file supported</td><td>No</td></tr>
  <tr><td>Regions</td><td>GCash: Philippines</td></tr>
  <tr><td>Currencies</td><td>PHP only</td></tr>
  <tr><td>Gateway features</td><td>None</td></tr>
</table>

## Setup

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Obtain dLocal credentials</h4><p>Log in to your dLocal account to retrieve the credentials you'll need to connect it with Recurly.</p></div>
  </div>
</div>

<ol>
  <li>Log in to your dLocal account. Engage with dLocal to address any applicable contracts and fees before proceeding. Access your dLocal <strong>Production account</strong> for production keys, or <strong>Sandbox account</strong> for sandbox keys.</li>
  <li>Within your dLocal merchant dashboard, select <strong>Settings</strong>, then choose the <strong>Integration</strong> option.</li>
  <li>Copy the <strong>X-Login</strong>, <strong>X-Trans-Key</strong>, and the <strong>Secret Key</strong>. You don't need the smartfields API key. Save these for the next step.</li>
</ol>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter credentials in Recurly</h4><p>Add your dLocal credentials to a new payment gateway in Recurly.</p></div>
  </div>
</div>

<ol>
  <li>In Recurly, navigate to <strong>Configuration → Payment Gateways</strong>, select <strong>Add a New Gateway</strong>, then choose <strong>dLocal</strong>.</li>
  <li>Paste your X-Login, X-Trans-Key, and Secret Key into the applicable fields, shown below.</li>
</ol>


<Image src="https://files.readme.io/ddf05a2bfadc9314c2876188a9753530ba1e3728abb7c38b5f1aa5dec583a8ff-dlocal-credentials.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Set your payment methods</h4><p>Under <strong>Alternative Payment Methods</strong>, enable <strong>GCash</strong> — it's the only option. No card options appear under Accepted Card Types, since Recurly doesn't currently support card processing with dLocal.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save and enable the gateway</h4><p>Select <strong>Add Payment Gateway</strong>. dLocal appears in your Production Gateways list in Recurly with a status of <strong>Enabled</strong>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Test the configuration</h4><p>Run a test transaction in development mode on your Recurly sandbox site before going live. If your settlement model is set incorrectly, you'll receive an authentication error.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Go live</h4><p>Confirm your Recurly site has production dLocal credentials entered, and that your dLocal account is in Production mode.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Keep your dLocal credentials secure and limit access to authorized personnel. Consult your dLocal representative to confirm your account is in good standing and compliant with all relevant regulations.</div>
</div>

## Integration guides

Refer to the individual payment method guides for implementation details:

<ul class="rp-list">
  <li><a href="/docs/gcash-integration-guide">GCash integration guide</a></li>
  <li><a href="/docs/e-commerce-purchase-guide">One-time payments / ecommerce</a> integration guide</li>
</ul>

## Payment method specifics

### GCash Wallet

dLocal and the <a href="/docs/gcash-wallet" target="_blank">GCash method</a> require specific fields to authorize a payment successfully.

- Customer first and last name
- Customer email address
- Customer billing address (street address, city, region/state, country, postal/PIN code)
  - **Street address** — House/street name and number
  - **City** — Locality and city
  - **State** — Province
  - **Postal code** — Postal / zip code (4 digit)
  - **Country** — Country code (e.g., PH)
- Customer phone number

# FAQs

<Accordion title="I am using the billing info ID for one-time purchases, and it's failing. What can I do?">
  Recurly's integration with dLocal includes GCash only, which doesn't allow CIT one-time purchases using on-file tokens. You must offer the customer the option of using GCash and use Recurly.js to allow them to authenticate their account for one-time / line item purchases. If there is a stored payment method, its specific use is for active subscriptions only.
</Accordion>

<Accordion title="I'm setting the store_billing_info API field to 'true' on a line item purchase, but I'm getting an error. What gives?">
  One-time, or more specifically, ecommerce transactions using GCash do not produce a storable token for future purchases. Customers must re-authenticate with their app for every purchase. You'll need to set the `store_billing_info` API parameter to `false` and set up your checkout flow to always prompt the user to select the payment method during checkout, rather than using a stored method.
</Accordion>

<br />

<br />
