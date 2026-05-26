---
title: Ramp pricing
excerpt: >-
  Configure subscription prices that increase or decrease over time using
  Recurly's ramp pricing — ideal for introductory offers and customer loyalty
  programs.
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
  <div class="rp-overview">
    Ramp pricing lets you define a series of price changes that take effect automatically over a subscription's lifetime. Use it to attract new customers with a lower introductory price that steps up over time, or reward long-term subscribers with a price that decreases as the relationship grows.
  </div>

  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true" /> Not included in Starter or Pro — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to upgrade</div>

  ### Prerequisites

  <ul class="rp-list">
    <li><strong>Only Bill What Changed</strong> must be enabled to use ramp pricing.</li>
    <li>If your account was created before May 2018, <strong>Credit Invoices</strong> must also be enabled. Contact <a href="mailto:support@recurly.com" target="_blank">[support@recurly.com](mailto:support@recurly.com)</a> to have these features added to your account.</li>
  </ul>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#create-a-plan-with-ramp-pricing"><span class="rp-toc-num">4</span>Create a plan with ramp pricing</a>
    <a class="rp-toc-pill" href="#create-a-subscription-with-ramp-pricing"><span class="rp-toc-num">5</span>Create a subscription with ramp pricing</a>
    <a class="rp-toc-pill" href="#edit-a-subscription-with-ramp-pricing"><span class="rp-toc-num">6</span>Edit a subscription with ramp pricing</a>
    <a class="rp-toc-pill" href="#migrate-existing-subscribers"><span class="rp-toc-num">7</span>Migrate existing subscribers</a>
  </div>
</div>

# Definition

<div class="rp-definition">
  Ramp pricing is a Recurly feature that lets you define a series of price points — called ramp intervals — that change automatically over a subscription's billing periods. Prices can step up to attract new customers at a lower introductory rate, or step down to reward long-term subscribers with loyalty pricing. Up to 12 intervals can be configured per plan.
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon">
      <i class="fa-solid fa-user-plus" aria-hidden="true" />
    </div>

    <strong>Customer acquisition</strong>
    <span>Start subscribers at a lower introductory price that increases over time — a natural way to reduce sign-up friction without permanently discounting your offering.</span>
  </div>

  <div class="rp-benefit">
    <div class="rp-benefit-icon">
      <i class="fa-solid fa-heart" aria-hidden="true" />
    </div>

    <strong>Customer retention</strong>
    <span>Reward loyalty with a pricing model that decreases over time, giving long-term subscribers a tangible reason to stay.</span>
  </div>

  <div class="rp-benefit">
    <div class="rp-benefit-icon">
      <i class="fa-solid fa-calendar-days" aria-hidden="true" />
    </div>

    <strong>Future price adjustments</strong>
    <span>Start with a single price point and add ramp intervals later — so you can adapt to market changes or business strategy shifts without rebuilding your plans.</span>
  </div>
</div>

# Key details

Ramp pricing is fully compatible with all other Recurly features including coupons, gift cards, trials, aligned renewals, paused subscriptions, plan changes, and subscription modifications.

## Ramp intervals

* Intervals can represent a price increase or decrease
* Up to 12 intervals per plan or subscription
* Prices can be set in all currencies configured on your site
* Intervals can extend beyond the subscription term; if the term auto-renews, intervals continue at the configured schedule once a new term starts
* A subscription must be created from a plan that already has ramp intervals — you can't add ramp intervals to a subscription independently

## Pausing subscriptions

* Ramp-priced subscriptions can be paused immediately or scheduled for pause
* The ramp interval schedule pauses with the subscription and resumes on unpause
* Modifying the pricing schedule cancels any scheduled pause and generates an invoice for the next billing cycle

## Trials

Trials work alongside ramp pricing. Set the trial duration on the plan — the first ramp interval price is charged once the trial period ends.

<span class="rp-zoom">
  <input type="checkbox" id="zoom-ramp-trial" class="rp-zoom-toggle" />

  <label for="zoom-ramp-trial">
    <img class="rp-zoom-img" src="https://files.readme.io/45e601c-Ramp_Sub_with_Trial.png" alt="Ramp subscription with trial period configured" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-ramp-trial" class="rp-zoom-overlay">
    <img src="https://files.readme.io/45e601c-Ramp_Sub_with_Trial.png" alt="" />
  </label>
</span>

## Ramp price change email

An email template is available to notify subscribers of upcoming price changes.

* Configure the **Ramp Price Change** template under Subscription Renewal templates in your email settings
* The email is sent when a new ramp interval begins
* Supported template parameters: `next_ramp_interval_start_date` and `next_ramp_interval_price`
* If the ramp price change email is scheduled on the same day as other renewal reminders, it takes priority

## Exports

* A dedicated **Subscriptions — Ramp Pricing Export** provides detailed information for each ramp interval per subscription. See the <a href="https://docs.recurly.com/docs/subscription-ramp-pricing-export" target="_blank">export documentation</a> for details.
* The **Subscriptions**, **Subscription — History**, and **Subscriptions — Churned** exports now include two additional columns: `pricing_model` and `current_ramp_id`

## Analytics

Ramp-priced plan performance is available in the Plans, Promotions & Pricing section of Recurly Analytics.

## Activity logs

Activity logs capture before-and-after comparisons for changes to a ramp-priced subscription's pricing schedule — useful for support teams verifying whether a change has already been applied.

## Checkout and Hosted Pages

* Checkout and Hosted Payment Page display the **starting price** — the price of the first ramp interval. Display additional pricing details on the page your customer is directed from.
* Hosted Account Management Page shows the cost of the next ramp interval at the next invoice date.

## Salesforce integration

Ramp-priced subscriptions can be created via Salesforce using the default ramp intervals from the plan.

## Sandbox to production

Ramp pricing can be tested on all Recurly sandbox and development sites. In production, it's available only on Professional or Elite plans.

When converting a sandbox or development site to a Core production site, all ramp-priced plans are deleted and cannot be edited or re-enabled on the Core plan. Once upgraded to a Professional or Elite plan, ramp-priced plans can be created and used normally.

## Changing plans on a subscription

You can change the base plan of a subscription immediately, at the billing date, or at renewal. When changing plans, you can modify the ramp interval schedule for the new plan — including removing introductory intervals and switching directly to the full price — without creating a new plan or saving and re-editing the subscription.

<div class="rp-card">
  ### Example

  A customer completes the intro ramp interval on a lower-priced plan and is now paying full price. If they want to upgrade to a higher-priced plan, you can move them directly to the full price on the new plan, bypassing its introductory intervals entirely.
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-plan-change" class="rp-zoom-toggle" />

  <label for="zoom-plan-change">
    <img class="rp-zoom-img" src="https://files.readme.io/34de9d9-Changing_plans_on_a_subscription.png" alt="Changing plans on a ramp-priced subscription" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-plan-change" class="rp-zoom-overlay">
    <img src="https://files.readme.io/34de9d9-Changing_plans_on_a_subscription.png" alt="" />
  </label>
</span>

# Create a plan with ramp pricing

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the new plan form</h4><p>Navigate to <strong>Configuration → Plans</strong> in the Recurly Admin Console and click <strong>New Plan</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step1" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step1">
    <img class="rp-zoom-img" src="https://files.readme.io/0d6fd0e-Step_1.png" alt="Plans list with New Plan button" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step1" class="rp-zoom-overlay">
    <img src="https://files.readme.io/0d6fd0e-Step_1.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Fill in the plan details and select Ramp pricing</h4><p>Complete all required fields. Under <strong>Billing Configuration</strong>, your end-of-subscription-term setting — auto-renew or expire — won't affect the ramp schedule for the subscription's lifetime. Under <strong>Pricing Model</strong>, select <strong>Ramp</strong> from the dropdown.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step2" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step2">
    <img class="rp-zoom-img" src="https://files.readme.io/776f024-Step_2.png" alt="Pricing model dropdown with Ramp selected" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step2" class="rp-zoom-overlay">
    <img src="https://files.readme.io/776f024-Step_2.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Set the first ramp interval price</h4><p>Enter the price per billing period for your first ramp. Prices can increase or decrease depending on your strategy.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step3" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step3">
    <img class="rp-zoom-img" src="https://files.readme.io/feaf205-Step_3.png" alt="First ramp interval price entry" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step3" class="rp-zoom-overlay">
    <img src="https://files.readme.io/feaf205-Step_3.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Add additional ramp intervals</h4><p>Click <strong>Add another ramp</strong> to add more intervals. You can add up to 12 ramps per plan.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step4" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step4">
    <img class="rp-zoom-img" src="https://files.readme.io/2885fbc-Step_4.png" alt="Adding a second ramp interval" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step4" class="rp-zoom-overlay">
    <img src="https://files.readme.io/2885fbc-Step_4.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Save and review the plan</h4><p>Once created, the plan appears in the <strong>Plans</strong> list. The price displayed is the first ramp interval's price.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step5" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step5">
    <img class="rp-zoom-img" src="https://files.readme.io/a5cf870-Step_5.png" alt="Plans list showing the newly created ramp-priced plan" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step5" class="rp-zoom-overlay">
    <img src="https://files.readme.io/a5cf870-Step_5.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Edit the plan when needed</h4><p>Navigate to the plan and select <strong>Edit Plan</strong> to modify ramp intervals and pricing at any time.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-create-plan-step6" class="rp-zoom-toggle" />

  <label for="zoom-create-plan-step6">
    <img class="rp-zoom-img" src="https://files.readme.io/113d4a9-Step_6.png" alt="Edit plan form for a ramp-priced plan" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-create-plan-step6" class="rp-zoom-overlay">
    <img src="https://files.readme.io/113d4a9-Step_6.png" alt="" />
  </label>
</span>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true" /> Multiple currencies</strong> If your site has multiple currencies enabled, you can set a price for each ramp interval in each currency.</div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-multiple-currencies" class="rp-zoom-toggle" />

  <label for="zoom-multiple-currencies">
    <img class="rp-zoom-img" src="https://files.readme.io/d297244-Plan_with_Multiple_Currencies.png" alt="Ramp plan with multiple currency pricing configured" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-multiple-currencies" class="rp-zoom-overlay">
    <img src="https://files.readme.io/d297244-Plan_with_Multiple_Currencies.png" alt="" />
  </label>
</span>

# Create a subscription with ramp pricing

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the add subscription form</h4><p>In the Recurly Admin Console, navigate to the customer's account and click <strong>Add Subscription</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step1" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step1">
    <img class="rp-zoom-img" src="https://files.readme.io/0f60395-sub_create_-_step1.png" alt="Account page with Add Subscription button" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step1" class="rp-zoom-overlay">
    <img src="https://files.readme.io/0f60395-sub_create_-_step1.png" alt="" />
  </label>
</span>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step1b" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step1b">
    <img class="rp-zoom-img" src="https://files.readme.io/3840d4e-sub_create_-_step1a.png" alt="Add subscription form" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step1b" class="rp-zoom-overlay">
    <img src="https://files.readme.io/3840d4e-sub_create_-_step1a.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select the ramp-priced plan</h4><p>Choose the ramp-priced plan you want to assign to this subscription.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step2" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step2">
    <img class="rp-zoom-img" src="https://files.readme.io/026956a-sub_create_-_step2.png" alt="Plan selection showing ramp-priced plan" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step2" class="rp-zoom-overlay">
    <img src="https://files.readme.io/026956a-sub_create_-_step2.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Review the ramp schedule</h4><p>By default, the subscription uses the ramp pricing schedule from the plan. Review it before proceeding.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step3" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step3">
    <img class="rp-zoom-img" src="https://files.readme.io/be53cb3-sub_create_-_step3.png" alt="Default ramp pricing schedule on the subscription" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step3" class="rp-zoom-overlay">
    <img src="https://files.readme.io/be53cb3-sub_create_-_step3.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Customize the ramp schedule (optional)</h4><p>To override the plan's default ramp schedule for this subscription, click <strong>Edit Pricing</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step4" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step4">
    <img class="rp-zoom-img" src="https://files.readme.io/e1fa048-sub_create_-_step4.png" alt="Edit Pricing link on the subscription form" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step4" class="rp-zoom-overlay">
    <img src="https://files.readme.io/e1fa048-sub_create_-_step4.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Apply and save</h4><p>Make your changes in the side dialog, then click <strong>Apply Changes</strong>. The updated pricing schedule is reflected immediately. Select <strong>Save</strong> on the subscription form to finalize.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-sub-create-step5" class="rp-zoom-toggle" />

  <label for="zoom-sub-create-step5">
    <img class="rp-zoom-img" src="https://files.readme.io/307ffa0-sub_create_-_step6.png" alt="Updated pricing schedule after applying changes" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-sub-create-step5" class="rp-zoom-overlay">
    <img src="https://files.readme.io/307ffa0-sub_create_-_step6.png" alt="" />
  </label>
