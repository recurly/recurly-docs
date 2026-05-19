---
title: 'Navigate Code Testing: SCALE (SubPillar)'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scale — Recurly Navigate</title>
<style>
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  --scale: #FF5810;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  background: var(--yellow);
  color: var(--offblack);
  display: flex;
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
.rc-brand-header { display: flex; align-items: center; justify-content: center; gap: 16px; margin-bottom: 30px; }
.rc-logo-image { height: 40px; width: auto; }
.rc-pillar-hero-icon { width: 72px; height: 72px; display: flex; align-items: center; justify-content: center; margin: 0 auto 24px; }
.rc-pillar-hero-icon img { width: 48px; height: 48px; object-fit: contain; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 16px; color: var(--offwhite); }
.rc-hero > p { font-size: 1.1rem; opacity: .9; max-width: 700px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* ── NAVIGATE QUICK LINKS NAV — Scale accent: Vermillion (#FF5810) ── */
details.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--scale);
  box-shadow: 0 4px 12px rgba(0,0,0,0.10);
  margin: 24px 0 48px 0;
  border-radius: 12px;
  border: 1px solid rgba(0,0,0,0.10);
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
  color: #fff;
}
.rc-nav-chevron {
  font-size: .72rem;
  color: #fff;
  opacity: 0.75;
  line-height: 1;
  transition: transform 0.25s ease;
}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }

