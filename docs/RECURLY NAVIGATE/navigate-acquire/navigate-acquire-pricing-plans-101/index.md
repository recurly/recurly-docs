---
title: 'Pricing & Packaging 101: The Basics'
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
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* Back link */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* Content wrap */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Announcement bar */
.rc-announce-bar {
  display: none; background: var(--yellow); color: var(--offblack);
  align-items: center; justify-content: space-between;
  padding: 10px 20px; font-size: .88rem; font-weight: 600;
  border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link { color: var(--offblack) !important; font-weight: 800; text-decoration: none !important; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; }
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close { background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0; }
.rc-announce-close:hover { opacity: 1; }

/* Hero — pillar subpage style (no stats, uses logo) */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #fff; padding: 52px 40px 48px; text-align: center; border-radius: 16px; margin-bottom: 0;
}
.rc-hero-logo { height: 32px; margin-bottom: 20px; display: block; margin-left: auto; margin-right: auto; }
.rc-hero-pill {
  display: inline-flex; align-items: center; gap: 7px;
  background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45);
  color: #FFD706; font-size: .75rem; font-weight: 800;
  letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 20px;
}
.rc-hero-pill img { width: 13px; height: 13px; object-fit: contain; }
.rc-hero h1 { font-size: 2.6rem; font-weight: 800; line-height: 1.1; color: #FFFDF2; margin: 0 0 16px; }
.rc-hero p { font-size: 1.05rem; opacity: .85; max-width: 660px; margin: 0 auto; color: #CCC9B8; line-height: 1.65; }

/* Hero stat strip */
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 28px; margin-top: 32px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 2rem; font-weight: 800; color: #FFD706; line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: #CCC9B8; line-height: 1.3; }

/* Nav — sticky, collapsed, Acquire yellow */
details.rc-sticky-nav-wrap {
  position: sticky; top: 0; z-index: 100;
  background-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0; border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08); overflow: hidden;
}
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
.rc-sticky-link {
  color: var(--offblack) !important; text-decoration: none !important;
  font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase;
  padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap;
  display: inline-flex; align-items: center; gap: 6px;
}
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Section headings */
.rc-lp-section { margin-bottom: 56px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* Intro pitch card */
.rc-pitch-card { background: #0D0D0B !important; border-radius: 14px; padding: 36px 40px; text-align: center; margin: 0 0 48px; border: 1px solid rgba(255,255,255,0.08); }
.rc-pitch-emoji { font-size: 2.4rem; margin-bottom: 12px; }
.rc-pitch-card h3 { font-size: 1.1rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; color: #FFD706 !important; margin: 0 0 16px; }
.rc-pitch-quote { font-size: 1.05rem; color: #FFFDF2 !important; line-height: 1.7; max-width: 700px; margin: 0 auto; font-style: italic; }
.rc-pitch-quote strong { color: #ffffff !important; font-style: normal; }

/* 6-card series grid */
.rc-series-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin: 0 0 40px; }
.rc-series-card {
  background: var(--offwhite); border: 1px solid var(--lightgray);
  border-radius: 12px; padding: 22px; display: flex; flex-direction: column;
  gap: 8px; transition: all .2s ease;
}
.rc-guide a.rc-series-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-series-card:hover { border-color: #FFD706; border-bottom: 1px solid #FFD706 !important; box-shadow: 0 4px 16px rgba(255,215,6,0.18); transform: translateY(-2px); }
.rc-series-num { display: inline-flex; align-items: center; justify-content: center; width: 28px; height: 28px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .75rem; font-weight: 800; flex-shrink: 0; margin-bottom: 4px; }
.rc-series-card h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-series-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-series-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

/* Stat strip (content) */
.rc-stat-strip { display: grid; grid-template-columns: repeat(3, 1fr); background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; overflow: hidden; margin: 0 0 32px; }
.rc-stat-tile { padding: 24px 20px; text-align: center; }
.rc-stat-tile + .rc-stat-tile { border-left: 1px solid var(--lightgray); }
.rc-stat-tile-num { font-size: 2rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 4px; }
.rc-stat-tile-label { font-size: .7rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; color: var(--gray); margin-bottom: 10px; }
.rc-stat-tile-context { font-size: .8rem; color: var(--darkgray); line-height: 1.5; padding-top: 10px; border-top: 1px solid var(--brightgray); }

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

/* Diagnostic checklist */
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

/* 201 CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: #FFD706; font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: #CCC9B8; font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: #FFFDF2; }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 48px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: #FFD706 !important; }

/* Footer nav */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .9rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-hero h1 { font-size: 1.9rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; margin-top: 24px; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-series-grid { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-oh-cta { padding: 24px 20px; }
}
</style>

<div class="rc-guide">

  <!-- Back link -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>

  <div class="rc-content-wrap">

    <!-- Announcement bar (hidden — activate by adding rc-active) -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live Pricing & Packaging Q&A session.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-hero-pill">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire
      </div>
      <h1>Pricing &amp; Packaging 101</h1>
      <p>Your pricing structure is your first acquisition message. Learn how to build plans, add-ons, trials, and currencies that convert — and keep subscribers coming back.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">78%</div>
          <div class="rc-hero-stat-label">of merchants offer both monthly &amp; annual plans</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">50–60%</div>
          <div class="rc-hero-stat-label">more revenue per user on annual plans</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">13%</div>
          <div class="rc-hero-stat-label">of buyers converted by micro-subscriptions</div>
        </div>
      </div>
    </div>

    <!-- Nav — sticky, collapsed, active on hub -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigate Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
						 <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Pricing & Plans 101
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-sticky-link"><span class="rc-step-badge">1</span> Plans</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-sticky-link"><span class="rc-step-badge">2</span> Add-Ons</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-sticky-link"><span class="rc-step-badge">3</span> Currency</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-sticky-link"><span class="rc-step-badge">4</span> Pricing Models</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-sticky-link"><span class="rc-step-badge">5</span> Trials</a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-sticky-link"><span class="rc-step-badge">6</span> Analytics</a>
           
          </div>
        </div>
      </div>
    </details>

    <!-- Pitch card -->
    <div class="rc-pitch-card">
      <div class="rc-pitch-emoji">🎯</div>
      <h3>Your pricing is your product</h3>
      <p class="rc-pitch-quote">"Growth is no longer about who spends the most. It's about how well you <strong>connect conversion, payment, and retention</strong> in one loop."<br><span style="font-size:.88rem; opacity:.7; font-style:normal; color:#CCC9B8;">— Brian Geier, VP Business Intelligence, Recurly</span></p>
    </div>

    <!-- Why this series matters -->
    <div class="rc-lp-section" id="why-it-matters">
      <h2>📊 Why pricing &amp; packaging is your #1 acquisition lever</h2>
      <p>The 2026 State of Subscriptions report is clear: <strong>price (86%) and value for money (88%)</strong> are the top two reasons consumers choose a subscription. Your plan structure isn't a billing configuration — it's the first value message your prospective subscriber receives.</p>
      <p>Yet the data shows a critical gap. While 78% of merchants now offer both monthly and annual plans, most still default to a single pricing tier. Merchants with diversified plan portfolios consistently outperform those with one option — because different subscribers need different entry points, and a single plan leaves acquisition on the table.</p>

      <div class="rc-stat-strip">
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num" style="color:#FFD706;">71%</div>
          <div class="rc-stat-tile-label">Offer Both Monthly &amp; Annual</div>
          <div class="rc-stat-tile-context">Across all industries. Software (76%) and Education (80%) lead.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num" style="color:#FFD706;">50–60%</div>
          <div class="rc-stat-tile-label">More Revenue Per User</div>
          <div class="rc-stat-tile-context">Annual subscribers generate significantly more LTV than monthly, despite higher renewal decline rates.</div>
        </div>
        <div class="rc-stat-tile">
          <div class="rc-stat-tile-num" style="color:#FFD706;">34%</div>
          <div class="rc-stat-tile-label">Trial Conversion (2025)</div>
          <div class="rc-stat-tile-context">Down from 47% in 2021. Micro-subscriptions (day/week passes) are filling the gap at 13% conversion.</div>
        </div>
      </div>

      <div class="rc-callout rc-callout-warning">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>The single-plan ceiling</strong>
          <p>If 70% or more of your subscribers are on your cheapest plan, that's not a pricing success — it's a value perception problem. This series will help you build a portfolio that moves subscribers toward higher-value tiers naturally.</p>
        </div>
      </div>
    </div>

    <!-- What's in this series -->
    <div class="rc-lp-section" id="whats-inside">
      <h2>📚 What's in the 101 series</h2>
      <p>Six micro-learning paths, each covering one core topic. Each path has three pages: Overview, Configure, and Strategy &amp; Best Practices. Work through them in order or jump to the topic you need most.</p>

      <div class="rc-series-grid">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-series-card">
          <div class="rc-series-num">1</div>
          <h4>Plans</h4>
          <p>Build a strategic plan portfolio — monthly, annual, and tiered options that serve different subscriber segments and drive more conversions.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-series-card">
          <div class="rc-series-num">2</div>
          <h4>Add-Ons</h4>
          <p>Increase ARPU and create flexible packaging with optional and required add-ons. Learn when to use the Item Catalog for reusable add-ons.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-series-card">
          <div class="rc-series-num">3</div>
          <h4>Currency</h4>
          <p>Configure multi-currency billing to reduce checkout friction for global subscribers. Understand regional payment behavior differences.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-series-card">
          <div class="rc-series-num">4</div>
          <h4>Pricing Models</h4>
          <p>Fixed, Ramp, Tiered, Volume, Stairstep — understand when each model wins and how to use introductory pricing to reduce acquisition friction.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-series-card">
          <div class="rc-series-num">5</div>
          <h4>Trials</h4>
          <p>Configure trials that convert. Understand the tradeoffs between free trials, cardless trials, and micro-subscriptions as acquisition entry points.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-series-card">
          <div class="rc-series-num">6</div>
          <h4>Plan Analytics</h4>
          <p>Know which plans are working and why. Use Recurly's Analytics dashboards to track MRR by plan, trial conversion, churn, and subscriber LTV.</p>
          <div class="rc-series-arrow">Start →</div>
        </a>
      </div>
    </div>

    <!-- Where to start diagnostic -->
    <div class="rc-lp-section" id="where-to-start">
      <h2>🧭 Where should you start?</h2>
      <p>Not sure which path to tackle first? Use this quick diagnostic to find your starting point. Check off what you already have in place — whatever's unchecked is where you'll find the quickest wins.</p>

      <div class="rc-checklist">
        <div class="rc-checklist-header">
          <span style="font-size:1rem;">✅</span>
          <h4>Your pricing &amp; packaging readiness checklist</h4>
        </div>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I offer at least two plan options (e.g., monthly and annual)</strong>
            <span>If not, start with Plans →</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I have at least one add-on configured for upsell</strong>
            <span>If not, start with Add-Ons →</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>My plans are priced in local currencies for my key markets</strong>
            <span>If not, start with Currency →</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I've considered Ramp or Tiered pricing for at least one plan or add-on</strong>
            <span>If not, start with Pricing Models →</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I have a trial or low-friction entry offer configured</strong>
            <span>If not, start with Trials →</span>
          </div>
        </label>
        <label class="rc-checklist-item">
          <input type="checkbox">
          <div class="rc-checkbox-box"></div>
          <div class="rc-checklist-text">
            <strong>I regularly review plan performance in Recurly Analytics</strong>
            <span>If not, start with Plan Analytics →</span>
          </div>
        </label>
        <div class="rc-checklist-footer">✓ Tap each item to mark it complete — use unchecked items as your priority list</div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Recommended path for most merchants</strong>
          <p>Start with <strong>Plans</strong> to establish your portfolio foundation, then <strong>Trials</strong> to optimize your acquisition entry point, then <strong>Plan Analytics</strong> to measure what's working before investing in more complex configurations.</p>
        </div>
      </div>
    </div>

    <!-- 201 Upgrade CTA -->
    <div class="rc-oh-cta">
      <h4>📈 Ready for the next level?</h4>
      <p>Once you've completed the 101 series, <strong>Pricing &amp; Packaging 201</strong> takes you deeper — pricing segmentation, parent/child account hierarchy, usage-based billing, advanced pricing models, and multi-currency strategy at scale.</p>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-oh-btn">Explore P&amp;P 201 →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/add-ons" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-analytics-overview" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Analytics</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
      </div>
    </div>

    <!-- Footer nav -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101" class="rc-footer-link">P&amp;P 101</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plans" class="rc-footer-link">1 · Plans</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-add-ons" class="rc-footer-link">2 · Add-Ons</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-currency" class="rc-footer-link">3 · Currency</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-pricing-models" class="rc-footer-link">4 · Pricing Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-trials" class="rc-footer-link">5 · Trials</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-101-plan-analytics" class="rc-footer-link">6 · Analytics</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
