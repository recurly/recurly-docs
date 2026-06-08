---
title: 'Section 1: Final Production Testing'
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
.rc-guide a,.rc-guide a:link,.rc-guide a:visited,.rc-guide a:hover,.rc-guide a:active {
  text-decoration:none !important;text-decoration-line:none !important;text-decoration-color:transparent !important;text-underline-offset:unset !important;border-bottom:0 !important;
}
html{scroll-behavior:smooth;scroll-padding-top:80px;}
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;max-width:960px;margin:0 auto;padding:0 0 60px;color:#32312D !important;background:#ffffff;}
.rc-top-nav{padding:20px 40px 16px;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-back-link{color:#807D73 !important;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-back-link:hover{color:#FF8200 !important;}
.rc-content-wrap{padding:0 40px;}
@media(max-width:768px){.rc-content-wrap{padding:0 20px;}.rc-top-nav{padding:16px 20px;}}
.rc-announce-bar{display:none;background:#FFD706;color:#0D0D0B;align-items:center;justify-content:space-between;padding:10px 20px;font-size:.88rem;font-weight:600;border-radius:10px;margin-bottom:16px;gap:12px;line-height:1.4;}
.rc-announce-bar.rc-active{display:flex;}
.rc-announce-inner{display:flex;align-items:center;gap:10px;flex:1;flex-wrap:wrap;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-announce-link{color:#0D0D0B !important;font-weight:800;padding:4px 12px;background:rgba(0,0,0,0.10);border-radius:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-announce-link:hover{background:rgba(0,0,0,0.20);color:#0D0D0B !important;}
.rc-hero{background:linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)),url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;background-color:var(--offblack);background-size:cover;color:#fff;padding:48px 40px 44px;text-align:center;border-radius:16px;margin-bottom:0;}
.rc-lp-pillar-tag{display:inline-flex;align-items:center;gap:7px;background:rgba(204,201,184,0.20);border:1px solid rgba(204,201,184,0.45);color:#CCC9B8;font-size:.75rem;font-weight:800;letter-spacing:1px;text-transform:uppercase;padding:6px 14px;border-radius:20px;margin-bottom:20px;}
.rc-lp-pillar-tag img{width:13px;height:13px;object-fit:contain;}
.rc-lp-hero-title{text-align:center;margin:0 0 14px;}
.rc-lp-hero-title h1{font-size:2.4rem;font-weight:800;line-height:1.15;color:#FFFDF2;margin:0;}
.rc-hero>p{font-size:1rem;opacity:.85;max-width:640px;margin:0 auto;color:#CCC9B8;line-height:1.6;}
@media(max-width:768px){.rc-hero{padding:36px 20px;}.rc-lp-hero-title h1{font-size:1.8rem;}}
details.rc-sticky-nav-wrap{position:relative;z-index:1;background-color:var(--brightgray);box-shadow:0 4px 12px rgba(0,0,0,0.08);margin:24px 0 48px 0;border-radius:12px;border:1px solid rgba(0,0,0,0.08);overflow:hidden;}
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
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;}
.rc-sticky-link img{width:15px;height:15px;object-fit:contain;}
.rc-step-badge{display:inline-flex;align-items:center;justify-content:center;width:20px;height:20px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:.65rem;font-weight:800;flex-shrink:0;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-sticky-link-active{font-weight:800;color:#0D0D0B !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link-active:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;}
.rc-lp-section{margin-bottom:48px;}
.rc-lp-section h2{font-size:1.5rem;font-weight:800;margin:0 0 20px;color:var(--offblack);display:flex;align-items:center;gap:12px;}
.rc-lp-section h2::after{content:"";flex-grow:1;height:1px;background:var(--lightgray);}
.rc-lp-section p{font-size:.95rem;line-height:1.65;color:var(--darkgray);margin:0 0 16px;}
.rc-fa-section{color:var(--orange);font-size:1rem;flex-shrink:0;}
.rc-fa-light{display:block;margin-bottom:10px;font-size:1.4rem;color:var(--offblack);}
.rc-fa-dark{display:block;margin-bottom:10px;font-size:1.4rem;color:var(--yellow);}
.rc-video-card{border:1px solid var(--lightgray);border-radius:14px;overflow:hidden;margin:0 0 40px;}
.rc-video-header{background:var(--offblack);padding:16px 22px;display:flex;align-items:center;gap:10px;}
.rc-video-header h4{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.7px;color:var(--yellow);margin:0;}
.rc-video-header span{font-size:.78rem;color:var(--lightgray);margin-left:auto;}
.rc-video-embed{position:relative;overflow:hidden;aspect-ratio:16/9;background:var(--offblack);}
.rc-video-embed iframe{position:absolute;width:100%;height:100%;top:0;left:0;border:none;padding:10;}
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
.rc-callout-caution{background:rgba(255,130,0,0.08);border-left:4px solid var(--orange);}
.rc-callout-caution .rc-callout-body>strong{color:var(--darkgray);}
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
.rc-checklist-footer{padding:10px 22px;background:var(--brightgray);border-top:1px solid var(--lightgray);font-size:.78rem;color:var(--gray);font-weight:600;}
.rc-pricing-card{border-radius:10px;padding:18px 22px;margin-bottom:12px;border:1px solid var(--lightgray);background:var(--offwhite);}
.rc-pricing-card.rc-pricing-free{border-left:4px solid #6ab187;}
.rc-pricing-card.rc-pricing-paid{border-left:4px solid var(--orange);}
.rc-pricing-card h4{font-size:.95rem;font-weight:800;color:var(--offblack);margin:0 0 6px;}
.rc-pricing-card p{font-size:.88rem;color:var(--gray);line-height:1.55;margin:0;}
.rc-webinar-cta{background:#0D0D0B !important;border:2px solid #CCC9B8;border-radius:14px;padding:32px 36px;margin:0 0 40px;display:flex;align-items:center;gap:28px;}
.rc-webinar-cta-icon{font-size:2.2rem;flex-shrink:0;line-height:1;}
.rc-webinar-cta-body{flex:1;}
.rc-webinar-cta-body p{font-size:.95rem;color:#FFFDF2 !important;line-height:1.6;margin:0 0 18px;}
.rc-webinar-cta-body p em{font-style:normal;font-weight:700;color:#ffffff !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-webinar-btn{background:#CCC9B8 !important;color:#0D0D0B !important;text-decoration:none !important;padding:12px 24px;border-radius:10px;font-weight:800;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid #CCC9B8 !important;border-bottom:2px solid #CCC9B8 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-webinar-btn:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-webinar-btn:hover{background:transparent !important;color:#CCC9B8 !important;border:2px solid #CCC9B8 !important;border-bottom:2px solid #CCC9B8 !important;}
@media(max-width:768px){.rc-webinar-cta{flex-direction:column;gap:16px;padding:24px 22px;}}
.rc-lp-nav{display:flex;align-items:center;justify-content:space-between;gap:16px;margin:40px 0 16px;}
.rc-lp-nav-indicator{font-size:.8rem;font-weight:600;color:var(--lightgray);letter-spacing:.5px;}
.rc-btn-start{background:var(--brightgray);color:var(--gray);padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;border:2px solid var(--lightgray);cursor:default;}
.rc-btn-complete{background:var(--brightgray);color:var(--offblack) !important;padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid var(--yellow);cursor:default;user-select:none;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-btn-prev{background:transparent;color:#0D0D0B !important;text-decoration:none !important;padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid #CCC9B8 !important;border-bottom:2px solid #CCC9B8 !important;transition:all .2s;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-btn-prev:hover{border:2px solid #0D0D0B !important;border-bottom:2px solid #0D0D0B !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-btn-path{background:var(--yellow);color:var(--offblack) !important;text-decoration:none !important;padding:13px 28px;border-radius:10px;font-weight:800;font-size:.95rem;display:inline-flex;align-items:center;gap:8px;border:2px solid var(--yellow) !important;border-bottom:2px solid var(--yellow) !important;transition:all .2s;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-path:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-btn-path:hover{background:transparent !important;color:var(--offblack) !important;border:2px solid var(--yellow) !important;border-bottom:2px solid var(--yellow) !important;}
@media(max-width:768px){.rc-lp-nav{flex-wrap:wrap;justify-content:center;}.rc-lp-nav-indicator{width:100%;text-align:center;}}
.rc-resources{background:var(--brightgray);border-left:4px solid var(--lightgray);border-radius:10px;padding:20px 24px;margin:32px 0 0;}
.rc-resources h3{font-size:.75rem;font-weight:700;text-transform:uppercase;letter-spacing:.9px;color:var(--gray);margin:0 0 12px;display:flex;align-items:center;gap:8px;}
.rc-resource-links{display:flex;flex-wrap:wrap;gap:4px 20px;}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-resource-link{color:#807D73 !important;text-decoration:underline !important;text-underline-offset:3px;text-decoration-color:#CCC9B8 !important;font-weight:500;font-size:.88rem;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-resource-link:hover{color:#0D0D0B !important;text-decoration:underline !important;text-decoration-color:#CCC9B8 !important;}
.rc-resource-group{margin-bottom:16px;}
.rc-resource-group:last-child{margin-bottom:0;}
.rc-resource-group-label{font-size:.72rem;font-weight:800;text-transform:uppercase;letter-spacing:.7px;color:var(--lightgray);margin:0 0 6px;display:block;}
.rc-footer-nav{border-top:1px solid var(--lightgray);padding-top:40px;margin-top:48px;padding-bottom:48px;}
.rc-footer-links{display:flex;flex-direction:column;gap:16px;}
.rc-footer-section{display:flex;flex-wrap:wrap;align-items:center;gap:8px 24px;}
.rc-footer-label{font-weight:800;font-size:.75rem;text-transform:uppercase;letter-spacing:.8px;color:var(--darkgray);background:var(--brightgray);padding:4px 10px;border-radius:6px;margin-right:4px;}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-footer-link{color:#807D73 !important;text-decoration:none !important;font-weight:600;font-size:.88rem;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-footer-link:hover{color:#FF8200 !important;}
.rc-footer-link img{width:14px;height:14px;object-fit:contain;opacity:0.5;}
.rc-footer-utility{display:flex;flex-wrap:wrap;gap:24px;margin-top:16px;padding-top:24px;border-top:1px solid var(--brightgray);}
</style>
<div class="rc-guide">
  <div class="rc-top-nav"><a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">← Back to Launch</a></div>
  <div class="rc-content-wrap">
    <div class="rc-announce-bar"><div class="rc-announce-inner"><i class="fa-regular fa-calendar-days"></i><strong>Upcoming:</strong> Join our CSMs live. <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register →</a></div></div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag"><img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch"> Launch · Launchpad Phase 1</div>
      <div class="rc-lp-hero-title"><h1>Production testing</h1></div>
      <p>Walk through checkout as a real subscriber to catch payment or compliance issues before they affect live revenue.</p>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary><span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link"><img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-overview" class="rc-sticky-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-production-testing" class="rc-sticky-link rc-sticky-link-active"><img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Production testing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-dunning" class="rc-sticky-link"><span class="rc-step-badge">2</span> Dunning</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-account-updater" class="rc-sticky-link"><span class="rc-step-badge">3</span> Account Updater</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-branding" class="rc-sticky-link"><span class="rc-step-badge">4</span> Branding</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-gateway-failover" class="rc-sticky-link"><span class="rc-step-badge">5</span> Gateway Failover</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-review" class="rc-sticky-link"><span class="rc-step-badge">6</span> Review &amp; resources</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-overview" class="rc-sticky-link"><img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start</a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-flask rc-fa-section"></i> Why test in production?</h2>
      <p>Testing from your subscriber's perspective surfaces issues your admin view won't show you — expired test cards, missing 3DS flows, and checkout errors that silently block signups. Do this before your first real renewal cycle.</p>

      <div class="rc-video-card">
        <div class="rc-video-header"><h4>Trail guide: production testing</h4><span>~3 min</span></div>
        <div class="rc-video-embed"><iframe src="https://share.synthesia.io/embeds/videos/f3384551-b4b2-4ab3-83fa-c8fe6e88c62f" loading="lazy" title="Production Testing" allowfullscreen allow="encrypted-media; fullscreen;"></iframe></div>
        <div class="rc-video-caption">What to test, how to test it, and what to look for in your Recurly admin.</div>
      </div>

      <h2><i class="fa-solid fa-list-check rc-fa-section"></i> Run your production test</h2>
      <p>Use a live card — not a sandbox test card. Run the lowest-price plan available, then cancel and refund immediately after confirming success.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content"><h4>Complete a live transaction</h4><p>Use a real payment method to sign up for your cheapest active plan. Complete the full checkout flow as a new subscriber would.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content"><h4>Verify the payment in Recurly</h4><p>Log in to your Recurly admin and confirm the transaction shows as successful. Check the invoice and subscription status.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content"><h4>Check your confirmation email</h4><p>Verify the post-signup email arrives promptly, displays your plan name and pricing correctly, and links to your subscriber portal.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content"><h4>Refund the test transaction</h4><p>From Recurly, issue and confirm the refund. This keeps your books clean and your test subscriber off your active list.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content"><h4>Verify PSD2 / 3DS (EU merchants only)</h4><p>If you process payments from EU subscribers, trigger a transaction that should require 3D Secure authentication. Confirm the challenge flow appears, completes, and the payment succeeds.</p></div>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-lightbulb"></i></div>
        <div class="rc-callout-body"><strong>Run the test on mobile</strong><p>Many checkout issues are device-specific. Use a mobile device and a different browser than your admin setup — this is where subscribers are most likely to encounter friction.</p></div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon"><i class="fa-solid fa-triangle-exclamation"></i></div>
        <div class="rc-callout-body"><strong>EU merchants: verify 3DS before launch</strong><p>If you haven't confirmed your 3D Secure setup and you process EU payments, you may see declined transactions at renewal. Review the PSD2 compliance docs linked below before proceeding.</p></div>
      </div>

      <div class="rc-checklist">
        <div class="rc-checklist-header"><i class="fa-solid fa-list-check" style="color:var(--yellow);font-size:1rem;"></i><h4>Production testing checklist</h4></div>
        <label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Completed a live test transaction</strong><span>Use your cheapest plan — refund immediately after.</span></div></label>
        <label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Confirmed the transaction in Recurly</strong><span>Invoice and subscription status show as successful.</span></div></label>
        <label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Refunded the test transaction</strong><span>Confirmed the refund processed in Recurly.</span></div></label>
        <label class="rc-checklist-item"><input type="checkbox"><div class="rc-checkbox-box"></div><div class="rc-checklist-text"><strong>Verified PSD2 / 3DS authentication</strong><span>EU merchants only. See docs below.</span></div></label>
        <div class="rc-checklist-footer">Tap each item to mark it complete</div>
      </div>
    </div>

    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-overview" class="rc-btn-prev">← Overview</a>
      <span class="rc-lp-nav-indicator">1 of 6</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-dunning" class="rc-btn-path">2. Dunning →</a>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/revised-payment-services-directive-psd2" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: PSD2 compliance</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/test" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Test gateway</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/checkout#configuration-landing-page" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-regular fa-file-lines"></i> Recurly Docs: Checkout configuration</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Launchpad</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-overview" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-production-testing" class="rc-footer-link">1. Production testing</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-dunning" class="rc-footer-link">2. Dunning</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-account-updater" class="rc-footer-link">3. Account Updater</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-branding" class="rc-footer-link">4. Branding</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-gateway-failover" class="rc-footer-link">5. Gateway Failover</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-review" class="rc-footer-link">6. Review &amp; resources</a>
        </div>
        <div class="rc-footer-utility">
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link"><img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home</a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>
  </div>
</div>
`}</HTMLBlock>

<br />
