---
title: Copy of Add-ons
excerpt: >-
  How add-ons work in Recurly, including pricing models, billing options, and
  how to configure them on plans or directly on subscriptions.
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<div class="rp-page">

  <div class="rp-overview">
    Add-ons let you charge for extras alongside a subscription's base price — flexible pricing, per-plan or shared across plans, and configurable directly on a subscription when needed.
  </div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#creating-an-add-on"><span class="rp-toc-num">3</span>Creating an add-on</a>
    <a class="rp-toc-pill" href="#configuring-item-add-ons-directly-on-subscriptions"><span class="rp-toc-num">4</span>Configuring item add-ons on subscriptions</a>
  </div>

  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>

  <div class="rp-definition">
    Add-ons are additional charges billed each period alongside a subscription's base charge. You can attach one or more add-ons to a plan, giving you granular control over packaging and pricing. Build them from scratch for a single plan, or derive them from an Item in your Item Catalog so you can reuse them across multiple plans.
  </div>

  <div class="rp-h1" id="key-benefits"><a class="rp-anchor" href="#key-benefits">Key benefits</a></div>

  <div class="rp-benefits">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Versatility</strong>
      <span>Design an add-on from scratch, or derive one from an Item in your catalog and reuse it across plans.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Customization</strong>
      <span>Define every detail — type, name, code, accounting code, pricing model, tiers, taxes, and opt-out or editable-quantity options.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Flexible billing</strong>
      <span>Bill up front or in arrears with usage-based billing — match how your customers actually consume the add-on.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Pricing models</strong>
      <span>Choose Fixed Price, Tiered, Volume, or Stairstep to fit any pricing strategy.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Items on subscriptions</strong>
      <span>Configure item-based add-ons directly on a subscription — no need to attach them to the plan first.</span>
    </div>
  </div>

  <div class="rp-h1" id="creating-an-add-on"><a class="rp-anchor" href="#creating-an-add-on">Creating an add-on</a></div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Navigate to your plan settings</h4><p>Open the plan in the Recurly Admin Console, or use the Plans or Add-ons API endpoints.</p></div>
    </div>
  </div>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Choose the add-on source</h4><p>Create an add-on that's unique to the plan, or build one from a saved item in your catalog.</p></div>
    </div>
  </div>

  <span class="rp-zoom">
    <input type="checkbox" id="zoom-add-on-source-selector" class="rp-zoom-toggle" />
    <label for="zoom-add-on-source-selector">
      <img class="rp-zoom-img"
           src="https://files.readme.io/5916c04-Screenshot_2023-12-05_at_1.58.47_PM.png"
           alt="Selector for creating an add-on unique to the plan or from an item in the catalog"
           style="display:block; width:90%; margin:16px auto; border:1px solid #CCC9B8; border-radius:8px;" />
    </label>
    <label for="zoom-add-on-source-selector" class="rp-zoom-overlay">
      <img src="https://files.readme.io/5916c04-Screenshot_2023-12-05_at_1.58.47_PM.png" alt="" />
    </label>
  </span>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Define the add-on's properties</h4><p>Set type, name, code, accounting code, HS code, pricing model, price, tiers, taxes, and options for opting out or editable quantity. Item-based add-ons auto-populate some of these fields.</p></div>
    </div>
  </div>

  <table class="rp-params">
    <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
    <tr>
      <td>Accounting code</td>
      <td>A unique code that identifies the plan in your internal invoice exports. Configure based on your tax settings and compliance requirements. Limited to 25 lowercase alphanumeric characters.</td>
    </tr>
    <tr>
      <td>HS code / Commodity code</td>
      <td>A Harmonized System (HS) code or Commodity Code that meets invoice compliance requirements for traded products. HS codes are typically at least six digits, with countries adding more for national or regional classification. Limited to 25 lowercase alphanumeric characters.</td>
    </tr>
  </table>

  <span class="rp-zoom">
    <input type="checkbox" id="zoom-add-on-properties" class="rp-zoom-toggle" />
    <label for="zoom-add-on-properties">
      <img class="rp-zoom-img"
           src="https://files.readme.io/8c21c4e0ebd874c93570696c830ee4b1e68664d47d108291d1fc23ff910077c1-image.png"
           alt="Add-on properties form showing accounting code and HS code fields"
           style="display:block; width:90%; margin:16px auto; border-radius:8px;" />
    </label>
    <label for="zoom-add-on-properties" class="rp-zoom-overlay">
      <img src="https://files.readme.io/8c21c4e0ebd874c93570696c830ee4b1e68664d47d108291d1fc23ff910077c1-image.png" alt="" />
    </label>
  </span>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">4</div>
      <div><h4>Save your changes</h4><p>Save the add-on to attach it to the plan.</p></div>
    </div>
  </div>

  <div class="rp-h1" id="configuring-item-add-ons-directly-on-subscriptions"><a class="rp-anchor" href="#configuring-item-add-ons-directly-on-subscriptions">Configuring item add-ons directly on subscriptions</a></div>

  <p>Item-based add-ons can be added straight to a customer's subscription — you don't need to configure availability on the plan first.</p>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Follow the Item Catalog instructions</h4><p>Set up the item in your catalog using the steps in the <a href="https://docs.recurly.com/docs/catalog" target="_blank">Item Catalog documentation</a>, then add it directly to the subscription.</p></div>
    </div>
  </div>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>You don't need to configure the add-on's availability on the plan first — item-based add-ons can be added to any subscription on demand.</div>
  </div>

</div>
`}</HTMLBlock>