---
title: 'Editing Page: Learning Path'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Figtree:wght@400;500;600;700;800;900&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* HOST-THEME BACKGROUND OVERRIDE */
body { background: #ffffff !important; }

/* GLOBAL CSS IMMUNITY BLOCK */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
/* FA6 font restore: (0,0,2,0) beats wildcard (0,0,1,0); must follow wildcard */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR: (0,0,7,1) beats global section 1.1 rule (0,0,6,2).
   All .rc-guide a.[class] overrides are declared AFTER this block. */
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:active {
  color: #008CFF !important;
  text-decoration: none !important;
  text-decoration-line: none !important;
  text-decoration-color: transparent !important;
  text-underline-offset: unset !important;
  border-bottom: 0 !important;
}
.rc-guide a:hover {
  color: #0067BE !important;
  text-decoration: underline !important;
  text-decoration-color: #008CFF !important;
  text-underline-offset: 2px !important;
}

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --launch:     #FF5126;
  --yellow:     #FFD706;
  --blue:       #008CFF;
  --blue-tint1: #D5EAFF;
  --blue-tint2: #96C8FF;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D75;
  --lightgray:  #D1CFC4;
  --brightgray: #F2F1EA;
  --offwhite:   #FCFBF7;
  --warning-fg: #FFD706;
  --warning-bg: #FFFECB;
  --error-fg:   #FF5126;
  --error-bg:   #FFEEE9;
  --success-fg: #5DC32E;
  --success-bg: #EFFAEA;
  --info-fg:    #008CFF;
  --info-bg:    #E5F3FF;
  font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* FONT AWESOME ICON HELPERS */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* TOP NAV / BACK LINK */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link { color: #807D75 !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #008CFF !important; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ANNOUNCEMENT BAR (hidden by default; add rc-active to show) */
.rc-announce-bar {
  display: none; background: #FFD706; color: #0D0D0B;
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link {
  color: #0D0D0B !important; font-weight: 800; white-space: nowrap;
  padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px;
  transition: background 0.2s; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* HERO */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-lp-pillar-tag {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,81,38,0.20); border: 1px solid rgba(255,81,38,0.45);
  color: #FF5126 !important; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FCFBF7 !important; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto; color: #D1CFC4 !important; line-height: 1.6; }

/* NAVIGATION MENU (non-sticky, open) */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
  background-color: #FF5126;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: #0D0D0B; }
.rc-nav-chevron { font-size: .72rem; color: #0D0D0B; opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link {
  color: #0D0D0B !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px;
  text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s;
  white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; text-decoration: none !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: #0D0D0B; color: #FFD706; font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* CONTENT SECTIONS */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #D1CFC4; }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 16px; }

/* CALLOUT */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: #32312D; }
.rc-callout-tip { background: #F2F1EA; border-left: 4px solid #0D0D0B; }
.rc-callout-tip .rc-callout-body > strong { color: #0D0D0B; }

/* TABLE OF CONTENTS CARDS */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 24px; }
.rc-toc-card {
  display: grid; grid-template-columns: 44px 1fr 32px;
  align-items: center; gap: 16px;
  background: #FCFBF7; border: 1px solid #D1CFC4;
  border-radius: 12px; padding: 18px 22px;
  transition: all .2s ease;
}
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-toc-card { border-bottom: 1px solid #D1CFC4 !important; color: #32312D !important; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-toc-card:hover { border-color: #FF5126; border-bottom: 1px solid #FF5126 !important; box-shadow: 0 4px 14px rgba(255,81,38,0.12); transform: translateX(3px); text-decoration: none !important; color: #32312D !important; }
.rc-toc-num {
  width: 36px; height: 36px; border-radius: 50%;
  background: #0D0D0B; color: #FFD706 !important;
  display: flex; align-items: center; justify-content: center;
  font-size: .85rem; font-weight: 800; flex-shrink: 0;
}
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B !important; margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: #807D75 !important; line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: #D1CFC4 !important; text-align: right; transition: color .2s; }
.rm-Markdown.markdown-body .rc-guide a.rc-toc-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover .rc-toc-arrow,
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #FF5126 !important; }

/* PATH NAVIGATION */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; flex-wrap: wrap; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: #D1CFC4; letter-spacing: .5px; white-space: nowrap !important; flex-shrink: 0; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path { background: #FFD706; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; white-space: nowrap !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: #0D0D0B !important; border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important; text-decoration: none !important; }
.rc-btn-start { background: #F2F1EA; color: #807D75; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid #D1CFC4; cursor: default; display: inline-flex; align-items: center; white-space: nowrap !important; }

/* RESOURCES */
.rc-resources { background: #F2F1EA; border-left: 4px solid #FF5126; border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D75; margin: 0 0 12px; display: flex; align-items: center; gap: 8px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D75 !important; text-decoration: underline !important; text-underline-offset: 3px;
  text-decoration-color: #D1CFC4 !important; font-weight: 500; font-size: .88rem;
  transition: all .18s; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover { color: #0D0D0B !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FF5126 !important; }

/* FOOTER NAV */
.rc-footer-nav { border-top: 1px solid #D1CFC4; padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: #32312D; background: #F2F1EA; padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D75 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #008CFF !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid #F2F1EA; }

/* RESPONSIVE (consolidated) */
@media(max-width:1300px) {
  .rc-lp-nav { justify-content: center !important; gap: 12px; }
  .rc-lp-nav-indicator { width: 100% !important; text-align: center; }
}
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
  .rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
  .rc-guide a.rc-btn-path,
  .rc-btn-start { padding: 10px 16px !important; font-size: 0.82rem !important; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">&larr; Back to Launch</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now &rarr;</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch &middot; Easy HTML guide
      </div>
      <div class="rc-lp-hero-title"><h1>Easy HTML guide: Overview</h1></div>
      <p>Brand every Recurly email with HTML, even if you have never edited a template.</p>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary><span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Path overview
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-sticky-link"><span class="rc-step-badge">1</span> HTML basics</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-merge-tags" class="rc-sticky-link"><span class="rc-step-badge">2</span> Merge tags</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-styling" class="rc-sticky-link"><span class="rc-step-badge">3</span> Styling &amp; layout</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-testing" class="rc-sticky-link"><span class="rc-step-badge">4</span> Testing &amp; previewing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-sticky-link"><span class="rc-step-badge">5</span> Common snippets</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-review" class="rc-sticky-link"><span class="rc-step-badge">6</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Launch
        </a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-code rc-fa-section"></i> What this path covers</h2>
      <p>Recurly builds each subscriber email from a template you can customize with HTML. This path covers the header and footer, merge tags, styling, and testing.</p>
      <p>You copy a block, replace the placeholder values, and check the result in Preview. No web development experience needed.</p>
      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body">
          <strong>What you need</strong>
          <p>Access to <strong>Configuration &rarr; Email Templates</strong>, a logo hosted at a public HTTPS URL, your brand hex colors and font stack, and links to your Subscription Terms and Privacy Policy.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-list-ol rc-fa-section"></i> What's inside</h2>
      <div class="rc-toc-list">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-toc-card">
          <div class="rc-toc-num">1</div>
          <div class="rc-toc-body">
            <h4>HTML basics</h4>
            <p>Find the header and footer templates and edit them safely.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-merge-tags" class="rc-toc-card">
          <div class="rc-toc-num">2</div>
          <div class="rc-toc-body">
            <h4>Merge tags</h4>
            <p>Insert account, plan, and invoice details that Recurly fills in at send time.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-styling" class="rc-toc-card">
          <div class="rc-toc-num">3</div>
          <div class="rc-toc-body">
            <h4>Styling &amp; layout</h4>
            <p>Set colors, fonts, and widths that hold up in Gmail and Outlook.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-testing" class="rc-toc-card">
          <div class="rc-toc-num">4</div>
          <div class="rc-toc-body">
            <h4>Testing &amp; previewing</h4>
            <p>Preview, send a test, and confirm your email is live and ready.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-toc-card">
          <div class="rc-toc-num">5</div>
          <div class="rc-toc-body">
            <h4>Common snippets</h4>
            <p>Copy HTML for your logo, footer, conditional messages, and social links.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-review" class="rc-toc-card">
          <div class="rc-toc-num">6</div>
          <div class="rc-toc-body">
            <h4>Review &amp; resources</h4>
            <p>Check what you learned and find every link in one place.</p>
          </div>
          <div class="rc-toc-arrow">&rarr;</div>
        </a>
      </div>
      <p>Work through the pages in order. Each one builds on the last.</p>
    </div>

    <div class="rc-lp-nav">
      <span class="rc-btn-start">&larr; Start</span>
      <span class="rc-lp-nav-indicator">Overview</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-btn-path">1. HTML basics &rarr;</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email templates</a>
        <a href="https://docs.google.com/document/d/1gE2fRLSSm1gjcR5d5NuUFYHTxZYl4AWHgRPghOC52uQ/edit?usp=sharing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Email HTML template guide</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Easy HTML guide</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide" class="rc-footer-link">Path overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-footer-link">1. HTML basics</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-merge-tags" class="rc-footer-link">2. Merge tags</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-styling" class="rc-footer-link">3. Styling &amp; layout</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-testing" class="rc-footer-link">4. Testing &amp; previewing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-footer-link">5. Common snippets</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-review" class="rc-footer-link">6. Review &amp; resources</a>
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
