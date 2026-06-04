---
title: Coupons & discounts
excerpt: >-
  Create and manage coupons and discounts in Recurly — configure discount types,
  duration, redemption rules, and eligible plans or items to run targeted
  promotions for your subscribers.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  image: https://files.readme.io/e9ce049-Screenshot_2.png
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">
    Coupons and discounts give you flexible tools to reduce prices for subscribers — automatically applied by you or redeemed via a code at checkout. Use them to run promotions, reward loyalty, and drive new signups across any plan or billing cycle.
  </div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#creating-a-coupon"><span class="rp-toc-num">3</span>Creating a coupon</a>
    <a class="rp-toc-pill" href="#types-of-discounts"><span class="rp-toc-num">4</span>Types of discounts</a>
    <a class="rp-toc-pill" href="#discount-duration"><span class="rp-toc-num">5</span>Discount duration</a>
    <a class="rp-toc-pill" href="#applying-a-coupon"><span class="rp-toc-num">6</span>Applying a coupon</a>
    <a class="rp-toc-pill" href="#editing-and-removing-coupons"><span class="rp-toc-num">7</span>Editing and removing coupons</a>
    <a class="rp-toc-pill" href="#expiration-and-restoration"><span class="rp-toc-num">8</span>Expiration and restoration</a>
    <a class="rp-toc-pill" href="#reporting-and-analysis"><span class="rp-toc-num">9</span>Reporting and analysis</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">10</span>FAQs</a>
  </div>
</div>

# Definition

<div class="rp-definition">
  <strong>Discounts</strong> are price reductions you apply automatically to a product or service — no action required from the subscriber. <strong>Coupons</strong> are codes subscribers enter at checkout to receive a price reduction. Both tools use the same underlying configuration in Recurly, and throughout this page "apply the discount" refers to both scenarios.
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Drive conversions and revenue</strong>
    <span>Run targeted promotions that attract new subscribers and convert trial users into paying customers.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-heart" aria-hidden="true"></i></div>
    <strong>Reward loyal customers</strong>
    <span>Offer exclusive discounts to your most valuable subscribers to build long-term loyalty and reduce churn.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-bar" aria-hidden="true"></i></div>
    <strong>Strategic flexibility and insights</strong>
    <span>Tailor promotions to specific plans, items, or billing cycles — then analyze redemption data to refine your strategy.</span>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Prerequisites</strong>
  You'll need at least one subscription plan configured in your Recurly site. To allow coupon redemption on hosted payment pages, enable coupons in your Checkout or Hosted Page Settings.
</div>

<div class="rp-callout rp-callout-important">
  <strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Limitations</strong>
  Once a coupon is created, the following attributes cannot be edited: coupon code, discount type, duration, eligible plans, eligible items, and discount level. Additionally: free trial coupons cannot be applied to an existing account (only at subscription creation); coupons cannot be applied alongside "On next renewal" subscription changes; a fixed amount discount that exceeds eligible charges does not carry over to future invoices; percentage discounts never apply to plan setup fees; and coupons cannot retroactively discount an existing invoice.
</div>

# Creating a coupon

## Coupon fields

Before building a coupon, here's what each field in the creation form does.

