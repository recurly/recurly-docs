---
title: 'Advanced Currency: Best practices & strategy'
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
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* Nav */
details.rc-sticky-nav-wrap { position: static; background-color: var(--yellow); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
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
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow) !important; color: var(--offblack) !important; }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Content sections */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack); display: flex; align-items: center; gap: 12px; }
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

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
.rc-callout-caution { background: rgba(255,130,0,0.08); border-left: 4px solid var(--orange); }
.rc-callout-caution .rc-callout-body > strong { color: var(--darkgray); }

/* Accent cards */
.rc-accent-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 24px 28px; margin: 20px 0; }
.rc-accent-card.rc-accent-orange { border-left: 4px solid var(--orange); }
.rc-accent-card.rc-accent-yellow { border-left: 4px solid var(--yellow); }
.rc-accent-card h4 { font-size: 1rem; font-weight: 800; color: var(--offblack); margin: 0 0 12px; }
.rc-accent-card p { font-size: .92rem; color: var(--darkgray); line-height: 1.65; margin: 0 0 10px; }
.rc-accent-card ul { font-size: .9rem; color: var(--gray); line-height: 1.75; padding-left: 20px; margin: 0; }
.rc-accent-card ul li { margin-bottom: 4px; }
.rc-accent-card ul li strong { color: var(--darkgray); }

/* Q&A steps */
.rc-steps { display: flex; flex-direction: column; gap: 0; margin: 20px 0 0; }
.rc-step { display: grid; grid-template-columns: 40px 1fr; gap: 16px; align-items: flex-start; padding: 18px 0; border-bottom: 1px solid var(--brightgray); }
.rc-step:last-child { border-bottom: none; }
.rc-step-num-q { width: 36px; height: 36px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; margin-top: 2px; }
.rc-step-content h4 { font-size: 1.02rem; font-weight: 800; color: var(--offblack); margin: 0 0 6px; line-height: 1.3; }
.rc-step-content p { font-size: .92rem; color: var(--gray); line-height: 1.6; margin: 0 0 8px; }
.rc-step-content p:last-child { margin-bottom: 0; }
.rc-step-content strong { color: var(--darkgray); }

