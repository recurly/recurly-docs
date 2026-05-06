---
title: Copy of Mercado Pago integration guide
excerpt: Create subscriptions via Purchase API using Mercado Pago with Ebanx.
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

  .rp-page {
    font-family: var(--font);
    color: var(--deepchar);
    font-size: 15px;
    line-height: 1.6;
    max-width: 860px;
  }

  .rp-overview {
    border-left: 4px solid var(--yellow);
    background: var(--offwhite);
    padding: 16px 22px;
    border-radius: 0 8px 8px 0;
    margin-bottom: 20px;
    font-size: 15px;
    color: var(--darkgray);
  }

  .rp-plan {
    display: inline-block;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 13px;
    font-weight: 700;
    padding: 6px 16px;
    border-radius: 20px;
    margin-bottom: 24px;
    letter-spacing: 0.3px;
  }

  .rp-cost {
    border-left: 4px solid var(--tangerine);
    background: #FFF8F2;
    padding: 14px 20px;
    border-radius: 0 8px 8px 0;
    margin-bottom: 20px;
    font-size: 14px;
    color: var(--darkgray);
  }
  .rp-cost a { color: var(--tangerine); }

  .rp-definition {
    background: var(--brightgray);
    border-radius: 10px;
    padding: 22px 26px;
    margin-bottom: 28px;
    font-size: 15px;
    color: var(--darkgray);
    line-height: 1.7;
  }

  .rp-benefits {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
    gap: 14px;
    margin-bottom: 32px;
  }
  .rp-benefits.rp-benefits-2x2 { grid-template-columns: repeat(2, 1fr); }
  .rp-benefit {
    background: var(--offblack);
    color: var(--offwhite);
    border-radius: 10px;
    padding: 20px;
  }
  .rp-benefit-icon { color: var(--yellow); font-size: 20px; margin-bottom: 10px; }
  .rp-benefit strong {
    display: block; font-size: 14px; font-weight: 700;
    margin-bottom: 6px; color: var(--offwhite);
  }
  .rp-benefit span { font-size: 13px; color: var(--lightgray); line-height: 1.5; }

  .rp-h1 {
    font-size: 1.5rem; font-weight: 800; color: var(--offblack);
    margin: 36px 0 14px; padding-bottom: 8px;
    border-bottom: 2px solid var(--yellow);
  }
  .rp-h2 { font-size: 1.1rem; font-weight: 700; color: var(--darknavy); margin: 28px 0 10px; }
  .rp-h3 { font-size: 0.95rem; font-weight: 700; color: var(--darkgray); margin: 20px 0 8px; }
  .rp-h4 { font-size: 0.9rem; font-weight: 600; color: var(--darkgray); margin: 16px 0 6px; }

  .rp-card {
    background: var(--offwhite);
    border: 1px solid var(--lightgray);
    border-radius: 10px;
    padding: 22px 26px;
    margin-bottom: 20px;
    font-size: 14px;
    color: var(--darkgray);
    line-height: 1.65;
  }

  .rp-steps { display: flex; flex-direction: column; margin-bottom: 24px; }
  .rp-step {
    display: flex; gap: 16px; align-items: flex-start;
    background: var(--offwhite); border: 1px solid var(--lightgray);
    border-radius: 10px; padding: 18px 22px;
    margin-bottom: 12px;
  }
  .rp-steps .rp-step { margin-bottom: 0; }
  .rp-steps .rp-step + .rp-step { margin-top: 12px; }
  .rp-step-num {
    width: 34px; height: 34px; border-radius: 50%;
    background: var(--yellow); color: var(--offblack);
    font-weight: 800; font-size: 14px;
    display: flex; align-items: center; justify-content: center; flex-shrink: 0;
  }
  .rp-step h4 { font-size: 0.95rem; font-weight: 700; color: var(--offblack); margin: 0 0 4px; }
  .rp-step p  { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }

  .rp-callout {
    border-radius: 0 8px 8px 0; padding: 14px 18px; margin: 16px 0;
    font-size: 14px; display: flex; gap: 12px; align-items: flex-start;
  }
  .rp-callout strong { display: block; margin-bottom: 3px; }
  .rp-callout-note      { border-left: 4px solid var(--offblack); background: var(--brightgray); color: var(--deepchar); }
  .rp-callout-tip       { border-left: 4px solid var(--yellow);    background: var(--offwhite);   color: var(--darkgray); }
  .rp-callout-warning   { border-left: 4px solid var(--tangerine); background: #FFF8F2;            color: var(--darkgray); }
  .rp-callout-important { border-left: 4px solid var(--vermillion);background: #FFF5F2;            color: var(--darkgray); }

  .rp-btn {
    display: inline-block; padding: 10px 22px; border-radius: 8px;
    font-weight: 700; font-size: 14px; text-decoration: none;
    margin: 6px 8px 6px 0; font-family: var(--font);
  }
  .rp-btn-primary   { background: var(--offblack); color: var(--yellow); }
  .rp-btn-secondary { background: var(--yellow);   color: var(--offblack); }
  .rp-btn-ghost     { background: transparent; color: var(--darkgray); border: 1px solid var(--lightgray); }

  .rp-gw-table { width: 100%; border-collapse: collapse; font-size: 14px; margin-bottom: 28px; }
  .rp-gw-table tr.rp-thead-row td {
    background: var(--offblack) !important;
    color: var(--offwhite) !important;
    font-weight: 700;
    padding: 12px 16px;
  }
  .rp-gw-table tr.rp-thead-row td:first-child { color: var(--offwhite) !important; }
  .rp-gw-table td { padding: 12px 16px; vertical-align: top; background: var(--offwhite) !important; }
  .rp-gw-table tr:not(.rp-thead-row) td:first-child {
    font-weight: 600; color: var(--offblack); width: 35%;
  }
  .rp-gw-table a { color: var(--tangerine); }

  .rp-pm-table { width: 100%; border-collapse: collapse; font-size: 13px; margin: 12px 0 24px; }
  .rp-pm-table tr.rp-thead-row td {
    background: var(--offblack) !important;
    color: var(--offwhite) !important;
    font-weight: 700;
    padding: 10px 12px;
  }
  .rp-pm-table tr.rp-thead-row td:first-child { color: var(--offwhite) !important; }
  .rp-pm-table td { padding: 10px 12px; border-bottom: 1px solid var(--lightgray); vertical-align: top; background: var(--offwhite) !important; }
  .rp-pm-table tr:not(.rp-thead-row) td:first-child { font-weight: 600; color: var(--offblack); }

  .rp-params { width: 100%; border-collapse: collapse; font-size: 14px; margin: 12px 0 24px; }
  .rp-params tr.rp-thead-row td {
    background: var(--offblack) !important;
    color: var(--offwhite) !important;
    font-weight: 700;
    padding: 10px 14px;
  }
  .rp-params tr.rp-thead-row td:first-child { color: var(--offwhite) !important; }
  .rp-params td { padding: 10px 14px; border-bottom: 1px solid var(--lightgray); vertical-align: top; background: var(--offwhite) !important; }
  .rp-params tr:not(.rp-thead-row) td:first-child { font-weight: 600; color: var(--offblack); width: 28%; }

  .rp-dl-btn {
    display: inline-block; background: var(--yellow); color: var(--offblack);
    font-family: var(--font); font-size: 14px; font-weight: 700;
    padding: 10px 22px; border-radius: 8px; text-decoration: none; margin-bottom: 20px;
  }

  .rp-list {
    background: var(--offwhite); border: 1px solid var(--lightgray);
    border-radius: 10px; padding: 16px 22px 16px 38px;
    margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.7;
  }

  .rp-video { position: relative; padding-top: 56.25%; margin-bottom: 28px;
              border-radius: 10px; overflow: hidden; }
  .rp-video iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }

  /* Click-to-expand image lightbox — JavaScript-free, checkbox-driven */
  .rp-zoom { display: contents; }
  .rp-zoom-toggle { position: absolute; opacity: 0; pointer-events: none; }
  .rp-zoom-img { cursor: zoom-in; transition: opacity 0.15s ease; }
  .rp-zoom-img:hover { opacity: 0.88; }
  .rp-zoom-overlay {
    display: none;
    position: fixed; inset: 0;
    background: rgba(13, 13, 11, 0.92);
    z-index: 9999;
    cursor: zoom-out;
    align-items: center; justify-content: center;
    padding: 40px;
  }
  .rp-zoom-overlay img {
    max-width: 95%; max-height: 95vh;
    border-radius: 8px;
    box-shadow: 0 20px 60px rgba(0,0,0,0.4);
  }
  .rp-zoom-overlay::after {
    content: "✕";
    position: absolute; top: 20px; right: 28px;
    color: var(--offwhite); font-size: 28px; font-weight: 300;
    opacity: 0.7;
  }
  .rp-zoom-toggle:checked ~ .rp-zoom-overlay { display: flex; }

  /* Table of contents navigation pills */
  .rp-toc {
    display: flex; flex-wrap: wrap; gap: 8px;
    margin: 0 0 32px;
  }
  .rp-toc-pill {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 8px 16px; border-radius: 20px;
    border: 1px solid var(--offblack); background: var(--offblack);
    color: var(--offwhite) !important; text-decoration: none !important;
    font-size: 13px; font-weight: 700;
    transition: background 0.15s, border-color 0.15s, color 0.15s;
  }
  .rp-toc-pill:hover {
    background: var(--tangerine);
    border-color: var(--tangerine);
    color: var(--offblack) !important;
  }
  .rp-toc-num {
    display: inline-flex; align-items: center; justify-content: center;
    width: 22px; height: 22px; border-radius: 50%;
    background: var(--yellow); color: var(--offblack);
    font-size: 11px; font-weight: 800; flex-shrink: 0;
    text-decoration: none !important;
  }

  /* Clickable heading anchors — click to set URL hash, copy from address bar */
  .rp-anchor { color: inherit; text-decoration: none; }
  .rp-anchor::after {
    content: " #"; opacity: 0;
    color: var(--lightgray); font-weight: 400; font-size: 0.75em;
    transition: opacity 0.15s;
  }
  .rp-anchor:hover::after { opacity: 1; }

  /* Plain ordered/unordered lists — used for sub-steps inside rp-h2 step headings.
     Excludes rp-list which has its own styled padding. */
  .rp-page ol:not(.rp-list), .rp-page ul:not(.rp-list) {
    margin: 8px 0 16px;
    padding-left: 24px;
  }
  .rp-page ol:not(.rp-list) li, .rp-page ul:not(.rp-list) li {
    margin-bottom: 6px;
    line-height: 1.6;
  }

  /* Code snippets — single or tabbed. Lives inside the HTMLBlock so the page
     doesn't have to split for fenced code blocks. JS helpers rpTab/rpCopy below. */
  .rp-code {
    background: var(--offblack);
    color: var(--offwhite);
    border: 1px solid var(--darkgray);
    border-radius: 10px;
    margin: 16px 0 24px;
    overflow: hidden;
    font-family: 'Menlo', 'Monaco', 'Consolas', 'Courier New', monospace;
    font-size: 13px;
    line-height: 1.55;
  }
  .rp-code-header {
    display: flex; align-items: center; justify-content: space-between;
    gap: 12px; flex-wrap: wrap;
    background: var(--darkgray);
    padding: 8px 14px;
    border-bottom: 1px solid var(--offblack);
    font-family: var(--font);
  }
  .rp-code-lang {
    color: var(--lightgray);
    font-size: 12px; font-weight: 700;
    text-transform: lowercase; letter-spacing: 0.4px;
  }
  .rp-code-tablist { display: flex; gap: 4px; flex-wrap: wrap; }
  .rp-code-tab {
    background: transparent; border: 0;
    color: var(--lightgray);
    font-family: inherit; font-size: 12px; font-weight: 700;
    padding: 5px 12px; border-radius: 14px;
    cursor: pointer;
    transition: background 0.12s, color 0.12s;
  }
  .rp-code-tab:hover { background: rgba(255,253,242,0.08); color: var(--offwhite); }
  .rp-code-tab-active,
  .rp-code-tab-active:hover { background: var(--yellow); color: var(--offblack); }
  .rp-code-copy {
    background: transparent;
    border: 1px solid var(--gray);
    color: var(--lightgray);
    font-family: inherit; font-size: 12px; font-weight: 700;
    padding: 4px 12px; border-radius: 6px;
    cursor: pointer; flex-shrink: 0;
    transition: background 0.12s, border-color 0.12s, color 0.12s;
  }
  .rp-code-copy:hover {
    background: var(--tangerine); border-color: var(--tangerine);
    color: var(--offblack);
  }
  .rp-code-body {
    margin: 0;
    padding: 16px 18px;
    overflow-x: auto;
    font-family: inherit; font-size: inherit; line-height: inherit;
    color: var(--offwhite); background: var(--offblack);
    white-space: pre;
  }
  .rp-code-body code {
    font-family: inherit; font-size: inherit;
    background: transparent; color: inherit; padding: 0;
  }
  .rp-code:not(.rp-code-tabs) .rp-code-body { display: block; }
  .rp-code-tabs .rp-code-body { display: none; }
  .rp-code-tabs .rp-code-body.rp-code-body-active { display: block; }

  @media (max-width: 640px) {
    .rp-benefits,
    .rp-benefits.rp-benefits-2x2 { grid-template-columns: 1fr; }
    .rp-h1 { font-size: 1.25rem; }
  }
</style>
<script>
function rpTab(btn, idx) {
  var wrap = btn.closest('.rp-code-tabs');
  if (!wrap) return;
  var tabs = wrap.querySelectorAll('.rp-code-tab');
  var bodies = wrap.querySelectorAll('.rp-code-body');
  for (var i = 0; i < tabs.length; i++) tabs[i].classList.toggle('rp-code-tab-active', i === idx);
  for (var i = 0; i < bodies.length; i++) bodies[i].classList.toggle('rp-code-body-active', i === idx);
}
function rpCopy(btn) {
  var wrap = btn.closest('.rp-code');
  if (!wrap) return;
  var body = wrap.classList.contains('rp-code-tabs')
    ? wrap.querySelector('.rp-code-body.rp-code-body-active')
    : wrap.querySelector('.rp-code-body');
  if (!body) return;
  var text = body.textContent.replace(/\s+$/, '');
  if (navigator.clipboard && navigator.clipboard.writeText) {
    navigator.clipboard.writeText(text).then(function () { rpFlashCopied(btn); }).catch(function () {});
  } else {
    var ta = document.createElement('textarea');
    ta.value = text;
    ta.setAttribute('readonly', '');
    ta.style.position = 'absolute'; ta.style.left = '-9999px';
    document.body.appendChild(ta);
    ta.select();
    try { document.execCommand('copy'); rpFlashCopied(btn); } catch (e) {}
    document.body.removeChild(ta);
  }
}
function rpFlashCopied(btn) {
  if (!btn.dataset.label) btn.dataset.label = btn.textContent;
  btn.textContent = 'Copied';
  setTimeout(function () { btn.textContent = btn.dataset.label; }, 1500);
}
</script>
<div class="rp-page">

  <div class="rp-overview">
    This guide walks through creating new subscriptions with Mercado Pago using Recurly's Purchase endpoint. You'll see how to generate a payment request, handle 3DS authentication through Recurly.js, and test the integration against the Ebanx sandbox simulator before going live.
  </div>

  <div class="rp-plan">[TODO: Confirm plan availability]</div>

  <div class="rp-h3" id="prerequisites"><a class="rp-anchor" href="#prerequisites">Prerequisites</a></div>
  <ul class="rp-list">
    <li>Familiarity with Recurly's API, webhooks, and basic REST concepts</li>
    <li>Completed the Quickstart Guide</li>
    <li>Familiarity with Recurly.js</li>
    <li>An Ebanx gateway account with Mercado Pago enabled</li>
  </ul>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>

  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>
  <div class="rp-definition">
    A purchase creates a customer account and subscription together in a single call to Recurly's Purchase endpoint. Bundling all the required resources into one request keeps your checkout flow simple — no multi-step orchestration on your end.
  </div>

  <div class="rp-h1" id="key-benefits"><a class="rp-anchor" href="#key-benefits">Key benefits</a></div>
  <div class="rp-benefits">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Single API call</strong>
      <span>Create the account, billing info, and subscription in one consolidated Purchase request.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Brazilian market reach</strong>
      <span>Accept Mercado Pago through Ebanx to support customers in Brazil and across LATAM.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Built-in 3DS handling</strong>
      <span>Recurly.js manages the consumer authentication flow with a token-based redirect — no custom modal required.</span>
    </div>
  </div>

  <div class="rp-h1" id="key-details"><a class="rp-anchor" href="#key-details">Key details</a></div>

  <div class="rp-h2" id="step-1-generate-a-mercado-pago-payment-request"><a class="rp-anchor" href="#step-1-generate-a-mercado-pago-payment-request">Step 1: Generate a Mercado Pago payment request</a></div>
  <p>Use a supported client library or set the payment type field in your front-end code. To specify Mercado Pago, set the <code>type</code> enum to <code>mercadopago</code> and pass the required fields. Send the request to the <code>create_purchase</code> method on Recurly's API, including:</p>
  <ul class="rp-list">
    <li>Customer account data — code, name, billing info, phone number, and email address</li>
    <li>Subscriptions — with plan codes</li>
    <li>Payment method type — <code>mercadopago</code></li>
  </ul>

  <div class="rp-code rp-code-tabs">
    <div class="rp-code-header">
      <div class="rp-code-tablist">
        <button type="button" class="rp-code-tab rp-code-tab-active" onclick="rpTab(this,0)">Ruby</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,1)">JavaScript</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,2)">Python</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,3)">Java</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,4)">C#</button>
      </div>
      <button class="rp-code-copy" type="button" onclick="rpCopy(this)">Copy</button>
    </div>
    <pre class="rp-code-body rp-code-body-active"><code>purchase = {
  currency: "BRL",
  account: {
    code: "bdumonde",
    first_name: "Benjamin",
    last_name: "Du Monde",
    email: "bdumonde@example.com",
    billing_info: {
      address: {
        street1: "Avenida Nipo-brasileira 1007",
        city: "Braganca Paulista",
        region: "BR",
        postal_code: "123456",
        country: "BR",
        phone: "1234679099"
      }
    },
    type: "mercadopago"
  },
  subscriptions: [
    { plan_code: "coffee-monthly" }
  ]
}
invoice_collection = @client.create_purchase(body: purchase)</code></pre>
    <pre class="rp-code-body"><code>// TODO: Add JavaScript example</code></pre>
    <pre class="rp-code-body"><code># TODO: Add Python example</code></pre>
    <pre class="rp-code-body"><code>// TODO: Add Java example</code></pre>
    <pre class="rp-code-body"><code>// TODO: Add C# example</code></pre>
  </div>

  <div class="rp-callout rp-callout-tip">
    <div><strong>Tip</strong>Many more parameters are available. See the <a href="[TODO: Add Create Purchase reference URL]">Create Purchase reference</a> to learn more.</div>
  </div>

  <div class="rp-h2" id="step-2-obtain-the-token-from-the-response"><a class="rp-anchor" href="#step-2-obtain-the-token-from-the-response">Step 2: Obtain the token from the response</a></div>
  <p>Submitting your API request returns a response like this:</p>

  <div class="rp-code">
    <div class="rp-code-header">
      <span class="rp-code-lang">json</span>
      <button class="rp-code-copy" type="button" onclick="rpCopy(this)">Copy</button>
    </div>
    <pre class="rp-code-body"><code>{
  "error": {
    "type": "transaction",
    "message": "Your card must be authenticated with 3-D Secure before continuing.",
    "transaction_error": {
      "object": "transaction_error",
      "transaction_id": "xt43lgkyc7s4",
      "category": "three_d_secure_action_required",
      "code": "three_d_secure_action_required",
      "decline_code": null,
      "message": "Your card must be authenticated with 3-D Secure before continuing.",
      "merchant_advice": "Your payment gateway is requesting that the transaction be completed with 3-D Secure.",
      "three_d_secure_action_token_id": "kFzyWEnvBZ82pccJwGiMag",
      "fraud_info": null
    }
  }
}</code></pre>
  </div>

  <p>Mercado Pago requires consumer authentication, so you'll use Recurly.js to let consumers authenticate their identity and authorize payments in their mobile apps. Use the <code>three_d_secure_action_token_id</code> value to render the authentication modal.</p>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>This initial call returns different behavior in production than in sandbox — see the sandbox callout in Step 3.</div>
  </div>

  <div class="rp-h2" id="step-3-interact-with-recurlyjs"><a class="rp-anchor" href="#step-3-interact-with-recurlyjs">Step 3: Interact with Recurly.js</a></div>
  <p>Follow the 3DS Redirect Guide, starting at Step 3.</p>
  <a class="rp-btn rp-btn-primary" href="https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/step-3-process-the-responsew" target="_blank">Open 3DS Redirect Guide →</a>

  <div class="rp-callout rp-callout-note">
    <div><strong>Sandbox behavior</strong>In sandbox, the modal displays the Ebanx-specific sandbox UI. You'll need to manually press buttons to simulate enrollments — accepted, denied, or declined responses are all available.</div>
  </div>

  <div class="rp-h2" id="step-4-submit-a-new-purchase-request"><a class="rp-anchor" href="#step-4-submit-a-new-purchase-request">Step 4: Submit a new Purchase request</a></div>
  <p>Once the user has interacted with the modal, you'll have a <code>three_d_secure_action_result_token_id</code> from Recurly.js. Resubmit your original request with this token to finalize authentication. The account and billing info must match the original request — changing these details will cause a token mismatch error.</p>
  <p>Your JSON payload may look like this:</p>

  <div class="rp-code">
    <div class="rp-code-header">
      <span class="rp-code-lang">json</span>
      <button class="rp-code-copy" type="button" onclick="rpCopy(this)">Copy</button>
    </div>
    <pre class="rp-code-body"><code>{
  "subscriptions": [
    {
      "plan_code": "monthly-plan"
    }
  ],
  "account": {
    "code": "maddams",
    "email": "maddams@recurly.com",
    "billing_info": {
      "first_name": "M",
      "last_name": "Addams",
      "address": {
        "street1": "Avenida Nipo-brasileira 1007",
        "city": "Braganca Paulista",
        "region": "BR",
        "postal_code": "12902-020",
        "country": "BR",
        "phone": "123456790"
      },
      "type": "mercadopago",
      "three_d_secure_action_result_token_id": "action-result-id"
    }
  },
  "currency": "BRL"
}</code></pre>
  </div>

  <div class="rp-h2" id="step-5-verify-and-finish"><a class="rp-anchor" href="#step-5-verify-and-finish">Step 5: Verify and finish</a></div>
  <p>After a successful purchase, confirm the details via the Recurly Admin UI or by calling Recurly's API to list the new account, subscription, or invoice.</p>

  <div class="rp-h2" id="step-6-listen-for-webhooks"><a class="rp-anchor" href="#step-6-listen-for-webhooks">Step 6: Listen for webhooks</a></div>
  <p>After a successful signup, listen to the relevant webhooks so you can grant feature access in your environment — and revoke access if a consumer cancels their subscription from within their mobile banking application.</p>

  <div class="rp-card">
    <div class="rp-h3" id="next-steps"><a class="rp-anchor" href="#next-steps">Next steps</a></div>
    <p>Now that you can create new subscriptions with Mercado Pago, explore the Mercado Pago payment method guide for other use cases and limitations.</p>
    <a class="rp-btn rp-btn-primary" href="[TODO: Add Mercado Pago payment method guide URL]" target="_blank">Open payment method guide →</a>
  </div>

</div>
`}</HTMLBlock>