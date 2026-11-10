---
title: 'Easy HTML guide: Review'
excerpt: >-
  Review essential best practices for launching Recurly email templates with
  this comprehensive QA checklist, covering merge tag rules, safe fallback
  fonts, testing protocols, and next steps for your automated subscription
  communications.
deprecated: false
hidden: true
metadata:
  description: >-
    Review essential best practices for launching Recurly email templates with
    this comprehensive QA checklist, covering merge tag rules, safe fallback
    fonts, testing protocols, and next steps for your automated subscription
    communications.
  keywords:
    - Recurly email template checklist
    - HTML email best practices
    - Recurly merge tag rules
    - transactional email QA
    - fallback fonts for Gmail
    - deploying Recurly emails
    - email branding review
    - testing subscription emails
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


/* CALLOUT VARIANTS */
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid #FFD706; }
.rc-callout-warning .rc-callout-body > strong { color: #32312D; }
.rc-callout-caution { background: #FFFECB; border-left: 4px solid #FFD706; }
.rc-callout-caution .rc-callout-body > strong { color: #32312D; }
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-body a { color: #008CFF !important; font-weight: 600; border-bottom: 0 !important; }

/* INLINE LINK + INLINE CODE */
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-inline-link { color: #008CFF !important; font-weight: 600; border-bottom: 0 !important; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-inline-link:hover { color: #0067BE !important; text-decoration: underline !important; text-decoration-color: #008CFF !important; text-underline-offset: 2px !important; }

.rc-guide code.rc-ic { background: #F2F1EA !important; color: #0D0D0B !important; padding: 2px 7px !important; border-radius: 4px !important; font-size: .82rem !important; border: 0 !important; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace !important; white-space: normal; }
.rc-lp-section p strong, .rc-step-content p strong { color: #32312D; }

/* NUMBERED STEPS */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid #F2F1EA; }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: #0D0D0B; color: #FFD706 !important; display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content { min-width: 0; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: #0D0D0B; margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: #807D75; line-height: 1.6; margin: 0; }
.rc-step-content strong { color: #32312D; }
.rm-Markdown.markdown-body .rc-guide .rc-step-content a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-step-content a { color: #008CFF !important; font-weight: 600; border-bottom: 0 !important; }

/* CARD GRID */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0 8px; }
.rc-feature-card { background: #FCFBF7; border: 1px solid #D1CFC4; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-feature-card:hover { border-color: #FF5126; box-shadow: 0 4px 16px rgba(255,81,38,0.15); transform: translateY(-2px); }
.rc-feature-icon { font-size: 1.4rem; line-height: 1; color: #0D0D0B; }
.rc-feature-card h4 { font-size: .98rem; font-weight: 800; color: #0D0D0B; margin: 0; }
.rc-feature-card p { font-size: .88rem; color: #807D75; line-height: 1.55; margin: 0; flex-grow: 1; }

/* CODE BLOCK (new component) */
.rc-code-block { background: #0D0D0B !important; border: 1px solid #32312D !important; border-radius: 12px; margin: 16px 0 20px; overflow: hidden; }
.rc-code-head { display: flex; justify-content: space-between; align-items: center; gap: 12px; flex-wrap: wrap; padding: 8px 16px; background: #32312D !important; }
.rc-code-label { font-size: .68rem; font-weight: 800; letter-spacing: .8px; text-transform: uppercase; color: #FFD706 !important; }
.rc-code-legend { font-size: .68rem; font-weight: 600; color: #D1CFC4 !important; }
.rc-code-legend .rc-lg-ph { color: #FFD706 !important; font-weight: 800; }
.rc-code-legend .rc-lg-tag { color: #96C8FF !important; font-weight: 800; }
.rm-Markdown.markdown-body .rc-guide pre.rc-code-pre,
.rc-guide pre.rc-code-pre { margin: 0 !important; padding: 16px 18px !important; background: #0D0D0B !important; border: 0 !important; border-radius: 0 !important; box-shadow: none !important; overflow-x: auto !important; white-space: pre !important; }
.rm-Markdown.markdown-body .rc-guide pre.rc-code-pre code,
.rc-guide pre.rc-code-pre code,
.rc-guide pre.rc-code-pre code span { background: transparent !important; color: #FCFBF7 !important; font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace !important; font-size: .8rem !important; line-height: 1.7 !important; padding: 0 !important; border: 0 !important; white-space: pre !important; }
.rc-guide pre.rc-code-pre code span.rc-c-ph { color: #FFD706 !important; font-weight: 700 !important; }
.rc-guide pre.rc-code-pre code span.rc-c-tag { color: #96C8FF !important; }
.rc-guide pre.rc-code-pre code span.rc-c-cm { color: #807D75 !important; }

/* REFERENCE TABLE (new component) */
.rc-table-wrap { overflow-x: auto; margin: 16px 0 24px; border: 1px solid #D1CFC4 !important; border-radius: 12px; background: #FCFBF7 !important; }
.rm-Markdown.markdown-body .rc-guide table.rc-ref-table,
.rc-guide table.rc-ref-table { width: 100% !important; display: table !important; border-collapse: collapse !important; margin: 0 !important; border: 0 !important; font-size: .88rem !important; }
.rm-Markdown.markdown-body .rc-guide table.rc-ref-table th,
.rc-guide table.rc-ref-table th { background: #0D0D0B !important; color: #FFD706 !important; text-align: left !important; font-size: .72rem !important; font-weight: 800 !important; text-transform: uppercase !important; letter-spacing: .7px !important; padding: 10px 16px !important; border: 0 !important; }
.rm-Markdown.markdown-body .rc-guide table.rc-ref-table td,
.rc-guide table.rc-ref-table td { background: #FCFBF7 !important; color: #32312D !important; padding: 11px 16px !important; border: 0 !important; border-bottom: 1px solid #F2F1EA !important; line-height: 1.5 !important; vertical-align: top !important; }
.rm-Markdown.markdown-body .rc-guide table.rc-ref-table tbody tr:last-child td,
.rc-guide table.rc-ref-table tbody tr:last-child td { border-bottom: 0 !important; }
.rc-guide table.rc-ref-table td:first-child { white-space: nowrap; font-weight: 700 !important; color: #0D0D0B !important; }
.rc-guide table.rc-ref-table td code.rc-ic { white-space: nowrap; }

/* CHECKLIST (pure CSS) */
.rc-fa-yellow { color: #FFD706; font-size: 1rem; }
.rc-checklist { background: #FCFBF7; border: 1px solid #D1CFC4; border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-checklist-header { padding: 14px 22px; background: #0D0D0B; display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #FFD706 !important; margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid #F2F1EA; display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: #F2F1EA; }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid #D1CFC4; flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: #0D0D0B; border-color: #0D0D0B; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '\2713'; color: #FFD706; font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: #807D75; }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: #EFFAEA; }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: #0D0D0B; display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: #807D75; line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: #F2F1EA; border-top: 1px solid #D1CFC4; font-size: .78rem; color: #807D75; font-weight: 600; }

/* QUIZ */
.rc-quiz-card { background: #FCFBF7; border: 1px solid #D1CFC4; border-radius: 14px; overflow: hidden; padding: 22px 24px; margin: 20px 0; }
.rc-quiz-label { display: inline-block; background: #0D0D0B; color: #FFD706 !important; font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; padding: 3px 8px; border-radius: 5px; margin-bottom: 10px; }
.rc-quiz-q { font-size: 1rem; font-weight: 800; color: #0D0D0B; margin: 0 0 16px; line-height: 1.45; }
.rc-quiz-options { display: flex; flex-direction: column; gap: 8px; margin-bottom: 16px; }
.rc-quiz-option { display: flex; align-items: center; gap: 10px; padding: 10px 14px; border-radius: 8px; border: 1px solid #D1CFC4; background: #fff; cursor: pointer; transition: all .18s; }
.rc-quiz-option input[type="radio"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-radio-dot { width: 16px; height: 16px; border-radius: 50%; border: 2px solid #D1CFC4; flex-shrink: 0; background: #fff; transition: all .18s; }
.rc-quiz-option:has(input[type="radio"]:checked) .rc-radio-dot { background: #0D0D0B; border-color: #0D0D0B; }
.rc-option-text { font-size: .9rem; color: #32312D; line-height: 1.4; }
.rc-quiz-option.rc-quiz-correct:has(input[type="radio"]:checked) { background: #EFFAEA; border-color: #5DC32E; }
.rc-quiz-option:not(.rc-quiz-correct):has(input[type="radio"]:checked) { background: #FFEEE9; border-color: #FF5126; }
details.rc-quiz-reveal > summary::-webkit-details-marker { display: none; }
details.rc-quiz-reveal > summary::marker { display: none; }
details.rc-quiz-reveal > summary::before { content: "\25B6"; font-size: .58rem; display: inline-block; transition: transform .2s; margin-right: 6px; }
details.rc-quiz-reveal[open] > summary::before { transform: rotate(90deg); }
details.rc-quiz-reveal > summary { font-size: .82rem; font-weight: 700; color: #807D75; cursor: pointer; user-select: none; display: inline-flex; align-items: center; }
.rc-quiz-answer { margin-top: 10px; background: #F2F1EA; border-radius: 8px; padding: 12px 16px; font-size: .88rem; color: #32312D; line-height: 1.55; }
.rc-quiz-answer strong { color: #0D0D0B; }

/* REFLECTION CARD */
.rc-reflect-card { background: #FCFBF7; border: 1px solid #D1CFC4; border-left: 4px solid #FFD706; border-radius: 14px; padding: 24px 28px; margin: 20px 0; }
.rc-reflect-label { display: inline-block; background: #FFD706; color: #0D0D0B !important; font-size: .72rem; font-weight: 800; text-transform: uppercase; letter-spacing: .6px; padding: 3px 10px; border-radius: 5px; margin-bottom: 12px; }
.rc-reflect-card h4 { font-size: 1rem; font-weight: 800; color: #0D0D0B; margin: 0 0 10px; line-height: 1.4; }
.rc-reflect-card p { font-size: .9rem; color: #807D75; line-height: 1.6; margin: 0; }

/* PATH NAV: PREV + COMPLETE */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-prev { background: transparent; color: #0D0D0B !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #D1CFC4 !important; border-bottom: 2px solid #D1CFC4 !important; transition: all .2s; white-space: nowrap !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-prev:hover { border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important; color: #0D0D0B !important; text-decoration: none !important; }

.rc-btn-complete { background: #F2F1EA; color: #0D0D0B !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid #FFD706; cursor: default; user-select: none; white-space: nowrap !important; }

/* CONTINUE YOUR JOURNEY */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: #807D75; margin: 0 0 16px; display: flex; align-items: center; gap: 8px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-next-card { background: #FCFBF7; border: 1px solid #D1CFC4; border-bottom: 1px solid #D1CFC4 !important; border-radius: 12px; padding: 20px; color: #32312D !important; text-decoration: none !important; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-next-card:hover { border-color: #FF5126; border-bottom: 1px solid #FF5126 !important; box-shadow: 0 4px 16px rgba(255,81,38,0.15); transform: translateY(-2px); text-decoration: none !important; color: #32312D !important; }

.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: #FF5126 !important; margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; color: #0D0D0B !important; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: #0D0D0B !important; margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: #807D75 !important; line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: #008CFF !important; margin-top: 4px; }

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
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
  .rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
  .rc-guide a.rc-btn-path,
  .rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
  .rc-guide a.rc-btn-prev,
  .rc-btn-start, .rc-btn-complete { padding: 10px 16px !important; font-size: 0.82rem !important; }
}
</style>

<div class="rc-guide">
<div class="rc-top-nav"><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">&larr; Back to Launch</a></div>
<div class="rc-content-wrap">
<div class="rc-announce-bar"><div class="rc-announce-inner"><i class="fa-regular fa-calendar-days rc-fa-announce"></i> <strong>Upcoming:</strong> Join our CSMs for a live session. <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now &rarr;</a></div></div>
<div class="rc-hero">
<div class="rc-lp-pillar-tag"><img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch &middot; Easy HTML guide</div>
<div class="rc-lp-hero-title"><h1>Review &amp; resources</h1></div>
<p>Check what you learned and find every link in one place.</p>
</div>
<details class="rc-sticky-nav-wrap" open>
<summary><span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span></summary>
<div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link"><img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide" class="rc-sticky-link">Path overview</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-sticky-link"><span class="rc-step-badge">1</span> HTML basics</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-merge-tags" class="rc-sticky-link"><span class="rc-step-badge">2</span> Merge tags</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-styling" class="rc-sticky-link"><span class="rc-step-badge">3</span> Styling &amp; layout</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-testing" class="rc-sticky-link"><span class="rc-step-badge">4</span> Testing &amp; previewing</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-sticky-link"><span class="rc-step-badge">5</span> Common snippets</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-review" class="rc-sticky-link rc-sticky-link-active"><img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Review &amp; resources</a>

</div></div></div>
</details>
<div class="rc-lp-section">
<h2><i class="fa-solid fa-trophy rc-fa-section"></i> Nice work</h2>
<p>You can now edit Recurly's email header and footer, use merge tags, style safely, and test before anything goes live.</p>
</div><div class="rc-lp-section">
<h2><i class="fa-solid fa-circle-question rc-fa-section"></i> Check your understanding</h2>
<div class="rc-quiz-card">
<span class="rc-quiz-label">Question 1 of 3 &middot; Multiple choice</span>
<p class="rc-quiz-q">What do you do with a merge tag such as <code class="rc-ic">&#123;&#123;account_email&#125;&#125;</code>?</p>
<div class="rc-quiz-options" id="quiz1">
<label class="rc-quiz-option"><input type="radio" name="quiz1" value="a"><div class="rc-radio-dot"></div><span class="rc-option-text">Replace it with the subscriber's email</span></label>
<label class="rc-quiz-option rc-quiz-correct"><input type="radio" name="quiz1" value="b"><div class="rc-radio-dot"></div><span class="rc-option-text">Leave it exactly as written</span></label>
<label class="rc-quiz-option"><input type="radio" name="quiz1" value="c"><div class="rc-radio-dot"></div><span class="rc-option-text">Delete it from the footer</span></label>
<label class="rc-quiz-option"><input type="radio" name="quiz1" value="d"><div class="rc-radio-dot"></div><span class="rc-option-text">Add a fourth curly brace</span></label>
</div>
<details class="rc-quiz-reveal"><summary>See answer</summary><div class="rc-quiz-answer"><strong>Leave it exactly as written.</strong> Recurly replaces the tag with the subscriber's data when it sends the email.</div></details>
</div><div class="rc-quiz-card">
<span class="rc-quiz-label">Question 2 of 3 &middot; Multiple choice</span>
<p class="rc-quiz-q">Why should every font stack end with Arial or Helvetica?</p>
<div class="rc-quiz-options" id="quiz2">
<label class="rc-quiz-option"><input type="radio" name="quiz2" value="a"><div class="rc-radio-dot"></div><span class="rc-option-text">Recurly requires both fonts</span></label>
<label class="rc-quiz-option rc-quiz-correct"><input type="radio" name="quiz2" value="b"><div class="rc-radio-dot"></div><span class="rc-option-text">Gmail and Outlook for Windows ignore custom fonts and use the next font in the stack</span></label>
<label class="rc-quiz-option"><input type="radio" name="quiz2" value="c"><div class="rc-radio-dot"></div><span class="rc-option-text">They load faster than WOFF2 files</span></label>
<label class="rc-quiz-option"><input type="radio" name="quiz2" value="d"><div class="rc-radio-dot"></div><span class="rc-option-text">They turn on the mobile layout</span></label>
</div>
<details class="rc-quiz-reveal"><summary>See answer</summary><div class="rc-quiz-answer"><strong>Gmail and Outlook for Windows ignore custom fonts.</strong> A safe fallback keeps your layout intact.</div></details>
</div><div class="rc-reflect-card"><span class="rc-reflect-label">Question 3 of 3 &middot; Exercise</span><h4>Apply it to one email</h4><p>Pick one template, add your logo and footer, send a test to a colleague, and open it in Gmail and Outlook. What is the first thing you would fix?</p></div>
</div><div class="rc-lp-section">
<h2><i class="fa-solid fa-list-check rc-fa-section"></i> Best practices checklist</h2>
<div class="rc-checklist" id="rcChecklist"><div class="rc-checklist-header"><i class="fa-solid fa-list-check rc-fa-yellow"></i><h4>Before you go live</h4></div>
<label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Replace only placeholder values</strong><span>Keep every quote and bracket intact.</span></div></label><label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Leave merge tags as written</strong><span>Use three braces for currency.</span></div></label><label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Set a fallback font</strong><span>End your stack with Arial or Helvetica.</span></div></label><label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Preview and send a test</strong><span>Check Gmail, Outlook, desktop, and mobile.</span></div></label><label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Click every link</strong><span>Include Subscription Terms and Privacy Policy.</span></div></label><label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Email live and ready</strong><span>Template saved, enabled, and test checked.</span></div></label>
<div class="rc-checklist-footer">Tap each item to mark it complete</div></div>
</div>
<div class="rc-lp-nav">
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-btn-prev">&larr; Common snippets</a>
<span class="rc-lp-nav-indicator">6 of 6</span>
<span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Path complete!</span>
</div>
<div class="rc-next-steps"><h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3><div class="rc-next-grid">
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one-branding" class="rc-next-card"><div class="rc-next-card-tag">Recommended next</div><div class="rc-next-card-icon"><i class="fa-solid fa-palette"></i></div><h4>Launchpad phase one: Branding emails &amp; invoices</h4><p>Apply your brand to the emails and invoices Recurly sends on your behalf.</p><div class="rc-next-card-arrow">Read next &rarr;</div></a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-next-card"><div class="rc-next-card-tag">Explore the pillar</div><div class="rc-next-card-icon"><i class="fa-solid fa-rocket"></i></div><h4>All Launch paths</h4><p>See every learning path in the Launch pillar.</p><div class="rc-next-card-arrow">View Launch &rarr;</div></a>
<a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-next-card"><div class="rc-next-card-tag">Live session</div><div class="rc-next-card-icon"><i class="fa-solid fa-microphone"></i></div><h4>Global Office Hours</h4><p>Bring your questions to our CSMs live. Sessions run weekly.</p><div class="rc-next-card-arrow">Register &rarr;</div></a>
</div></div>
<div class="rc-resources"><h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3><div class="rc-resource-links">
<a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Email templates</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates#parameters" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-tags"></i> Recurly Docs: Email parameters</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/email-templates#using-boolean-sections-for-custom-messages" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-code-branch"></i> Recurly Docs: Boolean sections</a>
<a href="https://docs.google.com/document/d/1gE2fRLSSm1gjcR5d5NuUFYHTxZYl4AWHgRPghOC52uQ/edit?usp=sharing" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Email HTML template guide</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-branding" class="rc-resource-link"><i class="fa-solid fa-palette"></i> Dunning 101: Email branding</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-dunning-101-email-configuration" class="rc-resource-link"><i class="fa-solid fa-gear"></i> Dunning 101: Email configuration</a>
<a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
</div></div>
<div class="rc-footer-nav"><div class="rc-footer-links">
<div class="rc-footer-section"><span class="rc-footer-label">Easy HTML guide</span>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide" class="rc-footer-link">Path overview</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-basics" class="rc-footer-link">1. HTML basics</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-merge-tags" class="rc-footer-link">2. Merge tags</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-styling" class="rc-footer-link">3. Styling &amp; layout</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-testing" class="rc-footer-link">4. Testing &amp; previewing</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-snippets" class="rc-footer-link">5. Common snippets</a>
<a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-easy-html-guide-review" class="rc-footer-link">6. Review &amp; resources</a>
</div>
<div class="rc-footer-utility"><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link"><img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home</a><a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a></div>
</div></div>
</div>
</div>
`}</HTMLBlock>