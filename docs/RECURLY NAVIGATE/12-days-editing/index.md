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
  --yellow:      #FFD706;  /* Recurly Gold / Acquire */
  --launch-red:  #FF5126;  /* Recurly Poppy / Holiday Red */
  --green:       #5DC32E;  /* Recurly Success / Evergreen */
  --blue:        #008CFF;  /* Recurly Scale / Ice Blue */
  --blue-tint1:  #D5EAFF;
  --blue-tint2:  #96C8FF;
  --offblack:    #0D0D0B;
  --darkgray:    #32312D;
  --gray:        #807D75;
  --lightgray:   #D1CFC4;
  --brightgray:  #F2F1EA;
  --offwhite:    #FCFBF7;

  --warning-fg:  #FFD706;
  --warning-bg:  #FFFECB;
  --error-fg:    #FF5126;
  --error-bg:    #FFEEE9;
  --success-fg:  #5DC32E;
  --success-bg:  #EFFAEA;

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

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none; background: #FFD706; color: #0D0D0B;
  align-items: center; justify-content: space-between;
  padding: 12px 22px; font-size: .88rem; font-weight: 600;
  border-radius: 12px; margin-bottom: 18px; gap: 12px; line-height: 1.4;
  border: 1px solid rgba(13,13,11,0.12);
  border-left: 6px solid #FF5126;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-announce-link {
  color: #0D0D0B !important; font-weight: 800; white-space: nowrap;
  padding: 5px 14px; background: rgba(0,0,0,0.10); border-radius: 6px;
  transition: background 0.2s; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-announce-link:hover { background: rgba(0,0,0,0.20); color: #0D0D0B !important; }

/* ── HERO WITH DRAPED CHRISTMAS LIGHTS ── */
.rc-hero {
  position: relative;
  background-color: #0D0D0B;
  color: #fff;
  padding: 54px 40px 50px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
  border: 1px solid rgba(255, 215, 6, 0.3);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.45);
  overflow: hidden;
}

/* Christmas lights draped across the top */
.rc-hero-lights-top {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 38px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='38' viewBox='0 0 240 38'%3E%3Cpath d='M0,4 Q60,24 120,4 Q180,24 240,4' fill='none' stroke='%231b2e20' stroke-width='2' stroke-linecap='round'/%3E%3Cg%3E%3Ccircle cx='35' cy='22' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='33' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='35' cy='21' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='33.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='60' cy='27' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='58' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='60' cy='26' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='58.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='85' cy='22' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='83' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='85' cy='21' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='83.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='155' cy='22' r='9' fill='%23008CFF' fill-opacity='0.40'/%3E%3Crect x='153' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='155' cy='21' rx='4.5' ry='6.5' fill='%23008CFF'/%3E%3Ccircle cx='153.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='180' cy='27' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='178' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='180' cy='26' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='178.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='205' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='203' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='205' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='203.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat-x;
  background-position: top center;
  z-index: 2;
  pointer-events: none;
}

/* Christmas lights draped across the bottom */
.rc-hero-lights-bottom {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 38px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='240' height='38' viewBox='0 0 240 38'%3E%3Cpath d='M0,4 Q60,24 120,4 Q180,24 240,4' fill='none' stroke='%231b2e20' stroke-width='2' stroke-linecap='round'/%3E%3Cg%3E%3Ccircle cx='35' cy='22' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='33' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='35' cy='21' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='33.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='60' cy='27' r='9' fill='%23008CFF' fill-opacity='0.40'/%3E%3Crect x='58' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='60' cy='26' rx='4.5' ry='6.5' fill='%23008CFF'/%3E%3Ccircle cx='58.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='85' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='83' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='85' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='83.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='155' cy='22' r='9' fill='%23FFD706' fill-opacity='0.40'/%3E%3Crect x='153' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='155' cy='21' rx='4.5' ry='6.5' fill='%23FFD706'/%3E%3Ccircle cx='153.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='180' cy='27' r='9' fill='%235DC32E' fill-opacity='0.40'/%3E%3Crect x='178' y='17' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='180' cy='26' rx='4.5' ry='6.5' fill='%235DC32E'/%3E%3Ccircle cx='178.5' cy='24' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3Cg%3E%3Ccircle cx='205' cy='22' r='9' fill='%23FF5126' fill-opacity='0.40'/%3E%3Crect x='203' y='12' width='4' height='3.5' rx='1' fill='%23121d15'/%3E%3Cellipse cx='205' cy='21' rx='4.5' ry='6.5' fill='%23FF5126'/%3E%3Ccircle cx='203.5' cy='19' r='1.2' fill='%23ffffff' fill-opacity='0.9'/%3E%3C/g%3E%3C/svg%3E");
  background-repeat: repeat-x;
  background-position: top center;
  transform: rotate(180deg);
  z-index: 2;
  pointer-events: none;
}

