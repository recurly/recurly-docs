---
title: Navigate Code Test - Gemini
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. Host-theme Armor — Prevents ReadMe border-bottom overrides */
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

/* 3. Top Nav & Layout */
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
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 12px auto 32px; color: var(--lightgray); line-height: 1.6; }

.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); }

/* 5. Sticky Nav (Scale Special Case: White Text) */
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

/* 6. Section & Content styles */
.rc-lp-section { margin-bottom: 56px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 24px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }

/* 7. Completion Showcase */
.rc-complete-card { background: var(--offblack) !important; border-radius: 14px; padding: 48px 40px; text-align: center; margin-bottom: 48px; border: 1px solid rgba(255,255,255,0.1); }
.rc-complete-emoji { font-size: 3rem; margin-bottom: 16px; }
.rc-complete-card h3 { color: var(--yellow) !important; font-size: 1.5rem; font-weight: 800; margin: 0 0 12px; text-transform: uppercase; letter-spacing: 1px; }
.rc-complete-card p { color: var(--offwhite) !important; font-size: 1rem; line-height: 1.6; max-width: 680px; margin: 0 auto 24px; }
.rc-guide a.rc-complete-btn { background: var(--yellow); color: var(--offblack) !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .95rem; border: 1px solid var(--yellow); transition: all .2s; display: inline-flex; align-items: center; gap: 10px; margin: 5px; }
.rc-guide a.rc-complete-btn-sec { background: transparent; border: 1px solid var(--lightgray) !important; color: var(--lightgray) !important; padding: 12px 24px; border-radius: 10px; font-weight: 700; font-size: .95rem; display: inline-flex; align-items: center; gap: 10px; margin: 5px; }

/* 8. Card Grids */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; transition: all .2s; }
.rc-feature-card:hover { border-color: var(--scale); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; margin-bottom: 10px; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0 0 8px; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; }

/* 9. CTAs & Resources */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: var(--yellow) !important; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray) !important; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; border: 1px solid var(--yellow) !important; transition: all .2s; display: inline-flex; align-items: center; gap: 8px; }

.rc-resources { background: var(--brightgray); border-left: 4px solid var(--scale); border-radius: 10px; padding: 20px 24px; margin: 40px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; color: var(--gray); margin: 0 0 12px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; font-weight: 500; font-size: .88rem; display: inline-flex; align-items: center; gap: 6px; margin-right: 20px; margin-bottom: 8px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration-color: var(--scale) !important; }

/* 10. Nav Buttons & Footer */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-guide a.rc-btn-prev { background: #fff; color: var(--darkgray) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 1px solid var(--lightgray) !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border-color: var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; border: 1px solid var(--yellow) !important; transition: all .2s; }

.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); font-weight: 600; font-size: .88rem; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link img { width: 13px !important; height: 13px !important; opacity: 0.55; }

@media(max-width:768px){ .rc-card-grid, .rc-card-grid-3col { grid-template-columns: 1fr; } .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; } .rc-hero-stat + .rc-hero-stat { border-left: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; } }
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
      <div class="rc-lp-hero-title"><h1>Payments Hub Review & Resources</h1></div>
      <p>Congratulations! You've successfully navigated the Payments Hub. Use this recap and resource list to master your payment strategy.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">77x</div><div class="rc-hero-stat-label">Average ROI</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">18%</div><div class="rc-hero-stat-label">Recovered Rev.</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">5/5</div><div class="rc-hero-stat-label">Dashboards Covered</div></div>
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
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account updater</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-sticky-link"><span class="rc-step-badge">4</span> Payment retries</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-sticky-link"><span class="rc-step-badge">5</span> Fraud prevention</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources" class="rc-sticky-link rc-sticky-link-active"><span class="rc-step-badge">6</span> Resources</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
          </div>
        </div>
      </div>
    </details>

    <div class="rc-complete-card">
      <div class="rc-complete-emoji">🎉</div>
      <h3>Path Complete!</h3>
      <p>You've explored all 5 Payments Hub dashboards. You now know how to interpret your payment health, analyze declines, and track recovery performance. Ready to go deeper?</p>
      <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank" class="rc-complete-btn">▶ Watch Walkthrough</a>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-complete-btn-sec">🗓️ Join Office Hours</a>
    </div>

    <div class="rc-lp-section">
      <h2>🗺️ What you've covered</h2>
      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🏠</div>
          <h4>Overview Dashboard</h4>
          <p>Top-level snapshots of CIT/MIT success rates and geographical payment volume summary.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">💳</div>
          <h4>Payment Processing</h4>
          <p>Deep-dive into success rates by gateway and card BIN, plus ranked decline reasons.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔄</div>
          <h4>Account Updater</h4>
          <p>Revenue protected through automatic updates before payments ever have a chance to fail.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔁</div>
          <h4>Retry Recovery</h4>
          <p>Analyzing revenue recovered through Recurly's intelligent, machine-learning retry logic.</p>
        </div>
        <div class="rc-feature-card" style="grid-column: span 2;">
          <div class="rc-feature-icon">🛡️</div>
          <h4>Fraud Prevention</h4>
          <p>Monitoring risk score trends and blocked transactions to identify emerging fraud patterns before they impact your success rate.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>📊 Metrics to watch regularly</h2>
      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <div class="rc-feature-icon">📈</div>
          <h4>Success Rate</h4>
          <p>Blended rate across gateways. Watch the trend for investigated drifts.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔁</div>
          <h4>Recovery Rate</h4>
          <p>Percentage of initially failed revenue recovered via intelligent retries.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🔄</div>
          <h4>Revenue Protected</h4>
          <p>Value authorized on cards updated automatically by Account Updater.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">⚠️</div>
          <h4>Top Decline Reason</h4>
          <p>Identify if your failures are hard or soft to adjust your response strategy.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🛡️</div>
          <h4>Avg. Risk Score</h4>
          <p>A falling score is a leading indicator of an upcoming spike in blocks.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon">🌍</div>
          <h4>Regional Success</h4>
          <p>Check for geographic drop-offs to identify routing or payment method gaps.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Keep in mind</strong>
          <p>Payments Hub data begins from Q1 2026. These dashboards show granular, payment-level data — some figures may differ slightly from standard billing analytics; both are accurate.</p>
        </div>
      </div>
    </div>

    <div class="rc-oh-cta">
      <h4>🗓️ Go deeper with a CSM</h4>
      <p>Global Office Hours are the best place to walk through your data with a Recurly CSM. Bring your numbers and leave with clear, actionable next steps for your business.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <div class="rc-resources">
      <h3>📚 Resources & documentation</h3>
      <div class="rc-resource-links">
        <a href="https://navigate.recurly.com/lunch-and-learn/new-payment-hub/" target="_blank" class="rc-resource-link">▶ Payments Hub Walkthrough (on-demand)</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" class="rc-resource-link">🌐 Join Global Office Hours</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank" class="rc-resource-link">📖 Recurly Docs: Payments Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/api-transaction-errors" target="_blank" class="rc-resource-link">📝 Decline messages reference</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/retry-logic" target="_blank" class="rc-resource-link">🔁 Intelligent retries documentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater" target="_blank" class="rc-resource-link">🔄 Account Updater learning</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-btn-prev">← Fraud prevention</a>
      <span style="color:var(--gray); font-size:.8rem; font-weight:700;">6 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub" class="rc-btn-path">↩ Back to start</a>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview" class="rc-footer-link">1. Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing" class="rc-footer-link">2. Processing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater" class="rc-footer-link">3. AU</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries" class="rc-footer-link">4. Retries</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention" class="rc-footer-link">5. Fraud</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
