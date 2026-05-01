---
title: 'Recurly Navigate: Scale'
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
/* Smooth scrolling and offset for the sticky nav */
html { scroll-behavior: smooth; scroll-padding-top: 90px; }

.rc-guide{
  --yellow:#FFD706;
  --orange:#FF8200;
  --offblack:#0D0D0B;
  --darkgray:#32312D;
  --gray:#807D73;
  --lightgray:#CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:#FFFDF2;
  --scale:#ff5810; /* Specific Scale Pillar Color */
  font-family:'Segoe UI',system-ui,sans-serif;
}
*{box-sizing:border-box}
body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray);background-color:#fff;}

/* TOP BACK NAVIGATION */
.rc-top-nav{padding:20px 40px 16px; margin-bottom: 8px; max-width: 1200px; margin: 0 auto;}
.rc-back-link{color:var(--gray);text-decoration:none;font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;transition:color .2s;}
.rc-back-link:hover{color:var(--orange);}

/* CONTENT WRAPPER */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* PILLAR HERO */
.rc-hero{
  background: linear-gradient(rgba(13, 13, 11, 0.8), rgba(13, 13, 11, 0.8)), 
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover; 
  color:#fff;
  padding:48px 40px 56px;
  text-align:center;
  border-radius:16px;
  margin-bottom:0; 
}

.rc-brand-header {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  margin-bottom: 30px; 
}
.rc-logo-image {
  height: 40px; 
  width: auto;
}

/* Floating icon styles */
.rc-pillar-hero-icon {
  width: 72px;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 24px;
}
.rc-pillar-hero-icon img {
  width: 48px;
  height: 48px;
  object-fit: contain;
}

.rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 16px;color:var(--offwhite)}
.rc-hero>p{font-size:1.1rem;opacity:.9;max-width:700px;margin:0 auto 0;color:var(--lightgray);line-height:1.6}

/* STICKY CATEGORY NAVIGATION (Scale Color) */
.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--scale); 
  box-shadow: 0 4px 12px rgba(0,0,0,0.08); 
  margin: 24px 0 48px 0;
  border-radius: 12px;
}
.rc-sticky-nav {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 40px; 
  padding: 18px 24px;
  overflow-x: auto;
  white-space: nowrap;
}
.rc-sticky-link {
  color: white; /* Swapped to white for better contrast on dark orange */
  text-decoration: none;
  font-weight: 800; 
  font-size: .95rem;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  position: relative;
  transition: opacity .2s;
}
.rc-sticky-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -4px;
  left: 50%;
  background-color: white;
  transition: all 0.2s ease-in-out;
  transform: translateX(-50%);
}
.rc-sticky-link:hover::after {
  width: 100%;
}
.rc-sticky-link:hover {
  opacity: 0.8;
}

/* CATEGORY SECTIONS */
.rc-category {
  margin-bottom: 56px;
}
.rc-category h2 {
  font-size: 1.6rem;
  font-weight: 800;
  margin: 0 0 24px;
  color: var(--offblack);
  display: flex;
  align-items: center;
  gap: 12px;
}
.rc-category h2::after {
  content: "";
  flex-grow: 1;
  height: 1px;
  background: var(--lightgray);
}

/* COMPACT HORIZONTAL CARDS */
.rc-path-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.rc-path-card{
  background:var(--offwhite);
  border:1px solid var(--lightgray);
  border-radius:12px;
  padding:20px 24px;
  text-decoration:none !important;
  color:inherit;
  transition:all .2s ease;
  display:grid;
  grid-template-columns: auto 1fr auto; 
  gap: 24px;
  align-items: center;
}
.rc-path-card:hover{
  border-color:var(--scale); 
  box-shadow:0 4px 16px rgba(255, 88, 16, 0.15);
  transform:translateY(-2px);
  text-decoration:none !important;
}
.rc-path-icon{
  width:48px;
  height:48px;
  border-radius:10px;
  display:flex;
  align-items:center;
  justify-content:center;
  background:var(--brightgray);
  border:1px solid rgba(0,0,0,0.05);
  flex-shrink: 0;
}
.rc-path-icon img{
  width:24px;
  height:24px;
  object-fit:contain;
}
.rc-path-content {
  min-width: 0; 
}
.rc-path-content h3{
  font-size:1.1rem;
  font-weight:800;
  margin:0 0 6px;
  color:var(--offblack);
  text-decoration:none !important;
}
.rc-path-content p{
  font-size:.92rem;
  color:var(--gray);
  line-height:1.5;
  margin:0;
  text-decoration:none !important;
}
.rc-path-arrow{
  color:var(--orange);
  font-weight:700;
  font-size:.9rem;
  text-decoration:none !important;
  white-space: nowrap;
}

/* GETTING STARTED CTA */
.rc-starter-cta{background:var(--brightgray);border:1px solid var(--lightgray);border-radius:16px;padding:24px 32px;display:flex;align-items:center;justify-content:space-between;gap:24px;margin-bottom:56px;}
.rc-starter-text h3{margin:0 0 6px;font-size:1.2rem;font-weight:800;color:var(--offblack);}
.rc-starter-text p{margin:0;font-size:.95rem;color:var(--darkgray);line-height:1.5;}
.rc-btn-secondary{background:transparent;color:var(--offblack);text-decoration:none;padding:10px 24px;border-radius:10px;font-weight:700;font-size:.9rem;border:2px solid var(--offblack);white-space:nowrap;transition:all .2s;}
.rc-btn-secondary:hover{background:var(--offblack);color:var(--yellow);}

