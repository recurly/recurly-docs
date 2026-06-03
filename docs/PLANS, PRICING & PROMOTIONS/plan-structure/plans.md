---
title: Plans
excerpt: >-
  How to create, configure, update, duplicate, and delete subscription plans in
  Recurly — including billing cycles, pricing models, price segments, and
  add-ons.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  image: https://files.readme.io/934dddc-Screenshot_2.png
  robots: index
next:
  description: ''
---
<span id="rp-close"></span>

<div class="rp-page">
  <div class="rp-overview">
    Plans are the blueprint for your subscription business — they define what your customers subscribe to, how often they're billed, and how much they pay. Whether your model includes free trials, setup fees, ramp pricing, or price segments, Recurly's plans are built to match your business exactly. There's no limit to the number of plans you can create.
  </div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-card">
    <h3>Plans dashboard</h3>
    <p>Your <a href="https://app.recurly.com/go/plans" target="_blank">plans dashboard</a> lists all plans defined in your Recurly account. Select any plan name to view its details, edit it, or link to its <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration or <a href="/docs/hosted" target="_blank">Hosted Payment Page</a>.</p>
  </div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#create-a-plan"><span class="rp-toc-num">3</span>Create a plan</a>
    <a class="rp-toc-pill" href="#edit-a-plan"><span class="rp-toc-num">4</span>Edit a plan</a>
    <a class="rp-toc-pill" href="#duplicate-a-plan"><span class="rp-toc-num">5</span>Duplicate a plan</a>
    <a class="rp-toc-pill" href="#delete-a-plan"><span class="rp-toc-num">6</span>Delete a plan</a>
  </div>
</div>

# Definition

<div class="rp-definition">
  A Recurly plan defines the billing frequency and base price for a subscription product. Plans support free trials, setup fees, multiple pricing models, and add-ons — giving you the flexibility to model any subscription business without limits on how many plans you create.
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexible plan configuration</strong>
    <span>Set billing cycles, trial periods, setup fees, renewal behavior, and pricing models — all in one place, tailored to how your business actually works.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tags" aria-hidden="true"></i></div>
    <strong>Multiple pricing models</strong>
    <span>Choose from fixed, ramp, or usage-based pricing to match your revenue strategy, with price segments for A/B testing and market-specific pricing without plan sprawl.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-plus" aria-hidden="true"></i></div>
    <strong>Built-in upsell with add-ons</strong>
    <span>Attach optional products and services to any plan to increase customer value and drive incremental revenue without creating separate plans.</span>
  </div>
</div>

# Create a plan

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the new plan form</h4><p>Navigate to <strong>Configuration → Plans</strong> and select <strong>New Plan</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-bc0ddaa4c88b375933ababdc2e75f4af992b177c">
    <img class="rp-zoom-img"
         src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png"
         alt="New Plan button on the plans list page" />
  </a>
  <a id="zoom-bc0ddaa4c88b375933ababdc2e75f4af992b177c" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Define plan parameters</h4><p>Work through each configuration group in order — plan details first, then billing, pricing, and the optional extras.</p></div>
  </div>
</div>

## Plan details

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-085cd9d0ffd02a7545515452a48328200dfbedb1">
    <img class="rp-zoom-img"
         src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png"
         alt="Plan details form fields" />
  </a>
  <a id="zoom-085cd9d0ffd02a7545515452a48328200dfbedb1" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Plan name</strong></td><td>Describes your plan. Appears on the Hosted Payment Page and the subscriber's invoice. Limit: 255 characters. Check with your payment gateway before using special characters.</td></tr>
  <tr><td><strong>Plan code</strong></td><td>Your plan's unique identifier in Recurly. Used in Hosted Payment Page URLs and API requests. Limit: 25 alphanumeric characters.</td></tr>
  <tr><td><strong>Plan description</strong></td><td>Describes what the plan includes. Appears on the subscriber's email invoice if configured in your email templates.</td></tr>
