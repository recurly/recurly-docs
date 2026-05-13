---
title: Navigate Code Testing Learning Path 3
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Account Updater: Things to Consider — Recurly Navigate</title>
<style>
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
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── ANNOUNCEMENT BAR (hidden — add class "rc-active" to show) ── */
.rc-announce-bar {
  display: none; background: var(--yellow); color: var(--offblack);
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link {
  color: var(--offblack) !important; font-weight: 800; text-decoration: none !important;
  white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close {
  background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer;
  color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── TOP BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45);
  color: var(--retain); font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* ── NAVIGATE QUICK LINKS NAV ── */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--retain); box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none; display: flex; align-items: center;
  padding: 15px 24px; cursor: pointer; user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
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
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge {
  display: inline-flex; align-items: center; justify-content: center;
  width: 20px; height: 20px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1;
}
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── NUMBERED STEPS ── */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step {
  display: grid; grid-template-columns: 40px 1fr;
  gap: 16px; align-items: flex-start;
  padding: 18px 0; border-bottom: 1px solid var(--brightgray);
}
.rc-step:last-child { border-bottom: none; }
.rc-step-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px;
}
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* ── CALLOUT BOXES ── */
.rc-callout {
  border-radius: 10px; padding: 16px 20px; margin: 20px 0;
  display: flex; gap: 14px; align-items: flex-start;
}
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-steps + .rc-callout { margin-top: 32px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body strong { color: var(--darkgray); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body strong { color: var(--darkgray); }

/* ── ACCENT CARD (for limitations, notes) ── */
.rc-accent-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 24px 28px; margin: 20px 0;
}
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card p:last-child { margin: 0; }
.rc-accent-card ul {
  font-size: .9rem; color: var(--gray); line-height: 1.75;
  padding-left: 20px; margin: 0;
}
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }
.rc-accent-card ul li em { color: var(--darkgray); font-style: normal; font-weight: 600; }

/* ── DIAGNOSTIC GRID (2-col) ── */
.rc-diag-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0 32px; }
.rc-diag-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 22px; display: flex; flex-direction: column; gap: 8px;
  transition: all .2s ease;
}
.rc-diag-card:hover { border-color: var(--retain); box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-diag-icon { font-size: 1.4rem; line-height: 1; }
.rc-diag-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-diag-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-diag-tag {
  display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px;
  font-size: .7rem; font-weight: 700; letter-spacing: .5px;
  background: var(--offblack); color: var(--yellow); width: fit-content;
}

/* ── SECTION DIVIDER ── */
.rc-divider { border: none; border-top: 1px solid var(--lightgray); margin: 36px 0; }

/* ── INTERACTIVE CHECKLIST ── */
.rc-checklist {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; overflow: hidden; margin: 20px 0 32px;
}
.rc-checklist-header {
  padding: 14px 22px; background: var(--offblack);
  display: flex; align-items: center; gap: 10px;
}
.rc-checklist-header h4 {
  font-size: .82rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .8px; color: var(--yellow); margin: 0;
}
.rc-checklist-item {
  padding: 14px 22px; border-bottom: 1px solid var(--brightgray);
  display: flex; align-items: flex-start; gap: 14px;
  transition: background .15s;
  cursor: pointer;
}
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }

/* Hide the native checkbox */
.rc-checklist-item input[type="checkbox"] {
  position: absolute; opacity: 0; width: 0; height: 0;
}
/* Custom checkbox box */
.rc-checkbox-box {
  width: 22px; height: 22px; border-radius: 6px;
  border: 2px solid var(--lightgray); flex-shrink: 0;
  background: #fff; display: flex; align-items: center;
  justify-content: center; transition: all .18s; margin-top: 1px;
}
/* Checked state */
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-body .rc-checkbox-box,
.rc-checklist-item.rc-checked .rc-checkbox-box {
  background: var(--offblack); border-color: var(--offblack);
}
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-body .rc-checkbox-box::after,
.rc-checklist-item.rc-checked .rc-checkbox-box::after {
  content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1;
}
/* Alternative: JS-free approach using label */
.rc-checklist-label {
  display: flex; align-items: flex-start; gap: 14px;
  width: 100%; cursor: pointer;
}
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong {
  font-size: .9rem; font-weight: 700; color: var(--offblack);
  display: block; margin-bottom: 2px;
}
.rc-checklist-text span {
  font-size: .8rem; color: var(--gray); line-height: 1.4; display: block;
}
/* Checked text styling */
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-label .rc-checklist-text strong {
  color: var(--gray); text-decoration: line-through;
}

