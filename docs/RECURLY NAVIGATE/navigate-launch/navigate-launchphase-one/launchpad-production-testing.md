---
title: 'Section 1: Final Production Testing'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
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
    color: #fff;
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
    background: #fff;
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
    box-shadow: 0 2px 12px rgba(255, 215, 6, 0.2);
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
    transition: box-shadow 0.2s;
  }

  .rc-step:hover {
    box-shadow: 0 4px 16px rgba(13, 13, 11, 0.08);
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
    .rc-hero h1 {
      font-size: 1.7rem;
    }

    .rc-2col {
      grid-template-columns: 1fr;
    }

    .rc-hero {
      padding: 36px 20px 32px;
    }

    .rc-hero-stats {
      gap: 20px;
    }

    .rc-nav,
    .rc-sec-nav,
    .rc-sec-header {
      flex-direction: column;
    }

    .rc-sec-nav {
      align-items: stretch;
    }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Navigate Launchpad</h1>
    <p>Your 90-day program to optimize, grow, and master your Recurly subscription business.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 1</div><div class="rc-lbl">Production Testing</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization</div></div>
      <div><div class="rc-num">~20</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">⚙️ Phase 1 · Week 1 of 6</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🧪</div>
      <div>
        <h2>Final Production Testing</h2>
        <p>Before customers start subscribing, walk your own checkout from start to finish. Catching a payment issue now saves you from losing revenue on day one.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🎯 Why This Matters</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">It’s one thing to have your Recurly account set up — it’s another to know it works flawlessly for the person actually trying to subscribe. A final production test puts you in your customer’s shoes and reveals friction points, configuration gaps, or payment issues that would not surface any other way.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">This is your last line of defense before real subscribers encounter your checkout. Do it once, do it right, and move forward with confidence.</p>
    </div>

    <h3 class="rc-subhead">🔧 What to Test</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">💳</div><h4>Payment Flow</h4><p>Complete a full subscription from the customer perspective — from plan selection through to a successful charge and confirmation.</p><span class="rc-tag">Must Test</span></div>
      <div class="rc-opt"><div class="rc-oicon">📧</div><h4>Confirmation Emails</h4><p>Verify that confirmation and receipt emails fire correctly after a successful transaction. Check timing, content, and formatting.</p><span class="rc-tag">Must Test</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔄</div><h4>Upgrade & Downgrade</h4><p>If you offer multiple plans, test plan changes mid-subscription to confirm proration logic and billing behavior work as expected.</p><span class="rc-tag">If Applicable</span></div>
      <div class="rc-opt"><div class="rc-oicon">❌</div><h4>Failed Payment Handling</h4><p>Test what happens when a card is declined. Does the customer get a clear error message? Does dunning kick in correctly?</p><span class="rc-tag">Important</span></div>
    </div>

    <h3 class="rc-subhead">✅ Step-by-Step: How to Run Your Production Test</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Use a real card in production</h3><p>Use your own credit card to place a real subscription order. This is the only way to confirm the full payment flow — including bank authorization, charge processing, and receipt delivery.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Walk through every step of your checkout</h3><p>Go through your entire purchase experience as if you were a new customer. Click every button, fill every field, and take note of anything that feels confusing or broken.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Check your Recurly dashboard</h3><p>Confirm the subscription appears correctly in Recurly — including the plan, billing cycle, subscriber details, and invoice status. Everything should match what you set up.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Review all triggered notifications</h3><p>Check that the correct emails fired. Review the content for accuracy — subscription details, amounts, renewal dates, and your branding should all appear correctly.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Cancel and verify the cancellation flow</h3><p>Process a cancellation, or test your cancellation or pause flow if enabled. Confirm the subscriber receives the correct messaging and the subscription status updates properly in Recurly.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge">6</div><div><h3>Refund your test charge</h3><p>Issue a refund for the test transaction from within Recurly or your gateway portal. Confirm the refund processes successfully before wrapping up.</p></div></div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>European merchants:</strong> Make sure your 3DS and SCA configuration is correctly set up before testing. SCA compliance is required for EU and UK card transactions. Review Recurly’s <a href="https://docs.recurly.com/docs/revised-payment-services-directive-psd2" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">PSD2 compliance documentation</a> if you haven’t already.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Test from Your Customer’s Device</h4>
        <p>Run your production test on a mobile device as well as desktop. A large percentage of subscribers will purchase on mobile, and a checkout that looks perfect on a laptop can have serious usability issues on a phone. Test both before declaring it done.</p>
      </div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 1 Checklist: Production Testing</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Completed a full subscription purchase in production with a real card<span>Including successful charge and receipt</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Confirmed subscription appears correctly in Recurly dashboard<span>Plan, billing cycle, subscriber details, invoice status</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Verified all confirmation emails fired with correct content<span>Amounts, renewal dates, and branding</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Tested checkout on both desktop and mobile<span>Confirm usability across devices</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Tested failed payment handling<span>Clear customer error message and dunning confirmation</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Processed a refund for the test charge<span>Confirmed refund processed successfully</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">European merchants: 3DS and SCA configuration verified<span>Required for EU and UK card transactions</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome">← Welcome</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning">Next: Dunning →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/test" target="_blank" rel="noopener noreferrer">📖 Gateway Testing Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/checkout" target="_blank" rel="noopener noreferrer">🛒 Checkout Configuration</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/revised-payment-services-directive-psd2" target="_blank" rel="noopener noreferrer">🇪🇺 PSD2 / 3DS Compliance</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com/hc/en-us/requests/new" target="_blank" rel="noopener noreferrer">🎧 Contact Support</a>
  </div>
</div>
`}</HTMLBlock>