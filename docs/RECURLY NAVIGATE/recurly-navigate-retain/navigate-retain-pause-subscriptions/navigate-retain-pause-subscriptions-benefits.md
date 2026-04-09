---
title: Pause API Test - Benefits
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Pause, Not Cancel</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: none; padding: 32px 16px; }.pv-panel.active { display: block; }</style></head><body><div class="pv-bar"><button class="pv-tab active" data-tab="pv-0">1. What Is It?</button><button class="pv-tab" data-tab="pv-1">2. Why Use It?</button><button class="pv-tab" data-tab="pv-2">3. Things to Consider</button><button class="pv-tab" data-tab="pv-3">4. When Not to Use It</button><button class="pv-tab" data-tab="pv-4">5. How to Enable It</button><button class="pv-tab" data-tab="pv-5">6. Tracking Impact</button><button class="pv-tab" data-tab="pv-6">7. Pitch to Leadership</button></div><div id="pv-0" class="pv-panel active"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <!-- 1. HERO SECTION -->
  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of forcing a binary stay-or-cancel decision.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
  </div>

  <!-- 2. TAB NAVIGATION -->
  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1" class="is-active">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <!-- 3. SECTION HEADER & CONTENT -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- package-check.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package-check" style="width:28px;height:28px;"></div>
      <div>
        <h2>What Is Pause Subscriptions?</h2>
        <p>Understand how Recurly's Pause feature works and why it's a powerful retention tool in your churn-reduction toolkit.</p>
      </div>
    </div>

    <!-- Intro Card -->
    <div class="rc-card">
      <h3>The Pause Concept in a Nutshell</h3>
      <p>Recurly's Pause Subscriptions feature lets you temporarily halt a subscriber's billing cycle without canceling their subscription. Instead of losing a subscriber entirely when they need a break—whether due to travel, seasonal usage patterns, budget constraints, or simply wanting time away—you give them a middle option. The subscription enters a paused state: no invoices are generated, no charges occur, and the subscriber's account remains intact. When the pause period ends (or the subscriber decides to come back early), billing resumes automatically on the next renewal date.</p>
      <p>Think of it this way: cancellation is a door that's hard to reopen. A pause is a bookmark—the subscriber's place is held, their payment method stays on file, and their return path is frictionless. This distinction has a profound impact on your retention metrics and lifetime revenue per subscriber.</p>
    </div>

    <!-- How It Works - Steps -->
    <div class="rc-subhead">How the Pause Lifecycle Works</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Pause Is Initiated</h4>
          <p>A pause can be triggered in multiple ways: by the subscriber through a self-service hosted page, by your team through the Recurly Admin Console, or programmatically via the Recurly API. You specify a <strong>remaining billing cycles</strong> value, which tells Recurly how many renewal periods to skip before automatically resuming. For example, setting this to 2 on a monthly plan means the subscriber skips two months of billing.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Current Period Completes</h4>
          <p>Importantly, the pause does not take effect immediately mid-cycle. The subscriber continues to have access through the end of their current billing period. Once that period expires, the subscription transitions into the <strong>paused</strong> state. This means you never have to issue partial refunds or prorate the current term—the subscriber gets the full value of what they've already paid for.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Subscription Enters Paused State</h4>
          <p>While paused, Recurly will not generate any invoices for that subscription. The subscriber's account, plan details, add-ons, coupon redemptions, and stored payment methods all remain intact. No dunning cycles are triggered. The subscription simply "sleeps" until the remaining billing cycles count reaches zero.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Automatic Resumption</h4>
          <p>When the specified number of paused cycles have elapsed, Recurly automatically resumes the subscription. A new invoice is generated, the stored payment method is charged, and the subscriber's billing cycle continues as if they'd never left. No manual intervention is required from your team or the subscriber. Alternatively, the subscriber (or your team) can resume the subscription early at any time before the pause period ends.</p>
        </div>
      </div>
    </div>

    <!-- Pause vs Cancel Comparison -->
    <div class="rc-subhead">Pause vs. Cancel: A Critical Distinction</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <h4>⏸️ Pause</h4>
        <p>Billing stops temporarily. Account stays active. Payment method retained. Automatic resumption. Subscriber returns with zero friction. Plan, add-ons, and coupons preserved.</p>
      </div>
      <div class="rc-wi">
        <h4>❌ Cancel</h4>
        <p>Subscription terminates. Subscriber must re-sign up manually. Payment method may be lost. Reacquisition cost is high. Previous plan terms and promotional pricing may not be recoverable.</p>
      </div>
    </div>

    <div class="rc-card">
      <p>The business impact of this distinction is significant. Industry data consistently shows that reactivating a canceled subscriber costs 5–7x more than retaining one who paused. When a subscriber cancels, they enter your win-back funnel—competing with every other brand vying for their attention and wallet. When they pause, they've made a conscious decision to <em>come back</em>. Their intent to return is built into the action itself. That's why pause is not just a feature—it's a retention strategy.</p>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p>Recurly's Pause feature is most powerful when integrated into your cancel-save flows. When a subscriber clicks "Cancel," present pause as an alternative before they finalize. This intercept can convert a significant percentage of would-be cancellations into temporary pauses—subscribers who come back automatically without any additional acquisition spend on your part.</p>
    </div>

    <!-- Key Technical Details -->
    <div class="rc-subhead">Key Technical Details</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <h4>API & Console</h4>
        <p>Pause can be managed via the Recurly API (PUT request with remaining_pause_cycles) or directly in the Admin Console UI.</p>
      </div>
      <div class="rc-wi">
        <h4>Webhooks</h4>
        <p>Recurly fires subscription state change webhooks when a subscription is paused and when it resumes, so your systems stay in sync.</p>
      </div>
      <div class="rc-wi">
        <h4>Hosted Pages</h4>
        <p>Subscribers can self-service pause through Recurly-hosted account management pages, reducing support ticket volume.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important: Pause Is Not the Same as a Trial Extension</strong>
      <p>A paused subscription does not extend a trial period. If the subscriber is still in a free trial when pause is initiated, the trial will end as scheduled and the pause will apply to future paid billing cycles. Make sure your team understands this distinction to set accurate expectations with subscribers.</p>
    </div>

    <!-- Quick Concepts Checklist -->
    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Concepts to Remember</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c1">
        <label for="c1">Pause halts billing but keeps the subscription record fully intact</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c2">
        <label for="c2">The current billing period completes before the pause takes effect</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c3">
        <label for="c3">You set the number of billing cycles to skip (remaining_pause_cycles)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c4">
        <label for="c4">Resumption is automatic—no action needed from subscriber or your team</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c5">
        <label for="c5">Subscribers (or your team) can resume early at any time</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c6">
        <label for="c6">Add-ons, coupons, and payment methods are all preserved during pause</label>
      </div>
    </div>

  </div>

  <!-- 5. BACK/NEXT NAVIGATION -->
  <div class="rc-sec-nav">
    <a href="#" class="rc-btn-prev rc-btn-disabled">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2" class="rc-btn-next">Next →</a>
  </div>

  <!-- 6. ADDITIONAL RESOURCES -->
  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Pause Subscriptions Video Walkthrough</a>
  </div>