/* Progress indicator */
.rc-checklist-progress {
  padding: 10px 22px; background: var(--brightgray);
  border-top: 1px solid var(--lightgray);
  font-size: .78rem; color: var(--gray); font-weight: 600;
  display: flex; align-items: center; gap: 10px;
}
.rc-progress-bar-wrap {
  flex: 1; height: 5px; background: var(--lightgray); border-radius: 10px; overflow: hidden;
}
.rc-progress-bar {
  height: 100%; background: var(--retain); border-radius: 10px;
  width: 0%; transition: width .3s ease;
}

/* ── PATH NAVIGATION BUTTONS ── */
.rc-lp-nav {
  display: flex; align-items: center; justify-content: space-between;
  gap: 16px; margin: 40px 0 16px;
}
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-prev {
  background: transparent; color: var(--offblack) !important;
  text-decoration: none !important; padding: 13px 24px; border-radius: 10px;
  font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid var(--lightgray); transition: all .2s;
}
.rc-btn-prev:hover { border-color: var(--offblack); }
.rc-btn-path {
  background: var(--yellow); color: var(--offblack) !important;
  text-decoration: none !important; padding: 13px 28px; border-radius: 10px;
  font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px;
  transition: all .2s; border: 2px solid var(--yellow);
}
.rc-btn-path:hover { background: transparent; color: var(--offblack) !important; }

