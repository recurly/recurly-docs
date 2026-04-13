---
title: Pause API Test - Considerations
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. MASTER PAGE OVERRIDES */
body, .theme-doc, .main-content { background-color: #F5F5F0 !important; }
.rc-guide { font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; max-width: 900px; margin: 0 auto; background: #F5F5F0; }

/* 2. HERO SECTION */
.rc-hero { background: #0D0D0B; color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; position: relative; overflow: hidden; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('https://drive.google.com/thumbnail?sz=w1000&id=1gLpfq5s-rR8anlQVCGhpNTPzPopYdPEd'); opacity: 0.1; pointer-events: none; }
.rc-badge { background: #FFD706; color: #0D0D0B; padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; position: relative; z-index: 1; }
.rc-subtitle { color: #CCC9B8; font-size: 16px; margin: 0; position: relative; z-index: 1; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: #FF9D88; color: #0D0D0B; position: relative; z-index: 1; }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; position: relative; z-index: 1; }
.rc-stat { color: #CCC9B8; font-size: 14px; }
.rc-stat-num { color: #FFD706; font-weight: 700; font-size: 20px; display: block; }

/* 3. NAVIGATION */
.rc-nav { display: flex; background: #F1EFE3; padding: 0; overflow-x: auto; border-bottom: 2px solid #CCC9B8; }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: #807D73; font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: #0D0D0B; background: #FFFDF2; }
.rc-nav a.is-active { color: #0D0D0B; font-weight: 600; border-bottom-color: #FFD706; background: #F5F5F0; }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: #CCC9B8; color: #807D73; display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #FFD706; color: #0D0D0B; }

/* 4. CONTENT AREA */
.rc-sec { padding: 40px; background: #F5F5F0; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: #FFD706; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-card { background: #F1EFE3; border-radius: 12px; padding: 28px; margin-bottom: 20px; border: 1px solid #CCC9B8; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: #32312D; line-height: 1.7; margin: 0 0 12px; font-size: 15px; }

.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: #0D0D0B; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: #F1EFE3; border-radius: 12px; padding: 20px; margin-bottom: 16px; border: 1px solid #CCC9B8; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: #FFD706; color: #0D0D0B; display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }

.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0; }
.rc-wi { background: #F1EFE3; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: #807D73; margin: 0; }

.rc-checklist { background: #F1EFE3; border-radius: 12px; padding: 24px; margin: 20px 0; border: 1px solid #CCC9B8; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 18px; height: 18px; border-radius: 4px; border: 2px solid #CCC9B8; flex-shrink: 0; margin-top: 3px; background: white; }

.rc-tip { border-left: 4px solid #FFD706; background: #F1EFE3; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FFD706; }
.rc-warning { border-left: 4px solid #FF8200; background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FF8200; }

.rc-sec-nav { display: flex; justify-content: space-between; padding: 24px 40px 40px; align-items: center; background: #F5F5F0; }
.rc-btn-prev { background: #F1EFE3; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #CCC9B8; }
.rc-btn-next { background: #FFD706; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #FFD706; }

.rc-link-sec { padding: 32px 40px; background: #F1EFE3; border-top: 1px solid #CCC9B8; border-radius: 0 0 16px 16px; }
.rc-link-btn { display: inline-flex; align-items: center; background: #ffffff; border: 1px solid #CCC9B8; padding: 10px 20px; border-radius: 8px; text-decoration: none; color: #0D0D0B; font-size: 14px; font-weight: 500; margin: 4px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of immediate cancellation.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations" class="is-active"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0;">Things to Consider</h2>
        <p style="margin:4px 0 0; color:#807D73;">Before enabling pause, understand the billing mechanics, subscriber experience implications, and strategic decisions.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Pause Is a Retention Strategy — Not Just a Feature Toggle</h3>
      <p>Turning on the pause feature in Recurly takes minutes. But deploying it as an effective churn-reduction strategy requires thoughtful planning. A poorly configured pause experience can create confusion for subscribers or complicate your revenue forecasting. These considerations will help you protect subscriber lifetime value rather than simply deferring cancellations.</p>
    </div>

    <div class="rc-subhead">Billing & Revenue Implications</div>
    <div class="rc-2col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Revenue Deferral</h4>
        <p>While paused, no invoices are generated. Ensure your finance team understands the distinction between "churned revenue" and "paused revenue."</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="card" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Method Freshness</h4>
        <p>Extended pauses risk card expiration. Use Recurly's Account Updater to keep billing details fresh during the gap.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠ Revenue Recognition Impact</strong>
      <p style="margin:8px 0 0;">Since no performance obligation is being fulfilled during the pause period, no revenue should be recognized. Work with finance to ensure your accounting system handles paused states correctly.</p>
    </div>

    <div class="rc-subhead">Pause Duration Strategy</div>
    <div class="rc-card">
      <h3>How Long Should You Allow Pauses?</h3>
      <p>Too short a window may frustrate subscribers; too long a window risks disengagement. Industry data suggests that subscribers who pause for more than 90 days resume at significantly lower rates than those pausing for 30–60 days.</p>
    </div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;"><h4>Define your maximum window</h4><p style="margin:0; font-size:14px; color:#32312D;">Most successful implementations cap pauses at 1–3 billing cycles. For monthly plans, this means 1–3 months.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;"><h4>Decide on subscriber choice</h4><p style="margin:0; font-size:14px; color:#32312D;">You can offer a fixed pause length ("1 month") or let subscribers choose from predefined options ("1, 2, or 3 months").</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;"><h4>Set repeat-pause policies</h4><p style="margin:0; font-size:14px; color:#32312D;">Consider implementing a cooldown period — for example, requiring at least two active cycles between pauses.</p></div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with a Re-Engagement Campaign</strong>
      <p style="margin:8px 0 0;">The pause period is not a dead zone. Use Recurly's webhooks (<code>subscription_paused</code>) to trigger emails that share new content or features released during their absence.</p>
    </div>

    <div class="rc-subhead">Subscriber Experience & Access</div>
    <div class="rc-3col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Clarity</h4>
        <p>Subscribers must understand when billing resumes. Ambiguity leads to disputes.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Access</h4>
        <p>Decide whether paused users retain limited service access or a clean cutoff.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="hand" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Resume</h4>
        <p>Automatic resumption must be clearly communicated to avoid surprise charges.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Access & Entitlement Management</h3>
      <p>Your application must enforce access rules based on the <code>paused</code> state. Options include <strong>Full Cutoff</strong> (strong incentive to resume), <strong>Degraded Access</strong> (preserves engagement), or <strong>Full access until period ends</strong> (most subscriber-friendly default).</p>
    </div>

    <div class="rc-subhead">Operational & Integration</div>
    <div class="rc-card">
      <h3>Downstream System Impact</h3>
      <p>Consider how the paused state flows to your CRM, data warehouse, and email platforms. Recurly fires webhooks (<code>subscription_pause_modified</code>) to help you keep these systems in sync without manual effort.</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Pre-Launch Readiness Checklist</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Defined maximum pause duration and documented policy</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Decided on repeat-pause guardrails (cooldown or annual cap)</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Determined subscriber access level during the pause period</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Mapped all downstream systems that consume subscription state</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Configured webhook listeners for pause and resume events</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Created subscriber-facing pause and resume reminder emails</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Aligned with finance on MRR and revenue recognition reporting</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Tested full pause-to-resume lifecycle in Recurly Sandbox</label></div>
    </div>

    <div class="rc-tip">
      <strong>💡 Think Like a Cancel-Save Flow</strong>
      <p style="margin:8px 0 0;">Surface pause as the primary alternative during your cancellation flow: "Not ready to commit? Pause your subscription instead." This framing leverages loss aversion to drive retention.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 3 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit" class="rc-btn-next">Next: When Not to Use It →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Video Walkthrough</a>
  </div>
</div>
`}</HTMLBlock>

<br />
