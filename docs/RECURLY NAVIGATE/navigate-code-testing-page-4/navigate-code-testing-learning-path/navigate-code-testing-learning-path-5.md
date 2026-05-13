---
title: Navigate Code Testing Learning Path 5-2
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
<title>Account Updater: Pitch to Leadership — Recurly Navigate</title>
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

/* ── ANNOUNCEMENT BAR ── */
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

/* ── ONE-LINE PITCH CARD ── */
.rc-pitch-card {
  background: #0D0D0B !important;
  border-radius: 14px;
  padding: 36px 40px;
  text-align: center;
  margin: 0 0 40px;
  border: 1px solid rgba(255,255,255,0.08);
}
.rc-pitch-emoji { font-size: 2.4rem; margin-bottom: 12px; }
.rc-pitch-card h3 {
  font-size: 1.1rem; font-weight: 800; text-transform: uppercase;
  letter-spacing: 1px; color: #FF9D88 !important; margin: 0 0 16px;
}
.rc-pitch-quote {
  font-size: 1.05rem; color: #FFFDF2 !important; line-height: 1.7;
  max-width: 680px; margin: 0 auto;
  font-style: italic;
}
.rc-pitch-quote strong { color: #ffffff !important; font-style: normal; }

/* ── ACCENT CARD ── */
.rc-accent-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 24px 28px; margin: 20px 0;
}

/* ── NUMBERED & Q STEPS ── */
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
/* Q badge variant — salmon for Q&A */
.rc-step-num-q {
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--retain); color: var(--offblack);
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px;
}
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-step-content a:hover { text-decoration: underline !important; }

/* ── CALLOUT BOXES ── */
.rc-callout {
  border-radius: 10px; padding: 16px 20px; margin: 20px 0;
  display: flex; gap: 14px; align-items: flex-start;
}
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }

/* ── OFFICE HOURS CTA ── */
.rc-oh-cta {
  background: var(--offblack);
  border: 2px solid var(--yellow);
  border-radius: 14px;
  padding: 32px 36px;
  margin: 32px 0;
}
.rc-oh-cta h4 {
  color: var(--yellow); font-size: 1.05rem; font-weight: 800;
  text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px;
}
.rc-oh-cta p {
  color: var(--lightgray); font-size: .95rem; line-height: 1.6; margin: 0 0 20px;
}
.rc-oh-cta p strong { color: var(--offwhite); }
.rc-oh-btn {
  background: var(--yellow); color: var(--offblack) !important;
  text-decoration: none !important; padding: 12px 24px; border-radius: 10px;
  font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px;
  transition: all .2s; border: 2px solid var(--yellow);
}
.rc-oh-btn:hover { background: transparent; color: var(--yellow) !important; }

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
/* Completion milestone — not a link */
.rc-btn-complete {
  background: var(--brightgray); color: var(--offblack) !important;
  padding: 13px 24px; border-radius: 10px;
  font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px;
  border: 2px solid var(--yellow); cursor: default; user-select: none;
}

