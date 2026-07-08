---
title: Try it
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
/* FA6 font restore — (0,0,2,0) beats wildcard (0,0,1,0) */
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:    #FFD706;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #D1CFC4;
  --brightgray:#F2F1EA;
  --offwhite:  #FCFBF7;
  font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #0D0D0B !important;
  background: #ffffff;
  max-width: 960px;
  margin: 0 auto;
  padding: 0 0 60px;
}
.rc-guide * { box-sizing: border-box; }

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

/* ── INLINE BODY LINKS (Omits :not(.rp-anchor) so it catches our bypassed links) ── */
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-inline-link {
  color: #008CFF !important;
  font-weight: 600;
  border-bottom: 0 !important;
  text-decoration: none !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-inline-link:hover {
  color: #0067BE !important;
  text-decoration: underline !important;
  text-decoration-color: #008CFF !important;
  text-underline-offset: 2px !important;
}

.rc-top-nav{padding:20px 40px 16px;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-back-link{color:#807D73 !important;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-back-link:hover{color:#008CFF !important;text-decoration:none !important;}
.rc-content-wrap{padding:0 40px;}
@media(max-width:768px){.rc-content-wrap{padding:0 20px;}.rc-top-nav{padding:16px 20px;}}

.rc-announce-bar{display:none;background:#FFD706;color:#0D0D0B;align-items:center;justify-content:space-between;padding:10px 20px;font-size:.88rem;font-weight:600;border-radius:10px;margin-bottom:16px;gap:12px;line-height:1.4;}
.rc-announce-bar.rc-active{display:flex;}
.rc-announce-inner{display:flex;align-items:center;gap:10px;flex:1;flex-wrap:wrap;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-announce-link{color:#0D0D0B !important;font-weight:800;padding:4px 12px;background:rgba(0,0,0,0.10);border-radius:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-announce-link:hover{background:rgba(0,0,0,0.20);color:#0D0D0B !important;text-decoration:none !important;}

.rc-hero{background:linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)),url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;background-color:var(--offblack);background-size:cover;color:#fff;padding:48px 40px 44px;text-align:center;border-radius:16px;margin-bottom:0;}
.rc-lp-pillar-tag{display:inline-flex;align-items:center;gap:7px;background:rgba(255,81,38,0.20);border:1px solid rgba(255,81,38,0.45);color:#FF5126;font-size:.75rem;font-weight:800;letter-spacing:1px;text-transform:uppercase;padding:6px 14px;border-radius:20px;margin-bottom:20px;}
.rc-lp-pillar-tag img{width:13px;height:13px;object-fit:contain;}
.rc-lp-hero-title{text-align:center;margin:0 0 14px;}
.rc-lp-hero-title h1{font-size:2.4rem;font-weight:800;line-height:1.15;color:#FFFDF2;margin:0;}
.rc-hero>p{font-size:1rem;opacity:.85;max-width:640px;margin:0 auto;color:var(--lightgray);line-height:1.6;}
@media(max-width:768px){.rc-hero{padding:36px 20px;}.rc-lp-hero-title h1{font-size:1.8rem;}}

details.rc-sticky-nav-wrap{position:relative;z-index:1;background-color:#FF5126;box-shadow:0 4px 12px rgba(0,0,0,0.08);margin:24px 0 48px 0;border-radius:12px;border:1px solid rgba(0,0,0,0.08);overflow:hidden;}
details.rc-sticky-nav-wrap>summary{list-style:none;display:flex;align-items:center;padding:15px 24px;cursor:pointer;user-select:none;}
details.rc-sticky-nav-wrap>summary::-webkit-details-marker{display:none;}
details.rc-sticky-nav-wrap>summary::marker{display:none;}
.rc-nav-toggle-label{display:inline-flex;align-items:center;gap:8px;font-weight:800;font-size:.88rem;letter-spacing:0.6px;text-transform:uppercase;color:var(--offblack);}
.rc-nav-chevron{font-size:.72rem;color:var(--offblack);opacity:0.55;transition:transform 0.25s ease;}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron{transform:rotate(180deg);}
.rc-nav-drawer{display:grid;grid-template-rows:0fr;transition:grid-template-rows 0.3s ease;}
details.rc-sticky-nav-wrap[open] .rc-nav-drawer{grid-template-rows:1fr;}
.rc-nav-drawer-inner{overflow:hidden;border-top:1px solid rgba(0,0,0,0.10);}
.rc-nav-links{display:flex;flex-wrap:wrap;gap:6px 4px;padding:12px 20px 18px;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-sticky-link{color:#0D0D0B !important;font-weight:700;font-size:.83rem;letter-spacing:0.4px;text-transform:uppercase;padding:7px 14px;border-radius:7px;transition:all .18s;white-space:nowrap;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;text-decoration:none !important;}
.rc-sticky-link img{width:15px;height:15px;object-fit:contain;}
.rc-step-badge{display:inline-flex;align-items:center;justify-content:center;width:20px;height:20px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:.65rem;font-weight:800;flex-shrink:0;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-sticky-link-active{font-weight:800;color:#0D0D0B !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link-active:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;text-decoration:none !important;}

.rc-lp-section{margin-bottom:48px;}
.rc-lp-section h2{font-size:1.5rem;font-weight:800;margin:0 0 20px;color:var(--offblack);display:flex;align-items:center;gap:12px;}
.rc-lp-section h2::after{content:"";flex-grow:1;height:1px;background:var(--lightgray);}
.rc-lp-section p{font-size:.95rem;line-height:1.65;color:var(--darkgray);margin:0 0 16px;}

.rc-fa-section{color:var(--offblack);font-size:1rem;flex-shrink:0;}
.rc-fa-light{display:block;margin-bottom:10px;font-size:1.4rem;color:var(--offblack);}
.rc-fa-dark{display:block;margin-bottom:10px;font-size:1.4rem;color:var(--yellow);}

.rc-video-card{border:1px solid var(--lightgray);border-radius:14px;overflow:hidden;margin:0 0 40px;}
.rc-video-header{background:var(--offblack);padding:16px 22px;display:flex;align-items:center;gap:10px;}
.rc-video-header h4{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.7px;color:var(--yellow);margin:0;}
.rc-video-header span{font-size:.78rem;color:var(--lightgray);margin-left:auto;}
.rc-video-embed{position:relative;overflow:hidden;aspect-ratio:16/9;background:var(--offblack);}
.rc-video-embed iframe{position:absolute;width:100%;height:100%;top:0;left:0;border:none;}
.rc-video-caption{padding:12px 22px;font-size:.83rem;color:var(--gray);background:var(--brightgray);border-top:1px solid var(--lightgray);line-height:1.5;}

.rc-card-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin:0 0 32px;}
.rc-feature-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;padding:20px 22px;}
.rc-card-title{font-size:1rem;font-weight:800;color:var(--offblack);margin:0 0 10px;display:flex;align-items:center;gap:8px;}
.rc-feature-card p{font-size:.9rem;color:var(--darkgray);line-height:1.6;margin:0;}
@media(max-width:768px){.rc-card-grid{grid-template-columns:1fr;}}

.rc-steps{display:flex;flex-direction:column;gap:12px;margin:0 0 32px;}
.rc-step{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:18px 20px;display:flex;gap:16px;align-items:flex-start;}
.rc-step-num{width:34px;height:34px;border-radius:9px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:.85rem;display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.rc-step-content h4{font-size:.95rem;font-weight:700;margin:0 0 5px;color:var(--offblack);}
.rc-step-content p{font-size:.88rem;color:var(--gray);line-height:1.6;margin:0;}

.rc-callout{border-radius:10px;padding:16px 20px;margin:20px 0;display:flex;gap:14px;align-items:flex-start;}
.rc-callout+.rc-callout{margin-top:12px;}
.rc-callout-icon{font-size:1.1rem;line-height:1.4;flex-shrink:0;}
.rc-callout-body{flex:1;}
.rc-callout-body>strong{font-size:.88rem;font-weight:800;display:block;margin-bottom:4px;}
.rc-callout-body p{font-size:.9rem;line-height:1.55;margin:0;color:var(--darkgray);}
.rc-callout-tip{background:var(--brightgray);border-left:4px solid var(--offblack);}
.rc-callout-tip .rc-callout-body>strong{color:var(--offblack);}
.rc-callout-warning{background:rgba(255,215,6,0.12);border-left:4px solid var(--yellow);}
.rc-callout-warning .rc-callout-body>strong{color:var(--darkgray);}
.rc-callout-caution{background:#FFFECB;border-left:4px solid #FFD706;}
.rc-callout-caution .rc-callout-body>strong{color:var(--darkgray);}

.rm-Markdown.markdown-body .rc-callout-caution .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rm-Markdown.markdown-body .rc-guide .rc-gw-table a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-callout-caution .rc-callout-body a,
.rc-guide .rc-gw-table a { color: #008CFF !important; border-bottom: 0 !important; }

.rm-Markdown.markdown-body .rc-callout-caution .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rm-Markdown.markdown-body .rc-guide .rc-gw-table a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-callout-caution .rc-callout-body a:hover,
.rc-guide .rc-gw-table a:hover { text-decoration: underline !important; text-decoration-color: #008CFF !important; text-underline-offset: 2px !important; color: #0067BE !important; }

.rc-checklist{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;overflow:hidden;margin:20px 0 32px;}
.rc-checklist-header{padding:14px 22px;background:var(--offblack);display:flex;align-items:center;gap:10px;}
.rc-checklist-header h4{font-size:.82rem;font-weight:700;text-transform:uppercase;letter-spacing:.8px;color:var(--yellow);margin:0;}
.rc-checklist-item{padding:14px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px;cursor:pointer;transition:background .15s;}
.rc-checklist-item:last-of-type{border-bottom:none;}
.rc-checklist-item:hover{background:var(--brightgray);}
.rc-checklist-item input[type="checkbox"]{position:absolute;opacity:0;width:0;height:0;pointer-events:none;}
.rc-checkbox-box{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;transition:all .18s;margin-top:1px;}
.rc-checklist-item input[type="checkbox"]:checked+.rc-checkbox-box{background:var(--offblack);border-color:var(--offblack);}
.rc-checklist-item input[type="checkbox"]:checked+.rc-checkbox-box::after{content:'✓';color:var(--yellow);font-size:.75rem;font-weight:800;line-height:1;}
.rc-checklist-item input[type="checkbox"]:checked~.rc-checklist-text strong{text-decoration:line-through;color:var(--gray);}
.rc-checklist-item:has(input[type="checkbox"]:checked){background:rgba(204,201,184,0.10);}
.rc-checklist-text{flex:1;}
.rc-checklist-text strong{font-size:.9rem;font-weight:700;color:var(--offblack);display:block;margin-bottom:2px;transition:color .18s;}
.rc-checklist-text span{font-size:.8rem;color:var(--gray);line-height:1.4;display:block;}

.rm-Markdown.markdown-body .rc-checklist-text a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rm-Markdown.markdown-body .rc-guide .rc-gw-table a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide .rc-checklist-text a,
.rc-guide .rc-gw-table a { color: #008CFF !important; border-bottom: 0 !important; }

.rm-Markdown.markdown-body .rc-checklist-text a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rm-Markdown.markdown-body .rc-guide .rc-gw-table a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide .rc-checklist-text a:hover,
.rc-guide .rc-gw-table a:hover { text-decoration: underline !important; text-decoration-color: #008CFF !important; text-underline-offset: 2px !important; color: #0067BE !important; }

.rc-checklist-footer{padding:10px 22px;background:var(--brightgray);border-top:1px solid var(--lightgray);font-size:.78rem;color:var(--gray);font-weight:600;}

.rc-pricing-card{border-radius:10px;padding:18px 22px;margin-bottom:12px;border:1px solid var(--lightgray);background:var(--offwhite);}
.rc-pricing-card.rc-pricing-free{border-left:4px solid #5DC32E;}
.rc-pricing-card.rc-pricing-paid{border-left:4px solid #FFD706;}
.rc-pricing-card h4{font-size:.95rem;font-weight:800;color:var(--offblack);margin:0 0 6px;}
.rc-pricing-card p{font-size:.88rem;color:var(--gray);line-height:1.55;margin:0;}

.rc-webinar-cta{background:#0D0D0B !important;border:2px solid #FF5126;border-radius:14px;padding:32px 36px;margin:0 0 40px;display:flex;align-items:center;gap:28px;}
.rc-webinar-cta-icon{font-size:2.2rem;flex-shrink:0;line-height:1;}
.rc-webinar-cta-body{flex:1;}
.rc-webinar-cta-body p{font-size:.95rem;color:#FFFDF2 !important;line-height:1.6;margin:0 0 18px;}
.rc-webinar-cta-body p em{font-style:normal;font-weight:700;color:#ffffff !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-webinar-btn{background:#FF5126 !important;color:#ffffff !important;text-decoration:none !important;padding:12px 24px;border-radius:10px;font-weight:800;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid #FF5126 !important;border-bottom:2px solid #FF5126 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp
`}</HTMLBlock>

<br />
