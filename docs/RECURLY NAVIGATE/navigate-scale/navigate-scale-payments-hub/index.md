---
title: 'Payments Hub: Getting started'
excerpt: >-
  Discover how Payments Hub centralizes your payment performance data by
  consolidating information from multiple gateways into a single, actionable
  dashboard. This guide explains how to access the hub within Recurly Analytics
  and provides a roadmap for the full learning path.
deprecated: false
hidden: false
metadata:
  keywords:
    - Payment performance analytics
    - Centralized payment data
    - Recurly Analytics dashboard
  robots: index
---
<HTMLBlock>{`
<style>
/* ═════════════════════════════════════════════════════════════════════
   NAVIGATE CSS — Payments Hub landing page
   Scoped to .rp-nav-guide. All classes use the rp-nav-* prefix.
   See Navigate-CSS.md for the canonical styleguide.
   ═════════════════════════════════════════════════════════════════════ */

/* ─── Design tokens ─────────────────────────────────────────────────── */
.rp-nav-guide {
  --yellow:#FFD706; --tangerine:#FF8200; --vermillion:#FF5810;
  --salmon:#FF9D88; --offblack:#0D0D0B; --darkgray:#32312D;
  --gray:#807D73; --lightgray:#CCC9B8; --brightgray:#F1EFE3;
  --offwhite:#FFFDF2; --deepchar:#232932; --darknavy:#343F4B;
  --font:'Plus Jakarta Sans','Segoe UI',system-ui,sans-serif;
  font-family:var(--font); color:var(--darkgray);
  scroll-behavior:smooth;
}
.rp-nav-guide *, .rp-nav-guide *::before, .rp-nav-guide *::after { box-sizing:border-box; }

/* Offset for ReadMe's fixed top nav so fragment jumps don't slide
   the target heading behind the chrome. */
.rp-nav-guide [id] { scroll-margin-top:80px; }

/* ─── Host-theme override armor ─────────────────────────────────────── */
/* ReadMe's host theme injects its own <a> rules (tangerine color,
   text-decoration, border-bottom) that bleed into the HTMLBlock.
   Reset every anchor to a neutral baseline; structural anchors below
   re-assert their own styles with !important. */
.rp-nav-guide a,
.rp-nav-guide a:link,
.rp-nav-guide a:visited,
.rp-nav-guide a:hover,
.rp-nav-guide a:active {
  border-bottom:0 !important;
  text-decoration:none !important;
}

/* ─── Hero ──────────────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-hero { background:var(--offblack); color:#fff; padding:56px 40px 48px; text-align:center; border-radius:16px; }
.rp-nav-guide .rp-nav-hero h1 { font-size:2.4rem; font-weight:800; line-height:1.15; margin:0 0 14px; color:var(--offwhite); }
.rp-nav-guide .rp-nav-hero p { font-size:1.05rem; opacity:.8; max-width:700px; margin:0 auto; color:var(--lightgray); }

/* ─── Program badge ─────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-badge { display:inline-flex; align-items:center; gap:8px; background:var(--yellow); color:var(--offblack); border-radius:20px; padding:6px 18px; font-size:13px; font-weight:700; letter-spacing:1px; text-transform:uppercase; margin-bottom:20px; }
.rp-nav-guide .rp-nav-badge img { width:16px; height:16px; display:block; object-fit:contain; }

/* ─── Guide nav (numbered stepper) ──────────────────────────────────── */
.rp-nav-guide .rp-nav-nav { display:flex; flex-wrap:wrap; gap:10px; margin:24px 0 28px; }
.rp-nav-guide .rp-nav-nav a {
  display:inline-flex; align-items:center; gap:10px;
  padding:10px 18px; border-radius:12px;
  border:1px solid var(--lightgray) !important;
  background:#fff !important;
  color:var(--darkgray) !important;
  text-decoration:none !important;
  font-size:.88rem; font-weight:700;
  transition:border-color .2s, box-shadow .2s;
}
.rp-nav-guide .rp-nav-nav a:hover {
  border-color:var(--yellow) !important;
  box-shadow:0 2px 8px rgba(255,215,6,.2);
  color:var(--offblack) !important;
}
.rp-nav-guide .rp-nav-nav a.is-active {
  background:var(--yellow) !important;
  border-color:var(--yellow) !important;
  color:var(--offblack) !important;
  box-shadow:0 2px 10px rgba(255,215,6,.25);
}
.rp-nav-guide .rp-nav-snum { display:inline-flex; align-items:center; justify-content:center; width:24px; height:24px; border-radius:50%; background:var(--offblack); color:var(--yellow); font-size:12px; font-weight:700; flex-shrink:0; }

/* ─── Section + section header ──────────────────────────────────────── */
.rp-nav-guide .rp-nav-sec { margin-bottom:56px; }
.rp-nav-guide .rp-nav-sec-header { display:flex; align-items:flex-start; gap:20px; margin-bottom:32px; }
.rp-nav-guide .rp-nav-sec-icon { width:56px; height:56px; border-radius:16px; display:flex; align-items:center; justify-content:center; font-size:26px; flex-shrink:0; background:var(--yellow); }
.rp-nav-guide .rp-nav-sec-header h2 { font-size:1.7rem; font-weight:800; margin:0 0 6px; color:var(--offblack); }
.rp-nav-guide .rp-nav-sec-header > div > p { color:var(--gray); font-size:.95rem; line-height:1.5; margin:0; }

/* ─── Heading anchor (whole-heading-is-the-link) ────────────────────── */
.rp-nav-guide .rp-nav-anchor,
.rp-nav-guide .rp-nav-anchor:link,
.rp-nav-guide .rp-nav-anchor:visited {
  color:inherit !important;
  text-decoration:none !important;
  background:transparent !important;
  border:0 !important;
  border-bottom:0 !important;
  font:inherit !important;
  cursor:pointer;
}
.rp-nav-guide .rp-nav-anchor:hover {
  color:var(--tangerine) !important;
  text-decoration:none !important;
}

/* ─── Card ──────────────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-card { background:var(--offwhite); border-radius:16px; padding:28px; border:1px solid var(--lightgray); margin-bottom:24px; }

/* ─── Subhead ───────────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-subhead { font-size:1rem; font-weight:700; margin:0 0 16px; color:var(--offblack); }

/* ─── 2-column + 3-column grids ─────────────────────────────────────── */
.rp-nav-guide .rp-nav-2col { display:grid; grid-template-columns:1fr 1fr; gap:14px; margin-bottom:24px; }
.rp-nav-guide .rp-nav-3col { display:grid; grid-template-columns:1fr 1fr 1fr; gap:14px; margin-bottom:24px; }
.rp-nav-guide .rp-nav-wi { background:var(--offwhite); border-radius:14px; padding:20px; border:1px solid var(--lightgray); }
.rp-nav-guide .rp-nav-wi.rp-nav-wi-center { text-align:center; }
.rp-nav-guide .rp-nav-wi-icon { font-size:28px; margin-bottom:10px; }
.rp-nav-guide .rp-nav-wi h4 { font-size:.9rem; font-weight:700; margin:0 0 6px; color:var(--offblack); }
.rp-nav-guide .rp-nav-wi p { font-size:.82rem; color:var(--gray); line-height:1.5; margin:0; }

/* ─── Vertical step rail ────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-steps { background:var(--offwhite); border-radius:14px; padding:28px; border:1px solid var(--lightgray); display:flex; flex-direction:column; gap:0; margin-bottom:28px; }
.rp-nav-guide .rp-nav-step { display:flex; gap:18px; align-items:flex-start; position:relative; padding-bottom:24px; }
.rp-nav-guide .rp-nav-step::after { content:""; position:absolute; left:19px; top:38px; bottom:0; width:2px; background:var(--lightgray); }
.rp-nav-guide .rp-nav-step:last-child { padding-bottom:0; }
.rp-nav-guide .rp-nav-step:last-child::after { display:none; }
.rp-nav-guide .rp-nav-sbadge { width:38px; height:38px; border-radius:10px; background:var(--offblack); color:var(--yellow); font-weight:800; font-size:15px; display:flex; align-items:center; justify-content:center; flex-shrink:0; z-index:1; }
.rp-nav-guide .rp-nav-step h3 { font-size:.98rem; font-weight:700; margin:0 0 5px; color:var(--offblack); }
.rp-nav-guide .rp-nav-step p { font-size:.87rem; color:var(--gray); line-height:1.6; margin:0; }

/* ─── Tip callout ───────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-tip { background:var(--offwhite); border:2px solid var(--yellow); border-radius:14px; padding:20px 24px; display:flex; gap:16px; align-items:flex-start; margin-bottom:24px; }
.rp-nav-guide .rp-nav-tipicon { font-size:24px; flex-shrink:0; }
.rp-nav-guide .rp-nav-tip h4 { font-size:.82rem; font-weight:700; color:var(--offblack); text-transform:uppercase; letter-spacing:.5px; margin:0 0 4px; }
.rp-nav-guide .rp-nav-tip p { font-size:.87rem; color:var(--darkgray); line-height:1.55; margin:0; }

/* ─── Warning callout ───────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-warning { background:#FFF8E6; border:1px solid var(--tangerine); border-radius:14px; padding:16px 20px; display:flex; gap:14px; align-items:flex-start; margin-bottom:24px; }
.rp-nav-guide .rp-nav-wicon { font-size:20px; flex-shrink:0; }
.rp-nav-guide .rp-nav-warning p { font-size:.87rem; color:var(--darkgray); line-height:1.55; margin:0; }

/* ─── Checklist ─────────────────────────────────────────────────────── */
.rp-nav-guide .rp-nav-checklist { background:var(--offwhite); border-radius:16px; border:1px solid var(--lightgray); overflow:hidden; margin-bottom:28px; }
.rp-nav-guide .rp-nav-cl-header { padding:16px 22px; border-bottom:1px solid var(--brightgray); display:flex; align-items:center; gap:10px; background:var(--offblack); }
.rp-nav-guide .rp-nav-cl-header h3 { font-size:.88rem; font-weight:700; text-transform:uppercase; letter-spacing:.5px; color:var(--yellow); margin:0; }
.rp-nav-guide .rp-nav-cli { padding:13px 22px; border-bottom:1px solid var(--brightgray); display:flex; align-items:flex-start; gap:14px; }
.rp-nav-guide .rp-nav-cli:last-child { border-bottom:none; }
.rp-nav-guide .rp-nav-cb { width:22px; height:22px; border-radius:6px; border:2px solid var(--lightgray); flex-shrink:0; background:#fff; }
.rp-nav-guide .rp-nav-clab { font-size:.88rem; color:var(--darkgray); line-height:1.4; }
.rp-nav-guide .rp-nav-clab span { display:block; font-size:.78rem; color:var(--gray); margin-top:2px; }

/* ─── Section pager (prev / next / disabled) ────────────────────────── */
.rp-nav-guide .rp-nav-sec-nav { display:flex; justify-content:space-between; align-items:center; gap:12px; margin-top:24px; flex-wrap:wrap; }
.rp-nav-guide .rp-nav-btn-prev,
.rp-nav-guide .rp-nav-btn-next,
.rp-nav-guide .rp-nav-btn-disabled,
.rp-nav-guide .rp-nav-link-btn {
  display:inline-flex; align-items:center; justify-content:center;
  padding:11px 18px; border-radius:10px;
  font-weight:700; font-size:.88rem;
  text-decoration:none !important;
  border-bottom:0 !important;
}
.rp-nav-guide .rp-nav-btn-prev {
  background:#fff !important;
  color:var(--darkgray) !important;
  border:1px solid var(--lightgray) !important;
}
.rp-nav-guide .rp-nav-btn-prev:hover {
  color:var(--offblack) !important;
  border-color:var(--gray) !important;
}
.rp-nav-guide .rp-nav-btn-next {
  background:var(--yellow) !important;
  color:var(--offblack) !important;
  border:1px solid var(--yellow) !important;
}
.rp-nav-guide .rp-nav-btn-next:hover {
  color:var(--offblack) !important;
  box-shadow:0 2px 10px rgba(255,215,6,.25);
}
.rp-nav-guide .rp-nav-btn-disabled {
  background:var(--brightgray) !important;
  color:var(--gray) !important;
  border:1px solid var(--lightgray) !important;
  cursor:default;
}
.rp-nav-guide .rp-nav-link-btn {
  gap:8px;
  background:var(--yellow) !important;
  color:var(--offblack) !important;
  border:1px solid var(--yellow) !important;
  margin:0 8px 8px 0;
}
.rp-nav-guide .rp-nav-link-btn:hover {
  color:var(--offblack) !important;
  box-shadow:0 2px 10px rgba(255,215,6,.25);
}
.rp-nav-guide .rp-nav-link-sec {
  background:var(--offwhite) !important;
  color:var(--darkgray) !important;
  border:1px solid var(--lightgray) !important;
}
.rp-nav-guide .rp-nav-link-sec:hover {
  color:var(--offblack) !important;
  border-color:var(--gray) !important;
  background:var(--offwhite) !important;
}

/* ─── Inline link auto-styling ──────────────────────────────────────── */
.rp-nav-guide a:not(.rp-nav-nav a):not(.rp-nav-btn-prev):not(.rp-nav-btn-next):not(.rp-nav-btn-disabled):not(.rp-nav-link-btn):not(.rp-nav-anchor) {
  color:var(--tangerine) !important;
  font-weight:700;
  text-decoration:none !important;
  border-bottom:0 !important;
}
.rp-nav-guide a:not(.rp-nav-nav a):not(.rp-nav-btn-prev):not(.rp-nav-btn-next):not(.rp-nav-btn-disabled):not(.rp-nav-link-btn):not(.rp-nav-anchor):hover {
  text-decoration:underline !important;
}

/* ─── Responsive ────────────────────────────────────────────────────── */
@media (max-width:640px) {
  .rp-nav-guide .rp-nav-hero { padding:36px 20px 32px; }
  .rp-nav-guide .rp-nav-hero h1 { font-size:1.7rem; }
  .rp-nav-guide .rp-nav-2col,
  .rp-nav-guide .rp-nav-3col { grid-template-columns:1fr; }
  .rp-nav-guide .rp-nav-nav,
  .rp-nav-guide .rp-nav-sec-nav,
  .rp-nav-guide .rp-nav-sec-header { flex-direction:column; }
  .rp-nav-guide .rp-nav-sec-nav { align-items:stretch; }
}
</style>

<div class="rp-nav-guide">
  <div class="rp-nav-hero">
    <div class="rp-nav-badge">
      <img src="https://files.readme.io/38bdbe95e36b4d13be3787855b9a3f2753d18eee342589915213b61a2e07e508-Scale-icon-black.png" alt="Scale">
      Scale
    </div>
    <h1>Payments Hub</h1>
    <p>Your payment performance data, all in one place. Learn your way around every dashboard — and know what to look for from day one.</p>
  </div>

  <nav class="rp-nav-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub">Payments Hub</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview"><span class="rp-nav-snum">1</span>Overview</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-processing"><span class="rp-nav-snum">2</span>Payment processing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-account-updater"><span class="rp-nav-snum">3</span>Account updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-payment-retries"><span class="rp-nav-snum">4</span>Payment retry recovery</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-fraud-prevention"><span class="rp-nav-snum">5</span>Fraud prevention</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-review-resources"><span class="rp-nav-snum">6</span>Review &amp; resources</a>
  </nav>

  <div class="rp-nav-sec">

    <div class="rp-nav-sec-header">
      <div class="rp-nav-sec-icon">📊</div>
      <div>
        <h2 id="what-is-payments-hub">
          <a class="rp-nav-anchor" href="#what-is-payments-hub">What is Payments Hub?</a>
        </h2>
        <p>A new payment analytics dashboard inside your Recurly account — giving you a complete view of your payment performance without ever leaving the platform.</p>
      </div>
    </div>

    <div class="rp-nav-card">
      <h3 class="rp-nav-subhead" id="the-problem-it-solves">
        <a class="rp-nav-anchor" href="#the-problem-it-solves">🧩 The problem it solves</a>
      </h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">Before Payments Hub, understanding your payment performance meant logging into each gateway portal separately, and manually reconciling the data.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Payments Hub changes that. It pulls all of your payment data — across every connected gateway, payment method, and value-add service — into one place. One view to understand what's working, what isn't, and where to focus.</p>
    </div>

    <h3 class="rp-nav-subhead" id="whats-inside">
      <a class="rp-nav-anchor" href="#whats-inside">🗺️ What's inside</a>
    </h3>
    <div class="rp-nav-3col">
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">🏠</div>
        <h4>Overview dashboard</h4>
        <p>Top-level payment health — success rates, volume by region, and payment method mix.</p>
      </div>
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">💳</div>
        <h4>Payment processing dashboard</h4>
        <p>Acceptance rates by gateway, payment method, card BIN, and decline reason.</p>
      </div>
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">🔄</div>
        <h4>Account updater dashboard</h4>
        <p>Revenue protected through automatic card updates before payments fail.</p>
      </div>
    </div>
    <div class="rp-nav-3col">
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">🔁</div>
        <h4>Payment retry recovery dashboard</h4>
        <p>How many failed invoices were recovered — and how quickly.</p>
      </div>
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">🛡️</div>
        <h4>Fraud prevention</h4>
        <p>Blocked transactions and risk score trends. Available for Kount-enabled merchants. Learn more about Kount <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount" target="_blank" rel="noopener noreferrer">here</a>.</p>
      </div>
      <div class="rp-nav-wi rp-nav-wi-center">
        <div class="rp-nav-wi-icon">🎯</div>
        <h4>How this path works</h4>
        <p>Each step walks through one dashboard, what it shows, and an activity to try in your account.</p>
      </div>
    </div>

    <div class="rp-nav-sec-header" style="margin-top:40px;">
      <div class="rp-nav-sec-icon">🧭</div>
      <div>
        <h2 id="how-to-find-it">
          <a class="rp-nav-anchor" href="#how-to-find-it">How to find it</a>
        </h2>
        <p>Payments Hub lives inside Analytics in your Recurly account. No setup required — if you have the Analytics role, it's already there.</p>
      </div>
    </div>

    <div class="rp-nav-steps">
      <div class="rp-nav-step">
        <div class="rp-nav-sbadge">1</div>
        <div>
          <h3>Log in to your Recurly account</h3>
          <p>Head to <strong>app.recurly.com</strong> and sign in with your credentials.</p>
        </div>
      </div>
      <div class="rp-nav-step">
        <div class="rp-nav-sbadge">2</div>
        <div>
          <h3>Navigate to Analytics</h3>
          <p>Click <strong>Analytics</strong> in the left-hand navigation.</p>
        </div>
      </div>
      <div class="rp-nav-step">
        <div class="rp-nav-sbadge">3</div>
        <div>
          <h3>Select Payments Hub</h3>
          <p>Under Analytics, click <strong>Payments Hub</strong> to open the Overview dashboard — your starting point for all payment analytics.</p>
        </div>
      </div>
    </div>

    <img src="https://files.readme.io/d1cfc1ddc7985620bb9f4247454a32a9b7176d88e8a359b1940d6ddd2af7280b-Navigate_Slides.png"
         alt="Navigating to Payments Hub in Recurly Analytics"
         style="width:100%;border-radius:14px;border:1px solid var(--lightgray);margin-bottom:24px;" />

    <div class="rp-nav-warning">
      <span class="rp-nav-wicon">⚠️</span>
      <p><strong>Don't see Payments Hub?</strong> You need the <strong>Analytics user role</strong> in Recurly. If it's missing from your nav, contact your Recurly admin to confirm your permissions. <a href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank" rel="noopener noreferrer">Learn about user roles →</a></p>
    </div>

    <div class="rp-nav-tip">
      <span class="rp-nav-tipicon">💡</span>
      <div>
        <h4>Data availability</h4>
        <p>Payments Hub began collecting data in Q1 2026. Data prior to that date is not available in these dashboards — this is expected.</p>
      </div>
    </div>

    <h3 class="rp-nav-subhead" id="before-you-move-on">
      <a class="rp-nav-anchor" href="#before-you-move-on">✅ Before you move on</a>
    </h3>
    <div class="rp-nav-checklist">
      <div class="rp-nav-cl-header">
        <span>✅</span>
        <h3>Getting started checklist</h3>
      </div>
      <div class="rp-nav-cli">
        <input type="checkbox" class="rp-nav-cb" id="gs1">
        <label for="gs1" class="rp-nav-clab">
          Open Payments Hub in your Recurly account
          <span>Analytics → Payments Hub → Overview</span>
        </label>
      </div>
      <div class="rp-nav-cli">
        <input type="checkbox" class="rp-nav-cb" id="gs2">
        <label for="gs2" class="rp-nav-clab">
          Confirm your available dashboards are visible: Overview, Payment Processing, Account Updater, Payment Retry Recovery, and Fraud Prevention
          <span>All Payments Hub dashboards require Analytics permissions for visibility. <strong>Note</strong>: The Fraud Prevention dashboard will only be visible if using Kount as a feature, and the Account Updater dashboard will only be available if you have Account Updater enabled.</span>
        </label>
      </div>
      <div class="rp-nav-cli">
        <input type="checkbox" class="rp-nav-cb" id="gs3">
        <label for="gs3" class="rp-nav-clab">
          Take note of the first number that catches your attention on the Overview dashboard
          <span>You'll dig into this in the next step</span>
        </label>
      </div>
    </div>

    <div class="rp-nav-sec-nav">
      <span class="rp-nav-btn-disabled">🎯 Start</span>
      <a class="rp-nav-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale-payments-hub-overview">Next: Overview →</a>
    </div>

    <h3 class="rp-nav-subhead" id="additional-resources" style="margin-top:28px;">
      <a class="rp-nav-anchor" href="#additional-resources">📚 Additional resources</a>
    </h3>
    <a class="rp-nav-link-btn rp-nav-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Payments Hub</a>
    <a class="rp-nav-link-btn rp-nav-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/user-roles-and-permissions" target="_blank" rel="noopener noreferrer">🔐 User roles and permissions</a>
    <a class="rp-nav-link-btn rp-nav-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rp-nav-link-btn rp-nav-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🌐 Join Global Office Hours</a>
  </div>
</div>
`}</HTMLBlock>

<br />