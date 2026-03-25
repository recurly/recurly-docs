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
  .rc-guide {
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
    font-family: 'Segoe UI', system-ui, sans-serif;
  }

  .rc-hero {
    background: var(--offblack);
    color: white;
    padding: 56px 40px 48px;
    text-align: center;
    border-radius: 16px;
    margin-bottom: 0;
  }

  .rc-badge {
    display: inline-block;
    background: var(--yellow);
    color: var(--offblack);
    border-radius: 20px;
    padding: 6px 18px;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .rc-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    line-height: 1.15;
    margin-bottom: 14px;
    color: var(--offwhite);
  }

  .rc-hero > p {
    font-size: 1.05rem;
    opacity: 0.8;
    max-width: 600px;
    margin: 0 auto 32px;
    color: var(--lightgray);
  }

  .rc-hero-stats {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
  }

  .rc-num {
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--yellow);
  }

  .rc-lbl {
    font-size: 0.8rem;
    color: var(--lightgray);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .rc-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin: 24px 0 28px;
  }

  .rc-nav a {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    border-radius: 12px;
    border: 1px solid var(--lightgray);
    background: white;
    color: var(--darkgray);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 700;
    transition: border-color 0.2s, box-shadow 0.2s, background 0.2s, color 0.2s;
  }

  .rc-nav a:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 8px rgba(255, 215, 6, 0.2);
    color: var(--offblack);
    text-decoration: none;
  }

  .rc-nav a.rc-active {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255, 215, 6, 0.25);
  }

  .rc-snum {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 12px;
    font-weight: 700;
    flex-shrink: 0;
  }

  .rc-sec {
    display: block;
    margin-bottom: 56px;
  }

  .rc-sec-header {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 32px;
  }

  .rc-sec-icon {
    width: 56px;
    height: 56px;
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 26px;
    flex-shrink: 0;
    background: var(--yellow);
  }

  .rc-sec-header h2 {
    font-size: 1.7rem;
    font-weight: 800;
    margin-bottom: 6px;
    color: var(--offblack);
  }

  .rc-sec-header > div > p {
    color: var(--gray);
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0;
  }

  .rc-video-card {
    display: flex;
    align-items: center;
    gap: 24px;
    background: var(--darkgray);
    border-radius: 16px;
    padding: 32px;
    margin-bottom: 24px;
    text-decoration: none;
    transition: opacity 0.2s;
  }

  .rc-video-card:hover {
    opacity: 0.88;
    text-decoration: none;
  }

  .rc-play {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: var(--yellow);
    color: var(--offblack);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    flex-shrink: 0;
  }

  .rc-vmeta { color: white; }

  .rc-vtag {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--lightgray);
    margin-bottom: 6px;
  }

  .rc-vmeta h3 {
    font-size: 1.05rem;
    font-weight: 700;
    margin-bottom: 4px;
    color: var(--offwhite);
  }

  .rc-vmeta p {
    font-size: 0.85rem;
    color: var(--lightgray);
    margin: 0;
  }

  .rc-steps {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-bottom: 28px;
  }

  .rc-step {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 22px 26px;
    border: 1px solid var(--lightgray);
    display: flex;
    gap: 18px;
    align-items: flex-start;
    transition: box-shadow 0.2s;
  }

  .rc-step:hover {
    box-shadow: 0 4px 16px rgba(13,13,11,0.08);
  }

  .rc-sbadge {
    width: 38px;
    height: 38px;
    border-radius: 10px;
    background: var(--offblack);
    color: var(--yellow);
    font-weight: 800;
    font-size: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .rc-step h3 {
    font-size: 0.98rem;
    font-weight: 700;
    margin-bottom: 5px;
    color: var(--offblack);
  }

  .rc-step p {
    font-size: 0.87rem;
    color: var(--gray);
    line-height: 1.6;
    margin: 0;
  }

  .rc-tip {
    background: var(--offwhite);
    border: 2px solid var(--yellow);
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 24px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }

  .rc-tipicon {
    font-size: 24px;
    flex-shrink: 0;
  }

  .rc-tip h4 {
    font-size: 0.82rem;
    font-weight: 700;
    color: var(--offblack);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 4px;
  }

  .rc-tip p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-warning {
    background: #FFF8E6;
    border: 1px solid var(--orange);
    border-radius: 14px;
    padding: 16px 20px;
    margin-bottom: 24px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .rc-wicon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .rc-warning p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-checklist {
    background: var(--offwhite);
    border-radius: 16px;
    border: 1px solid var(--lightgray);
    overflow: hidden;
    margin-bottom: 28px;
  }

  .rc-cl-header {
    padding: 16px 22px;
    border-bottom: 1px solid var(--brightgray);
    display: flex;
    align-items: center;
    gap: 10px;
    background: var(--offblack);
  }

  .rc-cl-header h3 {
    font-size: 0.88rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: var(--yellow);
    margin: 0;
  }

  .rc-cli {
    padding: 13px 22px;
    border-bottom: 1px solid var(--brightgray);
    display: flex;
    align-items: flex-start;
    gap: 14px;
  }

  .rc-cli:last-child { border-bottom: none; }

  .rc-cb {
    width: 22px;
    height: 22px;
    border-radius: 6px;
    border: 2px solid var(--lightgray);
    flex-shrink: 0;
    margin-top: 1px;
    background: white;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    color: var(--gray);
  }

  .rc-clab {
    font-size: 0.88rem;
    color: var(--darkgray);
    line-height: 1.4;
  }

  .rc-clab span {
    display: block;
    font-size: 0.78rem;
    color: var(--gray);
    margin-top: 2px;
  }

  .rc-2col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 26px;
  }

  .rc-opt {
    background: var(--offwhite);
    border: 1px solid var(--lightgray);
    border-radius: 14px;
    padding: 18px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .rc-opt:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 12px rgba(255,215,6,0.2);
  }

  .rc-oicon {
    font-size: 22px;
    margin-bottom: 8px;
  }

  .rc-opt h4 {
    font-size: 0.92rem;
    font-weight: 700;
    margin-bottom: 5px;
    color: var(--offblack);
  }

  .rc-opt p {
    font-size: 0.82rem;
    color: var(--gray);
    line-height: 1.5;
    margin: 0;
  }

  .rc-tag {
    display: inline-block;
    margin-top: 10px;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
    background: var(--offblack);
    color: var(--yellow);
  }

  .rc-card {
    background: var(--offwhite);
    border-radius: 16px;
    padding: 28px;
    border: 1px solid var(--lightgray);
    margin-bottom: 24px;
  }

  .rc-subhead {
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 16px;
    color: var(--offblack);
  }

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

  .rc-btn-prev,
  .rc-btn-next,
  .rc-btn-disabled {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 11px 18px;
    border-radius: 10px;
    font-weight: 700;
    font-size: 0.88rem;
    text-decoration: none;
    border: 1px solid var(--lightgray);
  }

  .rc-btn-prev {
    background: white;
    color: var(--darkgray);
  }

  .rc-btn-next {
    background: var(--yellow);
    color: var(--offblack);
    border-color: var(--yellow);
  }

  .rc-btn-disabled {
    background: var(--brightgray);
    color: var(--gray);
    cursor: default;
  }

  .rc-link-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--yellow);
    color: var(--offblack);
    text-decoration: none;
    padding: 11px 22px;
    border-radius: 10px;
    font-weight: 700;
    font-size: 0.88rem;
    transition: opacity 0.2s;
    margin-bottom: 8px;
    margin-right: 8px;
  }

  .rc-link-btn:hover {
    opacity: 0.85;
    text-decoration: none;
  }

  .rc-link-sec {
    background: var(--offwhite);
    color: var(--darkgray);
    border: 1px solid var(--lightgray);
  }

  .rc-link-sec:hover {
    background: var(--brightgray);
  }

  @media (max-width: 640px) {
    .rc-hero h1 { font-size: 1.7rem; }
    .rc-2col { grid-template-columns: 1fr; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-nav { flex-direction: column; }
    .rc-sec-nav { flex-direction: column; align-items: stretch; }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate Launchpad</div>
    <h1>Dunning Optimization</h1>
    <p>Recover more failed payments and reduce involuntary churn with a stronger dunning strategy in Recurly.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">6</div><div class="rc-lbl">Setup Steps</div></div>
      <div><div class="rc-num">~25</div><div class="rc-lbl">Min to Complete</div></div>
      <div><div class="rc-num">0</div><div class="rc-lbl">Code Required</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📬</div>
      <div>
        <h2>Dunning Optimization</h2>
        <p>Dunning is one of the most important tools you have for preventing involuntary churn. A strong strategy helps you recover failed payments automatically and keep more subscribers active without adding manual work for your team.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🤔 What Is Dunning?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin-bottom:14px;">Dunning is the process of retrying failed subscription payments and communicating with subscribers when billing issues happen. When a renewal fails, Recurly can retry the payment on a schedule and send notifications prompting the subscriber to update their payment information.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">When configured well, dunning recovers revenue that would otherwise be lost to passive churn. When it is left on default settings or not reviewed regularly, you risk losing subscribers who never intended to cancel in the first place.</p>
    </div>

    <h3 class="rc-subhead">📊 The Two Types of Churn</h3>
    <div class="rc-2col">
      <div class="rc-opt">
        <div class="rc-oicon">❌</div>
        <h4>Voluntary Churn</h4>
        <p>Subscribers who actively decide to cancel. Dunning does not solve this type of churn directly.</p>
        <span class="rc-tag">Intentional</span>
      </div>
      <div class="rc-opt">
        <div class="rc-oicon">🔄</div>
        <h4>Involuntary Churn</h4>
        <p>Subscribers who lapse because a payment fails and is never recovered. This is where dunning creates the most impact.</p>
        <span class="rc-tag">Preventable</span>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">⚡ How Dunning Works in Recurly</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step">
          <div class="rc-sbadge">1</div>
          <div>
            <h3>The renewal payment fails</h3>
            <p>A subscriber’s card is declined for a reason like insufficient funds, expired details, or a temporary bank issue.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">2</div>
          <div>
            <h3>Recurly retries the payment</h3>
            <p>Based on your configured schedule, Recurly automatically makes another attempt to collect the payment.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">3</div>
          <div>
            <h3>The subscriber receives notifications</h3>
            <p>Recurly can send dunning emails asking the subscriber to update their payment method and resolve the issue.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-sbadge">4</div>
          <div>
            <h3>The payment is either recovered or expires</h3>
            <p>If the card is updated or a retry succeeds, the subscription continues. If not, the subscription may eventually expire based on your settings.</p>
          </div>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">🎯 Dunning Best Practices</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Review your retry timing</h3>
          <p>Make sure your retry schedule gives subscribers enough time to act without waiting so long that revenue is lost unnecessarily. A thoughtful cadence is more effective than relying on defaults.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Improve your dunning emails</h3>
          <p>Write clear, concise messages with an obvious call to action. The subscriber should immediately understand that their payment failed and know exactly how to fix it.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Use Smart Retries when available</h3>
          <p>Smart Retries can improve your recovery rate by attempting charges at better times based on payment behavior patterns.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Set an appropriate grace period</h3>
          <p>A grace period that is too short can cut off subscribers before they have time to act. A grace period that is too long can delay a necessary expiration. Balance is key.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Pair dunning with Account Updater</h3>
          <p>Dunning works best when combined with proactive recovery tools. Account Updater helps fix card issues before payment failures happen, while dunning helps recover what still fails.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip</h4>
        <p>The strongest dunning strategies are both operational and customer-friendly. A good setup is not just about retrying charges — it is also about reducing friction and making recovery easy for the subscriber.</p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Don’t leave dunning on default settings.</strong> Recurly’s default configuration is a starting point, not necessarily the best strategy for your business. Review your retry cadence, messaging, and expiration rules to make sure they support your subscription model.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 2 Checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed your current retry schedule<span>Confirm your cadence aligns with your billing model</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Updated dunning email content<span>Make the message and CTA clear for subscribers</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Confirmed Smart Retries are enabled if available<span>Use intelligent retry timing where possible</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed your grace period and expiration rules<span>Make sure they fit your subscription terms</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Planned for proactive recovery with Account Updater<span>Layer recovery strategies for stronger results</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing">← Production Testing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater">Next: Account Updater →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/dunning-management" target="_blank" rel="noopener noreferrer">📖 Recurly Dunning Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" target="_blank" rel="noopener noreferrer">▶ Dunning On-Demand Video</a>
    <a class="rc-link-btn rc-link-sec" href="https://go.recurly.com/navigate_dunning_optimization_checklist.html" target="_blank" rel="noopener noreferrer">📋 Dunning Optimization Checklist</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
