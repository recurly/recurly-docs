---
title: Navigate Code Testing Learning Path 5
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
<title>Account Updater: Tracking Impact — Recurly Navigate</title>
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

/* ── KPI GRID (2x2) ── */
.rc-kpi-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin: 0 0 32px; }
.rc-kpi-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 20px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease;
}
.rc-kpi-card:hover { border-color: var(--retain); box-shadow: 0 4px 16px rgba(255,157,136,0.12); transform: translateY(-2px); }
.rc-kpi-icon { font-size: 1.4rem; line-height: 1; }
.rc-kpi-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-kpi-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; }

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
.rc-step-content strong { color: var(--darkgray); }
.rc-step-content code {
  background: var(--brightgray); color: var(--offblack);
  padding: 2px 7px; border-radius: 4px; font-size: .82rem; font-family: monospace;
}

/* ── VIDEO EMBED (within step — supporting content) ── */
.rc-step-video {
  border-radius: 10px; margin-top: 16px;
  border: 1px solid var(--lightgray); overflow: hidden;
  background: var(--offblack);
}
.rc-step-video-label {
  background: var(--offblack); padding: 9px 14px;
  display: flex; align-items: center; gap: 8px;
}
.rc-step-video-label span {
  font-size: .72rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .7px; color: var(--lightgray);
}
.rc-step-video-label::before {
  content: '▶'; font-size: .6rem; color: var(--retain); flex-shrink: 0;
}
.rc-step-video-frame {
  position: relative; overflow: hidden; aspect-ratio: 16/9;
}
.rc-step-video-frame iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-step-video-caption {
  font-size: .8rem; color: var(--gray); padding: 8px 14px 10px;
  background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5;
}

/* ── ACCENT CARD ── */
.rc-accent-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 24px 28px; margin: 20px 0;
}
.rc-accent-card.rc-accent-retain { border-left: 4px solid var(--retain); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 10px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 14px; }