</table>

## Plan configuration

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-1e6fd5ac40d29b88bed2635fcbed5ad786025c3d">
    <img class="rp-zoom-img"
         src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png"
         alt="Currency picker in plan configuration" />
  </a>
  <a id="zoom-1e6fd5ac40d29b88bed2635fcbed5ad786025c3d" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" alt="" />
  </a>
</span>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-33e11f60b02b189a65fe8e52c1c763b8bc1d0ae2">
    <img class="rp-zoom-img"
         src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png"
         alt="Free trial configuration options" />
  </a>
  <a id="zoom-33e11f60b02b189a65fe8e52c1c763b8bc1d0ae2" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" alt="" />
  </a>
</span>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-6cd83f00615d5d2814588ceb461b5f2b7e82903e">
    <img class="rp-zoom-img"
         src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png"
         alt="Setup fee configuration" />
  </a>
  <a id="zoom-6cd83f00615d5d2814588ceb461b5f2b7e82903e" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Currencies</strong></td><td>Choose which of your enabled currencies to include in this plan.</td></tr>
  <tr><td><strong>Free trial</strong></td><td>Define a free period in days or months. The paid subscription starts after the trial ends. Choose whether to require billing information at sign-up.</td></tr>
  <tr><td><strong>Setup fee</strong></td><td>A one-time charge processed at sign-up.</td></tr>
</table>

## Billing configuration

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-efa80b5db6b52990a9d51eb53785e7e6118dba20">
    <img class="rp-zoom-img"
         src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png"
         alt="Billing configuration section" />
  </a>
  <a id="zoom-efa80b5db6b52990a9d51eb53785e7e6118dba20" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Billing period</strong></td><td>How often a subscriber is billed.</td></tr>
  <tr><td><strong>Subscription term length</strong></td><td>The default length of time customers are committed to the subscription. Subscriptions always renew with this term unless modified at the individual account level.</td></tr>
  <tr><td><strong>Billing cycles</strong></td><td>Choose to automatically renew or expire the subscription after a set number of billing periods, configured in the "At end of subscription term" section.</td></tr>
</table>

## Pricing model

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-acf01be91a70711bb406a12ae7e6c942b6c1e50f">
    <img class="rp-zoom-img"
         src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png"
         alt="Pricing model selector" />
  </a>
  <a id="zoom-acf01be91a70711bb406a12ae7e6c942b6c1e50f" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Pricing model</strong></td><td>Choose fixed or ramp pricing to match your subscription model.</td></tr>
  <tr><td><strong>Price</strong></td><td>Set the fixed price charged to plan subscribers. For quantity-based pricing, use add-ons.</td></tr>
</table>

## Price segments

Price segments let you define multiple price points for a single plan within the same currency — useful for A/B testing or market-specific pricing without creating duplicate plans. A default price is always required and applies whenever no segment code is provided.

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-33c2e19de5efdd80e17eec6a136477329165f932">
    <img class="rp-zoom-img"
         src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png"
         alt="Price segments configuration" />
  </a>
  <a id="zoom-33c2e19de5efdd80e17eec6a136477329165f932" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" alt="" />
  </a>
</span>

**Example:** You run a gym where operating costs vary by city. Rather than cloning identical plans, create one plan with segments — `default`, `nyc`, `la` — and apply the right price at checkout based on the customer's location.

### How price segments work

- Recurly stores all segment prices and the default price on the plan.
- You decide which price to apply (by geography, campaign, experiment bucket, etc.) — Recurly doesn't choose the segment for you.
- Segment data (code and price) is returned via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#tag/price_segment" target="_blank">v3 API</a> and <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/" target="_blank">Recurly.js</a> so your checkout can display the intended price.