/* Thought question */
.rc-thought-q { background: var(--offblack); border-radius: 14px; padding: 36px 40px; margin: 40px 0; text-align: center; border: 1px solid rgba(255,255,255,0.08); }
.rc-thought-q-label { font-size: .72rem; font-weight: 700; letter-spacing: 1px; text-transform: uppercase; color: #FFD706; margin-bottom: 16px; display: block; }
.rc-thought-q h3 { font-size: 1.25rem; font-weight: 800; color: #FFFDF2 !important; line-height: 1.5; margin: 0 0 12px; max-width: 680px; margin-left: auto; margin-right: auto; }
.rc-thought-q p { font-size: .9rem; color: rgba(255,253,242,0.65) !important; line-height: 1.6; max-width: 580px; margin: 0 auto; }

/* OH CTA */
.rc-oh-cta { background: var(--offblack); border: 2px solid var(--yellow); border-radius: 14px; padding: 32px 36px; margin: 32px 0; }
.rc-oh-cta h4 { color: var(--yellow); font-size: 1.05rem; font-weight: 800; text-transform: uppercase; letter-spacing: 1px; margin: 0 0 12px; }
.rc-oh-cta p { color: var(--lightgray); font-size: .95rem; line-height: 1.6; margin: 0 0 20px; }
.rc-oh-cta p strong { color: var(--offwhite); }
@media(max-width:768px){ .rc-oh-cta { padding: 24px 20px; } }
.rc-guide a.rc-oh-btn { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 12px 24px; border-radius: 10px; font-weight: 800; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-oh-btn { border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-oh-btn:hover { background: transparent !important; color: var(--yellow) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Path nav */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-prev { background: transparent; color: var(--offblack) !important; text-decoration: none !important; padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 8px; border: 2px solid var(--lightgray); transition: all .2s; }
.rc-guide a.rc-btn-prev { border-bottom: 2px solid var(--lightgray) !important; }
.rc-guide a.rc-btn-prev:hover { border: 2px solid var(--offblack) !important; border-bottom: 2px solid var(--offblack) !important; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); border-bottom: 2px solid var(--yellow) !important; }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }

/* Continue Your Journey */
.rc-next-steps { margin: 40px 0 0; }
.rc-next-steps h3 { font-size: .78rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 16px; }
.rc-next-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
.rc-next-card { background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 20px; text-decoration: none !important; color: inherit; display: flex; flex-direction: column; gap: 8px; transition: all .2s ease; }
.rc-guide a.rc-next-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-next-card:hover { border-color: var(--yellow); border-bottom: 1px solid var(--yellow) !important; box-shadow: 0 4px 16px rgba(255,215,6,0.15); transform: translateY(-2px); }
.rc-next-card-tag { font-size: .68rem; font-weight: 700; text-transform: uppercase; letter-spacing: .8px; color: var(--yellow); margin-bottom: 2px; }
.rc-next-card-icon { font-size: 1.3rem; line-height: 1; }
.rc-next-card h4 { font-size: .95rem; font-weight: 800; color: var(--offblack); margin: 0; line-height: 1.3; }
.rc-next-card p { font-size: .85rem; color: var(--gray); line-height: 1.5; margin: 0; flex-grow: 1; }
.rc-next-card-arrow { font-size: .82rem; font-weight: 700; color: var(--orange); margin-top: 4px; }

/* Resources */
.rc-resources { background: var(--brightgray); border-left: 4px solid var(--yellow); border-radius: 10px; padding: 20px 24px; margin: 32px 0 0; }
.rc-resources h3 { font-size: .75rem; font-weight: 700; text-transform: uppercase; letter-spacing: .9px; color: var(--gray); margin: 0 0 12px; }
.rc-resource-links { display: flex; flex-wrap: wrap; gap: 4px 20px; }
.rc-resource-link { color: var(--gray) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--lightgray) !important; font-weight: 500; font-size: .88rem; transition: all .18s; display: inline-flex; align-items: center; gap: 6px; }
.rc-guide .rc-resource-link:hover { color: var(--offblack) !important; text-decoration: underline !important; text-underline-offset: 3px; text-decoration-color: var(--yellow) !important; }

/* Footer */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 32px; text-align: center; }
.rc-footer-section { margin-bottom: 14px; display: flex; flex-wrap: wrap; gap: 6px 20px; justify-content: center; align-items: center; }
.rc-footer-section-label { font-size: .72rem; font-weight: 700; text-transform: uppercase; letter-spacing: .6px; color: var(--gray); opacity: 0.65; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 8px 24px; justify-content: center; padding-top: 16px; border-top: 1px solid var(--brightgray); margin-top: 8px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s; display: inline-flex; align-items: center; gap: 5px; }
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* Responsive */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-thought-q { padding: 28px 24px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-back-link">← Back to Path Start</a>
  </div>

  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live P&amp;P strategy session.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- Hero -->
    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire · Pricing &amp; Plans 201
      </div>
      <div class="rc-lp-hero-title"><h1>Advanced currency — Strategy &amp; best practices</h1></div>
      <p>How to price by market — not by calculator — and how to manage multi-currency operations as your global subscriber base grows.</p>
      
    </div>

    <!-- Nav -->
    <details class="rc-sticky-nav-wrap" open>
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-sticky-link">
              <span class="rc-step-badge">1</span> Overview
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency-configure" class="rc-sticky-link">
              <span class="rc-step-badge">2</span> Configure
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency-strategy" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Strategy &amp; Best Practices
            </a>
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-sticky-link">
              <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Back to Path Start
            </a>
          </div>
        </div>
      </div>
    </details>

    <!-- Section 1: Localized Pricing Strategy -->
    <div class="rc-lp-section">
      <h2>🌏 Setting Prices by Market, Not by Formula</h2>
      <p>The most common mistake in multi-currency rollouts is treating pricing as a math problem — take the USD price, multiply by the exchange rate, and round. This approach produces prices that are technically accurate but strategically wrong. Pricing in a new market is a positioning decision, not a conversion calculation.</p>
      <p>A few principles that hold across most international expansion scenarios:</p>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Purchasing power parity matters more than exchange rates</h4>
        <p>A $49/month SaaS product is expensive for a customer in Brazil paying in BRL, even if the nominal BRL equivalent seems reasonable to you. Look at median software spend in the target market and benchmark against local competitors. A price that feels like good value in San Francisco may feel premium in São Paulo — not because the product is worse, but because the economic context is different. Markets like India, Brazil, Indonesia, and Eastern Europe often need prices set at 40–70% of the USD equivalent to achieve similar conversion rates.</p>
      </div>

      <div class="rc-accent-card rc-accent-yellow">
        <h4>Psychological price points vary by currency</h4>
        <p>In USD, $49 is a classic psychological price point (feels close to $40, not quite $50). In GBP, £39 or £49 work similarly. In JPY, ¥4,900 reads as a natural price. In BRL, R$249 may land better than the exact exchange rate equivalent. Take the time to look at how competitors and established SaaS companies price in each target currency — you'll quickly spot the local conventions. Recurly's manual pricing model lets you set these exactly.</p>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>Start with one or two markets, do them well</strong>
          <p>Activating 30 currencies at once creates a maintenance burden with no strategic focus. A better approach: identify your top two or three markets outside your home currency based on actual or projected subscriber volume, invest in intentional pricing research for those markets, and expand from there. Well-priced entry into one new market outperforms cursory entry into ten.</p>
        </div>
      </div>
    </div>

    <!-- Section 2: Currency + Price Segments -->
    <div class="rc-lp-section">
      <h2>🗂️ Combining Currency with Price Segments</h2>
      <p>Price segments and multi-currency are independent but complementary. Price segments let you serve different prices to different customer cohorts within the same currency — for example, different rates for channel partners, early adopters, or geographic regions within the same country. Multi-currency lets you serve those same cohorts in their local currency. Combined, they give you a powerful matrix of pricing flexibility on a single plan.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">💡</div>
        <div class="rc-callout-body">
          <strong>A practical multi-currency segment use case</strong>
          <p>You run a SaaS product sold through resellers in LATAM. Your standard EUR price in the Spanish market is €45/month. Your reseller partners in Mexico get a discounted rate of MXN$650 instead of the standard MXN$800. You can create a <code>reseller_mx</code> price segment on your plan, set it to MXN$650, and pass that segment code when creating subscriptions for reseller accounts. Standard direct-to-customer subscriptions in Mexico get MXN$800 via the default segment. One plan, two prices, one currency — plus all your other currency configurations.</p>
        </div>
      </div>

      <p>Remember the key constraint: price segments work on plans (fixed and ramp only). Add-ons, items, and setup fees have a single price per currency. If your subscription model relies heavily on add-ons for regional differentiation, you'll need separate plans rather than segments to achieve per-region add-on pricing.</p>
    </div>

    <!-- Section 3: Managing Exchange Rate Risk -->
    <div class="rc-lp-section">
      <h2>📉 Managing Exchange Rate Risk</h2>
      <p>Because Recurly's prices are set manually and subscription currencies are locked at creation, exchange rate movements don't automatically change what you charge customers. This is a feature, not a limitation — your customers have price certainty, and you have billing predictability. But it does mean you bear the exchange rate risk on your revenue side.</p>

      <div class="rc-accent-card rc-accent-orange">
        <h4>How to handle significant rate shifts</h4>
        <ul>
          <li><strong>Set prices with a buffer:</strong> When you configure a new currency price, don't set it at the current spot rate equivalent. Build in a margin that accounts for reasonable exchange rate movement over your typical contract term. If the current rate would produce €42, set €45 — the buffer protects your margin if EUR weakens.</li>
          <li><strong>Review prices periodically, not reactively:</strong> Schedule a quarterly review of your localized prices against current exchange rates. Adjust prices if the gap has become material — but don't chase every daily movement. Frequent price changes erode customer trust faster than a modest FX impact hurts your margin.</li>
          <li><strong>Communicate currency changes like any other price change:</strong> If you need to update prices in a market due to exchange rate shifts, give customers advance notice and frame it as a market pricing update, not a surprise. The same good communication practices that apply to USD price increases apply to any currency.</li>
          <li><strong>New subscriptions vs. existing:</strong> Remember that updating a plan's prices only affects new subscriptions. Existing subscribers keep the price they signed up on — in their original currency — until they change plans or you execute a migration.</li>
        </ul>
      </div>
    </div>

    <!-- Section 4: Q&A -->
    <div class="rc-lp-section">
      <h2>❓ Common Questions from Merchants</h2>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Our checkout uses geo-IP to auto-detect currency. What happens if the customer is traveling?"</h4>
            <p>Recurly's legacy hosted payment pages use geo-IP to serve the most appropriate currency for a customer's location, which can create friction for traveling customers or those using VPNs. The newer Checkout product gives you additional control over currency presentation. For API-driven integrations, you have full control over which currency is passed at subscription creation — meaning your frontend logic can make this decision. A common approach: ask the customer to confirm or select their billing currency during signup rather than relying purely on geo-detection. The currency they select at signup locks in for the life of their subscription, so getting it right upfront matters.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"We want to offer the same plan in 10 currencies. Does that mean 10x the maintenance?"</h4>
            <p>It's proportional, not exponential. Each plan needs one price per currency, and each coupon with a fixed-amount discount needs one value per currency. If you have 5 plans and 10 currencies, that's 50 price entries — a one-time setup task. Ongoing maintenance is only needed when you decide to update pricing, which should be infrequent and deliberate. The heavier lift is the initial audit and setup. Once configured, multi-currency plans behave like any other plan — subscriptions are created and managed the same way regardless of currency.</p>
          </div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num-q">Q</div>
          <div class="rc-step-content">
            <h4>"Can we run a promotion with a local-currency coupon — like a New Year's discount in Japan?"</h4>
            <p>Yes. When you create a coupon with a fixed-amount discount, you can set the discount value separately for each enabled currency. A "¥500 off first month" coupon for Japan operates entirely in JPY — no currency conversion math required from the customer or your team. Percentage-off coupons (e.g., 20% off) apply the same percentage across all currencies automatically, so they require no per-currency setup. If you run localized promotions frequently, percentage coupons are easier to manage at scale; fixed-amount coupons give you more precise control over the customer's perceived value in each market.</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Section 5: AI Strategy -->
    <div class="rc-lp-section">
      <h2>🤖 AI Strategy for Multi-Currency Pricing</h2>
      <p>Multi-currency operations surface data that, at scale, becomes a rich signal set for AI-assisted decisions. Here's where intelligence adds the most leverage.</p>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🌍</div>
        <div class="rc-callout-body">
          <strong>Identify conversion gaps by market to surface price optimization opportunities</strong>
          <p>If your conversion rate for EUR subscribers is significantly lower than for USD subscribers — holding everything else constant — that's a signal your EUR price may be too high for the market, or that your checkout experience has friction for European customers. An AI model comparing trial-to-paid conversion rates, churn rates, and LTV across currencies can surface which markets are underperforming and flag them for pricing review before the gap becomes a retention problem.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">📊</div>
        <div class="rc-callout-body">
          <strong>Use cohort data to model optimal price points per market</strong>
          <p>Once you have enough subscriber history in a given currency, you can analyze willingness-to-pay elasticity by market. A model trained on churned vs. retained subscribers at different price points can help you find the conversion-maximizing price for each currency. This is the same analysis done in USD A/B testing, applied globally — Recurly's manual pricing model means you can implement the output of that analysis with a straightforward plan price update.</p>
        </div>
      </div>

      <div class="rc-callout rc-callout-tip">
        <div class="rc-callout-icon">🔔</div>
        <div class="rc-callout-body">
          <strong>Flag when exchange rate drift has materially eroded localized pricing</strong>
          <p>If your EUR price was set when €1 = $1.05 and the rate has since moved to €1 = $0.92, the price you're charging in euros has effectively dropped in USD terms. An automated monitor that compares your current prices against the exchange rate at the time they were set — and alerts you when the drift exceeds a threshold (say, 15%) — turns reactive pricing reviews into a proactive process. This is a lightweight script or BI dashboard trigger, but it pays for itself in margin protection over a 2–3 year horizon.</p>
        </div>
      </div>
    </div>

    <!-- Thought Question -->
    <div class="rc-thought-q">
      <span class="rc-thought-q-label">💭 Something to Consider</span>
      <h3>If you showed a customer in Tokyo and a customer in Toronto the same product at the same dollar-equivalent price, would they both feel it was priced fairly for them — and does it matter if they don't?</h3>
      <p>Local currency billing isn't just a technical feature. It's a statement about whether you've built your pricing for a global audience or simply made a global audience accommodate your local defaults.</p>
    </div>

    <!-- Office Hours CTA -->
    <div class="rc-oh-cta">
      <h4>🗓️ Bring Your Global Pricing Questions to Office Hours</h4>
      <p>Multi-currency pricing decisions — which markets to enter, how to set prices, how to handle rate drift — are easier with a sounding board. Join a <strong>Customer Success Global Office Hours</strong> session and get a Recurly CSM's perspective on your specific market expansion plan.</p>
      <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-oh-btn">Register for Office Hours →</a>
    </div>

    <!-- Path nav -->
    <div class="rc-lp-nav">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency-configure" class="rc-btn-prev">← Configure</a>
      <span class="rc-lp-nav-indicator">3 of 3</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-analytics" class="rc-btn-path">Continue to Advanced Analytics →</a>
    </div>

    <!-- Resources -->
    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/currencies" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Currencies</a>
        <a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Currency Support by Gateway</a>
        <a href="https://docs.recurly.com/docs/gateway-configuration" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Multiple Gateway Configuration</a>
        <a href="https://docs.recurly.com/docs/billing-models" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Pricing Models</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <!-- Footer -->
    <div class="rc-footer-nav">
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">Advanced Currency:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency-configure" class="rc-footer-link">Configure</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency-strategy" class="rc-footer-link">Strategy &amp; Best Practices</a>
      </div>
      <div class="rc-footer-section">
        <span class="rc-footer-section-label">P&amp;P 201:</span>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201" class="rc-footer-link">P&amp;P 201 Hub</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-segmentation" class="rc-footer-link">Segmentation</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-hierarchy" class="rc-footer-link">Account Hierarchy</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-usage-billing" class="rc-footer-link">Usage Billing</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-models" class="rc-footer-link">Advanced Models</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-pricing-plans-201-advanced-currency" class="rc-footer-link">Advanced Currency</a>
      </div>
      <div class="rc-footer-utility">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt=""> Navigate Home
        </a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
