---
title: 'Dunning 101: Dunning window length'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
body { background: #ffffff !important; }
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"], .rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands, .rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a, .rc-guide a:link, .rc-guide a:visited, .rc-guide a:hover, .rc-guide a:active {
  text-decoration: none !important; text-decoration-line: none !important;
  text-decoration-color: transparent !important; text-underline-offset: unset !important; border-bottom: 0 !important;
}
html { scroll-behavior: smooth; }
.rc-guide {
  --yellow: #FFD706; --orange: #FF8200; --offblack: #0D0D0B; --darkgray: #32312D;
  --gray: #807D73; --lightgray: #CCC9B8; --brightgray: #F1EFE3; --offwhite: #FFFDF2; --retain: #FF9D88;
  color: #32312D !important; background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }

/* LAYOUT */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; transition: color .2s; }
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ANNOUNCE BAR */
.rc-announce-bar { display: none; background: #FFD706; color: #0D0D0B; align-items: center; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rc-guide a.rc-announce-link { color: #0D0D0B !important; font-weight: 800; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; border-bottom: 0 !important; }
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); }

/* HERO */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
    url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  padding: 48px 40px 44px; text-align: center; border-radius: 16px;
}
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45); color: #FF9D88; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0 0 14px; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* NAV */
details.rc-sticky-nav-wrap { position: relative; z-index: 1; background-color: #FF9D88; box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker, details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #0D0D0B; }
.rc-nav-chevron { font-size: .72rem; color: #0D0D0B; opacity: 0.55; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: #0D0D0B; color: #FFD706; font-size: .65rem; font-weight: 800; flex-shrink: 0; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); }

/* CONTENT SECTIONS */
.rc-lp-section { margin-bottom: 40px; }
.rc-lp-section h2 { font-size: 1.4rem; font-weight: 800; margin: 0 0 16px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #CCC9B8; }
.rc-lp-section > p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* CARD GRID */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 24px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; }

/* TABLE */
.rc-table { width: 100%; border-collapse: collapse; font-size: .88rem; margin: 0 0 24px; border-radius: 10px; overflow: hidden; border: 1px solid #CCC9B8; }
.rc-table thead { background: #0D0D0B; color: #FFFDF2; }
.rc-table thead th { padding: 12px 16px; text-align: left; font-size: .75rem; font-weight: 700; letter-spacing: .5px; text-transform: uppercase; }
.rc-table tbody tr:nth-child(even) { background: #F1EFE3; }
.rc-table tbody tr:nth-child(odd) { background: #FFFDF2; }
.rc-table tbody td { padding: 12px 16px; color: #32312D; border-bottom: 1px solid #CCC9B8; vertical-align: top; }
.rc-table tbody td strong { color: #0D0D0B; }

/* CALLOUTS */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 0 0 16px; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid #FFD706; }
.rc-callout-warning .rc-callout-body > strong { color: #32312D; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }

/* PATH NAV */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; transition: all .2s; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* RESOURCES */
.rc-resources { margin: 40px 0 0; }
.rc-resources h3 { font-size: 1.05rem; font-weight: 800; color: #0D0D0B; margin: 0 0 14px; display: flex; align-items: center; gap: 10px; }
.rc-resource-links { display: flex; flex-direction: column; gap: 8px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; font-size: .9rem; font-weight: 600; display: inline-flex; align-items: center; gap: 8px; border-bottom: 0 !important; transition: color .2s; }
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF9D88 !important; }

/* FOOTER */
.rc-footer-nav { border-top: 1px solid #CCC9B8; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F1EFE3; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; font-weight: 600; font-size: .88rem; border-bottom: 0 !important; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid #F1EFE3; }

@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; } .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 32px; } .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; } .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs to walk through dunning optimization live.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> Retain · Dunning 101
      </div>
      <div class="rc-lp-hero-title"><h1>Dunning window length</h1></div>
      <p>The window is the container everything else runs inside. Size it correctly and your retries and emails have maximum time to work.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">27 days</div>
          <div class="rc-hero-stat-label">Monthly plans</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">60 days</div>
          <div class="rc-hero-stat-label">Annual plans</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">+11%</div>
          <div class="rc-hero-stat-label">Recovery from window extension</div>
        </div>
      </div>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-length" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Understanding window length
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Configuring your window</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- WHAT IT IS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-calendar-days rc-fa-section"></i> What is the dunning window?</h2>
      <p>The dunning window is the number of days Recurly has to recover a failed payment before the subscription expires. During this window, Intelligent Retries is attempting the payment and your email sequence is running in parallel. When the window closes with no recovery, the subscription lapses.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-rotate"></i></div>
          <h4>Intelligent Retries</h4>
          <p>ML-powered retries run automatically throughout the window. A longer window means more retry attempts — which is the primary driver of passive churn recovery on soft declines.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-regular fa-envelope"></i></div>
          <h4>Dunning emails</h4>
          <p>Your email sequence runs in parallel, independently from retries. A longer window lets you space emails 4–5 days apart without compressing the cadence or overwhelming the subscriber.</p>
        </div>
      </div>
    </div>

    <!-- RECOMMENDED BENCHMARKS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-sliders rc-fa-section"></i> Recommended window lengths</h2>
      <p>These benchmarks are sized to fit just inside each billing cycle — long enough to maximize retry attempts and email touchpoints, short enough to prevent a second invoice generating before the first one is resolved.</p>

      <table class="rc-table">
        <thead>
          <tr><th>Billing frequency</th><th>Recommended window</th><th>Why</th></tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Monthly</strong></td>
            <td>27 days</td>
            <td>Sits just inside the 30-day billing cycle, giving retries maximum time without risking a duplicate invoice</td>
          </tr>
          <tr>
            <td><strong>Annual</strong></td>
            <td>60 days</td>
            <td>Annual subscribers represent high LTV — a short window here is one of the most costly mistakes in dunning setup</td>
          </tr>
          <tr>
            <td><strong>Quarterly</strong></td>
            <td>~90% of billing cycle</td>
            <td>Scale with the interval; the same logic applies — preserve as much recovery time as possible without crossing into the next cycle</td>
          </tr>
          <tr>
            <td><strong>Weekly</strong></td>
            <td>7 days</td>
            <td>Match the billing frequency; one retry window per cycle keeps recovery and billing in sync</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon"><i class="fa-solid fa-circle-info"></i></div>
        <div class="rc-callout-body">
          <strong>Worried about giving free access during recovery?</strong>
          <p>You can decouple dunning status from product entitlement using Recurly webhooks — keep the full recovery window open while restricting access after a 3–5 day grace period. This lets you protect revenue without cutting off subscribers who may resolve their payment issue within days.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>One default window applied to all plans will always underperform</strong>
          <p>Annual and monthly subscribers have very different recovery profiles — and very different LTV at stake. Set a separate campaign with its own window length for each billing frequency. You'll configure this in the next page.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-btn-prev">← Dunning 101</a>
      <span class="rc-lp-nav-indicator">1 of 2</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-btn-path">Next: Configuring your window →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning management</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-benchmarks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning benchmarks</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Dunning window length</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-length" class="rc-footer-link">Understanding window length</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-footer-link">Configuring your window</a>
        </div>
        <div class="rc-footer-section">
                   <span class="rc-footer-label">Dunning 101</span>
         <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-footer-link">Dunning 101 overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-footer-link">Dunning window length</a>
   <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-overview" class="rc-footer-link">Branding & CTAs</a>
   <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-overview" class="rc-footer-link">Multiple campaigns</a>
   <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-analytics" class="rc-footer-link">Measuring performance</a>
   <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-review" class="rc-footer-link">Review & resources</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

8&
