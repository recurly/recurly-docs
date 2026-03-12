---
title: How to enable it
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
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

  .rc-step:hover { box-shadow: 0 4px 16px rgba(13,13,11,0.08); }

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

  .rc-tipicon { font-size: 24px; flex-shrink: 0; }

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

  .rc-wicon { font-size: 20px; flex-shrink: 0; }

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
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/how-to-enable-it"><span class="rc-snum">5</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact"><span class="rc-snum">6</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pitch-to-leadership"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">⚙️</div>
      <div>
        <h2>How to Enable Account Updater</h2>
        <p>Enabling Account Updater in Recurly typically takes less than five minutes. Here's exactly what to do.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Trail Guide Walkthrough</h3>
      <div style="position: relative; overflow: hidden; aspect-ratio: 1920/1080; border-radius:14px;">
        <iframe
          src="https://share.synthesia.io/embeds/videos/b86fe7bd-1f74-491f-8632-acebd4794615"
          loading="lazy"
          title="Navigate: Secure Your Revenue — Account Updater"
          allowfullscreen
          allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"
          style="position:absolute;width:100%;height:100%;top:0;left:0;border:none;margin:0;">
        </iframe>
      </div>
      <p style="margin-top:14px;font-size:0.85rem;color:var(--gray);">
        Watch our Navigate CSM walk through enabling Account Updater step-by-step in your Recurly site.
      </p>
    </div>

    <h3 class="rc-subhead">🔧 Core Setup: Enable Account Updater</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Go to Payment Settings in Recurly</h3><p>In your Recurly admin, navigate to <strong>Settings → Payment Settings</strong>. This is where all payment-related feature toggles live.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Locate the Account Updater section</h3><p>Scroll to find the Account Updater configuration panel. You'll see toggle options for enabling the service across your supported card networks.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Review and accept the pricing disclaimer</h3><p>Recurly will present a disclaimer with the pricing terms applicable to your account. If Account Updater is included in your contract, this disclaimer is informational only. If you're on a usage-based model, review the per-update pricing and confirm you want to proceed.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Enable and save</h3><p>Toggle Account Updater on and save your settings. Recurly will now begin monitoring for card updates and applying them to stored payment methods across your subscriber base.</p></div></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🇺🇸 Optional: Enable American Express Cardrefresher</h3>
      <p style="font-size:0.88rem;color:var(--gray);margin-bottom:16px;">This step only applies if you have a direct American Express merchant account and your business is based in the United States. If this doesn't apply to you, skip this section.</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Locate your Amex Service Establishment (SE) Number</h3><p>Your SE number is found on your monthly Amex merchant statement, in your Amex merchant portal, or by calling Amex Merchant Services.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Locate your Merchant Category Code (MCC)</h3><p>Your MCC describes the type of business you operate. You can find it on your monthly processing statement, in your payment portal, or by calling your acquiring bank.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Enter both in Recurly and save</h3><p>In the Account Updater settings in Recurly, enter your SE number and MCC in the Amex Cardrefresher section and save.</p></div></div>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>OptBlue merchants are not supported.</strong> If your Amex acceptance is provided through your acquiring bank or payment gateway, you are not eligible for Amex Cardrefresher in Recurly. This requires a direct Amex merchant relationship.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Setup Checklist</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Account Updater toggled on in Recurly Payment Settings<span>Settings → Payment Settings → Account Updater</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Pricing disclaimer reviewed and accepted<span>Note whether you're on included or usage-based pricing</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">(If applicable) Amex SE number entered<span>Required for Amex Cardrefresher — US direct merchants only</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">(If applicable) Merchant Category Code (MCC) entered<span>Required for Amex Cardrefresher</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Settings saved<span>AU is now active and monitoring for card updates</span></div></div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Need More Detail?</h4>
        <p>For a full technical walkthrough including advanced configuration options, visit the <a href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">Recurly Account Updater documentation</a>. For questions about your specific setup, reach out to your Account Manager or contact <a href="mailto:customersuccess@recurly.com" style="color:var(--orange);">customersuccess@recurly.com</a>.</p>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/when-not-to-use-it">← When Not to Use It</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/tracking-impact">Next: Tracking Impact →</a>
    </div>

    <h3 class="rc-subhead">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater" target="_blank" rel="noopener noreferrer">🧭 Return to Learning Start</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