/* ── RESOURCES ── */
.rc-resources {
  background: var(--brightgray); border-left: 4px solid var(--retain);
  border-radius: 10px; padding: 20px 24px; margin: 32px 0 0;
}
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link {
  color: var(--darkgray) !important; text-decoration: underline !important;
  text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important;
  font-weight: 500; font-size: .88rem; transition: all .18s;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-resource-link:hover { color: var(--offblack) !important; text-decoration-color: var(--retain) !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link {
  color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .9rem;
  transition: color .2s; display: inline-flex; align-items: center; gap: 5px;
}
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; }
  .rc-diag-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live session on this topic.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO ── -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> Retain
      </div>
      <div class="rc-lp-hero-title">
        <h1>Things to Consider</h1>
      </div>
      <p>Confirm technical readiness by reviewing tokenization compatibility and understanding bank-level participation rules before you enable.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">77x</div><div class="rc-hero-stat-label">Average ROI</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">18%</div><div class="rc-hero-stat-label">Of recovered revenue</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">96M+</div><div class="rc-hero-stat-label">Card updates in 2025</div></div>
      </div>
    </div>

    <!-- ── NAVIGATE QUICK LINKS NAV ── -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigate Quick Links <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Account Updater
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why use it?</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">2</span> Things to consider</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-sticky-link"><span class="rc-step-badge">3</span> How to enable it</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-sticky-link"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link"><span class="rc-step-badge">5</span> Pitch to leadership</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── IS AU RIGHT FOR YOU ── -->
    <div class="rc-lp-section">
      <h2>🔍 Is Account Updater right for you?</h2>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Good news: Most merchants are already set up</strong>
          <p>For the majority of Recurly customers, enabling AU is a simple configuration toggle. Recurly's Real-Time Account Updater (RTAU) now covers major networks globally — including AMEX and Discover — on supported gateways.</p>
        </div>
      </div>

      <h2 style="margin-top: 36px;">🔑 Key questions to ask before you enable</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>How are you tokenizing payment data?</h4>
            <p>Recurly AU works seamlessly with Recurly.js and Recurly-hosted checkouts. If you use external gateway tokenization, Recurly can still run AU as long as the token is managed within the Recurly vault.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Is your gateway already running AU?</h4>
            <p>Running AU in both Recurly and your gateway can be redundant. However, many merchants choose to run Recurly AU alongside gateway RTAU to ensure coverage across all regions and card networks.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Are you an American Express merchant?</h4>
            <p>Modern RTAU now handles AMEX globally for many gateways. Legacy "Cardrefresher" is only required for specific direct-AMEX configurations and is generally not needed for new integrations.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- ── LIMITATIONS ── -->
    <div class="rc-lp-section">
      <h2>⚠️ Network &amp; issuer limitations</h2>
      <p>AU is highly effective, but success is subject to card network participation rules. A card may not update due to any of the following:</p>

      <div class="rc-accent-card rc-accent-orange">
        <ul>
          <li><strong>Bank participation:</strong> Not all global issuing banks participate in the automated update network.</li>
          <li><strong>Card type exclusions:</strong> Prepaid cards and certain specialized debit cards are typically ineligible for automated updates.</li>
          <li><strong>Closed accounts:</strong> Updates are only available for <em>replacement</em> cards. If a customer closes an account entirely, no new data is generated.</li>
          <li><strong>Visa opt-out:</strong> Some Visa issuers allow cardholders to manually opt out of sharing updated details with merchants.</li>
        </ul>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Stored billing info required</strong>
          <p>Account Updater requires a Billing Info object to exist in the Recurly vault. It will not run on guest checkouts where card details are not saved for future use.</p>
        </div>
      </div>

      <div class="rc-accent-card rc-accent-retain" style="margin-top: 20px;">
        <h4>📋 A note on Adyen users</h4>
        <p>Recurly supports a dedicated Adyen RTAU integration. For maximum efficiency, we recommend enabling both Adyen RTAU and Recurly AU to ensure comprehensive global coverage across all regions and card networks.</p>
      </div>
    </div>

    <!-- ── QUICK DIAGNOSTIC ── -->
    <div class="rc-lp-section">
      <h2>⚡ Quick diagnostic</h2>
      <div class="rc-diag-grid">
        <div class="rc-diag-card">
          <div class="rc-diag-icon">✅</div>
          <h4>Enable AU in Recurly if…</h4>
          <p>You have credit/debit cards stored in the Recurly vault and want to proactively ensure they remain valid, regardless of gateway-level services.</p>
          <span class="rc-diag-tag">Recommended</span>
        </div>
        <div class="rc-diag-card">
          <div class="rc-diag-icon">🔀</div>
          <h4>Check gateway config if…</h4>
          <p>You are using a third-party hosted checkout that does not pass card metadata or tokens back to Recurly for storage in the vault.</p>
          <span class="rc-diag-tag">Gateway Focus</span>
        </div>
      </div>
    </div>

    <!-- ── INTERACTIVE CHECKLIST ── -->
    <div class="rc-lp-section">
      <hr class="rc-divider" style="margin-top: 0;">
      <h2>✅ Pre-enablement checklist</h2>
      <p>Work through these before moving to the next step. Check each item off as you confirm it.</p>

      <div class="rc-checklist" id="rcChecklist">
        <div class="rc-checklist-header">
          <span style="font-size: 1rem;">✅</span>
          <h4>Before you enable</h4>
        </div>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Stored billing info exists in the Recurly vault</strong>
            <span>Credit/debit tokens and raw cards are both eligible</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Identified whether you need Cardrefresher or modern RTAU</strong>
            <span>RTAU is preferred for global AMEX support on new integrations</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Coordinated with payment ops to avoid overlapping gateway fees</strong>
            <span>Verify whether your gateway's AU is "Always On" by default</span>
          </div>
        </label>

        <div class="rc-checklist-progress">
          <span id="rcProgressLabel">0 of 3 complete</span>
          <div class="rc-progress-bar-wrap">
            <div class="rc-progress-bar" id="rcProgressBar"></div>
          </div>
        </div>
      </div>
    </div>

    <!-- ── PATH NAVIGATION ── -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-btn-prev">← Why use it?</a>
      <span class="rc-lp-nav-indicator">3 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-btn-path">Next: How to enable it →</a>
    </div>

    <!-- ── RESOURCES ── -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" class="rc-resource-link">📖 Recurly Docs: Account Updater</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- ── FOOTER NAV ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-footer-link">Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits" class="rc-footer-link">1. Why use it?</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-footer-link">2. Things to consider</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-footer-link">3. How to enable it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-footer-link">4. Tracking impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-footer-link">5. Pitch to leadership</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>

<script>
function rcUpdateProgress() {
  var checklist = document.getElementById('rcChecklist');
  var boxes = checklist.querySelectorAll('input[type="checkbox"]');
  var checked = 0;
  boxes.forEach(function(box) {
    var item = box.closest('.rc-checklist-item');
    if (box.checked) {
      checked++;
      item.style.background = 'rgba(255,157,136,0.06)';
      box.nextElementSibling.style.background = 'var(--offblack)';
      box.nextElementSibling.style.borderColor = 'var(--offblack)';
      box.nextElementSibling.innerHTML = '<span style="color:var(--yellow);font-size:.75rem;font-weight:800;line-height:1;">✓</span>';
      item.querySelector('strong').style.textDecoration = 'line-through';
      item.querySelector('strong').style.color = 'var(--gray)';
    } else {
      item.style.background = '';
      box.nextElementSibling.style.background = '#fff';
      box.nextElementSibling.style.borderColor = 'var(--lightgray)';
      box.nextElementSibling.innerHTML = '';
      item.querySelector('strong').style.textDecoration = '';
      item.querySelector('strong').style.color = 'var(--offblack)';
    }
  });
  var total = boxes.length;
  var pct = Math.round((checked / total) * 100);
  document.getElementById('rcProgressBar').style.width = pct + '%';
  document.getElementById('rcProgressLabel').textContent = checked + ' of ' + total + ' complete';
}
</script>
</body>
</html>
`}</HTMLBlock>

<br />
