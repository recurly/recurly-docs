---
title: Editing Page 2
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
.rc-guide [class^="fa-"], .rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands, .rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR */
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a, .rc-guide a:link, .rc-guide a:visited, .rc-guide a:hover, .rc-guide a:active {
  text-decoration: none !important; text-decoration-line: none !important;
  text-decoration-color: transparent !important; text-underline-offset: unset !important; border-bottom: 0 !important;
}

html { scroll-behavior: smooth; scroll-padding-top: 80px; }
.rc-guide {
  --yellow: #FFD706; --orange: #FF8200; --offblack: #0D0D0B; --darkgray: #32312D;
  --gray: #807D73; --lightgray: #CCC9B8; --brightgray: #F1EFE3; --offwhite: #FFFDF2;
  color: #32312D !important; background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D73 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF8200 !important; }

.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag { margin-bottom: 24px; display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }
.rc-pillar-icon-chip { display: inline-flex; align-items: center; gap: 7px; padding: 7px 14px; border-radius: 20px; font-size: .72rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; }
.rc-pillar-icon-chip img { width: 14px; height: 14px; object-fit: contain; }
.rc-chip-launch { background: rgba(204,201,184,0.20); border: 1px solid rgba(204,201,184,0.45); color: #CCC9B8; }
.rc-chip-acquire { background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; }
.rc-chip-retain { background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45); color: #FF9D88; }
.rc-chip-scale { background: rgba(255,88,16,0.20); border: 1px solid rgba(255,88,16,0.45); color: #FF5810; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0 0 14px; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

details.rc-sticky-nav-wrap { position: sticky; top: 0; z-index: 100; background-color: var(--brightgray); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link { color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section > p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-card-grid-3col { grid-template-columns: 1fr 1fr 1fr; }
.rc-feature-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #CCC9B8; box-shadow: 0 4px 16px rgba(204,201,184,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }

.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card { display: grid; grid-template-columns: 44px 1fr 32px; align-items: center; gap: 16px; background: #FFFDF2; border: 1px solid #CCC9B8; border-radius: 12px; padding: 18px 22px; transition: all .2s ease; }
/* ARMOR OVERRIDE: Double prefix + :not() block to strictly enforce the border across ReadMe global rules */
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-toc-card { border-bottom: 1px solid #CCC9B8 !important; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-toc-card:hover { border-color: #CCC9B8 !important; border-bottom: 1px solid #CCC9B8 !important; box-shadow: 0 4px 14px rgba(204,201,184,0.12); transform: translateX(3px); }
/* Hex color enforcement for child elements inside <a> */
.rc-toc-num { width: 36px; height: 36px; border-radius: 50%; background: #0D0D0B !important; color: #FFD706 !important; display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; }
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B !important; margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: #807D73 !important; line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: #CCC9B8 !important; text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #807D73 !important; }

.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

.rc-resources { background: var(--brightgray); border-left: 4px solid #CCC9B8; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link { color: #807D73 !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #CCC9B8 !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration-color: #CCC9B8 !important; }

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

@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; } .rc-top-nav { padding: 16px 20px; } .rc-hero { padding: 36px 20px 36px; } .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; } .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; } .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="/docs/navigate-home" class="rc-back-link">← Back to Home</a>
  </div>

  <div class="rc-content-wrap">
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <span class="rc-pillar-icon-chip rc-chip-launch"><img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt=""> Launch</span>
        <span class="rc-pillar-icon-chip rc-chip-acquire"><img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt=""> Acquire</span>
        <span class="rc-pillar-icon-chip rc-chip-retain"><img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt=""> Retain</span>
        <span class="rc-pillar-icon-chip rc-chip-scale"><img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt=""> Scale</span>
      </div>
      <div class="rc-lp-hero-title"><h1>Welcome to Navigate</h1></div>
      <p>Your official orientation to Navigate — Recurly's always-on, 360-degree Customer Success program.</p>
    </div>

    <details class="rc-sticky-nav-wrap">
      <summary><span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="/docs/navigate-intro-welcome" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Welcome to Navigate
        </a>
        <a href="/docs/navigate-intro-home" class="rc-sticky-link"><span class="rc-step-badge">1</span> Navigating Home</a>
        <a href="/docs/navigate-intro-expect" class="rc-sticky-link"><span class="rc-step-badge">2</span> Navigate full program</a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-compass rc-fa-section"></i> What is Recurly Navigate?</h2>
      <p>Recurly Navigate is your always-on, digital Customer Success program. We built it to bring the expertise of a dedicated Customer Success Manager directly to you, exactly when you need it. Customer Success goes beyond basic technical support—it is a proactive partnership focused on value realization. We connect Recurly's capabilities with your specific business priorities, guiding you toward measurable outcomes.</p>

      <p style="margin-top: 24px; font-weight: 700; color: var(--offblack);">How we bring Customer Success to you</p>
      <div class="rc-card-grid rc-card-grid-3col">
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-laptop-code"></i></div>
          <h4>Strategic learning</h4>
          <p>Self-paced learning paths focused on the "why" and "how" of subscription growth, available whenever you need them.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-chart-pie"></i></div>
          <h4>Proactive insights</h4>
          <p>Monthly performance scorecards and proactive outreach based on your specific subscription health metrics.</p>
        </div>
        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-headset"></i></div>
          <h4>Live guidance</h4>
          <p>Direct access to Recurly experts through weekly Office Hours, 1:1 strategy sessions, and live workshops.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list rc-fa-section"></i> What's in this path</h2>
      <p>This path is your official orientation to the Navigate program. It walks you through how to access the central hub, how the Recurly Flywheel organizes our content, and how you can leverage our live events and proactive outreach to hit your growth goals.</p>
      <div class="rc-toc-list">
        <a href="/docs/navigate-intro-welcome" class="rc-toc-card">
          <div class="rc-toc-num" style="background: transparent !important;"><img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt="Current page" style="width: 20px; height: 20px;"></div>
          <div class="rc-toc-body">
            <h4>Welcome to Navigate</h4>
            <p><strong>You are here.</strong> An introduction to Customer Success and the comprehensive Navigate program.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="/docs/navigate-intro-home" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>Navigating Home</h4>
            <p>Understand the Recurly Flywheel and learn how to access and use the Navigate Home hub.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
        <a href="/docs/navigate-intro-expect" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Navigate full program</h4>
            <p>Explore all the offerings within the Navigate program, from monthly scorecards to expert sessions.</p>
          </div>
          <div class="rc-toc-arrow">→</div>
        </a>
      </div>
      
      <p style="font-size: .95rem; color: var(--darkgray); margin-bottom: 24px;">Next, we'll learn about the subscription flywheel and its place in Navigate to help you understand the foundation of the site and the program as a whole.</p>
    </div>

    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">Welcome overview</span>
      <a href="/docs/navigate-intro-home" class="rc-btn-path">Next: Navigating Home →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="/docs/navigate-home" class="rc-resource-link"><i class="fa-solid fa-house"></i> Navigate Home in Recurly Docs</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Welcome to Navigate</span>
          <a href="/docs/navigate-intro-welcome" class="rc-footer-link">Welcome to Navigate</a>
          <a href="/docs/navigate-intro-home" class="rc-footer-link">Navigating Home</a>
          <a href="/docs/navigate-intro-expect" class="rc-footer-link">Navigate full program</a>
        </div>
        <div class="rc-footer-utility">
          <a href="/docs/navigate-home" class="rc-footer-link">
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
