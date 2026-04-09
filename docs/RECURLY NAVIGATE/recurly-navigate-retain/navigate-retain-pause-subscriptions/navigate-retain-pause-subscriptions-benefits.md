---
title: Pause API Test - Benefits
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Pause, Not Cancel</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: none; padding: 32px 16px; }.pv-panel.active { display: block; }</style></head>

<body><div class="pv-bar"><button class="pv-tab active" data-tab="pv-0">1. What Is It?</button><button class="pv-tab" data-tab="pv-1">2. Why Use It?</button><button class="pv-tab" data-tab="pv-2">3. Things to Consider</button><button class="pv-tab" data-tab="pv-3">4. When Not to Use It</button><button class="pv-tab" data-tab="pv-4">5. How to Enable It</button><button class="pv-tab" data-tab="pv-5">6. Tracking Impact</button><button class="pv-tab" data-tab="pv-6">7. Pitch to Leadership</button></div>

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
`}</HTMLBlock>

<br />
