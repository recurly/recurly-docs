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
<div class="rp-page">
  <div class="rp-overview">
    Plans are the blueprint for your subscription business — they define what your customers subscribe to, how often they're billed, and how much they pay. Whether your model includes free trials, setup fees, ramp pricing, or price segments, Recurly's plans are built to match your business exactly. There's no limit to the number of plans you can create.
  </div>

  <div class="rp-plan"><i class="fa fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

  <div class="rp-card">

    ### Plans dashboard

```
Your <a href="https://app.recurly.com/go/plans" target="_blank">plans dashboard</a> lists all plans defined in your Recurly account. Select any plan name to view its details, edit it, or link to its <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration or <a href="/docs/hosted" target="_blank">Hosted Payment Page</a>.
```

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
    <div class="rp-benefit-icon"><i class="fa fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexible plan configuration</strong>
    <span>Set billing cycles, trial periods, setup fees, renewal behavior, and pricing models — all in one place, tailored to how your business actually works.</span>
  </div>

  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa fa-tags" aria-hidden="true"></i></div>
    <strong>Multiple pricing models</strong>
    <span>Choose from fixed, ramp, or usage-based pricing to match your revenue strategy, with price segments for A/B testing and market-specific pricing without plan sprawl.</span>
  </div>

  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa fa-plus-circle" aria-hidden="true"></i></div>
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
  <input type="checkbox" id="zoom-new-plan-button" class="rp-zoom-toggle" />

  <label for="zoom-new-plan-button">
    <img class="rp-zoom-img" src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="New Plan button on the plans list page" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-new-plan-button" class="rp-zoom-overlay">
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Define plan parameters</h4><p>Work through each configuration group in order — plan details first, then billing, pricing, and the optional extras.</p></div>
  </div>
</div>

## Plan details

<span class="rp-zoom">
  <input type="checkbox" id="zoom-plan-details" class="rp-zoom-toggle" />

  <label for="zoom-plan-details">
    <img class="rp-zoom-img" src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" alt="Plan details form fields" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-plan-details" class="rp-zoom-overlay">
    <img src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" alt="" />
  </label>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Plan name</strong></td><td>Describes your plan. Appears on the Hosted Payment Page and the subscriber's invoice. Limit: 255 characters. Check with your payment gateway before using special characters.</td></tr>
  <tr><td><strong>Plan code</strong></td><td>Your plan's unique identifier in Recurly. Used in Hosted Payment Page URLs and API requests. Limit: 25 alphanumeric characters.</td></tr>
  <tr><td><strong>Plan description</strong></td><td>Describes what the plan includes. Appears on the subscriber's email invoice if configured in your email templates.</td></tr>
</table>

## Plan configuration

<span class="rp-zoom">
  <input type="checkbox" id="zoom-currency-picker" class="rp-zoom-toggle" />

  <label for="zoom-currency-picker">
    <img class="rp-zoom-img" src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" alt="Currency picker in plan configuration" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-currency-picker" class="rp-zoom-overlay">
    <img src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" alt="" />
  </label>
</span>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-free-trial" class="rp-zoom-toggle" />

  <label for="zoom-free-trial">
    <img class="rp-zoom-img" src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" alt="Free trial configuration options" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-free-trial" class="rp-zoom-overlay">
    <img src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" alt="" />
  </label>
</span>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-setup-fee" class="rp-zoom-toggle" />

  <label for="zoom-setup-fee">
    <img class="rp-zoom-img" src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" alt="Setup fee configuration" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-setup-fee" class="rp-zoom-overlay">
    <img src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" alt="" />
  </label>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Currencies</strong></td><td>Choose which of your enabled currencies to include in this plan.</td></tr>
  <tr><td><strong>Free trial</strong></td><td>Define a free period in days or months. The paid subscription starts after the trial ends. Choose whether to require billing information at sign-up.</td></tr>
  <tr><td><strong>Setup fee</strong></td><td>A one-time charge processed at sign-up.</td></tr>
