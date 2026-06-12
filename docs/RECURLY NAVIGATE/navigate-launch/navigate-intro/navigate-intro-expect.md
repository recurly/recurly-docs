---
title: 'Introduction to Navigate: What to expect'
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
html { scroll-behavior: smooth; scroll-padding-top: 80px; }
.rc-guide { --yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2; color:#32312D !important; background:#ffffff; }
.rc-guide * { box-sizing: border-box; }
.rc-fa-announce{color:#0D0D0B;font-size:1rem;flex-shrink:0;} .rc-fa-dark{color:#FFD706 !important;font-size:1.3rem;display:block;margin-bottom:10px;} .rc-fa-light{color:#0D0D0B;font-size:1.3rem;display:block;margin-bottom:10px;} .rc-fa-section{color:#0D0D0B;font-size:1rem;}
.rc-top-nav{padding:20px 40px 16px;max-width:1200px;margin:0 auto;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-back-link{color:#807D73 !important;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;transition:color .2s;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-back-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-back-link:hover{color:#FF8200 !important;}
.rc-content-wrap{max-width:1200px;margin:0 auto;padding:0 40px;}
.rc-announce-bar{display:none;background:#FFD706;color:#0D0D0B;align-items:center;justify-content:space-between;padding:10px 20px;font-size:.88rem;font-weight:600;border-radius:10px;margin-bottom:16px;gap:12px;line-height:1.4;}
.rc-announce-bar.rc-active{display:flex;} .rc-announce-inner{display:flex;align-items:center;gap:10px;flex:1;flex-wrap:wrap;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-announce-link{color:#0D0D0B !important;font-weight:800;white-space:nowrap;padding:4px 12px;background:rgba(0,0,0,0.10);border-radius:6px;transition:background 0.2s;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-announce-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-announce-link:hover{background:rgba(0,0,0,0.20);color:#0D0D0B !important;}
.rc-hero{background:linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)),url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;background-color:#0D0D0B;background-size:cover;color:#fff;padding:48px 40px 44px;text-align:center;border-radius:16px;margin-bottom:0;}
.rc-brand-header{display:flex;justify-content:center;margin-bottom:0;} .rc-logo-image{height:28px;display:block;}
.rc-pillar-icon-row{display:flex;justify-content:center;gap:12px;margin:36px auto 24px;flex-wrap:wrap;}
.rc-pillar-icon-chip{display:inline-flex;align-items:center;gap:7px;padding:7px 14px;border-radius:20px;font-size:.72rem;font-weight:800;letter-spacing:.8px;text-transform:uppercase;}
.rc-pillar-icon-chip img{width:14px;height:14px;object-fit:contain;}
.rc-chip-launch{background:rgba(204,201,184,0.20);border:1px solid rgba(204,201,184,0.45);color:#CCC9B8;}
.rc-chip-acquire{background:rgba(255,215,6,0.20);border:1px solid rgba(255,215,6,0.45);color:#FFD706;}
.rc-chip-retain{background:rgba(255,157,136,0.20);border:1px solid rgba(255,157,136,0.45);color:#FF9D88;}
.rc-chip-scale{background:rgba(255,88,16,0.20);border:1px solid rgba(255,88,16,0.45);color:#FF5810;}
.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;color:#FFFDF2;margin:0 0 14px;}
.rc-hero-sub{font-size:1rem;opacity:.85;max-width:640px;margin:0 auto;color:#CCC9B8;line-height:1.6;}
details.rc-sticky-nav-wrap{position:relative;z-index:1;background-color:#F1EFE3;box-shadow:0 4px 12px rgba(0,0,0,0.08);margin:24px 0 48px;border-radius:12px;border:1px solid rgba(0,0,0,0.08);overflow:hidden;}
details.rc-sticky-nav-wrap > summary{list-style:none;display:flex;align-items:center;padding:15px 24px;cursor:pointer;user-select:none;}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker{display:none;} details.rc-sticky-nav-wrap > summary::marker{display:none;}
.rc-nav-toggle-label{display:inline-flex;align-items:center;gap:8px;font-weight:800;font-size:.88rem;letter-spacing:0.6px;text-transform:uppercase;color:#0D0D0B;}
.rc-nav-chevron{font-size:.72rem;color:#0D0D0B;opacity:0.55;line-height:1;transition:transform 0.25s ease;}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron{transform:rotate(180deg);}
.rc-nav-drawer{display:grid;grid-template-rows:0fr;transition:grid-template-rows 0.3s ease;}
details.rc-sticky-nav-wrap[open] .rc-nav-drawer{grid-template-rows:1fr;}
.rc-nav-drawer-inner{overflow:hidden;border-top:1px solid rgba(0,0,0,0.10);}
.rc-nav-links{display:flex;flex-wrap:wrap;gap:6px 4px;padding:12px 20px 18px;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-sticky-link{color:#0D0D0B !important;font-weight:700;font-size:.83rem;letter-spacing:0.4px;text-transform:uppercase;padding:7px 14px;border-radius:7px;transition:all .18s;white-space:nowrap;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;}
.rc-sticky-link img{width:15px;height:15px;object-fit:contain;}
.rc-step-badge{display:inline-flex;align-items:center;justify-content:center;width:20px;height:20px;border-radius:50%;background:#0D0D0B;color:#FFD706;font-size:.65rem;font-weight:800;flex-shrink:0;line-height:1;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-sticky-link-active{font-weight:800;color:#0D0D0B !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-sticky-link-active:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-sticky-link-active:hover{background:rgba(0,0,0,0.10);color:#0D0D0B !important;}
.rc-lp-section{margin-bottom:48px;}
.rc-lp-section h2{font-size:1.5rem;font-weight:800;margin:0 0 20px;color:#0D0D0B;display:flex;align-items:center;gap:12px;}
.rc-lp-section h2::after{content:"";flex-grow:1;height:1px;background:#CCC9B8;}
.rc-lp-section > p{font-size:.95rem;line-height:1.65;color:#32312D;margin:0 0 16px;}
/* CARD */
.rc-card{background:#FFFDF2;border:1px solid #CCC9B8;border-radius:12px;padding:24px 28px;margin-bottom:24px;}
.rc-card h3{font-size:1rem;font-weight:800;color:#0D0D0B;margin:0 0 10px;display:flex;align-items:center;gap:8px;}
.rc-card p{font-size:.93rem;color:#32312D;line-height:1.65;margin:0 0 12px;}
.rc-card p:last-child{margin-bottom:0;}
/* SCORECARD IMAGE */
.rc-scorecard-img{overflow:hidden;margin-bottom:24px;}
.rc-scorecard-img img{width:100%;height:auto;display:block;}
/* 2-COL TILES */
.rc-wi-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px;}
.rc-wi{background:#FFFDF2;border-radius:12px;padding:20px;border:1px solid #CCC9B8;}
.rc-wi-header{background:#0D0D0B;margin:-20px -20px 14px -20px;padding:12px 16px;border-radius:10px 10px 0 0;display:flex;align-items:center;gap:10px;}
.rc-wi-header h4{margin:0;font-size:.9rem;font-weight:700;color:#FFD706;}
.rc-wi p{font-size:.85rem;color:#807D73;line-height:1.6;margin:0 0 10px;}
.rc-wi p:last-child{margin-bottom:0;}
.rm-Markdown.markdown-body .rc-guide .rc-wi a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide .rc-wi a{color:#FF8200 !important;font-size:.82rem;font-weight:700;border-bottom:0 !important;}
/* WARNING CALLOUT */
.rc-callout-warning-box{background:#FFF8E6;border:1px solid #FF8200;border-left:4px solid #FF8200;border-radius:10px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px;}
.rc-callout-warning-box p{font-size:.87rem;color:#32312D;line-height:1.55;margin:0;}
/* TIP CALLOUT */
.rc-callout{border-radius:10px;padding:16px 20px;margin:20px 0;display:flex;gap:14px;align-items:flex-start;}
.rc-callout-icon{font-size:1.1rem;line-height:1.4;flex-shrink:0;}
.rc-callout-body{flex:1;}
.rc-callout-body > strong{font-size:.88rem;font-weight:800;display:block;margin-bottom:4px;}
.rc-callout-body p{font-size:.9rem;line-height:1.55;margin:0;color:#32312D;}
.rc-callout-tip{background:#F1EFE3;border-left:4px solid #0D0D0B;}
.rc-callout-tip .rc-callout-body > strong{color:#0D0D0B;}
.rm-Markdown.markdown-body .rc-guide .rc-callout-body a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide .rc-callout-body a{color:#FF8200 !important;font-weight:600;border-bottom:0 !important;}
/* CHECKLIST */
.rc-checklist{background:#FFFDF2;border-radius:14px;border:1px solid #CCC9B8;overflow:hidden;margin-bottom:32px;}
.rc-cl-header{padding:16px 22px;display:flex;align-items:center;gap:10px;background:#0D0D0B;}
.rc-cl-header h3{font-size:.82rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:#FFD706;margin:0;}
.rc-cli{padding:13px 22px;border-bottom:1px solid #F1EFE3;display:flex;align-items:flex-start;gap:14px;}
.rc-cli:last-child{border-bottom:none;}
.rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid #CCC9B8;flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:#807D73;}
.rc-clab{font-size:.88rem;color:#32312D;line-height:1.4;}
.rc-clab span{display:block;font-size:.78rem;color:#807D73;margin-top:2px;}
/* COMPLETE BLOCK */
.rc-complete{background:#0D0D0B;border-radius:14px;padding:40px;text-align:center;margin-bottom:32px;}
.rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:#FFD706;}
.rc-complete p{color:#CCC9B8;font-size:.95rem;margin:0;line-height:1.6;}
/* CONTINUE YOUR JOURNEY */
.rc-next-steps{margin:0 0 48px;}
.rc-next-steps h3{font-size:.78rem;font-weight:700;text-transform:uppercase;letter-spacing:.9px;color:#807D73;margin:0 0 16px;display:flex;align-items:center;gap:8px;}
.rc-next-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;}
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-next-card{background:#FFFDF2;border:1px solid #CCC9B8 !important;border-bottom:1px solid #CCC9B8 !important;border-radius:12px;padding:20px;display:flex;flex-direction:column;gap:8px;transition:all .2s ease;}
.rm-Markdown.markdown-body .rc-guide a.rc-next-card:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-next-card:hover{border:1px solid #CCC9B8 !important;border-bottom:1px solid #CCC9B8 !important;box-shadow:0 4px 16px rgba(204,201,184,.35);transform:translateY(-2px);}
.rc-next-card-tag{font-size:.68rem;font-weight:700;text-transform:uppercase;letter-spacing:.8px;color:#CCC9B8 !important;margin-bottom:2px;}
.rc-next-card-icon{font-size:1.3rem;line-height:1;color:#0D0D0B !important;}
.rc-next-card h4{font-size:.95rem;font-weight:800;color:#0D0D0B !important;margin:0;line-height:1.3;}
.rc-next-card p{font-size:.85rem;color:#807D73 !important;line-height:1.5;margin:0;flex-grow:1;}
.rc-next-card-arrow{font-size:.82rem;font-weight:700;color:#FF8200 !important;margin-top:4px;}
/* PATH NAV BUTTONS */
.rc-lp-nav{display:flex;align-items:center;justify-content:space-between;gap:16px;margin:40px 0 16px;}
.rc-lp-nav-indicator{font-size:.8rem;font-weight:600;color:#CCC9B8;letter-spacing:.5px;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-btn-prev{background:transparent;color:#0D0D0B !important;padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid #CCC9B8 !important;border-bottom:2px solid #CCC9B8 !important;transition:all .2s;}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-prev:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-btn-prev:hover{border:2px solid #0D0D0B !important;border-bottom:2px solid #0D0D0B !important;}
.rc-btn-complete{background:#F1EFE3;color:#0D0D0B !important;padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:8px;border:2px solid #FFD706;cursor:default;user-select:none;}
/* RESOURCES */
.rc-resources{background:#F1EFE3;border-left:4px solid #CCC9B8;border-radius:10px;padding:20px 24px;margin:32px 0 0;}
.rc-resources h3{font-size:.75rem;font-weight:700;text-transform:uppercase;letter-spacing:.9px;color:#807D73;margin:0 0 12px;display:flex;align-items:center;gap:8px;}
.rc-resource-links{display:flex;flex-wrap:wrap;gap:4px 20px;}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-resource-link{color:#807D73 !important;text-decoration:underline !important;text-underline-offset:3px;text-decoration-color:#CCC9B8 !important;font-weight:500;font-size:.88rem;transition:all .18s;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-resource-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-resource-link:hover{color:#0D0D0B !important;text-decoration-color:#CCC9B8 !important;}
/* FOOTER */
.rc-footer-nav{border-top:1px solid #CCC9B8;padding-top:40px;margin-top:48px;padding-bottom:48px;}
.rc-footer-links{display:flex;flex-direction:column;gap:16px;}
.rc-footer-section{display:flex;flex-wrap:wrap;align-items:center;gap:8px 24px;}
.rc-footer-label{font-weight:800;font-size:.75rem;text-transform:uppercase;letter-spacing:.8px;color:#32312D;background:#F1EFE3;padding:4px 10px;border-radius:6px;margin-right:4px;}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),.rc-guide a.rc-footer-link{color:#807D73 !important;font-weight:600;font-size:.88rem;transition:color .2s ease;display:inline-flex;align-items:center;gap:6px;border-bottom:0 !important;}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,.rc-guide a.rc-footer-link:hover{color:#FF8200 !important;}
.rc-footer-link img{width:14px;height:14px;object-fit:contain;opacity:0.5;transition:opacity .2s ease;}
.rc-footer-link:hover img{opacity:1;}
.rc-footer-utility{display:flex;flex-wrap:wrap;gap:24px;margin-top:16px;padding-top:24px;border-top:1px solid #F1EFE3;}
@media(max-width:768px){
  .rc-content-wrap{padding:0 20px;} .rc-top-nav{padding:16px 20px;} .rc-hero{padding:36px 20px 36px;} .rc-hero h1{font-size:1.8rem;}
  .rc-lp-nav{flex-wrap:wrap;justify-content:center;} .rc-lp-nav-indicator{width:100%;text-align:center;}
  .rc-wi-grid{grid-template-columns:1fr;} .rc-next-grid{grid-template-columns:1fr;} .rc-pillar-icon-row{gap:8px;}
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-back-link">← Back to Launch</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>Upcoming:</strong> Join our CSMs for a live Q&amp;A session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
    </div>

    <div class="rc-hero">
      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>
      <div class="rc-pillar-icon-row">
        <span class="rc-pillar-icon-chip rc-chip-launch"><img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt=""> Launch</span>
        <span class="rc-pillar-icon-chip rc-chip-acquire"><img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt=""> Acquire</span>
        <span class="rc-pillar-icon-chip rc-chip-retain"><img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt=""> Retain</span>
        <span class="rc-pillar-icon-chip rc-chip-scale"><img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt=""> Scale</span>
      </div>
      <h1>What to expect from Navigate</h1>
      <p class="rc-hero-sub">Navigate is more than a hub; we’re a team, and we’re your partner in success. Explore the curated support, best practices, updates, and resources you can expect to receive as part of this program.</p>
    </div>

    <details class="rc-sticky-nav-wrap" open>
      <summary><span class="rc-nav-toggle-label">Navigation Menu <i class="fa-solid fa-chevron-up rc-nav-chevron"></i></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro" class="rc-sticky-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome" class="rc-sticky-link"><span class="rc-step-badge">1</span> Official welcome</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel" class="rc-sticky-link"><span class="rc-step-badge">2</span> The Recurly flywheel</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home" class="rc-sticky-link"><span class="rc-step-badge">3</span> Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> What to expect
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2><i class="fa-solid fa-circle-check rc-fa-section"></i> Your "always-on" Customer Success program</h2><p>
<p>Need to write a quick sentence to hammer down on the purpose of Navigate and introduce the items below.</p><br>

      <!-- MONTHLY SCORECARD -->
      <h2><i class="fa-solid fa-chart-bar rc-fa-section"></i> Monthly Scorecard</h2>
      <p>Every <strong>second Tuesday of the month</strong>, you'll receive your Navigate Monthly Scorecard: a snapshot of your most important subscription health metrics, benchmarked against your prior year and industry averages.</p>

      <div class="rc-scorecard-img">
        <img src="https://files.readme.io/bf0f3ed737a5783fbd0ac153303d2aec540da707789b1225059bdb25a9f3a146-Merchant_Scorecard_Example.png" alt="Navigate Monthly Scorecard example showing subscription health metrics" />
      </div>

      <!-- HOW NAVIGATE SHOWS UP -->
      <h2><i class="fa-solid fa-bullseye rc-fa-section"></i> How Navigate shows up for you</h2>
      <div class="rc-wi-grid">
        <div class="rc-wi">
          <div class="rc-wi-header"><i class="fa-solid fa-envelope" style="color:#FFD706;font-size:1.1rem;"></i><h4>Monthly Newsletter</h4></div>
          <p>Your curated monthly briefing: new Recurly features, upcoming events, optimization tips, industry insights, and highlights from the Navigate community.</p>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-header"><i class="fa-solid fa-calendar-days" style="color:#FFD706;font-size:1.1rem;"></i><h4>Open Office Hours</h4></div>
          <p>Drop in and ask a Customer Success Manager anything. No appointment or agenda required.</p>
          <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">View Office Hours schedule →</a>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-header"><i class="fa-solid fa-tower-broadcast" style="color:#FFD706;font-size:1.1rem;"></i><h4>Webinars &amp; events</h4></div>
          <p>Regular live sessions on new features, optimization strategies, and subscription trends, with Q&amp;A and on-demand recordings for everything.</p>
          <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">Browse upcoming webinars →</a>
        </div>
        <div class="rc-wi">
          <div class="rc-wi-header"><i class="fa-solid fa-headset" style="color:#FFD706;font-size:1.1rem;"></i><h4>1:1 Expert Sessions</h4></div>
          <p>Available upon request. Dedicated 1:1 time with a CSM to review your setup, strategize on a goal, or work through a specific challenge, focused entirely on your priorities.</p>
          <a href="mailto:recurlynavigate@recurly.com">Request an Expert Session →</a>
        </div>
      </div>

      <!-- EMAIL WHITELIST -->
      <div class="rc-callout-warning-box">
        <i class="fa-solid fa-triangle-exclamation" style="color:#FF8200;font-size:1.1rem;flex-shrink:0;margin-top:2px;"></i>
        <p><strong>Action required: Whitelist our email.</strong> All Navigate communications come from <strong>recurlynavigate@recurly.com</strong>. Add this address to your email whitelist to ensure scorecards, newsletters, and event invitations reach your inbox. If you're not seeing our emails, check your spam folder and mark us as a trusted sender.</p>
      </div>

      <!-- PROACTIVE MONITORING -->
      <div class="rc-card">
        <h3><i class="fa-solid fa-eye rc-fa-section"></i> Proactive monitoring &amp; outreach</h3>
        <p>Your Navigate team monitors your subscription health metrics. If we spot an opportunity to improve your results — a gap in your dunning setup, an underutilized feature, or a benchmark that suggests room for improvement — we'll reach out and offer to help.</p>
      </div>

      <!-- OPT OUT -->
      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon"><i class="fa-solid fa-door-open"></i></div>
        <div class="rc-callout-body">
          <strong>A note on opting out</strong>
          <p>You can opt out of Navigate at any time by contacting <a href="mailto:recurlynavigate@recurly.com">recurlynavigate@recurly.com</a>. Opting out means stepping away from your monthly scorecard, newsletter, proactive monitoring, live events, Office Hours, and Expert Sessions.</p>
        </div>
      </div>

      <!-- COMPLETION BLOCK — no buttons -->
      <div class="rc-complete">
        <i class="fa-solid fa-rocket rc-fa-dark"></i>
        <h2>You're all set.</h2>
        <p>Head to Navigate Home and explore the learning path that matches your biggest priority right now. If you're not sure where to start, drop in at the next Office Hours session and ask.</p>
      </div>

      <!-- CONTINUE YOUR JOURNEY -->
      <div class="rc-next-steps">
        <h3><i class="fa-solid fa-compass rc-fa-section"></i> Continue your journey</h3>
        <div class="rc-next-grid">

          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-launchpad-phase-one" class="rc-next-card">
            <div class="rc-next-card-tag">Recommended next</div>
            <div class="rc-next-card-icon"><i class="fa-solid fa-rocket"></i></div>
            <h4>Launchpad Phase 1: Optimize</h4>
            <p>Put your Recurly foundation to work. Covers subscription setup, billing model selection, checkout configuration, and free trial best practices.</p>
            <div class="rc-next-card-arrow">Start path →</div>
          </a>

          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-two" class="rc-next-card">
            <div class="rc-next-card-tag">Go deeper</div>
            <div class="rc-next-card-icon"><i class="fa-solid fa-chart-line"></i></div>
            <h4>Launchpad Phase 2: Mastering metrics</h4>
            <p>Learn how to read and act on your subscription data — the metrics that matter, how to benchmark your performance, and how to spot what needs attention.</p>
            <div class="rc-next-card-arrow">Start path →</div>
          </a>

          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-resource-library" class="rc-next-card">
            <div class="rc-next-card-tag">Resources</div>
            <div class="rc-next-card-icon"><i class="fa-solid fa-book-open"></i></div>
            <h4>The Navigate Resource Library</h4>
            <p>All Recurly documentation, support links, help articles, and a monthly-updated events calendar in one place.</p>
            <div class="rc-next-card-arrow">Explore →</div>
          </a>

        </div>
      </div>

      <div class="rc-lp-nav">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home" class="rc-btn-prev">← Navigate Home</a>
        <span class="rc-lp-nav-indicator">5 of 5</span>
        <span class="rc-btn-complete"><i class="fa-solid fa-circle-check"></i> Course complete!</span>
      </div>
    </div>

    <div class="rc-resources">
      <h3><i class="fa-solid fa-book-open rc-fa-section"></i> Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-house"></i> Navigate Home in Recurly Docs</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link"><i class="fa-solid fa-globe"></i> Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link"><i class="fa-solid fa-headset"></i> Contact Recurly Support</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro" class="rc-resource-link"><i class="fa-solid fa-rotate-left"></i> Restart this course</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Introduction to Navigate</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro" class="rc-footer-link">Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-welcome" class="rc-footer-link">1. Official welcome</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-flywheel" class="rc-footer-link">2. The Recurly flywheel</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-home" class="rc-footer-link">3. Navigate Home</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-intro-expect" class="rc-footer-link">4. What to expect</a>
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
