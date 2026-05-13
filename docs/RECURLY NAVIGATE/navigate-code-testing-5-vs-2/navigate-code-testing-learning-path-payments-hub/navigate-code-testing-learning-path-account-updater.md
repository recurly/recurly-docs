---
title: Navigate Code Testing Learning Path Account Updater
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. Global Reset & Variables */
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

/* 2. Host-theme Armor (Critical) */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* 3. Top Nav & Content Wrap */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px 60px; }

/* 4. Hero Section */
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
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }

.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* 5. Sticky Nav (Scale Special Case) */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--scale);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #fff; }
.rc-nav-chevron { font-size: .72rem; color: #fff; opacity: 0.8; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(255,255,255,0.20); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link { color: #fff !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; }
.rc-sticky-link-active { background: rgba(0,0,0,0.15); font-weight: 800; }

/* 6. Section & Content styles */
.rc-lp-section { margin-bottom: 56px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 24px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 20px; }

.rc-screenshot { width: 100%; border-radius: 14px; border: 1px solid var(--lightgray); margin-bottom: 32px; display: block; }

/* Video Card */
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 40px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-embed { position: relative; overflow: hidden; aspect-ratio: 16/9; background: var(--offblack); }
.rc-video-embed iframe { position: absolute; width: 100%; height: 100%; top: 0; left: 0; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: var(--gray); background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

/* Card Grid */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: var(--scale); box-shadow: 0 4px 16px rgba(255,88,16,0.15); transform: translateY(-2px); }
.rc-feature-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 24px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-body a { color: var(--orange) !important; font-weight: 600; }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }

/* Checklist (Pure CSS) */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 32px 0; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,88,16,0.06); }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* Office Hours CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: var(--yellow) !important; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray) !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: var(--offwhite) !important; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Path Nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 48px 0 0; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--gray); }
.rc-guide a.rc-btn-prev { color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; border: 2px solid var(--yellow); transition: all .2s; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--scale); border-radius: 10px; padding: 20px 24px; margin: 40px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration-color: var(--scale) !important; }

.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); font-weight: 600; font-size: .9rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link:hover { color: var(--offblack); }

@media(max-width:768px){ 
  .rc-content-wrap { padding: 0 20px; } 
  .rc-card-grid, .rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.1); padding-top: 16px; }
}
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
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">100%</div><div class="rc-hero-stat-label">PCI Compliant updates</div></div>
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
          <span>~2 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/REPLACE_WITH_ID" loading="lazy" title="Dashboard Walkthrough" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
        </div>
        <div class="rc-video-caption">A quick tour of how to interpret your Account Updater metrics and identifying revenue recovery trends.</div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Not seeing Account Updater data?</strong>
          <p>This dashboard requires Account Updater to be active. If you see no data, it may not be enabled for your site. <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">Learn about Account Updater →</a></p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>📋 What's on this dashboard</h2>
      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <h4>Successful updates</h4>
          <p>Total cards successfully updated in the period vs. the previous period.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Updates over time</h4>
          <p>A line chart showing daily counts. Drops may signal issuer-level issues.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Revenue Authorized</h4>
          <p>The total payment volume processed on cards that were previously updated.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Revenue over time</h4>
          <p>A bar chart showing the daily revenue volume recovered by updated cards.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Update Type</h4>
          <p>A breakdown of card number changes vs. routine expiration date updates.</p>
        </div>
        <div class="rc-feature-card">
          <h4>Updates by Card Type</h4>
          <p>Distribution of activity across card networks (Visa, Mastercard, etc.).</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Pro-Tip: Monitoring Update Type</strong>
          <p>A card number change means a subscriber received an entirely new card (often due to fraud). These carry more disruption risk than routine expiry updates. High proportions here may indicate widespread bank migrations or fraud events affecting your base.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>✅ Activity: Explore Account Updater</h2>
      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span>✅</span>
          <h4>Review your activity</h4>
        </div>
        
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Check 30-day recovered revenue</strong>
            <span>How much revenue was authorized on updated cards? This is the revenue likely saved by AU.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Analyze Update Types</strong>
            <span>What percentage are card number changes? High counts may signal external fraud events.</span>
          </div>
        </label>

        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Review Network Distribution</strong>
            <span>Check "Updates by Card Type." Zero updates for a major brand could indicate a technical problem.</span>
          </div>
        </label>

        <div class="rc-checklist-footer">✓ Tap each item to mark it complete</div>
      </div>
    </div>

    <div class="rc-oh-cta">
      <h4>🗓️ Not using Account Updater yet?</h4>
      <p>Join <strong>Global Office Hours</strong> to talk with a CSM about enabling Account Updater. It's one of the most impactful, proactive tools for merchant revenue recovery.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-btn-prev">← Payment processing</a>
      <span class="rc-lp-nav-indicator">3 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-btn-path">Next: Payment retries →</a>
    </div>

    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" class="rc-resource-link">📖 Navigate: Account Updater Learning Path</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-footer-link">Path Overview</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />