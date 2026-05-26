---
title: 'Recurly Navigate: Acquire'
excerpt: >-
  Master the subscription acquisition lifecycle. Learn to optimize checkout
  conversion using Recurly.js and Hosted Payment Pages, manage complex promotion
  logic with coupons and gift cards, and scale globally with multi-currency
  support. This Navigate pillar provides the technical framework for building
  high-conversion, PCI-compliant subscriber onboarding flows designed for
  Product-Led Growth.
deprecated: false
hidden: true
metadata:
  description: >-
    Master the subscription acquisition lifecycle. Learn to optimize checkout
    conversion using Recurly.js and Hosted Payment Pages, manage complex
    promotion logic with coupons and gift cards, and scale globally with
    multi-currency support. This Navigate pillar provides the technical
    framework for building high-conversion, PCI-compliant subscriber onboarding
    flows designed for Product-Led Growth.
  keywords:
    - Subscription acquisition strategy
    - checkout conversion optimization
    - Recurly.js integration
    - automated trial management
    - recurring billing promotions
    - hosted payment pages
    - subscription plan modeling
    - localized checkout experiences
    - PCI-compliant payment flows
    - multi-currency subscription billing
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* ── HOST-THEME BACKGROUND OVERRIDE ── */
body { background: #ffffff !important; }

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:     #FFD706;
  --orange:     #FF8200;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D73;
  --lightgray:  #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite:   #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
  background: #ffffff;
}
.rc-guide * { box-sizing: border-box; }

/* ── HOST-THEME ARMOR ── */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* ── FONT AWESOME ICON HELPERS ── */
.rc-fa-announce { color: var(--offblack); font-size: 1rem; flex-shrink: 0; }
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: var(--offblack); font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: var(--offblack); font-size: 1rem; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  display: none;
  background: var(--yellow);
  color: var(--offblack);
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  font-size: .88rem;
  font-weight: 600;
  border-radius: 10px;
  margin-bottom: 16px;
  gap: 12px;
  line-height: 1.4;
}
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 10px; flex: 1; flex-wrap: wrap; }
.rc-announce-link {
  color: var(--offblack) !important;
  font-weight: 800;
  text-decoration: none !important;
  white-space: nowrap;
  padding: 4px 12px;
  background: rgba(0,0,0,0.10);
  border-radius: 6px;
  transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close {
  background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer;
  color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── TOP BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link {
  color: var(--gray);
  text-decoration: none !important;
  font-weight: 700;
  font-size: .9rem;
  display: inline-flex;
  align-items: center;
  gap: 6px;
  transition: color .2s;
}
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── PILLAR HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover;
  color: #fff;
  padding: 48px 40px 44px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
}
.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; }
.rc-logo-image { height: 28px; display: block; }
.rc-pillar-hero-icon { width: 64px; height: 64px; object-fit: contain; display: block; margin: 44px auto 20px; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 24px; color: var(--offwhite); }
.rc-hero > p { font-size: 1.1rem; opacity: .9; max-width: 700px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* ── STICKY NAV — Acquire: yellow background ── */
details.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.08);
  overflow: hidden;
}
details.rc-sticky-nav-wrap > summary {
  list-style: none;
  display: flex;
  align-items: center;
  padding: 15px 24px;
  cursor: pointer;
  user-select: none;
}
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }

.rc-nav-toggle-label {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-weight: 800;
  font-size: .88rem;
  letter-spacing: 0.6px;
  text-transform: uppercase;
  color: var(--offblack);
}
.rc-nav-chevron {
  font-size: .72rem;
  color: var(--offblack);
  opacity: 0.55;
  line-height: 1;
  transition: transform 0.25s ease;
}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }

