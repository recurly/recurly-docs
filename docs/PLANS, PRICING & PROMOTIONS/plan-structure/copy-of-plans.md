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
  .rp-benefits { display: grid; grid-template-columns: repeat(auto-fit, minmax(210px, 1fr)); gap: 14px; margin-bottom: 32px; }
  .rp-benefit { background: var(--offblack); color: var(--offwhite); border-radius: 10px; padding: 20px; }
  .rp-benefit-icon { color: var(--yellow); font-size: 20px; margin-bottom: 10px; }
  .rp-benefit strong { display: block; font-size: 14px; font-weight: 700; margin-bottom: 6px; color: var(--offwhite); }
  .rp-benefit span { font-size: 13px; color: var(--lightgray); line-height: 1.5; }
  .rp-h1 { font-size: 1.5rem; font-weight: 800; color: var(--offblack); margin: 36px 0 14px; padding-bottom: 8px; border-bottom: 2px solid var(--yellow); }
  .rp-h2 { font-size: 1.1rem; font-weight: 700; color: var(--darknavy); margin: 28px 0 10px; }
  .rp-h3 { font-size: 0.95rem; font-weight: 700; color: var(--darkgray); margin: 20px 0 8px; }
  .rp-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 22px 26px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.65; }
  .rp-card ul { margin: 8px 0 0 0; padding-left: 20px; }
  .rp-card ul li { margin-bottom: 6px; }
  .rp-card ul ul { margin-top: 4px; }
  .rp-steps { display: flex; flex-direction: column; gap: 12px; margin-bottom: 24px; }
  .rp-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 18px 22px; }
  .rp-step-num { width: 34px; height: 34px; border-radius: 8px; background: var(--offblack); color: var(--yellow); font-weight: 800; font-size: 14px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
  .rp-step h4 { font-size: 0.95rem; font-weight: 700; color: var(--offblack); margin: 0 0 4px; }
  .rp-step p { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }
  .rp-step ul { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 6px 0 0; padding-left: 18px; }
  .rp-callout { border-radius: 0 8px 8px 0; padding: 14px 18px; margin: 16px 0; font-size: 14px; }
  .rp-callout strong { display: block; margin-bottom: 3px; }
  .rp-callout-tip     { border-left: 4px solid var(--yellow);    background: var(--offwhite);  color: var(--darkgray); }
  .rp-callout-warning { border-left: 4px solid var(--tangerine); background: #FFF8F2;           color: var(--darkgray); }
  .rp-callout-note    { border-left: 4px solid var(--offblack);  background: var(--brightgray); color: var(--deepchar); }
  .rp-btn { display: inline-block; padding: 10px 22px; border-radius: 8px; font-weight: 700; font-size: 14px; text-decoration: none; margin: 6px 8px 6px 0; font-family: var(--font); }
  .rp-btn-primary { background: var(--offblack); color: var(--yellow); }
  .rp-list { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 10px; padding: 16px 22px 16px 38px; margin-bottom: 20px; font-size: 14px; color: var(--darkgray); line-height: 1.7; }
  .rp-params { width: 100%; border-collapse: collapse; font-size: 14px; margin: 12px 0 20px; }
  .rp-params thead tr { background: var(--offblack); color: var(--offwhite); }
  .rp-params th { padding: 10px 14px; text-align: left; font-weight: 700; }
  .rp-params td { padding: 10px 14px; border-bottom: 1px solid var(--lightgray); vertical-align: top; }
  .rp-params tr:nth-child(even) td { background: var(--brightgray); }
  .rp-params tr:nth-child(odd) td { background: var(--offwhite); }
  .rp-params td:first-child { font-weight: 600; color: var(--offblack); width: 28%; }
  .rp-tag { display: inline-block; background: var(--yellow); color: var(--offblack); font-size: 11px; font-weight: 700; padding: 2px 8px; border-radius: 10px; margin-left: 6px; vertical-align: middle; }
  @media (max-width: 640px) { .rp-benefits { grid-template-columns: 1fr; } .rp-h1 { font-size: 1.25rem; } }
</style>
</head>
<body>
<div class="rp-page">

  <div class="rp-overview">
    Plans are the foundation of your subscription business in Recurly. They define how often and how much your customers are charged, and you can create as many as your business needs — with no limits. From free trials and setup fees to ramp pricing and price segments, every billing model has a home here.
  </div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-h1">Definition</div>
  <div class="rp-definition">
    A Recurly plan is the blueprint for a subscription offering — it sets the billing frequency, pricing model, trial periods, add-ons, and renewal behavior for any customer who subscribes to it. Plans don't lock you into one approach: you can configure fixed or ramp pricing, offer free trials, add setup fees, and define different price points for different customer segments, all within a single plan.
  </div>

  <div class="rp-h1">Key benefits</div>
  <div class="rp-benefits">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Unlimited plan creation</strong>
      <span>Create as many plans as your business needs with no restrictions — each one fully configurable to a specific audience or offering.</span>
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

  <div class="rp-h1">Key details</div>

  <div class="rp-h2">Plans dashboard</div>
  <div class="rp-card">
    Your <a href="https://app.recurly.com/go/plans" target="_blank" style="color: var(--tangerine);">plans dashboard</a> lists all plans defined in your Recurly account. Select any plan name to view its details, edit the plan, or access its <a href="https://docs.recurly.com/docs/checkout" target="_blank" style="color: var(--tangerine);">Checkout</a> configuration or Hosted Payment Page.
  </div>

  <div class="rp-h2">Creating a plan</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div>
        <h4>Create a new plan</h4>
        <p>Navigate to <strong>Configuration → Plans</strong> and click <strong>New Plan</strong>.</p>
      </div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div>
        <h4>Define plan parameters</h4>
        <p>Configure each section of the plan form:</p>
      </div>
    </div>
  </div>

  <div class="rp-h3">Plan details</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Plan name</td><td>Appears on the Hosted Payment Page and the subscriber's invoice. Limit: 255 characters. Check with your payment gateway before using special characters.</td></tr>
      <tr><td>Plan code</td><td>Your plan's unique identifier in Recurly. Used in Hosted Payment Page URLs and API requests. Limit: 25 alphanumeric characters.</td></tr>
      <tr><td>Plan description</td><td>Describes what the plan includes. Appears on the subscriber's email invoice if configured in email templates.</td></tr>
    </tbody>
  </table>

  <div class="rp-h3">Plan configuration</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Currencies</td><td>Choose which of your enabled currencies to include in this plan.</td></tr>
      <tr><td>Free trial</td><td>Define a free period in days or months. The paid subscription starts after the trial ends. You can choose whether to require billing information at sign-up.</td></tr>
      <tr><td>Setup fee</td><td>A one-time charge processed at sign-up.</td></tr>
    </tbody>
  </table>

  <div class="rp-h3">Billing configuration</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Billing period</td><td>How often a subscriber is billed.</td></tr>
      <tr><td>Subscription term length</td><td>The default length of a customer's commitment. All renewals use this term unless modified at the individual subscription level.</td></tr>
      <tr><td>Billing cycles</td><td>Choose to automatically renew or expire the subscription after a set number of billing periods.</td></tr>
    </tbody>
  </table>

  <div class="rp-h3">Pricing model</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Pricing model</td><td>Choose from fixed or ramp pricing to match your revenue strategy.</td></tr>
      <tr><td>Price</td><td>Set a fixed price for plan subscribers. For quantity-based pricing, use add-ons.</td></tr>
    </tbody>
  </table>

  <div class="rp-h3">Price segments</div>
  <div class="rp-card">
    Price segments let you define different price points for a single plan within the same currency — useful for A/B testing or market-based pricing without duplicating plans. A default price is always required and is used whenever no segment code is provided.
    <br/><br/>
    <strong>Example:</strong> A gym with higher operating costs in certain cities can create one plan with segments — <code>default</code>, <code>nyc</code>, <code>la</code> — instead of cloning identical plans per city.
  </div>

  <div class="rp-h3" style="margin-top: 4px;">How price segments work</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Add segments on the plan</h4><p>In the plan's Pricing section, create one or more segments and set a default.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Decide your selection rule</h4><p>For example: if <code>city=NYC</code> use segment <code>nyc</code>; if user is in test group B, use segment <code>exp-b</code>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Expose the right price in your UI</h4><p>Fetch the plan's price segments via the <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_plan" target="_blank" style="color: var(--tangerine);">API</a> or <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/" target="_blank" style="color: var(--tangerine);">Recurly.js</a> and render the price that matches your rule.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Apply the segment at checkout</h4><p>When creating the subscription, apply the chosen segment's price. If no segment is provided, the default price is used.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-tip">
    <strong>Tip</strong>For A/B tests, name segments clearly (e.g., <code>exp-a</code>, <code>exp-b</code>) and log the chosen segment code with your analytics events.
  </div>

  <div class="rp-h3">Price segmentation limits and notes</div>
  <ul class="rp-list">
    <li>No limit to the number of price segments per currency.</li>
    <li>Available on plans only (fixed and ramp). Not available on setup fees, add-ons, items, or Recurly Checkout.</li>
    <li>You can add segments to existing plans at any time.</li>
    <li>After creation, only the price within a segment can be edited — the segment code stays the same.</li>
    <li>Segment codes don't appear on invoices or in email templates; they're for your internal selection logic only.</li>
  </ul>

  <div class="rp-h3">Developer references</div>
  <div class="rp-card">
    <strong>v3 APIs</strong><br/>
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#tag/price_segment" target="_blank" style="color: var(--tangerine);">/price_segment</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_plans" target="_blank" style="color: var(--tangerine);">/plans</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription" target="_blank" style="color: var(--tangerine);">/subscriptions</a> &nbsp;·&nbsp;
    <a href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change" target="_blank" style="color: var(--tangerine);">/create_subscription_change</a>
    <br/><br/>
    <strong>Recurly.js</strong><br/>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/" target="_blank" style="color: var(--tangerine);">Surface the right price segment in your front end with Recurly.js</a>
  </div>

  <div class="rp-h3">Additional plan fields</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Add-ons</td><td>Optional products included in recurring subscription invoices. Supports quantity-based pricing. You can add items from the Item Catalog.</td></tr>
      <tr><td>Dunning campaign</td><td>Select the dunning campaign to associate with this plan.</td></tr>
      <tr><td>Customer emails</td><td>Enable email communication for specific events. Manage and modify templates on the Email Templates settings page.</td></tr>
      <tr><td>Accounting code</td><td>A unique code to identify plans in internal invoice exports. Based on your tax settings and compliance requirements. Limit: 25 lowercase alphanumeric characters.</td></tr>
      <tr><td>HS code / Commodity code</td><td>A Harmonized System (HS) code for invoice compliance on traded products. Typically six or more digits. Limit: 25 lowercase alphanumeric characters.</td></tr>
    </tbody>
  </table>

  <div class="rp-h3">Hosted Payment Page settings</div>
  <table class="rp-params">
    <thead><tr><th>Field</th><th>Description</th></tr></thead>
    <tbody>
      <tr><td>Plan quantity can be edited</td><td>Determines whether subscribers can choose their own quantity on the Hosted Payment Page.</td></tr>
      <tr><td>Return URL after success</td><td>Redirects the customer to a specific URL after a successful transaction via the Hosted Payment Page.</td></tr>
      <tr><td>Bypass Recurly confirmation</td><td>Skip Recurly's confirmation page and use a custom return URL instead.</td></tr>
    </tbody>
  </table>

  <div class="rp-step" style="margin-bottom: 24px;">
    <div class="rp-step-num">3</div>
    <div><h4>Create the plan</h4><p>Once all parameters are defined, click <strong>Create Plan</strong> to finalize.</p></div>
  </div>

  <div class="rp-h2">Checkout configurations</div>
  <div class="rp-card">
    After configuring a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank" style="color: var(--tangerine);">Checkout</a> configuration to direct customers to purchase it.
  </div>

  <div class="rp-h2">Updating plans</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Edit</h4><p>Hover over the plan row in the list view, or use the plan actions menu on the plan details page, and select <strong>Edit</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Save your changes</h4><p>Make your changes and select <strong>Save Changes</strong>.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-warning">
    <strong>Plan name changes apply to existing subscriptions</strong>Updating a plan's name updates it site-wide. Existing subscriptions will show the new plan name in the Admin UI, and future invoice line items will use the updated name.
  </div>

  <div class="rp-callout rp-callout-note">
    <strong>Note</strong>Versioned plan terms — such as price, billing interval, and setup fees — apply to new subscribers only. Existing subscribers keep the terms that were in effect when they signed up.
  </div>

  <div class="rp-h2">Duplicating plans</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Duplicate</h4><p>Hover over any plan row to reveal additional options, then select <strong>Duplicate</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Adjust the copied plan</h4><p>All details from the original plan are copied to the Create a Plan form. <code>-copy</code> is appended to the Plan Name and Plan Code fields. Update these and modify any other fields as needed.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Create the plan</h4><p>Click <strong>Create Plan</strong> once you've finished adjusting the details.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-tip">
    <strong>Tip</strong>You can also duplicate a plan immediately after creating it — the success alert includes a duplicate option.
  </div>

  <div class="rp-h2">Deleting plans</div>
  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to plans</h4><p>Go to <strong>Configuration → Plans</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Select Delete</h4><p>Either from the plan list view (hover over the row) or the plan actions dropdown on a plan's detail page, select <strong>Delete</strong>.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Confirm your decision</h4><p>Confirm the deletion in the prompt.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-warning">
    <strong>Deleting a plan is permanent</strong>New customers won't be able to subscribe to a deleted plan. Existing subscriptions will continue to renew, but the plan cannot be reactivated. Any subscriptions tied to a deleted plan cannot be edited — including frequency, price, and add-ons.
  </div>

  <div class="rp-h1">FAQs</div>

</div>
</body>
</html>
`}</HTMLBlock>
