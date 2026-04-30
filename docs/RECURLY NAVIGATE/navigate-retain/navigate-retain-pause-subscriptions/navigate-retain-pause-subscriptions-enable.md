---
title: Pause API Test - Enable
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
    <p class="rc-subtitle">Learn how to enable, configure, and deploy the Pause Subscriptions feature to reduce voluntary churn.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable" class="is-active"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1spkzqq7q_IQuxDwLVmw2tFtrL3XQ3JWp" alt="tool" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0;">How to Enable It</h2>
        <p style="margin:4px 0 0; color:#807D73;">A step-by-step walkthrough for configuring Pause in Recurly, from admin settings to API integration.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Before You Begin: Prerequisites</h3>
      <p>Preparation is key. Ensure you have admin-level access, a clear list of plans that support pausing, and alignment on maximum pause durations. We also recommend having your email templates (Pause Initiated, Reminder, Welcome Back) drafted and ready before flipping the switch.</p>
    </div>

    <div class="rc-subhead">Step-by-Step: Enabling Pause in Recurly</div>
    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;"><h4>Navigate to Subscription Configuration</h4><p style="margin:0; font-size:14px; color:#32312D;">Go to <strong>Configuration → Subscriptions</strong>. This is where you manage the global settings governing how pause events behave across your site.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;"><h4>Understand the Pause Mechanism</h4><p style="margin:0; font-size:14px; color:#32312D;">Recurly uses <code>remaining_pause_cycles</code> to determine how many billing cycles to skip. During this time, the subscription is "frozen" and no invoices are generated.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;"><h4>Pause via the Admin UI</h4><p style="margin:0; font-size:14px; color:#32312D;">Find a specific subscription, click the <strong>Pause</strong> action button, and enter the cycle count. The state transitions to "paused" immediately.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;"><h4>Pause via the Recurly API</h4><p style="margin:0; font-size:14px; color:#32312D;">Send a <strong>PUT</strong> request to <code>/subscriptions/{id}/pause</code> with <code>remaining_pause_cycles</code>. This allows for dynamic, subscriber-driven pause experiences.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">5</div>
      <div style="flex:1;"><h4>Integrate into Cancel-Save Flows</h4><p style="margin:0; font-size:14px; color:#32312D;">The highest impact comes from offering pause as a prominent alternative when a user clicks "Cancel." This intercepts churn intent at the critical moment.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">6</div>
      <div style="flex:1;"><h4>Configure Subscriber Notifications</h4><p style="margin:0; font-size:14px; color:#32312D;">Set up confirmation and reminder emails (3-7 days before resume) to reduce surprise charges and support tickets.</p></div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Use Webhooks for Real-Time Sync</strong>
      <p style="margin:8px 0 0;">Subscribe to <code>subscription_paused</code> events to automatically adjust access permissions or CRM statuses in real-time without polling the API.</p>
    </div>

    <div class="rc-subhead">Configuring Pause Options: Best Practices</div>
    <div class="rc-2col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Structured Choice</h4>
        <p>Present 2–3 pre-defined durations (e.g., 1, 2, or 3 months) rather than free-form input to simplify the decision.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedo" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Max Duration Cap</h4>
        <p>Cap pauses at 3 cycles. Data shows reactivation rates drop significantly beyond 90 days of absence.</p>
      </div>
    </div>
    <div class="rc-2col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="limit" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Limit Frequency</h4>
        <p>Enforce policies like "one pause per year" to prevent subscribers from gaming the system indefinitely.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="access" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Partial Access</h4>
        <p>Maintain a touchpoint (read-only mode or archived content) during pause to keep your brand top-of-mind.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important: Revenue Recognition & Add-Ons</strong>
      <p style="margin:8px 0 0;">One-time charges already invoiced are not reversed. Ensure finance understands how recognized vs. deferred revenue is reported during pause cycles.</p>
    </div>

    <div class="rc-subhead">Quick-Reference: API Endpoints</div>
    <div class="rc-card">
      <p><strong>Pause:</strong> <code>PUT /subscriptions/{id}/pause</code> — Body: <code>{"remaining_pause_cycles": 2}</code></p>
      <p><strong>Resume Early:</strong> <code>PUT /subscriptions/{id}/resume</code> — No body required.</p>
      <p><strong>Status:</strong> <code>GET /subscriptions/{id}</code> — Returns <code>paused_at</code> and projected resume date.</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Launch Readiness Checklist</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Admin team has tested pause/resume in the Sandbox environment</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">API integration complete (pause, resume, and webhook listeners)</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Cancel-save flow updated with pause as a prominent alternative</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Email notifications (Initiated, Ending Soon, Resumed) configured</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Maximum pause duration and frequency rules enforced in logic</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Downstream systems (CRM, access control) synced via webhooks</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Finance team briefed on invoicing and revenue recognition impact</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Support team trained on UI pause/resume troubleshooting</label></div>
    </div>

    <div class="rc-tip">
      <strong>💡 Retention Flywheel Connection</strong>
      <p style="margin:8px 0 0;">Use Pause alongside Recurly's <strong>Advanced Dunning</strong> to recover subscribers who return with expired payment methods and <strong>Revenue Recovery</strong> to optimize the first resume charge.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 5 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data" class="rc-btn-next">Next: Tracking Impact →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Documentation</a>
    <a href="https://docs.recurly.com/reference" class="rc-link-btn">🔗 API Reference</a>
  </div>
</div>
`}</HTMLBlock>

<br />