.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner {
  overflow: hidden;
  border-top: 1px solid rgba(255,255,255,0.25);
}
.rc-nav-links {
  display: flex;
  flex-wrap: wrap;
  gap: 6px 4px;
  padding: 12px 20px 18px;
}
.rc-sticky-link {
  color: #fff !important;
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
.rc-sticky-link:hover { background: rgba(0,0,0,0.20); color: #fff !important; text-decoration: none !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; filter: brightness(0) invert(1); }

/* ── CATEGORY SECTIONS ── */
.rc-category { margin-bottom: 56px; }
.rc-category h2 {
  font-size: 1.6rem; font-weight: 800; margin: 0 0 24px; color: var(--offblack);
  display: flex; align-items: center; gap: 12px;
}
.rc-category h2::after { content: ""; flex-grow: 1; height: 1px; background: var(--lightgray); }

/* ── LEARNING PATH CARDS ── */
.rc-path-list { display: flex; flex-direction: column; gap: 16px; }
.rc-path-card {
  background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px;
  padding: 20px 24px; text-decoration: none !important; color: inherit;
  transition: all .2s ease; display: grid; grid-template-columns: auto 1fr auto; gap: 24px; align-items: center;
}
.rc-path-card:hover { border-color: var(--scale); box-shadow: 0 4px 16px rgba(255,88,16,.15); transform: translateY(-2px); text-decoration: none !important; }
.rc-path-icon { width: 48px; height: 48px; border-radius: 10px; display: flex; align-items: center; justify-content: center; background: var(--brightgray); border: 1px solid rgba(0,0,0,0.05); flex-shrink: 0; }
.rc-path-icon img { width: 24px; height: 24px; object-fit: contain; }
.rc-path-content { min-width: 0; }
.rc-path-content h3 { font-size: 1.1rem; font-weight: 800; margin: 0 0 6px; color: var(--offblack); text-decoration: none !important; }
.rc-path-content p { font-size: .92rem; color: var(--gray); line-height: 1.5; margin: 0; text-decoration: none !important; }
.rc-path-arrow { color: var(--orange); font-weight: 700; font-size: .9rem; text-decoration: none !important; white-space: nowrap; }

/* ── BOTTOM CTA ── */
.rc-starter-cta { background: var(--brightgray); border: 1px solid var(--lightgray); border-radius: 16px; padding: 24px 32px; display: flex; align-items: center; justify-content: space-between; gap: 24px; margin-bottom: 56px; }
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); }
.rc-starter-text p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
.rc-btn-secondary { background: transparent; color: var(--offblack); text-decoration: none !important; padding: 10px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--offblack); white-space: nowrap; transition: all .2s; }
.rc-btn-secondary:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── FOOTER NAV — matches home page style exactly ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 20px; text-align: center; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 24px; justify-content: center; align-items: center; }
.rc-footer-link {
  color: var(--gray);
  text-decoration: none !important;
  font-weight: 600;
  font-size: .9rem;
  transition: color .2s;
  display: inline-flex;
  align-items: center;
  gap: 5px;
}
.rc-footer-link:hover { color: var(--offblack); }
.rc-footer-link img { width: 13px; height: 13px; object-fit: contain; opacity: 0.55; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; }
  .rc-path-arrow { margin-top: 4px; }
  .rc-hero { padding: 36px 20px 40px; }
  .rc-content-wrap { padding: 0 20px; }
  .rc-starter-cta { flex-direction: column; align-items: flex-start; }
  .rc-announce-bar { flex-direction: column; align-items: flex-start; gap: 8px; }
  .rc-top-nav { padding: 16px 20px; }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Navigate Hub</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>This Thursday:</strong> Global Office Hours — Dunning windows &amp; payment recovery with our lead CSMs.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO ── -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
      </div>
      <div class="rc-pillar-hero-icon">
        <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Scale" />
      </div>
      <h1>Scale</h1>
      <p>Expand your business, launch new products, and optimize global payments and analytics with advanced insights and enterprise-grade security.</p>
    </div>

    <!-- ── NAVIGATE QUICK LINKS NAV ── -->
    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">
          Navigate Quick Links
          <span class="rc-nav-chevron">▲</span>
        </span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
            </a>
            <a href="#analytics" class="rc-sticky-link">Analytics &amp; Reporting</a>
            <a href="#expansion" class="rc-sticky-link">Global Expansion</a>
            <a href="#optimization" class="rc-sticky-link">Revenue Optimization</a>
          </div>
        </div>
      </div>
    </details>

    <!-- ── ADVANCED ANALYTICS & REPORTING ── -->
    <div id="analytics" class="rc-category">
      <h2>Advanced Analytics &amp; Reporting</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Benchmarks</h3>
            <p>See how your subscription business stacks up. Learn how to interpret industry benchmarks for churn, LTV, and growth against your peers.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Churn Reporting</h3>
            <p>Master the Churn Analysis dashboard. Understand the difference between net and gross churn and how to identify retention trends.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Payments Hub</h3>
            <p>Optimize your gateway performance. Use the Payments Hub to track transaction success rates and decline reasons across all methods.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Data Exports &amp; Acquisition Data</h3>
            <p>Take your data to go. Learn how to leverage Recurly's robust data exports and acquisition data to power your internal BI tools.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── GLOBAL EXPANSION ── -->
    <div id="expansion" class="rc-category">
      <h2>Global Expansion</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Currency &amp; Localization</h3>
            <p>Go global with ease. Configure multi-currency support and localize your checkout experience to meet international customer expectations.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Local Payment Methods</h3>
            <p>Offer the methods your customers prefer. Learn how to enable and manage alternative payment methods (APMs) globally.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Tax &amp; Compliance</h3>
            <p>Simplify complex tax requirements. Learn how Recurly automates tax calculation and collection across different jurisdictions.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Account Hierarchies</h3>
            <p>Manage complex B2B relationships. Organize accounts into parent-child hierarchies to handle consolidated billing and department-level management.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── REVENUE OPTIMIZATION & SECURITY ── -->
    <div id="optimization" class="rc-category">
      <h2>Revenue Optimization &amp; Security</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Fraud &amp; Chargeback Management</h3>
            <p>Protect your revenue. Implement advanced fraud prevention rules and learn best practices for managing and disputing chargebacks.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>Revenue Recognition</h3>
            <p>Automate your month-end. Learn how Recurly manages deferred revenue and streamlines your accounting workflows.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/7038a0b3a299cfe800553d4c8a6721f92b1fc7e031ef697861d3603fb1bb5a05-Scale-icon-white.png" alt="Icon" style="opacity:.5;" />
          </div>
          <div class="rc-path-content">
            <h3>App Management &amp; Integrations</h3>
            <p>Connect your stack. Learn how to manage third-party app integrations and scale your technical ecosystem with the Recurly API.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── BOTTOM CTA ── -->
    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 Need live guidance on scaling your business?</h3>
        <p>Bring your expansion and data questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank">Register for Office Hours</a>
    </div>

    <!-- ── FOOTER NAV — matches home page style, all items linked ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Home
        </a>
        <a href="#analytics" class="rc-footer-link">Analytics &amp; Reporting</a>
        <a href="#expansion" class="rc-footer-link">Global Expansion</a>
        <a href="#optimization" class="rc-footer-link">Revenue Optimization</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />