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

  .rc-tabs input[type="radio"] { display: none; }

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

  .rc-num { font-size: 1.8rem; font-weight: 800; color: var(--yellow); }
  .rc-lbl { font-size: 0.8rem; color: var(--lightgray); text-transform: uppercase; letter-spacing: 0.5px; }

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

  #tab-what:checked ~ .rc-nav label[for="tab-what"],
  #tab-why:checked ~ .rc-nav label[for="tab-why"],
  #tab-consider:checked ~ .rc-nav label[for="tab-consider"],
  #tab-when-not:checked ~ .rc-nav label[for="tab-when-not"],
  #tab-how:checked ~ .rc-nav label[for="tab-how"],
  #tab-track:checked ~ .rc-nav label[for="tab-track"],
  #tab-pitch:checked ~ .rc-nav label[for="tab-pitch"] {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255,215,6,0.25);
  }

  .rc-panels .rc-panel { display: none; }

  #tab-what:checked ~ .rc-panels .rc-panel-what,
  #tab-why:checked ~ .rc-panels .rc-panel-why,
  #tab-consider:checked ~ .rc-panels .rc-panel-consider,
  #tab-when-not:checked ~ .rc-panels .rc-panel-when-not,
  #tab-how:checked ~ .rc-panels .rc-panel-how,
  #tab-track:checked ~ .rc-panels .rc-panel-track,
  #tab-pitch:checked ~ .rc-panels .rc-panel-pitch {
    display: block;
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

  .rc-video-card:hover { opacity: 0.88; text-decoration: none; }

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
  .rc-vtag { font-size: 11px; text-transform: uppercase; letter-spacing: 1px; color: var(--lightgray); margin-bottom: 6px; }
  .rc-vmeta h3 { font-size: 1.05rem; font-weight: 700; margin-bottom: 4px; color: var(--offwhite); }
  .rc-vmeta p { font-size: 0.85rem; color: var(--lightgray); margin: 0; }

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
  .rc-sbadge-orange,
  .rc-sbadge-verm,
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
  .rc-sbadge-orange { background: var(--orange); color: white; }
  .rc-sbadge-verm { background: var(--vermillion); color: white; }
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
  .rc-warning p { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

  .rc-callout {
    background: #F0F8FF;
    border: 1px solid #4A90D9;
    border-radius: 14px;
    padding: 16px 20px;
    margin-bottom: 24px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .rc-callout-icon { font-size: 20px; flex-shrink: 0; }
  .rc-callout p { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

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

  .rc-cl-header h3 { font-size: 0.88rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; color: var(--yellow); margin: 0; }

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

  .rc-clab { font-size: 0.88rem; color: var(--darkgray); line-height: 1.4; }
  .rc-clab span { display: block; font-size: 0.78rem; color: var(--gray); margin-top: 2px; }

  .rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 26px; }
  .rc-3col { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; margin-bottom: 24px; }

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

  .rc-tag-green { background: #2E7D32; color: white; }
  .rc-tag-orange { background: var(--orange); color: white; }

  .rc-wi {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 20px;
    border: 1px solid var(--lightgray);
    text-align: center;
  }

  .rc-wi-icon { font-size: 30px; margin-bottom: 10px; }
  .rc-wi h4 { font-size: 0.88rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
  .rc-wi p { font-size: 0.80rem; color: var(--gray); line-height: 1.5; margin: 0; }

  .rc-card {
    background: var(--offwhite);
    border-radius: 16px;
    padding: 28px;
    border: 1px solid var(--lightgray);
    margin-bottom: 24px;
  }

  .rc-subhead { font-size: 1rem; font-weight: 700; margin-bottom: 16px; color: var(--offblack); }

  .rc-stat-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; margin-bottom: 24px; }

  .rc-stat {
    background: var(--offblack);
    border-radius: 14px;
    padding: 24px 16px;
    text-align: center;
  }

  .rc-stat-num { font-size: 2rem; font-weight: 800; color: var(--yellow); }
  .rc-stat-label { font-size: 0.78rem; color: var(--lightgray); text-transform: uppercase; letter-spacing: 0.5px; margin-top: 4px; }

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

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

  .rc-btn-prev, .rc-btn-next, .rc-btn-disabled {
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

  .rc-btn-prev { background: white; color: var(--darkgray); cursor: pointer; }
  .rc-btn-next { background: var(--yellow); color: var(--offblack); border-color: var(--yellow); cursor: pointer; }
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
  .rc-link-sec { background: var(--offwhite); color: var(--darkgray); border: 1px solid var(--lightgray); }
  .rc-link-sec:hover { background: var(--brightgray); }

  .pricing-card {
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 16px;
    border: 1px solid var(--lightgray);
    background: var(--offwhite);
  }

  .pricing-card.free { border-left: 4px solid #2E7D32; }
  .pricing-card.paid { border-left: 4px solid var(--orange); }

  .pricing-card h4 { font-size: 0.95rem; font-weight: 700; color: var(--offblack); margin-bottom: 6px; }
  .pricing-card p { font-size: 0.86rem; color: var(--gray); line-height: 1.5; margin: 0; }

  @media (max-width: 640px) {
    .rc-hero h1 { font-size: 1.7rem; }
    .rc-2col, .rc-3col, .rc-stat-grid { grid-template-columns: 1fr; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-video-card { flex-direction: column; padding: 24px; }
    .rc-nav { flex-direction: column; }
    .rc-sec-nav { flex-direction: column; align-items: stretch; }
.rc-video-embed {
  margin-bottom: 0;
}

.rc-video-embed summary {
  list-style: none;
  cursor: pointer;
}

.rc-video-embed summary::-webkit-details-marker {
  display: none;
}

.rc-video-summary {
  display: block;
}

.rc-video-thumb {
  position: relative;
  border-radius: 14px;
  overflow: hidden;
  min-height: 280px;
  background:
    linear-gradient(rgba(13,13,11,0.45), rgba(13,13,11,0.65)),
    var(--darkgray);
  border: 1px solid var(--lightgray);
}

.rc-video-thumb-inner {
  position: absolute;
  inset: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 32px 24px;
}

.rc-video-thumb-play {
  width: 72px;
  height: 72px;
  border-radius: 50%;
  background: var(--yellow);
  color: var(--offblack);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 24px;
  font-weight: 800;
  margin-bottom: 18px;
  box-shadow: 0 4px 18px rgba(0,0,0,0.2);
}

.rc-video-thumb-text strong {
  display: block;
  font-size: 1.05rem;
  font-weight: 800;
  color: white;
  margin-bottom: 8px;
}

.rc-video-thumb-text span {
  display: block;
  max-width: 640px;
  font-size: 0.92rem;
  line-height: 1.55;
  color: var(--lightgray);
}

.rc-video-frame-wrap {
  position: relative;
  overflow: hidden;
  aspect-ratio: 1920 / 1080;
  border-radius: 14px;
  margin-top: 14px;
}

@media (max-width: 640px) {
  .rc-video-thumb {
    min-height: 220px;
  }

  .rc-video-thumb-inner {
    padding: 24px 18px;
  }

  .rc-video-thumb-text strong {
    font-size: 0.98rem;
  }

  .rc-video-thumb-text span {
    font-size: 0.86rem;
  }
}
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
    <label class="rc-tab-label" for="tab-what"><span class="rc-snum">1</span>What Is It?</label>
    <label class="rc-tab-label" for="tab-why"><span class="rc-snum">2</span>Why Use It?</label>
    <label class="rc-tab-label" for="tab-consider"><span class="rc-snum">3</span>Things to Consider</label>
    <label class="rc-tab-label" for="tab-when-not"><span class="rc-snum">4</span>When Not to Use It</label>
    <label class="rc-tab-label" for="tab-how"><span class="rc-snum">5</span>How to Enable It</label>
    <label class="rc-tab-label" for="tab-track"><span class="rc-snum">6</span>Tracking Impact</label>
    <label class="rc-tab-label" for="tab-pitch"><span class="rc-snum">✓</span>Pitch to Leadership</label>
  </nav>

  <div class="rc-panels">

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
          <div class="rc-wi">
            <div class="rc-wi-icon">🔄</div>
            <h4>Standard Account Updater</h4>
            <p>Supported for Visa, Mastercard, American Express, and Discover. Updates are fetched on a scheduled basis before renewal attempts.</p>
          </div>
          <div class="rc-wi">
            <div class="rc-wi-icon">⚡</div>
            <h4>Real-Time Account Updater (RTAU)</h4>
            <p>Available for Visa and Mastercard. Recurly receives a webhook the moment a card update is available — at any point in the subscription lifecycle, not just near renewal.</p>
          </div>
          <div class="rc-wi">
            <div class="rc-wi-icon">🏦</div>
            <h4>American Express Cardrefresher</h4>
            <p>Amex's proprietary version of AU. Requires a direct Amex merchant account and a US-based business. Configured separately within Recurly.</p>
          </div>
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
          <label class="rc-btn-next" for="tab-why">Next: Why Use It? →</label>
        </div>
      </div>
    </div>

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
            <p>Customers never have to update their card details themselves. No email asking them to update their payment method. No risk of them clicking through to cancel instead. The experience stays seamless.</p>
            <span class="rc-tag">CX Improvement</span>
          </div>
          <div class="rc-opt">
            <div class="rc-oicon">🔁</div>
            <h4>Works Alongside Dunning, Not Instead of It</h4>
            <p>Account Updater and Recurly's dunning (retry logic) are complementary. AU fixes known card changes before charging; dunning handles unexpected declines after the fact. Together they form a comprehensive revenue recovery strategy.</p>
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
          <label class="rc-btn-prev" for="tab-what">← What Is It?</label>
          <label class="rc-btn-next" for="tab-consider">Next: Things to Consider →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-consider">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🤔</div>
          <div>
            <h2>Things to Think About</h2>
            <p>Before enabling Account Updater, take a few minutes to review these considerations to ensure you get the most out of the feature.</p>
          </div>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>Good News: Most Merchants Are Already Set Up</h4>
            <p>For the majority of Recurly customers, there's little to no technical work required to enable Account Updater. The main steps are a configuration toggle and — if you're enabling American Express Cardrefresher — providing your Amex merchant account details.</p>
          </div>
        </div>

        <h3 class="rc-subhead">🔍 Key Questions to Ask Before You Enable</h3>
        <div class="rc-steps">
          <div class="rc-step">
            <div class="rc-sbadge">1</div>
            <div>
              <h3>How are you collecting card information?</h3>
              <p>Account Updater works only when Recurly has direct access to card data — meaning you're using Recurly.js or a Recurly-hosted checkout. If you're using your gateway's own checkout and passing a gateway token to Recurly, Recurly doesn't hold the card data and cannot run AU. In that case, you should enable AU with your gateway directly instead.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">2</div>
            <div>
              <h3>Are you already using Account Updater through your gateway?</h3>
              <p>If your payment gateway is already running Account Updater, enabling it again in Recurly would result in duplicate effort. You don't need both. However, if you're using Adyen, there is now a dedicated Recurly–Adyen RTAU integration that lets Recurly see Adyen-initiated card updates — this can actually extend your coverage rather than duplicate it.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">3</div>
            <div>
              <h3>What payment types make up your subscriber base?</h3>
              <p>Account Updater applies to credit and debit cards only. If a significant portion of your subscribers pay via ACH, bank transfer, PayPal, Apple Pay, Google Pay, or other alternative payment methods, those accounts won't benefit from AU. That's not a reason to skip it — just a realistic expectation-setter for coverage.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">4</div>
            <div>
              <h3>Do you use manual invoices?</h3>
              <p>Account Updater does not apply to one-time transactions or manual invoices. If your billing model relies primarily on manually issued invoices rather than automatic subscription charges, AU will have limited applicability.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">5</div>
            <div>
              <h3>Do you want to enable American Express Cardrefresher?</h3>
              <p>This requires a direct Amex merchant account (not an OptBlue/gateway-provided SE number) and your business must be based in the United States. You'll need your Amex Service Establishment (SE) number and Merchant Category Code (MCC) to complete setup.</p>
            </div>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">📋 A Note on Adyen Users</h3>
          <p style="font-size:0.88rem;color:var(--darkgray);line-height:1.6;">If Adyen is your primary gateway, Recurly now supports a dedicated Adyen Real-Time Account Updater integration. This is worth reviewing — Adyen's RTAU has some regional limitations. Enabling both Adyen RTAU and Recurly AU in parallel can maximize coverage across card brands and regions. Check the <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#adyen-realtime-account-updater" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">Recurly Adyen RTAU docs</a> for current details.</p>
        </div>

        <div class="rc-warning">
          <span class="rc-wicon">⚠️</span>
          <p><strong>One-time transactions are excluded.</strong> Account Updater is only applied to subscriptions — specifically to cards stored in Recurly's vault for recurring billing. It will not run on one-time charges or manual invoices regardless of how the feature is configured.</p>
        </div>

        <div class="rc-checklist">
          <div class="rc-cl-header"><span>✅</span><h3>Pre-Enablement Checklist</h3></div>
          <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You are using Recurly.js or Recurly-hosted checkout to collect card data<span>If using gateway tokens, enable AU with your gateway instead</span></div></div>
          <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You are not already running Account Updater through your gateway for the same card pool<span>Check with your payment ops team</span></div></div>
          <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Your subscriber base includes a meaningful volume of credit/debit card payers<span>AU does not apply to APMs</span></div></div>
          <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">If enabling Amex Cardrefresher: you have a direct Amex merchant account and a US business address<span>OptBlue accounts are not supported</span></div></div>
          <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">You have reviewed the pricing model that applies to your contract<span>Speak with your Account Manager if unsure</span></div></div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-why">← Why Use It?</label>
          <label class="rc-btn-next" for="tab-when-not">Next: When Not to Use It →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-when-not">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🚫</div>
          <div>
            <h2>When You Might Not Want to Use It</h2>
            <p>Account Updater is the right tool for most Recurly customers — but there are specific situations where enabling it in Recurly either doesn't apply or would create redundancy.</p>
          </div>
        </div>

        <div class="rc-callout">
          <span class="rc-callout-icon">ℹ️</span>
          <p>None of these situations are permanent disqualifiers. They are simply configurations worth understanding before you toggle AU on. If any apply to you, review them with your technical team or Recurly Account Manager.</p>
        </div>

        <div class="rc-steps">
          <div class="rc-step">
            <div class="rc-sbadge-orange">1</div>
            <div>
              <h3>You're already running AU through your gateway</h3>
              <p>If your gateway is already subscribed to an Account Updater service and is updating the card data in its own vault, running AU in Recurly as well would be redundant. In most cases, you should pick one place to run it.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge-orange">2</div>
            <div>
              <h3>You're using your gateway's hosted checkout and passing gateway tokens</h3>
              <p>If your checkout is powered by a gateway-native solution and you're sending a gateway token to Recurly rather than the raw card data, Recurly does not hold the actual card details. In this setup, you should enable AU with your gateway, not Recurly.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge-orange">3</div>
            <div>
              <h3>Your billing model relies primarily on manual invoices</h3>
              <p>Account Updater is designed for subscription-based, automatic recurring billing where a card is stored on file. If your primary billing workflow is manually issuing invoices, AU will have limited or no applicability to your billing flow.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge-orange">4</div>
            <div>
              <h3>You exclusively use Alternative Payment Methods</h3>
              <p>If your entire subscriber base pays via APMs — Apple Pay, Google Pay, SEPA, ACH, PayPal, etc. — Account Updater will not apply to any of your transactions. AU is a card-specific service.</p>
            </div>
          </div>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>Most Merchants Don't Fall Into These Categories</h4>
            <p>If you're using Recurly.js for checkout, billing credit or debit card subscribers on auto-renew, and not running AU elsewhere — you're a strong candidate to enable Account Updater today.</p>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">🔁 Not Sure? A Quick Diagnostic</h3>
          <div class="rc-2col">
            <div class="rc-opt">
              <div class="rc-oicon">✅</div>
              <h4>You should enable AU in Recurly if…</h4>
              <p>You use Recurly.js or Recurly-hosted checkout, have auto-renewing card subscribers, and are not running AU through your gateway for the same cards.</p>
              <span class="rc-tag rc-tag-green">Go for it</span>
            </div>
            <div class="rc-opt">
              <div class="rc-oicon">🔀</div>
              <h4>Enable AU with your gateway instead if…</h4>
              <p>You use gateway-hosted checkout and pass gateway tokens to Recurly. In this case, the gateway holds the card data and should run the update service.</p>
              <span class="rc-tag rc-tag-orange">Gateway side</span>
            </div>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-consider">← Things to Consider</label>
          <label class="rc-btn-next" for="tab-how">Next: How to Enable It →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-how">
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

  <details class="rc-video-embed">
    <summary class="rc-video-summary">
      <div class="rc-video-thumb">
        <div class="rc-video-thumb-inner">
          <div class="rc-video-thumb-play">▶</div>
          <div class="rc-video-thumb-text">
            <strong>Watch the walkthrough</strong>
            <span>Watch our Navigate CSM walk through enabling Account Updater step-by-step in your Recurly site.</span>
          </div>
        </div>
      </div>
    </summary>

    <div class="rc-video-frame-wrap">
      <iframe
        src="https://share.synthesia.io/embeds/videos/b86fe7bd-1f74-491f-8632-acebd4794615"
        loading="lazy"
        title="Navigate: Secure Your Revenue — Account Updater"
        allowfullscreen
        allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"
        style="position:absolute;width:100%;height:100%;top:0;left:0;border:none;margin:0;">
      </iframe>
    </div>
  </details>
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
          <label class="rc-btn-prev" for="tab-when-not">← When Not to Use It</label>
          <label class="rc-btn-next" for="tab-track">Next: Tracking Impact →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-track">
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
          <div class="rc-opt">
            <div class="rc-oicon">💰</div>
            <h4>Revenue Recovered via AU</h4>
            <p>The direct dollar amount of subscription revenue that was successfully charged because Account Updater updated the card before it was attempted.</p>
            <span class="rc-tag">Primary metric</span>
          </div>
          <div class="rc-opt">
            <div class="rc-oicon">📉</div>
            <h4>Failed Payment Rate (Card-based)</h4>
            <p>Track the rate of failed payments attributable to outdated card info. You should see this decline after enabling AU.</p>
            <span class="rc-tag">Secondary metric</span>
          </div>
          <div class="rc-opt">
            <div class="rc-oicon">🔄</div>
            <h4>AU Update Volume</h4>
            <p>The total number of card updates processed through Account Updater. Useful for understanding scale and managing costs if on usage-based pricing.</p>
            <span class="rc-tag">Operational</span>
          </div>
          <div class="rc-opt">
            <div class="rc-oicon">📊</div>
            <h4>AU as % of Total Recovery</h4>
            <p>What share of your total recovered revenue is coming from Account Updater vs. dunning vs. other methods?</p>
            <span class="rc-tag">Benchmark</span>
          </div>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>Pro Tip · Give It 60–90 Days Before Drawing Conclusions</h4>
            <p>Account Updater works over time as the cards in your vault age and as subscription renewal cycles come around. Give it at least two to three billing cycles before evaluating performance.</p>
          </div>
        </div>

        <div class="rc-card">
          <h3 class="rc-subhead">📈 For Your Navigate Program (Internal Tracking)</h3>
          <p style="font-size:0.88rem;color:var(--darkgray);line-height:1.6;margin-bottom:12px;">If you are tracking the Navigate program's impact, consider monitoring these signals to attribute AU-driven outcomes to the program:</p>
          <div class="rc-steps" style="margin-bottom:0;">
            <div class="rc-step"><div class="rc-sbadge">→</div><div><h3>AU Activation Rate</h3><p>What percentage of customers who accessed the Navigate AU learning path went on to enable AU?</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">→</div><div><h3>Pre/Post Revenue Recovery Comparison</h3><p>For accounts that enabled AU after the learning path, compare recovered revenue 90 days before vs. 90 days after enablement.</p></div></div>
            <div class="rc-step"><div class="rc-sbadge">→</div><div><h3>Involuntary Churn Delta</h3><p>Track whether accounts that enabled AU after Navigate engagement show measurable improvement in involuntary churn rate relative to a control group.</p></div></div>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-how">← How to Enable It</label>
          <label class="rc-btn-next" for="tab-pitch">Next: Pitch to Leadership →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-pitch">
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
          <div class="rc-step">
            <div class="rc-sbadge">Q</div>
            <div>
              <h3>"What's the cost?"</h3>
              <p>Depending on our contract, Account Updater is either included in our current Recurly subscription or available as a per-successful-update charge. Across Recurly's customer base, the average return is 77x.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">Q</div>
            <div>
              <h3>"Do we need engineering resources to set this up?"</h3>
              <p>No. Account Updater is enabled through a toggle in Recurly's Payment Settings. There is no code change or development work required for standard setup.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">Q</div>
            <div>
              <h3>"Are there any risks?"</h3>
              <p>The main thing to confirm is that we're not already running Account Updater through our payment gateway for the same card pool.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">Q</div>
            <div>
              <h3>"How quickly will we see results?"</h3>
              <p>Results build over 60–90 days as the feature works through our existing subscriber base. We can track impact directly in Recurly's Recovered Revenue dashboard.</p>
            </div>
          </div>
          <div class="rc-step">
            <div class="rc-sbadge">Q</div>
            <div>
              <h3>"Is this secure?"</h3>
              <p>Yes. Card network update programs operate through the same secure channels used for all card-network communications, and Recurly is PCI-compliant.</p>
            </div>
          </div>
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
          <label class="rc-btn-prev" for="tab-track">← Tracking Impact</label>
          <span class="rc-btn-disabled">🎉 You're Ready to Go!</span>
        </div>
      </div>
    </div>

  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