</div></div>
<div id="pv-1" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn how Recurly's Pause subscriptions feature reduces voluntary churn by giving subscribers a reason to stay instead of leave.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2" class="is-active">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- lightbulb-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>Why Use It?</h2>
        <p>The strategic case for offering pause as a retention lever — backed by behavioral science, industry benchmarks, and real business impact.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Core Problem: Cancellation Is a One-Way Door</h3>
      <p>When a subscriber clicks "cancel," they cross a psychological threshold that's extremely difficult to reverse. Research consistently shows that re-acquiring a churned customer costs five to seven times more than retaining an existing one. Even with the best win-back campaigns — emails, discount offers, retargeting ads — only 10-20% of churned subscribers ever return. The rest are gone for good.</p>
      <p>The root issue is that most cancellation flows present a binary choice: stay and pay, or leave entirely. But subscribers' reasons for wanting to cancel are rarely permanent. Financial constraints, travel schedules, seasonal usage patterns, content fatigue — these are all temporary states. By forcing a permanent decision during a temporary situation, businesses inadvertently lose subscribers who would have otherwise returned on their own.</p>
      <p>Pause bridges this gap. It gives subscribers a middle option that respects their current needs while preserving the relationship, the stored payment method, the plan configuration, and the behavioral habit of being a subscriber. When the pause ends, the subscription resumes automatically — no friction, no re-onboarding, no re-entering credit card details.</p>
    </div>

    <div class="rc-subhead">The Business Case by the Numbers</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet-01" style="width:28px;height:28px;">
        <h4>Lower CAC Pressure</h4>
        <p>Retaining a subscriber who pauses eliminates the need to spend acquisition dollars replacing them. Every saved subscriber directly improves your CAC-to-LTV ratio.</p>
      </div>
      <div class="rc-wi">
        <!-- bar-chart-11.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="bar-chart-11" style="width:28px;height:28px;">
        <h4>Higher Lifetime Value</h4>
        <p>A subscriber who pauses for one month then resumes for 12+ more months generates far more revenue than one who cancels and never returns.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart-hand" style="width:28px;height:28px;">
        <h4>Brand Goodwill</h4>
        <p>Offering pause signals that you value your subscribers as people, not just revenue sources. This builds trust and generates positive word-of-mouth referrals.</p>
      </div>
    </div>

    <div class="rc-subhead">Why Pause Outperforms Other Retention Tactics</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Pause vs. Discount Offers</h4>
          <p>Discounts erode your average revenue per user (ARPU) and train subscribers to expect future price reductions before every renewal. They also don't address the underlying reason someone wants to leave — if a subscriber is traveling for three months, a 20% discount doesn't solve the problem. Pause addresses the root cause (temporary non-use) without devaluing your product. When the subscriber returns, they return at full price, preserving ARPU integrity.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Pause vs. Plan Downgrade</h4>
          <p>Downgrading a subscriber to a cheaper plan creates a different problem: the subscriber often never upgrades back. You've permanently reduced their revenue contribution. Additionally, the overhead of managing multiple plan tiers — and the communication complexity of encouraging re-upgrades — adds operational cost. Pause avoids this entirely by keeping the subscriber on their existing plan, just temporarily suspended.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Pause vs. Win-Back Campaigns</h4>
          <p>Win-back campaigns target subscribers after they've already left. At that point, you're fighting inertia, forgetfulness, and the fact that the subscriber has likely already found an alternative. Pause intervenes before the relationship ends. The subscriber's account, preferences, and payment method remain intact. There's no re-acquisition funnel to navigate — just an automatic resumption date. The resume rate from pause vastly outperforms win-back conversion rates.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Pause vs. Cancel-Save Flows Alone</h4>
          <p>Cancel-save flows (also called deflection flows) are powerful retention tools — and pause works brilliantly as an offer within them. When a subscriber initiates cancellation and is presented with a pause option as part of the cancel-save flow, you're combining two Recurly retention features for maximum impact. Pause gives your cancel-save flow a compelling, no-cost-to-you offer that doesn't require discounting.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p>The most effective retention strategy isn't choosing between pause and cancel-save flows — it's using them together. Configure your cancel-save flow to present "Pause your subscription" as one of the primary offers when a subscriber tries to cancel. Recurly supports this natively. Merchants who embed pause as a cancel-save offer typically see significantly higher deflection rates compared to discount-only save flows.</p>
    </div>

    <div class="rc-subhead">Who Benefits Most from Pause?</div>

    <div class="rc-2col">
      <div class="rc-card">
        <h3>Seasonal & Lifestyle Businesses</h3>
        <p>Fitness apps, outdoor recreation platforms, and educational services often see predictable usage dips. A language learning app might see subscribers pause during summer vacation. A fitness app might see pauses during holiday travel. These are healthy, expected usage patterns. Without pause, these subscribers cancel — and most never come back because they forget, lose motivation, or find alternatives during the gap. Pause keeps them in your ecosystem through natural usage cycles.</p>
      </div>
      <div class="rc-card">
        <h3>Budget-Sensitive Subscribers</h3>
        <p>Economic uncertainty, unexpected expenses, or month-to-month budget fluctuations cause subscribers to cut discretionary spending. If cancel is the only option, you lose them permanently. But a subscriber who pauses for one or two months during a tight financial period is overwhelmingly likely to resume when their situation stabilizes. For SMB and mid-market merchants especially, preserving these subscribers through temporary financial dips can meaningfully impact monthly recurring revenue (MRR) stability.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>Important: Pause Is a Retention Tool, Not a Revenue Strategy</strong>
      <p>While pause dramatically improves retention metrics and lifetime value, it does temporarily reduce MRR for the pause duration. This is by design — the trade-off of short-term revenue deferral for long-term subscriber preservation is overwhelmingly positive. However, it's important to set expectations with leadership: pause will show a temporary MRR impact that is more than recovered by avoided churn and resumed subscriptions. We'll cover how to frame this in the "Pitch to Leadership" section.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Self-Assessment: Is Pause Right for Your Business?</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c1">
        <label for="c1">Your voluntary churn rate exceeds 5% monthly and you want to reduce it</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c2">
        <label for="c2">Subscribers cite temporary reasons (budget, travel, schedule) in cancellation surveys</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c3">
        <label for="c3">Your product has seasonal or cyclical usage patterns</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c4">
        <label for="c4">Your win-back campaign conversion rates are below 15%</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c5">
        <label for="c5">You're relying heavily on discounts to save cancellations (eroding ARPU)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c6">
        <label for="c6">You want to improve subscriber experience and brand perception</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>The Retention Flywheel Effect</strong>
      <p>Pause doesn't just save individual subscribers — it creates a compounding retention effect. Every subscriber who pauses instead of canceling is one fewer subscriber you need to replace through acquisition spend. This frees up budget to invest in product improvements that reduce churn further, creating a positive feedback loop. Over 12 months, even modest pause adoption rates (5-10% of would-be cancellers choosing pause) can translate into meaningful MRR preservation and a measurably healthier subscriber base.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1" class="rc-btn-prev">&larr; Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3" class="rc-btn-next">Next &rarr;</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">Pause Feature Video Walkthrough</a>
  </div>

