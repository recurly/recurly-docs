---
title: Commerce Experiment
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
/* ── RECURLY BRAND TOKENS ── */
.rc-guide {
  --yellow:     #FFD706;
  --orange:     #FF8200;
  --vermillion: #FF5810;
  --salmon:     #FF9D88;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D73;
  --lightgray:  #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite:   #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
}

/* HERO */
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

/* PROGRESS NAV */
.rc-nav {
  background: var(--offwhite);
  border-bottom: 2px solid var(--brightgray);
  display: flex;
  overflow-x: auto;
  position: sticky;
  top: 0;
  z-index: 100;
  border-radius: 0;
  box-shadow: 0 2px 8px rgba(13,13,11,0.08);
}
.rc-nav button {
  padding: 14px 18px;
  border: none;
  background: none;
  cursor: pointer;
  font-size: 13px;
  font-weight: 600;
  color: var(--gray);
  white-space: nowrap;
  border-bottom: 3px solid transparent;
  transition: all 0.2s;
}
.rc-nav button.rc-active { color: var(--offblack); border-bottom-color: var(--yellow); }
.rc-nav button:hover:not(.rc-active) { color: var(--darkgray); }
.rc-nav button.rc-done { color: var(--orange); }
.rc-snum {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 22px;
  height: 22px;
  border-radius: 50%;
  font-size: 11px;
  background: var(--lightgray);
  color: var(--darkgray);
  margin-right: 6px;
  font-weight: 700;
}
.rc-nav button.rc-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-nav button.rc-done .rc-snum   { background: var(--orange); color: white; }

/* CONTAINER */
.rc-container { padding: 40px 0 80px; }

/* SECTIONS */
.rc-sec { display: none; }
.rc-sec.rc-active { display: block; }

/* SECTION HEADER */
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

