---
title: 'Dunning 101: Branding & CTAs'
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
.rc-fa-dark { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
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

/* TABLE */
.rc-table { width: 100%; border-collapse: collapse; font-size: .88rem; margin: 0 0 24px; border-radius: 10px; overflow: hidden; border: 1px solid #CCC9B8; }
.rc-table thead { background: #0D0D0B; color: #FFFDF2; }
.rc-table thead th { padding: 12px 16px; text-align: left; font-size: .75rem; font-weight: 700; letter-spacing: .5px; text-transform: uppercase; }
.rc-table tbody tr:nth-child(even) { background: #F1EFE3; }
.rc-table tbody tr:nth-child(odd) { background: #FFFDF2; }
.rc-table tbody td { padding: 12px 16px; color: #32312D; border-bottom: 1px solid #CCC9B8; vertical-align: top; }
.rc-table tbody td strong { color: #0D0D0B; }

/* CARD GRID */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 24px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; }

/* CALLOUTS */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 0 0 16px; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F1EFE3; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #FF8200 !important; font-weight: 600; border-bottom: 0 !important; }

/* OH CTA */
.rc-oh-cta { background: #0D0D0B; border: 2px solid #FFD706; border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2; }
.rm-Markdown.markdown-body .rc-guide a.rc-oh-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-oh-btn { background: #FFD706; color: #0D0D0B !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; transition: all .2s; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: #FFD706 !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* REFLECT CARD */
.rc-reflect-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-left: 4px solid #FFD706; border-radius: 14px; padding: 24px 28px; margin: 0 0 32px; }
.rc-reflect-label { display: inline-block; background: #FFD706; color: #0D0D0B; font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; padding: 3px 10px; border-radius: 5px; margin-bottom: 12px; }
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: #0D0D0B; margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: #807D73; line-height: 1.6; margin: 0; }

/* PATH NAV */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #CCC9B8; letter-spacing: .5px; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #CCC9B8 !important; border-bottom: 2px solid #CCC9B8 !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; transition: all .2s; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; }

/* ── RESOURCES ── */
.rc-resources { background: #F1EFE3; border-left: 4px solid #FF9D88; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D73; margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF9D88 !important; }

/* ── FOOTER ── */
.rc-footer-nav { border-top: 1px solid #CCC9B8; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F1EFE3; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D73 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #FF8200 !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid #F1EFE3; }

@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; } .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 32px; } .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
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
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> Retain • Dunning 101
      </div>
      <div class="rc-lp-hero-title"><h1>Subject lines, CTAs &amp; message arc</h1></div>
      <p>What you say — and how urgency escalates across the sequence — is just as important as how the email looks.</p>
     
    </div>

<!-- STICKY NAV — LP Overview variant -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-sticky-link">
          Dunning 101 overview
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-length" class="rc-sticky-link">
          <span class="rc-step-badge">1</span> Dunning window length
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-sticky-link">
          <span class="rc-step-badge">2</span> Configuring your window
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-overview" class="rc-sticky-link">
          <span class="rc-step-badge">3</span> Branding dunning emails
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-sticky-link">
          <span class="rc-step-badge">4</span> Configuring email templates
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-strategy" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Branding &amp; CTAs
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-overview" class="rc-sticky-link">
          <span class="rc-step-badge">6</span> Multiple campaigns
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-configure" class="rc-sticky-link">
          <span class="rc-step-badge">7</span> Building &amp; assigning campaigns
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-analytics" class="rc-sticky-link">
          <span class="rc-step-badge">8</span> Measuring performance
        </a>
        
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-review" class="rc-sticky-link">
          <span class="rc-step-badge">9</span> Review &amp; resources
        </a>

      </div></div></div>
    </details>

    <!-- MESSAGE ARC -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-arrow-trend-up rc-fa-section"></i> The message arc — escalating urgency across the sequence</h2>
      <p>Each email in your dunning sequence should feel different from the last. Early emails are low-pressure reminders. Later emails communicate real consequences. Reusing the same message — or the same subject line — trains subscribers to ignore it.</p>

      <table class="rc-table">
        <thead>
          <tr><th>Email</th><th>Tone</th><th>Subject line approach</th><th>CTA</th></tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Day 0</strong></td>
            <td>Friendly, low-pressure</td>
            <td>"Heads up — your payment didn't go through"</td>
            <td>Update your payment method</td>
          </tr>
          <tr>
            <td><strong>Day 4–5</strong></td>
            <td>Helpful, mild urgency</td>
            <td>"We're still having trouble processing your payment"</td>
            <td>Fix it today</td>
          </tr>
          <tr>
            <td><strong>Day 10–12</strong></td>
            <td>Direct, value reminder</td>
            <td>"Your [Product] access is at risk"</td>
            <td>Keep your subscription active</td>
          </tr>
          <tr>
            <td><strong>Day 20–22</strong></td>
            <td>Urgent, consequence-forward</td>
            <td>"Final notice: your subscription expires in [X] days"</td>
            <td>Reactivate now</td>
          </tr>
          <tr>
            <td><strong>Final email</strong></td>
            <td>Last chance</td>
            <td>"Your [Product] subscription has been cancelled"</td>
            <td>Reactivate your account</td>
          </tr>
        </tbody>
      </table>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Use the subscriber's product name, not a generic label</strong>
          <p>Emails that reference what the subscriber will lose — their specific plan name, their content library, their team workspace — outperform generic "your subscription" language. It makes the stakes concrete and personal.</p>
        </div>
      </div>
    </div>

    <!-- SUBJECT LINES & CTAS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-pen-to-square rc-fa-section"></i> Subject lines and CTAs that drive action</h2>
      <p>The subject line determines whether the email gets opened. The CTA determines whether the subscriber acts. Both deserve as much attention as the email body.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-circle-check" style="color:#6ab187;"></i></div>
          <h4>Subject lines that work</h4>
          <p>Specific over vague — "Your payment for [Plan] didn't go through" beats "Action required." Include the subscriber's name or amount where possible. Keep it under 50 characters so it renders fully on mobile.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-circle-xmark" style="color:#FF8200;"></i></div>
          <h4>Subject lines that don't</h4>
          <p>"Important notice," "Account update required," and "Payment failed" are overused and feel automated. They get filtered or ignored. Be specific about what failed and what the subscriber needs to do.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-circle-check" style="color:#6ab187;"></i></div>
          <h4>CTAs that convert</h4>
          <p>Action-oriented and specific: "Update your payment method," "Fix it now," "Keep my subscription." Button text should match the urgency of the email — early emails can be calm, final emails should be direct.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-circle-xmark" style="color:#FF8200;"></i></div>
          <h4>CTAs that don't</h4>
          <p>"Click here," "Submit," and "Learn more" are vague and passive. They don't communicate what happens next or why the subscriber should act. Always use a verb that describes the outcome.</p>
        </div>
      </div>
    </div>

    <!-- REFLECTION -->
    <div class="rc-reflect-card">
      <span class="rc-reflect-label">Reflection</span>
      <h4>Read through your current dunning email sequence from start to finish — does each email feel meaningfully different from the one before it?</h4>
      <p>If the subject lines, tone, or CTA copy are similar across emails, subscribers will stop engaging after the first one. Distinct messaging at each stage is what keeps the sequence effective through to the window close.</p>
    </div>

    <!-- OH CTA -->
    <div class="rc-oh-cta">
      <h4><i class="fa-solid fa-headset rc-fa-dark"></i>Want a CSM to review your email copy?</h4>
      <p>Bring your current dunning sequence to <strong>Global Office Hours</strong>. Our CSMs can review your subject lines, CTAs, and message arc and give direct feedback on what to change.</p>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Join Global Office Hours →</a>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-btn-prev">← Configuring email templates</a>
      <span class="rc-lp-nav-indicator">5 of 9</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-overview" class="rc-btn-path">Continue to Multiple campaigns →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning management</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email templates</a>
        <a href="https://recurly.ondemand.goldcast.io/on-demand/a65f472f-9876-4736-9209-5b7b669de773" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-circle-play"></i> On-demand webinar: Stop the Leak</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

<!-- FOOTER -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Dunning 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-footer-link">Dunning 101 overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-length" class="rc-footer-link">Dunning window length</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-footer-link">Configuring your window</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-overview" class="rc-footer-link">Branding dunning emails</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-footer-link">Configuring email templates</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-strategy" class="rc-footer-link">Branding & CTAs</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-overview" class="rc-footer-link">Multiple campaigns</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-campaigns-configure" class="rc-footer-link">Building & assigning campaigns</a>
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
`}</HTMLBlock>

<br />