</div></div>
<div id="pv-2" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of immediate cancellation.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3" class="is-active">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- lightbulb-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>Things to Consider</h2>
        <p>Before enabling pause, understand the billing mechanics, subscriber experience implications, and strategic decisions that will shape your implementation.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Pause Is a Retention Strategy — Not Just a Feature Toggle</h3>
      <p>Turning on the pause feature in Recurly takes minutes. But deploying it as an effective churn-reduction strategy requires thoughtful planning. A poorly configured pause experience can create confusion for subscribers, complicate your revenue forecasting, or even train users to pause routinely instead of maintaining an active subscription. The considerations below will help you build a pause strategy that genuinely protects subscriber lifetime value rather than simply deferring cancellations.</p>
    </div>

    <div class="rc-subhead">Billing & Revenue Implications</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet-01" style="width:28px;height:28px;">
        <h4>Revenue Deferral</h4>
        <p>While a subscription is paused, no invoices are generated. This means your MRR will decrease during the pause window. Ensure your finance team understands the distinction between "churned revenue" and "paused revenue" so forecasts remain accurate.</p>
      </div>
      <div class="rc-wi">
        <!-- credit-card-refresh.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="credit-card-refresh" style="width:28px;height:28px;">
        <h4>Payment Method Freshness</h4>
        <p>Extended pause periods increase the risk of stored payment methods expiring or being replaced. Recurly's Account Updater helps mitigate this, but cards paused for 3+ months may still encounter declines on resume. Plan your dunning flows accordingly.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠ Revenue Recognition Impact</strong>
      <p>If your business follows ASC 606 or IFRS 15, paused subscriptions can create complexities in revenue recognition. Since no performance obligation is being fulfilled during the pause period, no revenue should be recognized. Work with your finance team to ensure your accounting system correctly handles paused subscription states, especially if you use Recurly's revenue recognition features.</p>
    </div>

    <div class="rc-subhead">Pause Duration Strategy</div>

    <div class="rc-card">
      <h3>How Long Should You Allow Pauses?</h3>
      <p>This is one of the most consequential decisions you'll make. Too short a pause window (e.g., one billing cycle) may frustrate subscribers who need more time away, pushing them toward cancellation anyway. Too long a window (e.g., six months or indefinite) risks subscribers disengaging entirely, making it unlikely they'll return. Industry data suggests that subscribers who pause for more than 90 days resume at significantly lower rates than those pausing for 30–60 days.</p>
      <p>In Recurly, you configure the remaining pause cycles when initiating or modifying a pause. This gives you granular control, but it also means you need a clear internal policy. Consider setting a maximum pause duration and communicating it clearly to subscribers so expectations are aligned from the start.</p>
    </div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Define your maximum pause window</h4>
          <p>Most successful implementations cap pauses at 1–3 billing cycles. For monthly plans, this means 1–3 months. For annual plans, pausing typically doesn't apply (consider a downgrade or plan swap instead). Decide your cap based on your content or service lifecycle — seasonal businesses may allow longer pauses than always-on services.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Decide whether subscribers choose their duration</h4>
          <p>You can offer a fixed pause length ("Pause for 1 month") or let subscribers choose from predefined options ("Pause for 1, 2, or 3 months"). Offering choice increases satisfaction, but a fixed option simplifies operations and gives you more predictable resume rates. Consider A/B testing both approaches.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Set a policy for repeat pauses</h4>
          <p>Can a subscriber pause, resume for one cycle, and then pause again? Without guardrails, some users will "game" the system by essentially paying every other month. Consider implementing a cooldown period — for example, requiring at least two active billing cycles between pauses — or limiting the total number of pauses per year.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with a Re-Engagement Campaign</strong>
      <p>The pause period is not a dead zone — it's a re-engagement opportunity. Use Recurly's webhooks (specifically <code>subscription_paused</code> and <code>subscription_resumed</code>) to trigger email sequences that remind subscribers what they're missing, share new content or features released during their absence, and count down to their resume date. Subscribers who receive at least two touchpoints during a pause period resume at higher rates than those who hear nothing.</p>
    </div>

    <div class="rc-subhead">Subscriber Experience Considerations</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- bell-ringing-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell-ringing-01" style="width:28px;height:28px;">
        <h4>Notification Clarity</h4>
        <p>Subscribers must clearly understand when their pause starts, when billing resumes, and what access they retain (if any) during the pause. Ambiguity leads to disputes and chargebacks.</p>
      </div>
      <div class="rc-wi">
        <!-- package-check.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package-check" style="width:28px;height:28px;">
        <h4>Access During Pause</h4>
        <p>Decide whether paused subscribers retain any service access (e.g., read-only mode, limited content). Partial access can increase resume rates, but some businesses prefer a clean cutoff to reinforce value.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart-hand" style="width:28px;height:28px;">
        <h4>Resume Experience</h4>
        <p>When the pause ends, the subscription resumes automatically. Make sure subscribers understand this and can easily cancel before resume if their situation hasn't changed, to avoid surprise charges.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Access & Entitlement Management</h3>
      <p>One of the most important technical decisions is what happens to service access during a pause. In Recurly, the subscription moves into a <code>paused</code> state, but your application must interpret that state and enforce access rules accordingly. There are three common approaches:</p>
      <p><strong>Full access cutoff:</strong> The subscriber loses all access immediately when the pause begins. This is the simplest to implement and creates the strongest incentive to resume, but may feel punitive to subscribers who are pausing due to financial constraints.</p>
      <p><strong>Degraded access:</strong> The subscriber retains limited functionality — for example, they can view their history or saved preferences but can't access new content. This approach preserves engagement and makes the resume decision feel natural rather than forced.</p>
      <p><strong>Full access until current period ends:</strong> Since the pause takes effect at the next renewal, the subscriber retains full access through the end of their already-paid billing period. This is the default behavior in Recurly and typically the most subscriber-friendly approach.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠ Communicate the Resume Date Clearly</strong>
      <p>One of the most common sources of subscriber frustration is being charged unexpectedly when a pause ends. Always display the exact resume date during the pause flow, in confirmation emails, and in the subscriber's account settings. Consider sending a reminder email 3–5 days before billing resumes. Subscribers who feel informed and in control are less likely to file chargebacks or leave negative reviews.</p>
    </div>

    <div class="rc-subhead">Operational & Integration Considerations</div>

    <div class="rc-card">
      <h3>Downstream System Impact</h3>
      <p>Pausing a subscription in Recurly affects more than billing. Consider how the paused state flows through to your broader tech stack. If you use a CRM like Salesforce or HubSpot, does the subscriber's status update correctly? If you sync with a data warehouse, will paused subscriptions be excluded from active subscriber counts? What about third-party entitlement systems, email platforms, or analytics tools?</p>
      <p>Recurly fires webhooks for pause-related events (<code>subscription_paused</code>, <code>subscription_pause_modified</code>, <code>subscription_resumed</code>), which you can use to keep downstream systems in sync. Map out every system that reads subscription state and ensure each one handles the paused state appropriately before launching the feature to subscribers.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Pre-Launch Readiness Checklist</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c1">
        <label for="c1">Defined maximum pause duration and documented the policy internally</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c2">
        <label for="c2">Decided on repeat-pause guardrails (cooldown period or annual cap)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c3">
        <label for="c3">Determined subscriber access level during the pause period</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c4">
        <label for="c4">Mapped all downstream systems that consume subscription state</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c5">
        <label for="c5">Configured webhook listeners for pause, modify, and resume events</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c6">
        <label for="c6">Created subscriber-facing communications: pause confirmation, mid-pause engagement, and resume reminder emails</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c7">
        <label for="c7">Aligned with finance on how paused revenue is reported in MRR and revenue recognition</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c8">
        <label for="c8">Tested the full pause-to-resume lifecycle in Recurly Sandbox</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Think Like a Cancel-Save Flow</strong>
      <p>Pause is most powerful when positioned as part of a broader cancel-save strategy. Rather than offering pause as a standalone option, present it as the primary alternative during your cancellation flow. When a subscriber clicks "Cancel," surface pause as the first option: "Not ready to commit? Pause your subscription instead and come back when you're ready." This framing leverages loss aversion and significantly increases the likelihood that a subscriber chooses pause over permanent cancellation. Many Recurly merchants see 15–30% of cancellation attempts convert to pauses when pause is presented at the right moment in the cancel flow.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-2" class="rc-btn-prev">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Pause Feature Video Walkthrough</a>
  </div>

