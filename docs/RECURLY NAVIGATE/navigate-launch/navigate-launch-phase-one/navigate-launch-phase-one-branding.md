---
title: 'Section 4: Branding Emails & Invoices'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--yellow)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.25);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(13,13,11,.15);color:var(--offblack)}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--yellow);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-steps{display:flex;flex-direction:column;gap:11px;margin-bottom:16px}
.rc-step{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:15px 17px;display:flex;gap:13px;align-items:flex-start}
.rc-sbadge{width:34px;height:34px;border-radius:9px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-step h3{font-size:.93rem;font-weight:700;margin:0 0 4px;color:var(--offblack)}
.rc-step p{font-size:.84rem;color:var(--gray);line-height:1.6;margin:0}
.rc-tip{background:#fffde6;border:1px solid var(--yellow);border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-checklist{background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:18px}
.rc-cl-header{padding:13px 19px;border-bottom:1px solid var(--lightgray);display:flex;align-items:center;gap:9px;background:var(--offblack)}
.rc-cl-header h3{font-size:.82rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
.rc-cli{padding:11px 19px;border-bottom:1px solid var(--brightgray);display:flex;gap:11px;align-items:flex-start}
.rc-cli:last-child{border-bottom:none}
.rc-cb{width:19px;height:19px;border-radius:5px;border:2px solid var(--lightgray);flex-shrink:0;margin-top:1px;background:#fff}
.rc-clab{font-size:.85rem;color:var(--darkgray);line-height:1.4}
.rc-clab span{display:block;font-size:.75rem;color:var(--gray);margin-top:2px}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate · Launchpad Phase 1</div>
    <h1>Branding & Customer Experience</h1>
    <p>Ensure every customer touchpoint — from checkout to monthly invoices — looks and feels like your brand, fostering trust and professional consistency.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 4</div><div class="rc-lbl">Phase 1</div></div>
      <div><div class="rc-num">Visual</div><div class="rc-lbl">Consistency</div></div>
      <div><div class="rc-num">Trust</div><div class="rc-lbl">Building</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding" class="rc-active"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎨</div>
      <div>
        <h2>Make Recurly Yours</h2>
        <p>A cohesive brand experience reduces "subscription anxiety." When checkout pages and emails match your website, customers are more likely to complete purchases and less likely to flag renewals as suspicious.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Designing the Experience — Branding</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/694b8e6f-5798-4663-8a35-081862590216" loading="lazy" title="Navigate Launchpad — Branding" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">Learn where to upload your logos, how to set your brand colors for checkout, and how to customize automated email templates.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🖼️ Core Branding Assets</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Logo & Favicon</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Upload your logo (max 256KB) for use on hosted pages and invoices. Don't forget your <strong>Icon</strong> for the browser favicon.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Brand Colors</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Apply your primary brand hex code to buttons and links in <strong>Checkout Styles</strong> to ensure a seamless transition from your site.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Billing Contact Email</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Set your <strong>Billing Contact Email</strong> in Site Settings. This ensures customers see your brand's support email as the "Sender" of all receipts.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Email Customization</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Add your logo to the Header template. Recurly automatically sends HTML and plain-text versions of every lifecycle email.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Deliverability Tip:</strong> Configure your <strong>SPF and DKIM</strong> records in your Domain settings. This proves to inbox providers that Recurly has permission to send emails as your domain, significantly improving open rates.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Branding Setup</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Configure Site Settings</h3>
          <p>Go to <strong>Configuration → Site Settings</strong>. Set your Company Name and Billing Contact Email. This information populates your default invoice and email footers.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Style Your Checkout</h3>
          <p>Navigate to <strong>Configuration → Checkout</strong>. Edit your "Starter Style" to upload your logo and set your brand color. Preview the experience to ensure it's mobile-responsive.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Update Email Templates</h3>
          <p>Go to <strong>Configuration → Email Templates</strong>. Use the "Header" and "Footer" templates to add branding once; it will then apply across all 20+ lifecycle emails automatically.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Customize Invoices</h3>
          <p>In <strong>Configuration → Invoice Templates</strong>, upload a high-resolution logo for your PDF receipts. You can also add custom notes or legal disclaimers to the footer here.</p>
        </div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">✅ Branding Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Verify Visuals Before Launch</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Billing Contact Email updated in Site Settings</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Logo and Brand Color applied to Checkout Styles</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Header/Footer images added to Email Templates</div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Sent a "Test Email" to yourself to verify logo appearance in an inbox</div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater">← Account Updater</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover">Step 5: Failover →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/docs/branding-your-recurly-site" target="_blank">📖 Branding Guide</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/email-templates">📧 Email Templates Docs</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