.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; position: relative; z-index: 3; }
.rc-logo-image { height: 28px; display: block; }

/* ── GREEN PILL (WINTER CHALLENGE) ── */
.rc-festive-hero-tag {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(93, 197, 46, 0.16); border: 1.5px solid #5DC32E;
  color: #5DC32E; font-size: .80rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 18px; border-radius: 20px; margin: 26px auto 16px;
  position: relative; z-index: 3;
}
.rc-home-title-block { position: relative; z-index: 3; }
.rc-home-title-block h1 {
  font-size: 2.5rem; font-weight: 800; line-height: 1.15; color: #FCFBF7; margin: 0 0 16px;
}
.rc-hero p {
  font-size: 1.02rem; opacity: .92; max-width: 740px; margin: 0 auto 12px;
  color: #D1CFC4; line-height: 1.6;
}

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
.rc-guide a.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: #0D0D0B !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }

/* ── SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── FESTIVE CALLOUT ── */
.rc-callout { border-radius: 12px; padding: 18px 24px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout-icon { font-size: 1.3rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .92rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-festive {
  background: #FCFBF7; border: 1px solid var(--lightgray); border-left: 5px solid #5DC32E;
}
.rc-callout-festive .rc-callout-body > strong { color: var(--offblack); }

/* ── 12-DAY ADVENT GRID ── */
.rc-advent-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
  margin: 24px 0 32px;
}

/* Base card */
.rc-advent-card {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 14px;
  padding: 22px;
  display: flex;
  flex-direction: column;
  gap: 10px;
  position: relative;
  transition: all .2s ease;
}

/* Unlocked cards */
.rm-Markdown.markdown-body .rc-guide a.rc-advent-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-advent-card {
  text-decoration: none !important;
  border-bottom: 1px solid var(--lightgray) !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-advent-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-advent-card:hover {
  border-color: #FF5126 !important;
  border-bottom: 1px solid #FF5126 !important;
  box-shadow: 0 6px 22px rgba(255, 81, 38, 0.18);
  transform: translateY(-2px);
  text-decoration: none !important;
}

/* Locked cards (Frost theme) */
.rc-advent-card.rc-advent-locked {
  background: #F7F8F9;
  border: 1px dashed #C8CCD0;
  user-select: none;
  cursor: default;
}
.rc-advent-card.rc-advent-locked h4 { color: #807D75 !important; }
.rc-advent-card.rc-advent-locked p { color: #A09E96 !important; }

/* Card Internals */
.rc-advent-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

/* Brand Christmas Badges */
.rc-badge-red {
  display: inline-flex; align-items: center; gap: 6px;
  background: #FF5126 !important; color: #ffffff !important;
  padding: 4px 11px; border-radius: 16px; font-size: .72rem; font-weight: 800;
  letter-spacing: .5px; text-transform: uppercase;
}
.rc-badge-green {
  display: inline-flex; align-items: center; gap: 6px;
  background: #5DC32E !important; color: #ffffff !important;
  padding: 4px 11px; border-radius: 16px; font-size: .72rem; font-weight: 800;
  letter-spacing: .5px; text-transform: uppercase;
}
.rc-badge-gold {
  display: inline-flex; align-items: center; gap: 6px;
  background: #FFD706 !important; color: #0D0D0B !important;
  padding: 4px 11px; border-radius: 16px; font-size: .72rem; font-weight: 800;
  letter-spacing: .5px; text-transform: uppercase;
}
.rc-badge-blue {
  display: inline-flex; align-items: center; gap: 6px;
  background: #008CFF !important; color: #ffffff !important;
  padding: 4px 11px; border-radius: 16px; font-size: .72rem; font-weight: 800;
  letter-spacing: .5px; text-transform: uppercase;
}
.rc-badge-locked {
  display: inline-flex; align-items: center; gap: 6px;
  background: #E5E4DE !important; color: #807D75 !important;
  padding: 4px 11px; border-radius: 16px; font-size: .72rem; font-weight: 800;
  letter-spacing: .5px; text-transform: uppercase;
}

.rc-advent-points {
  font-size: .74rem; font-weight: 800; color: #FF5126 !important;
  display: inline-flex; align-items: center; gap: 4px;
}
.rc-advent-points-locked {
  font-size: .74rem; font-weight: 700; color: #A09E96 !important;
  display: inline-flex; align-items: center; gap: 4px;
}
.rc-advent-date {
  font-size: .72rem; font-weight: 700; color: #807D75;
  text-transform: uppercase; letter-spacing: .6px;
}
.rc-advent-card h4 {
  font-size: 1.02rem; font-weight: 800; color: #0D0D0B !important;
  margin: 0; line-height: 1.35;
}
.rc-advent-card p {
  font-size: .88rem; color: #807D75 !important; line-height: 1.55;
  margin: 0; flex-grow: 1;
}
.rc-advent-action {
  font-size: .84rem; font-weight: 700; color: #008CFF !important; margin-top: 4px;
}
.rc-advent-action-locked {
  font-size: .82rem; font-weight: 700; color: #807D75 !important;
  margin-top: 4px; display: inline-flex; align-items: center; gap: 6px;
}

/* ── PRIZE TIERS ── */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin: 0 0 32px; }
.rc-feature-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 24px; display: flex; flex-direction: column; gap: 10px; transition: all .2s ease;
}
.rc-feature-card:hover {
  border-color: #5DC32E; box-shadow: 0 4px 18px rgba(93, 197, 46, 0.2); transform: translateY(-2px);
}
.rc-feature-icon-red { font-size: 1.5rem; line-height: 1; color: #FF5126; }
.rc-feature-icon-green { font-size: 1.5rem; line-height: 1; color: #5DC32E; }
.rc-feature-icon-gold { font-size: 1.5rem; line-height: 1; color: #FFD706; }
.rc-feature-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0; }
.rc-feature-card p { font-size: .88rem; color: var(--gray); line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-tag-red {
  display: inline-block; margin-top: 4px; padding: 4px 12px; border-radius: 20px;
  font-size: .7rem; font-weight: 800; letter-spacing: .5px; background: #FF5126;
  color: #ffffff; width: fit-content;
}
.rc-feature-tag-green {
  display: inline-block; margin-top: 4px; padding: 4px 12px; border-radius: 20px;
  font-size: .7rem; font-weight: 800; letter-spacing: .5px; background: #5DC32E;
  color: #ffffff; width: fit-content;
}
.rc-feature-tag-gold {
  display: inline-block; margin-top: 4px; padding: 4px 12px; border-radius: 20px;
  font-size: .7rem; font-weight: 800; letter-spacing: .5px; background: #FFD706;
  color: #0D0D0B; width: fit-content;
}

/* ── WEBINAR CTA BLOCK ── */
.rc-webinar-cta {
  background: #0D140E !important;
  border: 2px solid #5DC32E;
  border-radius: 14px;
  padding: 34px 38px;
  margin: 0 0 40px;
  display: flex;
  align-items: center;
  gap: 28px;
  box-shadow: 0 6px 24px rgba(13, 20, 14, 0.4);
}
.rc-webinar-cta-icon { font-size: 2.2rem; flex-shrink: 0; line-height: 1; color: #FFD706; }
.rc-webinar-cta-body { flex: 1; }
.rc-webinar-cta-body p {
  font-size: .95rem; color: #FCFBF7 !important; line-height: 1.6; margin: 0 0 18px;
}
.rc-webinar-cta-body p em { font-style: normal; font-weight: 700; color: #5DC32E !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-webinar-btn {
  background: #FF5126 !important;
  color: #ffffff !important;
  text-decoration: none !important;
  padding: 12px 24px;
  border-radius: 10px;
  font-weight: 800;
  font-size: .9rem;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: all .2s;
  border: 2px solid #FF5126 !important;
  border-bottom: 2px solid #FF5126 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-webinar-btn:hover {
  background: transparent !important;
  color: #FF5126 !important;
  border: 2px solid #FF5126 !important;
  border-bottom: 2px solid #FF5126 !important;
}

/* ── RESOURCES BLOCK ── */
.rc-resources {
  background: var(--brightgray);
  border-left: 4px solid #5DC32E;
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
  text-decoration-color: #FF5126 !important;
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
  color: #ffffff; background: #FF5126; padding: 4px 10px; border-radius: 6px;
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

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 46px 20px 42px; }
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
        <i class="fa-regular fa-snowflake rc-fa-announce" style="color: #FF5126;"></i>
        <strong>Winter optimization challenge:</strong> Complete 12 weekday micro-tasks, rack up points, and compete for the Recurly Holiday Gift Basket.
        <a href="#calendar" class="rc-announce-link">View scavenger hunt →</a>
      </div>
    </div>

    <!-- Festive Hero (Solid Rich Offblack with Draped Christmas Lights) -->
    <div class="rc-hero">
      <!-- Top strand of Christmas lights -->
      <div class="rc-hero-lights-top"></div>

      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>
      <div>
        <span class="rc-festive-hero-tag">
          <i class="fa-solid fa-tree"></i> Winter challenge
        </span>
      </div>
      <div class="rc-home-title-block">
        <h1>12 days of optimization</h1>
        <p>A 12-weekday scavenger hunt across your site settings, Compass prompts, and newest product release tools. Complete daily 3-minute missions, earn points, and compete to win our Recurly Holiday Gift Basket and a guest spotlight on our late Q1 2027 webinar.</p>
      </div>

      <!-- Bottom strand of Christmas lights -->
      <div class="rc-hero-lights-bottom"></div>
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
            <a href="#calendar" class="rc-sticky-link">Scavenger hunt calendar</a>
            <a href="#rules" class="rc-sticky-link">Scoring &amp; gift basket</a>
            <a href="#spotlight" class="rc-sticky-link">Customer spotlight webinar</a>
            <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Office Hours
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Overview Callout -->
    <div class="rc-callout rc-callout-festive" id="rules">
      <div class="rc-callout-icon"><i class="fa-solid fa-gift" style="color: #FF5126;"></i></div>
      <div class="rc-callout-body">
        <strong>How the holiday scavenger hunt works</strong>
        <p>Each weekday leading up to the holidays unlocks a new 3-minute mission. Follow the guided activity, submit your completed task through the short form at the bottom of that specific activity page, and earn 1 point. The merchant with the most points takes home the holiday gift basket!</p>
      </div>
    </div>

    <!-- Section 1: The 12 Days Advent Grid -->
    <div class="rc-lp-section" id="calendar">
      <h2><i class="fa-solid fa-calendar-days rc-fa-section"></i> Scavenger hunt calendar</h2>
      <p>Tasks unlock each weekday at midnight. Complete open tasks anytime before the campaign wraps up on Friday, December 18.</p>

      <div class="rc-advent-grid">

        <!-- Day 1 (Unlocked - Poppy Red) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-1" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-red"><i class="fa-solid fa-tree"></i> Day 1</span>
            <span class="rc-advent-points">+1 point</span>
          </div>
          <div class="rc-advent-date">Thursday, Dec 3</div>
          <h4>The Compass prompt expedition</h4>
          <p>Watch a 2-minute video on Compass AI, test an insightful churn prompt, and submit what you discover.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 2 (Unlocked - Evergreen) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-2" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-green"><i class="fa-regular fa-snowflake"></i> Day 2</span>
            <span class="rc-advent-points">+2 points</span>
          </div>
          <div class="rc-advent-date">Friday, Dec 4</div>
          <h4>The dunning email makeover</h4>
          <p>Audit your renewal recovery notices and draft a friendlier, high-converting notification template.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 3 (Unlocked - Gold) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-3" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-gold"><i class="fa-solid fa-gift"></i> Day 3</span>
            <span class="rc-advent-points">+3 points</span>
          </div>
          <div class="rc-advent-date">Monday, Dec 7</div>
          <h4>The silent churn investigation</h4>
          <p>Run your Signup Declines against your industry benchmark and spot your primary drop-off reason.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>


        <!-- Day 4 (Unlocked - Ice Blue) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-4" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-blue"><i class="fa-solid fa-wand-magic-sparkles"></i> Day 4</span>
            <span class="rc-advent-points">+5 points</span>
          </div>
          <div class="rc-advent-date">Tuesday, Dec 8</div>
          <h4>The gateway failover test run</h4>
          <p>Inspect your gateway routing settings and configure automatic failover rules to prevent card outages.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 5 (Unlocked - Poppy Red) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-5" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-red"><i class="fa-solid fa-tree"></i> Day 5</span>
            <span class="rc-advent-points">+5 points</span>
          </div>
          <div class="rc-advent-date">Wednesday, Dec 9</div>
          <h4>The wallet treasure hunt</h4>
          <p>Explore the Subscriber Wallet feature and log how backup payment methods boost subscription longevity.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 6 (Unlocked - Evergreen) -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/12-days-day-6" class="rc-advent-card">
          <div class="rc-advent-header">
            <span class="rc-badge-green"><i class="fa-regular fa-snowflake"></i> Day 6</span>
            <span class="rc-advent-points">+6 points</span>
          </div>
          <div class="rc-advent-date">Thursday, Dec 10</div>
          <h4>The Account Updater mystery</h4>
          <p>Dive into Payments Hub to calculate how many expiring cards were automatically rescued last month.</p>
          <div class="rc-advent-action">Start activity →</div>
        </a>

        <!-- Day 7 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 7</span>
            <span class="rc-advent-points-locked">+7 points</span>
          </div>
          <div class="rc-advent-date">Friday, Dec 11</div>
          <h4>The pause vs. cancel face-off</h4>
          <p>Examine how offering temporary pauses preserves loyal subscribers without forcing churn.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 11 at 12:00 AM</div>
        </div>

        <!-- Day 8 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 8</span>
            <span class="rc-advent-points-locked">+8 points</span>
          </div>
          <div class="rc-advent-date">Monday, Dec 14</div>
          <h4>Compass retention sleuth</h4>
          <p>Prompt Compass to surface subscribers showing low engagement patterns before billing renews.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 14 at 12:00 AM</div>
        </div>

        <!-- Day 9 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 9</span>
            <span class="rc-advent-points-locked">+9 points</span>
          </div>
          <div class="rc-advent-date">Tuesday, Dec 15</div>
          <h4>Dynamic statement detective</h4>
          <p>Fine-tune charge descriptors to clearly identify billing and prevent accidental chargebacks.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 15 at 12:00 AM</div>
        </div>

        <!-- Day 10 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 10</span>
            <span class="rc-advent-points-locked">+10 points</span>
          </div>
          <div class="rc-advent-date">Wednesday, Dec 16</div>
          <h4>The plan add-on architect</h4>
          <p>Configure a mock recurring add-on to test how modular pricing expands customer lifetime value.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 16 at 12:00 AM</div>
        </div>

        <!-- Day 11 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 11</span>
            <span class="rc-advent-points-locked">+11 points</span>
          </div>
          <div class="rc-advent-date">Thursday, Dec 17</div>
          <h4>The coupon stacking sandbox</h4>
          <p>Solve a tricky discount logic puzzle to ensure promo codes never unintentionally double-stack.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 17 at 12:00 AM</div>
        </div>

        <!-- Day 12 (LOCKED) -->
        <div class="rc-advent-card rc-advent-locked">
          <div class="rc-advent-header">
            <span class="rc-badge-locked"><i class="fa-solid fa-lock"></i> Day 12</span>
            <span class="rc-advent-points-locked">+12 points</span>
          </div>
          <div class="rc-advent-date">Friday, Dec 18</div>
          <h4>The grand optimization showcase</h4>
          <p>Submit your favorite optimization win or prompt insight to lock in your final leaderboard tally.</p>
          <div class="rc-advent-action-locked"><i class="fa-solid fa-lock"></i> Unlocks Dec 18 at 12:00 AM</div>
        </div>

      </div>
    </div>

    <!-- Section 2: Prizes and Scoring (Festive Card Tiers) -->
    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-trophy rc-fa-section"></i> Competition rewards &amp; scoring</h2>
      <p>Log your completed missions directly on each activity page. Every verified submission earns 1 point toward the leaderboard.</p>

      <div class="rc-card-grid">

        <div class="rc-feature-card">
          <div class="rc-feature-icon-red"><i class="fa-solid fa-basket-shopping"></i></div>
          <h4>The Recurly holiday gift basket</h4>
          <p>Awarded to the participant who logs the highest verified point total. Packed with curated artisan treats, luxury winter apparel, and Recurly team gifts.</p>
          <span class="rc-feature-tag-red">Grand champion</span>
        </div>

        <div class="rc-feature-card">
          <div class="rc-feature-icon-green"><i class="fa-solid fa-microphone"></i></div>
          <h4>Webinar guest speaker invite</h4>
          <p>Our Grand Champion will be invited to appear as a guest speaker on our late Q1 webinar to share their optimization tactics and results with the community.</p>
          <span class="rc-feature-tag-green">Customer spotlight</span>
        </div>

        <div class="rc-feature-card">
          <div class="rc-feature-icon-gold"><i class="fa-solid fa-ticket"></i></div>
          <h4>All-participant invitation</h4>
          <p>Every merchant who participates in at least one day will receive early access and guaranteed seating for our end-of-Q1 strategy and release webinar.</p>
          <span class="rc-feature-tag-gold">1+ activity</span>
        </div>

      </div>
    </div>

    <!-- Section 3: End of Q1 2027 Webinar CTA -->
    <div class="rc-webinar-cta" id="spotlight">
      <div class="rc-webinar-cta-icon"><i class="fa-solid fa-circle-play"></i></div>
      <div class="rc-webinar-cta-body">
        <p>Join us at the end of Q1 2027 for a community-wide <em>Subscriber Optimization &amp; Release Spotlight</em>. We will break down our newest features, examine benchmark shifts, and feature a live fireside chat with our 12 Days Champion to discuss real-world metric gains.</p>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-webinar-btn">Join the notification list →</a>
      </div>
    </div>

    <!-- Section 4: Standard Resources Block -->
    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open" style="color: #5DC32E; font-size: 1rem;"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly product documentation</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Customer Success Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-envelope"></i> Contact support</a>
      </div>
    </div>

    <!-- Standard Learning Path / Hub Footer Nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">12 days of optimization</span>
          <a href="#calendar" class="rc-footer-link">Scavenger hunt</a>
          <a href="#rules" class="rc-footer-link">Scoring &amp; prizes</a>
          <a href="#spotlight" class="rc-footer-link">Q1 2027 webinar</a>
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
