---
title: 'Dunning 101: The Basics'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* ── HOST-THEME BACKGROUND OVERRIDE ── */
body { background: #ffffff !important; }
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  --retain: #FF9D88;
  background: #ffffff;
  font-family: 'Segoe UI', system-ui, sans-serif;
}
* { box-sizing: border-box; }

/* ── HOST-THEME ARMOR ── */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark     { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light    { color: var(--offblack); font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section  { color: var(--offblack); font-size: 1rem; }

/* ── LAYOUT ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link {
  color: var(--gray); text-decoration: none !important; font-weight: 700;
  font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s;
}
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none; background: var(--yellow); color: var(--offblack);
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rc-announce-link {
  color: var(--offblack) !important; font-weight: 800; text-decoration: none !important;
  white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10);
  border-radius: 6px; transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close {
  background: none; border: none; font-size: 1.4rem; line-height: 1;
  cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45;
  transition: opacity 0.2s; flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center;
  border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45);
  color: #FF9D88; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 {
  font-size: 2.4rem; font-weight: 800; line-height: 1.15;
  color: var(--offwhite); margin: 0;
}
.rc-hero > p {
  font-size: 1rem; opacity: .85; max-width: 640px;
  margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6;
}

/* ── HERO STATS ── */
.rc-hero-stats {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 0;
  border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px;
}
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label {
  font-size: .72rem; font-weight: 600; letter-spacing: .8px;
  text-transform: uppercase; color: var(--lightgray); line-height: 1.3;
}

/* ── NAV — STICKY + COLLAPSED (LP Overview) ── */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: #FF9D88;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none; display: flex; align-items: center;
  padding: 15px 24px; cursor: pointer; user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label {
  display: inline-flex; align-items: center; gap: 8px;
  font-weight: 800; font-size: .88rem; letter-spacing: 0.6px;
  text-transform: uppercase; color: var(--offblack);
}
.rc-nav-chevron {
  font-size: .72rem; color: var(--offblack); opacity: 0.55;
  line-height: 1; transition: transform 0.25s ease;
}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link {
  color: var(--offblack) !important; text-decoration: none !important;
  font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase;
  padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
/* Active item — map pin icon only, no persistent background */
.rc-sticky-link-active { font-weight: 800; }
.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px;
  color: var(--offblack); display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── STAT STRIP (content variant — pillar-colored numbers, context sentences) ── */
.rc-stat-strip {
  display: grid; grid-template-columns: repeat(3, 1fr);
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; overflow: hidden; margin: 0 0 48px;
}
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: #FF9D88; line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label {
  font-size: .7rem; font-weight: 700; letter-spacing: .8px;
  text-transform: uppercase; color: var(--gray); margin-bottom: 10px;
}
.rc-stat-tile-context {
  font-size: .8rem; color: var(--darkgray); line-height: 1.5;
  padding-top: 10px; border-top: 1px solid var(--brightgray);
}

/* ── TOC CARDS ── */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card {
  display: grid; grid-template-columns: 44px 1fr 32px;
  align-items: center; gap: 16px;
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 18px 22px; transition: all .2s ease;
}
/* Armor overrides — explicit border-bottom on both states */
.rc-guide a.rc-toc-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-toc-card:hover {
  border-color: #FF9D88; border-bottom: 1px solid #FF9D88 !important;
  box-shadow: 0 4px 14px rgba(255,157,136,0.12); transform: translateX(3px);
}
.rc-toc-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0;
}
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: var(--lightgray); text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #FF9D88; }

/* ── PATH NAV BUTTONS ── */
.rc-lp-nav {
  display: flex; align-items: center; justify-content: space-between;
  gap: 16px; margin: 40px 0 16px;
}
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start {
  background: var(--brightgray); color: var(--gray); padding: 13px 24px;
  border-radius: 10px; font-weight: 700; font-size: .9rem;
  border: 2px solid var(--lightgray); cursor: default;
}
.rc-guide a.rc-btn-path {
  background: var(--yellow); color: var(--offblack) !important;
  text-decoration: none !important; padding: 13px 28px; border-radius: 10px;
  font-weight: 800; font-size: .95rem; display: inline-flex;
  align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid var(--yellow);
}
.rc-guide a.rc-btn-path:hover {
  background: transparent !important; color: var(--offblack) !important;
  border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important;
}

/* ── RESOURCES ── */
.rc-resources {
  background: var(--brightgray); border-left: 4px solid #FF9D88;
  border-radius: 10px; padding: 20px 24px; margin: 32px 0 0;
}
.rc-resources h3 {
  font-size: .75rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .9px; color: var(--gray); margin: 0 0 12px;
  display: flex; align-items: center; gap: 8px;
}
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link {
  color: var(--gray) !important; text-decoration: underline !important;
  text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important;
  font-weight: 500; font-size: .88rem; transition: all .18s;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-guide .rc-resource-link:hover {
  color: var(--offblack) !important; text-decoration: underline !important;
  text-underline-offset: 3px; text-decoration-color: #FF9D88 !important;
}

/* ── FOOTER ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label {
  font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px;
  color: var(--darkgray); background: var(--brightgray); padding: 4px 10px;
  border-radius: 6px; margin-right: 4px;
}
.rc-footer-link {
  color: var(--gray); text-decoration: none !important; font-weight: 600;
  font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px;
}
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility {
  display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px;
  padding-top: 24px; border-top: 1px solid var(--brightgray);
}

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-stat-tile + .rc-stat-tile { border-left: none; border-top: 1px solid var(--lightgray); }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
}
</style>

<div class="rc-guide">

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR (hidden by default — add rc-active class to show) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live dunning strategy session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://drive.google.com/thumbnail?id=16DEzXygnfOAnosP9dTcKi2hhmvNaMuY-&sz=w100-h100" alt="Retain"> Retain
      </div>
      <div class="rc-lp-hero-title">
        <h1>Dunning 101</h1>
      </div>
      <p>Recover the revenue you've already earned — by building a dunning strategy that works quietly in the background.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">27%</div>
          <div class="rc-hero-stat-label">Average recovery rate</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Up to 40%</div>
          <div class="rc-hero-stat-label">Of churn is passive</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">3–5%</div>
          <div class="rc-hero-stat-label">Uplift from optimization</div>
        </div>
      </div>
    </div>

    <!-- NAVIGATION MENU (sticky, collapsed) -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Dunning 101
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-passive-churn" class="rc-sticky-link">The passive churn problem</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configure" class="rc-sticky-link">Configure your dunning</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy" class="rc-sticky-link">Your dunning email strategy</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-beyond-inbox" class="rc-sticky-link">Beyond the inbox</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics" class="rc-sticky-link">Measuring what matters</a>
          </div>
        </div>
      </div>
    </details>

    <!-- INTRO -->
    <div class="rc-lp-section">
      <p>Payment failures are a normal part of running a subscription business — industry-wide, 5–10% of renewal payments fail on the first attempt. Most businesses treat this as an unavoidable cost. The ones who treat it as a recoverable revenue opportunity consistently outperform their peers.</p>
      <p>This learning path covers dunning from the ground up: what passive churn is actually costing your business, how Recurly's dunning system works, how to configure and optimize it correctly, and how to measure whether your changes are working. Each Micro-Path is self-contained — work through them in order for the full picture, or jump directly to the topic most relevant right now.</p>
    </div>

    <!-- STAT STRIP — content variant (pillar-colored numbers + context sentences) -->
    <div class="rc-stat-strip">
      <div class="rc-stat-tile">
        <div class="rc-stat-tile-num">27%</div>
        <div class="rc-stat-tile-label">Average recovery rate</div>
        <div class="rc-stat-tile-context">Roughly 1 in 4 failed payments gets recovered through dunning across Recurly merchants.</div>
      </div>
      <div class="rc-stat-tile">
        <div class="rc-stat-tile-num">40%</div>
        <div class="rc-stat-tile-label">Passive churn ceiling</div>
        <div class="rc-stat-tile-context">Up to 40% of subscriber losses come from failed payments, not intentional cancellations.</div>
      </div>
      <div class="rc-stat-tile">
        <div class="rc-stat-tile-num">3–5%</div>
        <div class="rc-stat-tile-label">Optimization uplift</div>
        <div class="rc-stat-tile-context">Following the 10 dunning best practices typically adds 3–5 percentage points to your recovery rate.</div>
      </div>
    </div>

    <!-- TABLE OF CONTENTS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-route rc-fa-section"></i> What's in this path</h2>

      <div class="rc-toc-list">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-passive-churn" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>The passive churn problem</h4>
            <p>Understand the real cost of passive churn and how Recurly's dunning system works mechanically — before touching any configuration.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configure" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Configure your dunning</h4>
            <p>Walk through your dunning setup step by step — window lengths, multiple campaigns, plan assignments, and email deliverability.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Your dunning email strategy</h4>
            <p>Build dunning emails that actually get opened — covering branding, cadence, message arc, dynamic variables, and progressive urgency.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-beyond-inbox" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Beyond the inbox</h4>
            <p>Add in-app payment recovery banners and understand your full recovery toolkit — from Account Updater to Recurly Engage.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Measuring what matters</h4>
            <p>Track the three core dunning metrics, benchmark against industry peers, and build a review cadence that keeps your setup improving over time.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

      </div>
    </div>

    <!-- TRANSITION TEXT + PATH NAV (Start state) -->
    <p style="font-size:.95rem; color:var(--darkgray); line-height:1.65; margin:0 0 8px;">Work through each Micro-Path in order for the complete picture, or jump directly to whichever topic is most pressing for your business right now.</p>

    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">Overview &middot; 14 pages total</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-passive-churn" class="rc-btn-path">Start path: The passive churn problem →</a>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning management</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning benchmarks</a>
        <a href="https://share.synthesia.io/7f58d816-a65c-42f4-950d-59b11953d1aa" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-circle-play"></i> Trail guide: Easy wins — dunning done right</a>
        <a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-circle-play"></i> Webinar: Stop the leak — how to optimize dunning for growth</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-optimization-checklist" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Dunning optimization checklist</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <!-- FOOTER NAV -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Dunning 101 &mdash; learning path:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-passive-churn" class="rc-footer-link">The passive churn problem</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-configure" class="rc-footer-link">Configure your dunning</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-strategy" class="rc-footer-link">Your dunning email strategy</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-beyond-inbox" class="rc-footer-link">Beyond the inbox</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-metrics" class="rc-footer-link">Measuring what matters</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-review-resources" class="rc-footer-link">Review &amp; resources</a>
        </div>

        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>

      </div>
    </div>

  </div><!-- /rc-content-wrap -->
</div><!-- /rc-guide -->
`}</HTMLBlock>

<br />
