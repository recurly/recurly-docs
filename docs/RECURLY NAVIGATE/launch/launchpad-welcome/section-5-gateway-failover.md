---
title: 'Section 5: Gateway Failover'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<!-- (styles unchanged — already consistent with previous pages) -->

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Navigate Launchpad</h1>
    <p>Your 90-day program to optimize, grow, and master your Recurly subscription business.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 5</div><div class="rc-lbl">Gateway Failover</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization</div></div>
      <div><div class="rc-num">~15</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">⚙️ Phase 1 · Week 5 of 6</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔒</div>
      <div>
        <h2>Gateway Failover</h2>
        <p>Outages are rare—but when your primary payment gateway goes down, having a backup in place is the difference between zero lost revenue and a very bad day.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🤔 What Is Gateway Failover?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 12px;">
        Gateway Failover allows Recurly to automatically route transactions to a secondary payment gateway when your primary gateway is unavailable or failing.
      </p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">
        When it's configured correctly, your customers never notice a disruption—payments go through, subscriptions continue, and your revenue stays protected.
      </p>
    </div>

    <h3 class="rc-subhead">⚡ What Can Trigger a Gateway Failure?</h3>
    <div class="rc-2col">
      <div class="rc-opt">
        <div class="rc-oicon">🔌</div>
        <h4>System Outages</h4>
        <p>Even major gateways experience downtime—planned or unexpected—that can interrupt payment processing.</p>
        <span class="rc-tag rc-tag-orange">Unpredictable</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">🚨</div>
        <h4>Fraud or Chargeback Thresholds</h4>
        <p>Spikes in fraud or chargebacks can trigger temporary suspensions, often without much warning.</p>
        <span class="rc-tag rc-tag-orange">Risk-Based</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">⚙️</div>
        <h4>Configuration Errors</h4>
        <p>Expired credentials or misconfigurations can quietly break your gateway connection until transactions begin failing.</p>
        <span class="rc-tag rc-tag-orange">Avoidable</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">🛡️</div>
        <h4>With Failover Enabled</h4>
        <p>Recurly automatically reroutes transactions to your backup gateway—keeping payments flowing without interruption.</p>
        <span class="rc-tag rc-tag-green">Protected</span>
      </div>
    </div>

    <h3 class="rc-subhead">⚙️ How to Enable Gateway Failover</h3>
    <div class="rc-steps">

      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Set up a secondary gateway</h3>
          <p>You’ll need a second gateway connected to Recurly. This can be a different provider or another account with your current provider.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Connect it in Recurly</h3>
          <p>Go to <strong>Settings → Payment Gateways</strong> and add your secondary gateway with verified credentials.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Define failover rules</h3>
          <p>Set your primary and backup gateways, along with the failure conditions that trigger rerouting.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Review routing logic</h3>
          <p>Understand how Recurly routes transactions based on card type, geography, and transaction type.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Test your setup</h3>
          <p>Simulate failure scenarios to confirm your secondary gateway activates correctly before you need it.</p>
        </div>
      </div>

    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Keep Your Backup Active</h4>
        <p>
          Run a small percentage of transactions through your secondary gateway regularly. This helps catch issues early and ensures it’s ready when you need it.
        </p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p>
        <strong>Not all gateways support failover.</strong> Review Recurly’s documentation to confirm compatibility and understand any limitations before relying on it.
      </p>
    </div>

    <div class="rc-complete-banner">
      <div style="font-size:36px;">🎉</div>
      <h3>You've Completed Phase 1!</h3>
      <p>
        Your setup is now optimized and protected. Next, you'll move into Phase 2—where you'll focus on the metrics that drive real subscription growth.
      </p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 5 Checklist: Gateway Failover</h3></div>

      <div class="rc-cli">
        <div class="rc-cb">✓</div>
        <div class="rc-clab">Secondary gateway identified<span>Confirmed it supports failover</span></div>
      </div>

      <div class="rc-cli">
        <div class="rc-cb">✓</div>
        <div class="rc-clab">Gateway connected in Recurly<span>Settings → Payment Gateways</span></div>
      </div>

      <div class="rc-cli">
        <div class="rc-cb">✓</div>
        <div class="rc-clab">Failover rules configured<span>Primary + backup routing set</span></div>
      </div>

      <div class="rc-cli">
        <div class="rc-cb">✓</div>
        <div class="rc-clab">Failover tested<span>Confirmed transactions reroute correctly</span></div>
      </div>

      <div class="rc-cli">
        <div class="rc-cb">✓</div>
        <div class="rc-clab">Backup gateway kept active<span>Optional traffic routing in place</span></div>
      </div>

    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding">← Branding</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics">Next: Metrics & Growth →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/gateway-failover" target="_blank">📖 Gateway Failover Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://share.synthesia.io/12149951-6016-4a63-86fb-bab20b93da0b" target="_blank">▶ Trail Guide Video</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com" target="_blank">🎧 Recurly Support</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
