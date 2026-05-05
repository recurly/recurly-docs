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
<HTMLBlock>{`
<style>
  :root {
    --yellow:     #FFD706;
    --tangerine:  #FF8200;
    --vermillion: #FF5810;
    --salmon:     #FF9D88;
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
  .rp-plan { display: inline-block; background: var(--offblack); color: var(--yellow); font-size: 13px; font-weight: 700; padding: 6px 16px; border-radius: 20px; margin-bottom: 24px; letter-spacing: 0.3px; }
  .rp-cost { border-left: 4px solid var(--tangerine); background: #FFF8F2; padding: 14px 20px; border-radius: 0 8px 8px 0; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); }
  .rp-cost a { color: var(--tangerine); }
  .rp-definition { background: var(--brightgray); border-radius: 10px; padding: 22px 26px; margin-bottom: 28px; font-size: 15px; color: var(--darkgray); line-height: 1.7; }
  .rp-benefits { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 14px; margin-bottom: 32px; }
  .rp-benefits.rp-benefits-2x2 { grid-template-columns: repeat(2, 1fr); }
  .rp-benefit { background: var(--offblack); color: var(--offwhite); border-radius: 10px; padding: 20px; }
  .rp-benefit-icon { color: var(--yellow); font-size: 20px; margin-bottom: 10px; }
  .rp-benefit strong { display: block; font-size: 14px; font-weight: 700; margin-bottom: 6px; color: var(--offwhite); }
  .rp-benefit span { font-size: 13px; color: var(--lightgray); line-height: 1.5; }
  .rp-h1 { font-size: 1.5rem; font-weight: 800; color: var(--offblack); margin: 36px 0 14px; padding-bottom: 8px; border-bottom: 2px solid var(--yellow); }
  .rp-h2 { font-size: 1.1rem; font-weight: 700; color: var(--darknavy); margin: 28px 0 10px; }
  .rp-h3 { font-size: 0.95rem; font-weight: 700; color: var(--darkgray); margin: 20px 0 8px; }
  .rp-h4 { font-size: 0.9rem; font-weight: 600; color: var(--darkgray); margin: 16px 0 6px; }
  .rp-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 22px 26px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.65; }
  .rp-steps { display: flex; flex-direction: column; gap: 12px; margin-bottom: 24px; }
  .rp-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 18px 22px; }
  .rp-step-num { width: 34px; height: 34px; border-radius: 8px; background: var(--offblack); color: var(--yellow); font-weight: 800; font-size: 14px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .rp-step h4 { font-size: 0.95rem; font-weight: 700; color: var(--offblack); margin: 0 0 4px; }
  .rp-step p { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }
  .rp-callout { border-radius: 0 8px 8px 0; padding: 14px 18px; margin: 16px 0; font-size: 14px; display: flex; gap: 12px; align-items: flex-start; }
  .rp-callout strong { display: block; margin-bottom: 3px; }
  .rp-callout-note      { border-left: 4px solid var(--offblack); background: var(--brightgray); color: var(--deepchar); }
  .rp-callout-tip       { border-left: 4px solid var(--yellow);    background: var(--offwhite);   color: var(--darkgray); }
  .rp-callout-warning   { border-left: 4px solid var(--tangerine); background: #FFF8F2;            color: var(--darkgray); }
  .rp-callout-important { border-left: 4px solid var(--vermillion);background: #FFF5F2;            color: var(--darkgray); }
  .rp-btn { display: inline-block; padding: 10px 22px; border-radius: 8px; font-weight: 700; font-size: 14px; text-decoration: none; margin: 6px 8px 6px 0; font-family: var(--font); }
  .rp-btn-primary   { background: var(--offblack); color: var(--yellow); }
  .rp-btn-secondary { background: var(--yellow);   color: var(--offblack); }
  .rp-btn-ghost     { background: transparent; color: var(--darkgray); border: 1px solid var(--lightgray); }
  .rp-gw-table { width: 100%; border-collapse: collapse; font-size: 14px; margin-bottom: 28px; }
  .rp-gw-table tr.rp-thead-row td { background: var(--offblack) !important; color: var(--offwhite) !important; font-weight: 700; padding: 12px 16px; }
  .rp-gw-table tr.rp-thead-row td:first-child { color: var(--offwhite) !important; }
  .rp-gw-table td { padding: 12px 16px; vertical-align: top; }
  .rp-gw-table tr.rp-row-a { background: var(--offwhite); }
  .rp-gw-table tr.rp-row-b { background: var(--brightgray); }
  .rp-gw-table tr:not(.rp-thead-row) td:first-child { font-weight: 600; color: var(--offblack); width: 35%; }
  .rp-gw-table a { color: var(--tangerine); }
  .rp-pm-table { width: 100%; border-collapse: collapse; font-size: 13px; margin: 12px 0 24px; }
  .rp-pm-table tr.rp-thead-row td { background: var(--offblack) !important; color: var(--offwhite) !important; font-weight: 700; padding: 10px 12px; }
  .rp-pm-table tr.rp-thead-row td:first-child { color: var(--offwhite) !important; }
  .rp-pm-table td { padding: 10px 12px; border-bottom: 1px solid var(--lightgray); vertical-align: top; }
  .rp-pm-table tr:nth-child(even):not(.rp-thead-row) td { background: var(--brightgray); }
  .rp-pm-table tr:nth-child(odd):not(.rp-thead-row) td  { background: var(--offwhite);   }
  .rp-pm-table tr:not(.rp-thead-row) td:first-child { font-weight: 600; color: var(--offblack); }
  .rp-list { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 16px 22px 16px 38px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.7; }
  @media (max-width: 640px) { .rp-benefits, .rp-benefits.rp-benefits-2x2 { grid-template-columns: 1fr; } .rp-h1 { font-size: 1.25rem; } }
</style>
<div class="rp-page">

  <div class="rp-overview">
    Recurly's integration with Adyen gives you access to an enterprise-level payment processor with extensive global coverage. It supports credit and debit card processing alongside a wide range of alternative payment methods — from ACH and SEPA to iDEAL, Cash App Pay, and Boleto — all within a single gateway connection.
  </div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-h3" id="prerequisites">Prerequisites</div>
  <ul class="rp-list">
    <li>Confirm your Business Entity Merchant Category Code is filled in correctly.</li>
    <li>Set up your Adyen webhooks, user permissions, and response settings correctly — missing configuration causes renewals and asynchronous payment methods to fail.</li>
    <li>Certain features require Adyen's V71 Checkout version, which is feature-flagged. This requires capturing CVV from returning customers via API or Recurly.js. Contact Recurly Support for details.</li>
  </ul>

  <div class="rp-h3" id="limitations">Limitations</div>
  <ul class="rp-list">
    <li><strong>Minimum processing requirements:</strong> Adyen has minimum processing requirements and business models they don't support. <a href="https://www.adyen.com/legal/list-restricted-prohibited" target="_blank">Visit Adyen's website</a> to confirm your business qualifies. For questions about minimums, contact Adyen directly.</li>
    <li>Asynchronous payment methods may take 48 hours or more for confirmation, depending on the method.</li>
    <li>Use Recurly.js or the Recurly API for credit and debit card transactions.</li>
    <li>SEPA supports EUR payments only.</li>
    <li>Certain features require migration to the latest version of Adyen — contact Customer Support about enabling V71.</li>
  </ul>

  <div class="rp-h1" id="definition">Definition</div>
  <div class="rp-definition">
    Adyen is an enterprise payment processor with global reach, supporting credit and debit cards, ACH, SEPA, and a range of regional and digital payment methods. Recurly's Adyen integration handles the full transaction lifecycle — authorizations, captures, refunds, voids, and recurring billing — while managing tokenization, webhook processing, and account updates behind the scenes.
  </div>

  <div class="rp-h1" id="key-details">Key details</div>

  <table class="rp-gw-table">
    <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
    <tr class="rp-row-a">
      <td>Services that work with Recurly</td>
      <td>Credit/debit cards, recurring, Adyen Web Components, <a href="#network-tokens">Adyen-derived network tokens</a>, <a href="#revenue-protect-and-protect-premium">Revenue Protect / Protect Premium</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions" target="_blank">MOTO processing</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/level-2-and-level-3-cedp-guide" target="_blank">Level 2/3 processing</a></td>
    </tr>
    <tr class="rp-row-b">
      <td>Supported operations</td>
      <td>Authorize and capture, purchase, refund, verify, void</td>
    </tr>
    <tr class="rp-row-a">
      <td>Supported payment types</td>
      <td>Credit/debit cards, ACH, Boleto, iDEAL, Klarna Debit Risk (existing merchants only), SEPA, Google Pay, Apple Pay, Cash App Pay. Klarna Debit Risk and Boleto are excluded from the new Adyen Components Recurly.js support.</td>
    </tr>
    <tr class="rp-row-b">
      <td>Supported card brands</td>
      <td>Visa, Mastercard, American Express, Discover, JCB, Diners Club, China Union Pay, ELO (BRL only), Hipercard (BRL only), Cartes Bancaires, Dankort, and Bancontact</td>
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
      <td><a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">All available</a> with special behavior for ISK and CLP. IDR and CVE are not supported.</td>
    </tr>
    <tr class="rp-row-a">
      <td>Gateway features</td>
      <td><a href="#network-tokens">Network token usage</a>, <a href="#revenue-protect-and-protect-premium">Revenue Protect / Protect Premium</a>, <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions" target="_blank">MOTO processing</a>, <a href="#adyen-real-time-account-updater-rtau">Realtime Account Updater</a></td>
    </tr>
  </table>

  <div class="rp-callout rp-callout-tip">
    <div><strong>Testing your gateway</strong>Visit Recurly's <a href="https://docs.recurly.com/docs/how-to-test-your-gateway" target="_blank">guide on testing gateway configurations</a> to confirm your payment processes are set up correctly before going live.</div>
  </div>

  <div class="rp-h2" id="setup">Setup</div>

  <div class="rp-h3" id="step-1-configure-adyen-account-credentials">Step 1 — Configure Adyen account credentials</div>

  <div class="rp-callout rp-callout-note">
    <div><strong>Two settings require a support request to Adyen</strong>
      <ul style="margin:6px 0 0;padding-left:18px;">
        <li><strong>API PCI Payments role</strong> for your web services user (step 11a below)</li>
        <li><strong>Skip CVC</strong> for your merchant account (step 11b below)</li>
      </ul>
    </div>
  </div>

  <div class="rp-callout rp-callout-important">
    <div><strong>Confirm Adyen V71 is enabled at Recurly</strong>V71 Adyen API requirements mandate sending a CVV on customer-initiated transactions using stored billing info. You may need to modify your Recurly integration or set up Skip CVC with Adyen. Future features won't be accessible without these changes.</div>
  </div>

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Access the Adyen dashboard</h4><p>Log in to your Adyen account.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Navigate to API credentials</h4><p>Go to Developers → API Credentials.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Create a new credential</h4><p>Click Create new credential.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Select credential type</h4><p>In the modal, select Web service user under Credential Type.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">5</div><div><h4>Name your credential</h4><p>Enter a username and optional description — for example, Recurly Adyen Credentials.</p></div></div>
  </div>

  <img src="https://files.readme.io/0958525-Screenshot_2023-10-26_at_1.45.41_PM.png" alt="Adyen credential creation modal showing Web service user selection" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">6</div><div><h4>Enable Merchant Recurring Role</h4><p>Confirm Merchant Recurring Role is checked. Without this, recurring transactions using stored cards fail.</p></div></div>
  </div>

  <img src="https://files.readme.io/47ce985afb27f46153651193d5dd02935a1c3a28c3fd4b64c724d175cc8a33a8-Screenshot_2025-02-07_at_9.45.08_AM.png" alt="Merchant Recurring Role checkbox in Adyen credential settings" style="display:block; width:85%; margin:16px auto; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">7</div><div><h4>Save your password immediately</h4><p>Your password is available under Server settings → Authentication → Basic auth. Record it now — you won't be able to access it after leaving this page.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">8</div><div><h4>Record credentials for Recurly</h4><p>Note the auto-generated username and password for use in the next phase.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">9</div><div><h4>Save changes</h4><p>Click Save changes.</p></div></div>
  </div>

  <img src="https://files.readme.io/748ce08-Screenshot_2023-10-26_at_1.46.10_PM.png" alt="Adyen Basic auth section showing username and password fields" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">10</div><div><h4>Configure Dynamic 3DS</h4><p>In the Risk section under Dynamic 3D Secure, set Dynamic 3DS to "prefer no" — unless you specifically want 3DS on all transactions. Don't enable this on a gateway instance running recurring billing.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">11</div><div><h4>Submit two requests to Adyen support</h4><p>API PCI Payments role: request activation for your web services user. Without this, payments using a raw card number fail. Disable CVC requirement: request this if you don't collect CVV codes from returning customers. If you're on V71 and you do collect CVV, confirm your integration passes it to Recurly via API.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">12</div><div><h4>Enable Acquirer Result fields</h4><p>Confirm Acquirer Result and Raw Acquirer Result are enabled in your API responses.</p></div></div>
  </div>

  <div class="rp-h3" id="step-2-configure-adyen-webhooks">Step 2 — Configure Adyen webhooks</div>

  <div class="rp-callout rp-callout-important">
    <div><strong>Webhook configuration is critical</strong>Incorrect setup causes renewals and asynchronous payment methods to fail. Follow every step below carefully.</div>
  </div>

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Navigate to webhooks</h4><p>Go to Developer → Webhooks.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Add a Standard webhook</h4><p>Click + Webhook, find Standard webhook, and click Add.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Set the server URL</h4><p>Under Server configuration, click the pencil icon and enter https://callbacks.recurly.com/adyen/&lt;MERCHANT_SUBDOMAIN&gt;. Replace &lt;MERCHANT_SUBDOMAIN&gt; with your Recurly site's subdomain. Click Apply. EU data centers: use callbacks.eu.recurly.com instead.</p></div></div>
  </div>

  <img src="https://files.readme.io/fc70703-image.png" alt="Adyen webhook server configuration showing Recurly callback URL" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Add the four required webhook types</h4><p>Add Direct-Debit Pending, Generic Pending, Recurring Token Lifecycle events, and Standard webhook.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">5</div><div><h4>Enable required event codes</h4><p>RECURRING_CONTRACT for tokenized payment methods. REPORT_AVAILABLE for settlement reports and Revenue Recognition. EXPIRE for correct Auth and Capture behavior. CAPTURE_FAILED for proper transaction handling with Auth and Capture. OFFER_CLOSED when using iDEAL. iDEAL details when using iDEAL — see <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks" target="_blank">Adyen's documentation</a>. recurring.token.created / updated / deleted when using Adyen gateway tokens. Configure event codes in both the <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#standard-webhook-page" target="_blank">Standard Webhooks page</a> and the <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#webhooks-settings-page" target="_blank">Webhooks Settings page</a>.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">6</div><div><h4>Enable the webhook</h4><p>Confirm the Enabled toggle is active.</p></div></div>
  </div>

  <img src="https://files.readme.io/1a31b55-image.png" alt="Adyen webhook Enabled toggle in active state" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">7</div><div><h4>Save changes</h4><p>Click Save changes at the bottom of the page.</p></div></div>
  </div>

  <div class="rp-h3" id="step-3-adyen-additional-data-configuration">Step 3 — Adyen additional data configuration</div>

  <div class="rp-card">
    Navigate to Developers → Additional Data in Adyen for all settings in this step. You can make all changes at once. To automatically receive new features in the future, enable all fields for a set-it-and-forget-it approach.
  </div>

  <div class="rp-h4" id="response-fields-via-api">Response fields via API</div>
  <div class="rp-card">
    Enable these fields in Adyen's Additional Data settings to populate card brand metadata when a token is received via webhook: Card bin, Card summary, and Expiry date.
  </div>

  <div class="rp-h4" id="3ds-results-data">3DS results data</div>
  <div class="rp-card">
    Enable 3DS response details in Developers → Additional Data — there are four separate settings. Enable all of them so transaction detail pages populate correctly.
  </div>

  <div class="rp-h4" id="network-transaction-reference-and-recurring-details">Network transaction reference and recurring details</div>
  <div class="rp-card">
    To process Merchant-Initiated Transactions (MIT) across all payment methods — including Google Pay, Apple Pay, and cards — activate Network transaction reference in your Adyen merchant account settings. For payment methods requiring tokenization, also enable Recurring Details in the same area. Navigate to Developers → Additional Data to enable these. Once active, Adyen generates a unique Network Transaction ID (NTID) — note this isn't visible in Recurly.
  </div>

  <div class="rp-h3" id="adding-adyen-to-your-recurly-site">Adding Adyen to your Recurly site</div>

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Add the Adyen gateway</h4><p>Go to Configuration → Payment Gateways → Add New Gateway in your Recurly Admin.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Enter your Adyen credentials</h4><p>Provide the username, password, and merchant account details from your Adyen configuration.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Set the custom endpoint</h4><p>Include only the specific endpoint portion provided by Adyen — not the full URL. Use a placeholder while testing; update for production.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Select Zero Dollar Authorization</h4><p>Select Zero Dollar Authorization for all card types.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">5</div><div><h4>Save your configuration</h4><p>Click Save.</p></div></div>
  </div>

  <div class="rp-callout rp-callout-note">
    <div><strong>Network Transaction Reference is required for MIT</strong>Enabling Network Transaction Reference in Adyen is required for successful MIT exemptions and payment processing across all methods. Transactions can fail even with correct Adyen settings if this isn't enabled.</div>
  </div>

  <div class="rp-callout rp-callout-note">
    <div><strong>Non-card payment method setup</strong>For non-standard gateway setup, see the payment method-specific instructions in the section below.</div>
  </div>

  <div class="rp-h2" id="payment-method-specifics">Payment method specifics</div>

  <div class="rp-h3" id="payment-methods-overview">Payment methods overview</div>

  <table class="rp-pm-table">
    <tr class="rp-thead-row"><td>Payment method</td><td>Currency</td><td>Recurrence</td><td>Key notes</td></tr>
    <tr><td>Credit/debit cards</td><td>Multi</td><td>Native</td><td>Dual-badge support for Cartes Bancaires, Dankort, and Bancontact. Raw PAN storage when not using third-party checkout.</td></tr>
    <tr><td>ACH</td><td>USD</td><td>Native</td><td>Requires GIACT/NACHA verification and report credentials. First and last name on checks must not be sent as dashes.</td></tr>
    <tr><td>SEPA</td><td>EUR only</td><td>Native</td><td>Recurly handles renewal notifications automatically. Raw IBAN storage. Status update webhooks required.</td></tr>
    <tr><td>BACS</td><td>GBP</td><td>Native</td><td>Token-based only. Recurly.js required for enrollment. Status update webhooks required.</td></tr>
    <tr><td>iDEAL | Wero</td><td>EUR</td><td>Converts to SEPA</td><td>First payment via iDEAL; all renewals via SEPA Direct Debit. Multiple webhooks required.</td></tr>
    <tr><td>Boleto</td><td>BRL</td><td>Invoice-based</td><td>Async; renewals generate a new invoice each cycle. Dedicated email template required.</td></tr>
    <tr><td>Klarna Debit Risk (Sofort)</td><td>EUR, CHF, GBP</td><td>Converts to SEPA</td><td>Existing merchants only. RECURRING_CONTRACT and recurring.token.created webhooks required.</td></tr>
    <tr><td>Cash App Pay</td><td>USD only</td><td>Native</td><td>US only. RECURRING_CONTRACT and recurring.token.created webhooks required.</td></tr>
  </table>

  <div class="rp-h3" id="ach-and-sepa-reporting-setup">ACH and SEPA reporting setup</div>
  <div class="rp-card">
    ACH and SEPA transactions through Adyen require a special report to be configured. To integrate ACH, initiate the Adyen ACH gateway on the Add Payment Gateway page. For SEPA, use the standard Adyen gateway.
  </div>

  <div class="rp-h4" id="setting-up-report-credentials">Setting up report credentials</div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Access API credentials</h4><p>Log in to Adyen and go to Developers → API credentials.</p></div></div>
  </div>

  <img src="https://files.readme.io/0e9f446-Screenshot_2023-10-26_at_2.32.53_PM.png" alt="Adyen API credentials page showing existing users" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Create a reporting user</h4><p>If no reporting user exists, create one and designate it as Report service user.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Save the password</h4><p>Copy the password from Server Settings → Authentication → Basic auth before saving changes.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Enter credentials in Recurly</h4><p>Add the reporting username and password to the REPORTS USERNAME and REPORTS PASSWORD fields in your Recurly Adyen configuration.</p></div></div>
  </div>

  <img src="https://files.readme.io/0ad6c72-image.png" alt="Recurly Adyen gateway configuration showing Reports Username and Password fields" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-h4" id="subscribing-to-the-payment-accounting-report-for-ach">Subscribing to the payment accounting report for ACH</div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Navigate to Reports</h4><p>In Adyen, go to Reports. Under Finance, click Payment Accounting then Manage report.</p></div></div>
  </div>

  <img src="https://files.readme.io/d471c36-image.png" alt="Adyen Payment Accounting report management screen" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <img src="https://files.readme.io/f40b511-image.png" alt="Adyen report settings showing automatic generation toggle" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Enable automatic generation</h4><p>Select Automatic, toggle to On, set file type to CSV, and close the dialog.</p></div></div>
  </div>

  <img src="https://files.readme.io/cbce972-image.png" alt="Adyen automatic report generation enabled with CSV selected" style="display:block; width:85%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />

  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Confirm the report is active</h4><p>Click Manage report again to verify automatic generation is on.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Subscribe to the report</h4><p>Actively subscribe to the Payment Accounting Report. See <a href="https://docs.recurly.com/docs/adyen#subscribing-to-the-payment-accounting-report-for-ach" target="_blank">Recurly's documentation</a> for the full process.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">5</div><div><h4>Set immediate capture</h4><p>In Adyen, configure transactions to immediate capture.</p></div></div>
  </div>

  <div class="rp-h4" id="enabling-nacha-verification">Enabling NACHA verification</div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Enable GIACT in Adyen</h4><p>Confirm GIACT is enabled for NACHA verification within Adyen.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Enable in Recurly</h4><p>In your Recurly Adyen configuration, check the NACHA verification box at the bottom of the page and save.</p></div></div>
  </div>

  <img src="https://files.readme.io/f49c57dc1b942f81b5044b7538580f260cb01da28a09a610e597a359ddfef0c7-Screenshot_2025-07-29_at_4.11.19_PM.png" alt="Recurly Adyen configuration showing NACHA verification checkbox" style="display:block; width:85%; margin:16px auto; border-radius:8px;" />

  <div class="rp-h3" id="bacs-united-kingdom">BACS (United Kingdom)</div>
  <div class="rp-card">
    Bankers' Automated Clearing Services (BACS) Direct Debit is widely used in the UK for one-time and recurring transactions. Because of chargeback and late failure risks, Recurly doesn't recommend BACS for one-time charges where physical goods are being shipped. BACS on Adyen uses Adyen gateway tokens exclusively — Recurly doesn't have access to the underlying payment details. One-time and recurring charges are still possible via Recurly.js and APIs. Creating a BACS gateway token is only possible via Recurly.js.
  </div>
  <div class="rp-callout rp-callout-note">
    <div><strong>BACS compliance</strong>When using Recurly.js, you're responsible for obtaining consent and displaying regulatory information to the consumer — including the charge amount, due date, frequency, and your merchant business name. Adyen's name appears on bank statements as "ADYEN RE [Merchant Name]."</div>
  </div>

  <div class="rp-h3" id="sepa-european-union">SEPA (European Union)</div>
  <div class="rp-card">
    SEPA Direct Debit is the primary payment mode across the EU, supporting one-time or recurring EUR payments using the customer's name and IBAN. Recurly automatically sends a notification email each time a debit is made, as required by the SEPA Direct Debit rulebook. Recurly supports automated retries for SEPA payments on Adyen. <a href="https://docs.recurly.com/docs/sepa-retries" target="_blank">Learn more about SEPA retries.</a>
  </div>
  <div class="rp-card">
    <div class="rp-h4" id="sepa-recurly-config">In Recurly</div>
    <ul style="margin:6px 0 14px;padding-left:20px;">
      <li>Integrate Adyen as your gateway.</li>
      <li>Select the BACS checkbox under APMs in Adyen.</li>
      <li>Enable EUR for SEPA and GBP for BACS. <a href="https://docs.recurly.com/docs/currencies" target="_blank">Learn about adding currencies.</a></li>
    </ul>
    <div class="rp-h4" id="sepa-adyen-config">In Adyen</div>
    <ul style="margin:6px 0 0;padding-left:20px;">
      <li>Activate SEPA, BACS, or both as needed.</li>
      <li>Confirm EUR is available for SEPA and GBP for BACS.</li>
      <li>Enable RECURRING_CONTRACT webhooks. <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/" target="_blank">See Adyen's guide.</a></li>
    </ul>
  </div>

  <div class="rp-h3" id="dual-badge-card-support-france-belgium-denmark">Dual-badge card support (France, Belgium, Denmark)</div>
  <div class="rp-card">
    Recurly supports Cartes Bancaires (France), Dankort (Denmark, DKK only), and Bancontact (Belgium) on Adyen. Dual-badge compliance requires giving customers a choice of network and a non-distinction policy — customers enter their card into a single field labeled "Card" regardless of whether it's debit or credit. Recurly.js handles this automatically.
  </div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Enable the card types in Adyen</h4><p>In your Adyen gateway settings, check Cartes Bancaires, Dankort, Bancontact, or any combination.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Integrate with Recurly.js</h4><p>Use the cardElement or cardNumberElement parameters. See <a href="https://recurly.com/developers/reference/recurly-js/#elements" target="_blank">Recurly.js documentation</a> and the <a href="https://docs.recurly.com/recurly-subscriptions/docs/co-badged-cards-guide" target="_blank">Dual/Co-Badged guide</a>.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Enable SEPA for Bancontact</h4><p>Bancontact converts to SEPA for recurring payments. Confirm SEPA is enabled at both Adyen and Recurly. Bancontact cards don't require CVV, always require 3DS, and don't support separate auth and capture.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Enable DKK for Dankort</h4><p>Dankort only works with DKK currency. Enable DKK at both Adyen and Recurly.</p></div></div>
  </div>
  <div class="rp-callout rp-callout-tip">
    <div><strong>Cartes Bancaires tip</strong>Cartes Bancaires cards experience fewer declines when transactions include the cardholder's billing address. Capture billing address data for customers using this card type.</div>
  </div>

  <div class="rp-h3" id="indian-cards-inr">Indian cards (INR)</div>
  <div class="rp-callout rp-callout-note">
    <div><strong>Regional mandate not supported</strong>Recurly doesn't support regional mandates for Indian cards on the Adyen gateway. If you're accepting Indian cards for subscriptions, review the RBI documentation before proceeding. <a href="https://docs.recurly.com/docs/rbi-mandate" target="_blank">Read the RBI documentation →</a></div>
  </div>

  <div class="rp-h3" id="cash-app-pay">Cash App Pay</div>
  <div class="rp-card">
    Cash App Pay is a US-only digital wallet for USD transactions. Customers select Cash App Pay at checkout, scan a QR code, and authorize through the app. Requires RECURRING_CONTRACT webhooks.
  </div>
  <div class="rp-card">
    <div class="rp-h4" id="cash-app-recurly-config">In Recurly</div>
    <ul style="margin:6px 0 14px;padding-left:20px;">
      <li>Integrate Adyen using <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank">Recurly.js Alternative Payment Methods</a>.</li>
      <li>Enable USD currency.</li>
      <li>Check Cash App Pay under Alternative Payment Methods in your Adyen gateway settings.</li>
    </ul>
    <div class="rp-h4" id="cash-app-adyen-config">In Adyen</div>
    <ul style="margin:6px 0 0;padding-left:20px;">
      <li>Activate Cash App Pay.</li>
      <li>Confirm USD currency is available.</li>
      <li>Enable all applicable webhooks per the webhook configuration section above.</li>
    </ul>
  </div>

  <div class="rp-h3" id="ideal-wero">iDEAL | Wero</div>
  <div class="rp-card">
    iDEAL | Wero is widely used in the Netherlands. The initial subscription payment uses iDEAL | Wero; all subsequent renewals use SEPA Direct Debit. Communicate this to customers clearly at signup.
  </div>
  <div class="rp-card">
    <div class="rp-h4" id="ideal-recurly-config">In Recurly</div>
    <ul style="margin:6px 0 14px;padding-left:20px;">
      <li>Integrate Adyen as the gateway.</li>
      <li>Activate SEPA for recurring payments.</li>
      <li>Confirm EUR currency is configured.</li>
      <li>See the <a href="https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods" target="_blank">Recurly.js developer guide</a>.</li>
    </ul>
    <div class="rp-h4" id="ideal-adyen-config">In Adyen</div>
    <ul style="margin:6px 0 0;padding-left:20px;">
      <li>Activate SEPA for recurring payments.</li>
      <li>Confirm EUR currency is configured.</li>
      <li>Enable all applicable webhooks.</li>
      <li>Add iDEAL | Wero details webhooks. <a href="https://docs.adyen.com/development-resources/webhooks/webhook-types/#other-webhooks" target="_blank">Steps here.</a></li>
    </ul>
  </div>
  <div class="rp-callout rp-callout-warning">
    <div><strong>iDEAL | Wero restrictions</strong>
      <ul style="margin:6px 0 0;padding-left:18px;">
        <li>Free trials aren't supported — use SEPA Direct Debit for free trials.</li>
        <li>Can't be used for subscriptions with a deferred start date.</li>
        <li>Chargeback management isn't available.</li>
        <li>Recurly's Checkout and Hosted Payment Pages don't support iDEAL.</li>
      </ul>
    </div>
  </div>

  <div class="rp-h3" id="sofort-klarna-debit-risk">Sofort (Klarna Debit Risk)</div>
  <div class="rp-callout rp-callout-warning">
    <div><strong>Existing merchants only</strong>Only merchants with an existing Sofort/Klarna Debit Risk account with Adyen can use this payment method. New signups aren't available.</div>
  </div>
  <div class="rp-card">
    Sofort (Klarna Debit Risk) is used in Germany, Austria, Switzerland, and Belgium — compatible with EUR, CHF, and GBP. For recurring transactions, SEPA is used instead of Sofort. Sofort is being phased out by Klarna and replaced by Klarna Debit Risk. No major technical changes are required, but the country code must be passed for proper routing. Update your Recurly.js implementations accordingly.
  </div>
  <div class="rp-callout rp-callout-warning">
    <div><strong>Sofort restrictions</strong>
      <ul style="margin:6px 0 0;padding-left:18px;">
        <li>Free trials aren't supported — use SEPA Direct Debit instead.</li>
        <li>Not compatible with subscriptions with a deferred start date.</li>
        <li>Chargeback management isn't available.</li>
        <li>Recurly's Hosted Payment Pages don't support Sofort.</li>
        <li>Sofort/Klarna Debit Risk isn't the BNPL/Buy Now Pay Later version of Klarna.</li>
      </ul>
    </div>
  </div>

  <div class="rp-h3" id="boleto">Boleto</div>
  <div class="rp-card">
    Boleto Bancário is a popular BRL payment method in Brazil. Because Boleto doesn't support direct recurring transactions, each renewal generates a new invoice — initially "Past Due" until the customer pays.
  </div>
  <div class="rp-card">
    <div class="rp-h4" id="boleto-recurly-config">In Recurly</div>
    <ul style="margin:6px 0 14px;padding-left:20px;">
      <li>Activate Brazilian Real (BRL) currency.</li>
      <li>Integrate Adyen as a gateway.</li>
      <li>Use Recurly.js to integrate Boleto into your checkout page.</li>
      <li>Set up a Boleto-specific email template for recurring payments with a link to download the Boleto invoice.</li>
    </ul>
    <div class="rp-h4" id="boleto-adyen-config">In Adyen</div>
    <ul style="margin:6px 0 0;padding-left:20px;">
      <li>Contact your Adyen representative to align your account with a Brazilian entity.</li>
      <li>Enable the Boleto payment method in your Adyen account settings.</li>
      <li>Confirm BRL is activated.</li>
    </ul>
  </div>

  <div class="rp-h3" id="currency-considerations-isk-and-clp">Currency considerations — ISK and CLP</div>
  <div class="rp-card">
    ISK and CLP are zero-decimal currencies, but Adyen hasn't updated their logic to reflect this. Recurly automatically appends <code>00</code> to the decimal places when sending these transactions to Adyen. Don't add the <code>00</code> in your own integration — this overcharges customers. Example: sending <code>23</code> → Recurly sends <code>2300</code> to Adyen. A plan set to <code>23.00</code> → Recurly also sends <code>2300</code>.
  </div>

  <div class="rp-h3" id="address-accuracy">Address accuracy</div>
  <div class="rp-card">
    Adyen requires a complete shipping address to avoid errors. Recurly won't send partial addresses. If you use Adyen's reporting or fraud services with shipping data, confirm the full address is stored — street address, city, state, country, and postal code. If any field is absent, Recurly omits the entire shipping address.
  </div>

  <div class="rp-h1" id="gateway-feature-support">Gateway feature support</div>

  <div class="rp-h2" id="adyen-real-time-account-updater-rtau">Adyen Real Time Account Updater (RTAU)</div>
  <div class="rp-card">
    Adyen RTAU updates card details and expiration dates in real time during a transaction. To process encrypted PCI card data returned by Adyen, generate an RSA key in Recurly and provide the public key to Adyen. Before starting, confirm with Adyen that RTAU is enabled for your account and that required agreements are in place.
  </div>

  <div class="rp-h3" id="rtau-eligibility-requirements">Eligibility requirements</div>
  <ul class="rp-list">
    <li>Using raw cards with Adyen as your primary gateway through a supported Recurly API or Recurly.js — not Adyen Web Components.</li>
    <li>Not using Adyen gateway tokens or network tokens.</li>
    <li>Not using Adyen third-party checkout or components through Recurly.js.</li>
  </ul>

  <div class="rp-h3" id="rtau-recurly-configuration">Recurly configuration — RSA key</div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Navigate to Payment Gateways</h4><p>Go to Configuration → Payment Gateways.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Open Manage Keys</h4><p>On your Adyen gateway, select Options, then Manage Keys.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Add or reuse a key</h4><p>Select Add a Real Time Account Updater Key. If you have multiple Adyen instances pointing to the same account, you can share an existing RSA key.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">4</div><div><h4>Generate or select a key</h4><p>Select Generate New Key to create one, or Use Existing Key to reuse one across multiple instances.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">5</div><div><h4>Add the key</h4><p>Select Add Key.</p></div></div>
  </div>

  <div class="rp-h3" id="rtau-adyen-configuration">Adyen configuration — RSA key and RTAU enablement</div>
  <div class="rp-card">
    You can't configure the RSA key directly in the Adyen dashboard. Copy the public key from Recurly and provide it to Adyen via a support ticket — include the key exactly as shown. Once Adyen applies it, RTAU starts working automatically.
  </div>

  <div class="rp-h3" id="how-adyen-rtau-works-with-recurly-account-updater">How Adyen RTAU works with Recurly Account Updater</div>
  <div class="rp-card">
    If both services are enabled, card updates through Adyen RTAU won't be sent to Recurly Account Updater. Adyen supports Visa, Mastercard, and regional American Express only. To keep receiving Discover and additional American Express updates, leave Recurly Account Updater enabled alongside Adyen RTAU. RTAU updates may include card PAN changes (Recurly decrypts the PAN and updates billing info — the updated card is used to complete the current transaction and saved for future use), card expiration date changes (Recurly updates the expiration date on file), closed account notices (Recurly invalidates the billing info for the account), and contact customer notices (Recurly logs the response in Account Activities when a transaction declines — no billing info update is made).
  </div>

  <div class="rp-h3" id="disabling-rsa-keys-for-adyen-rtau">Disabling RSA keys for Adyen RTAU</div>
  <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Navigate to Payment Gateways</h4><p>Go to Configuration → Payment Gateways.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Open Manage Keys</h4><p>Select Options → Manage Keys on the Adyen gateway.</p></div></div>
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Revoke the key</h4><p>Select Revoke. Also contact Adyen to disable RTAU on their side. Recurly Account Updater resumes processing supported card brands after RTAU is disabled.</p></div></div>
  </div>

  <div class="rp-h2" id="network-tokens">Network tokens</div>
  <div class="rp-card">
    If Adyen is enabled to create network tokens for your merchant account, Recurly shows whether a network token was used on each transaction — visible in transaction details in the Admin UI and in gateway parameter responses through the API. Recurly displays this as the boolean field Third Party Network Token Used: <code>False</code> means a raw PAN or card data was used; <code>True</code> means a network token was used. If network tokens aren't enabled in your Adyen account, this value is always <code>False</code>. Token usage is determined by Adyen — contact Adyen support for questions.
  </div>
  <div class="rp-callout rp-callout-important">
    <div><strong>Tokenization scope</strong>Adyen uses network tokenization only for tokenized payment methods. Recurly supports tokenizing cards only when you use Adyen Web Components through Recurly.js. If you're using third-party checkout, you get network token behavior by default.</div>
  </div>

  <div class="rp-h2" id="revenue-protect-and-protect-premium">Revenue Protect and Protect Premium</div>
  <div class="rp-card">
    Recurly sends the data Adyen needs to evaluate risk and apply your Revenue Protect or Protect Premium rules. If you have Adyen Protect Premium, create custom risk profiles in Adyen and pass the profile ID to Recurly when creating subscriptions or one-time charges through the V3 API. The V3 field is <code>billing_info.adyen_risk_profile_reference_id</code>. See Adyen's <a href="https://docs.adyen.com/risk-management/create-and-use-risk-profiles/" target="_blank">Create Risk Profiles</a> reference.
  </div>

  <div class="rp-h3" id="data-recurly-sends-to-support-risk-decisions">Data Recurly sends to support risk decisions</div>
  <ul class="rp-list">
    <li><strong>Billing and shipping address data</strong> — see <a href="#address-accuracy">Address accuracy</a>.</li>
    <li><strong>Shipping method and amount</strong> — Recurly sends the invoice shipping amount and shipping method Name value to Adyen.</li>
    <li><strong>Browser information</strong> — sent when the shopper goes through 3DS.</li>
    <li><strong>Shopper data</strong> — email address, phone number, name, IP address (in-session only), and shopper reference. Shopper IP addresses are not sent to Adyen on renewals.</li>
    <li><strong>Acquisition date</strong> — send using <code>acquisition.acquired_at</code> in the V3 API. See the <a href="https://recurly.com/developers/api/v2021-02-25/#operation/create_purchase" target="_blank">V3 acquired_at field documentation</a>.</li>
  </ul>
  <div class="rp-callout rp-callout-warning">
    <div><strong>Protect Premium limitation</strong>Review rules aren't supported for Adyen Protect when using Purchase transactions. If you need Review, use an Authorize and Capture flow. When using purchases, use only Allow, Block, or Check for 3DS actions.</div>
  </div>

  <div class="rp-h2" id="how-asynchronous-payments-work">How asynchronous payments work</div>
  <div class="rp-card">
    After a successful purchase, the subscription becomes active, but the invoice and transaction remain "processing" until Adyen confirms payment approval. Recurly sends a "processing payment" webhook and a "payment processing" email to customers (if enabled). Adyen's initial return token is "unverified" while the bank confirms payment. Within 48 hours, the token becomes "verified" and additional transactions can proceed. Recurly updates the transaction and invoice status based on Adyen feedback and sends the relevant webhooks and emails. Asynchronous payments require special dunning handling — see the <a href="https://docs.recurly.com/docs/paypal-payments#paypal-echecks" target="_blank">PayPal eChecks guidance</a> for reference.
  </div>

  <div class="rp-h2" id="billing-information-updates">Billing information updates</div>
  <div class="rp-card">
    Direct customers to Recurly hosted pages or build your own API connection for billing updates. Recurly charges a small amount or a zero-dollar verification. After Adyen approves the request, Recurly automatically issues a refund.
  </div>

  <div class="rp-h2" id="ip-address-allowlist">IP address allowlist</div>
  <div class="rp-card">
    In some scenarios, Adyen may use additional IP addresses that must be allowlisted in Recurly. Contact Recurly Support before moving to production.
  </div>

  <div class="rp-h2" id="api-integration-with-recurly">API integration with Recurly</div>
  <div class="rp-card">
    In a standard Recurly.js flow, Recurly handles payment authorization. The customer enters billing details first. After authorization, you create the subscription and process the charge.
  </div>

  <div class="rp-h2" id="important-notes">Important notes</div>
  <div class="rp-card">
    Follow customer notification requirements — for example, SEPA renewal notices. Recurly can export billing information from Adyen for SEPA subscription renewals. Recurly sends purchase transactions to Adyen with a capture flag, overriding your Adyen capture settings.
  </div>

  <div class="rp-h1" id="troubleshooting">Troubleshooting</div>

</div>
`}</HTMLBlock>

<Accordion title="A tokenized payment method I'm using isn't allowing conversions, or subscriptions are failing. What can I do?">
Confirm you've enabled the required webhooks. `RECURRING_CONTRACT` webhooks are critical for all non-card payment methods. Review the webhook configuration section above and make sure every required event code is active in both the Standard Webhooks page and the Webhooks Settings page in Adyen.
</Accordion>

<Accordion title="My customer got a decline from Adyen at checkout. What happened?">
Start with the decline code shown in the Recurly Admin UI for the transaction. If the decline is related to 3DS, confirm 3DS is enabled and configured in both Adyen and your Recurly.js implementation. If 3DS is already enabled, the customer may not have completed the 3DS challenge — in which case the decline is expected behavior.
</Accordion>