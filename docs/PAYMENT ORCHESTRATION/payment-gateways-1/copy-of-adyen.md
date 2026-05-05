---
title: Copy of Adyen
excerpt: >-
  Harness the power of Adyen's global payment solutions, seamlessly integrated
  with Recurly, to elevate your business's payment experience.
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<style>
  :root {
    --yellow:     #FFD706;
    --tangerine:  #FF8200;
    --vermillion: #FF5810;
    --offblack:   #0D0D0B;
    --darkgray:   #32312D;
    --gray:       #807D73;
    --lightgray:  #CCC9B8;
    --brightgray: #F1EFE3;
    --offwhite:   #FFFDF2;
    --deepchar:   #232932;
    --darknavy:   #343F4B;
    --font:       'Plus Jakarta Sans', 'Segoe UI', system-ui, sans-serif;
  }
  *, *::before, *::after { box-sizing: border-box; }
  .rp-page { font-family: var(--font); color: var(--deepchar); font-size: 15px; line-height: 1.6; max-width: 860px; }
  .rp-overview { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 16px 22px; border-radius: 0 8px 8px 0; margin-bottom: 20px; font-size: 15px; color: var(--darkgray); }
  .rp-plan { display: inline-block; background: var(--offblack); color: var(--yellow); font-size: 13px; font-weight: 700; padding: 6px 16px; border-radius: 20px; margin-bottom: 28px; letter-spacing: 0.3px; }
  .rp-definition { background: var(--brightgray); border-radius: 10px; padding: 22px 26px; margin-bottom: 28px; font-size: 15px; color: var(--darkgray); line-height: 1.7; }
  .rp-h1 { font-size: 1.5rem; font-weight: 800; color: var(--offblack); margin: 36px 0 14px; padding-bottom: 8px; border-bottom: 2px solid var(--yellow); }
  .rp-h2 { font-size: 1.1rem; font-weight: 700; color: var(--darknavy); margin: 28px 0 10px; }
  .rp-h3 { font-size: 0.95rem; font-weight: 700; color: var(--darkgray); margin: 20px 0 8px; }
  .rp-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 22px 26px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.65; }
  .rp-card ul { margin: 8px 0 0; padding-left: 20px; }
  .rp-card ul li { margin-bottom: 6px; }
  .rp-card ol { margin: 8px 0 0; padding-left: 20px; }
  .rp-card ol li { margin-bottom: 6px; }
  .rp-steps { display: flex; flex-direction: column; gap: 12px; margin-bottom: 24px; }
  .rp-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 18px 22px; }
  .rp-step-num { width: 34px; height: 34px; border-radius: 8px; background: var(--offblack); color: var(--yellow); font-weight: 800; font-size: 14px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .rp-step h4 { font-size: 0.95rem; font-weight: 700; color: var(--offblack); margin: 0 0 4px; }
  .rp-step p { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0 0 6px; }
  .rp-step ul { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 4px 0 0; padding-left: 18px; }
  .rp-step ol { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 4px 0 0; padding-left: 18px; }
  .rp-callout { border-radius: 0 8px 8px 0; padding: 14px 18px; margin: 16px 0; font-size: 14px; }
  .rp-callout strong { display: block; margin-bottom: 3px; }
  .rp-callout-note      { border-left: 4px solid var(--offblack);   background: var(--brightgray); color: var(--deepchar); }
  .rp-callout-tip       { border-left: 4px solid var(--yellow);     background: var(--offwhite);   color: var(--darkgray); }
  .rp-callout-warning   { border-left: 4px solid var(--tangerine);  background: #FFF8F2;            color: var(--darkgray); }
  .rp-callout-important { border-left: 4px solid var(--vermillion); background: #FFF5F2;            color: var(--darkgray); }
  .rp-btn { display: inline-block; padding: 10px 22px; border-radius: 8px; font-weight: 700; font-size: 14px; text-decoration: none; margin: 6px 8px 6px 0; font-family: var(--font); }
  .rp-btn-primary { background: var(--offblack); color: var(--yellow); }
  .rp-btn-ghost { background: transparent; color: var(--darkgray); border: 1px solid var(--lightgray); }
  .rp-list { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 16px 22px 16px 38px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.7; }
  .rp-gw-table { width: 100%; border-collapse: collapse; font-size: 14px; margin-bottom: 28px; }
  .rp-gw-table thead tr { background: var(--offblack); color: var(--offwhite); }
  .rp-gw-table th { padding: 12px 16px; text-align: left; font-weight: 700; }
  .rp-gw-table td { padding: 12px 16px; vertical-align: top; }
  .rp-gw-table tr.rp-row-a { background: var(--offwhite); }
  .rp-gw-table tr.rp-row-b { background: var(--brightgray); }
  .rp-gw-table td:first-child { font-weight: 600; color: var(--offblack); width: 30%; }
  .rp-gw-table a { color: var(--tangerine); }
  .rp-pm-table { width: 100%; border-collapse: collapse; font-size: 13px; margin: 12px 0 24px; }
  .rp-pm-table thead tr { background: var(--offblack); color: var(--offwhite); }
  .rp-pm-table th { padding: 10px 12px; text-align: left; font-weight: 700; }
  .rp-pm-table td { padding: 10px 12px; border-bottom: 1px solid var(--lightgray); vertical-align: top; }
  .rp-pm-table tr:nth-child(even) td { background: var(--brightgray); }
  .rp-pm-table tr:nth-child(odd) td { background: var(--offwhite); }
  .rp-pm-table td:first-child { font-weight: 600; color: var(--offblack); }
  @media (max-width: 640px) { .rp-h1 { font-size: 1.25rem; } .rp-gw-table, .rp-pm-table { font-size: 12px; } }
</style>
</head>
<body>
<div class="rp-page">

  <div class="rp-overview">
    Recurly's integration with Adyen gives you access to an enterprise-level payment processor with extensive global coverage. It supports credit and debit card processing alongside a wide range of alternative payment methods — from ACH and SEPA to iDEAL, Cash App Pay, and Boleto — all within a single gateway connection.
  </div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-h3">Requirements</div>
  <ul class="rp-list">
    <li>Ensure your Business Entity Merchant Category Code is filled in correctly.</li>
    <li>Set up your Adyen webhooks, user permissions, and response settings correctly — missing configuration will cause renewals and asynchronous payment methods to fail.</li>
    <li>Certain features require Adyen's V71 Checkout version, which is feature-flagged. This requires capturing CVV from returning customers via API or Recurly.js. Contact Recurly Support for details.</li>
  </ul>

  <div class="rp-h3">Limitations</div>
  <ul class="rp-list">
    <li><strong>Minimum processing requirements:</strong> Adyen has minimum processing requirements and business models they don't support. <a href="https://www.adyen.com/legal/list-restricted-prohibited" target="_blank" style="color: var(--tangerine);">Visit Adyen's website</a> to confirm your business qualifies. For questions about minimums, contact Adyen directly.</li>
    <li>Asynchronous payment methods may take 48 hours or more for confirmation, depending on the method.</li>
    <li>Use Recurly.js or the Recurly API for credit and debit card transactions.</li>
    <li>SEPA supports EUR payments only.</li>
    <li>Certain features require migration to the latest version of Adyen — contact Customer Support about enabling V71.</li>
  </ul>

  <div class="rp-h1">Definition</div>
  <div class="rp-definition">
    Adyen is an enterprise payment processor with global reach, supporting credit and debit cards, ACH, SEPA, and a range of regional and digital payment methods. Recurly's Adyen integration handles the full transaction lifecycle — authorizations, captures, refunds, voids, and recurring billing — while managing tokenization, webhook processing, and account updates behind the scenes.
  </div>

  <div class="rp-h1">Key details</div>

  <table class="rp-gw-table">
    <thead>
      <tr><th>Feature</th><th>Details</th></tr>
    </thead>
    <tbody>
      <tr class="rp-row-a">
        <td>Services that work with Recurly</td>
        <td>Credit/debit cards, Recurring, Adyen Web Components, <a href="https://docs.recurly.com/docs/adyen#/adyen-network-tokens" style="color: var(--tangerine);">Adyen-derived Network Tokens</a>, <a href="https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium" style="color: var(--tangerine);">Revenue Protect / Protect Premium</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/" style="color: var(--tangerine);">MOTO Processing</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/level-2-and-level-3-cedp-guide" style="color: var(--tangerine);">Level 2/3 Processing</a></td>
      </tr>
      <tr class="rp-row-b">
        <td>Supported operations</td>
        <td>Authorize &amp; Capture, Purchase, Refund, Verify, Void</td>
      </tr>
      <tr class="rp-row-a">
        <td>Supported payment types</td>
        <td>Credit/debit cards, ACH, Boleto, iDEAL, Klarna Debit Risk (existing merchants only), SEPA, Google Pay, Apple Pay, Cash App Pay.<br/><br/><strong>Note:</strong> Only a subset of payment methods are supported in the new Adyen Components Recurly.js support. Excluded methods: Klarna Debit Risk and Boleto.</td>
      </tr>
      <tr class="rp-row-b">
        <td>Supported card brands</td>
        <td>Visa, Mastercard, American Express, Discover, JCB, Diners Club, China Union Pay, ELO (BRL only), Hipercard (BRL only), Cartes Bancaires, Dankort, Bancontact</td>
      </tr>
      <tr class="rp-row-a">
        <td>Gateway-specific 3DS2 supported</td>
        <td>Yes</td>
      </tr>
      <tr class="rp-row-b">
        <td>Card on file supported</td>
        <td>Yes</td>
      </tr>
      <tr class="rp-row-a">
        <td>Regions</td>
        <td>Global</td>
      </tr>
      <tr class="rp-row-b">
        <td>Currencies</td>
        <td><a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank" style="color: var(--tangerine);">All available</a> with special behavior for <strong>ISK</strong> and <strong>CLP</strong>. <strong>IDR</strong> and <strong>CVE</strong> are not supported.</td>
      </tr>
      <tr class="rp-row-a">
        <td>Gateway features</td>
        <td><a href="https://docs.recurly.com/docs/adyen#/adyen-network-tokens" style="color: var(--tangerine);">Network Token usage</a>, <a href="https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium" style="color: var(--tangerine);">Revenue Protect / Protect Premium</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/" style="color: var(--tangerine);">MOTO Processing</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater" style="color: var(--tangerine);">Realtime Account Updater</a></td>
      </tr>
    </tbody>
  </table>

  <div class="rp-callout rp-callout-tip">
    <strong>Testing your gateway</strong>Visit Recurly's <a href="https://docs.recurly.com/docs/how-to-test-your-gateway" target="_blank" style="color: var(--tangerine);">guide on testing gateway configurations</a> to confirm your payment processes are set up correctly before going live.
  </div>

  <div class="rp-h2">Setting up Adyen with Recurly</div>
  <div class="rp-h3">Step 1 — Configure Adyen account credentials</div>

  <div class="rp-callout rp-callout-note">
    <strong>Two settings require a support request to Adyen</strong>
    <ul style="margin: 6px 0 0; padding-left: 18px;">
      <li><strong>API PCI Payments role</strong> for your web services user (step 11a below)</li>
      <li><strong>Skip CVC</strong> for your Merchant Account (step 11b below)</li>
    </ul>
  </div>

  <div class="rp-callout rp-callout-important">
    <strong>Ensure Adyen V71 is enabled at Recurly</strong>V71 Adyen API requirements mandate sending a CVV on customer-initiated transactions using stored billing info. You may need to modify your Recurly integration or set up Skip CVC with Adyen. Future features won't be accessible without these changes.
  </div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Access the Adyen dashboard</h4><p>Log in to your Adyen account.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Navigate to API credentials</h4><p>Go to <strong>Developers → API Credentials</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Create a new credential</h4><p>Click <strong>Create new credential</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Select credential type</h4><p>In the modal, select <strong>Web service user</strong> under Credential Type.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div><h4>Name your credential</h4><p>Enter a username and optional description — for example: <em>Recurly Adyen Credentials</em>.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/0958525-Screenshot_2023-10-26_at_1.45.41_PM.png"
       alt="Adyen credential creation modal showing Web service user selection"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">6</div>
      <div><h4>Enable Merchant Recurring Role</h4><p>Ensure <strong>Merchant Recurring Role</strong> is checked. Without this, recurring transactions using stored cards will fail.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/47ce985afb27f46153651193d5dd02935a1c3a28c3fd4b64c724d175cc8a33a8-Screenshot_2025-02-07_at_9.45.08_AM.png"
       alt="Merchant Recurring Role checkbox in Adyen credential settings"
       style="display:block; width:75%; margin:16px auto; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">7</div>
      <div><h4>Save your password immediately</h4><p>Your password is available under <strong>Server settings → Authentication → Basic auth</strong>. Record it now — you won't be able to access it after leaving this page. If you miss it, you'll need to regenerate it.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">8</div>
      <div><h4>Record credentials for Recurly</h4><p>Note the auto-generated username and password for use in the next phase.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">9</div>
      <div><h4>Save changes</h4><p>Click <strong>Save changes</strong>.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/748ce08-Screenshot_2023-10-26_at_1.46.10_PM.png"
       alt="Adyen Basic auth section showing username and password fields"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">10</div>
      <div><h4>Configure Dynamic 3DS</h4><p>In the <strong>Risk</strong> section under <strong>Dynamic 3D Secure</strong>, set Dynamic 3DS to <strong>prefer no</strong> — unless you specifically want to require 3DS on all transactions. Don't enable this on a gateway instance running recurring billing.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">11</div>
      <div>
        <h4>Submit two requests to Adyen support</h4>
        <ul>
          <li><strong>API PCI Payments role:</strong> Request activation for your web services user. Without this, payments using a raw card number will fail.</li>
          <li><strong>Disable CVC requirement:</strong> Request this if you don't collect CVV codes from returning customers. If you do collect CVV on all customer-initiated transactions and are on V71, ensure your integration passes the code to Recurly via API.</li>
        </ul>
      </div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">12</div>
      <div><h4>Enable Acquirer Result fields</h4><p>Ensure <strong>Acquirer Result</strong> and <strong>Raw Acquirer Result</strong> are enabled in your API responses.</p></div>
    </div>
  </div>

  <div class="rp-h3">Step 2 — Configure Adyen webhooks</div>

  <div class="rp-callout rp-callout-important">
    <strong>Webhook configuration is critical</strong>Incorrect setup will cause renewals and asynchronous payment methods to fail. Follow every step below carefully.
  </div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to webhooks</h4><p>Go to <strong>Developer → Webhooks</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Add a Standard webhook</h4><p>Click <strong>+ Webhook</strong>, find <strong>Standard webhook</strong>, and click <strong>Add</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Set the server URL</h4><p>Under <strong>Server configuration</strong>, click the pencil icon and enter:<br/><code>https://callbacks.recurly.com/adyen/&lt;MERCHANT_SUBDOMAIN&gt;</code><br/>Replace <code>&lt;MERCHANT_SUBDOMAIN&gt;</code> with your Recurly site's subdomain. Click <strong>Apply</strong>.</p>
      <p style="margin-top:8px;"><em>EU data centers: use <code>callbacks.eu.recurly.com</code> instead.</em></p></div>
    </div>
  </div>

  <img src="https://files.readme.io/fc70703-image.png"
       alt="Adyen webhook server configuration showing Recurly callback URL"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Add the four required webhook types</h4><p>In addition to any payment-method-specific events, add: <strong>Direct-Debit Pending</strong>, <strong>Generic Pending</strong>, <strong>Recurring Token Lifecycle events</strong>, and <strong>Standard webhook</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div>
        <h4>Enable required event codes</h4>
        <ul>
          <li><strong>RECURRING_CONTRACT</strong> — Required for tokenized payment methods.</li>
          <li><strong>REPORT_AVAILABLE</strong> — Required for settlement reports and Revenue Recognition.</li>
          <li><strong>EXPIRE</strong> — Required for correct Auth and Capture behavior.</li>
          <li><strong>CAPTURE_FAILED</strong> — Required for proper transaction handling, especially with Auth and Capture.</li>
          <li><strong>OFFER_CLOSED</strong> — Required when using the iDEAL payment method.</li>
          <li><strong>iDEAL details</strong> — Required when using iDEAL. See <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks" target="_blank" style="color: var(--tangerine);">Adyen's documentation</a>.</li>
          <li><strong>recurring.token.created / updated / deleted</strong> — Required when using Adyen gateway tokens.</li>
        </ul>
        <p style="margin-top:8px;">Configure event codes in both locations Adyen lists them: <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#standard-webhook-page" target="_blank" style="color: var(--tangerine);">Standard Webhooks Page</a> and <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#webhooks-settings-page" target="_blank" style="color: var(--tangerine);">Webhooks Settings Page</a>.</p>
      </div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">6</div>
      <div><h4>Enable the webhook</h4><p>Ensure the <strong>Enabled</strong> toggle is active.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/1a31b55-image.png"
       alt="Adyen webhook Enabled toggle in active state"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">7</div>
      <div><h4>Save changes</h4><p>Click <strong>Save changes</strong> at the bottom of the page.</p></div>
    </div>
  </div>

  <div class="rp-h3">Step 3 — Adyen additional data configuration</div>

  <div class="rp-card">
    Navigate to <strong>Developers → Additional Data</strong> in Adyen for all settings in this step. You can make all changes at once. To automatically receive new features in the future, enable all fields for a set-it-and-forget-it approach. If you prefer more control, enable only what's documented here and monitor Recurly's changelog for updates.
  </div>

  <div class="rp-h3">Activation of response fields via API</div>
  <div class="rp-card">
    To enable card data when a token is received via webhook, enable the following response fields in Adyen's Additional Data settings:
    <ul>
      <li>Card bin</li>
      <li>Card summary</li>
      <li>Expiry date</li>
    </ul>
    Once a token is received, Recurly receives extra data from Adyen to populate card brand metadata including the BIN, last four digits, and other details.
  </div>

  <div class="rp-h3">Activation of 3DS results data</div>
  <div class="rp-card">
    To populate 3DS results data in Recurly, enable 3DS response details in <strong>Developers → Additional Data</strong>. There are four separate settings — enable all of them to ensure transaction detail pages populate correctly.
  </div>

  <div class="rp-h3">Activation of network transaction reference and recurring details</div>
  <div class="rp-card">
    To successfully process Merchant-Initiated Transactions (MIT) across all payment methods — including Google Pay, Apple Pay, and cards — activate <strong>Network transaction reference</strong> in your Adyen Merchant Account settings. For payment methods requiring tokenization, also enable <strong>Recurring Details</strong> in the same area.<br/><br/>
    Navigate to <strong>Developers → Additional Data</strong> in Adyen to enable these features. Once activated, Adyen generates a unique Network Transaction ID (NTID) and reusable token (if applicable). Note: the NTID won't be visible in Recurly.
  </div>

  <div class="rp-h2">Adding Adyen to your Recurly site</div>
  <div class="rp-h3">Step 1 — Add Adyen in your Payment Gateway configuration</div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Add the Adyen gateway</h4><p>Go to <strong>Configuration → Payment Gateways → Add New Gateway</strong> in your Recurly Admin.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Enter your Adyen credentials</h4><p>Provide the <strong>username</strong>, <strong>password</strong>, and <strong>merchant account</strong> details from your Adyen configuration.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Set the custom endpoint</h4><p>Include only the specific portion of the endpoint provided by Adyen, not the full URL. You can use any placeholder while testing — update it for production.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Select Zero Dollar Authorization</h4><p>Select <strong>Zero Dollar Authorization</strong> for all card types.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div><h4>Save your configuration</h4><p>Click <strong>Save</strong>.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-note">
    <strong>Network Transaction Reference is required for MIT</strong>Enabling Network Transaction Reference in Adyen is required for successful MIT exemptions and payment processing across all methods — including Google Pay, Apple Pay, and cards. Transactions may fail even with correct Adyen settings if this isn't enabled.
  </div>

  <div class="rp-callout rp-callout-note">
    <strong>Non-card payment method setup</strong>For non-standard gateway setup, see the payment method-specific instructions in the Payment method specifics section below.
  </div>

  <div class="rp-h1">Payment method specifics</div>

  <div class="rp-h2">Payment methods overview</div>

  <table class="rp-pm-table">
    <thead>
      <tr><th>Payment method</th><th>Currency</th><th>Recurrence</th><th>Key notes</th></tr>
    </thead>
    <tbody>
      <tr><td>Credit/debit cards</td><td>Multi</td><td>Native</td><td>Dual-badge support for Cartes Bancaires, Dankort, Bancontact. Raw PAN storage when not using third-party checkout.</td></tr>
      <tr><td>ACH</td><td>USD</td><td>Native</td><td>Requires GIACT/NACHA verification and report credentials. First/last name on checks must not be sent as dashes.</td></tr>
      <tr><td>SEPA</td><td>EUR only</td><td>Native</td><td>Recurly handles renewal notifications automatically. Raw IBAN storage. Status update webhooks required.</td></tr>
      <tr><td>BACS</td><td>GBP</td><td>Native</td><td>Token-based only. Recurly.js required for enrollment. Status update webhooks required.</td></tr>
      <tr><td>iDEAL | Wero</td><td>EUR</td><td>Converts to SEPA</td><td>First payment via iDEAL; all renewals via SEPA Direct Debit. Multiple webhooks required.</td></tr>
      <tr><td>Boleto</td><td>BRL</td><td>Invoice-based</td><td>Async; renewals generate a new invoice each cycle. Dedicated email template required.</td></tr>
      <tr><td>Klarna Debit Risk (Sofort)</td><td>EUR, CHF, GBP</td><td>Converts to SEPA</td><td>Existing merchants only — new signups unavailable. RECURRING_CONTRACT and recurring.token.created webhooks required.</td></tr>
      <tr><td>Cash App Pay</td><td>USD only</td><td>Native</td><td>US only. RECURRING_CONTRACT and recurring.token.created webhooks required.</td></tr>
    </tbody>
  </table>

  <div class="rp-h2">ACH and SEPA reporting setup</div>

  <div class="rp-card">
    ACH and SEPA transactions through Adyen require a special report to be configured. To integrate the ACH gateway, initiate the <strong>Adyen ACH</strong> gateway on the Add Payment Gateway page. For SEPA, use the standard Adyen gateway.
  </div>

  <div class="rp-h3">Setting up report credentials</div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Access API credentials</h4><p>Log in to Adyen and go to <strong>Developers → API credentials</strong>.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/0e9f446-Screenshot_2023-10-26_at_2.32.53_PM.png"
       alt="Adyen API credentials page showing existing users"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Create a reporting user</h4><p>If no reporting user exists, create one and designate it as <strong>Report service user</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Save the password</h4><p>Copy the password from <strong>Server Settings → Authentication → Basic auth</strong> before saving changes — you'll need to regenerate it if you miss it.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Enter credentials in Recurly</h4><p>Add the reporting username and password to the <strong>REPORTS USERNAME</strong> and <strong>REPORTS PASSWORD</strong> fields in your Recurly Adyen configuration.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/0ad6c72-image.png"
       alt="Recurly Adyen gateway configuration showing Reports Username and Password fields"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-h3">Subscribing to the payment accounting report for ACH</div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to Reports</h4><p>In Adyen, go to <strong>Reports</strong>. Under the Finance section, click <strong>Payment Accounting</strong> then <strong>Manage report</strong>.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/d471c36-image.png"
       alt="Adyen Payment Accounting report management screen"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <img src="https://files.readme.io/f40b511-image.png"
       alt="Adyen report settings showing automatic generation toggle"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Enable automatic generation</h4><p>Select <strong>Automatic</strong>, toggle automatic generation to <strong>On</strong>, and set the file type to <strong>CSV</strong>. Click the X to close the dialog.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/cbce972-image.png"
       alt="Adyen automatic report generation enabled with CSV file type selected"
       style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Confirm the report is active</h4><p>Click <strong>Manage report</strong> again to verify automatic generation is on.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Subscribe to the report</h4><p>Actively subscribe to the Payment Accounting Report. See <a href="https://docs.recurly.com/docs/adyen#subscribing-to-the-payment-accounting-report-for-ach" target="_blank" style="color: var(--tangerine);">Recurly's documentation</a> for the full process.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div><h4>Set immediate capture</h4><p>In Adyen, set transactions to <strong>immediate capture</strong>.</p></div>
    </div>
  </div>

  <div class="rp-h3">Enabling NACHA verification</div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Enable GIACT in Adyen</h4><p>Within Adyen, ensure <strong>GIACT</strong> is enabled for NACHA verification.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Enable in Recurly</h4><p>In your Recurly Adyen configuration, check the NACHA verification box at the bottom of the page and save.</p></div>
    </div>
  </div>

  <img src="https://files.readme.io/f49c57dc1b942f81b5044b7538580f260cb01da28a09a610e597a359ddfef0c7-Screenshot_2025-07-29_at_4.11.19_PM.png"
       alt="Recurly Adyen configuration showing NACHA verification checkbox"
       style="display:block; width:75%; margin:16px auto; border-radius:8px;" />

  <div class="rp-h2">BACS (United Kingdom)</div>

  <div class="rp-card">
    Bankers' Automated Clearing Services (BACS) Direct Debit is widely used in the UK for one-time and recurring transactions. Due to chargeback and late failure risks, Recurly doesn't recommend BACS for one-time charges where physical goods are being shipped.<br/><br/>
    BACS on Adyen uses Adyen gateway tokens exclusively — Recurly doesn't have access to the underlying payment details. That said, one-time and recurring charges are still possible via Recurly.js and APIs. Creating a BACS gateway token is only possible via Recurly.js.
  </div>

  <div class="rp-callout rp-callout-note">
    <strong>BACS compliance</strong>When using Recurly.js, you're responsible for obtaining consent and displaying appropriate regulatory information to the consumer — including the charge amount, due date, frequency, and your merchant business name. Note that Adyen's name will appear on bank statements as "ADYEN RE [Merchant Name]."
  </div>

  <div class="rp-h2">SEPA (European Union)</div>

  <div class="rp-card">
    Single Euro Payments Area (SEPA) Direct Debit is the primary payment mode across the EU, supporting one-time or recurring payments in EUR using the customer's name and IBAN. As required by the SEPA Direct Debit rulebook, Recurly automatically sends a notification email to the customer each time a debit is made.<br/><br/>
    Recurly supports automated retries for SEPA payments on Adyen. <a href="https://docs.recurly.com/docs/sepa-retries" target="_blank" style="color: var(--tangerine);">Learn more about SEPA retries.</a>
  </div>

  <div class="rp-h3">Direct Debit configuration</div>

  <div class="rp-card">
    <strong>In Recurly:</strong>
    <ul>
      <li>Integrate Adyen as your gateway.</li>
      <li>Select the BACS checkbox under APMs in Adyen.</li>
      <li>Enable EUR for SEPA and GBP for BACS. <a href="https://docs.recurly.com/docs/currencies" target="_blank" style="color: var(--tangerine);">Learn about adding currencies.</a></li>
    </ul>
    <br/>
    <strong>In Adyen:</strong>
    <ul>
      <li>Activate SEPA and/or BACS as needed.</li>
      <li>Ensure EUR is available for SEPA and GBP for BACS.</li>
      <li>Enable RECURRING_CONTRACT webhooks. <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/" target="_blank" style="color: var(--tangerine);">See Adyen's guide.</a></li>
    </ul>
  </div>

  <div class="rp-h2">Dual-badge card support (France, Belgium, Denmark)</div>

  <div class="rp-card">
    Recurly supports <strong>Cartes Bancaires</strong> (France), <strong>Dankort</strong> (Denmark, DKK only), and <strong>Bancontact</strong> (Belgium) on Adyen. These dual-badged cards let customers choose between a major network (Visa or Mastercard) and the regional network at checkout.<br/><br/>
    Dual-badge compliance requires two things: giving customers a <em>choice</em> of network, and a <em>non-distinction policy</em> — customers must enter their card into a single field labeled "Card" regardless of whether it's debit or credit. Recurly.js elements handle this automatically. Custom UIs must implement it manually.
  </div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Enable the card types in Adyen</h4><p>In your Adyen gateway settings, check <strong>Cartes Bancaires</strong>, <strong>Dankort</strong>, and/or <strong>Bancontact</strong> as accepted card payment methods.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Integrate with Recurly.js</h4><p>Use the <code>cardElement</code> or <code>cardNumberElement</code> parameters. See <a href="https://recurly.com/developers/reference/recurly-js/#elements" target="_blank" style="color: var(--tangerine);">Recurly.js documentation</a> and the <a href="https://docs.recurly.com/recurly-subscriptions/docs/co-badged-cards-guide" target="_blank" style="color: var(--tangerine);">Dual/Co-Badged guide</a>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Enable SEPA for Bancontact</h4><p>Bancontact transactions convert to SEPA for recurring payments. Ensure SEPA is enabled at both Adyen and Recurly. Note: Bancontact cards don't require CVV, always require 3DS, and don't support separate auth and capture.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Enable DKK for Dankort</h4><p>Dankort is only accepted with DKK currency. Ensure DKK is enabled at both Adyen and Recurly.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-tip">
    <strong>Cartes Bancaires tip</strong>Cartes Bancaires cards experience fewer declines when transactions include the cardholder's billing address. Ensure you're capturing billing address data for customers using this card type.
  </div>

  <div class="rp-h2">Cash App Pay</div>

  <div class="rp-card">
    Cash App Pay is a US-only digital wallet allowing customers to pay using their Cash App balance or linked payment method. At checkout, customers select Cash App Pay, scan a QR code, and authorize through the Cash App. Cash App Pay through Adyen supports USD transactions only and requires RECURRING_CONTRACT webhooks.
  </div>

  <div class="rp-card">
    <strong>In Recurly:</strong>
    <ul>
      <li>Integrate Adyen as your gateway using <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank" style="color: var(--tangerine);">Recurly.js Alternative Payment Methods</a>.</li>
      <li>Enable USD currency.</li>
      <li>Check <strong>Cash App Pay</strong> under Alternative Payment Methods in your Adyen gateway settings in Recurly.</li>
    </ul>
    <br/>
    <strong>In Adyen:</strong>
    <ul>
      <li>Activate Cash App Pay.</li>
      <li>Ensure USD currency is available.</li>
      <li>Enable all applicable webhooks per the webhook configuration section above.</li>
    </ul>
  </div>

  <div class="rp-h2">iDEAL | Wero</div>

  <div class="rp-card">
    iDEAL | Wero is widely used in the Netherlands, representing a significant portion of the region's online transactions. The initial subscription payment uses iDEAL | Wero; all subsequent renewals use SEPA Direct Debit. Communicate this to customers clearly at signup.
  </div>

  <div class="rp-card">
    <strong>In Recurly:</strong>
    <ul>
      <li>Integrate Adyen as the gateway.</li>
      <li>Activate SEPA for recurring payments.</li>
      <li>Ensure EUR currency is configured.</li>
      <li>See the <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank" style="color: var(--tangerine);">Recurly.js developer guide</a>.</li>
    </ul>
    <br/>
    <strong>In Adyen:</strong>
    <ul>
      <li>Activate SEPA for recurring payments.</li>
      <li>Ensure EUR currency is configured.</li>
      <li>Enable all applicable webhooks.</li>
      <li>Add iDEAL | Wero details webhooks. <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks" target="_blank" style="color: var(--tangerine);">Steps here.</a></li>
    </ul>
  </div>

  <div class="rp-callout rp-callout-warning">
    <strong>iDEAL | Wero restrictions</strong>
    <ul style="margin: 6px 0 0; padding-left: 18px;">
      <li>Free trials via iDEAL are not supported — use SEPA Direct Debit for free trials.</li>
      <li>iDEAL can't be used for subscriptions with a deferred start date.</li>
      <li>Chargeback management isn't available with iDEAL.</li>
      <li>Recurly's Checkout and Hosted Payment Pages don't support iDEAL.</li>
    </ul>
  </div>

  <div class="rp-h2">Sofort (Klarna Debit Risk)</div>

  <div class="rp-callout rp-callout-warning">
    <strong>Existing merchants only</strong>Only merchants with an existing Sofort/Klarna Debit Risk account with Adyen can use this payment method. New signups are not available.
  </div>

  <div class="rp-card">
    Sofort (Klarna Debit Risk) is an online banking payment method used in Germany, Austria, Switzerland, and Belgium. It's compatible with EUR, CHF, and GBP. For recurring transactions, Sofort isn't viable — SEPA is used instead.<br/><br/>
    <em>Note: Sofort is being phased out by Klarna and replaced by Klarna Debit Risk. Adyen has stated no major technical changes are required, but the country code must be passed for proper routing. Update your Recurly.js implementations accordingly.</em>
  </div>

  <div class="rp-callout rp-callout-warning">
    <strong>Sofort restrictions</strong>
    <ul style="margin: 6px 0 0; padding-left: 18px;">
      <li>Free trials are not supported — use SEPA Direct Debit instead.</li>
      <li>Not compatible with subscriptions that have a deferred start date.</li>
      <li>Chargeback management is not available.</li>
      <li>Recurly's Hosted Payment Pages don't support Sofort.</li>
      <li>Sofort is not the BNPL/Buy Now Pay Later version of Klarna.</li>
    </ul>
  </div>

  <div class="rp-h2">Boleto</div>

  <div class="rp-card">
    Boleto Bancário is a popular payment method in Brazil, commonly used by customers without bank accounts. It supports BRL only. Because Boleto doesn't support direct recurring transactions, each renewal generates a new invoice — initially marked "Past Due" until the customer pays the Boleto.
  </div>

  <div class="rp-card">
    <strong>In Recurly:</strong>
    <ul>
      <li>Activate Brazilian Real (BRL) currency.</li>
      <li>Integrate Adyen as a gateway.</li>
      <li>Use Recurly.js to integrate Boleto into your checkout page.</li>
      <li>Set up a Boleto-specific email template for recurring payments, including a link to download the Boleto invoice.</li>
    </ul>
    <br/>
    <strong>In Adyen:</strong>
    <ul>
      <li>Contact your Adyen representative to align your account with a Brazilian entity.</li>
      <li>Enable the Boleto payment method in your Adyen account settings.</li>
      <li>Ensure BRL is activated in your Adyen account.</li>
    </ul>
  </div>

  <div class="rp-h2">Currency considerations — ISK and CLP</div>

  <div class="rp-card">
    ISK and CLP are zero-decimal currencies, but Adyen hasn't updated their logic to reflect this. To support them, Recurly automatically appends <code>00</code> to the decimal places when sending transactions to Adyen.<br/><br/>
    <strong>Do not add the <code>00</code> in your own integration</strong> — this will result in overcharging customers.<br/><br/>
    <strong>Example:</strong> If you send <code>23</code> as the amount, Recurly sends <code>2300</code> to Adyen. If a plan is set to <code>23.00</code>, Recurly also sends <code>2300</code>.
  </div>

  <div class="rp-h2">Address accuracy</div>

  <div class="rp-card">
    Recurly supports sending shipping addresses to Adyen, but Adyen requires a full, complete address to avoid errors. Recurly won't send partial addresses. If you use Adyen's reporting or fraud services with shipping address data, ensure the complete address is stored — including street address, city, state, country, and postal code. If any field is absent, Recurly omits the entire shipping address.
  </div>

  <div class="rp-h1">Gateway feature support</div>

  <div class="rp-h2">Adyen Real Time Account Updater (RTAU)</div>

  <div class="rp-card">
    Adyen RTAU updates card details and expiration dates in real time during a transaction, improving authorization rates and keeping renewals on track when a customer's card changes. Adyen returns PCI card data encrypted to Recurly — to process those updates, you must generate an RSA key in Recurly and provide the public key to Adyen.<br/><br/>
    Before starting, confirm with Adyen that RTAU is enabled for your account and that any required agreements are in place.
  </div>

  <div class="rp-h3">Eligibility requirements</div>
  <ul class="rp-list">
    <li>You're using raw cards with Adyen as your primary gateway through a supported Recurly API or Recurly.js — not Adyen Web Components.</li>
    <li>You're not using Adyen gateway tokens or network tokens.</li>
    <li>You're not using Adyen third-party checkout or components through Recurly.js.</li>
  </ul>

  <div class="rp-h3">Recurly configuration — RSA key</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to Payment Gateways</h4><p>Go to <strong>Configuration → Payment Gateways</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Open Manage Keys</h4><p>On your Adyen gateway, select <strong>Options</strong>, then <strong>Manage Keys</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Add or reuse a key</h4><p>If no key exists, select <strong>Add a Real Time Account Updater Key</strong>. If you have multiple Adyen instances pointing to the same Adyen account, you can share an existing RSA key.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Generate or select a key</h4><p>Select <strong>Generate New Key</strong> to create a new one, or <strong>Use Existing Key</strong> to reuse one across multiple Adyen instances.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div><h4>Add the key</h4><p>Select <strong>Add Key</strong>.</p></div>
    </div>
  </div>

  <div class="rp-h3">Adyen configuration — RSA key and RTAU enablement</div>
  <div class="rp-card">
    You can't configure the RSA key directly in the Adyen dashboard. Copy the public key from Recurly and provide it to Adyen via a support ticket. Include the key exactly as shown in Recurly. Once Adyen applies it, RTAU starts working automatically.
  </div>

  <div class="rp-h3">How Adyen RTAU works with Recurly Account Updater</div>
  <div class="rp-card">
    If both services are enabled, card updates through Adyen RTAU won't be sent to Recurly Account Updater. Adyen supports Visa, Mastercard, and regional American Express only. To continue receiving Discover and additional American Express updates, keep Recurly Account Updater enabled alongside Adyen RTAU.<br/><br/>
    Adyen RTAU updates may include:
    <ul>
      <li><strong>Card PAN changes:</strong> Recurly decrypts the PAN (when an RSA key is configured) and updates billing info. Because RTAU runs in real time, if Adyen returns a full card update, the updated card is used to complete the current transaction and saved for future use.</li>
      <li><strong>Card expiration date changes:</strong> Recurly updates the expiration date on file.</li>
      <li><strong>Closed account notices:</strong> Recurly invalidates the billing info for the account.</li>
      <li><strong>Contact customer notices:</strong> Recurly doesn't update billing info but logs the response in Account Activities when a transaction declines.</li>
    </ul>
  </div>

  <div class="rp-h3">Disabling RSA keys for Adyen RTAU</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to Payment Gateways</h4><p>Go to <strong>Configuration → Payment Gateways</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Open Manage Keys</h4><p>On the Adyen gateway, select <strong>Options → Manage Keys</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Revoke the key</h4><p>Select <strong>Revoke</strong> for the RSA key. Also contact Adyen to disable RTAU on their side. If Recurly Account Updater is enabled, it resumes processing updates for supported card brands after RTAU is disabled.</p></div>
    </div>
  </div>

  <div class="rp-h2">Network tokens</div>

  <div class="rp-card">
    If Adyen is enabled to create network tokens for your merchant account (cards only), Recurly surfaces whether a network token was used on each transaction. You can find this in transaction details in the Recurly Admin UI or in gateway parameter responses through the API.<br/><br/>
    Recurly displays this as a boolean field called <strong>Third Party Network Token Used</strong>:
    <ul>
      <li><code>False</code> — a raw primary account number (PAN) or card data was used</li>
      <li><code>True</code> — a network token was used</li>
    </ul>
    If network tokens aren't enabled in your Adyen account, this value will always be <code>False</code>. Token usage is determined by Adyen, not by Recurly — contact Adyen support for questions about why a token was or wasn't used.
  </div>

  <div class="rp-callout rp-callout-important">
    <strong>Important</strong>Adyen uses network tokenization only for tokenized payment methods. Recurly supports tokenizing cards only when you use Adyen Web Components through Recurly.js. If you're using third-party checkout, you get network token behavior by default.
  </div>

  <div class="rp-h2">Revenue Protect and Protect Premium</div>

  <div class="rp-card">
    Recurly supports sending the data Adyen needs to evaluate risk and apply your Revenue Protect or Protect Premium rules. If you have a paid subscription to Adyen Protect Premium, you can create custom risk profiles in Adyen and pass the profile ID to Recurly when creating subscriptions or one-time charges through the V3 API.
    <ul style="margin-top: 10px;">
      <li>V3 field: <code>billing_info.adyen_risk_profile_reference_id</code></li>
      <li>Adyen reference: <a href="https://docs.adyen.com/risk-management/create-and-use-risk-profiles/" target="_blank" style="color: var(--tangerine);">Create Risk Profiles</a></li>
    </ul>
  </div>

  <div class="rp-h3">Data Recurly sends to support risk decisions</div>
  <ul class="rp-list">
    <li><strong>Billing and shipping address data</strong> — See <a href="https://docs.recurly.com/docs/adyen#/special-address-considerations" target="_blank" style="color: var(--tangerine);">Shipping Data on Adyen</a> and <a href="https://docs.recurly.com/docs/shipping-addresses#/" target="_blank" style="color: var(--tangerine);">Shipping addresses</a>.</li>
    <li><strong>Shipping method and amount</strong> — Recurly sends the invoice shipping amount and the shipping method Name value to Adyen. See <a href="https://docs.recurly.com/docs/shipping#/shipping-methods" target="_blank" style="color: var(--tangerine);">Shipping methods</a>.</li>
    <li><strong>Browser information</strong> — Sent when the shopper goes through 3DS. Revenue Protect can evaluate browser-based rules at the gateway.</li>
    <li><strong>Shopper data</strong> — Email address, phone number, name, IP address (in-session only), and shopper reference. Shopper IP addresses are not sent to Adyen on renewals.</li>
    <li><strong>Acquisition date</strong> — Send using <code>acquisition.acquired_at</code> in the V3 API. You can backfill dates on existing accounts. See the <a href="https://recurly.com/developers/api/v2021-02-25/#operation/create_purchase" target="_blank" style="color: var(--tangerine);">V3 acquired_at field documentation</a>.</li>
  </ul>

  <div class="rp-callout rp-callout-warning">
    <strong>Protect Premium limitation</strong>Review rules aren't supported for Adyen Protect (new risk engine) when using Purchase transactions. If you need Review, use an Authorize and Capture flow where your system controls capture. When using purchases, use only Allow, Block, or Check for 3DS actions.
  </div>

  <div class="rp-h1">Important notes</div>

  <div class="rp-card">
    <ul>
      <li>Follow customer notification requirements — for example, SEPA renewal notices.</li>
      <li>Recurly can export billing information from Adyen for SEPA subscription renewals.</li>
      <li>Recurly sends purchase transactions to Adyen with a capture flag, overriding your Adyen capture settings.</li>
    </ul>
  </div>

  <div class="rp-h2">How asynchronous payments work</div>
  <div class="rp-card">
    <ul>
      <li>After a successful purchase, the subscription becomes active, but the invoice and transaction remain "processing" until Adyen confirms payment approval.</li>
      <li>Recurly sends a "processing payment" webhook and a "payment processing" email to customers (if enabled).</li>
      <li>Adyen's initial return token is "unverified" while the bank confirms payment.</li>
      <li>Within 48 hours, the token becomes "verified" and additional transactions can proceed.</li>
      <li>Recurly updates the transaction and invoice status based on Adyen feedback and sends the relevant webhooks and emails.</li>
      <li><strong>Dunning and retries:</strong> Asynchronous payments require special dunning handling. See the <a href="https://docs.recurly.com/docs/paypal-payments#paypal-echecks" target="_blank" style="color: var(--tangerine);">PayPal eChecks guidance</a> for reference.</li>
    </ul>
  </div>

  <div class="rp-h2">Billing information updates</div>
  <div class="rp-card">
    For billing information updates, direct customers to Recurly hosted pages or build your own API connection. Recurly charges a small amount or a zero-dollar verification if your gateway is set up correctly. After Adyen approves the request, Recurly automatically issues a refund.
  </div>

  <div class="rp-h2">IP address allowlist</div>
  <div class="rp-card">
    In some scenarios, Adyen may use additional IP addresses that must be allowlisted in Recurly. Contact Recurly Support before moving to production.
  </div>

  <div class="rp-h2">API integration with Recurly</div>
  <div class="rp-card">
    In a standard Recurly.js flow, Recurly handles payment authorization. The customer enters billing details first. After authorization, you create the subscription and process the charge.
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />

<Accordion title="A tokenized payment method I'm using isn't allowing conversions, or subscriptions are failing. What can I do?">
  Confirm you've enabled the required webhooks. `RECURRING_CONTRACT` webhooks are critical for all non-card payment methods. Review the webhook configuration section above and ensure every required event code is active in both the Standard Webhooks Page and the Webhooks Settings Page in Adyen.
</Accordion>

<Accordion title="My customer got a decline from Adyen at checkout. What happened?">
  Start with the decline code shown in the Recurly Admin UI for the transaction. If the decline is related to 3DS, confirm 3DS is enabled and configured in both Adyen and your Recurly.js implementation. If 3DS is already enabled, the customer may not have completed the 3DS challenge successfully — in which case the decline is expected behavior.
</Accordion>
