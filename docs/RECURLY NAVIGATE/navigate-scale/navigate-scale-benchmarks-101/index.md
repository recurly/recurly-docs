---
title: Benchmarks 101
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* HOST-THEME BACKGROUND OVERRIDE */
body { background: #ffffff !important; }

/* GLOBAL CSS IMMUNITY BLOCK */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Polar", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR */
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active {
  text-decoration: none !important;
  text-decoration-line: none !important;
  text-decoration-color: transparent !important;
  text-underline-offset: unset !important;
  border-bottom: 0 !important;
}

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:     #FFD706;
  --orange:     #FF8200;
  --scale:      #FF5810;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D73;
  --lightgray:  #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite:   #FFFDF2;
  color: #32312D !important;
  background: #ffffff;
}

/* FA6 ICON HELPERS */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* LAYOUT */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* BACK LINK */
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

/* ANNOUNCEMENT BAR */
.rc-announce-bar { display: none; background: var(--scale); color: #fff; align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link { color: #ffffff !important; font-weight: 800; white-space: nowrap; padding: 4px 12px; background: rgba(255,255,255,0.15); border-radius: 6px; transition: background 0.2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(255,255,255,0.25); color: #ffffff !important; }

/* HERO */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; }
.rc-pillar-hero-icon { width: 64px; height: 64px; object-fit: contain; display: block; margin: 44px auto 20px; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0 0 24px; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: #CCC9B8; line-height: 1.6; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,88,16,0.20); border: 1px solid rgba(255,88,16,0.45); color: #FF5810; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }

/* NAV — Scale dark variant */
details.rc-sticky-nav-wrap {
  position: relative;
  z-index: 1;
  background-color: #FF5810;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #ffffff; }
.rc-nav-chevron { font-size: .72rem; color: #ffffff; opacity: 0.7; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #ffffff !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.20); color: #ffffff !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: rgba(0,0,0,0.30); color: #ffffff; font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #ffffff !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.20); color: #ffffff !important; }

/* CONTENT SECTIONS */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* TOC CARDS */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card { display: grid; grid-template-columns: 44px 1fr 32px; align-items: center; gap: 16px; background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 18px 22px; transition: all .2s ease; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-toc-card { border-bottom: 1px solid #CCC9B8 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-toc-card:hover { border-color: #FF5810; border-bottom: 1px solid #FF5810 !important; box-shadow: 0 4px 14px rgba(255,88,16,0.12); transform: translateX(3px); }
.rc-toc-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; }
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: var(--lightgray); text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #FF5810; }

/* PATH NAV */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; display: inline-flex; align-items: center; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: var(--yellow); color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* RESOURCES */
.rc-resources { background: var(--brightgray); border-left: 4px solid #FF5810; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF5810 !important; }

/* FOOTER */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link { color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* RESPONSIVE */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-hero h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
}
</style>

<div class="rc-guide">

  <!-- BACK LINK -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-back-link">← Back to Scale</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ANNOUNCEMENT BAR (hidden by default — add rc-active to show) -->
    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce" style="color:#ffffff;"></i>
        <strong>Upcoming:</strong> Bring your benchmark questions to a live session with our CSMs.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <!-- HERO -->
    <div class="rc-hero">
      
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale"> Scale · Recurly Benchmarks 101
      </div>
      <h1>Recurly Benchmarks 101</h1>
      <p>Recurly benchmarks 8 key metrics across your subscription lifecycle — pulled from 2,200+ merchants. This course shows you where to find them, how to read them, and what to do with what you find.</p>
    </div>

    <!-- NAV — Course Overview active, non-sticky, open -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/83faba29b18efa915aa8aad0182d79d0f8328da2a9d7ea16504d8ee8a3cf3677-White_Home_Icon_1.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/c8c36df1d0552052603885aa5936c2474ddd7b3ece261aa70bac9fee6fd16017-White_Navigate_Home_Pin.png" alt=""> Overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-reading" class="rc-sticky-link"><span class="rc-step-badge">1</span> Reading benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber" class="rc-sticky-link"><span class="rc-step-badge">2</span> Subscriber benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn" class="rc-sticky-link"><span class="rc-step-badge">3</span> Churn benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal-dunning" class="rc-sticky-link"><span class="rc-step-badge">4</span> Renewal &amp; dunning benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-review" class="rc-sticky-link"><span class="rc-step-badge">5</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- CONTENT -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-bar rc-fa-section"></i> What this course covers</h2>
      <p>Recurly's built-in benchmarks compare your subscription metrics against thousands of similar businesses in your industry — in real time, without leaving your dashboard. This course walks you through all 8 benchmarked KPIs across 4 Analytics dashboards, so you can spot gaps, confirm strengths, and know exactly where to focus.</p>
      <p>Before you start: confirm your industry is set correctly under <strong>Analytics → Settings</strong>. An incorrect classification skews every comparison in this course. Changes take up to 24 hours to reflect.</p>

      <!-- TOC CARDS -->
      <div class="rc-toc-list">

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-reading" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>Reading benchmarks</h4>
            <p>How to navigate to each dashboard, interpret the quartile chart, and filter by industry and date range.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Subscriber benchmarks</h4>
            <p>Acquisition Rate and Sign-Up Decline Rate — the top of your subscription funnel.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Churn benchmarks</h4>
            <p>Churn Rate, Involuntary Churn Rate, and Voluntary Churn Rate — understand what's driving subscriber loss and which fix applies.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal-dunning" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Renewal &amp; dunning benchmarks</h4>
            <p>Renewal Invoice Paid Rate, Decline Rate at Renewal, and Dunning Recovery Rate — the revenue recovery trio.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-review" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Review &amp; resources</h4>
            <p>Check your understanding and access all course resources in one place.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>

      </div>

      <!-- PATH NAV -->
      <div class="rc-lp-nav">
        <span class="rc-btn-start">Start</span>
        <span class="rc-lp-nav-indicator">Overview</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-reading" class="rc-btn-path">Next: Reading benchmarks →</a>
      </div>
    </div>

    <!-- RESOURCES -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/built-in-benchmarks" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Built-in benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/analytics-settings" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Analytics settings</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <!-- FOOTER -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Recurly Benchmarks 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-reading" class="rc-footer-link">1. Reading benchmarks</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-subscriber" class="rc-footer-link">2. Subscriber benchmarks</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-churn" class="rc-footer-link">3. Churn benchmarks</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-renewal-dunning" class="rc-footer-link">4. Renewal &amp; dunning benchmarks</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-benchmarks-101-review" class="rc-footer-link">5. Review &amp; resources</a>
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

<br />
