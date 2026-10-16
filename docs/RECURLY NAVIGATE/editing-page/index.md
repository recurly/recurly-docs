---
title: 12 Days Editing Page
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Figtree:wght@400;500;600;700;800;900&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* ── HOST-THEME BACKGROUND OVERRIDE ── */
body { background: #ffffff !important; }

/* ── GLOBAL CSS IMMUNITY BLOCK ── */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* ── NAVIGATE MASTER ARMOR ── */
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

/* ── DESIGN TOKENS ── */
.rc-guide {
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

  --launch:      #FF5126;
  --acquire:     #FFD706;
  --retain:      #2DCECE;
  --scale:       #008CFF;
  --pillar:      #FFD706;
  --pillar-rgb:  255, 215, 6;

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

/* ── FONT AWESOME HELPERS ── */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1.1rem; }

/* ── TOP NAV & CONTENT CONTAINER ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link {
  color: #807D75 !important;
  font-weight: 700;
  font-size: .9rem;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  transition: color .2s;
  border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover {
  color: #008CFF !important;
}
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── ANNOUNCEMENT BAR ── */
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
.rc-guide a.rc-announce-link:hover {
  background: rgba(0,0,0,0.20); color: #0D0D0B !important;
}

/* ── HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack); background-size: cover;
  color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; }
.rc-logo-image { height: 28px; display: block; }
.rc-home-title-block { margin-top: 36px; }
.rc-home-title-block h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0 0 16px; }
.rc-hero p { font-size: 1rem; opacity: .85; max-width: 720px; margin: 0 auto 12px; color: var(--lightgray); line-height: 1.6; }

/* ── STICKY NAV ── */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--brightgray);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 40px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label {
  display: inline-flex; align-items: center; gap: 8px; font-weight: 800;
  font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack);
}
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
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
.rc-guide a.rc-sticky-link:hover {
  background: rgba(0,0,0,0.10); color: #0D0D0B !important;
}
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }

/* ── SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── CALLOUTS ── */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body > strong { color: var(--darkgray); }

/* ── INLINE BODY LINKS ── */
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-inline-link {
  color: #008CFF !important; font-weight: 600; border-bottom: 0 !important; text-decoration: none !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-inline-link:hover {
  color: #0067BE !important; text-decoration: underline !important;
  text-decoration-color: #008CFF !important; text-underline-offset: 2px !important;
}

/* ── ADVENT CALENDAR 12-DAY GRID ── */
.rc-advent-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin: 24px 0 32px;
}
.rm-Markdown.markdown-body .rc-guide a.rc-advent-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-advent-card {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-bottom: 1px solid var(--lightgray) !important;
  border-radius: 12px;
  padding: 22px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  text-decoration: none !important;
  transition: all .2s ease;
}
.rm-Markdown.markdown-body .rc-guide a.rc-advent-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-advent-card:hover {
  border-color: var(--yellow) !important;
  border-bottom: 1px solid var(--yellow) !important;
  box-shadow: 0 4px 18px rgba(255, 215, 6, 0.22);
  transform: translateY(-2px);
  text-decoration: none !important;
}
.rc-advent-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.rc-advent-badge {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: #0D0D0B !important;
  color: #FFD706 !important;
  padding: 4px 10px;
  border-radius: 16px;
  font-size: .72rem;
  font-weight: 800;
  letter-spacing: .5px;
  text-transform: uppercase;
}
.rc-advent-format {
  font-size: .74rem;
  font-weight: 700;
  color: #807D75 !important;
  display: inline-flex;
  align-items: center;
  gap: 5px;
}
.rc-advent-card h4 {
  font-size: 1rem;
  font-weight: 800;
  color: #0D0D0B !important;
  margin: 0;
  line-height: 1.35;
}
.rc-advent-card p {
  font-size: .88rem;
  color: #807D75 !important;
  line-height: 1.55;
  margin: 0;
  flex-grow: 1;
}
.rc-advent-action {
  font-size: .84rem;
  font-weight: 700;
  color: #008CFF !important;
  margin-top: 4px;
}

