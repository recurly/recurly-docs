---
title: Editing Page 2
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
  --yellow:      #FFD706;
  --launch-red:  #FF5126;
  --green:       #5DC32E;
  --blue:        #008CFF;
  --offblack:    #0D0D0B;
  --darkgray:    #32312D;
  --gray:        #807D75;
  --lightgray:   #D1CFC4;
  --brightgray:  #F2F1EA;
  --offwhite:    #FCFBF7;

  font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #32312D !important;
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* ── FONT AWESOME HELPERS ── */
.rc-fa-announce { color: #0D0D0B; font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #FF5126; font-size: 1.15rem; }

/* ── TOP NAV & CONTAINER ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-back-link {
  color: #807D75 !important; font-weight: 700; font-size: .9rem;
  display: inline-flex; align-items: center; gap: 6px; transition: color .2s; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-back-link:hover { color: #FF5126 !important; }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── FESTIVE HERO WITH LIGHTS ── */
.rc-hero {
  position: relative;
  background-color: #0D0D0B;
  color: #fff;
  padding: 52px 40px 48px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
  border: 1px solid rgba(255, 215, 6, 0.3);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.45);
  overflow: hidden;
}

.rc-hero-lights-top {
  position: absolute; top: 0; left: 0; right: 0; height: 38px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='38' viewBox='0 0 240 38'%3E%3Cpath d='M0,4 Q60,24 120,4 Q180,24 240,4' fill='none' stroke='%231b2e20' stroke-width='2' stroke-linecap='round'/%3E%3Cg%3E%3Ccircle cx='35' cy='22' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='33' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='35' cy='21' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='33.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='60' cy='27' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='58' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='60' cy='26' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='58.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='85' cy='22' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='83' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='85' cy='21' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='83.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='155' cy='22' r='9' fill='%23008CFF' fill-opacity='0.40'/%3E%3Crect x='153' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='155' cy='21' rx='4.5' ry='6.5' fill='%23008CFF'/%3E%3Ccircle cx='153.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='180' cy='27' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='178' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='180' cy='26' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='178.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='205' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='203' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='205' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='203.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat-x; background-position: top center; z-index: 2; pointer-events: none;
}

.rc-hero-lights-bottom {
  position: absolute; bottom: 0; left: 0; right: 0; height: 38px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='38' viewBox='0 0 240 38'%3E%3Cpath d='M0,4 Q60,24 120,4 Q180,24 240,4' fill='none' stroke='%231b2e20' stroke-width='2' stroke-linecap='round'/%3E%3Cg%3E%3Ccircle cx='35' cy='22' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='33' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='35' cy='21' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='33.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='60' cy='27' r='9' fill='%23008CFF' fill-opacity='0.40'/%3E%3Crect x='58' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='60' cy='26' rx='4.5' ry='6.5' fill='%23008CFF'/%3E%3Ccircle cx='58.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='85' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='83' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='85' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='83.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='155' cy='22' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='153' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='155' cy='21' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='153.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='180' cy='27' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='178' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='180' cy='26' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='178.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='205' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='203' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='205' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='203.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat-x; background-position: top center; transform: rotate(180deg); z-index: 2; pointer-events: none;
}

.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; position: relative; z-index: 3; }
.rc-logo-image { height: 28px; display: block; }