<table class="rp-params">
  <tbody>
    <tr class="rp-thead-row">
      <td>Field</td>
      <td>Description</td>
    </tr>
    <tr>
      <td>Internal name</td>
      <td>Identifies the coupon campaign internally. Not shown to subscribers unless exposed via API or email. Use a descriptive name for easy reference.</td>
    </tr>
    <tr>
      <td>Code type</td>
      <td><strong>Single code</strong> — one code reusable multiple times based on redemption settings. <strong>Bulk unique codes</strong> — a set of one-time-use codes generated in bulk, ideal for personalized offers. See <a href="https://docs.recurly.com/docs/bulk-unique-coupons" target="_blank">bulk unique codes</a> for details.</td>
    </tr>
    <tr>
      <td>Coupon code</td>
      <td>Supports alphanumeric characters, dashes (-), underscores (_), and plus signs (+). A code can be reused only after the previous coupon using it has expired or reached its redemption limit.</td>
    </tr>
    <tr>
      <td>Type of discount</td>
      <td>Fixed amount, percentage, or free trial. Fixed amount coupons support multi-currency — specify a different amount for each currency you accept.</td>
    </tr>
    <tr>
      <td>Duration</td>
      <td>How long the discount applies after redemption: forever, single use, or limited time (days, weeks, or months).</td>
    </tr>
    <tr>
      <td>Maximum redemptions</td>
      <td>Total number of times the coupon can be redeemed across all accounts. Leave unlimited or set a cap.</td>
    </tr>
    <tr>
      <td>Redemptions per account</td>
      <td>How many times a single account can redeem the coupon — once, unlimited, or a specific number.</td>
    </tr>
    <tr>
      <td>Redeem by date</td>
      <td>Optional expiration date. After this date the coupon can no longer be redeemed.</td>
    </tr>
    <tr>
      <td>Eligible charges</td>
      <td>Which charge types the coupon can discount: recurring charges (plan fees, add-ons, setup fees), one-time charges only, or both.</td>
    </tr>
    <tr>
      <td>Eligible plans</td>
      <td>Which subscription plans qualify for the discount. Defaults to all plans but can be restricted to specific ones.</td>
    </tr>
    <tr>
      <td>Eligible items</td>
      <td>Which catalog items qualify for the discount. Defaults to all items but can be restricted to specific ones.</td>
    </tr>
    <tr>
      <td>Discount level</td>
      <td><strong>Account level</strong> — applies across all eligible subscriptions on the account. <strong>Subscription level</strong> — tied to a specific subscription only.</td>
    </tr>
    <tr>
      <td>Payment page description</td>
      <td>Shown to subscribers when they redeem the coupon on your checkout page, hosted payment page, or via API. Up to 255 characters.</td>
    </tr>
    <tr>
      <td>Invoice description</td>
      <td>Appears in the "Discounts applied" section on the invoice. Not applicable to free trial coupons, which don't provide a monetary discount.</td>
    </tr>
  </tbody>
</table>

## Step-by-step: create a new coupon

<span id="rp-close"></span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div>
      <h4>Navigate to Coupons</h4>
      <p>Go to <strong>Configuration</strong> and click <strong>Coupons</strong>.</p>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/8d4e1fda7827d03b8f9d95d4ab67e4911db8cc092db4072c44c08d0f83f7607a-image.png" alt="Configuration menu with Coupons highlighted" class="rp-zoom-img" />
  </a>
  <a id="zoom-8d4e1fd" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/8d4e1fda7827d03b8f9d95d4ab67e4911db8cc092db4072c44c08d0f83f7607a-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div>
      <h4>Click New Coupon</h4>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/6eb6423097ca5013a67c2465b02c775705143514fb838a48b056ade1f7eb33a8-image.png" alt="New Coupon button on the Coupons list page" class="rp-zoom-img" />
  </a>
  <a id="zoom-6eb6423" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/6eb6423097ca5013a67c2465b02c775705143514fb838a48b056ade1f7eb33a8-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div>
      <h4>Enter an internal name</h4>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/2fef3df53f39b9e4fa4010ab5f7558d34ea3d236ba085162288d6b364d7c1ece-image.png" alt="Internal name field in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-2fef3df" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/2fef3df53f39b9e4fa4010ab5f7558d34ea3d236ba085162288d6b364d7c1ece-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div>
      <h4>Select a code type</h4>
      <p>Choose <strong>Single code</strong> or <strong>Bulk unique codes</strong>.</p>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/319f342ec6bdb8fbe9d15e4d3ae1fa1ab46ffc1b43bba9e5dd664a8662b4f8a5-image.png" alt="Code type selection in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-319f342" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/319f342ec6bdb8fbe9d15e4d3ae1fa1ab46ffc1b43bba9e5dd664a8662b4f8a5-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div>
      <h4>Choose a discount type</h4>
      <p>Select <strong>Percentage</strong>, <strong>Fixed amount</strong>, or <strong>Free trial</strong>.</p>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/4adaab2597af8e79038a3fbe21b7523378bf990bf8d463e6629204fa46991452-image.png" alt="Discount type selection in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-4adaab2" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/4adaab2597af8e79038a3fbe21b7523378bf990bf8d463e6629204fa46991452-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div>
      <h4>Set the coupon duration</h4>
      <p>Choose <strong>Single use</strong>, <strong>Forever</strong>, or <strong>Limited time</strong> (specify days, weeks, or months).</p>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/552c773229720e3d71d8d5ebff6867ba6faadb03b86946d7c560a88745ec95a5-image.png" alt="Duration options in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-552c773" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/552c773229720e3d71d8d5ebff6867ba6faadb03b86946d7c560a88745ec95a5-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div>
      <h4>Configure redemption rules</h4>
      <p>Set maximum redemptions, redemptions per account, and an optional redeem-by date.</p>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/e301291244dce72198845b003186c2a73dcd1051f15e07d4c086fc98c1908af8-image.png" alt="Redemption rules fields in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-e301291" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/e301291244dce72198845b003186c2a73dcd1051f15e07d4c086fc98c1908af8-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div>
      <h4>Define eligible charges, plans, and items</h4>
    </div>
  </div>