/* ── PRIZE TIERS (3-COLUMN CARD GRID) ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease;
}
.rc-feature-card:hover {
  border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,0.18); transform: translateY(-2px);
}
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: var(--offblack); }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag {
  display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px;
  font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: var(--offblack);
  color: var(--yellow); width: fit-content;
}

/* ── FORM EMBED CONTAINER (WRIKE TRACKER) ── */
.rc-form-card {
  border: 1px solid var(--lightgray);
  border-radius: 14px;
  overflow: hidden;
  margin: 20px 0 40px;
  background: #ffffff;
}
.rc-form-header {
  background: var(--offblack);
  padding: 16px 22px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.rc-form-header h4 {
  font-size: .88rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: .7px;
  color: var(--yellow);
  margin: 0;
}
.rc-form-header span {
  font-size: .78rem;
  color: var(--lightgray);
  margin-left: auto;
}
.rc-form-frame {
  width: 100%;
  background: #ffffff;
  min-height: 580px;
}
.rc-form-frame iframe {
  display: block;
  width: 100%;
  height: 580px;
  border: none;
}
.rc-form-caption {
  padding: 12px 22px;
  font-size: .83rem;
  color: var(--gray);
  background: var(--brightgray);
  border-top: 1px solid var(--lightgray);
  line-height: 1.5;
}

/* ── WEBINAR CTA BLOCK ── */
.rc-webinar-cta {
  background: #0D0D0B !important;
  border: 2px solid var(--yellow);
  border-radius: 14px;
  padding: 32px 36px;
  margin: 0 0 40px;
  display: flex;
  align-items: center;
  gap: 28px;
}
.rc-webinar-cta-icon { font-size: 2.2rem; flex-shrink: 0; line-height: 1; }
.rc-webinar-cta-body { flex: 1; }
.rc-webinar-cta-body p {
  font-size: .95rem; color: #FCFBF7 !important; line-height: 1.6; margin: 0 0 18px;
}
.rc-webinar-cta-body p em { font-style: normal; font-weight: 700; color: #ffffff !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-webinar-btn {
  background: var(--yellow) !important;
  color: #0D0D0B !important;
  text-decoration: none !important;
  padding: 12px 24px;
  border-radius: 10px;
  font-weight: 800;
  font-size: .9rem;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: all .2s;
  border: 2px solid var(--yellow) !important;
  border-bottom: 2px solid var(--yellow) !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-webinar-btn:hover {
  background: transparent !important;
  color: var(--yellow) !important;
  border: 2px solid var(--yellow) !important;
  border-bottom: 2px solid var(--yellow) !important;
}

/* ── RESOURCES BLOCK ── */
.rc-resources {
  background: var(--brightgray);
  border-left: 4px solid var(--yellow);
  border-radius: 10px;
  padding: 20px 24px;
  margin: 32px 0 0;
}
.rc-resources h3 {
  font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px;
  color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px;
}
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D75 !important;
  text-decoration: underline !important;
  text-underline-offset: 3px;
  text-decoration-color: #D1CFC4 !important;
  font-weight: 500;
  font-size: .88rem;
  transition: all .18s;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover {
  color: #0D0D0B !important;
  text-decoration: underline !important;
  text-underline-offset: 3px;
  text-decoration-color: #FFD706 !important;
}

/* ── FOOTER NAV ── */
.rc-footer-nav {
  border-top: 1px solid var(--lightgray);
  padding-top: 40px;
  margin-top: 48px;
  padding-bottom: 48px;
}
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label {
  font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px;
  color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px;
  margin-right: 4px;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D75 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #008CFF !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── CONSOLIDATED RESPONSIVE BREAKPOINT ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-home-title-block h1 { font-size: 1.8rem; }
  .rc-advent-grid { grid-template-columns: 1fr; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-webinar-cta { flex-direction: column; gap: 16px; padding: 24px 22px; }
}
</style>

<div class="rc-guide">

  <!-- Top back link -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Home</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Active Announcement Bar -->
    <div class="rc-announce-bar rc-active">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Campaign live:</strong> Complete daily micro-tasks, submit your progress, and earn prizes.
        <a href="#activities" class="rc-announce-link">View daily activities →</a>
      </div>
    </div>

    <!-- Hero Section -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>
      <div class="rc-home-title-block">
        <h1>12 days of subscriptions</h1>
        <p>Explore our latest release features through daily 3-minute videos, practical configuration tips, and quick knowledge checks. Log your completed tasks to earn tier prizes and secure your seat for our exclusive Q1 2027 release webinar.</p>
      </div>
    </div>

    <!-- Sticky Navigation Menu -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="#activities" class="rc-sticky-link">12 days activities</a>
            <a href="#rewards" class="rc-sticky-link">Prizes &amp; rewards</a>
            <a href="#tracker" class="rc-sticky-link">Activity tracker</a>
            <a href="#webinar" class="rc-sticky-link">Q1 2027 webinar</a>
            <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Office Hours
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Overview Callout -->
    <div class="rc-callout rc-callout-tip">
      <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
      <div class="rc-callout-body">
        <strong>How to participate in the 12 days</strong>
        <p>Each card below links to a dedicated activity hidden within Navigate. Every task is designed to be completed in 3 minutes or less. Once finished, submit the form at the bottom of the page using your account email to log your activity.</p>
      </div>
    </div>

    <!-- Section 1: The 12 Days Advent Grid -->
    <div class="rc-lp-section" id="activities">
      <h2><i class="fa-solid fa-calendar-days rc-fa-section"></i> 12 days calendar</h2>
      <p>Click into each daily module below to access the video, tip, or knowledge check.</p>

      <div class="rc-advent-grid">

        <!-- Day 1 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-1" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 1</span>
            <span class="rc-advent-format"><i class="fa-solid fa-video"></i> Video · 3 min</span>
          </div>
          <h4>Release walkthrough &amp; architecture</h4>
          <p>Get a concise visual tour of our newest capabilities and core workflow updates.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 2 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-2" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 2</span>
            <span class="rc-advent-format"><i class="fa-solid fa-lightbulb"></i> Best practice</span>
          </div>
          <h4>Optimizing transaction descriptors</h4>
          <p>Reduce cardholder confusion and dispute volume with clear dynamic statement text.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 3 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-3" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 3</span>
            <span class="rc-advent-format"><i class="fa-solid fa-circle-question"></i> Quiz · 2 min</span>
          </div>
          <h4>Involuntary churn diagnostic</h4>
          <p>Test your knowledge on passive churn drivers and retry logic configurations.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 4 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-4" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 4</span>
            <span class="rc-advent-format"><i class="fa-solid fa-video"></i> Video · 3 min</span>
          </div>
          <h4>Account Updater in action</h4>
          <p>See how automated card refreshes keep billing continuity intact behind the scenes.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 5 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-5" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 5</span>
            <span class="rc-advent-format"><i class="fa-solid fa-lightbulb"></i> Best practice</span>
          </div>
          <h4>Calibrating dunning windows</h4>
          <p>Learn why a 27-day monthly cycle prevents duplicate invoices from triggering.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 6 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-6" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 6</span>
            <span class="rc-advent-format"><i class="fa-solid fa-circle-question"></i> Quiz · 2 min</span>
          </div>
          <h4>Gateway failover &amp; routing</h4>
          <p>Confirm how backup gateways capture revenue during unexpected processing outages.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 7 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-7" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 7</span>
            <span class="rc-advent-format"><i class="fa-solid fa-video"></i> Video · 3 min</span>
          </div>
          <h4>Subscriber wallet &amp; payment methods</h4>
          <p>Watch how storing secondary payment methods protects recurring subscriptions.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 8 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-8" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 8</span>
            <span class="rc-advent-format"><i class="fa-solid fa-lightbulb"></i> Best practice</span>
          </div>
          <h4>Pause rules versus cancellations</h4>
          <p>Discover how offering a temporary pause reduces voluntary subscriber churn.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 9 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-9" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 9</span>
            <span class="rc-advent-format"><i class="fa-solid fa-circle-question"></i> Quiz · 2 min</span>
          </div>
          <h4>Promotions &amp; coupon logic</h4>
          <p>Evaluate edge cases for stacking discounts and setting bulk unique redemption limits.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 10 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-10" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 10</span>
            <span class="rc-advent-format"><i class="fa-solid fa-lightbulb"></i> Best practice</span>
          </div>
          <h4>Customizing invoice branding</h4>
          <p>Align renewal notices and receipts directly with your company visual identity.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 11 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-11" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 11</span>
            <span class="rc-advent-format"><i class="fa-solid fa-video"></i> Video · 3 min</span>
          </div>
          <h4>Payments Hub dashboard insights</h4>
          <p>Identify decline reasons and monitor recovery metrics in one unified dashboard.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 12 -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-12" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-advent-badge">Day 12</span>
            <span class="rc-advent-format"><i class="fa-solid fa-circle-question"></i> Quiz · 2 min</span>
          </div>
          <h4>The 12-day capstone challenge</h4>
          <p>Complete the final knowledge check to lock in your grand prize drawing entry.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

      </div>
    </div>

    <!-- Section 2: Prizes and Rewards -->
    <div class="rc-lp-section" id="rewards">
      <h2><i class="fa-solid fa-trophy rc-fa-section"></i> Campaign rewards and tracking</h2>
      <p>Participation earns entry into tiered prize brackets based on total tasks logged before the campaign closes.</p>

      <div class="rc-card-grid">

        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-crown"></i></div>
          <h4>Grand champion</h4>
          <p>Awarded to participants who finish all 12 activities. Includes premium Recurly gear, team swag bundle, and priority access to new release betas.</p>
          <span class="rc-feature-tag">12 of 12 complete</span>
        </div>

        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-medal"></i></div>
          <h4>Momentum tier</h4>
          <p>Awarded to merchants completing at least 8 activities. Includes customized Recurly merchandise and entry into our strategy raffle.</p>
          <span class="rc-feature-tag">8+ activities</span>
        </div>

        <div class="rc-feature-card">
          <div class="rc-feature-icon"><i class="fa-solid fa-ticket"></i></div>
          <h4>Active participant</h4>
          <p>Every merchant who completes at least one module receives a guaranteed VIP invite to our Q1 2027 feature webinar.</p>
          <span class="rc-feature-tag">1+ activity</span>
        </div>

      </div>
    </div>

    <!-- Section 3: Wrike Activity Completion Tracker -->
    <div class="rc-lp-section" id="tracker">
      <h2><i class="fa-solid fa-clipboard-check rc-fa-section"></i> Log your activity</h2>
      <p>Submit your task completion directly through the secure form below. Make sure to use the same email address for all submissions so your points aggregate accurately.</p>

      <div class="rc-form-card">
        <div class="rc-form-header">
          <h4><i class="fa-solid fa-list-check" style="color: var(--yellow); margin-right: 8px;"></i> Activity completion submission</h4>
          <span>Wrike form embed</span>
        </div>
        <div class="rc-form-frame">
          <!-- Replace YOUR_WRIKE_FORM_ID with your specific Wrike permanent embed URL -->
          <iframe src="https://www.wrike.com/form/YOUR_WRIKE_FORM_ID" title="12 days of subscriptions completion form" loading="lazy"></iframe>
        </div>
        <div class="rc-form-caption">
          Trouble viewing the form? You can also <a href="https://www.wrike.com/form/YOUR_WRIKE_FORM_ID" target="_blank" rel="noopener noreferrer" class="rc-inline-link rp-anchor">open the standalone submission form in a new tab →</a>
        </div>
      </div>
    </div>

    <!-- Section 4: Q1 2027 Webinar CTA -->
    <div class="rc-webinar-cta" id="webinar">
      <div class="rc-webinar-cta-icon"><i class="fa-solid fa-circle-play rc-fa-dark"></i></div>
      <div class="rc-webinar-cta-body">
        <p>All participants completing at least one activity earn an exclusive invitation to our live <em>Q1 2027 feature release and strategy webinar</em>. Join our product directors for an interactive roadmap reveal and live Q&amp;A.</p>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-webinar-btn">Reserve your seat →</a>
      </div>
    </div>

    <!-- Section 5: Standard Resources Block -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly documentation</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Customer Success Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-envelope"></i> Contact support</a>
      </div>
    </div>

    <!-- Standard Learning Path / Hub Footer Nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">12 days of subscriptions</span>
          <a href="#activities" class="rc-footer-link">Daily activities</a>
          <a href="#rewards" class="rc-footer-link">Campaign prizes</a>
          <a href="#tracker" class="rc-footer-link">Submit completion</a>
          <a href="#webinar" class="rc-footer-link">Q1 2027 webinar</a>
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
