---
title: Copy of Authorize.net
excerpt: >-
  Harness the power of Authorize.net’s global payment solutions, seamlessly
  integrated with Recurly, to elevate your business's payment experience.
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

<HTMLBlock>{`
<div class="rp-page">
 
  <div class="rp-overview">Authorize.net is a widely supported payment gateway that connects your Recurly account to credit card processors worldwide. It supports recurring subscriptions, ecommerce, and MOTO transactions, with built-in fraud prevention through Address Verification Service (AVS) and Card Code Verification (CVV).</div>
 
  <div class="rp-plan">✦ Available on all Recurly plans</div>
 
  <div class="rp-h3" id="limitations"><a class="rp-anchor" href="#limitations">Limitations</a></div>
  <ul class="rp-list">
    <li>Authorize.net's API returns limited decline detail. Recurly uses decline reasons, merchant-advice-code logic, and network responses to inform retry behavior. Because Authorize.net's responses are generic, Recurly follows the gateway's own best practices — declines flagged as "hard" (expired cards, lost or stolen cards) are not retried. See <a href="https://support.authorize.net/knowledgebase/Knowledgearticle/?code=000001111" target="_blank">Authorize.net's knowledgebase</a> for the full list of gateway response codes.</li>
    <li>Recurly does not support Authorize.net's fraud review flow. If you use Authorize.net's fraud monitoring, the gateway may void transactions that Recurly initially approved. Monitor your Authorize.net account directly to catch any post-approval cancellations outside Recurly's visibility.</li>
    <li>Authorize.net does not return raw Network Transaction IDs (NTIDs). If you need to migrate away from Authorize.net, contact Recurly Support to start an NTID migration conversation with our team and Authorize.net directly.</li>
  </ul>
 
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#gateway-feature-support"><span class="rp-toc-num">3</span>Gateway feature support</a>
  </div>
 
  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>
  <div class="rp-definition">Authorize.net is a payment gateway that facilitates secure credit card transactions between your payment portal — website or mobile app — and credit card processors. It provides tools to accept payments and prevent fraud, and it's available to merchants worldwide across multiple currencies.</div>
 
  <div class="rp-h1" id="key-details"><a class="rp-anchor" href="#key-details">Key details</a></div>
 
  <table class="rp-gw-table">
    <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
    <tr><td>Services that work with Recurly</td><td>Recurring subscriptions, payments (ecommerce and <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/" target="_blank">MOTO</a>)</td></tr>
    <tr><td>Supported operations</td><td>Anti-Fraud, Authorize and Capture, Purchase, Refund, Verify, Void</td></tr>
    <tr><td>Supported payment types</td><td>Credit card</td></tr>
    <tr><td>Supported card brands</td><td>Visa, Mastercard, Amex, Discover, JCB, Diners Club, Union Pay</td></tr>
    <tr><td>Gateway-specific 3DS2 supported</td><td>No — Authorize.net does not support 3DS2</td></tr>
    <tr><td>Card on file supported</td><td>Yes</td></tr>
    <tr><td>Regions</td><td>Worldwide</td></tr>
    <tr><td>Currencies</td><td>AUD, CAD, EUR, GBP, NZD, PLN, and USD</td></tr>
    <tr><td>Gateway features</td><td>Address Verification Service (AVS), Card Code Verification (CVV)</td></tr>
  </table>
 
  <div class="rp-h2" id="setup"><a class="rp-anchor" href="#setup">Setup</a></div>
 
  <p style="font-size:14px; color:var(--darkgray); margin-bottom:20px;">The steps below walk you through signing up for an Authorize.net account, retrieving your API credentials, and configuring the gateway in Recurly. For pricing and new account signup, visit <a href="https://www.authorize.net/" target="_blank" style="color:var(--tangerine);">Authorize.net</a>.</p>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Sign up for an Authorize.net account</h4><p>Visit the <a href="https://www.authorize.net/sign-up/" target="_blank">Authorize.net signup page</a> and complete the application form with your business details. Once approved, log in to your Authorize.net account.</p></div>
    </div>
  </div>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Obtain your API Login ID and Transaction Key</h4><p>In your Authorize.net account, navigate to <strong>Account → Settings → API Credentials &amp; Keys</strong>. Note your API Login ID. If you don't have a Transaction Key or haven't created one before, select <strong>New Transaction Key</strong> and click <strong>Submit</strong>.</p></div>
    </div>
  </div>
 
  <div class="rp-callout rp-callout-important">
    <div><strong>Important</strong> The "Disable Old Transaction Key Immediately" checkbox will instantly break any active Authorize.net integrations the moment you click Submit. Only check this box if you've been instructed to do so for security purposes, or if no active integrations depend on your previous Transaction Keys.</div>
  </div>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-authnet-transaction-key" class="rp-zoom-toggle" />
    <label for="zoom-authnet-transaction-key">
      <img class="rp-zoom-img"
           src="https://files.readme.io/2c5f346-image.png"
           alt="Authorize.net API Credentials & Keys settings page showing the New Transaction Key option"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-authnet-transaction-key" class="rp-zoom-overlay">
      <img src="https://files.readme.io/2c5f346-image.png" alt="" />
    </label>
  </span>
 
  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong> In some cases, Authorize.net may ask for a PIN to create a Transaction Key. Check your email for a PIN from Authorize.net, copy it into the field provided, and click Submit to receive your Transaction Key.</div>
  </div>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-authnet-pin-modal" class="rp-zoom-toggle" />
    <label for="zoom-authnet-pin-modal">
      <img class="rp-zoom-img"
           src="https://files.readme.io/cdbb55e-image.png"
           alt="Authorize.net PIN verification modal"
           style="display:block; width:280px; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-authnet-pin-modal" class="rp-zoom-overlay">
      <img src="https://files.readme.io/cdbb55e-image.png" alt="" />
    </label>
  </span>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-authnet-pin-email" class="rp-zoom-toggle" />
    <label for="zoom-authnet-pin-email">
      <img class="rp-zoom-img"
           src="https://files.readme.io/4976dc3-image.png"
           alt="Example email from Authorize.net containing the PIN code"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-authnet-pin-email" class="rp-zoom-overlay">
      <img src="https://files.readme.io/4976dc3-image.png" alt="" />
    </label>
  </span>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Configure Authorize.net in Recurly</h4><p>In Recurly, navigate to <strong>Configuration → Payment Gateways</strong>, select <strong>Add a Gateway</strong>, and choose <strong>Authorize.net</strong>. Enter your API Login ID and Transaction Key.</p></div>
    </div>
  </div>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-authnet-credentials" class="rp-zoom-toggle" />
    <label for="zoom-recurly-authnet-credentials">
      <img class="rp-zoom-img"
           src="https://files.readme.io/060ff09-image.png"
           alt="Recurly payment gateway configuration screen with API Login ID and Transaction Key fields for Authorize.net"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-authnet-credentials" class="rp-zoom-overlay">
      <img src="https://files.readme.io/060ff09-image.png" alt="" />
    </label>
  </span>
 
  <p style="font-size:14px; color:var(--darkgray); margin:12px 0 8px;">Select the card types you want to accept — this depends on which types Authorize.net has approved for your account. Contact your Authorize.net representative if you're unsure.</p>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-card-types" class="rp-zoom-toggle" />
    <label for="zoom-recurly-card-types">
      <img class="rp-zoom-img"
           src="https://files.readme.io/73811e6-image.png"
           alt="Recurly card type selector for Authorize.net gateway configuration"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-card-types" class="rp-zoom-overlay">
      <img src="https://files.readme.io/73811e6-image.png" alt="" />
    </label>
  </span>
 
  <p style="font-size:14px; color:var(--darkgray); margin:12px 0 8px;">Select the currencies your Authorize.net account is approved to accept.</p>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-currency-picker" class="rp-zoom-toggle" />
    <label for="zoom-recurly-currency-picker">
      <img class="rp-zoom-img"
           src="https://files.readme.io/c4a227a-image.png"
           alt="Recurly currency selector for Authorize.net gateway"
           style="display:block; width:280px; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-currency-picker" class="rp-zoom-overlay">
      <img src="https://files.readme.io/c4a227a-image.png" alt="" />
    </label>
  </span>
 
  <p style="font-size:14px; color:var(--darkgray); margin:12px 0 8px;">Select which card types should support zero-dollar authorization (ZDA) transactions. ZDA lets Recurly verify a card's validity without billing any amount — useful for checking card health at signup without an initial charge.</p>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-zda" class="rp-zoom-toggle" />
    <label for="zoom-recurly-zda">
      <img class="rp-zoom-img"
           src="https://files.readme.io/b4559de-image.png"
           alt="Recurly zero-dollar authorization settings for Authorize.net"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-zda" class="rp-zoom-overlay">
      <img src="https://files.readme.io/b4559de-image.png" alt="" />
    </label>
  </span>
 
  <p style="font-size:14px; color:var(--darkgray); margin:12px 0 20px;">Once your configuration is complete, click <strong>Add Payment Gateway</strong> (or <strong>Update Payment Gateway</strong> if editing an existing setup).</p>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Set up Address Verification Service (AVS)</h4><p>In Recurly, navigate to <strong>Configuration → Payment Settings</strong> and scroll to the <strong>Address Verification Check</strong> section. Select your preferred AVS rules and click <strong>Save Changes</strong>.</p></div>
    </div>
  </div>
 
  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong> AVS settings apply across all supported gateways — they're not Authorize.net-specific. When AVS is enabled, Recurly rejects any transaction where the address provided doesn't match what the card issuer has on file. If you accept payments from international customers, be aware that AVS can't match postal codes containing letters (common outside the US). Recurly recommends allowing the transaction to proceed if either the street address or the postal code matches.</div>
  </div>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">5</div>
      <div><h4>Enable Card Code Verification (CVV)</h4><p>In Recurly, navigate to <strong>Configuration → Payment Settings</strong> and scroll to the <strong>Credit Card Verification Code Check</strong> section. Set the option to <strong>Enabled</strong> and click <strong>Save Changes</strong>.</p></div>
    </div>
  </div>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-cvv" class="rp-zoom-toggle" />
    <label for="zoom-recurly-cvv">
      <img class="rp-zoom-img"
           src="https://files.readme.io/9306094-image.png"
           alt="Recurly Credit Card Verification Code Check setting"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-cvv" class="rp-zoom-overlay">
      <img src="https://files.readme.io/9306094-image.png" alt="" />
    </label>
  </span>
 
  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong> CVV settings also apply across all supported gateways. When enabled, transactions with invalid or mismatched CVV codes are rejected based on issuer feedback. Per PCI regulations, CVV values cannot be stored — Recurly submits the CVV only on the initial transaction (new subscription creation or card number update). Subsequent transactions on the same card process normally once the issuer has established a positive transaction history with your merchant account.</div>
  </div>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">6</div>
      <div><h4>Test your integration</h4><p>In Recurly, navigate to <strong>Configuration → Payment Gateways → Authorize.net</strong> and click <strong>Test Configuration</strong>. A confirmation message confirms that Recurly can communicate with your Authorize.net account successfully.</p></div>
    </div>
  </div>
 
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-recurly-test-config" class="rp-zoom-toggle" />
    <label for="zoom-recurly-test-config">
      <img class="rp-zoom-img"
           src="https://files.readme.io/f5ff63a-image.png"
           alt="Recurly Test Configuration button and success confirmation for Authorize.net"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-recurly-test-config" class="rp-zoom-overlay">
      <img src="https://files.readme.io/f5ff63a-image.png" alt="" />
    </label>
  </span>
 
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">7</div>
      <div><h4>Go live</h4><p>Once the test passes, you're ready to accept real transactions. Monitor your transactions in both Recurly and Authorize.net to confirm everything is working as expected.</p></div>
    </div>
  </div>
 
  <div class="rp-h1" id="gateway-feature-support"><a class="rp-anchor" href="#gateway-feature-support">Gateway feature support</a></div>
 
  <div class="rp-h2" id="address-verification-service-avs"><a class="rp-anchor" href="#address-verification-service-avs">Address Verification Service (AVS)</a></div>
  <p style="font-size:14px; color:var(--darkgray); line-height:1.7; margin-bottom:16px;">AVS checks whether the billing address provided at checkout matches what the card issuer has on file. When enabled, mismatched addresses cause Recurly to reject the transaction before it's sent to the processor.</p>
  <div class="rp-callout rp-callout-warning">
    <div><strong>International customers</strong> AVS can't match postal codes that contain letters — a common format outside the US. To avoid rejecting valid international cards, configure your AVS rules to allow a transaction if either the street address or postal code matches accurately.</div>
  </div>
 
  <div class="rp-h2" id="card-code-verification-cvv"><a class="rp-anchor" href="#card-code-verification-cvv">Card Code Verification (CVV)</a></div>
  <p style="font-size:14px; color:var(--darkgray); line-height:1.7; margin-bottom:16px;">Recurly submits the CVV alongside the card number on new subscriptions and card number updates. Including the CVV on the first transaction improves approval rates and reduces fraud risk. After a successful first transaction, issuers typically allow subsequent charges from the same merchant to process without re-verification.</p>
  <div class="rp-callout rp-callout-note">
    <div><strong>PCI compliance</strong> Storing CVV values is prohibited under PCI regulations, regardless of encryption. Recurly submits the CVV only once — on the initial request — and never stores it.</div>
  </div>
 
</div>
`}</HTMLBlock>
