---
title: Postpone subscription
excerpt: >-
  Learn how to extend or shorten a subscription's current billing cycle by
  changing the next bill date using the Admin Console or API.
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
  <div class="rp-overview">Sometimes a billing date just needs to shift — a customer's anniversary has moved, a special arrangement was made, or an onboarding timeline didn't line up. Postponing a subscription lets you adjust the current billing cycle forward or backward without touching the plan, price, or subscription terms. It's a lightweight, targeted change that works through both the Admin Console and the API.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">4</span>FAQs</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Postpone subscription feature lets you extend or shorten the active billing period for a specific subscription by setting a new next bill date. No invoice is generated for any added time, and all future billing dates permanently shift to align with the new date from that point forward.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Billing flexibility</strong>
    <span>Adjust billing cycles on the fly to meet both business requirements and individual customer needs without disrupting the subscription itself.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-dollar-to-slot" aria-hidden="true"></i></div>
    <strong>Cost-effective adjustments</strong>
    <span>No need to create new plans or restructure subscriptions — a single postpone aligns the billing date to the target date cleanly and quickly.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Better customer experience</strong>
    <span>Offer tailored billing accommodations without interrupting service, helping customers feel in control of their subscription.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gear" aria-hidden="true"></i></div>
    <strong>Flexible implementation</strong>
    <span>Supported in both the Admin Console and the API, so your team can apply postponements however fits your workflow best.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-heart" aria-hidden="true"></i></div>
    <strong>Retention-friendly</strong>
    <span>Handle short-term billing requests gracefully — meeting customers where they are increases loyalty without requiring a cancellation and re-signup.</span>
  </div>
</div>

# Key details

Postponing a subscription changes the subscriber's next bill date. No further subscription invoices are generated until that postponed date is reached. Importantly, the change is permanent going forward — all future billing dates shift to align with the new date.

**Example:** A yearly subscription running from May 15, 2016, through May 20, 2017, postponed to December 10, 2016, will now cover May 15 – December 10, 2016. The next billing cycle then runs December 10, 2016 – December 10, 2017.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Proration warning</strong>If you make an immediate subscription change after postponing, the system treats the extended period as already paid. This means the proration credit may exceed 100% of the per-unit price, resulting in credits and charges that surpass the original amount. Plan any post-postpone changes carefully.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Calendar billing</strong>Postponing one subscription on an account doesn't affect other subscriptions on that account. If all subscriptions bill on the 15th of each month, changing one won't shift the rest.</div>
</div>

## Postpone via Admin Console

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the customer account</h4><p>Navigate to the relevant customer's account in the Admin Console.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the subscription</h4><p>View the subscription you want to postpone. Locate the <strong>Current period</strong> field in the subscription details.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Select Change</h4><p>Click the <strong>Change</strong> link next to <strong>Current period</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Set the new bill date</h4><p>Enter the date you'd like the current period to end. This becomes the new next bill date.</p></div>
  </div>
</div>

## Postpone via API

Use the appropriate call based on your API version:

- **V2 API** — Use the <a href="https://dev.recurly.com/docs/postpone-subscription" target="_blank">Postpone Subscription</a> call.
- **V3 API** — Use the <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/modify_subscription" target="_blank">Modify Subscription</a> call.

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Need to skip billing cycles instead?</strong>If your goal is to pause billing for several cycles without permanently shifting the billing date, use <a href="https://docs.recurly.com/docs/pause-subscription" target="_blank">Pause subscription</a> instead.</div>
</div>

# FAQs

<Accordion title="Does postponing one subscription affect other subscriptions on the same account?">
  No. Postponing a single subscription only changes the next bill date for that specific subscription. Other subscriptions on the account — even those that share the same billing date — are unaffected.
</Accordion>

<Accordion title="Is the customer charged for any extra time added by postponing?">
  No. Recurly doesn't invoice the customer for any additional time added through a postpone. However, if you make an immediate change to the subscription after postponing, the system assumes the customer was already charged for the extended period and will credit them accordingly — which can result in proration exceeding 100%.
</Accordion>

<Accordion title="Is the billing date change permanent?">
  Yes. When you postpone a subscription, all future billing dates shift to align with the new date. This isn't a one-time skip — it's a permanent adjustment to the billing cycle going forward.
</Accordion>

<Accordion title="What's the difference between postponing and pausing a subscription?">
  Postponing changes the current billing period's end date, permanently shifting all future billing dates to align with the new one. Pausing suspends billing for a set number of cycles without altering the underlying billing date. Use pause when you want to skip cycles and return to the original schedule; use postpone when you want to change the schedule itself.
</Accordion>

<br />
