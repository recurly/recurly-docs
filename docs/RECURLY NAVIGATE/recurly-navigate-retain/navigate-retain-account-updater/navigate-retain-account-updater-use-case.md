---
title: 'Section 5: Pitch to leadership'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-complete{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px;color:#fff}
  .rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:var(--yellow)}.rc-complete p{color:var(--lightgray);font-size:.95rem;margin:0;line-height:1.6}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge-dark{width:38px;height:38px;border-radius:10px;background:var(--darkgray);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none;border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-sec-header{flex-direction:column}.rc-nav,.rc-sec-nav{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>
</head>
<body>
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">1</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">2</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">3</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">4</span>Tracking Impact</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">5</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎤</div>
      <div>
        <h2>How to Pitch Account Updater to Leadership</h2>
        <p>Build a data-backed case for proactive revenue recovery by highlighting ROI benchmarks and the frictionless subscriber experience provided by this best-effort service.</p>
      </div>
    </div>

    <div class="rc-complete">
      <div style="font-size:40px;">🎯</div>
      <h2>The One-Line Pitch</h2>
      <p>"Account Updater (AU) is a proactive **best-effort assistant** that automatically keeps our subscribers' card details up to date — recovering revenue we'd otherwise lose, with zero effort from customers."</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📋 The Business Case — Key Points</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge-dark">1</div><div><h3>Stop unnecessary revenue leakage</h3><p>Subscription failures are often caused by card expirations, not cancellations. AU resolves these lifecycle events before they trigger a decline.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">2</div><div><h3>Proven ROI benchmarks</h3><p>Recurly customers using AU see an average of 18% of total recovered revenue attributed to this feature, with a 77x average ROI.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">3</div><div><h3>Zero friction for subscribers</h3><p>Card details refresh silently in the background. Customers don't need to receive "update your card" emails to stay active.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">4</div><div><h3>Favorable cost-to-value ratio</h3><p>The cost of Account Updater is consistently a small fraction of the monthly recurring revenue it successfully secures.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge-dark">5</div><div><h3>Rapid implementation</h3><p>Enabling the service is a simple settings toggle. No engineering resources or development work are required for standard setup.</p></div></div>
      </div>
    </div>

    <h3 class="rc-subhead">❓ Anticipated Questions & Answers</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge-dark">Q</div><div><h3>"What's the cost?"</h3><p>Depending on our contract, AU is either included in our subscription or usage-based. The average return is 77x. Speak with your Account Manager or <a href="mailto:support@recurly.com" style="color:var(--orange); font-weight:700; text-decoration:none;">Contact Recurly Support</a> to confirm our specific model.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">Q</div><div><h3>"Do we need engineering resources?"</h3><p>No. Account Updater is enabled through a self-serve toggle in the admin. There is no code change or development work required for setup.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">Q</div><div><h3>"Are there any risks?"</h3><p>AU is a secure, PCI-compliant **best-effort service**. It is subject to card network participation rules, so it should be used as a primary layer alongside our existing dunning strategy.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">Q</div><div><h3>"How quickly will we see results?"</h3><p>Impact builds over 60–90 days as card cycles renew. We can monitor this directly in the Recurly Churn Management analytics dashboard.</p></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🎯</span>
      <div>
        <h4>Ready to enable Account Updater?</h4>
        <p>Head to <strong>Configuration → Payment Settings</strong> in your Recurly admin and click Enable. </p>
      </div>
    </div>

    <div style="background-color:#0D0D0B; color:#FFFFFF; border-radius:16px; padding:32px; margin:32px 0; border:1px solid #FFD706;">
      <div class="rc-oh-content">
        <h4 style="color:#FFD706; margin:0 0 12px; font-size:1.1rem; font-weight:800; text-transform:uppercase; letter-spacing:1px;">🗓️ Book time with an expert first</h4>
        <p style="color:#CCC9B8; font-size:.95rem; line-height:1.6; margin:0 0 20px;">If you're not quite sure, join a <strong>Customer Success Global Office Hours</strong> to talk strategy with our CSMs. They'll walk you through all considerations, details, benefits, and implications of Account Updater (AU) for your subscription business.</p>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" style="background-color:#FFD706; color:#0D0D0B; text-decoration:none; padding:12px 24px; border-radius:10px; font-weight:900; font-size:.9rem; display:inline-flex; align-items:center; gap:10px;">Register for Office Hours →</a>
      </div>
    </div>

    <div class="rc-sec-nav" style="margin-top:40px;">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data">← Section 4: Tracking Impact</a>
      <span class="rc-btn-disabled">🎉 You're Ready to Go!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:40px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Customer Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">🧭 Return to Start</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