/* BOTTOM NAVIGATION */
.rc-footer-nav{border-top:1px solid var(--lightgray);padding-top:32px;margin-top:20px;text-align:center;}
.rc-footer-title{font-size:.85rem;font-weight:700;text-transform:uppercase;letter-spacing:1px;color:var(--gray);margin-bottom:16px;}
.rc-footer-links{display:flex;flex-wrap:wrap;gap:12px;justify-content:center;}
.rc-footer-link{color:var(--darkgray);text-decoration:none;font-weight:700;font-size:.9rem;padding:8px 20px;background:var(--brightgray);border-radius:8px;transition:all .2s;}
.rc-footer-link:hover{background:var(--offblack);color:var(--yellow);}

/* FOOTER SUMMARY */
.rc-footer-summary{margin-top:40px;padding-top:32px;border-top:1px solid var(--lightgray);text-align:center;color:var(--gray);font-size:.95rem;line-height:1.6;max-width:800px;margin-left:auto;margin-right:auto;margin-bottom:24px;}
.rc-footer-summary strong{color:var(--darkgray);}
.rc-footer-summary a{color:var(--orange);text-decoration:none;font-weight:700;}
.rc-footer-summary a:hover{text-decoration:underline;}

/* RESPONSIVE */
@media(max-width:768px){
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; text-align: left; }
  .rc-path-icon { margin-bottom: 0; }
  .rc-path-arrow { margin-top: 8px; }
  .rc-hero { padding: 36px 20px 40px; }
  .rc-content-wrap { padding: 0 20px; }
  .rc-starter-cta{flex-direction:column;align-items:flex-start;}
}
@media(max-width:640px){
  .rc-sticky-nav { justify-content: flex-start; gap: 24px; }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="index.html" class="rc-back-link">← Back to Navigate Hub</a>
  </div>

  <div class="rc-content-wrap">
    
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

    <div class="rc-sticky-nav-wrap">
      <div class="rc-sticky-nav">
        <a href="#analytics" class="rc-sticky-link">Analytics</a>
        <a href="#expansion" class="rc-sticky-link">Global Expansion</a>
        <a href="#optimization" class="rc-sticky-link">Optimization</a>
      </div>
    </div>

    <div id="analytics" class="rc-category">
      <h2>Advanced Analytics & Reporting</h2>
      <div class="rc-path-list">
        
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Reporting Benchmarks</h3>
            <p>See how your subscription business stacks up. Learn how to interpret industry benchmarks for churn, LTV, and growth against your peers.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Reporting Churn</h3>
            <p>Master the Churn Analysis dashboard. Understand the difference between net and gross churn and how to identify retention trends.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Reporting Payments Hub</h3>
            <p>Optimize your gateway performance. Use the Payments Hub to track transaction success rates and decline reasons across all methods.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Data Exports & Acquisition Data</h3>
            <p>Take your data to go. Learn how to leverage Recurly's robust data exports and acquisition data to power your internal BI tools.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div id="expansion" class="rc-category">
      <h2>Global Expansion</h2>
      <div class="rc-path-list">
        
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Currency & Localization</h3>
            <p>Go global with ease. Configure multi-currency support and localize your checkout experience to meet international customer expectations.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Local Payment Methods</h3>
            <p>Offer the methods your customers prefer. Learn how to enable and manage alternative payment methods (APMs) globally.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Tax & Compliance</h3>
            <p>Simplify complex tax requirements. Learn how Recurly automates tax calculation and collection across different jurisdictions.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Account Hierarchies</h3>
            <p>Manage complex B2B relationships. Organize accounts into parent-child hierarchies to handle consolidated billing and department-level management.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div id="optimization" class="rc-category">
      <h2>Revenue Optimization & Security</h2>
      <div class="rc-path-list">

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Fraud & Chargeback Management</h3>
            <p>Protect your revenue. Implement advanced fraud prevention rules and learn best practices for managing and disputing chargebacks.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Revenue Recognition</h3>
            <p>Automate your month-end. Learn how Recurly manages deferred revenue and streamlines your accounting workflows.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Icon" style="opacity: 0.6;" />
          </div>
          <div class="rc-path-content">
            <h3>App Management & Integrations</h3>
            <p>Connect your stack. Learn how to manage third-party app integrations and scale your technical ecosystem with the Recurly API.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>

      </div>
    </div>

    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 Need live guidance on scaling your business?</h3>
        <p>Bring your expansion and data questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank">Register for Office Hours</a>
    </div>

    <div class="rc-footer-summary">
      <h3><strong>Maximizing your subscription potential.</strong></h3>
      <br>
      <p>Navigate is designed to put Recurly’s strategic insights directly in your hands, ensuring you have the resources needed to drive revenue and scale efficiently. Have questions about the program? Reach out to <a href="mailto:support@recurly.com">support@recurly.com</a>.</p>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-title">Jump to a section</div>
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" class="rc-footer-link">Acquire</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" class="rc-footer-link">Scale</a>
        <a href="https://navigate.recurly.com/event-hub/" class="rc-footer-link" target="_blank">Events</a>
        <a href="https://navigate.recurly.com/global-office-hours/" class="rc-footer-link" target="_blank">Office Hours</a>
      </div>
    </div>

  </div> </div>
</body>
</html>
`}</HTMLBlock>

<br />