</div>

<span class="rp-zoom">
  <a class="rp-zoom-label" href="#rp-close">
    <img src="https://files.readme.io/75fef086e8d7aee54cd6470171ed8a5d706899f64a1fdfbeaa47f1e7a93cb551-image.png" alt="Eligible charges, plans, and items fields in the coupon creation form" class="rp-zoom-img" />
  </a>
  <a id="zoom-75fef08" class="rp-zoom-overlay" href="#rp-close">
    <img src="https://files.readme.io/75fef086e8d7aee54cd6470171ed8a5d706899f64a1fdfbeaa47f1e7a93cb551-image.png" alt="" />
  </a>
</span>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div>
      <h4>Add descriptions (optional)</h4>
      <p>Optionally enter a payment page description and/or invoice description.</p>
    </div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div>
      <h4>Click Create coupon</h4>
      <p>The discount will automatically appear on the invoice when it's generated.</p>
    </div>
  </div>
</div>

# Types of discounts

## Percentage discounts

A percentage discount applies the same rate to each eligible charge on the invoice. Percentage discounts never apply to plan setup fees.

**Example:** A 10% discount on a plan with a $50 setup fee, $15 plan fee, and $7 add-on:

<table class="rp-pm-table">
  <tbody>
    <tr class="rp-thead-row">
      <td>Charge</td>
      <td>Amount</td>
      <td>Discounted?</td>
      <td>Discount applied</td>
    </tr>
    <tr>
      <td>Setup fee</td>
      <td>$50.00</td>
      <td>No</td>
      <td>—</td>
    </tr>
    <tr>
      <td>Plan fee</td>
      <td>$15.00</td>
      <td>Yes</td>
      <td>($1.50)</td>
    </tr>
    <tr>
      <td>Add-on</td>
      <td>$7.00</td>
      <td>Yes</td>
      <td>($0.70)</td>
    </tr>
    <tr>
      <td><strong>Total discount</strong></td>
      <td></td>
      <td></td>
      <td><strong>($2.20) — payable: $69.80</strong></td>
    </tr>
  </tbody>
</table>

## Fixed amount discounts

A fixed amount discount is distributed across eligible charges starting with the first subscription line item — typically the setup fee. If the discount exceeds total eligible charges, the remaining balance is not returned or carried to future invoices.

One-time charges appear on the invoice before subscription charges but are discounted _after_ them. If the fixed amount discount is less than total subscription charges, one-time charges won't receive any discount.

To target only a setup fee: create a single-use coupon with a fixed amount equal to or less than the setup fee — it will apply there before reaching other charges.

**Example:** A $20 discount on a plan with a $15 plan fee and $7 add-on:

