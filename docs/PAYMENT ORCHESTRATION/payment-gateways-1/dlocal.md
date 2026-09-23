---
title: dLocal (Philippines)
excerpt: >-
  Connect dLocal to Recurly to process GCash one-time and subscription payments
  in the Philippines.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">dLocal is a gateway platform focused on emerging markets in Asia, Africa, the Middle East, and Latin America (LATAM). Integrating it with Recurly lets you process one time and recurring subscription payments via the GCash wallet payment method used in the Philippines. An existing dLocal relationship is required to enable this integration.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#configuring-dlocal-in-recurly"><span class="rp-toc-num">3</span>Configuring dLocal in Recurly</a>
    <a class="rp-toc-pill" href="#one-time-payments-with-gcash"><span class="rp-toc-num">4</span>One-time Payments with GCash and dLocal</a>
    <a class="rp-toc-pill" href="#subscription-behavior"><span class="rp-toc-num">5</span>Subscription behavior</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">6</span>FAQs</a>
  </div>
</div>

### Limitations

<ul class="rp-list">
  <li><strong>GCash billing info updates not supported</strong> — If a customer needs to update their wallet funding source, they must do so in the app itself.</li>
  <li><strong>No ad-hoc or one-time purchases using stored billing info</strong> — Customer-initiated one-time purchases using stored billing info and merchant-initiated force collections are not supported.</li>
  <li><strong>Chargebacks not reflected</strong> — Chargebacks are not currently supported or reflected in Recurly.</li>
  <li><strong>GCash one time payments do not store billing info by design. Customers must reauthenticate via Recurly.js every time.</li>
</ul>

# Definition

<div class="rp-definition">dLocal is a full-service payment management platform built for emerging markets in APAC, specifically, the Philippines. It supports subscription enrollment, recurring transactions, one time payments, and refunds for GCash. You'll need an existing dLocal relationship and a valid Integration Key to connect Ebanx with Recurly.</div>

# Key details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
  <tr><td>Services that work with Recurly</td><td>Payment processing, subscriptions, one-time / ecommerce payments with GCash</td></tr>
  <tr><td>Supported operations</td><td>Subscription signups, recurring transactions, refunds, one time purchases</td></tr>
  <tr><td>Supported payment types</td><td><a href="https://docs.recurly.com/docs/upi-autopay#/" target="_blank">GCash</a></td></tr>
  <tr><td>Supported card brands</td><td>N/A</td></tr>
  <tr><td>Gateway-specific 3DS2 supported</td><td>No</td></tr>
  <tr><td>Card on file supported</td><td>No</td></tr>
  <tr><td>Regions</td><td>GCash: Philippines</td></tr>
  <tr><td>Currencies</td><td>PHP only</td></tr>
  <tr><td>Additional feature support</td><td>None</td></tr>
</table>

## Integration guides

Refer to the individual payment method guides for implementation details:

- <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay-integration-guide#/" target="_blank">GCash integration guide</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/pix-automatico-integration-guide#" target="_blank">One-time Payments / eCommerce integration guide</a>

## Required fields

dLocal and the [GCash method](https://docs.recurly.com/recurly-subscriptions/v1.0_dlocal-gcash/docs/gcash-wallet) requires specific fields authorize a payment successfully.

### GCash Wallet

- Customer first and last name
- Customer email address
- Customer billing address (street address, city, region/state, country, postal/PIN code)
  - **Street address** — House/street name and number&#x20;
  - **City** — Locality and city&#x20;
  - **State** — State or union territory&#x20;
  - **Postal code** — Postal / zip code&#x20;
  - **Country** — Country code (e.g., IN)
- Customer phone number

# Configuring dLocal in Recurly

## Step 1: Obtain dLocal credentials

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to your dLocal account</h4><p>Engage with dLocal to address any applicable contracts and fees before proceeding. Access your dLocal <strong>Production account</strong> for production keys, or <strong>Sandbox account</strong> for sandbox keys.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open Settings</h4><p>Within your dLocal merchant dashboard, select <strong>Settings</strong>, then choose the <strong>Integration</strong> option.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Copy your credentials</h4><p>Copy the <strong>X-Login</strong>, <strong>X-Trans-Key</strong> and the <strong>Secret Key</strong>. You do not need the smartfields API key. Save these for Step 2.</p></div>
  </div>
</div>

## Step 2: Enter credentials in Recurly

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Payment Gateways</h4><p>In Recurly, navigate to <strong>Configuration → Payment Gateways</strong>, click <strong>Add a New Gateway</strong>, and select <strong>dLocal</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your credentials</h4><p>Paste your X-Login, X-Trans-Key, and Secret Key into the applicable fields.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/6c473d99f0f0f7f50fad57259059ba00ac561bc6f0086714a548fc6a14d8d692-Screenshot_2026-09-23_at_3.31.20_PM.png" align="left" width="50%" border={true} wrap={false} />


## Step 3: Set your payment methods

Under **Alternative Payment Methods**, enable **GCash** as it is the only option. No card options appear under Accepted Card Types — Recurly does not support card processing with dLocal presently.

## Step 4: Save and enable the gateway

Click **Add Payment Gateway**. dLocal will appear in your Production Gateways list in Recurly with a status of **Enabled**.

## Step 5: Test the configuration

Run a test transaction in development mode on your Recurly sandbox site before going live. If your settlement model is set incorrectly, you'll receive an Authentication error.

## Step 8: Go live

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Confirm production credentials</h4><p>Verify your Recurly site has production dLocal credentials entered and your dLocal account is in Production mode.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> Keep your dLocal credentials secure and limit access to authorized personnel. Consult your dLocal representative to confirm your account is in good standing and compliant with all relevant regulations.</div>
</div>

***

# FAQs

<Accordion title="I am using the billing info ID for one time purchases, and it's failing. What can I do?">
  Recurly's integration with dLocal includes GCash only, which doesn't allow CIT one time purchases using on-file tokens. You must offer the customer the option of using GCash and use Recurly.js to allow them to authenticate their account for one time / line item purchases. If there is a stored payment method, its specific use is for active subscriptions only.
</Accordion>

<Accordion title="I'm setting Store Billing Info API field to 'true' on a line item purchase, but I'm getting an error. What gives?">
  One time, or more specifically, ecommerce transactions using GCash does not produce a storable token for future purchases. Customers must re-authenticate with their app for every purchase. You will need to set the `store_billing_info` api param to `false` and setup your Checkout flow to always prompt the user to select the payment method during checkout versus a stored method.
</Accordion>