</table>

## Billing configuration

<span class="rp-zoom">
  <input type="checkbox" id="zoom-billing-configuration" class="rp-zoom-toggle" />

  <label for="zoom-billing-configuration">
    <img class="rp-zoom-img" src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" alt="Billing configuration section" style={{display:"block", width:"90%", margin:"16px auto", borderRadius:"8px"}} />
  </label>

  <label for="zoom-billing-configuration" class="rp-zoom-overlay">
    <img src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" alt="" />
  </label>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Billing period</strong></td><td>How often a subscriber is billed.</td></tr>
  <tr><td><strong>Subscription term length</strong></td><td>The default length of time customers are committed to the subscription. Subscriptions always renew with this term unless modified at the individual account level.</td></tr>
  <tr><td><strong>Billing cycles</strong></td><td>Choose to automatically renew or expire the subscription after a set number of billing periods, configured in the "At end of subscription term" section.</td></tr>
</table>

## Pricing model

<span class="rp-zoom">
  <input type="checkbox" id="zoom-pricing-model" class="rp-zoom-toggle" />

  <label for="zoom-pricing-model">
    <img class="rp-zoom-img" src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" alt="Pricing model selector" style={{display:"block", width:"90%", margin:"16px auto", borderRadius:"8px"}} />
  </label>

  <label for="zoom-pricing-model" class="rp-zoom-overlay">
    <img src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" alt="" />
  </label>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Pricing model</strong></td><td>Choose fixed or ramp pricing to match your subscription model.</td></tr>
  <tr><td><strong>Price</strong></td><td>Set the fixed price charged to plan subscribers. For quantity-based pricing, use add-ons.</td></tr>
</table>

## Price segments

Price segments let you define multiple price points for a single plan within the same currency — useful for A/B testing or market-specific pricing without creating duplicate plans. A default price is always required and applies whenever no segment code is provided.

<span class="rp-zoom">
  <input type="checkbox" id="zoom-price-segments" class="rp-zoom-toggle" />

  <label for="zoom-price-segments">
    <img class="rp-zoom-img" src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" alt="Price segments configuration" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-price-segments" class="rp-zoom-overlay">
    <img src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" alt="" />
  </label>
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
  <div><strong><i class="fa fa-lightbulb" aria-hidden="true"></i> Tip</strong> For A/B tests, name segments clearly — for example, <code>exp-a</code> and <code>exp-b</code> — and log the chosen segment code with your analytics events.</div>
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
  <input type="checkbox" id="zoom-billing-details" class="rp-zoom-toggle" />

  <label for="zoom-billing-details">
    <img class="rp-zoom-img" src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" alt="Billing details fields" style={{display:"block", width:"90%", margin:"16px auto", borderRadius:"8px"}} />
  </label>

  <label for="zoom-billing-details" class="rp-zoom-overlay">
    <img src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" alt="" />
  </label>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Accounting code</strong></td><td>A unique code to identify this plan in your internal invoice exports. Configure based on your tax settings and compliance requirements. Limit: 25 lowercase alphanumeric characters.</td></tr>
  <tr><td><strong>HS code / Commodity code</strong></td><td>An HS or Commodity code for invoice compliance on traded products. HS codes are at least six digits, with countries adding digits for regional classification. Limit: 25 lowercase alphanumeric characters.</td></tr>
</table>

## Plan add-ons

<span class="rp-zoom">
  <input type="checkbox" id="zoom-plan-addons" class="rp-zoom-toggle" />

  <label for="zoom-plan-addons">
    <img class="rp-zoom-img" src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" alt="Plan add-ons section" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-plan-addons" class="rp-zoom-overlay">
    <img src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" alt="" />
  </label>
</span>

Optional products that can be included in a recurring subscription's invoices. Add-ons also support quantity-based pricing models. You can add items directly from your item catalog to a plan.