.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }
.rc-sticky-link {
  color: var(--offblack) !important;
  text-decoration: none !important;
  font-weight: 700;
  font-size: .83rem;
  letter-spacing: 0.4px;
  text-transform: uppercase;
  padding: 7px 14px;
  border-radius: 7px;
  transition: all .18s;
  white-space: nowrap;
  display: inline-flex;
  align-items: center;
  gap: 6px;
}
.rc-sticky-link:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link-active { font-weight: 800; }
.rc-sticky-link-active:hover { background: rgba(0,0,0,0.10); color: var(--offblack) !important; }

/* ── CONTENT SECTIONS ── */
.rc-lp-section { margin-bottom: 48px; }
.rc-lp-section h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 20px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-lp-section h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }
.rc-lp-section p { font-size: .95rem; line-height: 1.65; color: var(--darkgray); margin: 0 0 16px; }

/* ── LEARNING PATH CARDS ── */
.rc-path-list { display: flex; flex-direction: column; gap: 16px; }
.rc-path-card {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 12px;
  padding: 20px 24px;
  text-decoration: none !important;
  color: inherit;
  transition: all .2s ease;
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 24px;
  align-items: center;
}
.rc-guide a.rc-path-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-path-card:hover { border-color: var(--yellow); box-shadow: 0 4px 16px rgba(255,215,6,.12); transform: translateY(-2px); }
.rc-guide a.rc-path-card:hover { border-bottom: 1px solid var(--yellow) !important; }
.rc-path-icon {
  width: 48px; height: 48px; border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  background: var(--brightgray); border: 1px solid rgba(0,0,0,0.05); flex-shrink: 0;
}
.rc-path-icon img { width: 24px; height: 24px; object-fit: contain; }
.rc-path-content { min-width: 0; }
.rc-path-content h3 { font-size: 1.1rem; font-weight: 800; margin: 0 0 6px; color: var(--offblack); }
.rc-path-content p { font-size: .92rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-path-arrow { color: var(--orange); font-weight: 700; font-size: .9rem; white-space: nowrap; }

/* ── BOTTOM CTA ── */
.rc-starter-cta {
  background: var(--brightgray);
  border: 1px solid var(--lightgray);
  border-radius: 16px;
  padding: 24px 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
  margin-bottom: 56px;
}
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); display: flex; align-items: center; gap: 10px; }
.rc-starter-text p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
.rc-guide a.rc-btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  color: var(--offblack) !important;
  text-decoration: none !important;
  padding: 11px 22px;
  border-radius: 10px;
  font-weight: 700;
  font-size: .9rem;
  border: 2px solid var(--offblack);
  border-bottom: 2px solid var(--offblack) !important;
  white-space: nowrap;
  transition: all .2s;
}
.rc-guide a.rc-btn-secondary:hover {
  background: var(--offblack) !important;
  color: var(--yellow) !important;
  border: 2px solid var(--offblack) !important;
  border-bottom: 2px solid var(--offblack) !important;
}