### Implement price segments

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add segments to the plan</h4><p>In the plan's Pricing section, create one or more segments and set a default price.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Define your selection rule</h4><p>For example: if <code>city=NYC</code> use segment <code>nyc</code>; if the user is in test group B, use segment <code>exp-b</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Surface the right price in your UI</h4><p>Fetch the plan's price segments via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_plan" target="_blank">API</a> or <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/" target="_blank">Recurly.js</a> and render the price that matches your rule.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Apply the segment at checkout</h4><p>When creating the purchase or subscription, pass the chosen segment's price. If no segment code is provided, the default price is used.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> For A/B tests, name segments clearly — for example, <code>exp-a</code> and <code>exp-b</code> — and log the chosen segment code with your analytics events.</div>
</div>

### Notes and limits

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Detail</td><td>Value</td></tr>
  <tr><td><strong>Number of segments</strong></td><td>No limit per currency</td></tr>
  <tr><td><strong>Availability</strong></td><td>Plans only (fixed and ramp pricing). Not available on setup fees, add-ons, items, or Recurly Checkout.</td></tr>
  <tr><td><strong>Adding segments</strong></td><td>You can add segments to existing plans at any time.</td></tr>
  <tr><td><strong>Editing segments</strong></td><td>After creation, only the price within a segment can be edited — the segment code is fixed.</td></tr>
  <tr><td><strong>Invoice visibility</strong></td><td>Segment codes don't appear on invoices or in email templates — they're for your internal selection logic only.</td></tr>
</table>

### Developer references

- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_price_segments" target="_blank">/price\_segment</a>
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_plans" target="_blank">/plans</a>
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription" target="_blank">/subscriptions</a>
- <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change" target="_blank">/create\_subscription\_change</a>
- <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/" target="_blank">Recurly.js — surface price segments in your front end</a>

## Billing details

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-74aa52e78f94702312f92e6fcafbbb00e8e7528e">
    <img class="rp-zoom-img"
         src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png"
         alt="Billing details fields" />
  </a>
  <a id="zoom-74aa52e78f94702312f92e6fcafbbb00e8e7528e" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Accounting code</strong></td><td>A unique code to identify this plan in your internal invoice exports. Configure based on your tax settings and compliance requirements. Limit: 25 lowercase alphanumeric characters.</td></tr>
  <tr><td><strong>HS code / Commodity code</strong></td><td>An HS or Commodity code for invoice compliance on traded products. HS codes are at least six digits, with countries adding digits for regional classification. Limit: 25 lowercase alphanumeric characters.</td></tr>
</table>

## Plan add-ons

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-ace61210674443e1e3313351841cff1758a81a7d">
    <img class="rp-zoom-img"
         src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png"
         alt="Plan add-ons section" />
  </a>
  <a id="zoom-ace61210674443e1e3313351841cff1758a81a7d" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" alt="" />
  </a>
</span>

Optional products that can be included in a recurring subscription's invoices. Add-ons also support quantity-based pricing models. You can add items directly from your item catalog to a plan.

## Dunning campaign

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-2016200d6fed0e474767bb6da138c4ad3f2091dd">
    <img class="rp-zoom-img"
         src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png"
         alt="Dunning campaign selector" />
  </a>
  <a id="zoom-2016200d6fed0e474767bb6da138c4ad3f2091dd" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" alt="" />
  </a>
</span>

Select the dunning campaign to apply to this plan.

## Customer emails

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-36c3e1eec931e2d3b84a0a1ca45bba5cb9601a35">
    <img class="rp-zoom-img"
         src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png"
         alt="Customer emails configuration" />
  </a>
  <a id="zoom-36c3e1eec931e2d3b84a0a1ca45bba5cb9601a35" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" alt="" />
  </a>
</span>

Check the boxes to enable email communication for specific billing events. You can modify and manage your templates on the Email Templates settings page.

