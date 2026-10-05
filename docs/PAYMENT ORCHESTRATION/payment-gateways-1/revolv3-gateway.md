---
title: Revolv3
excerpt: >-
  Configure Revolv3 as a payment gateway in Recurly to accept Credit Cards
  across global markets.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-callout rp-callout-tip">
    <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Early access</strong> Revolv3 is currently available in early access. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> to request access.</div>
  </div>

  <div class="rp-overview">

Revolv3 is a global payment gateway that plugs into Recurly to handle recurring subscriptions, one-time payments, and 3D Secure authentication — across virtually any currency or region. Whether you're onboarding fresh or migrating from another gateway, setup follows a straightforward process.

  </div>

  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#set-up-revolv3-with-recurly"><span class="rp-toc-num">3</span>Setup</a>
    <a class="rp-toc-pill" href="#additional-configuration"><span class="rp-toc-num">4</span>Additional configuration</a>
    <a class="rp-toc-pill" href="#production-and-sandbox-behavior"><span class="rp-toc-num">5</span>Production and sandbox behavior</a>
  </div>

</div>

# Definition

<div class="rp-definition">

Revolv3 is a global payment gateway that integrates with Recurly to manage financial transactions for recurring subscriptions and one-time payments. It supports a wide range of card brands and currencies worldwide, and employs best-in-class orchestration behind-the-scenes to improve auth rates.

</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Best practices before you start</strong>
  <ul>
    <li>Using 3DS requires <strong>Recurly.js</strong> to collect browser and device data, and deliver the customer challenge.</li>
    <li>Ensure your Business Entity's Merchant Category Code (MCC) is filled in correctly before enabling 3DS.</li>
    <li>The CVV is required for all CIT card payments, including MOTO. Ensure you are capturing the CVV for return customer transactions including signups, and one-time transactions. Recurly will never store the CVV code on your behalf.</li>
  </ul></div>
</div>

# Key details

<table class="rp-gw-table">
  <tr class="rp-thead-row">
    <td>Feature</td>
    <td>Details</td>
  </tr>
  <tr>
    <td>Services that work with Recurly</td>
    <td>Recurring subscriptions, payments (ecommerce and <a href="https://docs.recurly.com/recurly-subscriptions/docs/moto-transactions#/" target="_blank">MOTO</a>), 3D Secure</td>
  </tr>
  <tr>
    <td>Supported operations</td>
    <td>Authorize and Capture, Purchase, Refund, Verify, Void, Recurring, Unscheduled MIT</td>
  </tr>
  <tr>
    <td>Supported payment types</td>
    <td>Credit card</td>
  </tr>
  <tr>
    <td>Supported card brands</td>
    <td>Visa, Mastercard, Amex, Discover, JCB, Diners Club, Union Pay</td>
  </tr>
  <tr>
    <td>Unified 3DS2 supported</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Card on file supported</td>
    <td>Yes</td>
  </tr>
  <tr>
    <td>Regions</td>
    <td>Worldwide</td>
  </tr>
  <tr>
    <td>Currencies</td>
    <td>All supported currencies</td>
  </tr>
  <tr>
    <td>Additional feature support</td>
    <td>Billing and shipping information, Level 2 data, Dynamic Descriptors, AVS/CVV checks, and line item passthrough</td>
  </tr>
</table>

# Set up Revolv3 with Recurly

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Pricing and account setup</strong> For pricing and signup information for a new production Revolv3 account, contact your Revolv3 account representative directly.</div>
</div>

## Step 1 — Obtain your Revolv3 credentials

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Retrieve your credentials from Revolv3</h4><p>Log in to your Revolv3 dashboard, go to <strong>Settings → Integration Profile</strong>, and open <strong>Developer Static Tokens</strong>.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i>Create your Token</strong>There are few steps easier than this -- simply create a static token and keep it somewhere safe for onboarding to Recurly.</div>
</div>

For additional guidance, see Revolv3's direct documentation: <a href="https://docs.revolv3.com/docs/getting-started/getting-started#step-1-obtain-a-sandbox-token" target="_blank">Access and/or create Static Tokens</a>.

**If you plan to enable 3DS**, you'll also need the following from Revolv3 before proceeding:

- Your Acquirer BIN (6 digits)
- Your Acquirer Merchant ID
- Your Acquirer Country

