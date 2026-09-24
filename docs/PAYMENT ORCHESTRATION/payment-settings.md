---
title: Payment settings
excerpt: >-
  Configure Account Updater, CVV and AVS verification rules, Direct Debit
  Retries, and duplicate billing information prevention from Recurly's Payment
  Settings page.
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
<div class="rp-overview">Payment settings gives you fine-grained control over how Recurly handles card verification and billing data quality. From one page you can enroll in Account Updater to keep expiring cards current, enforce CVV and AVS rejection rules to block potentially fraudulent initial transactions, and prevent duplicate billing information from being saved to your account.</div>
<div class="rp-cost"><strong>Additional cost — Account Updater</strong><br/>Account Updater requires an additional cost. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your Recurly account manager for pricing details.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
<a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">4</span>FAQs</a>
</div>
</div>

### Prerequisites

**AVS and CVV rejection rules**

<ul class="rp-list">
<li>A gateway that supports returning AVS and CVV results on initial transactions</li>
</ul>

**Account Updater**

<ul class="rp-list">
<li>A gateway that supports credit card payments</li>
<li>An active Recurly subscription</li>
</ul>

### Limitations

**AVS and CVV rejection rules**

<ul class="rp-list">
<li>Gateways that do not return AVS or CVV results will not work with this feature</li>
<li>Only certain gateways are supported: Adyen, Authorize.net, Chase Orbital, PayPal Complete, Stripe, and TSYS. Cybersource's AVS rules are located on the gateway configuration page.</li>
<li>Applicable to credit card payments only</li>
</ul>

**Account Updater**

<ul class="rp-list">
<li>Applicable to credit card payments only</li>
<li>OptBlue Amex MIDs are not supported</li>
<li>Merchants outside the US using Amex will not be able to use Card Refresher</li>
</ul>

**Mandate Revocation Settings**

<ul class="rp-list">
<li>Applicable to mandated-payment methods only</li>
<li>Gateways supported: Ebanx, Stripe, PayPal Complete</li>
</ul>

# Definition

<div class="rp-definition">Payment settings is your central hub for configuring how Recurly handles card verification and billing data integrity. It brings together Account Updater — which keeps subscription billing data current as cards expire or change — and AVS/CVV rejection rules, which let you automatically void approved transactions where the cardholder's address or security code doesn't match what the issuing bank has on file.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
<strong>Keep recurring billing uninterrupted</strong>
<span>Account Updater automatically refreshes expiring or changed card details so long-running subscriptions don't fail due to stale billing information.</span>
</div>
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
<strong>Block fraudulent sign-ups at the start</strong>
<span>CVV and AVS rejection rules let you void approved transactions where the card code, street address, or postal code doesn't match the issuer's records — stopping fraud at the moment of first contact.</span>
</div>
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
<strong>Maintain clean billing data</strong>
<span>The duplicate billing information prevention setting keeps your account wallet free of redundant card entries, reducing confusion and improving payment reliability.</span>
</div>
</div>

# Key details

## Industry examples — AVS and CVV rules

To illustrate how AVS, CVV, and Account Updater work in practice:

<table class="rp-gw-table">
<tr class="rp-thead-row"><td>Industry</td><td>Best practices</td></tr>
<tr><td>Streaming media, eLearning, and digital publishing</td><td><strong>Account Updater:</strong> For recurring transactions, cardholder data can become stale for long-running accounts. Account Updater refreshes billing information to ensure subscriptions continue running over time.<br/><br/><strong>AVS and CVV rules:</strong> For initial sign-ups, reject fraudulent transactions where the billing address or CVV provided doesn't match the issuer's data.</td></tr>
</table>

## Enabling Account Updater

To learn more about Account Updater, see the dedicated <a href="https://docs.recurly.com/docs/account-updater" target="_blank">Account Updater</a> page.

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Confirm your plan eligibility</h4><p>If you haven't yet signed up for a Recurly subscription, you'll see a message indicating Account Updater isn't available.</p></div>
</div>
</div>