/* VIDEO CARD */
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
.rc-video-card:hover { opacity: 0.88; }
.rc-video-alt { background: #32312D; margin-top: -8px; }
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
.rc-play-orange { background: var(--orange); color: white; }
.rc-vmeta { color: white; }
.rc-vtag { font-size: 11px; text-transform: uppercase; letter-spacing: 1px; color: var(--lightgray); margin-bottom: 6px; }
.rc-vmeta h3 { font-size: 1.05rem; font-weight: 700; margin-bottom: 4px; color: var(--offwhite); }
.rc-vmeta p  { font-size: 0.85rem; color: var(--lightgray); margin: 0; }

/* STEP CARDS */
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
.rc-sbadge-orange { background: var(--orange); color: white; }
.rc-sbadge-verm   { background: var(--vermillion); color: white; }
.rc-sbadge-dark   { background: var(--darkgray); color: var(--yellow); }
.rc-step h3 { font-size: 0.98rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
.rc-step p  { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* PRO TIP */
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
.rc-tip h4  { font-size: 0.82rem; font-weight: 700; color: var(--offblack); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 4px; }
.rc-tip p   { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

/* WARNING */
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

/* CHECKLIST */
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
  cursor: pointer;
}
.rc-cli:last-child { border-bottom: none; }
.rc-cli:hover { background: var(--brightgray); }
.rc-cb {
  width: 22px;
  height: 22px;
  border-radius: 6px;
  border: 2px solid var(--lightgray);
  flex-shrink: 0;
  margin-top: 1px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  color: transparent;
  transition: all 0.2s;
}
.rc-cli.rc-checked .rc-cb    { background: var(--yellow); border-color: var(--yellow); color: var(--offblack); }
.rc-cli.rc-checked .rc-clab  { text-decoration: line-through; color: var(--lightgray); }
.rc-clab { font-size: 0.88rem; color: var(--darkgray); line-height: 1.4; }
.rc-clab span { display: block; font-size: 0.78rem; color: var(--gray); margin-top: 2px; }

/* 2-COL OPTIONS GRID */
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
.rc-opt p  { font-size: 0.82rem; color: var(--gray); line-height: 1.5; margin: 0; }
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

/* 3-COL WHAT-IS GRID */
.rc-3col { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; margin-bottom: 24px; }
.rc-wi {
  background: var(--offwhite);
  border-radius: 14px;
  padding: 20px;
  border: 1px solid var(--lightgray);
  text-align: center;
}
.rc-wi-icon { font-size: 30px; margin-bottom: 10px; }
.rc-wi h4 { font-size: 0.88rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
.rc-wi p  { font-size: 0.80rem; color: var(--gray); line-height: 1.5; margin: 0; }

/* JOURNEY */
.rc-journey { display: flex; overflow-x: auto; padding-bottom: 8px; margin-bottom: 0; }
.rc-jstep  { flex: 1; min-width: 100px; text-align: center; position: relative; }
.rc-jstep::after { content: '→'; position: absolute; right: -12px; top: 10px; font-size: 18px; color: var(--lightgray); }
.rc-jstep:last-child::after { display: none; }
.rc-jdot {
  width: 38px; height: 38px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  font-size: 14px; display: flex; align-items: center; justify-content: center;
  margin: 0 auto 6px;
}
.rc-jlbl { font-size: 0.72rem; font-weight: 700; color: var(--darkgray); }

/* GENERIC CARD */
.rc-card {
  background: var(--offwhite);
  border-radius: 16px;
  padding: 28px;
  border: 1px solid var(--lightgray);
  margin-bottom: 24px;
}

/* COMPLETE BANNER */
.rc-complete {
  background: var(--offblack);
  border-radius: 16px;
  padding: 40px;
  text-align: center;
  margin-bottom: 28px;
  color: white;
}
.rc-complete h2 { font-size: 1.8rem; font-weight: 800; margin: 12px 0 10px; color: var(--yellow); }
.rc-complete p  { color: var(--lightgray); font-size: 0.95rem; margin: 0; }

/* SUBHEADING */
.rc-subhead { font-size: 1rem; font-weight: 700; margin-bottom: 16px; color: var(--offblack); }

/* SECTION NAV */
.rc-sec-nav {
  display: flex;
  justify-content: space-between;
  margin-top: 40px;
  padding-top: 28px;
  border-top: 1px solid var(--lightgray);
}
.rc-btn-prev, .rc-btn-next {
  padding: 12px 26px;
  border-radius: 10px;
  font-weight: 700;
  font-size: 0.88rem;
  cursor: pointer;
  transition: all 0.2s;
  border: none;
}
.rc-btn-prev { background: var(--offwhite); border: 1px solid var(--lightgray); color: var(--darkgray); }
.rc-btn-prev:hover { background: var(--brightgray); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-next:hover { opacity: 0.85; }
.rc-btn-next:disabled, .rc-btn-prev:disabled { opacity: 0.35; cursor: not-allowed; }

/* LINK BUTTONS */
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

/* RESPONSIVE */
@media (max-width: 640px) {
  .rc-hero h1 { font-size: 1.7rem; }
  .rc-2col, .rc-3col { grid-template-columns: 1fr; }
  .rc-hero-stats { gap: 20px; }
  .rc-sec-header { flex-direction: column; gap: 12px; }
  .rc-hero { padding: 36px 20px 32px; }
}

/* ============================================================
   JS — paste the block below into the JS tab in ReadMe
   Appearance → Custom CSS/JS → JavaScript tab
   ============================================================

function rcGoTo(n) {
  document.querySelectorAll('.rc-sec').forEach(function(s, i) {
    s.classList.toggle('rc-active', i === n);
  });
  document.querySelectorAll('.rc-nav button').forEach(function(b, i) {
    b.classList.remove('rc-active', 'rc-done');
    if (i === n) b.classList.add('rc-active');
    else if (i < n) b.classList.add('rc-done');
  });
  var guide = document.querySelector('.rc-guide');
  if (guide) guide.scrollIntoView({ behavior: 'smooth', block: 'start' });
}

function rcCheck(el) {
  el.classList.toggle('rc-checked');
}

*/

----------

<div class="rc-guide">

  <!-- HERO -->
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

  <!-- PROGRESS NAV -->
  <nav class="rc-nav" id="rcNav">
    <button class="rc-active" onclick="rcGoTo(0)"><span class="rc-snum">1</span>Intro</button>
    <button onclick="rcGoTo(1)"><span class="rc-snum">2</span>Plans</button>
    <button onclick="rcGoTo(2)"><span class="rc-snum">3</span>Storefront</button>
    <button onclick="rcGoTo(3)"><span class="rc-snum">4</span>Portal</button>
    <button onclick="rcGoTo(4)"><span class="rc-snum">5</span>Notifications</button>
    <button onclick="rcGoTo(5)"><span class="rc-snum">6</span>Integrations</button>
    <button onclick="rcGoTo(6)"><span class="rc-snum">✓</span>Launch!</button>
  </nav>

  <div class="rc-container">

    <!-- ── SECTION 0: INTRO ── -->
    <div class="rc-sec rc-active" id="rcSec0">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">🧭</div>
        <div>
          <h2>What is Recurly Commerce?</h2>
          <p>A quick orientation before you dive in — understand what you just installed and what it can do for your Shopify store.</p>
        </div>
      </div>

      <a href="https://navigate.recurly.com/commerce/launch-smarter/" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch First · Full Overview</div>
          <h3>Launch Smarter: Optimize your Recurly Commerce Setup</h3>
          <p>Start here for a full walkthrough of the platform before diving into setup.</p>
        </div>
      </a>

      <div class="rc-3col">
        <div class="rc-wi">
          <div class="rc-wi-icon">📦</div>
          <h4>Subscription Management</h4>
          <p>Create recurring product offers with flexible billing frequencies and discounts — all without touching code.</p>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-icon">🛍️</div>
          <h4>Native Shopify Integration</h4>
          <p>Everything lives inside your Shopify admin. No separate dashboard to juggle — it's all connected.</p>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-icon">💳</div>
          <h4>Revenue Recovery</h4>
          <p>Automatically retries failed payments and notifies customers so you lose less revenue to billing hiccups.</p>
        </div>
      </div>

      <div class="rc-card">
        <h3 class="rc-subhead">🗺️ Your Onboarding Journey</h3>
        <div class="rc-journey">
          <div class="rc-jstep"><div class="rc-jdot">📋</div><div class="rc-jlbl">Choose Plan</div></div>
          <div class="rc-jstep"><div class="rc-jdot">🏷️</div><div class="rc-jlbl">Create Sub Plans</div></div>
          <div class="rc-jstep"><div class="rc-jdot">🛒</div><div class="rc-jlbl">Set Up Storefront</div></div>
          <div class="rc-jstep"><div class="rc-jdot">👤</div><div class="rc-jlbl">Customer Portal</div></div>
          <div class="rc-jstep"><div class="rc-jdot">🔔</div><div class="rc-jlbl">Notifications</div></div>
          <div class="rc-jstep"><div class="rc-jdot">🔗</div><div class="rc-jlbl">Integrations</div></div>
        </div>
      </div>

      <div class="rc-warning">
        <span class="rc-wicon">⚠️</span>
        <p><strong>Before you begin:</strong> Make sure the Shopify user setting up Recurly Commerce has <strong>"Approve app charges"</strong> permission enabled. Without this, you won't be able to activate a plan. Check this under Shopify Admin → Settings → Users &amp; Permissions.</p>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div>
          <h4>Pro Tip · Set Your Goal First</h4>
          <p>Before configuring anything, ask yourself: <em>What products do I want to offer as subscriptions? How often should customers receive them?</em> Having a clear picture of your offer structure will make every step below feel fast and intuitive.</p>
        </div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" disabled>← Back</button>
        <button class="rc-btn-next" onclick="rcGoTo(1)">Next: Subscription Plans →</button>
      </div>
    </div>

    <!-- ── SECTION 1: PLANS ── -->
    <div class="rc-sec" id="rcSec1">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">🏷️</div>
        <div>
          <h2>Step 1: Create Your Subscription Plans</h2>
          <p>Your subscription plan defines <em>what</em> customers subscribe to, <em>how often</em> they're billed, and <em>what discounts</em> apply. This is the foundation everything else is built on.</p>
        </div>
      </div>

      <a href="https://docs.google.com/videos/d/1WzuHBw53KIPXWd2OlqYGM-qR61RIBAiyD3F5uSivW4g/edit?usp=sharing" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Step 1 Video</div>
          <h3>Subscription Plans Deep Dive</h3>
          <p>Watch how to create and configure your first subscription plan from scratch.</p>
        </div>
      </a>

      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Open Recurly Commerce → Subscription Plans</h3><p>In your Shopify admin, open the Recurly Commerce app and navigate to <strong>Subscription Plans</strong>. Click <strong>+ Create Offer</strong> in the top-right corner to get started.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Select Your Products</h3><p>Choose which Shopify products (SKUs) will be available as subscriptions. Your Shopify catalog must already be synced, and each product can only be assigned to one plan at a time.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Set Billing Frequency Options</h3><p>Click <strong>+ Add Option</strong> to define delivery frequencies (e.g., every 1 month, every 2 months). Offer multiple frequencies so customers can choose what fits their lifestyle.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Configure Discounts</h3><p>Assign a discount percentage to each frequency tier. Larger discounts for more frequent orders incentivize subscriptions and improve retention.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Configure Advanced Options (Optional)</h3><p>Enable gift subscriptions, product swaps, one-time add-ons, free trials, prepaid plans, or term commitments. These can be added now or anytime later.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">6</div><div><h3>Publish Your Offer</h3><p>When satisfied with your setup, click <strong>Publish Offer</strong> in the top-right. Your subscription plan is now live on the product pages you configured. 🎉</p></div></div>
      </div>

      <h3 class="rc-subhead">📐 Subscription Plan Types — What to Offer</h3>
      <div class="rc-2col">
        <div class="rc-opt"><div class="rc-oicon">🔄</div><h4>Recurring (Subscribe &amp; Save)</h4><p>The classic model. Customers receive products on a set schedule and save a percentage vs. one-time purchase. Great for consumables and everyday essentials.</p><span class="rc-tag">Most Common</span></div>
        <div class="rc-opt"><div class="rc-oicon">💳</div><h4>Prepaid Plans</h4><p>Customers pay upfront for multiple deliveries (e.g., 3-month bundle). Great for gift subscriptions and improving cash flow from day one.</p><span class="rc-tag">Higher AOV</span></div>
        <div class="rc-opt"><div class="rc-oicon">🎁</div><h4>Gift Subscriptions</h4><p>Let customers send subscriptions as gifts. Toggle the "Add gift option" setting when creating your plan to enable the gift flag at checkout.</p><span class="rc-tag">Boosts Acquisition</span></div>
        <div class="rc-opt"><div class="rc-oicon">🆓</div><h4>Free Trials</h4><p>Let customers try before they commit. Trial ending reminder emails are sent automatically 3 days before the trial ends.</p><span class="rc-tag">Reduces Friction</span></div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div><h4>Pro Tip · Discount Strategy</h4><p>Offering a slightly larger discount for your most frequent delivery option (e.g., 15% off monthly vs. 10% off every 2 months) pushes customers toward higher order frequency — which means more predictable revenue and better LTV for you.</p></div>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>✅</span><h3>Step 1 Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Shopify catalog is synced with Recurly Commerce<span>Confirm products appear when creating an offer</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">At least one subscription plan created and published<span>Check for green "Published" status</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Delivery frequencies and discounts configured<span>At least 1-2 frequency options per plan</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Advanced options reviewed (gifts, trials, add-ons)<span>Enable what's relevant to your business</span></div></div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(0)">← Intro</button>
        <button class="rc-btn-next" onclick="rcGoTo(2)">Next: Storefront Setup →</button>
      </div>
    </div>

    <!-- ── SECTION 2: STOREFRONT ── -->
    <div class="rc-sec" id="rcSec2">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">🛍️</div>
        <div>
          <h2>Step 2: Set Up Your Storefront</h2>
          <p>Your subscription widget is what shoppers see on your product pages. Getting this right is essential — it's the moment a customer decides to subscribe.</p>
        </div>
      </div>

      <a href="https://docs.google.com/videos/d/1xta8LjDuEVLA-l7ThtVSG2m1SlQ32RdjXih1Mo2gU6M/edit?usp=sharing" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Step 2 Video</div>
          <h3>Storefront Setup Walkthrough</h3>
          <p>See exactly how to install and customize the subscription widget on your product pages.</p>
        </div>
      </a>

      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Navigate to Storefront in Recurly Commerce</h3><p>In the Recurly Commerce app, go to the <strong>Storefront</strong> section. This is where you'll install and customize the subscription purchase widget.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Click Enable → Opens Shopify Theme Editor</h3><p>Clicking Enable launches the Shopify Theme Editor. Once there, click <strong>Save</strong> in the top-right corner to install the widget onto your theme.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Wait for the Green Published Badge</h3><p>Return to the Recurly Commerce app. Wait for the loading bar to complete — you'll see a green <strong>Published</strong> badge when the widget is live.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Customize the Widget's Look &amp; Feel</h3><p>Adjust text labels (e.g., change "Subscribe" to "Join the Club"), reorder options via drag-and-drop, and match colors, fonts, and spacing to your brand.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Save and Publish → Verify Live</h3><p>Click <strong>Save and Publish</strong>. Then visit a product page with an active subscription plan to confirm the widget appears correctly for shoppers.</p></div></div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div><h4>Pro Tip · Make Subscription the Default</h4><p>In the widget settings, reorder so the subscription option appears first — with the discount clearly visible. Defaulting to subscription significantly increases conversion rates. Lead with the value!</p></div>
      </div>

      <div class="rc-warning">
        <span class="rc-wicon">⚠️</span>
        <p><strong>Don't skip the test!</strong> After publishing, always navigate to an actual product page and verify the widget loads correctly. Check on both desktop and mobile. A widget that doesn't display means missed subscriptions from day one.</p>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>✅</span><h3>Step 2 Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Widget enabled and green Published badge confirmed<span>In the Storefront section of the app</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Widget branding customized (colors, fonts, labels)<span>Match your store's look and feel</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Subscription option order reviewed<span>Consider leading with the subscription option</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Widget tested on live product page (desktop + mobile)<span>Visit the page in an incognito window to see the customer view</span></div></div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(1)">← Plans</button>
        <button class="rc-btn-next" onclick="rcGoTo(3)">Next: Customer Portal →</button>
      </div>
    </div>

    <!-- ── SECTION 3: CUSTOMER PORTAL ── -->
    <div class="rc-sec" id="rcSec3">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">👤</div>
        <div>
          <h2>Step 3: Configure the Customer Portal</h2>
          <p>The Customer Portal is where your subscribers manage everything about their subscription. A well-configured portal reduces support tickets and keeps customers from cancelling.</p>
        </div>
      </div>

      <a href="https://docs.google.com/videos/d/1bB2CgaV8TvZ0J8XE4834PgdY9z99pR7fZyA9lNzz7Bo/edit?usp=sharing" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Step 3 Video</div>
          <h3>Customer Portal Configuration</h3>
          <p>Learn how to set up self-service options and brand your customer portal.</p>
        </div>
      </a>

      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Navigate to Customer Portal in the App</h3><p>In Recurly Commerce, click the <strong>Customer Portal</strong> tab. Note: this feature must be enabled on your plan before it becomes available.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Enable Self-Service Actions</h3><p>Toggle the subscriber permissions you want to allow. Each toggle applies immediately after saving, so review carefully before clicking Save.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Match Your Brand</h3><p>Customize portal colors, fonts, borders, and copy to align with your storefront. A seamless experience between your store and portal builds trust.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Set Up Cancellation Flows</h3><p>Configure what happens when a subscriber tries to cancel — offer a pause, a discount, or gather feedback. This is one of your most powerful churn prevention tools.</p></div></div>
      </div>

      <h3 class="rc-subhead">🎛️ Self-Service Permissions — What to Enable</h3>
      <div class="rc-2col">
        <div class="rc-opt"><div class="rc-oicon">⏭️</div><h4>Skip Next Delivery</h4><p>Let customers skip without cancelling. Perfect for vacations or "I still have some left" moments. Prevents a cancel that was really just a pause.</p><span class="rc-tag">Highly Recommended</span></div>
        <div class="rc-opt"><div class="rc-oicon">📅</div><h4>Change Renewal Date</h4><p>Allow customers to push or pull their next charge date. Flexibility here reduces "I got charged before I expected" cancellations.</p><span class="rc-tag">Recommended</span></div>
        <div class="rc-opt"><div class="rc-oicon">🔀</div><h4>Swap Products</h4><p>Let subscribers switch SKUs within a plan. Keep them in the ecosystem even when preferences change — swapping is always better than cancelling.</p><span class="rc-tag">Recommended</span></div>
        <div class="rc-opt"><div class="rc-oicon">⏸️</div><h4>Pause Subscription</h4><p>Offer an indefinite or limited pause instead of a hard cancel. Customers who pause are far more likely to resume than those who cancel outright.</p><span class="rc-tag">Churn Saver</span></div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div><h4>Pro Tip · Churn Prevention Flows</h4><p>Before a subscriber can cancel, show them a retention offer — a discount, a skip option, or a pause. This single feature can recover a significant percentage of would-be cancellations. Set it up before you go live so it's working from day one.</p></div>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>✅</span><h3>Step 3 Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Customer Portal feature confirmed active on your plan<span>Check Plan settings if this section is unavailable</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Self-service permissions configured (skip, swap, pause, etc.)<span>Enable at least skip + change renewal date</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Portal branding matched to your storefront<span>Colors, fonts, and copy aligned</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Cancellation/churn prevention flow configured<span>At minimum, offer a pause or discount before cancel</span></div></div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(2)">← Storefront</button>
        <button class="rc-btn-next" onclick="rcGoTo(4)">Next: Notifications →</button>
      </div>
    </div>

    <!-- ── SECTION 4: NOTIFICATIONS ── -->
    <div class="rc-sec" id="rcSec4">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">🔔</div>
        <div>
          <h2>Step 4: Configure Notifications</h2>
          <p>Subscribers who feel informed stay longer. Set up automated emails and SMS to keep customers in the loop at every stage — from first order to renewal.</p>
        </div>
      </div>

      <a href="https://docs.google.com/videos/d/1ucFUfkmnG4_sYTybWNzb08jfWTTWScYz_5UeZiFJmI0/edit?usp=sharing" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Step 4 Video</div>
          <h3>Notifications Setup</h3>
          <p>Walk through configuring transactional emails and SMS for the full subscriber lifecycle.</p>
        </div>
      </a>

      <a href="https://docs.google.com/videos/d/1cIEPUE97awZVH17kXggJC4oANRbOa8XV3CHM5jld_4k/edit?usp=sharing" target="_blank" class="rc-video-card rc-video-alt">
        <div class="rc-play rc-play-orange">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Related Video</div>
          <h3>Failed Payment Experience</h3>
          <p>Understand how Recurly Commerce handles failed payments and keeps revenue from slipping away.</p>
        </div>
      </a>

      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Go to Notifications in Recurly Commerce</h3><p>Open the Notifications tab in your app dashboard. Here you'll manage all transactional emails and SMS across the subscriber lifecycle.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Configure Transactional Emails</h3><p>Enable and customize automated emails for key events: order placed, upcoming renewal, failed payment, subscription paused, and more. These are free and built-in.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Enable SMS Alerts (Optional)</h3><p>Add concise SMS notifications for high-urgency moments like payment failures or upcoming order alerts. SMS drives faster action than email for billing issues.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Set Up Renewal Reminders</h3><p>Configure how many days before renewal to notify customers (1–180 days). This reduces "I didn't know I was going to be charged" disputes and builds trust.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>Brand Your Email Templates</h3><p>Customize subject lines, copy, and visual styling to match your brand. Branded emails feel personal — generic ones get ignored or marked as spam.</p></div></div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div><h4>Pro Tip · The Notifications That Matter Most</h4><p>Prioritize these three from day one: (1) <strong>Upcoming renewal reminder</strong> — sent 3–5 days before charge, prevents disputes. (2) <strong>Failed payment alert</strong> — fast communication recovers revenue before subscribers churn passively. (3) <strong>Order confirmation</strong> — builds excitement and trust after every charge.</p></div>
      </div>

      <div class="rc-warning">
        <span class="rc-wicon">⚠️</span>
        <p><strong>Compliance note:</strong> In many regions, renewal reminder emails are legally required before charging a customer. Make sure renewal reminders are enabled before you go live — this protects both your customers and your business.</p>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>✅</span><h3>Step 4 Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Order confirmation email enabled and branded<span>Sent immediately after every subscription charge</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Upcoming renewal reminder configured (3–7 days prior)<span>Reduces disputes and builds subscriber trust</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Failed payment notification enabled<span>Critical for passive churn prevention</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Email templates branded (logo, colors, tone of voice)<span>Consistency with your store builds trust</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">SMS alerts reviewed (enable if available on your plan)<span>High-urgency events benefit from SMS reach</span></div></div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(3)">← Customer Portal</button>
        <button class="rc-btn-next" onclick="rcGoTo(5)">Next: Integrations →</button>
      </div>
    </div>

    <!-- ── SECTION 5: INTEGRATIONS ── -->
    <div class="rc-sec" id="rcSec5">
      <div class="rc-sec-header">
        <div class="rc-sec-icon">🔗</div>
        <div>
          <h2>Step 5: Connect Your Integrations</h2>
          <p>Recurly Commerce works even harder when connected to your existing marketing and support tools. Link the platforms you already use to supercharge your subscriber experience.</p>
        </div>
      </div>

      <a href="https://docs.google.com/videos/d/1dstC6O60nzzcNvS-lsclxMDHb3EFuvx0_MnDoJbwDKE/edit?usp=sharing" target="_blank" class="rc-video-card">
        <div class="rc-play">▶</div>
        <div class="rc-vmeta">
          <div class="rc-vtag">📹 Watch · Step 5 Video</div>
          <h3>Integrations Overview</h3>
          <p>See how to connect Recurly Commerce to Klaviyo, Gorgias, Postscript, and more.</p>
        </div>
      </a>

      <h3 class="rc-subhead">🔌 Available Integrations</h3>
      <div class="rc-2col">
        <div class="rc-opt"><div class="rc-oicon">📧</div><h4>Klaviyo</h4><p>Sync subscriber data to Klaviyo for advanced email marketing flows — win-back campaigns, loyalty rewards, and personalized renewal series.</p><span class="rc-tag">Email &amp; SMS Marketing</span></div>
        <div class="rc-opt"><div class="rc-oicon">💬</div><h4>Postscript / Attentive</h4><p>Connect SMS marketing platforms for targeted subscriber campaigns beyond built-in transactional messages.</p><span class="rc-tag">SMS Marketing</span></div>
        <div class="rc-opt"><div class="rc-oicon">🎧</div><h4>Gorgias</h4><p>Surface subscriber data directly in your customer support tickets. Your support team sees subscription status, history, and next billing date without switching tabs.</p><span class="rc-tag">Customer Support</span></div>
        <div class="rc-opt"><div class="rc-oicon">📊</div><h4>Fivetran</h4><p>Pipe Recurly Commerce data into your data warehouse for advanced BI reporting, cohort analysis, and custom dashboards.</p><span class="rc-tag">Analytics / BI</span></div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">💡</span>
        <div><h4>Pro Tip · Start with Klaviyo</h4><p>If you're already on Klaviyo, connecting it to Recurly Commerce is the single highest-leverage integration to start with. Subscriber lifecycle events map directly to Klaviyo flows, and you can turn on campaigns that run on autopilot from day one.</p></div>
      </div>

      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>Navigate to Integrations in Recurly Commerce</h3><p>In the Recurly Commerce app, find the <strong>Integrations</strong> section. You'll see all available partner integrations listed here.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>Connect Your Priority Tool</h3><p>Choose the integration most relevant to your stack today. Each integration has a guided setup with API key fields and connection confirmation. Start with one and build from there.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Verify Data Is Flowing</h3><p>After connecting, trigger a test event (like a test subscription) and confirm data appears in your integrated platform. Don't assume — verify.</p></div></div>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>✅</span><h3>Step 5 Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Priority integration identified (e.g., Klaviyo, Gorgias)<span>Match to tools already in your marketing/support stack</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">At least one integration connected and tested<span>Confirm data flows through with a test event</span></div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Webhooks reviewed if using custom data pipelines<span>Advanced: available in the Settings → Webhooks section</span></div></div>
      </div>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(4)">← Notifications</button>
        <button class="rc-btn-next" onclick="rcGoTo(6)">Next: Launch! →</button>
      </div>
    </div>

    <!-- ── SECTION 6: LAUNCH ── -->
    <div class="rc-sec" id="rcSec6">
      <div class="rc-complete">
        <div style="font-size:48px;">🚀</div>
        <h2>You're Ready to Launch!</h2>
        <p>You've completed all the essential setup steps. Here's your final checklist before you go live.</p>
      </div>

      <div class="rc-checklist">
        <div class="rc-cl-header"><span>🏁</span><h3>Final Pre-Launch Checklist</h3></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Subscription plan published with correct products and frequencies</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Storefront widget live and tested on product pages (desktop + mobile)</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Customer Portal configured with self-service options and churn flow</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Renewal reminder and failed payment notifications active</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Email templates branded to match your store</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Priority integration(s) connected and verified</div></div>
        <div class="rc-cli" onclick="rcCheck(this)"><div class="rc-cb">✓</div><div class="rc-clab">Placed a test subscription order to verify end-to-end experience</div></div>
      </div>

      <div class="rc-card">
        <h3 class="rc-subhead">📈 What to Focus On After Launch</h3>
        <div class="rc-steps">
          <div class="rc-step"><div class="rc-sbadge rc-sbadge-orange">📊</div><div><h3>Monitor Your Analytics Dashboard</h3><p>Check General Analytics and Subscription Analytics weekly. Watch your MRR, churn rate, and active subscriber count — these are your north-star metrics.</p></div></div>
          <div class="rc-step"><div class="rc-sbadge rc-sbadge-verm">🔄</div><div><h3>Review Failed Payment Reports</h3><p>Passive churn from failed payments is the silent revenue killer. Review weekly and ensure your dunning (retry) settings are optimized.</p></div></div>
          <div class="rc-step"><div class="rc-sbadge rc-sbadge-dark">💌</div><div><h3>Survey Canceling Customers</h3><p>Use your cancellation flow to collect feedback. The reasons customers cancel tell you exactly what to fix — whether it's price, frequency, or product fit.</p></div></div>
        </div>
      </div>

      <div class="rc-tip">
        <span class="rc-tipicon">🎯</span>
        <div><h4>Your 30-Day Goal</h4><p>Focus on <strong>3 things</strong>: (1) Get your first 10 subscribers. (2) Make sure every subscriber receives their renewal reminder on time. (3) Review your cancellation reasons and iterate on your churn prevention flow. Everything else comes second.</p></div>
      </div>

      <h3 class="rc-subhead">📚 Additional Resources</h3>
      <a class="rc-link-btn" href="https://navigate.recurly.com/commerce/launch-smarter/" target="_blank">▶ Full On-Demand Video</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-commerce/docs/getting-started-rc" target="_blank">📖 Recurly Docs</a>
      <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com" target="_blank">🎧 Recurly Support</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.google.com/presentation/d/1hEvBMcNC7PpQj-Fl-IMz6QM6cLfLi92ECI5gq_A_XbI/edit" target="_blank">📊 Presentation Deck</a>

      <div class="rc-sec-nav">
        <button class="rc-btn-prev" onclick="rcGoTo(5)">← Integrations</button>
        <button class="rc-btn-next" disabled>🎉 You're Done!</button>
      </div>
    </div>

  </div><!-- /rc-container -->
</div><!-- /rc-guide -->
`}</HTMLBlock>

<br />
