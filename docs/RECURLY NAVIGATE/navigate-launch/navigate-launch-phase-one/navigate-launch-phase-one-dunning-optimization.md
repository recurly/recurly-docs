---
title: 'Section 2: Dunning Optimization'
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
.rc-deep-dive{background:var(--offblack);border-radius:14px;padding:20px 22px;margin-bottom:18px;display:flex;align-items:flex-start;gap:16px}
.rc-deep-dive h4{font-size:.96rem;font-weight:800;color:var(--yellow);margin:0 0 6px}
.rc-deep-dive p{font-size:.86rem;color:#CCC9B8;margin:0 0 14px;line-height:1.5}
.rc-webinar-btn{display:inline-flex;align-items:center;gap:7px;padding:10px 18px;border-radius:9px;background:var(--orange);color:#fff;font-weight:700;font-size:.86rem;text-decoration:none;border:none}
.rc-webinar-btn:hover{opacity:.9;text-decoration:none}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none}
.rc-link-btn{background:var(--yellow);color:var(--offblack);border-color:var(--yellow);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}.rc-deep-dive{flex-direction:column}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate · Launchpad Phase 1</div>
    <h1>Optimize Your Dunning Strategy</h1>
    <p>A smart dunning strategy is one of the most impactful things you can do to recover failed payments and reduce involuntary churn automatically.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">Step 2</div><div class="rc-lbl">Phase 1</div></div>
      <div><div class="rc-num">27%</div><div class="rc-lbl">Avg Recovery Rate</div></div>
      <div><div class="rc-num">Auto</div><div class="rc-lbl">Revenue Recovery</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization" class="rc-active"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔄</div>
      <div>
        <h2>What Is Dunning — and Why Does It Matter?</h2>
        <p>Dunning is the automated process of retrying failed payments and communicating with subscribers when a charge doesn't go through. A well-configured dunning strategy silently saves revenue you'd otherwise lose to card declines, expiries, and insufficient funds.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Dunning Done Right</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/7f58d816-a65c-42f4-950d-59b11953d1aa" loading="lazy" title="Navigate Launchpad — Dunning Optimization" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">Learn how to configure Recurly's dunning settings for maximum payment recovery — including retry schedules, email templates, and subscriber communication best practices.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">💡 Why Dunning Is Worth Getting Right Early</p>
      <div class="rc-2col">
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Failed payments are common</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Industry-wide, 5–10% of subscription payments fail on first attempt. Without dunning, each of those is a lost subscriber.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Intelligent Retries run automatically</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Recurly's Intelligent Retry logic is built into the dunning system and active by default. It uses machine learning from billions of transactions to pick the optimal retry time for each subscriber — no setup required.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Window length matters</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">For monthly subscriptions, Recurly recommends a dunning window of no longer than 27 days. This maximizes the number of Intelligent Retry attempts while preventing subscribers from receiving a second invoice.</p>
        </div>
        <div>
          <p style="font-size:.87rem;font-weight:700;color:var(--offblack);margin:0 0 5px">Emails keep subscribers engaged</p>
          <p style="font-size:.84rem;color:var(--gray);line-height:1.5;margin:0">Dunning emails prompt subscribers to update their payment method — a critical second line of defense for invoices that retries can't recover on their own.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Intelligent Retries are always on:</strong> You do not need to enable Intelligent Retries separately. They are part of Recurly's dunning engine and run automatically on every failed invoice that enters a dunning campaign. Your job is to configure the campaign settings around them — window length, email sequence, and expiration behavior.
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">🪜 Step-by-Step: Configure Your Dunning Campaign</p>
    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div>
          <h3>Open Dunning Management</h3>
          <p>In your Recurly admin, navigate to <strong>Configuration → Dunning Management</strong>. You'll see your default dunning campaign. Every Recurly account has a default campaign — your goal is to optimize its settings.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div>
          <h3>Set your dunning window length</h3>
          <p>Configure the total length of your dunning cycle. For monthly subscriptions, Recurly recommends a maximum of <strong>27 days</strong> and <strong>60 days</strong> for plans that are two months or longer. This gives Intelligent Retries the maximum number of attempts while preventing a second invoice from generating before the subscription expires.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div>
          <h3>Configure your dunning email sequence</h3>
          <p>Set up 2–4 dunning emails spaced throughout your window. The first should go out promptly on failure; subsequent emails should become progressively more urgent. Each email must include a direct link for the subscriber to update their payment method — this drives self-serve recovery.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div>
          <h3>Set your expiration behavior</h3>
          <p>Decide what happens when a dunning cycle ends without recovery: cancel the subscription immediately, or move it to a past-due grace period to give the subscriber more time. For high-value subscribers, most merchants prefer to keep the subscription active and the invoice open.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div>
          <h3>Consider multiple campaigns for different plans</h3>
          <p>Recurly supports multiple dunning campaigns (available on Pro and Enterprise plans). You can assign different campaigns to specific plans or accounts — for example, a longer, more generous campaign for your highest-tier plan. Contact your CSM to discuss if this is right for your setup.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Best Practice:</strong> Pair dunning with Account Updater (Step 3) for maximum recovery. Account Updater proactively updates expired or replaced card details before the invoice even fails — reducing how many payments enter dunning in the first place.
    </div>
    <div class="rc-deep-dive">
      <div style="font-size:26px;flex-shrink:0;margin-top:2px">🎧</div>
      <div>
        <h4>Recommended Deep Dive: Dunning Optimization Webinar</h4>
        <p>Want to go further? Watch the Navigate Dunning Optimization webinar for a complete walkthrough of recovery strategy best practices — including how to benchmark your Dunning Recovery Rate against industry peers and identify opportunities to improve. Use the <strong>Dunning Optimization Checklist</strong> below to follow along and ensure you've optimized your setup.</p>
        <a class="rc-webinar-btn" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">▶ Watch the Dunning Optimization Webinar</a>
      </div>
    </div>
    <p class="rc-subhead" style="margin-bottom:12px">✅ Dunning Optimization Checklist</p>
    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>Complete Before Moving to Account Updater</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Match your branding across all dunning emails.<span>Ensure your email design, colors, fonts, and tone align with the rest of your brand communications to build trust and credibility.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Adjust your Dunning window length, and space out messages.<span>Aim for a 27-day window for monthly plans or up to 60 days for subscriptions two months or longer to allow for retries and customer action. Additionally leave at least 3-4 days between emails.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use different email templates and tones.<span>Customize each dunning email with a unique message and tone to keep customers engaged and avoid sounding repetitive.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Let customers know when their account will close.<span>Be transparent about how many days are left before their account is suspended or canceled.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Remind customers why your product is valuable.<span>Reiterate the benefits they’ll lose, like access, pricing, features, or user perks, to create urgency and FOMO.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Offer helpful CTAs beyond just “update billing."<span>Include links to FAQs, support, live chat, community, or even offer a pause option — make it easy for them to get help.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Build urgency into subject lines and copy.<span>Gradually increase urgency in your messaging as the dunning cycle progresses. For example, “Last Chance,” “Don’t Lose Access.”.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Set up multiple campaigns for different user groups.<span>Tailor your dunning strategy by plan type or audience — monthly vs. annual, enterprise vs. individual, etc.</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Use the right email delivery method.<span>Choose the best option for your business, whether that’s Recurly’s default service or a custom setup using Sendgrid, Mailchimp, or Braze, for more control and visibility.</span></div></div>			<div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Add an in-app or onsite ‘Payment Overdue’ banner.<span>Catch users who don’t open emails by showing a prominent message in your product or app with a link to update billing.</span></div></div>
	</div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing">← Production Testing</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater">Step 3: Account Updater →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" target="_blank" rel="noopener noreferrer">📖 Dunning Management Docs</a>
      <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/docs/retry-logic" target="_blank" rel="noopener noreferrer">🔁 Intelligent Retries Docs</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">✉ Contact Customer Success</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