</div></div>
<div id="pv-3" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn when the Pause subscriptions feature is the right tool—and when other retention strategies serve you better.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4" class="is-active">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">
        <!-- bell-ringing-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell-ringing-01" style="width:28px;height:28px;">
      </div>
      <div>
        <h2>When Not to Use It</h2>
        <p>Pause is a powerful retention lever, but it's not a universal fix. Understanding when other approaches work better will help you build a more effective churn-reduction strategy.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Pause Is One Tool in a Larger Retention Toolkit</h3>
      <p>Recurly's Pause subscriptions feature is designed for a specific scenario: a subscriber who intends to return but needs temporary relief from billing. It works beautifully in that context. However, not every at-risk subscriber fits that profile. Some subscribers are dissatisfied with your product. Others are looking for a better price. And some have already mentally checked out and simply want to leave cleanly. Offering a pause to these subscribers can feel tone-deaf, create friction, or delay the inevitable—costing you operational overhead without recovering meaningful revenue.</p>
      <p>The key to an effective retention strategy is matching the right intervention to the right reason for leaving. This section helps you identify the scenarios where pause is not the best first response, and points you toward alternatives that Recurly supports—including cancel-save flows, plan downgrades, and targeted promotional offers.</p>
    </div>

    <div class="rc-subhead">Scenarios Where Pause Is the Wrong Move</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>The Subscriber Is Dissatisfied with Your Product</h4>
          <p>When a subscriber is canceling because the product doesn't meet their expectations—whether it's missing features, poor content quality, or a bad user experience—a pause doesn't address the root cause. The subscriber will simply return after the pause period, encounter the same issues, and cancel for good. In this case, you're better off using a cancel-save flow that captures their specific feedback through a cancellation reason survey. This data lets your product team take action, and you can re-engage the subscriber later with a targeted "we've improved" campaign once the issue is resolved.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>The Subscriber Wants a Lower Price, Not a Break</h4>
          <p>Price-sensitive subscribers who feel your service isn't worth the current cost aren't looking to pause—they want a better deal. Offering a pause delays their billing but doesn't change their price perception. When the pause ends and they see the same charge, they'll cancel anyway. A more effective approach is to present a plan downgrade option or a limited-time discount through Recurly's cancel-save flow. You can offer a smaller plan tier, an annual discount, or a promotional coupon that reduces their next few billing cycles. These interventions directly address the price objection while keeping the subscriber active and engaged.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>The Subscriber Has Already Churned Mentally</h4>
          <p>Some subscribers have firmly decided to leave. They've stopped using the product weeks ago, they've already found an alternative, or they simply no longer need the service. For these subscribers, a pause offer can feel manipulative or create the impression that you're making it difficult to leave. This damages your brand trust and can lead to negative reviews or support complaints. The best retention strategy here is a graceful exit: confirm their cancellation, send a warm offboarding email, and set up a win-back campaign for 30, 60, or 90 days later. Sometimes the most retention-positive thing you can do is let someone leave on good terms.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Your Business Model Has High Onboarding Costs</h4>
          <p>If your subscription involves significant per-subscriber costs during active periods—such as dedicated account management, physical inventory allocation, or reserved capacity—a paused subscriber who returns creates a spike in reactivation costs. In these models, it may be more efficient to offer a reduced-service tier rather than a full pause. This keeps the subscriber in a lower-cost state while maintaining some revenue flow, rather than pausing revenue entirely and then absorbing full reactivation costs upon resumption.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Regulatory or Contractual Obligations Prevent It</h4>
          <p>In some industries—particularly those with compliance requirements around continuous service delivery, such as insurance, healthcare, or certain financial services—pausing a subscription may violate regulatory obligations or contractual terms. If your subscribers are required to maintain uninterrupted coverage or access, a pause feature could expose your business to legal risk. Always consult with your legal and compliance teams before enabling pause in regulated verticals. In these cases, alternative retention plays like plan modifications or extended payment terms may be more appropriate.</p>
        </div>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Use Pause as a Dark Pattern</strong>
      <p>If you find that most subscribers who pause end up canceling immediately after resumption, that's a signal that pause is being offered to the wrong audience segment. Subscribers should genuinely intend to come back. Review your pause-to-cancel conversion rate regularly—if it exceeds 40-50%, revisit your cancellation flow targeting logic. A pause that simply delays churn by one billing cycle doesn't improve LTV; it just obscures your true churn rate.</p>
    </div>

    <div class="rc-subhead">Better Alternatives by Cancellation Reason</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet-01" style="width:28px;height:28px;">
        <h4>Price Objection</h4>
        <p>Offer a plan downgrade, promotional discount, or switch to annual billing at a reduced rate through cancel-save flows.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1_bHnEewv-l9uMxpkMdZvgKyKTiGuc4di" alt="message-chat-square" style="width:28px;height:28px;">
        <h4>Product Dissatisfaction</h4>
        <p>Capture detailed feedback via cancellation surveys. Route to customer success for intervention before the subscriber leaves.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1HhXev0Ya9ke3e1IxfytHklXgrvT0taWq" alt="announcement-01" style="width:28px;height:28px;">
        <h4>Competitor Switch</h4>
        <p>Highlight unique value propositions and offer a loyalty incentive. If they leave, trigger a 60-day win-back sequence.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart-hand" style="width:28px;height:28px;">
        <h4>No Longer Needed</h4>
        <p>Allow a graceful exit. Send a warm offboarding email with an easy reactivation link for when their needs change.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Layer Your Cancel-Save Flow Strategically</strong>
      <p>The most effective retention strategies present different offers based on the cancellation reason the subscriber selects. Use Recurly's cancel-save flows to first ask why the subscriber is leaving, then dynamically present the most relevant intervention. Pause should appear as a primary option only when the subscriber selects reasons like "I'll be back later," "traveling," "seasonal use," or "need a temporary break." For all other reasons, lead with the more targeted alternatives described above, and include pause as a secondary fallback option only.</p>
    </div>

    <div class="rc-subhead">Decision Framework: Should You Offer Pause?</div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Run Through This Checklist Before Deploying Pause</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk1">
        <label for="chk1">Your cancellation survey data shows a meaningful percentage (15%+) of subscribers citing temporary or seasonal reasons for leaving</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk2">
        <label for="chk2">Your business model doesn't incur significant per-subscriber costs during idle periods that make pause financially neutral or negative</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk3">
        <label for="chk3">You have a plan to re-engage paused subscribers before their pause period ends (email sequences, in-app nudges, content previews)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk4">
        <label for="chk4">You are NOT in a regulated industry where continuous service is legally required</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk5">
        <label for="chk5">You already have other retention interventions (downgrades, discounts, cancel-save flows) handling price and product objections</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="chk6">
        <label for="chk6">You have the analytics infrastructure to track pause-to-reactivation rates and distinguish genuine saves from delayed churn</label>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Bottom Line: Pause Complements—It Doesn't Replace</h3>
      <p>Pause subscriptions is a surgical tool for a specific type of churn: the subscriber who wants to return. It works best as part of a layered retention strategy that includes cancel-save flows with targeted offers, plan flexibility (downgrades and upgrades), promotional incentives for price-sensitive subscribers, and robust win-back campaigns for those who do leave. When you deploy pause alongside these other Recurly retention features, you create a comprehensive safety net that addresses every major cancellation reason—not just the temporary ones. The result is a measurable reduction in voluntary churn across the board, not just in the subset of subscribers who need a break.</p>
      <p>In the next section, we'll walk through exactly how to enable and configure pause in your Recurly account so you can start putting this strategy into action.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-3" class="rc-btn-prev">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Pause Subscriptions Video Walkthrough</a>
  </div>