## Dunning campaign

<span class="rp-zoom">
  <input type="checkbox" id="zoom-dunning-campaign" class="rp-zoom-toggle" />

  <label for="zoom-dunning-campaign">
    <img class="rp-zoom-img" src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" alt="Dunning campaign selector" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-dunning-campaign" class="rp-zoom-overlay">
    <img src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" alt="" />
  </label>
</span>

Select the dunning campaign to apply to this plan.

## Customer emails

<span class="rp-zoom">
  <input type="checkbox" id="zoom-customer-emails" class="rp-zoom-toggle" />

  <label for="zoom-customer-emails">
    <img class="rp-zoom-img" src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" alt="Customer emails configuration" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-customer-emails" class="rp-zoom-overlay">
    <img src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" alt="" />
  </label>
</span>

Check the boxes to enable email communication for specific billing events. You can modify and manage your templates on the Email Templates settings page.

## Hosted Payment Pages

<span class="rp-zoom">
  <input type="checkbox" id="zoom-hosted-payment-pages" class="rp-zoom-toggle" />

  <label for="zoom-hosted-payment-pages">
    <img class="rp-zoom-img" src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" alt="Hosted Payment Pages settings" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-hosted-payment-pages" class="rp-zoom-overlay">
    <img src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" alt="" />
  </label>
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
  ### Checkout configuration

After creating a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration to direct customers to purchase it.

  <span class="rp-zoom">
    <input type="checkbox" id="zoom-checkout-config" class="rp-zoom-toggle" />

```
<label for="zoom-checkout-config">
  <img class="rp-zoom-img" src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" alt="Checkout configuration button" style={{display:"block", width:"280px", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
</label>

<label for="zoom-checkout-config" class="rp-zoom-overlay">
  <img src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" alt="" />
</label>
```

  </span>
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
  <input type="checkbox" id="zoom-plan-row-actions" class="rp-zoom-toggle" />

  <label for="zoom-plan-row-actions">
    <img class="rp-zoom-img" src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" alt="Plan row hover actions showing Edit, Duplicate, and Delete options" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-plan-row-actions" class="rp-zoom-overlay">
    <img src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Make your changes and select <strong>Save Changes</strong>.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa fa-exclamation-triangle" aria-hidden="true"></i> Plan name changes apply to existing subscriptions</strong> Updating a plan's name updates it site-wide. Existing subscriptions will show the new name in the Admin UI, and future invoice line items will use the updated name.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong> Versioned plan terms — such as price, billing interval, and setup fees — apply to new subscribers only. Existing subscribers keep the terms that were in effect when they signed up.</div>
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
  <input type="checkbox" id="zoom-duplicate-plan-form" class="rp-zoom-toggle" />

  <label for="zoom-duplicate-plan-form">
    <img class="rp-zoom-img" src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" alt="Duplicate plan form with -copy appended to name and code fields" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-duplicate-plan-form" class="rp-zoom-overlay">
    <img src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" alt="" />
  </label>
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
  <div><strong><i class="fa fa-lightbulb" aria-hidden="true"></i> Tip</strong> You can also duplicate a plan immediately after creating it — the success confirmation includes a duplicate option.</div>
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
  <input type="checkbox" id="zoom-delete-confirmation" class="rp-zoom-toggle" />

  <label for="zoom-delete-confirmation">
    <img class="rp-zoom-img" src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" alt="Delete plan confirmation dialog" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-delete-confirmation" class="rp-zoom-overlay">
    <img src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" alt="" />
  </label>
</span>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa fa-exclamation-triangle" aria-hidden="true"></i> Warning</strong> Deleting a plan is permanent and prevents new customers from subscribing to it. Existing subscriptions continue to renew, but once deleted, a plan can't be reactivated. Subscriptions tied to a deleted plan cannot be edited — including frequency, price, and add-ons.</div>
</div>

<br />