.rc-day-pill {
  display: inline-flex; align-items: center; gap: 8px;
  background: #FF5126; color: #ffffff;
  font-size: .78rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 18px; border-radius: 20px; margin: 24px auto 16px; position: relative; z-index: 3;
}
.rc-home-title-block { position: relative; z-index: 3; }
.rc-home-title-block h1 { font-size: 2.3rem; font-weight: 800; line-height: 1.15; color: #FCFBF7; margin: 0 0 14px; }
.rc-hero p { font-size: 1rem; opacity: .92; max-width: 720px; margin: 0 auto; color: #D1CFC4; line-height: 1.6; }

/* ── EXPANDED NAV MENU ── */
details.rc-sticky-nav-wrap {
  position: relative; z-index: 1;
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
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }

/* Active nav item */
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-sticky-link-active { font-weight: 800; color: #0D0D0B !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }

/* ── POINTS BANNER / STRIP ── */
.rc-points-banner {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-left: 5px solid #FF5126;
  border-radius: 12px;
  padding: 18px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 36px;
}
.rc-points-left { display: flex; align-items: center; gap: 14px; }
.rc-points-badge {
  background: #FF5126; color: #ffffff;
  font-size: 1.15rem; font-weight: 900;
  padding: 8px 16px; border-radius: 10px;
  display: inline-flex; align-items: center; gap: 6px;
  white-space: nowrap;
}
.rc-points-text strong { display: block; font-size: .95rem; color: var(--offblack); margin-bottom: 2px; }
.rc-points-text p { font-size: .86rem; color: var(--gray); margin: 0; line-height: 1.45; }
.rc-points-indicator {
  font-size: .78rem; font-weight: 800; text-transform: uppercase;
  color: var(--gray); letter-spacing: .6px; white-space: nowrap;
}

/* ── SECTIONS ── */
.rc-lp-section { margin-bottom: 44px; }
.rc-lp-section h2 {
  font-size: 1.45rem; font-weight: 800; margin: 0 0 18px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

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

/* ── FEATURED VIDEO CARD (Component 12a) ── */
.rc-video-card { border: 1px solid var(--lightgray); border-radius: 14px; overflow: hidden; margin: 0 0 36px; }
.rc-video-header { background: var(--offblack); padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h4 { font-size: .88rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: var(--yellow); margin: 0; }
.rc-video-header span { font-size: .78rem; color: var(--lightgray); margin-left: auto; }
.rc-video-embed { background: var(--offblack); }
.rc-video-embed iframe { display: block; width: 100%; aspect-ratio: 16/9; border: none; }
.rc-video-caption { padding: 12px 22px; font-size: .83rem; color: var(--gray); background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5; }

/* ── PROMPT EXPEDITION CARDS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin: 20px 0 28px; }
.rc-prompt-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 22px; display: flex; flex-direction: column; gap: 10px; transition: all .2s ease;
}
.rc-prompt-card:hover {
  border-color: #5DC32E; box-shadow: 0 4px 16px rgba(93, 197, 46, 0.18); transform: translateY(-2px);
}
.rc-prompt-badge {
  display: inline-block; padding: 3px 9px; border-radius: 5px;
  font-size: .7rem; font-weight: 800; text-transform: uppercase; letter-spacing: .5px;
  background: #0D0D0B; color: #FFD706; width: fit-content;
}
.rc-prompt-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-prompt-box {
  background: var(--brightgray); border-left: 3px solid var(--blue);
  padding: 10px 12px; border-radius: 6px; font-size: .85rem; color: var(--darkgray);
  line-height: 1.45; font-style: italic; flex-grow: 1;
}

/* ── CALLOUT (SUMMARY) ── */
.rc-callout { border-radius: 12px; padding: 18px 24px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.3rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .92rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-festive {
  background: #FCFBF7; border: 1px solid var(--lightgray); border-left: 5px solid #5DC32E;
}
.rc-callout-festive .rc-callout-body > strong { color: var(--offblack); }

/* ── WRIKE FORM SUBMISSION CARD ── */
.rc-form-card {
  border: 1px solid var(--lightgray); border-radius: 14px;
  overflow: hidden; margin: 24px 0 40px; background: #ffffff;
}
.rc-form-header {
  background: var(--offblack); padding: 16px 22px;
  display: flex; align-items: center; gap: 10px;
}
.rc-form-header h4 {
  font-size: .88rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .7px; color: var(--yellow); margin: 0;
}
.rc-form-header span { font-size: .78rem; color: #5DC32E; margin-left: auto; font-weight: 700; }
.rc-form-frame { width: 100%; background: #ffffff; min-height: 600px; }
.rc-form-frame iframe { display: block; width: 100%; height: 600px; border: none; }
.rc-form-caption {
  padding: 12px 22px; font-size: .83rem; color: var(--gray);
  background: var(--brightgray); border-top: 1px solid var(--lightgray); line-height: 1.5;
}

/* ── PATH NAVIGATION BUTTONS ── */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; flex-wrap: wrap; }
.rc-lp-nav-indicator { font-size: .85rem; font-weight: 700; color: var(--gray); letter-spacing: .5px; white-space: nowrap !important; }
.rc-btn-start {
  background: var(--brightgray); color: var(--gray); padding: 13px 24px;
  border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray);
  cursor: default; display: inline-flex; align-items: center; white-space: nowrap !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-path {
  background: #FF5126; color: #ffffff !important; text-decoration: none !important;
  padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem;
  display: inline-flex; align-items: center; gap: 8px; transition: all .2s;
  border: 2px solid #FF5126 !important; border-bottom: 2px solid #FF5126 !important;
  white-space: nowrap !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-path:hover {
  background: transparent !important; color: #FF5126 !important;
  border: 2px solid #FF5126 !important; border-bottom: 2px solid #FF5126 !important;
}

/* ── RESOURCES BLOCK ── */
.rc-resources {
  background: var(--brightgray); border-left: 4px solid #5DC32E;
  border-radius: 10px; padding: 20px 24px; margin: 32px 0 0;
}
.rc-resources h3 {
  font-size: .75rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; display: flex; align-items: center; gap: 8px;
}
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-resource-link {
  color: #807D75 !important; text-decoration: underline !important;
  text-underline-offset: 3px; text-decoration-color: #D1CFC4 !important;
  font-weight: 500; font-size: .88rem; transition: all .18s;
  display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-resource-link:hover {
  color: #0D0D0B !important; text-decoration: underline !important;
  text-underline-offset: 3px; text-decoration-color: #FF5126 !important;
}

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label {
  font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px;
  color: #ffffff; background: #FF5126; padding: 4px 10px; border-radius: 6px; margin-right: 4px;
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

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 46px 20px 42px; }
  .rc-home-title-block h1 { font-size: 1.7rem; }
  .rc-points-banner { flex-direction: column; align-items: flex-start; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
}
</style>

<div class="rc-guide">

  <!-- Top back link -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-home" class="rc-back-link">← Back to 12 days calendar</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Festive Hero (Day 1) -->
    <div class="rc-hero">
      <div class="rc-hero-lights-top"></div>

      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>
      <div>
        <span class="rc-day-pill">
          <i class="fa-solid fa-tree"></i> Day 1 of 12 · Video mission
        </span>
      </div>
      <div class="rc-home-title-block">
        <h1>The Compass prompt expedition</h1>
        <p>Kick off the 12 Days of Optimization! Learn how Compass AI Knowledge Agent instantly surfaces answers from technical documentation, tests edge cases, and accelerates billing configuration.</p>
      </div>

      <div class="rc-hero-lights-bottom"></div>
    </div>

    <!-- Navigation Menu (Expanded) -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> 12 Days Home
            </a>
            <a href="[current-page-url]" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> 1. Compass video
            </a>
            <a href="#prompts" class="rc-sticky-link">2. Test a prompt</a>
            <a href="#submit" class="rc-sticky-link">3. Submit &amp; earn points</a>
            <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Office Hours
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Point Value & Escalation Callout -->
    <div class="rc-points-banner">
      <div class="rc-points-left">
        <div class="rc-points-badge">
          <i class="fa-solid fa-gift"></i> +25 pts
        </div>
        <div class="rc-points-text">
          <strong>Mission value: 25 points</strong>
          <p>Watch the video, test one prompt in Compass, and log your result below to claim your points.</p>
        </div>
      </div>
      <div class="rc-points-indicator">
        Tier 1: Kickoff challenge
      </div>
    </div>

    <!-- Section 1: Video Walkthrough (Component 12a) -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-circle-play rc-fa-section"></i> Compass Knowledge Agent walkthrough</h2>
      <p>Watch this quick 2-minute overview showing how the Compass Knowledge Agent searches, synthesizes, and explains Recurly's entire technical library directly within your workflow.</p>

      <div class="rc-video-card">
        <div class="rc-video-header">
          <h4>Compass AI skills: Documentation search · Knowledge Agent</h4>
          <span>~2 min</span>
        </div>
        <div class="rc-video-embed">
          <iframe src="https://share.synthesia.io/embeds/videos/1a464b2c-f916-480a-9332-490d201eddad" loading="lazy" title="Synthesia video player - Compass AI Skills: Documentation Search - Knowledge Agent" allowfullscreen allow="encrypted-media; fullscreen; microphone; screen-wake-lock;"></iframe>
        </div>
        <div class="rc-video-caption">
          Learn how to prompt Compass for complex pricing model comparisons, gateway prerequisites, and retry settings.
        </div>
      </div>
    </div>

    <!-- Section 2: Try a Prompt -->
    <div class="rc-lp-section" id="prompts">
      <h2><i class="fa-solid fa-wand-magic-sparkles rc-fa-section"></i> Test a Compass prompt</h2>
      <p>Now it is your turn to explore! Open <strong>Compass Assistant</strong> in your Recurly console and run one of the following prompts (or test one of your own real billing questions):</p>

      <div class="rc-card-grid">

        <div class="rc-prompt-card">
          <span class="rc-prompt-badge">Gateway rules</span>
          <h4>Prerequisite check</h4>
          <div class="rc-prompt-box">
            "What are the specific requirements for enabling automated Account Updater with our payment gateway?"
          </div>
        </div>

        <div class="rc-prompt-card">
          <span class="rc-prompt-badge">Pricing models</span>
          <h4>Model comparison</h4>
          <div class="rc-prompt-box">
            "Explain the functional difference between tiered pricing and volume pricing for customer add-ons."
          </div>
        </div>

        <div class="rc-prompt-card">
          <span class="rc-prompt-badge">Dunning logic</span>
          <h4>Cadence optimization</h4>
          <div class="rc-prompt-box">
            "Why does Recurly recommend a 27-day dunning window for standard monthly billing plans?"
          </div>
        </div>

      </div>
    </div>

    <!-- Section 3: Summary -->
    <div class="rc-callout rc-callout-festive">
      <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb" style="color: #5DC32E;"></i></div>
      <div class="rc-callout-body">
        <strong>Key takeaway</strong>
        <p>Compass does not just locate documentation links; it understands your account context to recommend optimal configurations and prevent common dunning mistakes. Keep Compass open as a tactical co-pilot as you complete the upcoming 12 Days challenges.</p>
      </div>
    </div>

    <!-- Section 4: Wrike Activity Completion Tracker Form -->
    <div class="rc-lp-section" id="submit">
      <h2><i class="fa-solid fa-clipboard-check rc-fa-section"></i> Log your mission &amp; claim 25 points</h2>
      <p>Submit your task completion directly through the secure form below. Make sure to use the same account email for all 12 submissions so your leaderboard score accumulates correctly!</p>

      <div class="rc-form-card">
        <div class="rc-form-header">
          <h4><i class="fa-solid fa-list-check" style="color: var(--yellow); margin-right: 8px;"></i> Day 1 mission submission</h4>
          <span>+25 points</span>
        </div>
        <div class="rc-form-frame">
          <iframe src="https://www.wrike.com/forms/ABSCXHL7RH4EAC5A/12-Days-of-Optimization:-Day-1" title="12 Days of Optimization: Day 1 Form" loading="lazy"></iframe>
        </div>
        <div class="rc-form-caption">
          Trouble viewing the form? You can also <a href="https://www.wrike.com/forms/ABSCXHL7RH4EAC5A/12-Days-of-Optimization:-Day-1" target="_blank" rel="noopener noreferrer" class="rc-inline-link rp-anchor">open the standalone submission form in a new tab →</a>
        </div>
      </div>
    </div>

    <!-- Path Navigation Buttons -->
    <div class="rc-lp-nav">
      <span class="rc-btn-start">← Start</span>
      <span class="rc-lp-nav-indicator">Day 1 of 12</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-2" class="rc-btn-path">Next: Day 2 →</a>
    </div>

    <!-- Standard Resources Block -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open" style="color: #5DC32E; font-size: 1rem;"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/overview-recurly-compass" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Compass documentation</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Customer Success Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-envelope"></i> Contact support</a>
      </div>
    </div>

    <!-- Footer Nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">12 days of optimization</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-home" class="rc-footer-link">Calendar</a>
          <a href="[current-page-url]" class="rc-footer-link">1. Compass video</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-2" class="rc-footer-link">2. Dunning makeover</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-3" class="rc-footer-link">3. Churn investigation</a>
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