<Image src="https://files.readme.io/f4acf3a-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Click Enable</h4><p>Once you have an active Recurly subscription and a credit card–supported gateway enabled, an Enable button appears to begin the enrollment process.</p></div>
</div>
</div>


<Image src="https://files.readme.io/e84bb21-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Provide card brand information</h4><p>A modal appears where you can supply additional details required for certain card brands.</p></div>
</div>
</div>

- **Mastercard** — Account Updater requires your Merchant Category Code (MCC) to enroll. Your MCC is a four-digit code that describes your business type (for example, 5942 for Book Stores).
- **American Express** — If you have a direct Amex account and want to enable Account Updater for Amex cards, provide your SE (Service Establishment) Number. OptBlue accounts are not supported.

If you choose not to enter this information, only Visa and Discover will be enrolled.


<Image src="https://files.readme.io/0ed852b-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">4</div>
<div><h4>Confirm and activate</h4><p>Check the box to acknowledge the additional charges associated with Account Updater, then click Enable. Account Updater will be active immediately, and cards expiring soon will be submitted for updates.</p></div>
</div>
</div>


<Image src="https://files.readme.io/0f44fa3-image.png" align="center" width="75%" border={true} />


## Enabling CVV checks

When Recurly sends a CVV to the cardholder's bank, the bank responds with a match or mismatch based on what it has on file. Enabling CVV checks causes Recurly to void approved transactions where the CVV doesn't match.

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Go to Configuration → Payment Settings</h4><p>Navigate to Configuration, then select Payment Settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Verify your gateway</h4><p>Confirm your gateway appears in the supported list and is active in your gateway settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Toggle CVV checks to Enabled</h4><p>Switch the CVV checks setting to Enabled.</p></div>
</div>
</div>


<Image src="https://files.readme.io/c8ea553-image.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>CVV checks are enabled by default on most accounts. Any approved transaction that receives a mismatched CVV will be voided when this setting is on.</div>
</div>

## Enabling AVS checks

When Recurly sends a billing address (street number and postal code) to the cardholder's bank, the bank responds with a full match, partial match, or full mismatch. Enabling AVS checks causes Recurly to void approved transactions that receive a full mismatch response.

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Go to Configuration → Payment Settings</h4><p>Navigate to Configuration, then select Payment Settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Verify your gateway</h4><p>Confirm your gateway appears in the supported list and is active in your gateway settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Toggle AVS checks to Enabled</h4><p>Switch the AVS checks setting to Enabled.</p></div>
</div>
</div>


<Image src="https://files.readme.io/4d6fe1c5919f5fcde2426a87dc4bf43f0a7e16c22d96803d27a021bc5f8b4967-image.png" align="center" width="75%" border={true} />


## Duplicate billing information prevention

When the <a href="https://docs.recurly.com/recurly-subscriptions/docs/wallet" target="_blank">Wallet</a> feature is enabled, an additional payment setting becomes available to prevent duplicate billing information from being saved to your account. This control applies to credit cards (with PANs) and RJS tokens.

By default, the setting is configured to allow duplicates. When set to block duplicates, any attempt to save a duplicate entry returns an error — both in the Recurly UI and via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_billing_infos" target="_blank">billing infos API</a>.


<Image src="https://files.readme.io/d5fb633232ff5ac8ccc03566f54a76df4e1caa9caab01a8c96d5e7c1862da351-Screenshot_2026-04-15_at_12.42.35_PM.png" align="center" width="75%" border={true} />


## Direct Debit Retry Enablement&#x20;

When you have a supported gateway and payment method enabled, we will retry certain Direct Debit failures within compliant limitations. Retries for Direct Debit are only actionable on insufficient funds responses, and various regulatory bodies restrict retries to only 2 attempts after the initial decline.

You can read more on our dedicated documentation for <Anchor target="_blank" href="https://docs.recurly.com/recurly-subscriptions/docs/sepa-retries">Direct Debit retries</Anchor>.

Direct Debit payment methods include:&#x20;

- ACH&#x20;
- SEPA
- BACS
- BECS

## Enabling Mandate Settings

There are two features to Mandate settings:&#x20;

