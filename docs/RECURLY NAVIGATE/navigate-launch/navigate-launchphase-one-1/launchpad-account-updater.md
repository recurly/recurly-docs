---
title: 'Section 3: Account Updater'
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
    margin: 0 0 14px;
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
    margin: 0 0 6px;
    color: var(--offblack);
  }

  .rc-sec-header > div > p {
    color: var(--gray);
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0;
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
    margin: 0 0 16px;
    color: var(--offblack);
  }

  .rc-stat-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-stat {
    background: var(--offblack);
    border-radius: 14px;
    padding: 24px 16px;
    text-align: center;
  }

  .rc-stat-num {
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--yellow);
  }

  .rc-stat-label {
    font-size: 0.78rem;
    color: var(--lightgray);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-top: 4px;
  }

  .rc-2col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
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
    margin: 0 0 5px;
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
    margin: 0 0 5px;
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
    margin: 0 0 4px;
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

  .rc-cli:last-child {
    border-bottom: none;
  }

  .rc-cb {
    width: 22px;
    height: 22px;
    border-radius: 6px;
    border: 2px solid var(--lightgray);
    flex-shrink: 0;
    margin-top: 1px;
    background: #fff;
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

  .rc-phase-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--offblack);
    color: var(--yellow);
    border-radius: 20px;
    padding: 4px 14px;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 20px;
  }

  .rc-pricing-card {
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 16px;
    border: 1px solid var(--lightgray);
    background: var(--offwhite);
  }

  .rc-pricing-card.free {
    border-left: 4px solid #2E7D32;
  }

  .rc-pricing-card.paid {
    border-left: 4px solid var(--orange);
  }

  .rc-pricing-card h4 {
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--offblack);
    margin: 0 0 6px;
  }

  .rc-pricing-card p {
    font-size: 0.86rem;
    color: var(--gray);
    line-height: 1.5;
    margin: 0;
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
  .rc-link-btn {
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
    background: #fff;
    color: var(--darkgray);
  }

  .rc-btn-next {
    background: var(--yellow);
    color: var(--offblack);
    border-color: var(--yellow);
  }

  .rc-link-btn {
    gap: 8px;
    background: var(--yellow);
    color: var(--offblack);
    margin: 0 8px 8px 0;
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
    .rc-2col, .rc-stat-grid { grid-template-columns: 1fr; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-hero-stats { gap: 20px; }
    .rc-nav, .rc-sec-nav, .rc-sec-header { flex-direction: column; }
    .rc-sec-nav { align-items: stretch; }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Navigate Launchpad</h1>
    <p>Your 90-day program to optimize, grow, and master your Recurly subscription business.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 3</div><div class="rc-lbl">Account Updater</div></div>
      <div><div class="rc-num">77x</div><div class="rc-lbl">Avg. ROI</div></div>
      <div><div class="rc-num">18%</div><div class="rc-lbl">Of Recovered Revenue</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">⚙️ Phase 1 · Week 3 of 6</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">💳</div>
      <div>
        <h2>Account Updater</h2>
        <p>The unsung hero of revenue recovery. Account Updater keeps your subscribers' card details current automatically — so renewals succeed before a failure ever happens.</p>
      </div>
    </div>

    <div class="rc-stat-grid">
      <div class="rc-stat">
        <div class="rc-stat-num">77x</div>
        <div class="rc-stat-label">Average ROI for AU customers</div>
      </div>
      <div class="rc-stat">
        <div class="rc-stat-num">18%</div>
        <div class="rc-stat-label">Of recovered revenue from AU</div>
      </div>
      <div class="rc-stat">
        <div class="rc-stat-num">96M+</div>
        <div class="rc-stat-label">Card updates in 2025</div>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💡 What Is Account Updater?</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When a customer's card expires, gets replaced after fraud, or is reissued by their bank, the card number or expiration date changes. If you try to charge that card on your next billing cycle, the charge will fail — even though the subscriber has done nothing wrong and fully intends to keep their subscription.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Account Updater is a service run by the major card networks — Visa, Mastercard, American Express, and Discover — that automatically sends updated card details to Recurly whenever a stored card changes. The result: your billing attempt uses fresh, accurate card data without the subscriber needing to do a single thing.</p>
    </div>

    <h3 class="rc-subhead">🔑 Why Enable It Now?</h3>
    <div class="rc-2col">
      <div class="rc-opt">
        <div class="rc-oicon">🛡️</div>
        <h4>Proactive, Not Reactive</h4>
        <p>Unlike dunning, which responds after a payment fails, Account Updater prevents the failure from happening in the first place. It's your most upstream revenue protection tool.</p>
        <span class="rc-tag">Most Proactive</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">🤝</div>
        <h4>Zero Friction for Subscribers</h4>
        <p>Customers never receive an “update your card” email. Renewals just work, invisibly. The experience stays seamless and subscribers stay happy.</p>
        <span class="rc-tag">Best CX</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">💰</div>
        <h4>Strong ROI</h4>
        <p>Recurly customers using Account Updater see 77x average ROI. Whether AU is included in your contract or usage-based, the cost is consistently lower than the revenue it protects.</p>
        <span class="rc-tag">High Return</span>
      </div>

      <div class="rc-opt">
        <div class="rc-oicon">⚡</div>
        <h4>Works Alongside Dunning</h4>
        <p>AU and dunning are complementary — AU catches known card changes before billing, dunning handles unexpected declines after. Together, they form your complete revenue recovery strategy.</p>
        <span class="rc-tag">Complementary</span>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">💰 A Note on Pricing</h3>
      <p style="font-size:0.88rem;color:var(--gray);margin:0 0 16px;">How Account Updater is priced depends on your contract. Check with your Account Manager if you're unsure which applies to you.</p>

      <div class="rc-pricing-card free">
        <h4>✅ Included in Your Contract</h4>
        <p>For many Recurly customers, Account Updater is bundled into their plan at no additional per-update cost. If this is your situation, there is no financial reason not to enable it immediately.</p>
      </div>

      <div class="rc-pricing-card paid">
        <h4>💳 Usage-Based Pricing</h4>
        <p>For some customers, AU is available at a per-successful-update charge — meaning you only pay when Recurly successfully retrieves updated card information. Compare the cost per update against your average subscription value. At a 77x average ROI, the math typically works in your favor.</p>
      </div>
    </div>

    <h3 class="rc-subhead">⚙️ How to Enable Account Updater</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Go to Settings → Payment Settings</h3>
          <p>In your Recurly admin, navigate to Payment Settings. This is where all payment-related feature toggles live, including Account Updater.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Locate the Account Updater section</h3>
          <p>Scroll to find the Account Updater configuration panel. You'll see toggle options for enabling the service across supported card networks.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Review the pricing disclaimer</h3>
          <p>Recurly will show a disclaimer with the pricing terms applicable to your account. If AU is included in your contract, this is informational only. Review it and confirm you want to proceed.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Toggle on and save</h3>
          <p>Enable Account Updater and save your settings. Recurly will now monitor for card updates and apply them to stored payment methods across your subscriber base.</p>
        </div>
      </div>

      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>(Optional) Enable American Express Cardrefresher</h3>
          <p>If you have a direct American Express merchant account and a US-based business, you can also enable Amex's proprietary Cardrefresher. You'll need your Amex SE Number and Merchant Category Code. Check your monthly Amex statement for these details.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Track Your Impact</h4>
        <p>Once enabled, you can measure Account Updater's impact in <strong>Analytics → Churn Management → Recovered Revenue</strong>. You'll see AU as a percentage of your total recovered revenue each month. Give it 60–90 days to build up meaningful data across your subscriber base.</p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Important:</strong> Account Updater works only when Recurly holds the card data directly — meaning you're using Recurly.js or a Recurly-hosted checkout. If you're using your gateway's own checkout and passing a gateway token to Recurly, enable Account Updater through your gateway instead. Not sure which applies to you? Check with your technical team or contact <a href="mailto:customersuccess@recurly.com" style="color:var(--orange);">Customer Success</a>.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 3 Checklist: Account Updater</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Confirmed how card data is collected (Recurly.js vs gateway token)<span>Determines whether to enable AU in Recurly or your gateway</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Reviewed pricing model for Account Updater in your contract<span>Confirm whether included or usage-based</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Enabled Account Updater in Settings → Payment Settings<span>Accepted pricing disclaimer and saved</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">(If applicable) Amex Cardrefresher configured<span>Requires direct Amex merchant account + US business</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Noted where to track AU impact in Analytics<span>Analytics → Churn Management → Recovered Revenue</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning">← Dunning</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding">Next: Branding →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Account Updater Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://share.synthesia.io/2c1e1470-aa37-4474-a9d2-e6e1ef1e33e7" target="_blank" rel="noopener noreferrer">▶ Setup Walkthrough Video</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-account-updater" target="_blank" rel="noopener noreferrer">🎓 Full Account Updater Learning Path</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
