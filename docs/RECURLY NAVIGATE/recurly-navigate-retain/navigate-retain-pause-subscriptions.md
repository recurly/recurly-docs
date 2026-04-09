---
title: Pause Subscription - API Test
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Pause, Not Cancel</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: none; padding: 32px 16px; }.pv-panel.active { display: block; }</style></head>
  
  
<body>

<div id="pv-0" class="pv-panel active"><style>
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
  </div></div></body>
`}</HTMLBlock>

<br />
