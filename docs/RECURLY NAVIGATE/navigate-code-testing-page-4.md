---
title: 'Navigate Code Testing Page: RETAIN (SubPillar)'
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
  --retain:    #FF9D88;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── HOST-THEME ARMOR ── */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* ── ANNOUNCEMENT BAR — hidden by default ── */
.rc-announce-bar {
  background: var(--yellow);
  color: var(--offblack);
  display: none;
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
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
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
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── PILLAR HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.8), rgba(13,13,11,0.8)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover;
  color: #fff;
  padding: 48px 40px 56px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
}
.rc-brand-header { display: flex; align-items: center; justify-content: center; gap: 16px; margin-bottom: 28px; }
.rc-logo-image { height: 40px; width: auto; }
.rc-pillar-hero-icon { width: 64px; height: 64px; object-fit: contain; display: block; margin: 0 auto 24px; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 16px; color: var(--offwhite); }
.rc-hero > p { font-size: 1.1rem; opacity: .9; max-width: 700px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* ── STICKY NAV — Retain salmon bg ── */
details.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--retain);
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
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }

/* ── CATEGORY SECTIONS ── */
.rc-category { margin-bottom: 56px; }
.rc-category h2 {
  font-size: 1.5rem; font-weight: 800; margin: 0 0 24px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-category h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }

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
/* Armor override — explicit border-bottom on base and hover states */
.rc-guide a.rc-path-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-path-card:hover {
  border-color: var(--retain);
  border-bottom: 1px solid var(--retain) !important;
  box-shadow: 0 4px 16px rgba(255,157,136,.2);
  transform: translateY(-2px);
}
.rc-path-icon { width: 48px; height: 48px; border-radius: 10px; display: flex; align-items: center; justify-content: center; background: var(--brightgray); border: 1px solid rgba(0,0,0,0.05); flex-shrink: 0; }
.rc-path-icon img { width: 24px; height: 24px; object-fit: contain; }
.rc-path-content { min-width: 0; }
.rc-path-content h3 { font-size: 1.1rem; font-weight: 800; margin: 0 0 6px; color: var(--offblack); }
.rc-path-content p { font-size: .92rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-path-arrow { color: var(--orange); font-weight: 700; font-size: .9rem; white-space: nowrap; }

/* ── OFFICE HOURS CTA ── */
.rc-starter-cta { background: var(--brightgray); border: 1px solid var(--lightgray); border-radius: 16px; padding: 24px 32px; display: flex; align-items: center; justify-content: space-between; gap: 24px; margin-bottom: 56px; }
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); }
.rc-starter-text p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
/* Armor-safe selector pattern for secondary button */
.rc-guide a.rc-btn-secondary {
  display: inline-flex; align-items: center; gap: 8px;
  background: transparent; color: var(--offblack) !important;
  text-decoration: none !important;
  padding: 11px 22px; border-radius: 10px;
  font-weight: 700; font-size: .9rem;
  border: 2px solid var(--offblack);
  border-bottom: 2px solid var(--offblack) !important;
  white-space: nowrap; transition: all .2s;
}
.rc-guide a.rc-btn-secondary:hover {
  background: var(--offblack);
  color: var(--yellow) !important;
  border: 2px solid var(--offblack) !important;
  border-bottom: 2px solid var(--offblack) !important;
}

/* ── FOOTER NAV — grouped sections ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; }
  .rc-path-arrow { margin-top: 4px; }
  .rc-starter-cta { flex-direction: column; align-items: flex-start; }
  .rc-announce-bar.rc-active { flex-direction: column; align-items: flex-start; gap: 8px; }
}
</style>

<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Home</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR — hidden by default, add rc-active to show ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>This Thursday:</strong> Global Office Hours — Dunning windows &amp; payment recovery with our lead CSMs.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO — pillar subpage: logo + pillar icon + h1 + subtitle, no stats ── -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly Navigate" class="rc-logo-image">
      </div>
      <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain icon" class="rc-pillar-hero-icon">
      <h1>Retain</h1>
      <p>Reduce involuntary churn, recover revenue, and keep subscribers engaged with intelligent tools that protect your bottom line.</p>
    </div>

    <!-- ── STICKY NAV — collapsed, section anchors ── -->
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
            <a href="#involuntary" class="rc-sticky-link">Involuntary Churn</a>
            <a href="#voluntary" class="rc-sticky-link">Voluntary Churn</a>
            <a href="#communication" class="rc-sticky-link">Communication</a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── INVOLUNTARY CHURN ── -->
    <div id="involuntary" class="rc-category">
      <h2>Involuntary Churn Management</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Dunning 101</h3>
            <p>Master Recurly's core revenue recovery tool. Learn how to configure custom dunning cycles and emails to effectively capture failed payments.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Account Updater</h3>
            <p>Automatically refresh expired or replaced credit cards before they fail. Discover how Account Updater drastically reduces passive churn.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Intelligent Retries</h3>
            <p>Go beyond basic dunning by leveraging machine learning to retry transactions at the exact moment they are most likely to succeed.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Backup Payment Methods</h3>
            <p>Ensure continuous service by capturing and falling back on secondary payment methods when a primary transaction fails.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── VOLUNTARY CHURN ── -->
    <div id="voluntary" class="rc-category">
      <h2>Voluntary Churn &amp; Lifecycle</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Pause Subscriptions</h3>
            <p>Give your customers flexibility. Learn how to let subscribers easily pause their billing instead of outright canceling their accounts.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Cancel Save &amp; Offers</h3>
            <p>Intercept cancellations with targeted, personalized discount offers and down-sell options directly within the offboarding flow.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Customer Self-Service</h3>
            <p>Empower your subscribers to update payment details, manage their plans, and view invoices without contacting your support team.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── COMMUNICATION ── -->
    <div id="communication" class="rc-category">
      <h2>Communication &amp; Experience</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Payment Banners</h3>
            <p>Keep users informed without disruption. Implement native application banners to alert customers of failing cards or upcoming renewals.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/2d6b0dfecebc907c932c4a7a27f8d76daeb9f8ff7ba76f775e1878a15c658e69-Retain-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Invoice Sequences &amp; Proration</h3>
            <p>Optimize your billing communications. Ensure clarity around upgrades, downgrades, and proration to prevent chargebacks and disputes.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── OFFICE HOURS CTA ── -->
    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 Need live guidance on your retention strategy?</h3>
        <p>Bring your churn data and configuration questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank" rel="noopener noreferrer">Register for Office Hours</a>
    </div>

    <!-- ── FOOTER NAV — pillar subpage: one section with on-page anchors + utility row ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">

        <div class="rc-footer-section">
          <span class="rc-footer-label">Retain</span>
          <a href="#involuntary" class="rc-footer-link">Involuntary Churn</a>
          <a href="#voluntary" class="rc-footer-link">Voluntary Churn</a>
          <a href="#communication" class="rc-footer-link">Communication</a>
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