</div></div>
<div id="pv-4" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn how to enable, configure, and deploy the Pause Subscriptions feature to reduce voluntary churn and keep subscribers in your ecosystem.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5" class="is-active">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- tool-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1spkzqq7q_IQuxDwLVmw2tFtrL3XQ3JWp" alt="tool-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>How to Enable It</h2>
        <p>A step-by-step walkthrough for configuring the Pause Subscriptions feature in Recurly, from admin settings through API integration and subscriber-facing deployment.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Before You Begin: Prerequisites</h3>
      <p>Enabling the Pause Subscriptions feature in Recurly is straightforward, but a little preparation goes a long way. Before you start flipping switches, make sure you have the following in place: admin-level access to your Recurly site, a clear understanding of which subscription plans should support pausing, and alignment with your team on maximum pause durations and any business rules you want to enforce. If you plan to surface the pause option through a self-service portal or cancel-save flow, coordinate with your development team so front-end work can happen in parallel with back-end configuration.</p>
      <p>It's also wise to have your subscriber communication templates ready—email notifications that confirm a pause has been initiated, remind subscribers when their pause is about to end, and welcome them back when their subscription resumes. Getting these drafted ahead of time means you can launch the full experience without gaps.</p>
    </div>

    <div class="rc-subhead">Step-by-Step: Enabling Pause in Recurly</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Navigate to Subscription Configuration</h4>
          <p>Log in to your Recurly admin dashboard with admin privileges. Go to <strong>Configuration → Subscriptions</strong>. This is where you manage the global settings that govern how subscription lifecycle events—including pauses—behave across your site. Familiarize yourself with your current plan structures, as pause settings apply at the subscription level, not the plan level.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Understand the Pause Mechanism</h4>
          <p>In Recurly, pausing a subscription works by setting a <strong>remaining_pause_cycles</strong> value on an active subscription. This tells Recurly how many billing cycles to skip before automatically resuming. During the paused period, no invoices are generated and the subscriber's billing is frozen. The subscription state transitions to "paused" and will automatically return to "active" once the pause cycles are exhausted—or you can resume it early via the admin UI or API.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Pause a Subscription via the Admin UI</h4>
          <p>For individual subscribers, navigate to <strong>Subscriptions</strong> in the left sidebar, find the target subscription, and open its detail page. Click the <strong>Pause</strong> action button. You'll be prompted to enter the number of billing cycles to pause. For example, entering "2" on a monthly plan means the subscriber skips two months of billing. Confirm the action, and the subscription immediately transitions to the paused state. The subscriber will not be billed again until the pause period expires or you manually resume.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Pause via the Recurly API</h4>
          <p>For programmatic control—especially if you're integrating pause into a cancel-save flow or self-service portal—use the Recurly API. Send a <strong>PUT</strong> request to <code>/subscriptions/{subscription_id}/pause</code> with a JSON body specifying <code>remaining_pause_cycles</code>. The API responds with the updated subscription object showing the new paused state. To resume early, send a <strong>PUT</strong> request to <code>/subscriptions/{subscription_id}/resume</code>. This flexibility lets you build dynamic experiences where subscribers choose their own pause duration from a set of options you define.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Integrate into Your Cancel-Save Flow</h4>
          <p>The highest-impact deployment is embedding pause as an option within your cancellation flow. When a subscriber clicks "Cancel," present pause as a prominent alternative—e.g., "Not ready to commit? Pause your subscription for 1–3 months instead." Use the API to execute the pause based on the subscriber's selection. This is where pause becomes a powerful retention tool: it intercepts churn intent at the exact moment it happens and offers a lower-friction alternative that keeps the subscriber relationship intact.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">6</div>
        <div class="rc-step-content">
          <h4>Configure Subscriber Notifications</h4>
          <p>Set up automated email notifications for key pause lifecycle events. At minimum, configure messages for: <strong>Pause Initiated</strong> (confirming the pause and expected resume date), <strong>Pause Ending Soon</strong> (sent 3–7 days before resumption as a courtesy reminder), and <strong>Subscription Resumed</strong> (confirming the subscription is active again and the next billing date). These communications reduce surprise charges, build trust, and lower support ticket volume. You can configure these in Recurly's email notification settings or through your own email platform using webhooks.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Use Webhooks for Real-Time Sync</strong>
      <p>Subscribe to the <code>subscription_paused</code> and <code>subscription_resumed</code> webhook events to keep your internal systems in sync. This is critical if you need to adjust access permissions, update a CRM record, trigger marketing automation sequences, or notify a fulfillment system to stop shipments during the pause window. Webhooks ensure your entire tech stack responds instantly to pause state changes without polling the API.</p>
    </div>

    <div class="rc-subhead">Configuring Pause Options: Best Practices</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- package-check.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package-check" style="width:28px;height:28px;">
        <h4>Offer Structured Choices</h4>
        <p>Rather than a free-form input, present 2–3 pre-defined pause durations (e.g., 1 month, 2 months, 3 months). This simplifies the decision for the subscriber and lets you control the maximum absence window.</p>
      </div>
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer-04" style="width:28px;height:28px;">
        <h4>Set a Maximum Pause Duration</h4>
        <p>Cap pause at 3 billing cycles for most businesses. Data shows that subscribers who pause beyond 3 months have significantly lower reactivation rates. A cap protects revenue while still offering meaningful flexibility.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- bell-ringing-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell-ringing-01" style="width:28px;height:28px;">
        <h4>Limit Pause Frequency</h4>
        <p>Consider enforcing a policy like "one pause per 12 months" to prevent subscribers from cycling between paused and active states indefinitely. You can enforce this in your application logic using the subscription's pause history.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart-hand" style="width:28px;height:28px;">
        <h4>Maintain Partial Access</h4>
        <p>Decide whether paused subscribers retain limited access to your product (read-only mode, archived content, community forums). Maintaining a touchpoint during pause keeps your brand top-of-mind and improves resume rates.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important: Revenue Recognition & Add-Ons</strong>
      <p>When a subscription is paused, no invoices are generated for that subscription's base charge. However, be aware that any one-time charges or usage-based add-ons that were already invoiced will not be reversed. Additionally, if your business has revenue recognition requirements, ensure your finance team understands how pause cycles affect recognized vs. deferred revenue reporting. Coordinate with your accounting team before enabling pause at scale to avoid reporting surprises.</p>
    </div>

    <div class="rc-subhead">Quick-Reference: API Endpoints</div>

    <div class="rc-card">
      <h3>Essential API Calls for Pause</h3>
      <p><strong>Pause a subscription:</strong> <code>PUT /subscriptions/{subscription_id}/pause</code> — Body: <code>{ "remaining_pause_cycles": 2 }</code></p>
      <p><strong>Resume a paused subscription:</strong> <code>PUT /subscriptions/{subscription_id}/resume</code> — No body required. The subscription immediately returns to active and the next billing date is set.</p>
      <p><strong>Check pause status:</strong> <code>GET /subscriptions/{subscription_id}</code> — The response includes <code>paused_at</code>, <code>remaining_pause_cycles</code>, and the projected <code>current_period_ends_at</code> for resume timing.</p>
      <p><strong>Webhook events to subscribe to:</strong> <code>subscription_paused</code>, <code>subscription_resumed</code>, <code>subscription_pause_modified</code> (if the remaining cycles are adjusted mid-pause).</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Launch Readiness Checklist</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check1">
        <label for="check1">Admin team has tested pausing and resuming a subscription in your Recurly sandbox environment</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check2">
        <label for="check2">API integration is complete and tested (pause, resume, and webhook handling)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check3">
        <label for="check3">Cancel-save flow updated to present pause as a prominent alternative to cancellation</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check4">
        <label for="check4">Email notifications configured for pause initiated, pause ending soon, and subscription resumed</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check5">
        <label for="check5">Maximum pause duration and frequency rules defined and enforced in application logic</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check6">
        <label for="check6">Internal systems (CRM, fulfillment, access control) integrated via webhooks to respond to pause state changes</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check7">
        <label for="check7">Finance and accounting teams briefed on how paused subscriptions affect invoicing and revenue recognition</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check8">
        <label for="check8">Customer support team trained on how to pause, resume, and troubleshoot paused subscriptions in the admin UI</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Retention Flywheel Connection</strong>
      <p>Pause Subscriptions is most powerful when combined with Recurly's other retention-stage features. Use it alongside <strong>cancel-save flows</strong> to intercept churn intent, <strong>advanced dunning campaigns</strong> to recover subscribers who return from pause with expired payment methods, and <strong>AI/ML revenue recovery</strong> to intelligently retry the first billing attempt when a subscription resumes. Together, these tools form a comprehensive retention strategy that minimizes both voluntary and involuntary churn.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-4" class="rc-btn-prev">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Pause Subscriptions Video Walkthrough</a>
    <a href="https://docs.recurly.com/reference" class="rc-link-btn">🔗 Recurly API Reference</a>
  </div>