**Mandate Buffer:** Certain APMs require an 'upper limit' for the mandate to allow for price changes, and Recurly's default is 18% calculated off the plan amount itself. You may use this setting to customize the percentage of the buffer based on your business's specific requirements.&#x20;

Keep in mind, the upper limit of a mandate is **visible&#x20;**&#x74;o your consumer in their banking apps, and as such it is not recommended to make the buffer percentage too high as this can cause cart abandonment. No higher than 30% is recommended.

It is also not recommended to go _lower_ than 15%, as this gives you very little wiggle room if you want to make minor price changes. For example, a buffer of 15% on a $10.00 plan only nets you a 11.50 mandate upper limit, only allowing you to modify your prices a teeny bit.

- **Supported Gateways:&#x20;**&#x45;banx, Stripe (India e-mandates)

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Go to Configuration → Payment Settings</h4><p>Navigate to Configuration, then select Payment Settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Verify your gateway</h4><p>Confirm your gateway appears in the supported list and is active in your gateway settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Choose the Default or a Custom Percentage</h4><p>The default will be the 18% buffer, but you may choose to change to a custom value. Simply select 'Set a custom percentage', and enter the value you want to use.</p></div>
</div>
</div>

![](https://files.readme.io/145e72fcebdd3ffef7285263be977550ee0a759886dd5d10d757d5fecc9e6ae2-Screenshot_2026-09-24_at_4.52.28_PM.png)

<br />

**Mandate Revocation handling**: When Recurly has a mandate on file, that mandate also exists at a bank-level, and for certain APMs, customers can revoke their mandates through a banking app. Supported methods include: UPI AutoPay, Cards in India using e-mandates (Stripe only), Pix Automatico, Mercado Pago.

* **Supported Gateways:&#x20;**&#x45;banx, Stripe (India e-mandates)

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Go to Configuration → Payment Settings</h4><p>Navigate to Configuration, then select Payment Settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Verify your gateway</h4><p>Confirm your gateway appears in the supported list and is active in your gateway settings.</p></div>
</div>
</div>

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Choose Automated Subscription handling or Manual handling</h4><p>The default will be automatic management, and you are given a choice to auto-cancel or auto-expire subscriptions if a customer cancels their mandate externally. If you are listening to the <code>mandate.inactive</code> subscription webhook, you may choose to change to manual handling. With manual management, Recurly will not cancel or expire subscriptions upon mandate revocation, and you must take action on your own by calling our APIs to change subscription states to cancelled or expired.</p></div>
</div>
</div>


<Image src="https://files.readme.io/b9b6655bc7dfc4fc8b291a67aad124a6d8dd0b1828a6dc0a0b8f0f73a440f2e1-Screenshot_2026-09-24_at_4.42.04_PM.png" align="center" width="75%" border={true} />


# FAQs

<Accordion title="What if my customer doesn't provide an address on the initial transaction?">
  Your gateway will still generate an AVS response code — and without address data, the result will likely be a rejection. To avoid a spike in declines when AVS checks are enabled, make sure your checkout flow captures billing information for all transactions.
</Accordion>

<Accordion title="Does Account Updater work on bank account details?">
  No. Account Updater is exclusively for credit card payment methods and is not needed if you don't accept credit cards.
</Accordion>

<Accordion title="Will CVV be checked on recurring transactions?">
  No. Recurly doesn't store CVV codes in order to comply with PCI standards, so the CVV is never included in recurring transactions. Both AVS and CVV rules apply only to initial transactions — for example, a customer's first sign-up.
</Accordion>

<Accordion title="If I set my mandate buffer to 0%, can I raise my prices later?">
  No. External mandates with specific APMs will decline transaction requests if they exceed the mandate upper limit applied at the start of the subscription. If you have set your mandate buffer to 0%, which is not recommended, the subscription needs to be cancelled and the customer brought back into session to sign up again.
</Accordion>

<Accordion title="My customer revoked their mandate on a subscription and the subscription is now cancelled. Can I reactivate it?">
  No. External mandates that have been revoked will remain in that state. Customers will need to come back into session to sign up for a subscription again, as the mandate is no longer valid with the bank and transaction attempts against it will fail.
</Accordion>
