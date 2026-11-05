---
title: 'Editing page 4: Newsletter ideas'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Figtree:wght@400;500;600;700;800;900&display=swap">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
/* HOST-THEME BACKGROUND OVERRIDE */
body { background: #ffffff !important; }

/* GLOBAL CSS IMMUNITY BLOCK */
.rc-guide h1 { border-bottom: none !important; padding-bottom: 0 !important; }
.rc-guide, .rc-guide * { font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important; }
.rc-guide [class^="fa-"],
.rc-guide [class*=" fa-"] { font-family: "Font Awesome 6 Free" !important; }
.rc-guide .fa-brands,
.rc-guide [class*="fa-brands"] { font-family: "Font Awesome 6 Brands" !important; }

/* NAVIGATE MASTER ARMOR */
.rm-Markdown.markdown-body .rc-guide a:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:active {
  color: #008CFF !important;
  text-decoration: none !important;
  text-decoration-line: none !important;
  text-decoration-color: transparent !important;
  text-underline-offset: unset !important;
  border-bottom: 0 !important;
}
.rc-guide a:hover {
  color: #0067BE !important;
  text-decoration: underline !important;
  text-decoration-color: #008CFF !important;
  text-underline-offset: 2px !important;
}

.rc-guide {
  --yellow:     #FFD706;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D75;
  --lightgray:  #D1CFC4;
  --brightgray: #F2F1EA;
  --offwhite:   #FCFBF7;
  font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #32312D !important;
  background: #ffffff;
  max-width: 600px;
  margin: 0 auto;
  padding: 0 0 40px;
}
.rc-guide * { box-sizing: border-box; }

/* Email-matched layout: a 600px column with one shared rhythm */
.rc-email { background: #FFFFFF; border: 1px solid #D1CFC4; border-radius: 0; overflow: hidden; }
.rc-pad { padding-left: 40px; padding-right: 40px; }
.rc-kicker { font-size: 11px; font-weight: 700; letter-spacing: .12em; text-transform: uppercase; color: #807D75; margin: 0 0 8px; }

/* Header: topo map with logo linked to Navigate home */
.rc-header {
  background: linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover; padding: 28px 40px;
}
.rc-header a.rc-header-logo { display: inline-block; }
.rc-header img { height: 18px; width: auto; display: block; }

/* Hero */
.rc-hero { background: #FCFBF7; padding: 44px 40px 40px; border-bottom: 1px solid #D1CFC4; }
.rc-tag-row { display: flex; align-items: center; gap: 10px; margin-bottom: 24px; }
.rc-tag-icon {
  width: 36px; height: 36px; border-radius: 10px; background: #FFD706; color: #0D0D0B;
  display: flex; align-items: center; justify-content: center; font-size: 1.05rem; flex-shrink: 0;
}
.rc-tag-label {
  height: 36px; line-height: 34px; padding: 0 14px; border-radius: 10px;
  background: #E9E8E3; border: 0; font-size: 15px; font-weight: 700; color: #0D0D0B;
}
.rc-hero h1 { font-size: 52px; line-height: 1.02; font-weight: 800; letter-spacing: -0.02em; color: #0D0D0B; margin: 0; }
.rc-hero .rc-date { font-size: 17px; line-height: 1.4; color: #32312D; margin: 14px 0 0; }
.rc-hero .rc-date strong { color: #0D0D0B; }

/* Body copy */
.rc-body { padding-top: 40px; }
.rc-body p { font-size: 15px; line-height: 1.6; color: #32312D; margin: 0 0 16px; }
.rc-body .rc-greet { font-size: 17px; color: #0D0D0B; }
.rc-body .rc-note { font-size: 13px; color: #807D75; margin: 0; }

/* Sections share one spacing rule */
.rc-block { padding-top: 40px; }
.rc-block h2 { font-size: 26px; line-height: 1.15; font-weight: 800; color: #0D0D0B; margin: 0 0 10px; }
.rc-block h2.rc-sm { font-size: 22px; line-height: 1.2; margin-bottom: 8px; }
.rc-block p { font-size: 14px; line-height: 1.6; color: #32312D; margin: 0 0 14px; }
.rc-block p:last-child { margin-bottom: 0; }
.rc-link { display: block; font-size: 14px; font-weight: 700; color: #008CFF; text-decoration: underline; margin: 0 0 8px; }
.rc-link:last-child { margin-bottom: 0; }
.rc-link-row { margin-bottom: 20px; }

/* Pill */
.rc-pill { display: inline-block; background: #0D0D0B; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: .04em; padding: 4px 9px; border-radius: 999px; }
.rc-pill.rc-soon { background: #F2F1EA; color: #32312D; }

/* Bordered feature card */
.rc-card { border: 1px solid #D1CFC4; padding: 24px; }
.rc-card-inner-callout {
  background: #F2F1EA; border-left: 4px solid #FFD706; padding: 12px 14px; margin-top: 4px;
}
.rc-card-inner-callout p { font-size: 13px; line-height: 1.55; color: #0D0D0B; margin: 0; }

/* Side icon layout (icon left, text right) */
.rc-side { display: flex; gap: 16px; align-items: flex-start; }
.rc-side-icon {
  width: 48px; height: 48px; border-radius: 12px; background: #FFD706; color: #0D0D0B;
  display: flex; align-items: center; justify-content: center; font-size: 1.3rem; flex-shrink: 0;
}
.rc-side-body { flex: 1; min-width: 0; }

/* Video */
.rc-video {
  aspect-ratio: 16/9; border: 1px solid #0D0D0B; display: flex; align-items: center; justify-content: center;
  background: linear-gradient(rgba(13,13,11,0.75),rgba(13,13,11,0.75)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
}
.rc-play {
  width: 74px; height: 74px; border-radius: 50%; background: #FFD706; color: #0D0D0B;
  display: flex; align-items: center; justify-content: center; font-size: 1.6rem; padding-left: 6px;
}

/* More list */
.rc-more { border-top: 1px solid #D1CFC4; margin-top: 16px; }
.rc-more-item { padding: 18px 0; border-bottom: 1px solid #D1CFC4; font-size: 14px; line-height: 1.55; color: #32312D; }
.rc-more-item strong { color: #0D0D0B; }
.rc-more-item .rc-link { margin-top: 8px; }

/* Office hours ad */
.rc-ad a { display: block; }
.rc-ad img { display: block; width: 100%; max-width: 520px; height: auto; border: 0; }

/* Roadmap call-out */
.rc-roadmap { border: 2px solid #0D0D0B; padding: 22px 24px; }
.rc-roadmap .rc-kicker { margin-bottom: 6px; }
.rc-roadmap h3 { font-size: 18px; font-weight: 800; line-height: 1.3; color: #0D0D0B; margin: 0 0 6px; }
.rc-roadmap p { font-size: 14px; line-height: 1.55; color: #32312D; margin: 0; }

/* Footer: links only, black band */
.rc-footer { background: #0D0D0B; padding: 36px 40px; text-align: center; margin-top: 40px; }
.rc-footer-links { font-size: 14px; line-height: 2; }
.rc-footer-links a { color: #FFFFFF !important; text-decoration: underline !important; padding: 0 12px; }
.rc-footer-links a:hover { color: #FFD706 !important; }
.rc-footer-links .rc-sep { color: #807D75; }

/* Inline body links inside paragraphs use the armor-safe class */
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-inline-link { color: #008CFF !important; font-weight: 700; border-bottom: 0 !important; text-decoration: underline !important; }

@media(max-width:620px){
  .rc-pad, .rc-hero, .rc-header, .rc-footer { padding-left: 20px !important; padding-right: 20px !important; }
  .rc-hero h1 { font-size: 36px; }
  .rc-block h2 { font-size: 24px; }
  .rc-side { flex-direction: column; }
}
</style>

<div class="rc-guide">
<div class="rc-email">

  <!-- Header with topo map -->
  <div class="rc-header">
    <a class="rc-header-logo" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home">
      <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Navigate home">
    </a>
  </div>

  <!-- Hero -->
  <div class="rc-hero">
    <div class="rc-tag-row">
      <span class="rc-tag-icon"><i class="fa-solid fa-arrows-rotate"></i></span>
      <span class="rc-tag-label">Subscriptions</span>
    </div>
    <h1>Quarter connect</h1>
    <p class="rc-date"><strong>2026</strong>&nbsp;&nbsp;|&nbsp;&nbsp;July, August, September</p>
  </div>

  <!-- Body -->
  <div class="rc-pad rc-body">
    <p class="rc-greet">Hi {{First Name}},</p>
    <p>Navigate is our digital customer success program, designed to make sure all of our customers are maximizing value. This is your quarterly update on what's new for Subscriptions.</p>
    <p>Failed payments, chargebacks and paused subscriptions quietly cost you subscribers. This quarter's updates help you catch them sooner and recover more of them. Each feature below lists what it needs before you turn it on, including feature flags and plan limits.</p>
    <p class="rc-note"><em>These features are part of Recurly Subscription Management (RSM).</em></p>
  </div>

  <!-- Feature: Payments hub (video feature) -->
  <div class="rc-pad rc-block">
    <div class="rc-kicker">Watch</div>
    <h2>Payments hub: see where payments fail, and why</h2>
    <p>Six dashboards cover processing, recovery and fraud in one place. Watch the walkthrough to see how to use them to find and fix payment problems.</p>
    <a class="rc-link rc-link-row" href="https://docs.recurly.com/recurly-subscriptions/docs/payments-hub" target="_blank" rel="noopener noreferrer">Learn more about Payments hub &rarr;</a>
    <div class="rc-video">
      <span class="rc-play"><i class="fa-solid fa-play"></i></span>
    </div>
  </div>

  <!-- Feature: Justt.ai -->
  <div class="rc-pad rc-block">
    <div class="rc-card">
      <span class="rc-pill">Feature flagged</span>
      <h2 class="rc-sm" style="margin-top:14px;">Justt.ai chargeback integration</h2>
      <p>Automate chargeback dispute management with AI-powered recovery. Keep subscription actions in sync as disputes are resolved. When a dispute is lost, choose a refund, expire the subscription or handle it manually.</p>
      <a class="rc-link rc-link-row" href="https://docs.recurly.com/recurly-subscriptions/docs/justtai" target="_blank" rel="noopener noreferrer">Learn more about Justt.ai &rarr;</a>
      <div class="rc-card-inner-callout">
        <p><strong>Before you start:</strong> an active Justt.ai account, a supported gateway (Stripe, Braintree, PayPal Complete or Adyen) and a Recurly API key. Recurly Support enables the Justt.ai and Chargeback Management feature flags. Available on all plans, with one chargeback system and one Justt.ai configuration per site.</p>
      </div>
    </div>
  </div>

  <!-- Feature: Paused subscriptions -->
  <div class="rc-pad rc-block">
    <div class="rc-side">
      <span class="rc-side-icon"><i class="fa-solid fa-arrows-rotate"></i></span>
      <div class="rc-side-body">
        <h2 class="rc-sm">Paused subscription resume date API</h2>
        <p>Retrieve scheduled resume dates for paused subscriptions to power personalized portals, lifecycle messages and connected workflows. Subscription data includes <code>resume_at</code>, <code>paused_at</code> and <code>remaining_pause_cycles</code>.</p>
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-notifications" target="_blank" rel="noopener noreferrer">Learn more about paused subscription notifications &rarr;</a>
      </div>
    </div>
  </div>

  <!-- Feature: Coupons -->
  <div class="rc-pad rc-block">
    <div class="rc-side">
      <span class="rc-side-icon"><i class="fa-solid fa-arrows-rotate"></i></span>
      <div class="rc-side-body">
        <h2 class="rc-sm">Coupon enhancements and bulk unique coupons</h2>
        <p>Build promotions with billing-period coupons for an exact number of cycles, rolling expiration dates and multiple coupons per account. Billing-period coupons apply at the subscription level only.</p>
        <p>Generate single-use codes on demand with bulk unique coupons, then set redeem-by windows for each code.</p>
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/bulk-unique-coupons" target="_blank" rel="noopener noreferrer">Learn more about bulk unique coupons &rarr;</a>
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/coupons#billing-period-coupons" target="_blank" rel="noopener noreferrer">Learn more about billing-period coupons &rarr;</a>
        <a class="rc-link" href="https://recurly.com/developers/api/v2021-02-25/index.html#operation/generate_unique_coupon_codes_sync" target="_blank" rel="noopener noreferrer">Generate unique codes on demand with the API &rarr;</a>
      </div>
    </div>
  </div>

  <!-- More updates -->
  <div class="rc-pad rc-block">
    <h2 class="rc-sm">More for Subscriptions</h2>
    <div class="rc-more">
      <div class="rc-more-item">
        <strong>Custom fields on invoices.</strong> Display custom account, subscription, plan and line-item data on invoices. Text only, up to 255 characters. Limits by plan: Pro up to 5, Elite up to 10, Sandbox and Developer up to 5. Starter isn't supported. Requires the Configuration permission.
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/custom-fields" target="_blank" rel="noopener noreferrer">Learn more about custom fields &rarr;</a>
      </div>
      <div class="rc-more-item">
        <strong>Tax-inclusive invoice display.</strong> Show customers a cleaner all-in invoice price while keeping tax accurate. Off by default and requires native tax, Avalara or Vertex. Once tax-inclusive pricing is enabled on a site, it can't be reversed.
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/tax-inclusive-pricing#invoicing" target="_blank" rel="noopener noreferrer">Learn more about tax-inclusive pricing &rarr;</a>
      </div>
      <div class="rc-more-item">
        <strong>Data retention settings.</strong> Set retention windows from 1 to 10 years for payment method and PII data on inactive accounts. Requires the data retention feature flag from Recurly Support and the site admin permission.
        <a class="rc-link" href="https://docs.recurly.com/recurly-subscriptions/docs/data-retention" target="_blank" rel="noopener noreferrer">Learn more about data retention &rarr;</a>
      </div>
      <div class="rc-more-item">
        <strong>Granular user permissions.</strong> Give admins more precise control over user access with page- and resource-level permissions across Recurly Admin. <span class="rc-pill rc-soon">Coming soon</span>
      </div>
    </div>
  </div>

  <!-- Office hours ad -->
  <div class="rc-pad rc-block rc-ad">
    <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">
      <img src="https://recurly.com/img2/navigate/navigate-got-questions.png" alt="Navigate: got questions? Join Global Office Hours.">
    </a>
  </div>

  <!-- Roadmap session -->
  <div class="rc-pad rc-block">
    <div class="rc-roadmap">
      <div class="rc-kicker">Next</div>
      <h3>Join the Navigate Recurly roadmap &amp; vision session</h3>
      <p>See where Subscriptions and the rest of the Recurly platform are headed, and what's next for your team.</p>
    </div>
  </div>

  <!-- Footer: links only -->
  <div class="rc-footer">
    <div class="rc-footer-links">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home">Navigate home</a>
      <span class="rc-sep">|</span>
      <a href="https://recurly.com" target="_blank" rel="noopener noreferrer">Recurly home</a>
      <span class="rc-sep">|</span>
      <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer">Office hours</a>
    </div>
  </div>

</div>
</div>
`}</HTMLBlock>