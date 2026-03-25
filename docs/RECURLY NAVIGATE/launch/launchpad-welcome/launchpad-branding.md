---
title: 'Section 4: Branding Emails & Invoices'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<style>
  .rc-guide {
    --yellow: #FFD706;
    --orange: #FF8200;
    --vermillion: #FF5810;
    --offblack: #0D0D0B;
    --darkgray: #32312D;
    --gray: #807D73;
    --lightgray: #CCC9B8;
    --brightgray: #F1EFE3;
    --offwhite: #FFFDF2;
    font-family: 'Segoe UI', system-ui, sans-serif;
  }

  .rc-hero {
    background: var(--offblack);
    color: white;
    padding: 56px 40px 48px;
    text-align: center;
    border-radius: 16px;
    margin-bottom: 0;
  }

  .rc-badge {
    display: inline-block;
    background: var(--yellow);
    color: var(--offblack);
    border-radius: 20px;
    padding: 6px 18px;
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  .rc-hero h1 {
    font-size: 2.4rem;
    font-weight: 800;
    line-height: 1.15;
    margin: 0 0 14px;
    color: var(--offwhite);
  }

  .rc-hero > p {
    font-size: 1.05rem;
    opacity: 0.8;
    max-width: 700px;
    margin: 0 auto 32px;
    color: var(--lightgray);
  }

  .rc-hero-stats {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
  }

  .rc-num {
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--yellow);
  }

  .rc-lbl {
    font-size: 0.8rem;
    color: var(--lightgray);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .rc-nav {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin: 24px 0 28px;
  }

  .rc-nav a {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    border-radius: 12px;
    border: 1px solid var(--lightgray);
    background: white;
    color: var(--darkgray);
    text-decoration: none;
    font-size: 0.88rem;
    font-weight: 700;
    transition: border-color 0.2s, box-shadow 0.2s, background 0.2s, color 0.2s;
  }

  .rc-nav a:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 8px rgba(255,215,6,0.2);
    color: var(--offblack);
    text-decoration: none;
  }

  .rc-nav a.rc-active {
    background: var(--yellow);
    border-color: var(--yellow);
    color: var(--offblack);
    box-shadow: 0 2px 10px rgba(255,215,6,0.25);
  }

  .rc-snum {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: var(--offblack);
    color: var(--yellow);
    font-size: 12px;
    font-weight: 700;
    flex-shrink: 0;
  }

  .rc-sec {
    margin-bottom: 56px;
  }

  .rc-sec-header {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 32px;
  }

  .rc-sec-icon {
    width: 56px;
    height: 56px;
    border-radius: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 26px;
    flex-shrink: 0;
    background: var(--yellow);
  }

  .rc-sec-header h2 {
    font-size: 1.7rem;
    font-weight: 800;
    margin: 0 0 6px;
    color: var(--offblack);
  }

  .rc-sec-header > div > p {
    color: var(--gray);
    font-size: 0.95rem;
    line-height: 1.5;
    margin: 0;
  }

  .rc-card {
    background: var(--offwhite);
    border-radius: 16px;
    padding: 28px;
    border: 1px solid var(--lightgray);
    margin-bottom: 24px;
  }

  .rc-subhead {
    font-size: 1rem;
    font-weight: 700;
    margin: 0 0 16px;
    color: var(--offblack);
  }

  .rc-2col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-3col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 14px;
    margin-bottom: 24px;
  }

  .rc-opt {
    background: var(--offwhite);
    border: 1px solid var(--lightgray);
    border-radius: 14px;
    padding: 18px;
    transition: border-color 0.2s, box-shadow 0.2s;
  }

  .rc-opt:hover {
    border-color: var(--yellow);
    box-shadow: 0 2px 12px rgba(255,215,6,0.2);
  }

  .rc-oicon {
    font-size: 22px;
    margin-bottom: 8px;
  }

  .rc-opt h4 {
    font-size: 0.92rem;
    font-weight: 700;
    margin: 0 0 5px;
    color: var(--offblack);
  }

  .rc-opt p {
    font-size: 0.82rem;
    color: var(--gray);
    line-height: 1.5;
    margin: 0;
  }

  .rc-tag {
    display: inline-block;
    margin-top: 10px;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
    background: var(--offblack);
    color: var(--yellow);
  }

  .rc-steps {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-bottom: 28px;
  }

  .rc-step {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 22px 26px;
    border: 1px solid var(--lightgray);
    display: flex;
    gap: 18px;
    align-items: flex-start;
  }

  .rc-sbadge {
    width: 38px;
    height: 38px;
    border-radius: 10px;
    background: var(--offblack);
    color: var(--yellow);
    font-weight: 800;
    font-size: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .rc-step h3 {
    font-size: 0.98rem;
    font-weight: 700;
    margin: 0 0 5px;
    color: var(--offblack);
  }

  .rc-step p {
    font-size: 0.87rem;
    color: var(--gray);
    line-height: 1.6;
    margin: 0;
  }

  .rc-tip {
    background: var(--offwhite);
    border: 2px solid var(--yellow);
    border-radius: 14px;
    padding: 20px 24px;
    margin-bottom: 24px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }

  .rc-tipicon {
    font-size: 24px;
    flex-shrink: 0;
  }

  .rc-tip h4 {
    font-size: 0.82rem;
    font-weight: 700;
    color: var(--offblack);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin: 0 0 4px;
  }

  .rc-tip p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-warning {
    background: #FFF8E6;
    border: 1px solid var(--orange);
    border-radius: 14px;
    padding: 16px 20px;
    margin-bottom: 24px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .rc-wicon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .rc-warning p {
    font-size: 0.87rem;
    color: var(--darkgray);
    line-height: 1.55;
    margin: 0;
  }

  .rc-checklist {
    background: var(--offwhite);
    border-radius: 16px;
    border: 1px solid var(--lightgray);
    overflow: hidden;
    margin-bottom: 28px;
  }

  .rc-cl-header {
    padding: 16px 22px;
    border-bottom: 1px solid var(--brightgray);
    display: flex;
    align-items: center;
    gap: 10px;
    background: var(--offblack);
  }

  .rc-cl-header h3 {
    font-size: 0.88rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: var(--yellow);
    margin: 0;
  }

  .rc-cli {
    padding: 13px 22px;
    border-bottom: 1px solid var(--brightgray);
    display: flex;
    align-items: flex-start;
    gap: 14px;
  }

  .rc-cli:last-child {
    border-bottom: none;
  }

  .rc-cb {
    width: 22px;
    height: 22px;
    border-radius: 6px;
    border: 2px solid var(--lightgray);
    flex-shrink: 0;
    margin-top: 1px;
    background: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    color: var(--gray);
  }

  .rc-clab {
    font-size: 0.88rem;
    color: var(--darkgray);
    line-height: 1.4;
  }

  .rc-clab span {
    display: block;
    font-size: 0.78rem;
    color: var(--gray);
    margin-top: 2px;
  }

  .rc-phase-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: var(--offblack);
    color: var(--yellow);
    border-radius: 20px;
    padding: 4px 14px;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 20px;
  }

  .rc-wi {
    background: var(--offwhite);
    border-radius: 14px;
    padding: 20px;
    border: 1px solid var(--lightgray);
    text-align: center;
  }

  .rc-wi-icon {
    font-size: 30px;
    margin-bottom: 10px;
  }

  .rc-wi h4 {
    font-size: 0.88rem;
    font-weight: 700;
    margin: 0 0 5px;
    color: var(--offblack);
  }

  .rc-wi p {
    font-size: 0.8rem;
    color: var(--gray);
    line-height: 1.5;
    margin: 0;
  }

  .rc-sec-nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    margin-top: 24px;
    flex-wrap: wrap;
  }

  .rc-btn-prev,
  .rc-btn-next,
  .rc-link-btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: 11px 18px;
    border-radius: 10px;
    font-weight: 700;
    font-size: 0.88rem;
    text-decoration: none;
    border: 1px solid var(--lightgray);
  }

  .rc-btn-prev {
    background: #fff;
    color: var(--darkgray);
  }

  .rc-btn-next {
    background: var(--yellow);
    color: var(--offblack);
    border-color: var(--yellow);
  }

  .rc-link-btn {
    gap: 8px;
    background: var(--yellow);
    color: var(--offblack);
    margin: 0 8px 8px 0;
  }

  .rc-link-sec {
    background: var(--offwhite);
    color: var(--darkgray);
    border: 1px solid var(--lightgray);
  }

  .rc-link-sec:hover {
    background: var(--brightgray);
  }

  @media (max-width: 640px) {
    .rc-hero h1 { font-size: 1.7rem; }
    .rc-2col, .rc-3col { grid-template-columns: 1fr; }
    .rc-hero { padding: 36px 20px 32px; }
    .rc-hero-stats { gap: 20px; }
    .rc-nav, .rc-sec-nav, .rc-sec-header { flex-direction: column; }
    .rc-sec-nav { align-items: stretch; }
  }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">⚙️ Phase 1: Optimization</div>
    <h1>Navigate Launchpad</h1>
    <p>Your 90-day program to optimize, grow, and master your Recurly subscription business.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Week 4</div><div class="rc-lbl">Branding</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization</div></div>
      <div><div class="rc-num">~20</div><div class="rc-lbl">Min to Complete</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-welcome"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-dunning"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a class="rc-active" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-metrics"><span class="rc-snum">6</span>Metrics & Growth</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-phase-tag">⚙️ Phase 1 · Week 4 of 6</div>

    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎨</div>
      <div>
        <h2>Branding Your Emails &amp; Invoices</h2>
        <p>Every email and invoice Recurly sends on your behalf is a touchpoint with your subscriber. Make sure each one feels unmistakably like your brand.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🎯 Why Branding Matters in Recurly</h3>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When a subscriber receives a billing confirmation, a renewal reminder, or a failed payment alert, that communication either builds trust or undermines it. A generic, unbranded email can feel disposable or suspicious. A polished, recognizable email that matches your experience reinforces your identity and signals professionalism.</p>
      <p style="font-size:0.95rem;color:var(--darkgray);line-height:1.6;margin:0;">Consistent branding across your Recurly communications helps reduce confusion, improve engagement, and strengthen the subscriber relationship during some of the most sensitive moments in the lifecycle: billing, renewal, and payment recovery.</p>
    </div>

    <h3 class="rc-subhead">✨ The Business Impact of Branded Communications</h3>
    <div class="rc-3col">
      <div class="rc-wi">
        <div class="rc-wi-icon">🤝</div>
        <h4>Builds Trust</h4>
        <p>Subscribers recognize your brand in their inbox. Familiar, consistent messaging increases confidence and helps reduce disputes.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">📬</div>
        <h4>Improves Engagement</h4>
        <p>Branded emails are more likely to be opened, trusted, and acted on — especially when the message is tied to billing or renewal.</p>
      </div>
      <div class="rc-wi">
        <div class="rc-wi-icon">🎯</div>
        <h4>Supports Retention</h4>
        <p>Renewal reminders and failed payment emails are more effective when they feel like a natural extension of your product experience.</p>
      </div>
    </div>

    <h3 class="rc-subhead">📧 Priority 1: Brand Your Email Templates</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Navigate to Email Templates in Recurly</h3>
          <p>In your Recurly admin, go to <strong>Settings → Email Templates</strong>. This is where you can manage the transactional emails Recurly sends on your behalf.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Upload your logo</h3>
          <p>Add your company logo to the email header. Use a high-resolution PNG or SVG with a transparent background for best rendering across email clients.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Set your brand colors</h3>
          <p>Apply your primary brand color to the email header and buttons so your templates feel visually aligned with the rest of your customer experience.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Review and customize the copy</h3>
          <p>Read through the default content and update the tone, greeting style, and support language to better reflect your brand voice and customer experience.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Add support contact information</h3>
          <p>Make sure subscribers know how to reach you if they have a billing question. A clear support path helps reduce friction and builds confidence.</p>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">🧾 Priority 2: Customize Your Invoices</h3>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Go to Invoice Customization</h3>
          <p>Navigate to <strong>Settings → Invoice Customization</strong> to manage how invoices and receipts appear to subscribers.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Add your logo and business details</h3>
          <p>Confirm your company name, logo, and business information are accurate and customer-facing on every invoice sent from Recurly.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Add a custom footer message</h3>
          <p>Use the invoice footer for a thank-you message, support email, website URL, or any required legal or tax language relevant to your business.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Review line item descriptions</h3>
          <p>Make sure your plan names and invoice descriptions are subscriber-friendly and clear. Confusing labels can lead to disputes or support tickets.</p>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">⭐ The Emails That Matter Most</h3>
    <div class="rc-2col">
      <div class="rc-opt">
        <div class="rc-oicon">🎉</div>
        <h4>Subscription Confirmation</h4>
        <p>The first billing touchpoint after purchase. This should feel welcoming, polished, and aligned to your brand.</p>
        <span class="rc-tag">First Impression</span>
      </div>
      <div class="rc-opt">
        <div class="rc-oicon">🔔</div>
        <h4>Renewal Reminder</h4>
        <p>These messages help reduce confusion before billing. Strong branding makes the charge feel expected and legitimate.</p>
        <span class="rc-tag">Trust Builder</span>
      </div>
      <div class="rc-opt">
        <div class="rc-oicon">⚠️</div>
        <h4>Failed Payment Notice</h4>
        <p>This is one of your most important recovery emails. If it doesn't look like it came from you, subscribers may ignore it.</p>
        <span class="rc-tag">Revenue Critical</span>
      </div>
      <div class="rc-opt">
        <div class="rc-oicon">📄</div>
        <h4>Invoice / Receipt</h4>
        <p>Invoices are often saved, reviewed, or forwarded. A clear, professional invoice strengthens credibility and reduces disputes.</p>
        <span class="rc-tag">Operational Essential</span>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div>
        <h4>Pro Tip · Test Everything Before You Publish</h4>
        <p>After updating your templates, send test emails to yourself and review them on both desktop and mobile. Check logo rendering, spacing, button styling, and how the copy reads in a real inbox. A small formatting issue in Gmail or Outlook can have a big impact on trust.</p>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Don't stop at the confirmation email.</strong> Merchants often brand the welcome and billing confirmation emails but leave renewal reminders and failed payment notices untouched. Those are some of the most important emails in your lifecycle — and some of the most likely to affect revenue and retention.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Week 4 Checklist: Branding</h3></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Logo uploaded to email templates<span>Use a high-resolution image with a transparent background</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Brand colors applied to email templates<span>Match your primary brand palette where possible</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Email copy reviewed and updated<span>Especially confirmation, renewal reminder, and failed payment emails</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Support contact information added<span>Include a help link or direct support email</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Invoice customization completed<span>Logo, company details, and footer reviewed</span></div></div>
      <div class="rc-cli"><div class="rc-cb">✓</div><div class="rc-clab">Templates tested on desktop and mobile<span>Review in at least two email clients before finalizing</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-account-updater">← Account Updater</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/launchpad-gateway-failover">Next: Gateway Failover →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/invoice-customization" target="_blank" rel="noopener noreferrer">📖 Invoice Customization Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/email-notifications" target="_blank" rel="noopener noreferrer">📧 Email Notification Docs</a>
    <a class="rc-link-btn rc-link-sec" href="https://support.recurly.com" target="_blank" rel="noopener noreferrer">🎧 Recurly Support</a>
  </div>
</div>
</HTMLBlock>
`}</HTMLBlock>

<br />
