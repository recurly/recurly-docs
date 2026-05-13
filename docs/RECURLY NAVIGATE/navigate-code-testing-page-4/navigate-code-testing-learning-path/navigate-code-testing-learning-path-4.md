---
title: Navigate Code Testing Learning Path 4
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
<title>Account Updater: How to Enable It — Recurly Navigate</title>
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

/* ── VIDEO CARD ── */
.rc-video-card {
  border: 1px solid var(--lightgray); border-radius: 14px;
  overflow: hidden; margin: 0 0 40px;
}
.rc-video-header {
  background: var(--offblack); padding: 16px 22px;
  display: flex; align-items: center; gap: 10px;
}
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-embed {
  position: relative; overflow: hidden; aspect-ratio: 16/9;
  background: var(--offblack);
}
.rc-video-embed iframe {
  position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none;
}
.rc-video-caption {
  padding: 12px 22px;
  font-size: .83rem; color: var(--gray); background: var(--brightgray);
  border-top: 1px solid var(--lightgray); line-height: 1.5;
}

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
.rc-step-content p strong { color: var(--darkgray); }
.rc-step-content a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-step-content a:hover { text-decoration: underline !important; }

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
.rc-callout-body a { color: var(--orange); font-weight: 600; text-decoration: none !important; }
.rc-callout-body a:hover { text-decoration: underline !important; }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body strong { color: var(--darkgray); }

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
  transition: background .15s; cursor: pointer;
}
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; }
.rc-checkbox-box {
  width: 22px; height: 22px; border-radius: 6px;
  border: 2px solid var(--lightgray); flex-shrink: 0;
  background: #fff; display: flex; align-items: center;
  justify-content: center; transition: all .18s; margin-top: 1px;
}
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-progress {
  padding: 10px 22px; background: var(--brightgray);
  border-top: 1px solid var(--lightgray);
  font-size: .78rem; color: var(--gray); font-weight: 600;
  display: flex; align-items: center; gap: 10px;
}
.rc-progress-bar-wrap { flex: 1; height: 5px; background: var(--lightgray); border-radius: 10px; overflow: hidden; }
.rc-progress-bar { height: 100%; background: var(--retain); border-radius: 10px; width: 0%; transition: width .3s ease; }

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
        <h1>How to Enable It</h1>
      </div>
      <p>Follow the direct implementation path to activate proactive card management — from Payment Settings through final configuration and disclosure.</p>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">3</span> How to enable it</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-sticky-link"><span class="rc-step-badge">4</span> Tracking impact</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case" class="rc-sticky-link"><span class="rc-step-badge">5</span> Pitch to leadership</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── VIDEO WALKTHROUGH ── -->
    <div class="rc-lp-section">
      <h2>📹 Trail guide walkthrough</h2>
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Navigate: Secure Your Revenue — Account Updater</h4>
          <span>~3 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe
            src="https://share.synthesia.io/embeds/videos/b86fe7bd-1f74-491f-8632-acebd4794615"
            loading="lazy"
            title="Navigate: Secure Your Revenue — Account Updater"
            allowfullscreen
            allow="encrypted-media; fullscreen; microphone; screen-wake-lock;">
          </iframe>
        </div>
        <div class="rc-video-caption">
          Watch our Navigate CSM walk through enabling Account Updater step-by-step in your Recurly site.
        </div>
      </div>
    </div>

    <!-- ── CORE SETUP STEPS ── -->
    <div class="rc-lp-section">
      <h2>🔧 Core setup</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Navigate to Payment Settings</h4>
            <p>Log in to your Recurly admin and go to <strong>Configuration → Payment Settings</strong>. Scroll to the Account Updater section and click the toggle to open the configuration modal.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Select your MasterCard MCC</h4>
            <p>In the card brand configuration box, use the search field under MasterCard to select your <strong>Merchant Category Code (MCC)</strong>. This is required for MasterCard updates.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Enter your American Express SE number</h4>
            <p>Input your 10-digit <strong>Service Establishment (SE)</strong> number in the American Express field. This enables direct communication with the AMEX network for card updates.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Accept the disclosure and confirm</h4>
            <p>Check the box to agree to the terms in the modal. <strong>Note:</strong> Account Updater is a best-effort proactive measure — it does not guarantee an update for every card event. Contact <a href="mailto:support@recurly.com">Recurly Support</a> with any pricing questions.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Save and confirm</h4>
            <p>Once you click "Enable," your status will update immediately. Recurly begins scanning for card updates within your stored payment methods right away.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Activation window</strong>
          <p>While the toggle is instant, card networks typically take 24–48 hours to complete the initial batch sync. Real-Time Account Updater (RTAU) will be active for your very next transaction attempt.</p>
        </div>
      </div>
    </div>

    <!-- ── SETUP CHECKLIST ── -->
    <div class="rc-lp-section">
      <h2>✅ Setup checklist</h2>
      <p>Check each item off as you complete it to confirm your setup is complete.</p>

      <div class="rc-checklist" id="rcChecklist">
        <div class="rc-checklist-header">
          <span style="font-size: 1rem;">⚙️</span>
          <h4>Before you finish</h4>
        </div>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Toggled on under Configuration → Payment Settings</strong>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>MasterCard MCC selected from the configuration dropdown</strong>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>American Express 10-digit SE number entered</strong>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Pricing and terms disclosure reviewed and checked</strong>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox" onchange="rcUpdateProgress()">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Settings saved — status shows "Enabled"</strong>
          </div>
        </label>

        <div class="rc-checklist-progress">
          <span id="rcProgressLabel">0 of 5 complete</span>
          <div class="rc-progress-bar-wrap">
            <div class="rc-progress-bar" id="rcProgressBar"></div>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Expert tip</strong>
          <p>Account Updater works most effectively alongside a strong dunning strategy. Always monitor your "Expired" decline codes in analytics to ensure dunning picks up any cards AU cannot resolve. See the <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank">Recurly Docs</a> for full detail.</p>
        </div>
      </div>
    </div>

    <!-- ── PATH NAVIGATION ── -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations" class="rc-btn-prev">← Things to consider</a>
      <span class="rc-lp-nav-indicator">4 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data" class="rc-btn-path">Next: Tracking impact →</a>
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