<table class="rp-pm-table">
  <tbody>
    <tr class="rp-thead-row">
      <td>Charge</td>
      <td>Amount</td>
      <td>Discount applied</td>
    </tr>
    <tr>
      <td>Plan fee</td>
      <td>$15.00</td>
      <td>($15.00) — fully discounted</td>
    </tr>
    <tr>
      <td>Add-on</td>
      <td>$7.00</td>
      <td>($5.00) — remaining $5 of discount applied</td>
    </tr>
    <tr>
      <td><strong>Total discount</strong></td>
      <td></td>
      <td><strong>($20.00) — payable: $2.00</strong></td>
    </tr>
  </tbody>
</table>

## Free trial coupons

Free trial coupons let you offer a custom trial length that differs from your plan's standard trial period. The trial starts on the day the subscription is created. Because free trial coupons don't provide a monetary discount, they don't appear on any invoices.

# Discount duration

<table class="rp-pm-table">
  <tbody>
    <tr class="rp-thead-row">
      <td>Duration</td>
      <td>Behavior</td>
    </tr>
    <tr>
      <td>Forever</td>
      <td>The discount applies indefinitely for as long as the subscription is active.</td>
    </tr>
    <tr>
      <td>Single use</td>
      <td>The discount applies to one invoice only.</td>
    </tr>
    <tr>
      <td>Limited time</td>
      <td>The discount applies for a defined period — a specified number of days, weeks, months, or years. All invoices generated within that period receive the discount. Recurly recommends matching the period to the billing cycle of the eligible plans. Note: limited-time coupons expire automatically one hour before the anniversary of their redemption date.</td>
    </tr>
  </tbody>
</table>

# Applying a coupon

## During a purchase

Subscribers can enter a coupon code at checkout via your hosted payment page, your own checkout page using Recurly.js or the API, or the Recurly UI when adding a subscription to an existing account.

<div class="rp-list">
  <ul>
    <li>The purchase must include charges eligible for the discount — a coupon for Plan B won't apply during signup for Plan A.</li>
    <li>If the subscription creation fails due to a declined transaction, the coupon won't be applied.</li>
    <li>If only one active coupon is allowed per account, a new coupon replaces any existing one.</li>
    <li>If multiple active coupons are allowed, the new code is added and applied after existing discounts.</li>
    <li>Subscription-level coupons redeemed at subscription creation are automatically tied to that subscription.</li>
    <li>Account-level coupons apply to the new subscription and any future subscriptions on the account.</li>
  </ul>
</div>

To pre-populate a coupon code on your hosted payment page, append this URL parameter: `?subscription[coupon_code]=10off`

<div class="rp-callout rp-callout-note">
  <strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>
  Coupons cannot currently be applied to existing accounts through hosted account management pages. To request this capability, submit a <a href="https://support.recurly.com/" target="_blank">support ticket</a>.
</div>

## During an upgrade or downgrade

You can apply a coupon when upgrading or downgrading a subscription so the discount applies to the updated invoice. Keep in mind:

<div class="rp-list">
  <ul>
    <li>The eligible charges must include the new plan.</li>
    <li>Coupons cannot be applied with "On next renewal" changes.</li>
    <li>A plan, quantity, or price change must be part of the update — the coupon cannot be the only change.</li>
  </ul>
</div>

## Directly on an account

To discount the next invoice for an existing subscription or a one-time charge, apply the coupon directly to the account via **Manage Coupons** on the account page in the Recurly UI, or via the API.

# Editing and removing coupons

## Editing an existing coupon

Go to **Configuration > Coupons**, select the coupon, and click **Edit**. The following fields can be modified after a coupon is created:

<div class="rp-list">
  <ul>
    <li>Internal name</li>
    <li>Maximum redemptions</li>
    <li>Redeem by date</li>
    <li>Redemptions per account</li>
    <li>Payment page description</li>
    <li>Invoice description (not applicable to free trial coupons)</li>
  </ul>
</div>

<div class="rp-callout rp-callout-note">
  <strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>
  Changes only affect coupons redeemed after the update is saved. Existing redemptions are not impacted.
</div>

