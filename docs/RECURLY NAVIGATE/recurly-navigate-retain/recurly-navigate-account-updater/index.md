---
title: 'Recurly Navigate: Account Updater'
deprecated: false
hidden: true
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

  .rc-tabs input[type="radio"] {
    display: none;
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

  .rc-tab-label {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    border-radius: 12px;
    border: 1px solid var(--lightgray);
    background: white;
    color: var(--darkgray);
    font-size: 0.88rem;
    font-weight: 700;
    transition: border-color 0.2s, box-shadow 0.2s, background 0.2s, color 0.2s;
    cursor: pointer;
  }

  .rc-tab-label:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 8px rgba(255,215,6,0.2);
    color: var(--offblack);
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

  .rc-anchor {
    display: block;
    position: relative;
    top: -12px;
    visibility: hidden;
    height: 0;
  }

  .rc-panels .rc-panel {
    display: none;
  }

  /* Default tab states */
  #tab-what:checked ~ .rc-nav label[for="tab-what"],
  #tab-why:checked ~ .rc-nav label[for="tab-why"] {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255,215,6,0.25);
  }

  #tab-what:checked ~ .rc-panels .rc-panel-what,
  #tab-why:checked ~ .rc-panels .rc-panel-why {
    display: block;
  }

  /* Anchor-link overrides */
  #what:target ~ .rc-panel-what,
  #why:target ~ .rc-panel-why {
    display: block;
  }

  /* When a hash target is present, suppress the default checked panel */
  .rc-panels:has(#what:target) .rc-panel,
  .rc-panels:has(#why:target) .rc-panel {
    display: none;
  }

  .rc-panels:has(#what:target) .rc-panel-what,
  .rc-panels:has(#why:target) .rc-panel-why {
    display: block;
  }

  /* Anchor-link active nav highlight */
  .rc-nav a {
    text-decoration: none;
  }

  .rc-panels:has(#what:target) ~ * {
  }

  .rc-guide:has(#what:target) .rc-nav .rc-link-what,
  .rc-guide:has(#why:target) .rc-nav .rc-link-why {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255,215,6,0.25);
  }

  /* If using anchor links, don't also show radio-active style on wrong tab */
  .rc-guide:has(#what:target) #tab-what:checked ~ .rc-nav label[for="tab-what"],
  .rc-guide:has(#why:target) #tab-what:checked ~ .rc-nav label[for="tab-what"],
  .rc-guide:has(#what:target) #tab-why:checked ~ .rc-nav label[for="tab-why"],
  .rc-guide:has(#why:target) #tab-why:checked ~ .rc-nav label[for="tab-why"] {
    background: white;
    border-color: var(--lightgray);
    color: var(--darkgray);
    box-shadow: none;
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

  .rc-3col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-wi {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 20px;
    border: 1px solid var(--lightgray);
    text-align: center;
  }

  .rc-wi-icon {
    font-size: 30px;
    margin-bottom: 10px;
  }

  .rc-wi h4 {
    font-size: 0.88rem;
    font-weight: 700;
    margin-bottom: 5px;
    color: var(--offblack);
  }

  .rc-wi p {
    font-size: 0.80rem;
    color: var(--gray);
    line-height: 1.5;
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
    font-size: 2rem;
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

  .pricing-card {
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 16px;
    border: 1px solid var(--lightgray);
    background: var(--offwhite);
  }

  .pricing-card.free {
    border-left: 4px solid #2E7D32;
  }

  .pricing-card.paid {
    border-left: 4px solid var(--orange);
  }

  .pricing-card h4 {
    font-size: 0.95rem;
    font-weight: 700;
    color: var(--offblack);
    margin-bottom: 6px;
  }

  .pricing-card p {
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
    cursor: pointer;
  }

  .rc-btn-next {
    background: var(--yellow);
    color: var(--offblack);
    border-color: var(--yellow);
    cursor: pointer;
  }

  .rc-btn-disabled {
    background: var(--brightgray);
    color: var(--gray);
    cursor: default;
  }

  @media (max-width: 640px) {
    .rc-hero h1 { font-size: 1.7rem; }
    .rc-2col, .rc-3col, .rc-stat-grid { grid-template-columns: 1fr; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-video-card { flex-direction: column; padding: 24px; }
    .rc-nav { flex-direction: column; }
    .rc-sec-nav { flex-direction: column; align-items: stretch; }
  }
</style>

<div class="rc-guide rc-tabs">
  <input type="radio" name="rc-tabs" id="tab-what" checked>
  <input type="radio" name="rc-tabs" id="tab-why">
  <input type="radio" name="rc-tabs" id="tab-consider">
  <input type="radio" name="rc-tabs" id="tab-when-not">
  <input type="radio" name="rc-tabs" id="tab-how">
  <input type="radio" name="rc-tabs" id="tab-track">
  <input type="radio" name="rc-tabs" id="tab-pitch">

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
    <a class="rc-tab-label rc-link-what" href="#what"><span class="rc-snum">1</span>What Is It?</a>
    <a class="rc-tab-label rc-link-why" href="#why"><span class="rc-snum">2</span>Why Use It?</a>
    <label class="rc-tab-label" for="tab-consider"><span class="rc-snum">3</span>Things to Consider</label>
    <label class="rc-tab-label" for="tab-when-not"><span class="rc-snum">4</span>When Not to Use It</label>
    <label class="rc-tab-label" for="tab-how"><span class="rc-snum">5</span>How to Enable It</label>
    <label class="rc-tab-label" for="tab-track"><span class="rc-snum">6</span>Tracking Impact</label>
    <label class="rc-tab-label" for="tab-pitch"><span class="rc-snum">✓</span>Pitch to Leadership</label>
  </nav>

  <div class="rc-panels">

    <span id="what" class="rc-anchor"></span>
    <div class="rc-panel rc-panel-what">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">💳</div>
          <div>
            <h2>What is Account Updater?</h2>
            <p>A plain-language explanation of what Account Updater does and how it works — no prior knowledge required.</p>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">🧩 The Simple Version</h3>
          <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;">When a customer's credit or debit card expires, gets lost or stolen, or is reissued by their bank, the card number or expiration date changes. If you're charging that card on a recurring basis — like a subscription renewal — that charge will simply fail. The customer hasn't cancelled. They still want your product. Their card just changed.</p>
          <br>
          <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;"><strong>Account Updater (AU) is the solution.</strong> It's a service run by the major card networks — Visa, Mastercard, American Express, and Discover — that automatically pushes updated card details to Recurly whenever a card on file changes. Recurly then stores that fresh information so that your next billing attempt uses the correct card data, without the customer needing to do anything.</p>
        </div>

        <div class="rc-3col">
          <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Standard Account Updater</h4><p>Supported for Visa, Mastercard, American Express, and Discover. Updates are fetched on a scheduled basis before renewal attempts.</p></div>
          <div class="rc-wi"><div class="rc-wi-icon">⚡</div><h4>Real-Time Account Updater (RTAU)</h4><p>Available for Visa and Mastercard. Recurly receives a webhook the moment a card update is available — at any point in the subscription lifecycle, not just near renewal.</p></div>
          <div class="rc-wi"><div class="rc-wi-icon">🏦</div><h4>American Express Cardrefresher</h4><p>Amex's proprietary version of AU. Requires a direct Amex merchant account and a US-based business. Configured separately within Recurly.</p></div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">🗺️ How It Works — Step by Step</h3>
          <div class="rc-steps" style="margin-bottom:0;">
            <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>A cardholder's bank issues a card change</h3><p>This could be a new card number, updated expiration date, or a card that's been closed or replaced. Common events: annual renewals, fraud replacements, or bank-issued card migrations.</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>The card network is notified</h3><p>Visa, Mastercard, Amex, or Discover updates their internal records with the new card details associated with that account.</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Recurly is alerted</h3><p>For standard AU, Recurly checks for updates on a scheduled basis. For Real-Time AU (Visa and Mastercard), the card network sends a webhook to Recurly instantly.</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Recurly updates the stored payment method</h3><p>The new card details replace the old ones in Recurly's payment vault — silently, automatically, and without any action required from your customer or your team.</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>The next renewal charges successfully</h3><p>Because the billing info is already up to date, the subscription renews without interruption. No failed payment. No dunning. No involuntary churn.</p></div></div>
          </div>
        </div>

        <div class="rc-warning">
          <span class="rc-wicon">⚠️</span>
          <p><strong>Important to know:</strong> Account Updater works with credit and debit cards stored directly in Recurly's payment vault. It does <strong>not</strong> apply to alternative payment methods like Apple Pay or Google Pay — these are token-based and do not participate in card network update programs.</p>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>The Bottom Line</h4>
            <p>Account Updater quietly fixes outdated card details behind the scenes — reducing failed payments and churn before they ever happen. It's one of the few revenue recovery tools that is entirely proactive rather than reactive. No dunning, no customer action, no friction.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <span class="rc-btn-disabled">← Back</span>
          <a class="rc-btn-next" href="#why">Next: Why Use It? →</a>
        </div>
      </div>
    </div>

    <span id="why" class="rc-anchor"></span>
    <div class="rc-panel rc-panel-why">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">📈</div>
          <div>
            <h2>Why Should You Use Account Updater?</h2>
            <p>The business case for enabling Account Updater — including what it protects, what it recovers, and what it costs.</p>
          </div>
        </div>

        <div class="rc-stat-grid">
          <div class="rc-stat">
            <div class="rc-stat-num">77x</div>
            <div class="rc-stat-label">Average ROI across Recurly customers using AU</div>
          </div>
          <div class="rc-stat">
            <div class="rc-stat-num">18%</div>
            <div class="rc-stat-label">Of recovered revenue attributed to AU on average</div>
          </div>
          <div class="rc-stat">
            <div class="rc-stat-num">96M+</div>
            <div class="rc-stat-label">Card updates processed by Recurly in 2025</div>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">🎯 The Core Problem It Solves</h3>
          <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;">Involuntary churn — customers who leave not because they wanted to, but because a payment failed — is one of the largest and most preventable sources of subscriber loss for recurring businesses. Failed payments happen every day, and a large share of them are caused not by lack of funds or genuine cancellation intent, but simply by outdated card information.</p>
          <br>
          <p style="font-size:0.92rem;color:var(--darkgray);line-height:1.6;">When a card expires or is reissued, the subscriber probably doesn't think to update it in your system — especially if they haven't interacted with your product recently. They may not even know their card changed. Account Updater catches those changes before the charge ever fails.</p>
        </div>

        <h3 class="rc-subhead">💼 Key Business Benefits</h3>
        <div class="rc-2col">
          <div class="rc-opt">
            <div class="rc-oicon">🛡️</div>
            <h4>Prevent Involuntary Churn Before It Starts</h4>
            <p>Unlike dunning, which attempts to recover revenue after a payment has already failed, Account Updater acts before the failed charge ever occurs. It's the most upstream form of revenue protection available.</p>
            <span class="rc-tag">Proactive</span>
          </div>

          <div class="rc-opt">
            <div class="rc-oicon">💸</div>
            <h4>Reduce Failed Payment Volume</h4>
            <p>Fewer failed payments means less dunning overhead, fewer customer service inquiries about billing, and less operational cost spent chasing recoverable revenue.</p>
            <span class="rc-tag">Cost Reduction</span>
          </div>

          <div class="rc-opt">
            <div class="rc-oicon">🤝</div>
            <h4>Zero-Friction for Your Subscribers</h4>
            <p>Customers never have to update their card details themselves. No email asking them to update a payment method. No risk of them clicking through to cancel instead. The experience stays seamless.</p>
            <span class="rc-tag">CX Improvement</span>
          </div>

          <div class="rc-opt">
            <div class="rc-oicon">🔁</div>
            <h4>Works Alongside Dunning, Not Instead of It</h4>
            <p>Account Updater and Recurly's dunning logic are complementary. AU fixes known card changes before charging; dunning handles unexpected declines after the fact. Together they form a comprehensive revenue recovery strategy.</p>
            <span class="rc-tag">Complementary</span>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">💰 Pricing Considerations</h3>
          <p style="font-size:0.88rem;color:var(--gray);margin-bottom:16px;">How Account Updater is priced depends on your Recurly contract. Check your contract or speak with your Account Manager to understand which applies to you.</p>

          <div class="pricing-card free">
            <h4>✅ Included in Your Contract</h4>
            <p>For many Recurly customers, Account Updater is bundled into their subscription plan at no additional per-update cost. If this is your situation, there is no incremental cost to enable it — and no financial reason not to. You'll see the disclaimer in your Recurly settings, but enabling it will not trigger additional charges.</p>
          </div>

          <div class="pricing-card paid">
            <h4>💳 Usage-Based Pricing</h4>
            <p>For some customers, Account Updater is available as a per-successful-update service. A charge applies only when Recurly successfully retrieves updated card information — not for every lookup. Given the revenue protected per successful update, Recurly customers on this model still see strong positive ROI. Compare the cost per update against your average subscription value to assess the business case for your specific situation.</p>
          </div>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>Think About the Lifetime Value</h4>
            <p>When a subscription renews successfully instead of failing, you're not just recovering one month of revenue — you're protecting the subscriber's entire future lifetime value. A successful card update today can be worth many months or even years of continued subscription revenue.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <a class="rc-btn-prev" href="#what">← What Is It?</a>
          <label class="rc-btn-next" for="tab-consider">Next: Things to Consider →</label>
        </div>
      </div>
    </div>

  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