</div></div>
<div id="pv-5" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn how to measure the business impact of your pause subscriptions feature and prove ROI to stakeholders.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6" class="is-active">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- bar-chart-12.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1gyrfwrpUd15NA_lJ-Te4PCpQqYgJv0l4" alt="bar-chart-12" style="width:28px;height:28px;"></div>
      <div>
        <h2>Tracking Impact</h2>
        <p>Measure the effectiveness of your pause feature, identify the metrics that matter, and build a data-driven feedback loop to optimize retention outcomes.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Why Measurement Is Non-Negotiable</h3>
      <p>Enabling the pause feature is only half the story. Without rigorous tracking, you won't know whether paused subscribers are actually returning, how much revenue the feature is saving, or whether your pause durations need adjustment. Measurement transforms the pause feature from a "nice-to-have" into a proven retention lever with quantifiable business impact. It also gives you the ammunition you need to expand the feature, refine your cancel-save flows, and justify investment to leadership—which we'll cover in the next section.</p>
      <p>The key principle: compare the behavior of subscribers who paused against those who cancelled outright. This cohort analysis is the foundation of every metric below. If your paused subscribers resume at a meaningful rate, you've found recoverable revenue that would have otherwise walked out the door permanently.</p>
    </div>

    <div class="rc-subhead">The Five Metrics That Matter</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer" style="width:28px;height:28px;">
        <h4>Pause Adoption Rate</h4>
        <p>Percentage of subscribers who choose pause over cancel when presented with both options in your cancel-save flow.</p>
      </div>
      <div class="rc-wi">
        <!-- users-check.png -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=11dQBMq_TcX74F5Byiw-xE9bRRPY8AQBO" alt="users-check" style="width:28px;height:28px;">
        <h4>Resume Rate</h4>
        <p>The percentage of paused subscribers who reactivate their subscription, either automatically or manually, after the pause period ends.</p>
      </div>
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet" style="width:28px;height:28px;">
        <h4>Revenue Saved</h4>
        <p>Total recurring revenue retained from subscribers who resumed after pausing, compared to what would have been lost if they cancelled.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- bar-chart-11.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="bar-chart-11" style="width:28px;height:28px;">
        <h4>Post-Resume Retention</h4>
        <p>How long resumed subscribers stay active after coming back. This tells you whether pause truly retains or merely delays churn.</p>
      </div>
      <div class="rc-wi">
        <!-- credit-card-refresh.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="credit-card-refresh" style="width:28px;height:28px;">
        <h4>Pause-to-Cancel Fallthrough</h4>
        <p>The percentage of paused subscribers who ultimately cancel instead of resuming. A high rate may signal your pause durations are too long.</p>
      </div>
    </div>

    <div class="rc-subhead">How to Calculate Each Metric</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Pause Adoption Rate</h4>
          <p><strong>Formula:</strong> (Number of subscribers who chose pause ÷ Total subscribers who entered the cancel flow) × 100. Track this weekly. A healthy adoption rate typically falls between 15–30%. If it's below 10%, your pause offer may not be prominent enough in the cancel-save flow, or the terms (e.g., maximum pause duration) may not be attractive. Experiment with placement, copy, and available pause lengths to increase adoption.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Resume Rate</h4>
          <p><strong>Formula:</strong> (Number of subscribers who resumed ÷ Total subscribers whose pause period ended) × 100. This is your most important metric. Industry benchmarks suggest that well-implemented pause features see resume rates of 40–70%. If you're below 40%, consider shortening your default pause duration, sending re-engagement emails before the pause ends, or offering a "welcome back" incentive. Segment this metric by pause duration—you may find that 30-day pauses yield much higher resume rates than 90-day pauses.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Revenue Saved</h4>
          <p><strong>Formula:</strong> Sum of MRR from all resumed subscribers over a given period. For a more conservative calculation, multiply each resumed subscriber's MRR by the number of months they've remained active post-resume. This gives you a "revenue saved" figure that accounts for post-resume churn. Compare this against your total voluntary churn to understand what percentage of lost revenue the pause feature is recovering. Even a 5–10% reduction in voluntary churn can translate to significant annual revenue.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Post-Resume Retention</h4>
          <p><strong>Formula:</strong> Measure the 30-day, 60-day, and 90-day retention rates of resumed subscribers. Compare these cohorts against your overall subscriber retention rates. If resumed subscribers churn at dramatically higher rates than your general population within 30 days, the pause feature may be delaying rather than preventing churn. Ideally, post-resume retention should be within 10–15 percentage points of your overall retention after the first billing cycle.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Pause-to-Cancel Fallthrough</h4>
          <p><strong>Formula:</strong> (Number of paused subscribers who cancelled during or at the end of their pause ÷ Total paused subscribers) × 100. A fallthrough rate above 60% is a red flag. Investigate whether specific pause durations correlate with higher fallthrough, whether subscribers who pause multiple times are more likely to cancel, and whether lack of communication during the pause period is contributing to disengagement.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Use Recurly's Export and Webhooks for Real-Time Tracking</strong>
      <p>Recurly fires webhooks for subscription state changes including <code>paused</code>, <code>resumed</code>, and <code>canceled</code>. Pipe these events into your analytics platform (Amplitude, Mixpanel, Looker, or even a simple spreadsheet via Zapier) to build a live dashboard. This lets you monitor resume rates in real time rather than waiting for end-of-month reports. You can also use Recurly's subscription exports to pull historical data for cohort analysis and trend identification.</p>
    </div>

    <div class="rc-subhead">Building Your Tracking Dashboard</div>

    <div class="rc-card">
      <h3>Recommended Dashboard Layout</h3>
      <p>Whether you use Recurly's built-in analytics, a BI tool like Looker or Tableau, or a simple Google Sheet, structure your pause tracking dashboard around three views:</p>
      <p><strong>1. Real-Time Snapshot:</strong> Current number of paused subscriptions, upcoming resume dates in the next 7/14/30 days, and week-over-week change in pause adoption rate. This gives your operations team immediate visibility into the pipeline of subscribers who are about to either resume or fall through.</p>
      <p><strong>2. Monthly Cohort View:</strong> Group paused subscribers by the month they paused. For each cohort, track the resume rate, fallthrough rate, and average time to resume. This longitudinal view reveals trends—are your resume rates improving over time as you refine your re-engagement strategy? Are seasonal patterns emerging?</p>
      <p><strong>3. Revenue Impact Summary:</strong> Total MRR currently paused (temporarily lost), total MRR recovered from resumes this month, net revenue impact (recovered minus permanently lost from fallthrough), and cumulative revenue saved since launch. This is the view your CFO and leadership team will care about most.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Forget: Account for MRR Temporarily Lost During Pause</strong>
      <p>Paused subscriptions represent revenue that is temporarily not being collected. While this is preferable to permanent cancellation, your finance team needs visibility into the total MRR sitting in "paused" state at any given time. If this number grows disproportionately large relative to your active MRR, it may indicate that subscribers are using pause as a way to get a perpetual discount. Set maximum pause durations and monitor this metric closely.</p>
    </div>

    <div class="rc-subhead">Optimization Feedback Loop</div>

    <div class="rc-card">
      <h3>Iterate Based on What the Data Tells You</h3>
      <p>Tracking is only valuable if it drives action. Establish a monthly review cadence where your product or retention team examines pause metrics and makes adjustments. Here are the most common optimization levers:</p>
      <p><strong>Pause Duration Optimization:</strong> If your data shows that 30-day pauses have a 65% resume rate but 90-day pauses drop to 25%, consider making 30 days the default and requiring subscribers to actively request longer pauses. Shorter pauses keep subscribers closer to your product and make it easier to re-engage them.</p>
      <p><strong>Re-engagement Timing:</strong> Test sending a "We miss you" email at the midpoint of the pause, one week before the pause ends, and on the day the pause ends. Measure which touchpoint has the highest correlation with successful resumes. Many merchants find that a reminder 3–5 days before the pause expires, combined with a teaser of new content or features, significantly boosts resume rates.</p>
      <p><strong>Cancel-Save Flow Placement:</strong> A/B test the position and presentation of the pause option within your cancellation flow. Is it more effective as the first option ("Before you go, would you like to pause instead?") or as a counter-offer after the subscriber has stated their cancellation reason? Data from your adoption rate metric will answer this question definitively.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Tracking Impact Readiness Checklist</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t1">
        <label for="t1">Webhooks configured for paused, resumed, and canceled subscription events</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t2">
        <label for="t2">Analytics platform connected and receiving Recurly subscription state change events</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t3">
        <label for="t3">Dashboard built with real-time snapshot, monthly cohort view, and revenue impact summary</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t4">
        <label for="t4">Baseline metrics established for pause adoption rate and resume rate</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t5">
        <label for="t5">Monthly review cadence scheduled with product/retention team to analyze pause data</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t6">
        <label for="t6">Post-resume retention tracking configured to measure 30/60/90-day retention of resumed subscribers</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="t7">
        <label for="t7">Revenue saved calculation documented and shared with finance stakeholders</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Benchmark Yourself</strong>
      <p>If you're just launching the pause feature, set a 90-day evaluation window before drawing conclusions. Early data will be noisy as subscribers discover and test the feature. After 90 days, you'll have enough cohort data to establish reliable baselines for adoption, resume, and fallthrough rates. From there, set quarterly improvement targets—even a 5% improvement in resume rate can meaningfully impact your annual retention numbers and lifetime value.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-5" class="rc-btn-prev">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎬 Pause Feature Video Walkthrough</a>
  </div>

