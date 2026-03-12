---
title: Pitch to leadership
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
    max-width: 700px;
    margin: 0 auto 32px;
    color: var(--lightgray);
  }

  .rc-hero-stats {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
  }

  .rc-num { font-size: 1.8rem; font-weight: 800; color: var(--yellow); }
  .rc-lbl { font-size: 0.8rem; color: var(--lightgray); text-transform: uppercase; letter-spacing: 0.5px; }

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
    box-shadow: 0 2px 8px rgba(255,215,6,0.2);
    color: var(--offblack);
    text-decoration: none;
  }

  .rc-nav a.rc-active {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255,215,6,0.25);
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

  .rc-sec { display: block; margin-bottom: 56px; }

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

  .rc-sec-header h2 { font-size: 1.7rem; font-weight: 800; margin-bottom: 6px; color: var(--offblack); }
  .rc-sec-header > div > p { color: var(--gray); font-size: 0.95rem; line-height: 1.5; }

  .rc-complete {
    background: var(--offblack);
    border-radius: 16px;
    padding: 40px;
    text-align: center;
    margin-bottom: 28px;
    color: white;
  }

  .rc-complete h2 { font-size: 1.8rem; font-weight: 800; margin: 12px 0 10px; color: var(--yellow); }
  .rc-complete p { color: var(--lightgray); font-size: 0.95rem; margin: 0; }

  .rc-card {
    background: var(--offwhite);
    border-radius: 16px;
    padding: 28px;
    border: 1px solid var(--lightgray);
    margin-bottom: 24px;
  }

  .rc-subhead { font-size: 1rem; font-weight: 700; margin-bottom: 16px; color: var(--offblack); }

  .rc-steps { display: flex; flex-direction: column; gap: 16px; margin-bottom: 28px; }

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

  .rc-step:hover { box-shadow: 0 4px 16px rgba(13,13,11,0.08); }

  .rc-sbadge,
  .rc-sbadge-dark {
    width: 38px;
    height: 38px;
    border-radius: 10px;
    font-weight: 800;
    font-size: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .rc-sbadge { background: var(--offblack); color: var(--yellow); }
  .rc-sbadge-dark { background: var(--darkgray); color: var(--yellow); }

  .rc-step h3 { font-size: 0.98rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
  .rc-step p { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }

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

  .rc-tipicon { font-size: 24px; flex-shrink: 0; }
  .rc-tip h4 { font-size: 0.82rem; font-weight: 700; color: var(--offblack); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 4px; }
  .rc-tip p { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

  .rc-btn-prev,
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

  .rc-btn-prev { background: white; color: var(--darkgray); }
  .rc-btn-disabled { background: var(--brightgray); color: var(--gray); cursor: default; }

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

  .rc-link-btn:hover { opacity: 0.85; text-decoration: none; }

  .rc-link-sec {
    background: var(--offwhite);
    color: var(--darkgray);
    border: 1px solid var(--lightgray);
  }

  .rc-link-sec:hover { background: var(--brightgray); }

  @media (max-width: 640px) {
    .rc-hero h1 { font-size: 1.7rem; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-nav { flex-direction: column; }
    .rc-sec-nav { flex-direction: column; align-items: stretch; }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">💳 Revenue Recovery</div>
    <h1>Account Updater</h1>
    <p>Protect your recurring revenue by automatically keeping card details up to date — before payments ever fail.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">77x</div><div class="rc-lbl">Average ROI</div></div>
      <div><div class="rc-num">18%</div><div class="rc-lbl">Of recovered revenue</div></div>
      <div><div class="rc-num">96M+</div><div class="rc-lbl">Card updates in 2025</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/why-use-it"><span class="rc-snum">2</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/things-to-consider"><span class="rc-snum">3</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it"><span class="rc-snum">4</span>When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it"><span class="rc-snum">5</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎤</div>
      <div>
        <h2>How to Pitch Account Updater to Leadership</h2>
        <p>If you need to build a case for enabling Account Updater internally, here's everything you need to make it easy.</p>
      </div>
    </div>

    <div class="rc-complete">
      <div style="font-size:40px;">🎯</div>
      <h2>The One-Line Pitch</h2>
      <p>"Account Updater automatically keeps our subscribers' card details up to date — recovering revenue we'd otherwise lose to failed payments, with zero effort from customers or our team."</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📋 The Business Case — Key Points</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge-dark">1</div><div><h3>We're losing revenue we don't need to lose</h3><p>A significant share of subscription failures are caused not by customers choosing to cancel, but by their card expiring or being reissued. This is recoverable revenue.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">2</div><div><h3>The data supports it</h3><p>Recurly customers using Account Updater see an average of 18% of total recovered revenue attributed to this single feature, with an average 77x ROI.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">3</div><div><h3>It requires no customer action</h3><p>Customers never receive an "update your card" email. Renewals just work.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">4</div><div><h3>The cost model is favorable</h3><p>Whether Account Updater is included in your Recurly contract or available as a per-update service, the cost is consistently lower than the revenue it protects.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">5</div><div><h3>Setup takes less than five minutes</h3><p>There's no development work required for most configurations. It's a settings toggle in Recurly.</p></div></div>
      </div>
    </div>

    <h3 class="rc-subhead">❓ Anticipated Questions & Answers</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">Q</div><div><h3>"What's the cost?"</h3><p>Depending on our contract, Account Updater is either included in our current Recurly subscription or available as a per-successful-update charge. Across Recurly's customer base, the average return is 77x.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">Q</div><div><h3>"Do we need engineering resources to set this up?"</h3><p>No. Account Updater is enabled through a toggle in Recurly's Payment Settings. There is no code change or development work required for standard setup.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">Q</div><div><h3>"Are there any risks?"</h3><p>The main thing to confirm is that we're not already running Account Updater through our payment gateway for the same card pool.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">Q</div><div><h3>"How quickly will we see results?"</h3><p>Results build over 60–90 days as the feature works through our existing subscriber base. We can track impact directly in Recurly's Recovered Revenue dashboard.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">Q</div><div><h3>"Is this secure?"</h3><p>Yes. Card network update programs operate through the same secure channels used for all card-network communications, and Recurly is PCI-compliant.</p></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🎯</span>
      <div>
        <h4>Your Next Step</h4>
        <p>Ready to enable Account Updater? Head to <strong>Settings → Payment Settings</strong> in your Recurly admin and toggle it on. If you have questions about pricing or your specific configuration, reach out to your Recurly Account Manager or contact <a href="mailto:customersuccess@recurly.com" style="color:var(--orange);">customersuccess@recurly.com</a>.</p>
      </div>
    </div>

    <h3 class="rc-subhead">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://share.synthesia.io/2c1e1470-aa37-4474-a9d2-e6e1ef1e33e7" target="_blank" rel="noopener noreferrer">▶ Setup Walkthrough Video</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater" target="_blank" rel="noopener noreferrer">🔗 Adyen RTAU Integration</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact">← Tracking Impact</a>
      <span class="rc-btn-disabled">🎉 You're Ready to Go!</span>
    </div>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
