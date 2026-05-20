---
title: 'Trials: Best practices & strategy'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
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
.rc-lp-section p:last-child { margin-bottom: 0; }

/* Callouts */
.rc-callout { border-radius: 10px; padding: 16px 20px; margin: 20px 0; display: flex; gap: 14px; align-items: flex-start; }
.rc-callout + .rc-callout { margin-top: 12px; }
.rc-callout-icon { font-size: 1.1rem; line-height: 1.4; flex-shrink: 0; }
.rc-callout-body { flex: 1; }
.rc-callout-body > strong { font-size: .88rem; font-weight: 800; display: block; margin-bottom: 4px; }
.rc-callout-body p { font-size: .9rem; line-height: 1.55; margin: 0; color: var(--darkgray); }
.rc-callout-body a { color: var(--orange) !important; font-weight: 600; }
.rc-guide .rc-callout-body a:hover { text-decoration: underline !important; }
.rc-callout-tip { background: var(--brightgray); border-left: 4px solid var(--offblack); }
.rc-callout-tip .rc-callout-body > strong { color: var(--offblack); }
.rc-callout-warning { background: rgba(255,215,6,0.12); border-left: 4px solid var(--yellow); }
.rc-callout-warning .rc-callout-body > strong { color: var(--darkgray); }

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