</div></div>
<div id="pv-6" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <!-- 1. HERO SECTION -->
  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of cancellation</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <!-- 2. TAB NAVIGATION -->
  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7" class="is-active">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <!-- 3. SECTION HEADER & CONTENT -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- announcement-01.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1HhXev0Ya9ke3e1IxfytHklXgrvT0taWq" alt="announcement-01" style="width:28px;height:28px;"></div>
      <div>
        <h2>Pitch to Leadership</h2>
        <p>Build a compelling business case for enabling Recurly's Pause Subscriptions feature and secure stakeholder buy-in across your organization.</p>
      </div>
    </div>

    <!-- MAIN CONTENT -->

    <div class="rc-card">
      <h3>Why This Conversation Matters</h3>
      <p>Introducing a pause option may initially feel counterintuitive to leadership. After all, a paused subscriber temporarily stops paying — so the instinct might be to resist. But the data tells a very different story. When subscribers are forced into a binary "stay or cancel" decision, a significant portion choose to cancel permanently. A pause option transforms that moment of friction into a retention opportunity, preserving the billing relationship, keeping payment credentials on file, and dramatically increasing the likelihood of reactivation.</p>
      <p>The pitch to leadership is not about asking for permission to reduce revenue — it's about framing the Pause feature as a strategic investment in subscriber lifetime value (LTV), churn reduction, and competitive positioning. This section gives you the framework, talking points, and data to make that case convincingly.</p>
    </div>

    <div class="rc-subhead">The Executive Summary Framework</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Open With the Churn Problem</h4>
          <p>Lead with your own numbers. Pull your current voluntary churn rate from Recurly's analytics and calculate the monthly recurring revenue (MRR) lost to cancellations. Highlight that a meaningful portion of cancellations come from subscribers who don't actually want to leave permanently — they're dealing with temporary circumstances like budget constraints, seasonal use patterns, or life changes. Frame pause as a net designed to catch these recoverable subscribers before they're lost.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Present the Pause Value Proposition</h4>
          <p>Explain that Recurly's Pause feature lets subscribers temporarily halt billing for a defined period, after which their subscription automatically resumes. Emphasize three key advantages: (1) The subscriber relationship is preserved — no re-acquisition cost. (2) Payment credentials stay on file, eliminating the friction of re-entering billing details. (3) The automatic resume date creates a built-in reactivation mechanism without requiring any action from the subscriber or your team.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Show the Financial Model</h4>
          <p>Build a simple model: take your monthly cancellation volume, estimate the percentage of those cancellations that are "soft" (temporary intent), apply a conservative pause-to-resume conversion rate of 60–80%, and calculate the recovered MRR. Even recovering 10–15% of cancelling subscribers through pause can represent significant annual revenue. Compare this to the cost of re-acquiring those customers through paid marketing, which typically runs 5–7x the cost of retaining them.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Address the "Revenue Gap" Concern</h4>
          <p>Leadership will likely ask about the revenue lost during the pause period. Acknowledge this directly: yes, paused subscribers don't pay during the pause window. But frame the real comparison — a paused subscriber who resumes in 30–90 days versus a cancelled subscriber who never returns. The net LTV difference is overwhelmingly in favor of pause. Additionally, paused subscribers may still engage with your brand (depending on your access policies), maintaining habit loops that drive long-term loyalty.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Close With Competitive Context</h4>
          <p>Leading subscription businesses — from streaming services to SaaS platforms — have increasingly adopted pause as a standard retention lever. Not offering pause puts you at a competitive disadvantage, especially among price-sensitive subscribers who will compare your cancellation experience to competitors. Position pause as a signal of subscriber-first thinking that strengthens brand perception and reduces negative sentiment at the cancellation touchpoint.</p>
        </div>
      </div>
    </div>

    <div class="rc-subhead">Key Metrics to Include in Your Pitch</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet-01" style="width:28px;height:28px;">
        <h4>Customer Acquisition Cost</h4>
        <p>Show your CAC alongside the cost of retaining a paused subscriber ($0). The contrast makes the ROI case immediately clear.</p>
      </div>
      <div class="rc-wi">
        <!-- bar-chart-11.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="bar-chart-11" style="width:28px;height:28px;">
        <h4>Voluntary Churn Rate</h4>
        <p>Pull your current voluntary churn rate and calculate the MRR at risk. Even a 10% reduction through pause is a powerful number.</p>
      </div>
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer-04" style="width:28px;height:28px;">
        <h4>Subscriber LTV</h4>
        <p>Compare the projected LTV of a paused-then-resumed subscriber vs. a cancelled subscriber. The difference is your pause ROI.</p>
      </div>
    </div>

    <div class="rc-subhead">Tailoring the Pitch by Stakeholder</div>

    <div class="rc-2col">
      <div class="rc-card">
        <h3>For the CFO / Finance Team</h3>
        <p>Focus on the financial model. Finance leaders need to see the numbers: MRR at risk from voluntary churn, projected recovery rate from pause, cost comparison against re-acquisition spend, and the net impact on annual recurring revenue (ARR). Use conservative assumptions — a 60% resume rate from paused subscribers and a 5% diversion rate from the cancellation flow. Even conservative projections typically show meaningful revenue recovery. Emphasize that Recurly's Pause feature requires no additional licensing cost — it's built into the platform.</p>
      </div>
      <div class="rc-card">
        <h3>For the CPO / Product Team</h3>
        <p>Lead with subscriber experience and product differentiation. Product leaders care about user delight, engagement metrics, and competitive positioning. Explain how pause reduces the negative sentiment associated with cancellation, preserves the subscriber's personalized data and preferences, and creates a smoother re-engagement experience compared to re-signup. Highlight that Recurly handles the billing logic natively, meaning the product team doesn't need to build custom pause/resume workflows — reducing engineering effort significantly.</p>
      </div>
      <div class="rc-card">
        <h3>For the CMO / Growth Team</h3>
        <p>Frame pause as a retention marketing channel. Growth leaders think in terms of funnel optimization and lifecycle marketing. Position the pause option as the final stage of a cancel-save flow — one more chance to retain a subscriber before they leave. Highlight the marketing opportunities during the pause window: targeted emails, exclusive return offers, or early access to new features. Emphasize that paused subscribers are "warm leads" with existing payment methods on file, making reactivation campaigns dramatically more effective than cold win-back efforts.</p>
      </div>
      <div class="rc-card">
        <h3>For the CTO / Engineering</h3>
        <p>Address implementation effort head-on. Technical leaders want to know the scope. The good news: Recurly's Pause feature is platform-native and configurable without custom development. Pause can be enabled via the Recurly Admin Console or the API, subscriptions automatically resume on the scheduled date, and webhooks are available to trigger downstream systems (CRM updates, access management, analytics events). Estimate implementation at days, not weeks — particularly when using Recurly's hosted pages or existing API integration.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Propose a Pilot Program</strong>
      <p>If leadership is hesitant to roll out pause across all plans, propose a time-boxed pilot. Enable pause for one plan or one subscriber segment for 60–90 days, measure the impact on churn reduction and resume rates, then use those results to justify a full rollout. Pilots reduce perceived risk and give you real, internal data to strengthen your case — which is always more persuasive than industry benchmarks alone.</p>
    </div>

    <div class="rc-subhead">Common Objections and Responses</div>

    <div class="rc-card">
      <h3>"Won't subscribers abuse the pause feature?"</h3>
      <p>This is the most common concern, and the data consistently shows it's overblown. The vast majority of subscribers who pause do so for legitimate, temporary reasons. Recurly gives you full control over pause parameters — you set the maximum pause duration and can limit the number of pauses per subscription period. In practice, abuse rates are negligible. The subscribers most likely to pause are those who would otherwise cancel, meaning you're not creating new non-paying behavior — you're converting permanent churn into temporary pauses with a high probability of resumption.</p>
    </div>

    <div class="rc-card">
      <h3>"We'll lose too much revenue during the pause window."</h3>
      <p>Reframe the comparison. The alternative to a paused subscriber isn't a paying subscriber — it's a cancelled subscriber generating zero revenue forever. A subscriber paused for one month who resumes and stays for another 12 months generates 12x more revenue than one who cancels today. Additionally, you can offer limited-access or reduced-rate alternatives alongside pause, giving subscribers a spectrum of options before reaching the cancellation point.</p>
    </div>

    <div class="rc-card">
      <h3>"Our churn isn't high enough to justify this."</h3>
      <p>Every point of churn reduction matters at scale. Even if your voluntary churn rate is relatively low, the compounding effect of retained subscribers over 12–24 months is significant. A 1% improvement in monthly churn compounds to a 12–14% improvement in annual retention. And implementing pause is low-effort with Recurly — it's not a large investment for a potentially meaningful return. Frame it as a low-risk, high-ceiling opportunity rather than a response to a crisis.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Pitch Pause in Isolation</strong>
      <p>Pause is most compelling when positioned as part of a broader retention strategy that includes Recurly's cancel-save flows and advanced dunning campaigns. Leadership is more likely to approve a holistic churn-reduction initiative than a single feature request. Show how pause fits into the full subscriber lifecycle — alongside win-back campaigns, personalized offers, and intelligent retry logic — to demonstrate strategic thinking, not just feature adoption.</p>
    </div>

    <div class="rc-subhead">Your One-Page Pitch Template</div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Include these elements in your internal pitch document</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch1">
        <label for="pitch1"><strong>Problem Statement:</strong> Current voluntary churn rate, MRR lost to cancellations monthly, and the percentage of cancellations that appear temporary or avoidable</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch2">
        <label for="pitch2"><strong>Proposed Solution:</strong> Enable Recurly's native Pause Subscriptions feature as a cancel-save intervention for all (or select) subscription plans</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch3">
        <label for="pitch3"><strong>Financial Projection:</strong> Conservative model showing recovered MRR based on diversion rate from cancellation and expected resume rate from paused subscribers</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch4">
        <label for="pitch4"><strong>Implementation Scope:</strong> Timeline (typically 1–2 weeks), zero incremental Recurly cost, minimal engineering effort due to native platform support</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch5">
        <label for="pitch5"><strong>Success Metrics:</strong> KPIs you'll track — pause adoption rate, resume rate, impact on net churn, recovered MRR, and subscriber LTV comparison</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch6">
        <label for="pitch6"><strong>Competitive Benchmarks:</strong> Examples of industry peers or competitors offering pause, and subscriber expectations around flexible billing options</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch7">
        <label for="pitch7"><strong>Risk Mitigation:</strong> Controls available (max pause duration, pause frequency limits) and option to run a time-boxed pilot before full rollout</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="pitch8">
        <label for="pitch8"><strong>Strategic Alignment:</strong> How pause connects to broader retention goals, cancel-save flows, and the Recurly Retain flywheel stage</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Final Thought: Start the Conversation Today</strong>
      <p>The best time to introduce pause is before your next cancellation spike — not after. Seasonal businesses should enable it before their off-season. Growth-stage companies should implement it while churn patterns are still forming. And every subscription business benefits from giving subscribers more choices at the moment they're considering leaving. Recurly has made the feature available and configurable out of the box — the only thing standing between you and reduced churn is the decision to turn it on.</p>
    </div>

  </div>

  <!-- 5. BACK/NEXT NAVIGATION -->
  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-6" class="rc-btn-prev">← Previous</a>
    <a href="#" class="rc-btn-next rc-btn-disabled">Next →</a>
  </div>

  <!-- 6. ADDITIONAL RESOURCES -->
  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎬 Pause Subscriptions Video Walkthrough</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-1" class="rc-link-btn">🔄 Restart Course: What Is It?</a>
  </div>

</div></div><script>document.querySelectorAll(".pv-tab").forEach(function(btn) {  btn.addEventListener("click", function() {    document.querySelectorAll(".pv-tab").forEach(function(b) { b.classList.remove("active"); });    document.querySelectorAll(".pv-panel").forEach(function(p) { p.classList.remove("active"); });    btn.classList.add("active");    document.getElementById(btn.dataset.tab).classList.add("active");    window.scrollTo(0, 0);  });});</script></body></html>
`}</HTMLBlock>

<br />
