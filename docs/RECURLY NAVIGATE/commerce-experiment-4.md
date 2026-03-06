---
title: Commerce Experiment 4
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>{\`
<style>
  :root {
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
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .rc-guide {
    font-family: 'Segoe UI', system-ui, sans-serif;
    color: var(--darkgray);
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
    margin-bottom: 24px;
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
    transition: border-color 0.2s, box-shadow 0.2s, opacity 0.2s, background 0.2s, color 0.2s;
    cursor: pointer;
  }

  .rc-tab-label:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 8px rgba(255, 215, 6, 0.2);
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

  #tab-intro:checked ~ .rc-nav label[for="tab-intro"],
  #tab-plans:checked ~ .rc-nav label[for="tab-plans"],
  #tab-storefront:checked ~ .rc-nav label[for="tab-storefront"],
  #tab-portal:checked ~ .rc-nav label[for="tab-portal"],
  #tab-notifications:checked ~ .rc-nav label[for="tab-notifications"],
  #tab-integrations:checked ~ .rc-nav label[for="tab-integrations"],
  #tab-launch:checked ~ .rc-nav label[for="tab-launch"] {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255, 215, 6, 0.25);
  }

  .rc-panels .rc-panel {
    display: none;
  }

  #tab-intro:checked ~ .rc-panels .rc-panel-intro,
  #tab-plans:checked ~ .rc-panels .rc-panel-plans,
  #tab-storefront:checked ~ .rc-panels .rc-panel-storefront,
  #tab-portal:checked ~ .rc-panels .rc-panel-portal,
  #tab-notifications:checked ~ .rc-panels .rc-panel-notifications,
  #tab-integrations:checked ~ .rc-panels .rc-panel-integrations,
  #tab-launch:checked ~ .rc-panels .rc-panel-launch {
    display: block;
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

  .rc-video-alt {
    background: #32312D;
    margin-top: -8px;
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

  .rc-play-orange {
    background: var(--orange);
    color: white;
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
    box-shadow: 0 4px 16px rgba(13, 13, 11, 0.08);
  }

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

  .rc-3col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-opt,
  .rc-wi,
  .rc-card {
    background: var(--offwhite);
    border: 1px solid var(--lightgray);
    border-radius: 16px;
  }

  .rc-opt {
    padding: 18px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .rc-opt:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 12px rgba(255, 215, 6, 0.2);
  }

  .rc-oicon { font-size: 22px; margin-bottom: 8px; }

  .rc-opt h4,
  .rc-wi h4 {
    font-size: 0.92rem;
    font-weight: 700;
    margin-bottom: 5px;
    color: var(--offblack);
  }

  .rc-opt p,
  .rc-wi p {
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

  .rc-wi {
    padding: 20px;
    text-align: center;
  }

  .rc-wi-icon {
    font-size: 30px;
    margin-bottom: 10px;
  }

  .rc-card {
    padding: 28px;
    margin-bottom: 24px;
  }

  .rc-journey {
    display: flex;
    overflow-x: auto;
    padding-bottom: 8px;
  }

  .rc-jstep {
    flex: 1;
    min-width: 100px;
    text-align: center;
    position: relative;
  }

  .rc-jstep::after {
    content: '→';
    position: absolute;
    right: -12px;
    top: 10px;
    font-size: 18px;
    color: var(--lightgray);
  }

  .rc-jstep:last-child::after { display: none; }

  .rc-jdot {
    width: 38px;
    height: 38px;
    border-radius: 50%;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 6px;
  }

  .rc-jlbl {
    font-size: 0.72rem;
    font-weight: 700;
    color: var(--darkgray);
  }

  .rc-complete {
    background: var(--offblack);
    border-radius: 16px;
    padding: 40px;
    text-align: center;
    margin-bottom: 28px;
    color: white;
  }

  .rc-complete h2 {
    font-size: 1.8rem;
    font-weight: 800;
    margin: 12px 0 10px;
    color: var(--yellow);
  }

  .rc-complete p {
    color: var(--lightgray);
    font-size: 0.95rem;
    margin: 0;
  }

  .rc-subhead {
    font-size: 1rem;
    font-weight: 700;
    margin-bottom: 16px;
    color: var(--offblack);
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
    .rc-2col, .rc-3col { grid-template-columns: 1fr; }
    .rc-hero-stats { gap: 20px; }
    .rc-sec-header { flex-direction: column; gap: 12px; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-video-card { flex-direction: column; padding: 24px; }
    .rc-nav { flex-direction: column; }
    .rc-sec-nav { flex-direction: column; align-items: stretch; }
  }
</style>

<div class="rc-guide rc-tabs">
  <input type="radio" name="rc-tabs" id="tab-intro" checked>
  <input type="radio" name="rc-tabs" id="tab-plans">
  <input type="radio" name="rc-tabs" id="tab-storefront">
  <input type="radio" name="rc-tabs" id="tab-portal">
  <input type="radio" name="rc-tabs" id="tab-notifications">
  <input type="radio" name="rc-tabs" id="tab-integrations">
  <input type="radio" name="rc-tabs" id="tab-launch">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Getting Started</div>
    <h1>Welcome to Recurly Commerce</h1>
    <p>You've installed the app — now let's get your subscriptions live. Follow these 6 steps and you'll be up and running in no time.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">6</div><div class="rc-lbl">Setup Steps</div></div>
      <div><div class="rc-num">~60</div><div class="rc-lbl">Min to Launch</div></div>
      <div><div class="rc-num">0</div><div class="rc-lbl">Code Required</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <label class="rc-tab-label" for="tab-intro"><span class="rc-snum">1</span>Intro</label>
    <label class="rc-tab-label" for="tab-plans"><span class="rc-snum">2</span>Subscription Plans</label>
    <label class="rc-tab-label" for="tab-storefront"><span class="rc-snum">3</span>Storefront Setup</label>
    <label class="rc-tab-label" for="tab-portal"><span class="rc-snum">4</span>Customer Portals</label>
    <label class="rc-tab-label" for="tab-notifications"><span class="rc-snum">5</span>Notifications</label>
    <label class="rc-tab-label" for="tab-integrations"><span class="rc-snum">6</span>Integrations</label>
    <label class="rc-tab-label" for="tab-launch"><span class="rc-snum">✓</span>Launch!</label>
  </nav>

  <div class="rc-panels">

    <div class="rc-panel rc-panel-intro">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🧭</div>
          <div>
            <h2>What is Recurly Commerce?</h2>
            <p>A quick orientation before you dive in — understand what you just installed and what it can do for your Shopify store.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <span class="rc-btn-disabled">← Back</span>
          <label class="rc-btn-next" for="tab-plans">Next: Subscription Plans →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-plans">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🏷️</div>
          <div>
            <h2>Step 1: Create Your Subscription Plans</h2>
            <p>Your subscription plan defines <em>what</em> customers subscribe to, <em>how often</em> they're billed, and <em>what discounts</em> apply. This is the foundation everything else is built on.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-intro">← Intro</label>
          <label class="rc-btn-next" for="tab-storefront">Next: Storefront Setup →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-storefront">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🛍️</div>
          <div>
            <h2>Step 2: Set Up Your Storefront</h2>
            <p>Your subscription widget is what shoppers see on your product pages. Getting this right is essential — it's the moment a customer decides to subscribe.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-plans">← Subscription Plans</label>
          <label class="rc-btn-next" for="tab-portal">Next: Customer Portals →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-portal">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">👤</div>
          <div>
            <h2>Step 3: Configure the Customer Portal</h2>
            <p>The Customer Portal is where your subscribers manage everything about their subscription.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-storefront">← Storefront Setup</label>
          <label class="rc-btn-next" for="tab-notifications">Next: Notifications →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-notifications">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🔔</div>
          <div>
            <h2>Step 4: Configure Notifications</h2>
            <p>Subscribers who feel informed stay longer.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-portal">← Customer Portals</label>
          <label class="rc-btn-next" for="tab-integrations">Next: Integrations →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-integrations">
      <div class="rc-sec">
        <div class="rc-sec-header">
          <div class="rc-sec-icon">🔗</div>
          <div>
            <h2>Step 5: Connect Your Integrations</h2>
            <p>Link the platforms you already use to supercharge your subscriber experience.</p>
          </div>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-notifications">← Notifications</label>
          <label class="rc-btn-next" for="tab-launch">Next: Launch! →</label>
        </div>
      </div>
    </div>

    <div class="rc-panel rc-panel-launch">
      <div class="rc-sec">
        <div class="rc-complete">
          <div style="font-size:48px;">🚀</div>
          <h2>You're Ready to Launch!</h2>
          <p>You've completed all the essential setup steps. Here's your final checklist before you go live.</p>
        </div>

        <div class="rc-sec-nav">
          <label class="rc-btn-prev" for="tab-integrations">← Integrations</label>
          <span class="rc-btn-disabled">🎉 You're Done!</span>
        </div>
      </div>
    </div>

  </div>
</div>
\`}</HTMLBlock>
`}</HTMLBlock>
