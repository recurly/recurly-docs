---
title: Editing page 5
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

html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:     #FFD706;
  --blue:       #008CFF;
  --blue-tint1: #D5EAFF;
  --blue-tint2: #96C8FF;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D75;
  --lightgray:  #D1CFC4;
  --brightgray: #F2F1EA;
  --offwhite:   #FCFBF7;
  --warning-fg: #FFD706;
  --warning-bg: #FFFECB;
  --error-fg:   #FF5126;
  --error-bg:   #FFEEE9;
  --success-fg: #5DC32E;
  --success-bg: #EFFAEA;
  --info-fg:    #008CFF;
  --info-bg:    #E5F3FF;
  font-family: "Figtree", "Helvetica Neue", Helvetica, arial, sans-serif !important;
  color: #32312D !important;
  background: #ffffff;
  max-width: 1000px;
  margin: 0 auto;
  padding: 0 0 48px;
}
.rc-guide * { box-sizing: border-box; }

/* Icon helpers */
.rc-fa-dark  { color: #FFD706 !important; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-light { color: #0D0D0B; font-size: 1.3rem; display: block; margin-bottom: 10px; }
.rc-fa-section { color: #0D0D0B; font-size: 1rem; }

/* Hero — topo background, Navigate brand header */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
  color: #ffffff; padding: 48px 40px 44px; text-align: center; border-radius: 16px;
}
.rc-brand-header { display: flex; justify-content: center; margin-bottom: 0; }
.rc-logo-image { height: 28px; display: block; }
.rc-home-title-block { margin-top: 44px; }
.rc-home-title-block h1 { font-size: 2.6rem; font-weight: 800; line-height: 1.1; color: #FCFBF7; margin: 0 0 14px; }
.rc-home-title-block p { font-size: 1rem; line-height: 1.6; color: #D1CFC4; max-width: 640px; margin: 0 auto; }
.rc-hero-tag {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(255,215,6,0.20); border: 1px solid rgba(255,215,6,0.45); color: #FFD706;
  font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 20px; margin-bottom: 18px;
}

/* Section headings */
.rc-section { margin: 48px 0 0; }
.rc-section h2 { font-size: 1.5rem; font-weight: 800; margin: 0 0 16px; color: #0D0D0B; display: flex; align-items: center; gap: 12px; }
.rc-section h2::after { content: ""; flex-grow: 1; height: 1px; background: #D1CFC4; }
.rc-section p { font-size: .95rem; line-height: 1.65; color: #32312D; margin: 0 0 14px; }

/* Intro */
.rc-intro p { font-size: 1.02rem; }

/* Feature cards */
.rc-card-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 0; }
.rc-feature-card { background: #FCFBF7; border: 1px solid #D1CFC4; border-radius: 12px; padding: 22px; display: flex; flex-direction: column; gap: 8px; }
.rc-feature-card.rc-span-2 { grid-column: span 2; }
.rc-feature-icon-tile { width: 44px; height: 44px; display: block; }
.rc-feature-card h3 { font-size: 1.05rem; font-weight: 800; color: #0D0D0B; margin: 4px 0 0; line-height: 1.3; }
.rc-feature-card p { font-size: .9rem; color: #807D75; line-height: 1.55; margin: 0; flex-grow: 1; }
.rc-feature-card p strong { color: #32312D; }
.rc-feature-tag { display: inline-block; margin-top: 4px; padding: 3px 10px; border-radius: 20px; font-size: .7rem; font-weight: 700; letter-spacing: .5px; background: #0D0D0B; color: #FFD706; width: fit-content; }
.rc-feature-tag.rc-soon { background: transparent; color: #0D0D0B; border: 1.5px solid #0D0D0B; }

/* Before-you-start callout */
.rc-callout {
  background: #F2F1EA; border-left: 4px solid #FFD706; border-radius: 10px;
  padding: 14px 18px; margin-top: 10px; display: flex; gap: 12px; align-items: flex-start;
}
.rc-callout i { color: #0D0D0B; font-size: 1rem; margin-top: 2px; }
.rc-callout p { font-size: .88rem; line-height: 1.55; color: #32312D; margin: 0; }
.rc-callout p strong { color: #0D0D0B; }

/* Video card */
.rc-video-card { border: 1px solid #D1CFC4; border-radius: 14px; overflow: hidden; margin: 0; }
.rc-video-header { background: #0D0D0B; padding: 16px 22px; display: flex; align-items: center; gap: 10px; }
.rc-video-header h3 { font-size: .85rem; font-weight: 700; text-transform: uppercase; letter-spacing: .7px; color: #FFD706; margin: 0; }
.rc-video-header span { font-size: .78rem; color: #D1CFC4; margin-left: auto; }
.rc-video-frame {
  aspect-ratio: 16/9; display: flex; align-items: center; justify-content: center;
  background: linear-gradient(rgba(13,13,11,0.78), rgba(13,13,11,0.78)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: #0D0D0B; background-size: cover;
}
.rc-play-btn {
  width: 84px; height: 84px; border-radius: 50%; background: #FFD706;
  display: flex; align-items: center; justify-content: center; color: #0D0D0B; font-size: 1.8rem;
}
.rc-video-caption { padding: 12px 22px; font-size: .85rem; color: #807D75; background: #F2F1EA; border-top: 1px solid #D1CFC4; line-height: 1.5; }

/* Tiles row for "more" */
.rc-more-list { border-top: 1px solid #D1CFC4; margin: 0; padding: 0; list-style: none; }
.rc-more-list li { padding: 16px 0; border-bottom: 1px solid #D1CFC4; font-size: .92rem; line-height: 1.6; color: #32312D; }
.rc-more-list li strong { color: #0D0D0B; }

/* Office hours ad */
.rc-ad-link { display: block; border-radius: 12px; overflow: hidden; border: 1px solid #D1CFC4; }
.rc-ad-link img { display: block; width: 100%; height: auto; }

/* Roadmap CTA */
.rc-roadmap-cta { background: #FCFBF7; border: 2px solid #0D0D0B; border-radius: 14px; padding: 26px 28px; margin: 48px 0 0; }
.rc-roadmap-cta .rc-eyebrow { font-size: .72rem; font-weight: 800; letter-spacing: .9px; text-transform: uppercase; color: #807D75; margin: 0 0 8px; }
.rc-roadmap-cta h3 { font-size: 1.3rem; font-weight: 800; color: #0D0D0B; margin: 0 0 8px; line-height: 1.3; }
.rc-roadmap-cta p { font-size: .95rem; color: #32312D; line-height: 1.6; margin: 0; }

/* Footer */
.rc-footer { border-top: 1px solid #D1CFC4; margin-top: 48px; padding-top: 24px; display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 16px; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; }
.rc-footer-copy { font-size: .8rem; color: #807D75; margin: 0; }

/* Footer links — double prefix, hex color */
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-footer-link {
  color: #807D75 !important; text-decoration: none !important; font-weight: 600; font-size: .88rem;
  display: inline-flex; align-items: center; gap: 6px; border-bottom: 0 !important;
}
.rm-Markdown.markdown-body .rc-guide a.rc-footer-link:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-footer-link:hover { color: #008CFF !important; }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; }

/* Button — yellow primary */
.rm-Markdown.markdown-body .rc-guide a.rc-btn-primary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-btn-primary {
  display: inline-flex; align-items: center; gap: 8px;
  background: #FFD706; color: #0D0D0B !important; text-decoration: none !important;
  padding: 12px 22px; border-radius: 10px; font-weight: 800; font-size: .92rem;
  border: 2px solid #FFD706 !important; border-bottom: 2px solid #FFD706 !important;
  transition: all .2s;
}
.rm-Markdown.markdown-body .rc-guide a.rc-btn-primary:not([class*="Button"]):not(.rp-anchor):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-btn-primary:hover {
  background: transparent !important; color: #0D0D0B !important;
  border: 2px solid #0D0D0B !important; border-bottom: 2px solid #0D0D0B !important;
}

/* Inline body link */
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn),
.rc-guide a.rc-inline-link { color: #008CFF !important; font-weight: 600; border-bottom: 0 !important; text-decoration: none !important; }
.rm-Markdown.markdown-body .rc-guide a.rc-inline-link:not([class*="Button"]):not(.rp-toc-pill):not(.rp-btn):hover,
.rc-guide a.rc-inline-link:hover { color: #0067BE !important; text-decoration: underline !important; text-decoration-color: #008CFF !important; text-underline-offset: 2px !important; }

/* Responsive */
@media(max-width:768px){
  .rc-guide { padding: 0 16px 36px; }
  .rc-hero { padding: 36px 20px; }
  .rc-home-title-block h1 { font-size: 1.9rem; }
  .rc-card-grid { grid-template-columns: 1fr; }
  .rc-feature-card.rc-span-2 { grid-column: span 1; }
  .rc-roadmap-cta { padding: 22px 20px; }
  .rc-play-btn { width: 64px; height: 64px; font-size: 1.3rem; }
}
</style>

<div class="rc-guide">

  <!-- Hero -->
  <div class="rc-hero">
    <div class="rc-brand-header">
      <img class="rc-logo-image" src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly Navigate">
    </div>
    <div class="rc-home-title-block">
      <div class="rc-hero-tag"><i class="fa-solid fa-repeat"></i> Subscriptions · Q3 2026</div>
      <h1>Quarter connect</h1>
      <p>2026 | July, August, September. What's new for Subscriptions, and how to put it to work.</p>
    </div>
  </div>

  <!-- Intro -->
  <div class="rc-section rc-intro">
    <p>Navigate is our digital customer success program, designed to make sure all of our customers are maximizing value. This is your quarterly update on what's new for Subscriptions.</p>
    <p>Failed payments, chargebacks and paused subscriptions quietly cost you subscribers. This quarter's updates help you catch them sooner and recover more of them. Each feature below lists what it needs before you turn it on, including feature flags and plan limits.</p>
    <p class="rc-section" style="margin-top:12px;font-size:.85rem;color:#807D75;"><em>These features are part of Recurly Subscription Management (RSM).</em></p>
  </div>

  <!-- Churn and recovery features -->
  <div class="rc-section">
    <h2><i class="fa-solid fa-shield-halved rc-fa-section"></i> Protect revenue</h2>
    <div class="rc-card-grid">

      <div class="rc-feature-card rc-span-2">
        <span class="rc-feature-tag">Feature flagged</span>
        <h3>Justt.ai chargeback integration</h3>
        <p>Automate chargeback dispute management with AI-powered recovery. Keep subscription actions in sync as disputes are resolved. When a dispute is lost, choose a refund, expire the subscription or handle it manually.</p>
        <div class="rc-callout">
          <i class="fa-solid fa-circle-info"></i>
          <p><strong>Before you start:</strong> an active Justt.ai account, a supported gateway (Stripe, Braintree, PayPal Complete or Adyen) and a Recurly API key. Recurly Support enables the Justt.ai and Chargeback Management feature flags. Available on all plans, with one chargeback system and one Justt.ai configuration per site.</p>
        </div>
      </div>

      <div class="rc-feature-card">
        <i class="fa-solid fa-credit-card rc-fa-section"></i>
        <h3>Payments hub</h3>
        <p>Six dashboards cover processing, recovery and fraud in one place: Overview, Payment processing, Account updater, 3DS, Payment retry recovery and Fraud prevention (Kount).</p>
        <p><strong>Access:</strong> available on all plans. Users need the Analytics user role.</p>
      </div>

      <div class="rc-feature-card">
        <i class="fa-solid fa-calendar-check rc-fa-section"></i>
        <h3>Paused subscription resume date API</h3>
        <p>Retrieve scheduled resume dates for paused subscriptions to power personalized portals, lifecycle messages and connected workflows. Subscription data includes <code>resume_at</code>, <code>paused_at</code> and <code>remaining_pause_cycles</code>.</p>
      </div>

    </div>
  </div>

  <!-- Video feature -->
  <div class="rc-section">
    <h2><i class="fa-solid fa-circle-play rc-fa-section"></i> Watch: Payments hub</h2>
    <div class="rc-video-card">
      <div class="rc-video-header">
        <h3>Payments hub walkthrough</h3>
        <span>~3 min</span>
      </div>
      <div class="rc-video-frame">
        <span class="rc-play-btn"><i class="fa-solid fa-play"></i></span>
      </div>
      <div class="rc-video-caption">See where payments fail and how to act on it, using the Payments hub dashboards.</div>
    </div>
  </div>

  <!-- Coupons -->
  <div class="rc-section">
    <h2><i class="fa-solid fa-tag rc-fa-section"></i> Coupons</h2>
    <div class="rc-card-grid">
      <div class="rc-feature-card rc-span-2">
        <h3>Coupon enhancements and bulk unique coupons</h3>
        <p>Build promotions with billing-period coupons for an exact number of cycles, rolling expiration dates and multiple coupons per account. Billing-period coupons apply at the subscription level only.</p>
        <p>Generate single-use codes on demand with bulk unique coupons, then set redeem-by windows for each code.</p>
        <p><a href="https://docs.recurly.com/recurly-subscriptions/docs/bulk-unique-coupons" target="_blank" rel="noopener noreferrer" class="rc-inline-link rp-anchor">Learn more about bulk unique coupons &rarr;</a></p>
      </div>
    </div>
  </div>

  <!-- More updates -->
  <div class="rc-section">
    <h2><i class="fa-solid fa-plus rc-fa-section"></i> More for Subscriptions</h2>
    <ul class="rc-more-list">
      <li><strong>Custom fields on invoices.</strong> Display custom account, subscription, plan and line-item data on invoices. Text only, up to 255 characters. Limits by plan: Pro up to 5, Elite up to 10, Sandbox and Developer up to 5. Starter isn't supported. Requires the Configuration permission.</li>
      <li><strong>Tax-inclusive invoice display.</strong> Show customers a cleaner all-in invoice price while keeping tax accurate. Off by default and requires native tax, Avalara or Vertex. Once tax-inclusive pricing is enabled on a site, it can't be reversed.</li>
      <li><strong>Data retention settings.</strong> Set retention windows from 1 to 10 years for payment method and PII data on inactive accounts. Requires the data retention feature flag from Recurly Support and the site admin permission.</li>
      <li><strong>Granular user permissions.</strong> Give admins more precise control over user access with page- and resource-level permissions across Recurly Admin. <span class="rc-feature-tag rc-soon">Coming soon</span></li>
    </ul>
  </div>

  <!-- Office hours -->
  <div class="rc-section">
    <h2><i class="fa-solid fa-headset rc-fa-section"></i> Have questions?</h2>
    <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-ad-link">
      <img src="https://recurly.com/img2/navigate/navigate-got-questions.png" alt="Navigate: got questions? Join Global Office Hours.">
    </a>
  </div>

  <!-- Roadmap session -->
  <div class="rc-roadmap-cta">
    <p class="rc-eyebrow">Next</p>
    <h3>Join the Navigate Recurly roadmap &amp; vision session</h3>
    <p>See where Subscriptions and the rest of the Recurly platform are headed, and what's next for your team.</p>
  </div>

  <!-- Footer -->
  <div class="rc-footer">
    <div class="rc-footer-utility">
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link">
        <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt=""> Navigate Home
      </a>
      <a href="mailto:support@recurly.com" class="rc-footer-link"><i class="fa-solid fa-headset"></i> Contact Support</a>
    </div>
    <p class="rc-footer-copy">&copy; 2026 Recurly, Inc.</p>
  </div>

</div>
`}</HTMLBlock>
