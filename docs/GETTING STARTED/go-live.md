---
title: Go live checklist
excerpt: >-
  A step-by-step checklist covering everything you need to set up, test, and
  launch your Recurly integration — from sandbox to production.
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

  <div class="rp-overview">
    Getting from your first sandbox login to live billing doesn't have to be complicated. This checklist walks you through every milestone — from setting up your integration and connecting a payment gateway to training your team and importing existing customers. Work through each step in order, and you'll be collecting real revenue with confidence.
  </div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#before-you-go-live"><span class="rp-toc-num">1</span>Before you go live</a>
    <a class="rp-toc-pill" href="#go-live"><span class="rp-toc-num">2</span>Go live</a>
    <a class="rp-toc-pill" href="#after-you-go-live"><span class="rp-toc-num">3</span>After you go live</a>
  </div>

</div>

# Before you go live

<div class="rp-definition">
  The steps below prepare your Recurly environment for production. Complete them in sandbox and development modes so your integration is fully validated before a real transaction ever runs. Need help? <a href="https://recurly.com/product/support-and-services" target="_blank">Enablement packages</a> for onboarding, data migration, and professional services can make this process significantly faster.
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Sign up for a sandbox site</h4><p><a href="https://app.recurly.com/signup/" target="_blank">Create your sandbox</a> and explore Recurly's capabilities before any real money moves. Use this time to build out your configuration — <a href="https://docs.recurly.com/docs/sandbox-features-to-discover" target="_blank">here's a list of sandbox features to discover</a> as you get set up.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong>Warning</strong>When you're ready to go live, all sandbox customer accounts, transactions, and invoices are wiped clean so accounting starts fresh with real data. You can clear test data any time by clicking <strong>Clear Test Data</strong>.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Set up your checkout integration</h4><p>Recurly offers two ways to create PCI-compliant checkouts. Choose the approach that fits your stack.</p></div>
  </div>
</div>

<div class="rp-card">

**Custom checkout** — Add the [Recurly.js](https://developers.recurly.com/reference/recurly-js/) library to a new or existing checkout page, then use the [API](https://recurly.com/developers/api/v2021-02-25/index.html) to create accounts, subscriptions, and one-time purchases in a single flow. The `/purchase` endpoint is the recommended starting point.

**Hosted Pages** — Use Recurly's [Checkout](https://docs.recurly.com/docs/checkout) to get a ready-made signup flow up and running quickly, without custom development.

</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Connect a payment gateway</h4><p>Link your existing gateway to your Recurly account. If you don't have one yet, <a href="https://recurly.com/gateways/" target="_blank">choose from Recurly's supported gateways</a> and establish an account. Keep in mind that initiating a new gateway can take up to 45 days.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Enable development mode</h4><p>Once you've subscribed to a <a href="https://recurly.com/plans/" target="_blank">Recurly plan</a> and are ready to test against a live gateway, <a href="https://support.recurly.com/" target="_blank">contact support</a> to enable development mode on your account.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Test your gateway in development mode</h4><p>Run transactions through your <a href="https://docs.recurly.com/docs/payment-gateways#test-configuration" target="_blank">configured gateway(s)</a> to confirm your Recurly integration is working end-to-end.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Train your customer service team</h4><p>Make sure the people handling day-to-day subscriptions know how to manage accounts, create subscriptions, process refunds, and handle common billing scenarios inside Recurly.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Review all API and Recurly.js calls</h4><p>Before you flip the switch to production, do a final review of every integration touchpoint using the <a href="https://developers.recurly.com/api/v2021-02-25/index.html" target="_blank">API documentation</a>.</p></div>
  </div>
</div>

Run through this verification checklist as part of step 7:

<ol>
  <li>Complete a full customer signup in your sandbox environment. Confirm the customer account and subscription were created correctly.</li>
  <li>Test any additional API flows — upgrades, downgrades, cancellations, and refunds.</li>
  <li>Review all Recurly.js and API calls for operational efficiency before go-live.</li>
</ol>

# Go live

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Switch to production mode</h4><p>When you're confident everything is working, go to the <a href="https://app.recurly.com/go/guides/progress" target="_blank">Welcome page</a> and click the link to switch to Production Mode. This starts live billing.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong>Important</strong>Switching to Production Mode is irreversible. Make sure you've finished all sandbox and development testing before you proceed.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Update all configurations to production</h4><p>Swap out every sandbox or development setting for its production equivalent — including your payment gateways, <a href="https://developers.recurly.com/reference/webhooks/" target="_blank">webhooks</a>, and any other environment-specific configurations.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Send a test transaction and void it</h4><p>Now that you're in production, run one real transaction through the gateway to confirm everything is wired up correctly, then <a href="https://docs.recurly.com/docs/transactions#refunds-and-voids" target="_blank">void it</a> immediately. All transactions affect reporting and can't be deleted — voiding is the clean way to verify without leaving a real charge behind.</p></div>
  </div>
</div>

# After you go live

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">11</div>
    <div><h4>Import your existing customers</h4><p>Bring in your existing business data — customer accounts, billing information, and subscription history — using the <a href="https://docs.recurly.com/docs/customer-imports" target="_blank">API</a> or through a <a href="https://go.recurly.com/rs/439-LSC-903/images/Recurly-EnablementServices-Imports-Overview.pdf" target="_blank">Professional Services engagement</a>.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong>Note</strong>Historical transaction data is not imported, and data from gateways may take time to prepare. Plan for this window when communicating your go-live timeline internally.</div>
</div>