/* ── FOOTER NAV — grouped sections ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label {
  font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px;
  color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px;
}
.rc-footer-link {
  color: var(--gray);
  text-decoration: none !important;
  font-weight: 600;
  font-size: .88rem;
  transition: color .2s ease;
  display: inline-flex;
  align-items: center;
  gap: 6px;
}
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility {
  display: flex; flex-wrap: wrap; gap: 24px;
  margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray);
}

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-hero h1 { font-size: 1.8rem; }
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; }
  .rc-path-arrow { margin-top: 4px; }
  .rc-starter-cta { flex-direction: column; align-items: flex-start; }
  .rc-starter-text h3 { flex-wrap: wrap; }
  .rc-announce-bar { flex-direction: column; align-items: flex-start; gap: 8px; }
}
</style>

<div class="rc-guide">

  <!-- ── BACK LINK ── -->
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Home</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR (hidden by default — no rc-active class) ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        <i class="fa-regular fa-calendar-days rc-fa-announce"></i>
        <strong>This Thursday:</strong> Global Office Hours — Dunning windows &amp; payment recovery with our lead CSMs.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO (pillar subpage — no stats) ── -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly">
      </div>
      <img class="rc-pillar-hero-icon" src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire icon">
      <h1>Acquire</h1>
      <p>Convert more customers, optimize sign-ups, and sustainably grow your subscriber base by leveraging Recurly's powerful acquisition tools.</p>
    </div>

    <!-- ── NAVIGATION MENU (sticky, collapsed) ── -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
            </a>
            <a href="#plans" class="rc-sticky-link">Plans &amp; pricing</a>
            <a href="#incentives" class="rc-sticky-link">Incentives</a>
            <a href="#gifting" class="rc-sticky-link">Gifting &amp; expansion</a>
            <a href="#payments" class="rc-sticky-link">Payments</a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── PLANS & PRICING ── -->
    <div id="plans" class="rc-lp-section">
      <h2><i class="fa-solid fa-sliders rc-fa-section"></i> Plans &amp; pricing</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Plans icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Plans</h3>
            <p>Learn how to seamlessly structure and configure your core subscription plans to attract and convert your target audience.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Pricing models icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Pricing models: tiers vs ramp</h3>
            <p>Explore advanced pricing strategies, including tiered models and ramp pricing, to maximize early conversions and lifetime value.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Plan flexibility icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Plan flexibility</h3>
            <p>Understand how to offer flexible plan options, allowing subscribers to pause, seamlessly upgrade, or alter their cadence.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
      </div>
    </div>

    <!-- ── INCENTIVES ── -->
    <div id="incentives" class="rc-lp-section">
      <h2><i class="fa-solid fa-tag rc-fa-section"></i> Incentives</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Trials icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Trials</h3>
            <p>Set up and optimize free trials to lower the barrier to entry and effectively turn curious prospects into paying subscribers.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Coupons icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Coupons</h3>
            <p>Create targeted coupon campaigns to drive flash promotions, reward loyalty, and incentivize new sign-ups during key seasons.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
      </div>
    </div>

    <!-- ── GIFTING & EXPANSION ── -->
    <div id="gifting" class="rc-lp-section">
      <h2><i class="fa-solid fa-gift rc-fa-section"></i> Gifting &amp; expansion</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Gift cards icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Gift cards</h3>
            <p>Leverage gift cards as a powerful secondary acquisition channel to reach entirely new audiences and drive immediate prepaid revenue.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Gift subscriptions icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Gift subscriptions</h3>
            <p>Enable gift subscriptions so your biggest brand advocates can easily purchase and share your service with friends and family.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
      </div>
    </div>

    <!-- ── PAYMENTS ── -->
    <div id="payments" class="rc-lp-section">
      <h2><i class="fa-solid fa-credit-card rc-fa-section"></i> Payments</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/35c0068f04fa0b50334daeeffa3213ef486e96a2a9d628d5057127bb7786d541-Acquire-icon-black.png" alt="Payments icon" style="opacity:.6;">
          </div>
          <div class="rc-path-content">
            <h3>Payments for acquisition</h3>
            <p>Optimize your checkout experience and payment gateway configurations to reduce friction and boost your overall conversion rates.</p>
          </div>
          <div class="rc-path-arrow">Start path →</div>
        </a>
      </div>
    </div>

    <!-- ── BOTTOM CTA ── -->
    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3><i class="fa-solid fa-headset rc-fa-light"></i>Need live guidance on your acquisition strategy?</h3>
        <p>Bring your configuration and growth questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank" rel="noopener noreferrer">Register for Office Hours</a>
    </div>

    <!-- ── FOOTER NAV — grouped sections ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Acquire</span>
          <a href="#plans" class="rc-footer-link">Plans &amp; pricing</a>
          <a href="#incentives" class="rc-footer-link">Incentives</a>
          <a href="#gifting" class="rc-footer-link">Gifting &amp; expansion</a>
          <a href="#payments" class="rc-footer-link">Payments</a>
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
