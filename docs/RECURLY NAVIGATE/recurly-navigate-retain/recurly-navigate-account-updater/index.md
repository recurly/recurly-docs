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

  .rc-wi-icon { font-size: 30px; margin-bottom: 10px; }
  .rc-wi h4 { font-size: 0.88rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
  .rc-wi p { font-size: 0.80rem; color: var(--gray); line-height: 1.5; margin: 0; }

  .rc-steps { display: flex; flex-direction: column; gap: 16px; margin-bottom: 28px; }
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

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

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
    .rc-3col { grid-template-columns: 1fr; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-hero { padding: 36px 20px 32px; }
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
          <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;">When a customer's credit or debit card expires, gets lost or stolen, or is reissued by their bank, the card number or expiration date changes. If you're charging that card on a recurring basis — like a subscription renewal — that charge will simply fail.</p>
        </div>

        <div class="rc-3col">
          <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Standard Account Updater</h4><p>Updates are fetched on a scheduled basis before renewal attempts.</p></div>
          <div class="rc-wi"><div class="rc-wi-icon">⚡</div><h4>Real-Time Account Updater</h4><p>Recurly receives a webhook the moment a card update is available.</p></div>
          <div class="rc-wi"><div class="rc-wi-icon">🏦</div><h4>Amex Cardrefresher</h4><p>Amex's proprietary version of AU.</p></div>
        </div>

        <div class="rc-tip">
          <span class="rc-tipicon">💡</span>
          <div>
            <h4>The Bottom Line</h4>
            <p>Account Updater quietly fixes outdated card details behind the scenes.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <span class="rc-btn-disabled">← Back</span>
          <label class="rc-btn-next" for="tab-why">Next: Why Use It? →</label>
        </div>
      </div>
    </div>

    <!-- Add remaining panels here -->

  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>

<br />