</span>

# Edit a subscription with ramp pricing

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true" /> Note</strong> Only immediate changes can be made to a ramp pricing schedule on an existing subscription.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the subscription edit form</h4><p>Navigate to the subscription and click <strong>Edit Subscription</strong>.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-edit-sub-step1" class="rp-zoom-toggle" />

  <label for="zoom-edit-sub-step1">
    <img class="rp-zoom-img" src="https://files.readme.io/39f09af-edit_-_step_1.png" alt="Edit Subscription button on the subscription page" style={{display:"block", width:"90%", margin:"16px auto", borderRadius:"8px"}} />
  </label>

  <label for="zoom-edit-sub-step1" class="rp-zoom-overlay">
    <img src="https://files.readme.io/39f09af-edit_-_step_1.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the pricing editor</h4><p>Click <strong>Edit Pricing</strong> to open the ramp schedule editor.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-edit-sub-step2" class="rp-zoom-toggle" />

  <label for="zoom-edit-sub-step2">
    <img class="rp-zoom-img" src="https://files.readme.io/4144501-edit_-_step_2.png" alt="Edit Pricing link on the subscription edit form" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-edit-sub-step2" class="rp-zoom-overlay">
    <img src="https://files.readme.io/4144501-edit_-_step_2.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Make your changes</h4><p>Add new price change intervals, adjust the price or duration of an upcoming interval, or modify the price for the current billing period.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-edit-sub-step3" class="rp-zoom-toggle" />

  <label for="zoom-edit-sub-step3">
    <img class="rp-zoom-img" src="https://files.readme.io/322092c-edit_-_step_3.png" alt="Ramp pricing editor showing interval options" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-edit-sub-step3" class="rp-zoom-overlay">
    <img src="https://files.readme.io/322092c-edit_-_step_3.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Apply the changes</h4><p>Click <strong>Apply Changes</strong> to update the pricing schedule. If you modified the current billing period's price, a prorated invoice is generated.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-edit-sub-step4" class="rp-zoom-toggle" />

  <label for="zoom-edit-sub-step4">
    <img class="rp-zoom-img" src="https://files.readme.io/eb31281-edit_-_step_4.png" alt="Updated pricing schedule after applying changes" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-edit-sub-step4" class="rp-zoom-overlay">
    <img src="https://files.readme.io/eb31281-edit_-_step_4.png" alt="" />
  </label>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Save the subscription</h4><p>Click <strong>Save</strong> on the subscription edit form to apply all changes.</p></div>
  </div>
</div>

<span class="rp-zoom">
  <input type="checkbox" id="zoom-edit-sub-step5" class="rp-zoom-toggle" />

  <label for="zoom-edit-sub-step5">
    <img class="rp-zoom-img" src="https://files.readme.io/929dcb7-edit_-_step_5.png" alt="Saved subscription with updated ramp pricing schedule" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <label for="zoom-edit-sub-step5" class="rp-zoom-overlay">
    <img src="https://files.readme.io/929dcb7-edit_-_step_5.png" alt="" />
  </label>
</span>

# Migrate existing subscribers

If you're rolling out ramp pricing across your existing subscriber base, use the approach that fits your situation.

## New subscribers

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create ramp-priced plans</h4><p>Set up new ramp-priced plans for new subscribers.</p></div>
  </div>

  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Offer them at sign-up</h4><p>Use these plans for new subscription sign-ups so new subscribers get automatic price changes from day one — no manual workarounds needed.</p></div>
  </div>
</div>

## Existing subscribers

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create ramp-priced plans</h4><p>Set up new ramp-priced plans to migrate existing subscribers to.</p></div>
  </div>

  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Move subscribers via the API</h4><p>Use the subscription change <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_subscription_change" target="_blank">endpoint</a> to shift existing subscribers to the new ramp-priced plan. The subscription adopts the base ramp schedule from the plan, and you can then modify the pricing schedule per-subscription as needed.</p></div>
  </div>
</div>