/* Mini audit step inside card */
.rc-audit-step {
  display: flex; align-items: flex-start; gap: 12px;
  padding-top: 14px; border-top: 1px solid var(--brightgray);
}
.rc-audit-badge {
  width: 28px; height: 28px; border-radius: 8px;
  background: var(--retain); color: var(--offblack);
  display: flex; align-items: center; justify-content: center;
  font-size: .78rem; font-weight: 800; flex-shrink: 0; margin-top: 1px;
}
.rc-audit-step p { font-size: .9rem; color: var(--darkgray); line-height: 1.6; margin: 0; }

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
  background: var(--offblack); border: 2px solid var(--yellow);
  border-radius: 14px; padding: 32px 36px; margin: 32px 0;
}
.rc-oh-cta h4 { color: var(--yellow); font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray); font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
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
  .rc-kpi-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-oh-cta { padding: 24px 20px; }
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
        <h1>Tracking Impact</h1>
      </div>
      <p>Quantify your retention success by isolating revenue recovered through card updates — using Churn Management dashboards and granular transaction exports.</p>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link"><span class="rc-step-badge">5</span> Pitch to leadership</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── KPIs ── -->
    <div class="rc-lp-section">
      <h2>📏 Key performance indicators</h2>
      <div class="rc-kpi-grid">
        <div class="rc-kpi-card">
          <div class="rc-kpi-icon">💰</div>
          <h4>Recovered revenue (AU)</h4>
          <p>The total currency value successfully processed on cards updated by AU prior to the billing attempt. This is your primary ROI signal.</p>
        </div>
        <div class="rc-kpi-card">
          <div class="rc-kpi-icon">📉</div>
          <h4>Involuntary churn rate</h4>
          <p>The percentage of subscribers lost due to payment failure. This should decrease as AU proactively handles card lifecycle events.</p>
        </div>
        <div class="rc-kpi-card">
          <div class="rc-kpi-icon">📋</div>
          <h4>Renewal count by AU</h4>
          <p>The raw volume of subscription invoices that renewed successfully because of a card update. Found in Renewal Invoices reporting.</p>
        </div>
        <div class="rc-kpi-card">
          <div class="rc-kpi-icon">🔍</div>
          <h4>Remaining "expired" declines</h4>
          <p>Found in Renewal Declines — identifies cards AU could not update (subject to network participation), helping you refine your dunning strategy.</p>
        </div>
      </div>
    </div>

    <!-- ── DASHBOARD NAVIGATION ── -->
    <div class="rc-lp-section">
      <h2>📍 Navigating your dashboards</h2>
      <div class="rc-steps">

        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Recovered Revenue dashboard</h4>
            <p>Navigate to <strong>Analytics → Churn Management → Recovered Revenue</strong>. Use the <strong>Recovered Revenue by Method</strong> chart to see the contribution of card updates compared to dunning.</p>
            <div class="rc-step-video">
              <div class="rc-step-video-label"><span>Trail guide walkthrough</span></div>
              <div class="rc-step-video-frame">
                <iframe
                  src="https://share.synthesia.io/embeds/videos/57b979ea-216b-4e3f-8215-cd6060e32107"
                  loading="lazy"
                  title="Trail Guide: Recovered Revenue Dashboard"
                  allowfullscreen
                  allow="encrypted-media; fullscreen;">
                </iframe>
              </div>
              <div class="rc-step-video-caption">Walk through the Recovered Revenue dashboard with your Navigate CSM.</div>
            </div>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Renewal Invoices — the "Other Outcomes" chart</h4>
            <p>Go to <strong>Analytics → Churn Management → Renewal Invoices</strong>. Review the <strong>Invoices with Other Outcomes</strong> chart to see the specific count of invoices saved by AU logic.</p>
          </div>
        </div>

        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Renewal Declines dashboard</h4>
            <p>Navigate to <strong>Analytics → Churn Management → Renewal Declines</strong>. Filter for <strong>Expired Card</strong> codes to see remaining friction points that AU could not resolve.</p>
          </div>
        </div>

      </div>
    </div>

    <!-- ── ADVANCED AUDIT ── -->
    <div class="rc-lp-section">
      <h2>📁 Advanced audit</h2>
      <div class="rc-accent-card rc-accent-retain">
        <h4>Invoices Summary Export</h4>
        <p>For raw data verification, use the <strong>Invoices Summary Export</strong> under <strong>Analytics → Exports</strong>. This report provides underlying proof of card updates at the transaction level.</p>
        <div class="rc-audit-step">
          <div class="rc-audit-badge">A</div>
          <p><strong>Filter by <code>recovery_reason</code>:</strong> Choose <code>account_updater</code> transactions to isolate AU collections and calculate your exact AU-attributed revenue.</p>
        </div>
      </div>
    </div>

    <!-- ── OFFICE HOURS CTA ── -->
    <div class="rc-oh-cta">
      <h4>🗓️ Need strategic support?</h4>
      <p>Join our <strong>Customer Success Global Office Hours</strong>. Meet live with our CSMs to walk through your analytics, work through roadblocks, and get strategic advice on optimizing your revenue recovery stack.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- ── TIP ── -->
    <div class="rc-callout rc-callout-tip">
      <div class="rc-callout-icon">💡</div>
      <div class="rc-callout-body">
        <strong>Expert insight: The 90-day rule</strong>
        <p>AU impact is cumulative. It takes roughly 90 days to see the full stabilized effect on your recovery metrics. Use this window to establish your new churn baseline before drawing conclusions.</p>
      </div>
    </div>

    <!-- ── PATH NAVIGATION ── -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-btn-prev">← How to enable it</a>
      <span class="rc-lp-nav-indicator">5 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-btn-path">Next: Pitch to leadership →</a>
    </div>

    <!-- ── RESOURCES ── -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/recovered-revenue" target="_blank" class="rc-resource-link">📈 Recovered Revenue dashboard</a>
        <a href="https://docs.recurly.com/docs/renewal-invoices" target="_blank" class="rc-resource-link">📋 Renewal Invoices report</a>
        <a href="https://docs.recurly.com/docs/renewal-declines" target="_blank" class="rc-resource-link">📉 Renewal Declines dashboard</a>
        <a href="https://docs.recurly.com/docs/transaction-export" target="_blank" class="rc-resource-link">📂 Transactions export guide</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
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