## Removing a coupon from an account

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div>
      <h4>Go to Coupon Redemptions</h4>
      <p>Navigate to the <strong>Coupon Redemptions</strong> page for the subscriber's account.</p>
    </div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div>
      <h4>Locate the coupon</h4>
      <p>In the "Redeemed on account" table, find the coupon you want to remove.</p>
    </div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div>
      <h4>Remove and confirm</h4>
      <p>Select the coupon and follow the prompts. Removing a coupon stops the discount from applying to future invoices — already-issued invoices are unaffected and the subscriber will be charged the regular price on their next billing cycle.</p>
    </div>
  </div>
</div>

# Expiration and restoration

## Expiring a coupon early

Go to the coupon's overview page and select **Expire early**. The coupon expires immediately. Subscribers who have already redeemed it are not affected.

## Automatic expiration

Coupons expire automatically when they reach their redeem-by date or maximum redemptions limit.

## Reusing a coupon code

Once a coupon expires or reaches its redemption limit, the code becomes available to reuse when creating a new coupon.

## Restoring an expired coupon

You can restore an expired coupon to make it redeemable again. If it expired due to reaching its redemption limit or redeem-by date, update those fields before restoring.

# Reporting and analysis

Track and analyze coupon performance from the **Exports** page under **Reports**.

<table class="rp-gw-table">
  <tbody>
    <tr class="rp-thead-row">
      <td>Export</td>
      <td>What it shows</td>
    </tr>
    <tr>
      <td>Coupons</td>
      <td>All coupons on your site, their rules, and creation or expiration dates.</td>
    </tr>
    <tr>
      <td>Coupon Redemptions</td>
      <td>Who redeemed coupons, when, and how much discount was applied.</td>
    </tr>
    <tr>
      <td>Invoices – Summary</td>
      <td>Which coupons were applied to each invoice (see the <code>coupon_code</code> column).</td>
    </tr>
    <tr>
      <td>Invoices – Line Items</td>
      <td>Which coupons were applied to each line item and the total discount.</td>
    </tr>
    <tr>
      <td>Invoices – Line Items – Coupons</td>
      <td>Specific discounts per coupon per line item. Only visible when Multiple Coupons Per Account is enabled.</td>
    </tr>
  </tbody>
</table>

# FAQs

<Accordion title="What happens with discounts when a plan includes a free trial and a setup fee?">
  Discounts are not applied to a free trial invoice unless there's a setup fee and the coupon is a fixed amount. In that case, Recurly recommends setting the coupon duration to "Limited time" for one month rather than "Single use." This ensures both the setup fee and the first paid month receive the discount.
</Accordion>

<Accordion title="How does coupon accounting work in Recurly?">
  Both percentage and fixed amount coupons are applied to charge line items before tax is calculated. Credits are applied after coupons have already discounted the charges. Coupons apply to the next invoice created after redemption — they can't retroactively adjust an existing invoice. To correct an already-issued invoice, you can issue a partial refund equal to the discount amount, or do a full refund, redeem the coupon, and reissue the invoice. Free trial coupons don't offer a monetary discount and don't appear on any invoices.
</Accordion>

<Accordion title="Can subscribers have multiple active coupon redemptions on their account?">
  Yes — you can allow multiple active coupon redemptions per account, which can result in multiple discounts on a single invoice or line item. Settings for this feature are adjusted on the coupon configuration page. See the <a href="https://docs.recurly.com/recurly-subscriptions/v2021-02-25/reference/list_coupons" target="_blank">Multiple Coupons Per Account documentation</a> for details on how stacked discounts are applied.
</Accordion>

<Accordion title="How do I create a coupon that discounts across several billing cycles?">
  Set the duration to "Limited time" and configure the period to match your plan's billing cycle. Keep in mind that if the discount is a fixed amount and eligible charges are less than the discount on any given invoice, the remaining balance won't carry forward.
</Accordion>

<Accordion title="Where can I find coupon redemption data?">
  Every coupon has a Redemptions table showing all accounts that have redeemed it and the total discount applied. For bulk coupons, a "Not redeemed" table shows all unused unique codes. You can expire unredeemed codes early — expired codes appear at the end of the table.
</Accordion>

<br />