These are used in [Step 4](#step-4-enable-3d-secure). Gather them now so you have them ready.

## Step 2 — Enter your credentials in Recurly

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the payment gateway settings</h4><p>In Recurly, go to <strong>Configuration → Payment Gateways</strong> and select <strong>Revolv3</strong> from the available options.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your Revolv3 credentials</h4><p>Fill in the required fields using the values you collected in Steps 1 and 2.</p></div>
  </div>
</div>

| Field         | Where to find it                                                  |
| ------------- | ----------------------------------------------------------------- |
| Developer Key | Revolv3 dashboard → Integration Profile → Developer Static Tokens |
| Static Token  | Revolv3 dashboard → Integration Profile → Developer Static Tokens |
| 3DS Details   | Your Revolv3 account manager                                      |

## Step 3 — Enable 3D Secure

Skip this step if you're not using 3DS.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Required before enabling 3DS</strong> Your default Business Entity must have both the consumer-facing website domain (URL) and your business's MCC value populated before you enable 3DS.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Enable 3D Secure</h4><p>In the Revolv3 gateway configuration screen in Recurly, select <strong>Enable 3D Secure</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your 3DS credentials</h4><p>Fill in your <strong>Acquirer BIN</strong>, <strong>Acquirer Merchant ID (CAID)</strong>, and <strong>Acquirer Country</strong> — all obtained from Revolv3 directly.</p></div>
  </div>
</div>

## Step 5 — Enable currencies

Select the currencies your Revolv3 gateway should accept. You can add or change currencies at any time — choose only from those you're approved to process.


<Image src="https://files.readme.io/c4a227a-image.png" align="center" width="75%" border={true} />


## Step 6 — Save your gateway configuration

Once you've configured everything, select **Add Payment Gateway**. If you're updating an existing configuration, the button reads **Update Payment Gateway** instead.

# Additional configuration

## Address and card code verification

You can configure Recurly to automatically reject transactions where the billing address or CVV doesn't match what the card issuer has on file. These settings apply across all gateways — they're not Revolv3-specific.

**Enable Address Verification (AVS)**

1. Go to **Configuration → Payment Settings**.
2. Scroll to the **Address Verification Check** section.
3. Select your preferred AVS rule.
4. Select **Save Changes**.

**Enable Card Code Verification (CVV)**

1. Go to **Configuration → Payment Settings**.
2. Scroll to the **Credit Card Verification Code Check** section.
3. Set the option to **Enabled**. When enabled, transactions with an invalid or mismatched CVV are rejected based on issuer feedback.
4. Select **Save Changes**.


<Image src="https://files.readme.io/9306094-image.png" align="center" width="75%" border={true} />


## Test your integration

1. Go to **Configuration → Payment Gateways**.
2. Find your Revolv3 configuration and select **Options → Test Configuration**.

If your credentials are correct, Recurly will confirm a successful connection.

## Go live

Once testing passes, your gateway is ready for real transactions. Monitor activity in both Recurly and your Revolv3 dashboard to confirm everything is processing as expected.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> PCI compliance</strong> Ensure you comply with PCI Data Security Standards (PCI DSS) when handling card data. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your Revolv3 representative with any compliance questions.</div>
</div>

# Production and sandbox behavior

Production and sandbox environments in Revolv3 are entirely separate systems with distinct endpoints. Keep the following in mind when managing your environments:

- If you create a Revolv3 gateway configuration while your Recurly site is in either Production or Sandbox mode, you can control which Revolv3 endpoint — production or sandbox — your transactions hit.
- **If you ever change your Recurly site's mode** (for example, from Sandbox to Production), your existing gateway tiles will stop working. You must create new gateway configurations for the new mode and disable the old ones.
- **Best practice:** Keep your site in a consistent mode and use a dedicated development site for integration testing. Set that site to Development mode before adding gateway accounts, and keep it there for the duration of your testing.
- When testing Revolv3, it is best to use their test cards for streamlined development and testing. You can find their test cards and sandbox limitations at the below two pages. Please note, Recurly does not control Revolv3 test card behavior or sandbox limitations.&#x20;
  - [Revolv3 Test cards](https://docs.revolv3.com/docs/testing-sandbox/test-cards-for-sandbox)
  - [Revolv3 Sandbox limitations](https://docs.revolv3.com/docs/testing-sandbox/sandbox-environment-limitations)

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Going live from a copied configuration</strong> When going live, you cannot simply copy your sandbox gateway configuration. The copied gateway does not carry the correct site identifiers for the production environment — you must re-onboard Revolv3 from scratch in your production site.</div>
</div>