/* ── CONTINUE YOUR JOURNEY ── */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 {
  font-size: .78rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .9px; color: var(--gray); margin: 0 0 16px;
}
.rc-next-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 14px;
}
.rc-next-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 20px;
  text-decoration: none !important; color: inherit;
  display: flex; flex-direction: column; gap: 8px;
  transition: all .2s ease;
}
.rc-next-card:hover {
  border-color: var(--retain);
  box-shadow: 0 4px 16px rgba(255,157,136,0.15);
  transform: translateY(-2px);
}
.rc-next-card-tag {
  font-size: .68rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .8px; color: var(--retain); margin-bottom: 2px;
}
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 {
  font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0;
  line-height: 1.3;
}
.rc-next-card p {
  font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1;
}
.rc-next-card-arrow {
  font-size: .82rem; font-weight: 700; color: var(--orange);
  margin-top: 4px;
}
@media(max-width:768px){ .rc-next-grid { grid-template-columns: 1fr; } }
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
  .rc-pitch-card { padding: 28px 24px; }
  .rc-oh-cta { padding: 24px 20px; }
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
        <h1>Pitch to Leadership</h1>
      </div>
      <p>Build a data-backed case for proactive revenue recovery — with ROI benchmarks, a frictionless subscriber story, and answers to every leadership question.</p>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-sticky-link"><span class="rc-step-badge">2</span> Things to consider</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-sticky-link"><span class="rc-step-badge">3</span> How to enable it</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-sticky-link"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">5</span> Pitch to leadership</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── ONE-LINE PITCH ── -->
    <div class="rc-lp-section">
      <h2>🎤 The pitch</h2>
      <div class="rc-pitch-card">
        <div class="rc-pitch-emoji">🎯</div>
        <h3>The one-line pitch</h3>
        <p class="rc-pitch-quote">"Account Updater is a proactive <strong>best-effort assistant</strong> that automatically keeps our subscribers' card details up to date — recovering revenue we'd otherwise lose, with zero effort from customers."</p>
      </div>
    </div>

    <!-- ── BUSINESS CASE ── -->
    <div class="rc-lp-section">
      <h2>📋 The business case</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Stop unnecessary revenue leakage</h4>
            <p>Subscription failures are often caused by card expirations, not cancellations. AU resolves these lifecycle events before they trigger a decline.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Proven ROI benchmarks</h4>
            <p>Recurly customers using AU see an average of 18% of total recovered revenue attributed to this feature, with a 77x average return on investment.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Zero friction for subscribers</h4>
            <p>Card details refresh silently in the background. Customers don't receive "update your card" emails — they simply stay active.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Favorable cost-to-value ratio</h4>
            <p>The cost of Account Updater is consistently a small fraction of the monthly recurring revenue it successfully secures.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Rapid implementation</h4>
            <p>Enabling the service is a simple settings toggle. No engineering resources or development work are required for standard setup.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- ── Q&A ── -->
    <div class="rc-lp-section">
      <h2>❓ Anticipated questions</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"What's the cost?"</h4>
            <p>Depending on your contract, AU is either included or usage-based. The average return is 77x. <a href="mailto:support@recurly.com">Contact Recurly Support</a> to confirm your specific model.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Do we need engineering resources?"</h4>
            <p>No. Account Updater is enabled through a self-serve toggle in the Recurly admin. There is no code change or development work required.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Are there any risks?"</h4>
            <p>AU is a secure, PCI-compliant best-effort service. It is subject to card network participation rules and should be used as a primary layer alongside your existing dunning strategy.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"How quickly will we see results?"</h4>
            <p>Impact builds over 60–90 days as card cycles renew. Progress can be monitored directly in the Recurly Churn Management analytics dashboard.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- ── TIP ── -->
    <div class="rc-callout rc-callout-tip">
      <div class="rc-callout-icon">🎯</div>
      <div class="rc-callout-body">
        <strong>Ready to enable Account Updater?</strong>
        <p>Head to <strong>Configuration → Payment Settings</strong> in your Recurly admin and click Enable. The toggle takes seconds — the impact compounds over months.</p>
      </div>
    </div>

    <!-- ── OFFICE HOURS CTA ── -->
    <div class="rc-oh-cta">
      <h4>🗓️ Not sure yet? Book time with an expert first</h4>
      <p>Join a <strong>Customer Success Global Office Hours</strong> session to talk strategy with our CSMs. They'll walk you through all considerations, details, benefits, and implications of Account Updater for your subscription business.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- ── PATH NAVIGATION ── -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-btn-prev">← Tracking impact</a>
      <span class="rc-lp-nav-indicator">6 of 6</span>
      <span class="rc-btn-complete">🎉 Path complete!</span>
    </div>

    <!-- ── CONTINUE YOUR JOURNEY ── -->
    <div class="rc-next-steps">
      <h3>🧭 Continue your journey</h3>
      <div class="rc-next-grid">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-next-card">
          <div class="rc-next-card-tag">Recommended next</div>
          <div class="rc-next-card-icon">🔔</div>
          <h4>Dunning 101</h4>
          <p>AU handles card updates proactively. Dunning handles what happens after a charge still fails. Together they form a complete involuntary churn defense.</p>
          <div class="rc-next-card-arrow">Start path →</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-next-card">
          <div class="rc-next-card-tag">Explore the pillar</div>
          <div class="rc-next-card-icon">🛡️</div>
          <h4>All Retain paths</h4>
          <p>See every learning path in the Retain pillar — from Intelligent Retries to Pause Subscriptions and Cancel Save.</p>
          <div class="rc-next-card-arrow">View Retain →</div>
        </a>

        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon">🎙️</div>
          <h4>Global Office Hours</h4>
          <p>Bring your retention questions to our CSMs live. Sessions run weekly — no agenda required, just show up.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>

      </div>
    </div>

    <!-- ── RESOURCES ── -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" class="rc-resource-link">📖 Recurly Docs: Account Updater</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-resource-link">🌐 Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" class="rc-resource-link">🧭 Return to start</a>
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
</body>
</html>
`}</HTMLBlock>

<br />