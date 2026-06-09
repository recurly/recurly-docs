---
title: 'Plans: Best practices & strategy'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
/<style>
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* Host-theme armor */
.rc-guide a, .rc-guide a:link, .rc-guide a:visited, .rc-guide a:hover, .rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* Layout */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link { color: var(--offblack) !important; font-weight: 800; text-decoration: none !important; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; }
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close { background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0; }
.rc-announce-close:hover { opacity: 1; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: #0D0D0B; background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: #FFFDF2; margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: #CCC9B8; line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* Nav — non-sticky, open, Micro-Path */
details.rc-sticky-nav-wrap { position: relative; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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
.rc-sticky-link { color: var(--offblack) !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Sections */
.rc-lp-section { margin-bottom: 52px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-body a { color: var(--orange) !important; font-weight: 600; }
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body strong { color: var(--darkgray); }

/* Numbered + Q steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-num-q { width: 36px; height: 36px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0; }
.rc-step-content p + p { margin-top: 8px; }
.rc-step-content strong { color: var(--darkgray); }

/* Checklist */
.rc-checklist { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 20px 0 32px; }
.rc-checklist-header { padding: 14px 22px; background: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-checklist-header h4 { font-size: .82rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin: 0; }
.rc-checklist-item { padding: 14px 22px; border-bottom: 1px solid var(--brightgray); display: flex; align-items: flex-start; gap: 14px; transition: background .15s; cursor: pointer; }
.rc-checklist-item:last-child { border-bottom: none; }
.rc-checklist-item:hover { background: var(--brightgray); }
.rc-checklist-item input[type="checkbox"] { position: absolute; opacity: 0; width: 0; height: 0; pointer-events: none; }
.rc-checkbox-box { width: 22px; height: 22px; border-radius: 6px; border: 2px solid var(--lightgray); flex-shrink: 0; background: #fff; display: flex; align-items: center; justify-content: center; transition: all .18s; margin-top: 1px; }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box { background: var(--offblack); border-color: var(--offblack); }
.rc-checklist-item input[type="checkbox"]:checked + .rc-checkbox-box::after { content: '✓'; color: var(--yellow); font-size: .75rem; font-weight: 800; line-height: 1; }
.rc-checklist-item input[type="checkbox"]:checked ~ .rc-checklist-text strong { text-decoration: line-through; color: var(--gray); }
.rc-checklist-item:has(input[type="checkbox"]:checked) { background: rgba(255,215,6,0.06); }
.rc-checklist-text { flex: 1; }
.rc-checklist-text strong { font-size: .9rem; font-weight: 700; color: var(--offblack); display: block; margin-bottom: 2px; transition: color .18s; }
.rc-checklist-text span { font-size: .8rem; color: var(--gray); line-height: 1.4; display: block; }
.rc-checklist-footer { padding: 10px 22px; background: var(--brightgray); border-top: 1px solid var(--lightgray); font-size: .78rem; color: var(--gray); font-weight: 600; }

/* Pitch card — dark, !important required */
.rc-pitch-card { background: #0D0D0B !important; border-radius: 14px; padding: 36px 40px; text-align: center; margin: 0 0 40px; border: 1px solid rgba(255,255,255,0.08); }
.rc-pitch-emoji { font-size: 2.4rem; margin-bottom: 12px; }
.rc-pitch-card h3 { font-size: 1.1rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; color: #FFD706 !important; margin: 0 0 16px; }
.rc-pitch-quote { font-size: 1.05rem; color: #FFFDF2 !important; line-height: 1.7; max-width: 680px; margin: 0 auto; font-style: italic; }
.rc-pitch-quote strong { color: #ffffff !important; font-style: normal; }

/* OH CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Continue your journey */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: #FFD706; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); border-bottom: 2px solid var(--lightgray) !important; transition: all .2s; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-oh-cta { padding: 24px 20px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Plans Q&amp;A.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing & Plans 101
      </div>
      <div class="rc-lp-hero-title"><h1>Plans — Strategy &amp; Best Practices</h1></div>
      <p>Configuration gets your plan live. Strategy keeps it working. Here's how subscription-forward businesses think about plan design, pricing reviews, and staying competitive in 2026.</p>
    </div>

    <!-- Navigation Menu — non-sticky, open, Micro-Path, page 3 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-sticky-link"><span class="rc-step-badge">1</span> Plans: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Plans: Configure</a>
        <!-- Active page: map pin replaces badge -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Plans: Strategy
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Portfolio strategy -->
    <div class="rc-lp-section" id="portfolio-strategy">
      <h2>🏗️ Building a plan portfolio that works</h2>
      <p>The best plan portfolios aren't designed around what's easy to configure — they're designed around how different subscribers make buying decisions. Here are the principles that consistently separate high-performing portfolios from ones that plateau.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Lead with monthly, migrate to annual</h4>
            <p>Monthly plans lower the barrier to entry — they let a prospect try your product without a year-long commitment. But annual plans are where your LTV is built. The strategy that works: <strong>use monthly as your acquisition tier, then trigger an annual upgrade offer when a subscriber hits an engagement milestone</strong> — consistent usage, feature adoption, or a specific action that signals they've found value.</p>
            <p>Don't pitch annual at signup to cold traffic. Pitch it to subscribers who've already decided they want to stay.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Stay at 3–4 tiers maximum</h4>
            <p>Good / Better / Best (+ Enterprise) is the proven framework. Beyond four tiers, conversion drops because subscribers spend more energy comparing plans than deciding to buy. Each tier should offer a meaningfully different value proposition — not just more of the same features at a higher price.</p>
            <p>If you're struggling to differentiate tiers, the problem is usually that <strong>you're adding features instead of adding outcomes</strong>. "10 users vs. 25 users" is a feature. "Growth plan for scaling teams" is an outcome.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Never lock essential features behind the top tier</h4>
            <p>Putting features subscribers need to get basic value from your product behind an expensive tier is one of the fastest ways to drive churn. If a subscriber on your entry tier can't achieve the core outcome your product promises, they'll cancel — not upgrade.</p>
            <p>Reserve top-tier features for <strong>expansion</strong> — more capacity, faster performance, dedicated support, advanced analytics, team collaboration. Lock power-user features, not core functionality.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Assign dunning campaigns at the plan level — always</h4>
            <p>Monthly and annual subscribers experience payment failures differently. Monthly plans fail more frequently but recover faster. Annual plans fail less often but the stakes are higher when they do — a failed annual renewal means losing a full year of revenue.</p>
            <p><strong>Assign plan-specific dunning campaigns</strong> rather than relying on your site default. Monthly: tight, fast cadence. Annual: longer window with pre-renewal email communication built in. This single configuration decision will measurably improve your involuntary churn rate.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content">
            <h4>Review pricing at least annually — and know when to do it sooner</h4>
            <p>Pricing isn't a set-and-forget decision. The right cadence is a formal review at minimum once per year, plus an immediate review when you see: a spike in price-driven churn from exit surveys, a significant product change, new market entry, or a meaningful competitive pricing shift.</p>
            <p>When you update pricing for existing subscribers, remember that <strong>versioned terms mean you'll need to communicate changes at the subscription level</strong> — either via email, in-product messaging, or an API-driven price update with appropriate notice.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Audit checklist -->
    <div class="rc-lp-section" id="audit">
      <h2>🔍 Your plan portfolio audit checklist</h2>
      <p>Run this audit on your current plan setup. These are the signals that tell you where your portfolio is working and where it's leaving acquisition on the table.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span style="font-size:1rem;">📋</span>
          <h4>Plan portfolio health check</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I offer at least one monthly and one annual option</strong>
            <span>If not: you're choosing between acquisition and retention. You can have both.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>No more than 4 active plan tiers for any given product</strong>
            <span>If more: audit which tiers are actually converting and archive the rest.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Less than 70% of subscribers are on my cheapest plan</strong>
            <span>If over 70%: your value messaging for higher tiers needs work — not your price.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Each plan has a dedicated dunning campaign assigned</strong>
            <span>If not: you're using one-size-fits-all recovery logic. This is costing you revenue.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Plan names are customer-facing and benefit-led (not internal codes)</strong>
            <span>If not: you're wasting prime invoice real estate. Your plan name is a retention message.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I have a pre-renewal email strategy for annual plans</strong>
            <span>If not: you're walking into your highest-risk billing moment without preparation.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I review plan distribution and churn by plan monthly</strong>
            <span>If not: Plan Analytics → Subscriptions by Plan takes 5 minutes and tells you everything.</span>
          </div>
        </label>
        <div class="rc-checklist-footer">✓ Mark each item complete as you address it — any unchecked item is a specific, actionable opportunity</div>
      </div>
    </div>

    <!-- AI strategy -->
    <div class="rc-lp-section" id="ai-strategy">
      <h2>🤖 Plans in the AI era — what to think about now</h2>
      <p>The way subscribers discover and evaluate subscription plans is changing. AI assistants are increasingly being asked questions like "what's the best project management subscription for a 10-person team?" Your plan names, descriptions, and pricing structure are part of how those answers get built.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"How does my plan name affect AI search results?"</h4>
            <p>AI assistants pull plan information from your public-facing pages. <strong>Plan names that are descriptive and benefit-led are more likely to be surfaced accurately</strong> in AI-generated comparisons. "Pro Monthly" tells an AI assistant what the tier is and how it bills. "Plan B" tells it nothing.</p>
            <p>The same applies to your plan description field — it appears on invoices but also indexes publicly. Use it to state the value your plan delivers, not just what it includes.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"What does 43% of consumers comfortable with AI managing subscriptions mean for me?"</h4>
            <p>AI agents are beginning to evaluate, manage, and switch subscriptions on users' behalf — comparing value, flagging underused subscriptions, and recommending alternatives. <strong>Plans that are easy to compare — clear pricing, clear value, clear differentiation between tiers — will win in that environment.</strong></p>
            <p>Plans with opaque pricing, confusing tier names, or hidden upgrade paths will lose. Simplicity is now a competitive advantage, not just a UX preference.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Should I be using AI tools to inform my pricing decisions?"</h4>
            <p>Yes — and many of your competitors already are. On the pricing side, AI tools can help you analyze your plan distribution exports, identify cohorts where churn is concentrated, and surface patterns in which plans convert best from trial to paid.</p>
            <p>Start simple: export your plan performance data from Recurly Analytics and use an AI tool to analyze it. Ask "which plan has the highest LTV and why?" The answer will sharpen every pricing decision you make.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>The 2026 competitive edge</strong>
          <p>The merchants winning in this environment treat subscription data as a strategic asset, not billing infrastructure. Your plan codes, segment codes, add-on codes, and analytics exports are the raw material for AI-assisted decision-making. The cleaner and more consistent your data structure, the more intelligence you can extract from it.</p>
        </div>
      </div>
    </div>

    <!-- Pitch card -->
    <div class="rc-pitch-card">
      <div class="rc-pitch-emoji">📈</div>
      <h3>Pricing is a retention decision</h3>
      <p class="rc-pitch-quote">"The model you choose today shapes subscriber behavior <strong>12 months from now.</strong> Price to acquire the subscriber you want to keep — not just the subscriber you want to convert."</p>
    </div>

    <!-- Thought-provoking question — required on last page of every Micro-Path -->
    <div class="rc-lp-section">
      <h2>💭 Something to consider</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">?</div>
          <div class="rc-step-content">
            <h4>If you could only keep one plan in your current portfolio, which one would you keep — and what does that tell you about your pricing strategy?</h4>
            <p>This question often surfaces the tension between your acquisition plan (the one that converts most) and your retention plan (the one that generates most LTV). If the answer is two different plans, that's a signal your portfolio is doing its job — serving distinct subscriber needs at distinct stages. If it's the same plan, it may be worth asking whether your tiers are genuinely differentiated, or whether you're offering the same value at different prices.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- OH CTA — follows thought-provoking question per skill rule -->
    <div class="rc-oh-cta">
      <h4>🗓️ Questions about your specific plan setup?</h4>
      <p>Our Customer Success team runs weekly <strong>Global Office Hours</strong> sessions where you can bring your real configuration questions — plan structure, dunning setup, migration strategy, pricing model decisions. No agenda required.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav — completion state -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-btn-prev">← Configure</a>
      <span class="rc-lp-nav-indicator">3 of 3 · Plans</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-btn-path">Continue to Add-Ons →</a>
    </div>


    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://recurly.com/blog/subscription-pricing-strategy-playbook/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Subscription Pricing Strategy Playbook</a>
        <a href="https://recurly.com/blog/pricing-subscription-strategies/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Best Subscription Pricing Strategies</a>
        <a href="https://recurly.com/research/saas-benchmarks-for-subscription-plans/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📊 SaaS Plan Benchmarks</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans-pricing-and-promotions-analytics" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📊 Plans, Pricing &amp; Promotions Analytics</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped sections -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Plans:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-configure" class="rc-footer-link">Plans: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans-strategy" class="rc-footer-link">Plans: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Plans 101</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">Pricing & Plans 101: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">Analytics</a>
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
