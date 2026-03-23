---
title: 'Section 2: Dunning Optimization'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<style>
/* (same CSS — unchanged, already clean and reusable) */
</style>

<div class="rc-guide">

  <!-- HERO -->
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Dunning Optimization</h1>
    <p>Recover failed payments automatically and reduce involuntary churn with a strong dunning strategy.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 2</div><div class="rc-lbl">Launchpad</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization</div></div>
      <div><div class="rc-num">~25</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <!-- NAV -->
  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a class="rc-active" href="#"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">

    <div class="rc-phase-tag">⚙️ Phase 1 · Week 2 of 6</div>

    <!-- HEADER -->
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📬</div>
      <div>
        <h2>Dunning Optimization</h2>
        <p>A well-configured dunning strategy turns failed payments into recovered revenue automatically — and prevents silent subscriber loss.</p>
      </div>
    </div>

    <!-- WHAT IS -->
    <div class="rc-card">
      <h3 class="rc-subhead">🤔 What Is Dunning?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin-bottom:14px;">
        Dunning is the process of retrying failed payments and notifying subscribers when billing issues occur.
      </p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">
        When configured correctly, it recovers revenue automatically. When ignored, it becomes one of the biggest drivers of preventable churn.
      </p>
    </div>

    <!-- CHURN TYPES -->
    <h3 class="rc-subhead">📊 The Two Types of Churn</h3>
    <div class="rc-2col">
      <div class="rc-opt">
        <div class="rc-oicon">❌</div>
        <h4>Voluntary Churn</h4>
        <p>Customers who choose to cancel. Dunning doesn’t prevent this.</p>
        <span class="rc-tag">Intentional</span>
      </div>
      <div class="rc-opt">
        <div class="rc-oicon">🔄</div>
        <h4>Involuntary Churn</h4>
        <p>Customers lost due to failed payments — and fully recoverable.</p>
        <span class="rc-tag">Preventable</span>
      </div>
    </div>

    <!-- FLOW -->
    <h3 class="rc-subhead">⚡ How Dunning Works</h3>

    <div class="rc-dunning-flow">
      <div class="rc-df-row">
        <div class="rc-df-step"><div class="day">Day 0</div><h4>Payment Fails</h4><p>Initial renewal attempt is declined.</p></div>
        <div class="rc-df-step"><div class="day">Day 1–3</div><h4>Retry + Email</h4><p>Retry attempt + notification sent.</p></div>
        <div class="rc-df-step"><div class="day">Day 5–7</div><h4>Second Retry</h4><p>Another retry attempt.</p></div>
      </div>
      <div class="rc-df-row">
        <div class="rc-df-step"><div class="day">Day 10–14</div><h4>Final Attempt</h4><p>Last retry + urgency messaging.</p></div>
        <div class="rc-df-step"><div class="day">Day 16–21</div><h4>Expires</h4><p>Subscription cancels if unresolved.</p></div>
        <div class="rc-df-step" style="background:var(--brightgray);border-color:var(--yellow);">
          <div class="day" style="color:var(--darkgray);">Anytime</div>
          <h4>Customer Updates Card</h4>
          <p>Retry succeeds and subscription is saved.</p>
        </div>
      </div>
    </div>

    <!-- BEST PRACTICES -->
    <h3 class="rc-subhead">🎯 Best Practices</h3>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Optimize retry timing</h3>
          <p>Use a spaced schedule (Day 1, 3, 7, 14) to maximize recovery without overloading customers.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Improve email clarity</h3>
          <p>Make subject lines clear, CTA obvious, and update flow frictionless.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Enable Smart Retries</h3>
          <p>Let Recurly optimize retry timing automatically.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Set the right grace period</h3>
          <p>Typically 14–21 days for monthly subscriptions.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Pair with Account Updater</h3>
          <p>Combine reactive (dunning) and proactive (AU) recovery.</p>
        </div>
      </div>
    </div>

    <!-- TIP -->
    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip</h4>
        <p>Personalized subject lines dramatically increase recovery rates.</p>
      </div>
    </div>

    <!-- WARNING -->
    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Don't rely on defaults.</strong> Customize your strategy — defaults are a baseline, not optimized performance.</p>
    </div>

    <!-- CHECKLIST -->
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Dunning Checklist</h3></div>

      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Retry schedule optimized<span>Day 1, 3, 7, 14 recommended</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Emails updated<span>Clear CTA + strong subject lines</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Smart Retries enabled<span>Automatic optimization</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Grace period configured<span>14–21 days typical</span></div></div>
    </div>

    <!-- NAV BUTTONS -->
    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing">← Production Testing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater">Next: Account Updater →</a>
    </div>

    <!-- RESOURCES (CORRECT POSITION) -->
    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>

    <a class="rc-link-btn" href="https://docs.recurly.com/docs/dunning-management" target="_blank">📖 Recurly Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" target="_blank">▶ Watch Webinar</a>
    <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/navigate_dunning_optimization_checklist.html" target="_blank">📋 Download Checklist</a>

  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