/* Pitch card */
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
.rc-btn-complete { background: var(--brightgray); color: var(--offblack) !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--yellow); cursor: default; user-select: none; }

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
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Pricing &amp; Packaging Q&amp;A.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · P&amp;P 101
      </div>
      <div class="rc-lp-hero-title"><h1>Trials — Strategy &amp; Best Practices</h1></div>
      <p>Trial strategy isn't just about how long the trial is — it's about who starts, what they do during it, and whether the trial creates the conditions for a confident purchase decision. Here's how to match trial design to business outcome and know when your trial is the problem vs. when the trial is fine and something else is broken.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Card first</div><div class="rc-hero-stat-label">default to requiring billing info — cardless trials widen the funnel but rarely improve paid conversion</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Shorter</div><div class="rc-hero-stat-label">shorter trials often outperform longer ones — the goal is a value moment, not feature exploration</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">Activate fast</div><div class="rc-hero-stat-label">the most reliable conversion lever is how quickly the subscriber reaches a product value moment</div></div>
      </div>
    </div>

    <!-- Navigation Menu — page 3 active -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-sticky-link"><span class="rc-step-badge">1</span> Trials: Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-sticky-link"><span class="rc-step-badge">2</span> Trials: Configure</a>
        <!-- Active page: map pin replaces badge -->
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-strategy" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Trials: Strategy
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
        </a>
      </div></div></div>
    </details>

    <!-- Trial design framework -->
    <div class="rc-lp-section" id="trial-framework">
      <h2>🏗️ Matching trial design to business outcome</h2>
      <p>A trial converts when a subscriber reaches a clear value moment during the trial period and believes the product is worth the full price at the end. Every trial design decision — length, card requirement, onboarding flow — should be optimised for creating that moment, not for maximising trial starts.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content">
            <h4>Start with time-to-value, not trial length</h4>
            <p>Before you set a trial length, ask: how long does it take a new subscriber to reach the moment where they clearly understand what your product does for them? That's your minimum viable trial length. A 7-day trial is better than a 30-day trial if your product's value moment happens within the first week — subscribers who see value quickly convert at higher rates and with less decision delay. Longer trials don't compensate for a slow time-to-value; they just delay the conversion decision.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content">
            <h4>Default to requiring billing info</h4>
            <p>Card-required trials produce cleaner conversion signals, automatic billing at trial end, and no payment collection risk. The tradeoff — fewer trial starts — is usually worth it for SaaS products with a defined ICP and a sales motion that can qualify intent at the funnel entry point. Reserve cardless trials for products where the value proposition is self-evident quickly and the cost to acquire a trial user is very low — consumer apps, low-touch PLG products, or markets where card-at-signup creates significant cultural friction.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content">
            <h4>Design the trial as an activation sprint, not a feature tour</h4>
            <p>The most effective trial onboarding sequences are not "here's everything you can do" — they're "here's the one thing that will show you why this product is worth paying for." Identify your product's highest-correlation activation event (the action that most predicts conversion) and build the first 72 hours of onboarding around getting every trial subscriber to that event. Recurly's trial mechanism gives you the time window; your onboarding stack fills it with purpose.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content">
            <h4>Set your conversion benchmark before you optimise</h4>
            <p>You can't improve trial conversion without knowing what it currently is. Before testing trial length, card requirement, or onboarding changes, establish a baseline: what percentage of trial starts convert to paid in the current configuration? Track this separately for card-required and cardless trials if you run both. Without a baseline, trial experiments produce noise, not insight. Recurly's subscription reporting gives you trial conversion data — pull it before making structural trial changes.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Common Q&A -->
    <div class="rc-lp-section" id="qa">
      <h2>❓ Common trial strategy questions</h2>
      <p>These are the questions most frequently raised in office hours sessions and CSM conversations when merchants are diagnosing or redesigning their trial configuration.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Our trial conversion rate is low. Should we make the trial longer?"</h4>
            <p>Probably not — and definitely not without data. First, segment your conversion data: are subscribers who complete a specific activation event converting at a higher rate than those who don't? If yes, the problem is activation, not trial length. If subscribers are reaching your product's value moment within the trial window but still not converting, the problem may be pricing, trust, or the decision-making environment at trial end — not how many days they had. <strong>Extend trial length only after confirming that subscribers who need more time actually convert at a meaningfully higher rate.</strong></p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"We switched to cardless trials and our trial starts tripled. Is this a success?"</h4>
            <p>Not necessarily — it depends on what happened to your paid conversion rate. Tripling trial starts with a cardless trial is a top-of-funnel metric; it tells you more people are willing to try something for free than to commit with a card. <strong>What matters is paid conversion rate and paid conversion volume.</strong> If 300% more starts at a 10% conversion rate produces fewer paid subscribers than 100% starts at a 40% conversion rate, the cardless trial is worse for the business despite looking better on a chart. Review the full funnel, not just the first step.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can we run different trial lengths on different plans to test which converts better?"</h4>
            <p>Yes — because trials are plan-level settings, different plans can have different trial configurations. You can create two plans with identical pricing but different trial lengths (e.g. 7 days vs. 14 days), route cohorts of new subscribers to each plan, and compare conversion rates after a statistically significant sample period. <strong>Make sure the plans are otherwise identical</strong> so you're isolating trial length as the variable. Use Recurly's subscription reporting filtered by plan to pull conversion data for each cohort.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Subscribers are canceling during the trial before it ends. What should we do?"</h4>
            <p>In-trial cancellations are a product or expectation signal, not a trial design problem. Check what subscribers are doing before they cancel: are they reaching any activation events? Did they complete onboarding? Were they on a self-serve flow or a sales-assisted one? In-trial cancellations that happen in the first 24–48 hours are often expectation mismatches at signup — the product didn't match what was advertised. In-trial cancellations that happen in days 5–7 of a 14-day trial often indicate an activation failure. The diagnosis shapes the intervention.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Audit checklist -->
    <div class="rc-lp-section" id="audit">
      <h2>🔍 Trial health check</h2>
      <p>Run this audit on your current trial configuration and conversion data. The most common finding is a mismatch between what the trial is designed to do and what the business actually needs it to do.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span style="font-size:1rem;">📋</span>
          <h4>Trial configuration and strategy audit</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial-to-paid conversion rate is tracked and has a documented baseline</strong>
            <span>If not: pull conversion data from Recurly reporting filtered by plan before making any trial changes. You can't improve what you haven't measured.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial length is based on time-to-value data, not a round number</strong>
            <span>If "30 days" was chosen because it felt right, audit your activation data: when do converting subscribers typically reach their first value moment? That's your real trial length target.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Cardless trials have an active payment collection workflow</strong>
            <span>If cardless trials are in use: confirm there's an email/in-app sequence prompting subscribers to add a payment method before trial end — and that past-due handling is configured in Recurly dunning settings.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial end notifications are set up and tested</strong>
            <span>Subscribers should receive at least one email before their trial ends reminding them of the conversion date and the price they'll be charged. Verify these emails are firing in your email service — Recurly generates the events, but delivery depends on your connected email stack.</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial extension policy is documented and known to your support and CS teams</strong>
            <span>If your teams are extending trials ad hoc without a policy, you're losing conversion signal and delaying revenue unpredictably. Define the criteria for extension (e.g. high-intent enterprise prospects only, maximum 7 additional days).</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>Trial behavior has been tested in sandbox for all three outcomes: convert, cancel, expire without payment</strong>
            <span>If the "expire without payment" case hasn't been tested: verify what happens to past-due subscriptions in your Recurly dunning workflow and confirm your team knows what to do with them operationally.</span>
          </div>
        </label>
        <div class="rc-checklist-footer">✓ Mark each item complete as you address it — any unchecked item is a specific, actionable opportunity</div>
      </div>
    </div>

    <!-- AI era -->
    <div class="rc-lp-section" id="ai-trials">
      <h2>🤖 Trials in the AI era</h2>
      <p>Two shifts are changing how trials perform as AI adoption accelerates. First, AI-assisted onboarding is compressing the time it takes subscribers to reach product value — tools that guide users through setup, explain features contextually, and surface relevant capabilities faster are shortening the time-to-value window. Second, AI agents evaluating subscriptions on a buyer's behalf are increasingly making the trial decision before a human even starts one.</p>

      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Does AI-assisted onboarding mean we should shorten our trial length?"</h4>
            <p>Possibly — and it's worth testing. If your product's onboarding is becoming more guided and the time-to-value is shrinking, a shorter trial may convert just as well as a longer one while reducing the decision delay at trial end. <strong>Monitor your activation event timing</strong> as you improve onboarding: if the median activation event moves from day 6 to day 3 of a 14-day trial, a 7-day trial becomes a meaningful experiment to run. Use Recurly's plan-level trial A/B capability (separate plans, different trial lengths) to test without disrupting existing subscribers.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"If AI agents are evaluating subscriptions for buyers, how does that change trial strategy?"</h4>
            <p>An AI agent asked "what's the best tool for X, and is there a trial?" will surface your trial based on what's discoverable and clearly described in your public content. <strong>Your trial terms need to be machine-readable and unambiguous:</strong> how long is the trial, is a card required, what happens at the end. AI agents that can't clearly extract trial terms will either misrepresent them or default to a competitor with clearer terms. This is an argument for plain, structured trial communication on your pricing page — not just for human readers.</p>
          </div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>The activation speed advantage</strong>
          <p>As AI tools make product onboarding faster and more guided, the products that convert trials best will be the ones that reach a value moment earliest — not the ones with the longest trial windows. Investing in activation velocity (faster setup, smarter defaults, proactive feature guidance) will compound on trial conversion more reliably than adjusting trial length alone.</p>
        </div>
      </div>
    </div>

    <!-- Pitch card -->
    <div class="rc-pitch-card">
      <div class="rc-pitch-emoji">🧪</div>
      <h3>A trial converts when it earns trust — not just time</h3>
      <p class="rc-pitch-quote">"The best trial isn't the longest one — it's the one that gets the subscriber to a <strong>clear, undeniable value moment</strong> and then steps out of the way and asks for the commitment."</p>
    </div>

    <!-- Thought-provoking question — required on last page of every Micro-Path -->
    <div class="rc-lp-section">
      <h2>💭 Something to consider</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">?</div>
          <div class="rc-step-content">
            <h4>Look at your current trial configuration: are you measuring the right things, and does your trial length reflect time-to-value data or a historical default that no one has questioned?</h4>
            <p>Many subscription products are running the same trial length they launched with — because changing it felt risky and no one had the baseline data to justify the experiment. If your trial conversion rate hasn't been reviewed in the last two quarters, that's the most important next step — not configuration changes. Understanding what's actually happening at trial end (conversion, cancellation, expiry) with your current setup gives you the baseline to make every subsequent trial decision evidence-based rather than instinct-based.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- OH CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Questions about your trial strategy or configuration?</h4>
      <p>Our Customer Success team runs weekly <strong>Global Office Hours</strong> sessions where you can bring specific trial questions — whether to require a card, how to measure conversion, how to set up a coupon-based trial, or how to handle cardless trial expiry in your dunning workflow.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav — completion state -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-btn-prev">← Configure</a>
      <span class="rc-lp-nav-indicator">3 of 3 · Trials</span>
      <span class="rc-btn-complete">Continue to Analytics!</span>
    </div>

    <!-- Continue your journey -->
    <div class="rc-next-steps">
      <h3>🧭 Continue your journey</h3>
      <div class="rc-next-grid">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-next-card">
          <div class="rc-next-card-tag">Next in series</div>
          <div class="rc-next-card-icon">📊</div>
          <h4>Analytics</h4>
          <p>Your trial strategy produces data — but only if you know where to find it and what to measure. Learn how to use Recurly's plan analytics to track trial conversion, subscription growth, and revenue by plan.</p>
          <div class="rc-next-card-arrow">Start Analytics →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-next-card">
          <div class="rc-next-card-tag">Series hub</div>
          <div class="rc-next-card-icon">🎯</div>
          <h4>P&amp;P 101 Overview</h4>
          <p>Return to the full series overview to see all six paths and track your progress through the Pricing &amp; Packaging 101 program.</p>
          <div class="rc-next-card-arrow">View all paths →</div>
        </a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-next-card">
          <div class="rc-next-card-tag">Live session</div>
          <div class="rc-next-card-icon">🎙️</div>
          <h4>Global Office Hours</h4>
          <p>Bring your trial strategy questions to our CSMs live. Ask about conversion benchmarks, cardless trial workflows, or how to run a trial A/B test — sessions run weekly.</p>
          <div class="rc-next-card-arrow">Register →</div>
        </a>
      </div>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/trials" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Trials</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Dunning</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Coupons</a>
        <a href="https://recurly.com/blog/free-trial-conversion-rate/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📝 Recurly Blog: Free Trial Conversion</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Support</a>
      </div>
    </div>

    <!-- Footer — grouped sections -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Micro-Path: Trials:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">Trials: Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-configure" class="rc-footer-link">Trials: Configure</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials-strategy" class="rc-footer-link">Trials: Strategy &amp; Best Practices</a>
        </div>
        <div class="rc-footer-section">
          <span class="rc-footer-label">Pricing &amp; Packaging 101:</span>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101 Overview</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">Plans</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">Add-Ons</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">Currency</a>
          <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">Pricing Models</a>
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
