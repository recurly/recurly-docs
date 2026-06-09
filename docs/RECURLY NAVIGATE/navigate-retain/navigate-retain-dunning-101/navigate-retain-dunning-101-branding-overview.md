---
title: 'Dunning 101: Why Branding your Dunning emails matters'
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

/* CARD GRID */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 24px; }
.rc-feature-card { background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF9D88; box-shadow: 0 4px 16px rgba(255,157,136,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D73; line-height: 1.55; margin: 0; }

/* STAT STRIP */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; overflow: hidden; margin: 0 0 28px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid #CCC9B8; }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: #FF9D88; line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: #807D73; margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: #32312D; line-height: 1.5; padding-top: 10px; border-top: 1px solid #F1EFE3; }

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
  .rc-stat-strip { grid-template-columns: 1fr; }
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
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> Retain
      </div>
      <div class="rc-lp-hero-title"><h1>Why branding your dunning emails matters</h1></div>
      <p>Unbranded dunning emails look like phishing attempts. Branded ones look like a trusted business asking for help. That difference shows up directly in your recovery rate.</p>
      
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-overview" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Why branding matters
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Configuring email templates</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-strategy" class="rc-sticky-link"><span class="rc-step-badge">3</span> Subject lines, CTAs &amp; message arc</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- WHAT IT IS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-envelope-open-text rc-fa-section"></i> What branding your dunning emails means</h2>
      <p>By default, Recurly's dunning email templates are functional but generic — plain layout, no logo, no brand colors. To a subscriber, an unformatted email asking them to update their payment details looks like a phishing attempt, not a trusted message from a business they subscribe to. Brand recognition is what turns a suspicious-looking email into an actionable one.</p>
      <p>Branded dunning emails match your other transactional communications — same logo, colors, tone, and footer. Subscribers recognize who it's from immediately, which increases open rates, click-through rates, and ultimately recovery.</p>

      <div class="rc-card-grid">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-image"></i></div>
          <h4>Visual identity</h4>
          <p>Your logo, brand colors, and header image. Makes the email instantly recognizable and sets the tone before the subscriber reads a word.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-font"></i></div>
          <h4>Tone of voice</h4>
          <p>Write in the same voice as your other customer communications — friendly, clear, and direct. Avoid generic system language like "payment failure detected."</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-arrow-pointer"></i></div>
          <h4>Clear CTA</h4>
          <p>A prominent, action-oriented button — "Update your payment method" — styled in your brand colors. The CTA is the only job of the email; make it impossible to miss.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-list"></i></div>
          <h4>Branded footer</h4>
          <p>Copyright line, links to your support page and terms, and your company address. Signals legitimacy and gives the subscriber somewhere to go if they have questions.</p>
        </div>
      </div>
    </div>

    <!-- WHY IT MATTERS — STATS -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-chart-line rc-fa-section"></i> The impact of branding on recovery</h2>
      <p>Recurly data shows that merchants who apply full branding — logo, colors, personalization, and a clear CTA — consistently outperform those running generic templates. These aren't marginal gains.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">+12%</div>
          <div class="rc-stat-tile-label">Recovery rate uplift</div>
          <div class="rc-stat-tile-context">From adding branded headers, updated window length, and optimized email frequency — one of the highest single-change gains in the dataset.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">~60%</div>
          <div class="rc-stat-tile-label">Higher click-through rate</div>
          <div class="rc-stat-tile-context">Branded emails with a clear CTA see significantly higher click-through than plain-text templates — subscribers trust what they recognize.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num">+279%</div>
          <div class="rc-stat-tile-label">Recovery revenue in month 1</div>
          <div class="rc-stat-tile-context">My Music Workshop implemented all dunning best practices from scratch, including full branding, and saw this result in their first month.</div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>Personalization amplifies branding</strong>
          <p>Use Recurly's dynamic variables to include the subscriber's name, the amount owed, the last four digits of their card, and the days remaining in the dunning window. A personalized email feels like it was written for that subscriber specifically — which drives action far more effectively than a generic one.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-window-configure" class="rc-btn-prev">← Dunning window length</a>
      <span class="rc-lp-nav-indicator">1 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-btn-path">Next: Configuring email templates →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Dunning management</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email templates</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Branding &amp; CTAs</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-overview" class="rc-footer-link">Why branding matters</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-configure" class="rc-footer-link">Configuring email templates</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-branding-strategy" class="rc-footer-link">Subject lines, CTAs &amp; message arc</a>
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

<br />
