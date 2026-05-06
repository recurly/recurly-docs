---
title: Copy of Plans
excerpt: >-
  Streamline your billing process with Recurly's versatile and customizable
  plans. Establish varied pricing strategies, offer free trials, and create
  seamless user journeys through the Checkout and Hosted Payment Pages.
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

<HTMLBlock>{`
<div class="rp-page">
  <div class="rp-overview">
    Plans are the foundation of your subscription business in Recurly. They define how often and how much your customers are charged, and you can create as many as your business needs — with no limits. From free trials and setup fees to ramp pricing and price segments, every billing model has a home here.
  </div>
  <div class="rp-plan">✦ Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#create-a-plan"><span class="rp-toc-num">3</span>Create a plan</a>
    <a class="rp-toc-pill" href="#edit-a-plan"><span class="rp-toc-num">4</span>Edit a plan</a>
    <a class="rp-toc-pill" href="#duplicate-a-plan"><span class="rp-toc-num">5</span>Duplicate a plan</a>
    <a class="rp-toc-pill" href="#delete-a-plan"><span class="rp-toc-num">6</span>Delete a plan</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">7</span>FAQs</a>
  </div>
  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>
  <div class="rp-definition">
    A Recurly plan is the blueprint for a subscription offering — it sets the billing frequency, pricing model, trial periods, add-ons, and renewal behavior for any customer who subscribes to it. Plans don't lock you into one approach: you can configure fixed or ramp pricing, offer free trials, add setup fees, and define different price points for different customer segments, all within a single plan.
  </div>
  <div class="rp-h1" id="key-benefits"><a class="rp-anchor" href="#key-benefits">Key benefits</a></div>
  <div class="rp-benefits rp-benefits-2x2">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Unlimited plan creation</strong>
      <span>Create as many plans as your business needs — each fully configurable to a specific audience or offering, with no restrictions.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Flexible pricing models</strong>
      <span>Choose from fixed, ramp, or usage-based pricing, and layer in price segments to target different customer groups without duplicating plans.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Built-in trial and fee support</strong>
      <span>Configure free or discounted trial periods and one-time setup fees directly on the plan — no custom workarounds needed.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Extensible with add-ons</strong>
      <span>Attach optional products and services to any plan to support upsells, quantity-based pricing, and enhanced customer value.</span>
    </div>
  </div>
  <div class="rp-card">
    Your <a href="https://app.recurly.com/go/plans" target="_blank" style="color:var(--tangerine);">plans dashboard</a> lists all plans defined in your Recurly account. Select any plan name to view its details, edit it, or access its <a href="https://docs.recurly.com/docs/checkout" target="_blank" style="color:var(--tangerine);">Checkout</a> configuration or Hosted Payment Page.
  </div>
  <div class="rp-h1" id="create-a-plan"><a class="rp-anchor" href="#create-a-plan">Create a plan</a></div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Open the new plan form</h4><p>Navigate to Configuration → Plans and click New Plan.</p></div>
    </div>
  </div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-new-plan-button" class="rp-zoom-toggle" />
    <label for="zoom-new-plan-button">
      <img class="rp-zoom-img" src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="New Plan button in the plans dashboard" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-new-plan-button" class="rp-zoom-overlay">
      <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
    </label>
  </span>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Define plan parameters</h4><p>Configure each section of the plan form using the fields described below.</p></div>
    </div>
  </div>
  <div class="rp-h2" id="plan-details"><a class="rp-anchor" href="#plan-details">Plan details</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-plan-details-fields" class="rp-zoom-toggle" />
    <label for="zoom-plan-details-fields">
      <img class="rp-zoom-img" src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" alt="Plan details fields including plan name, plan code, and plan description" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-plan-details-fields" class="rp-zoom-overlay">
      <img src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Plan name</td><td>Appears on the Hosted Payment Page and the subscriber's invoice. Limit: 255 characters. Check with your payment gateway before using special characters.</td></tr>
    <tr><td>Plan code</td><td>Your plan's unique identifier in Recurly. Used in Hosted Payment Page URLs and API requests. Limit: 25 alphanumeric characters.</td></tr>
    <tr><td>Plan description</td><td>Describes what the plan includes. Appears on the subscriber's email invoice if configured in email templates.</td></tr>
  </table>
  <div class="rp-h2" id="plan-configuration"><a class="rp-anchor" href="#plan-configuration">Plan configuration</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-currency-picker" class="rp-zoom-toggle" />
    <label for="zoom-currency-picker">
      <img class="rp-zoom-img" src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" alt="Currency picker in plan configuration" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-currency-picker" class="rp-zoom-overlay">
      <img src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" alt="" />
    </label>
  </span>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-free-trial-config" class="rp-zoom-toggle" />
    <label for="zoom-free-trial-config">
      <img class="rp-zoom-img" src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" alt="Free trial configuration options" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-free-trial-config" class="rp-zoom-overlay">
      <img src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" alt="" />
    </label>
  </span>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-setup-fee-field" class="rp-zoom-toggle" />
    <label for="zoom-setup-fee-field">
      <img class="rp-zoom-img" src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" alt="Setup fee configuration field" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-setup-fee-field" class="rp-zoom-overlay">
      <img src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Currencies</td><td>Choose which of your enabled currencies to include in this plan.</td></tr>
    <tr><td>Free trial</td><td>Define a free period in days or months. The paid subscription starts after the trial ends. You can choose whether to require billing information at sign-up.</td></tr>
    <tr><td>Setup fee</td><td>A one-time charge processed at sign-up.</td></tr>
  </table>
  <div class="rp-h2" id="billing-configuration"><a class="rp-anchor" href="#billing-configuration">Billing configuration</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-billing-configuration" class="rp-zoom-toggle" />
    <label for="zoom-billing-configuration">
      <img class="rp-zoom-img" src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" alt="Billing configuration settings including billing period and subscription term" style="display:block; width:75%; margin:16px auto; border-radius:8px;" />
    </label>
    <label for="zoom-billing-configuration" class="rp-zoom-overlay">
      <img src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Billing period</td><td>How often a subscriber is billed.</td></tr>
    <tr><td>Subscription term length</td><td>The default length of a customer's commitment. All renewals use this term unless modified at the individual subscription level.</td></tr>
    <tr><td>Billing cycles</td><td>Choose to automatically renew or expire the subscription after a set number of billing periods.</td></tr>
  </table>
  <div class="rp-h2" id="pricing-model"><a class="rp-anchor" href="#pricing-model">Pricing model</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-pricing-model-selector" class="rp-zoom-toggle" />
    <label for="zoom-pricing-model-selector">
      <img class="rp-zoom-img" src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" alt="Pricing model selector showing fixed and ramp options" style="display:block; width:75%; margin:16px auto; border-radius:8px;" />
    </label>
    <label for="zoom-pricing-model-selector" class="rp-zoom-overlay">
      <img src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Pricing model</td><td>Choose from fixed or ramp pricing to match your revenue strategy.</td></tr>
    <tr><td>Price</td><td>Set a fixed price for plan subscribers. For quantity-based pricing, use add-ons.</td></tr>
  </table>
  <div class="rp-h2" id="price-segments"><a class="rp-anchor" href="#price-segments">Price segments</a></div>
  <div class="rp-card">
    Price segments let you define different price points for a single plan within the same currency — useful for A/B testing or market-based pricing without duplicating plans. A default price is always required and is used whenever no segment code is provided.
    <br/><br/>
    <strong>Example:</strong> A gym with higher operating costs in certain cities can create one plan with segments — <code>default</code>, <code>nyc</code>, <code>la</code> — instead of cloning identical plans per city.
  </div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-price-segments-config" class="rp-zoom-toggle" />
    <label for="zoom-price-segments-config">
      <img class="rp-zoom-img" src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" alt="Price segments configuration showing multiple segment codes and prices" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-price-segments-config" class="rp-zoom-overlay">
      <img src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" alt="" />
    </label>
  </span>
  <div class="rp-h3" id="how-price-segments-work"><a class="rp-anchor" href="#how-price-segments-work">How price segments work</a></div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Add segments on the plan</h4><p>In the plan's Pricing section, create one or more segments and set a default.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Decide your selection rule</h4><p>For example: if city=NYC use segment nyc; if the user is in test group B, use segment exp-b.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Expose the right price in your UI</h4><p>Fetch the plan's price segments via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_plan" target="_blank" style="color:var(--tangerine);">API</a> or <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs" target="_blank" style="color:var(--tangerine);">Recurly.js</a> and render the price that matches your rule.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Apply the segment at checkout</h4><p>When creating the subscription, apply the chosen segment's price. If no segment is provided, the default price is used.</p></div>
    </div>
  </div>
  <div class="rp-callout rp-callout-tip">
    <strong>Tip</strong> For A/B tests, name segments clearly (e.g., <code>exp-a</code>, <code>exp-b</code>) and log the chosen segment code with your analytics events.
  </div>
  <div class="rp-h3" id="price-segmentation-limits-and-notes"><a class="rp-anchor" href="#price-segmentation-limits-and-notes">Price segmentation limits and notes</a></div>
  <ul class="rp-list">
    <li>No limit to the number of price segments per currency.</li>
    <li>Available on plans only (fixed and ramp). Not available on setup fees, add-ons, items, or Recurly Checkout.</li>
    <li>You can add segments to existing plans at any time.</li>
    <li>After creation, only the price within a segment can be edited — the segment code stays the same.</li>
    <li>Segment codes don't appear on invoices or in email templates; they're for your internal selection logic only.</li>
  </ul>
  <div class="rp-h3" id="developer-references"><a class="rp-anchor" href="#developer-references">Developer references</a></div>
  <div class="rp-card">
    <strong>v3 APIs</strong><br/>
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#tag/price_segment" target="_blank" style="color:var(--tangerine);">/price_segment</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_plans" target="_blank" style="color:var(--tangerine);">/plans</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription" target="_blank" style="color:var(--tangerine);">/subscriptions</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change" target="_blank" style="color:var(--tangerine);">/create_subscription_change</a>
    <br/><br/>
    <strong>Recurly.js</strong><br/>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs" target="_blank" style="color:var(--tangerine);">Surface the right price segment in your front end with Recurly.js</a>
  </div>
  <div class="rp-h2" id="additional-plan-fields"><a class="rp-anchor" href="#additional-plan-fields">Additional plan fields</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-billing-details-fields" class="rp-zoom-toggle" />
    <label for="zoom-billing-details-fields">
      <img class="rp-zoom-img" src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" alt="Billing details fields including accounting code and HS code" style="display:block; width:75%; margin:16px auto; border-radius:8px;" />
    </label>
    <label for="zoom-billing-details-fields" class="rp-zoom-overlay">
      <img src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" alt="" />
    </label>
  </span>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-plan-addons" class="rp-zoom-toggle" />
    <label for="zoom-plan-addons">
      <img class="rp-zoom-img" src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" alt="Plan add-ons configuration section" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-plan-addons" class="rp-zoom-overlay">
      <img src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" alt="" />
    </label>
  </span>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-dunning-campaign" class="rp-zoom-toggle" />
    <label for="zoom-dunning-campaign">
      <img class="rp-zoom-img" src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" alt="Dunning campaign selector on the plan form" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-dunning-campaign" class="rp-zoom-overlay">
      <img src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" alt="" />
    </label>
  </span>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-customer-emails" class="rp-zoom-toggle" />
    <label for="zoom-customer-emails">
      <img class="rp-zoom-img" src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" alt="Customer emails settings on the plan form" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-customer-emails" class="rp-zoom-overlay">
      <img src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Accounting code</td><td>A unique code to identify plans in internal invoice exports. Based on your tax settings and compliance requirements. Limit: 25 lowercase alphanumeric characters.</td></tr>
    <tr><td>HS code / Commodity code</td><td>A Harmonized System (HS) code for invoice compliance on traded products. Typically six or more digits. Limit: 25 lowercase alphanumeric characters.</td></tr>
    <tr><td>Add-ons</td><td>Optional products included in recurring subscription invoices. Supports quantity-based pricing. You can add items from the Item Catalog.</td></tr>
    <tr><td>Dunning campaign</td><td>Select the dunning campaign to associate with this plan.</td></tr>
    <tr><td>Customer emails</td><td>Enable email communication for specific events. Manage and modify templates on the Email Templates settings page.</td></tr>
  </table>
  <div class="rp-h2" id="hosted-payment-page-settings"><a class="rp-anchor" href="#hosted-payment-page-settings">Hosted Payment Page settings</a></div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-legacy-hpp" class="rp-zoom-toggle" />
    <label for="zoom-legacy-hpp">
      <img class="rp-zoom-img" src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" alt="Hosted Payment Page configuration settings" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-legacy-hpp" class="rp-zoom-overlay">
      <img src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" alt="" />
    </label>
  </span>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr><td>Plan quantity can be edited</td><td>Determines whether subscribers can choose their own quantity on the Hosted Payment Page.</td></tr>
    <tr><td>Return URL after success</td><td>Redirects the customer to a specific URL after a successful transaction.</td></tr>
    <tr><td>Bypass Recurly confirmation</td><td>Skip Recurly's confirmation page and use a custom return URL instead.</td></tr>
  </table>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Create the plan</h4><p>Once all parameters are defined, click Create Plan to finalize.</p></div>
    </div>
  </div>
  <div class="rp-card">
    <div class="rp-h3" id="checkout-configurations" style="margin-top:0;"><a class="rp-anchor" href="#checkout-configurations">Checkout configurations</a></div>
    After configuring a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank" style="color:var(--tangerine);">Checkout</a> configuration to direct customers to purchase it.
    <br/><br/>
    <span class="rp-zoom">
      <input type="checkbox" id="zoom-checkout-config-option" class="rp-zoom-toggle" />
      <label for="zoom-checkout-config-option">
        <img class="rp-zoom-img" src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" alt="Checkout configuration option on the plan detail page" style="display:block; width:280px; margin:8px auto 0; border:1px solid #CCC9B8; border-radius:8px;" />
      </label>
      <label for="zoom-checkout-config-option" class="rp-zoom-overlay">
        <img src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" alt="" />
      </label>
    </span>
  </div>
  <div class="rp-h1" id="edit-a-plan"><a class="rp-anchor" href="#edit-a-plan">Edit a plan</a></div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to Configuration → Plans.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Edit</h4><p>Hover over the plan row in the list view, or use the plan actions menu on the plan details page, and select Edit.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Save your changes</h4><p>Make your changes and select Save Changes.</p></div>
    </div>
  </div>
  <div class="rp-callout rp-callout-warning">
    <strong>Plan name changes apply to existing subscriptions</strong> Updating a plan's name updates it site-wide. Existing subscriptions show the new plan name in the Admin UI, and future invoice line items use the updated name.
  </div>
  <div class="rp-callout rp-callout-note">
    <strong>Note</strong> Versioned plan terms — such as price, billing interval, and setup fees — apply to new subscribers only. Existing subscribers keep the terms that were in effect when they signed up.
  </div>
  <div class="rp-h1" id="duplicate-a-plan"><a class="rp-anchor" href="#duplicate-a-plan">Duplicate a plan</a></div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to Configuration → Plans.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Duplicate</h4><p>Hover over any plan row to reveal additional options, then select Duplicate.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Adjust the copied plan</h4><p>All details from the original plan are copied to the Create a Plan form. <code>-copy</code> is appended to the Plan Name and Plan Code. Update these and modify any other fields as needed.</p></div>
    </div>
  </div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-duplicate-plan-form" class="rp-zoom-toggle" />
    <label for="zoom-duplicate-plan-form">
      <img class="rp-zoom-img" src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" alt="Create a Plan form pre-filled with duplicated plan details" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-duplicate-plan-form" class="rp-zoom-overlay">
      <img src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" alt="" />
    </label>
  </span>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Create the plan</h4><p>Click Create Plan once you've finished adjusting the details.</p></div>
    </div>
  </div>
  <div class="rp-callout rp-callout-tip">
    <strong>Tip</strong> You can also duplicate a plan immediately after creating it — the success alert includes a duplicate option.
  </div>
  <div class="rp-h1" id="delete-a-plan"><a class="rp-anchor" href="#delete-a-plan">Delete a plan</a></div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to Configuration → Plans.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Delete</h4><p>Hover over the plan row, or use the plan actions dropdown on the plan details page, and select Delete.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Confirm your decision</h4><p>Confirm the deletion in the prompt.</p></div>
    </div>
  </div>
  <span class="rp-zoom">
    <input type="checkbox" id="zoom-delete-confirmation" class="rp-zoom-toggle" />
    <label for="zoom-delete-confirmation">
      <img class="rp-zoom-img" src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" alt="Delete confirmation dialog" style="display:block; width:75%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-delete-confirmation" class="rp-zoom-overlay">
      <img src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" alt="" />
    </label>
  </span>
  <div class="rp-callout rp-callout-warning">
    <strong>Deleting a plan is permanent</strong> New customers can't subscribe to a deleted plan. Existing subscriptions will continue to renew, but the plan can't be reactivated. Any subscriptions tied to a deleted plan can't be edited — including frequency, price, and add-ons.
  </div>
  <div class="rp-h1" id="faqs"><a class="rp-anchor" href="#faqs">FAQs</a></div>
</div>
`}</HTMLBlock>

<Accordion title="Is there a limit to how many plans I can create?">
  No. You can create as many plans as your business needs — there are no limits on plan count, currencies per plan, or price segments per currency.
</Accordion>

<Accordion title="If I edit a plan's price, do existing subscribers pay the new price?">
  No. Versioned plan terms — including price, billing interval, and setup fees — apply only to new subscribers. Existing subscribers keep the terms that were in effect when they signed up. To change pricing for existing subscribers, you'll need to modify their individual subscriptions.
</Accordion>

<Accordion title="Can I recover a plan after deleting it?">
  No. Deletion is permanent. The plan can't be reactivated, no new customers can subscribe to it, and any subscriptions still tied to it can't be edited — including frequency, price, and add-ons. Existing subscriptions will continue to renew on their current terms until they end. If you might want the plan back later, duplicate it first or use Edit to make it inactive instead.
</Accordion>