## Hosted Payment Pages

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-13991f75755f5e278537208a94c860cdb87a6801">
    <img class="rp-zoom-img"
         src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png"
         alt="Hosted Payment Pages settings" />
  </a>
  <a id="zoom-13991f75755f5e278537208a94c860cdb87a6801" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" alt="" />
  </a>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Plan quantity can be edited</strong></td><td>Determines whether subscribers can choose their own quantity on the Hosted Payment Page.</td></tr>
  <tr><td><strong>Return URL after success</strong></td><td>Redirects the customer to a specific URL after a successful transaction via the Hosted Page.</td></tr>
  <tr><td><strong>Bypass Recurly confirmation</strong></td><td>Skip Recurly's confirmation page and send the customer directly to your custom return URL.</td></tr>
</table>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Create the plan</h4><p>Once all parameters are configured, select <strong>Create Plan</strong> to finalize.</p></div>
  </div>
</div>

<div class="rp-card">
  <h3>Checkout configuration</h3>
  <p>After creating a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration to direct customers to purchase it.</p>
  <div class="rp-zoom-small">
    <span class="rp-zoom">
      <a class="rp-zoom-label" href="#zoom-5812722bde5118573fa786b4a575e1b615b86880">
        <img class="rp-zoom-img"
             src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png"
             alt="Checkout configuration button" />
      </a>
      <a id="zoom-5812722bde5118573fa786b4a575e1b615b86880" class="rp-zoom-overlay" href="#rp-close">
        <img src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" alt="" />
      </a>
    </span>
  </div>
</div>

# Edit a plan

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select Edit</h4><p>Hover over the plan row in the list view, or use the plan actions menu on the plan details page, and select <strong>Edit</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-be953bbb65864484f35eb5cb51428ed06b2c966e">
    <img class="rp-zoom-img"
         src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png"
         alt="Plan row hover actions showing Edit, Duplicate, and Delete options" />
  </a>
  <a id="zoom-be953bbb65864484f35eb5cb51428ed06b2c966e" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Make your changes and select <strong>Save Changes</strong>.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Plan name changes apply to existing subscriptions</strong> Updating a plan's name updates it site-wide. Existing subscriptions will show the new name in the Admin UI, and future invoice line items will use the updated name.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Versioned plan terms — such as price, billing interval, and setup fees — apply to new subscribers only. Existing subscribers keep the terms that were in effect when they signed up.</div>
</div>

# Duplicate a plan

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select Duplicate</h4><p>Hover over the plan row to reveal the action options, then select <strong>Duplicate</strong>. All details from the original plan are copied to the Create a Plan form, with <strong>-copy</strong> appended to the plan name and plan code.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-3b6b286cc277c222905012f1fcd013f9235bdcb5">
    <img class="rp-zoom-img"
         src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png"
         alt="Duplicate plan form with -copy appended to name and code fields" />
  </a>
  <a id="zoom-3b6b286cc277c222905012f1fcd013f9235bdcb5" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Adjust the details</h4><p>Update the plan name, plan code, and any other fields as needed for the new plan.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Create the plan</h4><p>Select <strong>Create Plan</strong> once you've finished adjusting the details.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> You can also duplicate a plan immediately after creating it — the success confirmation includes a duplicate option.</div>
</div>

# Delete a plan

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select Delete</h4><p>Hover over the plan row in the list view, or use the plan actions dropdown on the plan details page, and select <strong>Delete</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Confirm deletion</h4><p>Confirm your decision in the dialog.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#zoom-ced811d9006f4cb407e9866bc6bbb04513fa104e">
    <img class="rp-zoom-img"
         src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png"
         alt="Delete plan confirmation dialog" />
  </a>
  <a id="zoom-ced811d9006f4cb407e9866bc6bbb04513fa104e" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" alt="" />
  </a>
</span>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong> Deleting a plan is permanent and prevents new customers from subscribing to it. Existing subscriptions continue to renew, but once deleted, a plan can't be reactivated. Subscriptions tied to a deleted plan cannot be edited — including frequency, price, and add-ons.</div>
</div>

<br />