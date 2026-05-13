---
title: Navigate Code Testing Learning Path Payment Hubs Review Resources
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. Host-theme Armor — MUST be at the top */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* 2. Global Variables & Base Styles */
html { scroll-behavior: smooth; scroll-padding-top: 80px; }
.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  --scale:     #FF5810;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }

/* 3. Layout Wrappers */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px 60px; }

/* 4. Hero (Topo Background) */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,88,16,0.20); border: 1px solid rgba(255,88,16,0.45);
  color: var(--scale); font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px !important; height: 13px !important; object-fit: contain; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }

.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); }

/* 5. Sticky Nav (Scale Case: White Text) */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--scale);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #fff; }
.rc-nav-chevron { font-size: .72rem; color: #fff; opacity: 0.8; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(255,255,255,0.20); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link { color: #fff !important; font-weight: 700; font-size: .83rem; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px !important; height: 15px !important; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; }
.rc-sticky-link-active { background: rgba(0,0,0,0.15); font-weight: 800; }

/* 6. Section Headings */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }

/* 7. Components (Cards, Grids, Videos) */
.rc-screenshot { width: 100%; border-radius: 14px; border: 1px solid var(--lightgray); margin-bottom: 32px; display: block; }
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-embed { position: relative; aspect-ratio: 16/9; background: var(--offblack); }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }

.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin-bottom: 32px; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; transition: all .2s; }
.rc-feature-card:hover { border-color: var(--scale); transform: translateY(-2px); }
.rc-feature-card h4 { font-size: .95rem; font-weight: 800; margin: 0 0 8px; color: var(--offblack); }
.rc-feature-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; }

/* 8. Checklist (Pure CSS) */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; cursor: pointer; }
.rc-checklist-item input { position: absolute; opacity: 0; width: 0; height: 0; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; }
.rc-checklist-item input:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; }
.rc-checklist-item:has(input:checked) { background: rgba(255,88,16,0.06); }

/* 9. Buttons (Fixed Specificity for Borders) */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-guide a.rc-btn-prev { background: #fff; color: var(--darkgray) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 1px solid var(--lightgray) !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border-color: var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; border: 1px solid var(--yellow) !important; transition: all .2s; }

/* 10. Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); font-weight: 600; font-size: .9rem; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link img { width: 13px !important; height: 13px !important; opacity: 0.55; }

@media(max-width:768px){ .rc-card-grid { grid-template-columns: 1fr; } .rc-hero-stats { grid-template-columns: 1fr; } }
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-back-link">← Back to Scale</a>
  </div>

  <div class="rc-content-wrap">
    
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale"> Scale
      </div>
      <div class="rc-lp-hero-title"><h1>Account Updater Dashboard</h1></div>
      <p>Monitor your proactive revenue recovery and see how many cards are updated automatically behind the scenes.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">75%</div><div class="rc-hero-stat-label">Avg. Update Success</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">24/7</div><div class="rc-hero-stat-label">Automated Monitoring</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">100%</div><div class="rc-hero-stat-label">PCI Compliant</div></div>
      </div>
    </div>

    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigate Quick Links <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Payments Hub
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-sticky-link"><span class="rc-step-badge">1</span> Overview</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-sticky-link"><span class="rc-step-badge">2</span> Payment processing</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">3</span> Account updater</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-sticky-link"><span class="rc-step-badge">4</span> Payment retries</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-sticky-link"><span class="rc-step-badge">5</span> Fraud prevention</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-sticky-link"><span class="rc-step-badge">6</span> Resources</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <div class="rc-lp-section">
      <h2>🖼️ Dashboard Overview</h2>
      <img class="rc-screenshot" src="https://files.readme.io/2e488cefdf0e0cbbac44170f4774480b23c60e9445a66061c27f83f040bccf4c-Account_Updater_Dashboard.png" alt="Account Updater dashboard overview">
      
      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Account Updater Dashboard Walkthrough</h4>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/REPLACE_WITH_ID" loading="lazy" allowfullscreen></iframe>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>📋 What's on this dashboard</h2>
      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <h4>Successful updates</h4>
          <p>Total number of cards successfully updated in the period.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Updates over time</h4>
          <p>A line chart showing the daily count of card updates.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Revenue Authorized</h4>
          <p>The total payment volume authorized on updated cards.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>✅ Activity: Explore Account Updater</h2>
      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span>✅</span><h4>Review your activity</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Check 30-day recovered revenue</strong>
            <span>Identify how much revenue was saved by AU this month.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Analyze Update Types</strong>
            <span>Verify the percentage of card number changes vs. expiry updates.</span>
          </div>
        </label>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-btn-prev">← Payment processing</a>
      <span style="color:var(--gray); font-size:.8rem; font-weight:600;">3 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-btn-path">Next: Payment retries →</a>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-footer-link">1. Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-footer-link" style="color:var(--offblack)">3. Account Updater</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
