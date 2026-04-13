---
title: Tracking impact
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

  .rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 26px; }

  .rc-opt {
    background: var(--offwhite);
    border: 1px solid var(--lightgray);
    border-radius: 14px;
    padding: 18px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .rc-opt:hover { border-color: var(--yellow); box-shadow: 0 2px 12px rgba(255,215,6,0.2); }
  .rc-oicon { font-size: 22px; margin-bottom: 8px; }
  .rc-opt h4 { font-size: 0.92rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
  .rc-opt p { font-size: 0.82rem; color: var(--gray); line-height: 1.5; margin: 0; }

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
  .rc-btn-next {
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
  .rc-btn-next { background: var(--yellow); color: var(--offblack); border-color: var(--yellow); }

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
    .rc-2col { grid-template-columns: 1fr; }
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
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📊</div>
      <div>
        <h2>Tracking the Impact of Account Updater</h2>
        <p>Once Account Updater is enabled, here's how to measure what it's doing for your revenue — and how to share those results with your team.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📍 Where to Find AU Data in Recurly</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge-dark">1</div><div><h3>Navigate to Analytics → Churn Management</h3><p>In your Recurly admin, go to <strong>Analytics → Churn Management → Recovered Revenue</strong>. This is the primary dashboard for understanding how different recovery methods are performing.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">2</div><div><h3>Review the Recovered Revenue chart</h3><p>You'll see a bar chart broken down by recovery method — including Account Updater. This shows both the percentage and absolute dollar value of revenue recovered through AU month over month.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">3</div><div><h3>Monitor trends over time</h3><p>As Account Updater works through your existing subscriber base, the impact compounds. Look for a growing share of recovered revenue attributed to AU, and a corresponding reduction in involuntary churn.</p></div></div>
      </div>
    </div>

    <h3 class="rc-subhead">📏 Metrics Worth Tracking</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">💰</div><h4>Revenue Recovered via AU</h4><p>The direct dollar amount of subscription revenue that was successfully charged because Account Updater updated the card before it was attempted.</p><span class="rc-tag">Primary metric</span></div>
      <div class="rc-opt"><div class="rc-oicon">📉</div><h4>Failed Payment Rate (Card-based)</h4><p>Track the rate of failed payments attributable to outdated card info. You should see this decline after enabling AU.</p><span class="rc-tag">Secondary metric</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔄</div><h4>AU Update Volume</h4><p>The total number of card updates processed through Account Updater. Useful for understanding scale and managing costs if on usage-based pricing.</p><span class="rc-tag">Operational</span></div>
      <div class="rc-opt"><div class="rc-oicon">📊</div><h4>AU as % of Total Recovery</h4><p>What share of your total recovered revenue is coming from Account Updater vs. dunning vs. other methods?</p><span class="rc-tag">Benchmark</span></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Give It 60–90 Days Before Drawing Conclusions</h4>
        <p>Account Updater works over time as the cards in your vault age and as subscription renewal cycles come around. Give it at least two to three billing cycles before evaluating performance.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it">← How to Enable It</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership">Next: Pitch to Leadership →</a>
    </div>

    <h3 class="rc-subhead">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater" target="_blank" rel="noopener noreferrer">🧭 Return to Learning Start</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
