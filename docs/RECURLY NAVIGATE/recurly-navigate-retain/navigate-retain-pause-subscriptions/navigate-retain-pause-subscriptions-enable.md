---
title: Pause API Test - Enable
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<div id="pv-4" class="pv-panel"><style>
:root {
  --yellow: #FFD706;
  --orange: #FF8200;
  --vermillion: #FF5810;
  --salmon: #FF9D88;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
}
.rc-guide { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; color: var(--offblack); max-width: 900px; margin: 0 auto; }
.rc-hero { background: var(--offblack); color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
.rc-subtitle { color: var(--lightgray); font-size: 16px; }
.rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; }
.rc-flywheel-launch { background: var(--lightgray); color: var(--offblack); }
.rc-flywheel-acquire { background: var(--yellow); color: var(--offblack); }
.rc-flywheel-retain { background: var(--salmon); color: var(--offblack); }
.rc-flywheel-scale { background: var(--orange); color: var(--offblack); }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
.rc-stat { color: var(--lightgray); font-size: 14px; }
.rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
.rc-nav { display: flex; gap: 0; background: var(--brightgray); padding: 0; overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: var(--offblack); background: var(--offwhite); }
.rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
.rc-sec { padding: 40px; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
.rc-sec-header h2 { font-size: 24px; margin: 0 0 4px; font-weight: 700; }
.rc-sec-header p { color: var(--gray); margin: 0; font-size: 15px; }
.rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
.rc-card p:last-child { margin-bottom: 0; }
.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: var(--offblack); }
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin: 20px 0; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: var(--offwhite); border-radius: 12px; padding: 20px; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0; }
.rc-step-content h4 { margin: 0 0 4px; font-size: 16px; font-weight: 600; }
.rc-step-content p { margin: 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-tip strong { color: var(--offblack); }
.rc-tip p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
.rc-warning strong { color: var(--offblack); }
.rc-warning p { margin: 4px 0 0; color: var(--darkgray); font-size: 14px; line-height: 1.6; }
.rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
.rc-cl-header { font-size: 16px; font-weight: 600; margin-bottom: 16px; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 20px; height: 20px; border-radius: 4px; border: 2px solid var(--lightgray); flex-shrink: 0; cursor: pointer; margin-top: 2px; }
.rc-cli label { font-size: 14px; color: var(--darkgray); line-height: 1.5; cursor: pointer; }
.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
.rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: var(--gray); margin: 0; }
.rc-sec-nav { display: flex; justify-content: space-between; padding: 0 40px 40px; }
.rc-btn-prev, .rc-btn-next { display: inline-flex; align-items: center; gap: 8px; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; transition: all 0.2s; }
.rc-btn-prev { background: var(--brightgray); color: var(--offblack); }
.rc-btn-next { background: var(--yellow); color: var(--offblack); }
.rc-btn-prev:hover { background: var(--lightgray); }
.rc-btn-next:hover { filter: brightness(0.95); }
.rc-btn-disabled { opacity: 0.4; pointer-events: none; }
.rc-link-btn { display: inline-flex; align-items: center; gap: 8px; padding: 10px 20px; background: var(--brightgray); border-radius: 8px; text-decoration: none; color: var(--offblack); font-size: 14px; font-weight: 500; margin: 4px; transition: all 0.2s; }
.rc-link-btn:hover { background: var(--lightgray); }
.rc-link-sec { padding: 32px 40px; background: var(--brightgray); border-radius: 0 0 16px 16px; }
.rc-link-sec h3 { font-size: 18px; margin: 0 0 16px; font-weight: 600; }
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn how to enable, configure, and deploy the Pause Subscriptions feature to reduce voluntary churn and keep subscribers in your ecosystem.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-5" class="is-active">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- tool-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1spkzqq7q_IQuxDwLVmw2tFtrL3XQ3JWp" alt="tool-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>How to Enable It</h2>
        <p>A step-by-step walkthrough for configuring the Pause Subscriptions feature in Recurly, from admin settings through API integration and subscriber-facing deployment.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Before You Begin: Prerequisites</h3>
      <p>Enabling the Pause Subscriptions feature in Recurly is straightforward, but a little preparation goes a long way. Before you start flipping switches, make sure you have the following in place: admin-level access to your Recurly site, a clear understanding of which subscription plans should support pausing, and alignment with your team on maximum pause durations and any business rules you want to enforce. If you plan to surface the pause option through a self-service portal or cancel-save flow, coordinate with your development team so front-end work can happen in parallel with back-end configuration.</p>
      <p>It's also wise to have your subscriber communication templates ready—email notifications that confirm a pause has been initiated, remind subscribers when their pause is about to end, and welcome them back when their subscription resumes. Getting these drafted ahead of time means you can launch the full experience without gaps.</p>
    </div>

    <div class="rc-subhead">Step-by-Step: Enabling Pause in Recurly</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Navigate to Subscription Configuration</h4>
          <p>Log in to your Recurly admin dashboard with admin privileges. Go to <strong>Configuration → Subscriptions</strong>. This is where you manage the global settings that govern how subscription lifecycle events—including pauses—behave across your site. Familiarize yourself with your current plan structures, as pause settings apply at the subscription level, not the plan level.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Understand the Pause Mechanism</h4>
          <p>In Recurly, pausing a subscription works by setting a <strong>remaining_pause_cycles</strong> value on an active subscription. This tells Recurly how many billing cycles to skip before automatically resuming. During the paused period, no invoices are generated and the subscriber's billing is frozen. The subscription state transitions to "paused" and will automatically return to "active" once the pause cycles are exhausted—or you can resume it early via the admin UI or API.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Pause a Subscription via the Admin UI</h4>
          <p>For individual subscribers, navigate to <strong>Subscriptions</strong> in the left sidebar, find the target subscription, and open its detail page. Click the <strong>Pause</strong> action button. You'll be prompted to enter the number of billing cycles to pause. For example, entering "2" on a monthly plan means the subscriber skips two months of billing. Confirm the action, and the subscription immediately transitions to the paused state. The subscriber will not be billed again until the pause period expires or you manually resume.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Pause via the Recurly API</h4>
          <p>For programmatic control—especially if you're integrating pause into a cancel-save flow or self-service portal—use the Recurly API. Send a <strong>PUT</strong> request to <code>/subscriptions/{subscription_id}/pause</code> with a JSON body specifying <code>remaining_pause_cycles</code>. The API responds with the updated subscription object showing the new paused state. To resume early, send a <strong>PUT</strong> request to <code>/subscriptions/{subscription_id}/resume</code>. This flexibility lets you build dynamic experiences where subscribers choose their own pause duration from a set of options you define.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Integrate into Your Cancel-Save Flow</h4>
          <p>The highest-impact deployment is embedding pause as an option within your cancellation flow. When a subscriber clicks "Cancel," present pause as a prominent alternative—e.g., "Not ready to commit? Pause your subscription for 1–3 months instead." Use the API to execute the pause based on the subscriber's selection. This is where pause becomes a powerful retention tool: it intercepts churn intent at the exact moment it happens and offers a lower-friction alternative that keeps the subscriber relationship intact.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">6</div>
        <div class="rc-step-content">
          <h4>Configure Subscriber Notifications</h4>
          <p>Set up automated email notifications for key pause lifecycle events. At minimum, configure messages for: <strong>Pause Initiated</strong> (confirming the pause and expected resume date), <strong>Pause Ending Soon</strong> (sent 3–7 days before resumption as a courtesy reminder), and <strong>Subscription Resumed</strong> (confirming the subscription is active again and the next billing date). These communications reduce surprise charges, build trust, and lower support ticket volume. You can configure these in Recurly's email notification settings or through your own email platform using webhooks.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Use Webhooks for Real-Time Sync</strong>
      <p>Subscribe to the <code>subscription_paused</code> and <code>subscription_resumed</code> webhook events to keep your internal systems in sync. This is critical if you need to adjust access permissions, update a CRM record, trigger marketing automation sequences, or notify a fulfillment system to stop shipments during the pause window. Webhooks ensure your entire tech stack responds instantly to pause state changes without polling the API.</p>
    </div>

    <div class="rc-subhead">Configuring Pause Options: Best Practices</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- package-check.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=14XOgUOyBDzpi-vHu0sBtN12cv23Z4Ds7" alt="package-check" style="width:28px;height:28px;">
        <h4>Offer Structured Choices</h4>
        <p>Rather than a free-form input, present 2–3 pre-defined pause durations (e.g., 1 month, 2 months, 3 months). This simplifies the decision for the subscriber and lets you control the maximum absence window.</p>
      </div>
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer-04" style="width:28px;height:28px;">
        <h4>Set a Maximum Pause Duration</h4>
        <p>Cap pause at 3 billing cycles for most businesses. Data shows that subscribers who pause beyond 3 months have significantly lower reactivation rates. A cap protects revenue while still offering meaningful flexibility.</p>
      </div>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- bell-ringing-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell-ringing-01" style="width:28px;height:28px;">
        <h4>Limit Pause Frequency</h4>
        <p>Consider enforcing a policy like "one pause per 12 months" to prevent subscribers from cycling between paused and active states indefinitely. You can enforce this in your application logic using the subscription's pause history.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart-hand" style="width:28px;height:28px;">
        <h4>Maintain Partial Access</h4>
        <p>Decide whether paused subscribers retain limited access to your product (read-only mode, archived content, community forums). Maintaining a touchpoint during pause keeps your brand top-of-mind and improves resume rates.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important: Revenue Recognition & Add-Ons</strong>
      <p>When a subscription is paused, no invoices are generated for that subscription's base charge. However, be aware that any one-time charges or usage-based add-ons that were already invoiced will not be reversed. Additionally, if your business has revenue recognition requirements, ensure your finance team understands how pause cycles affect recognized vs. deferred revenue reporting. Coordinate with your accounting team before enabling pause at scale to avoid reporting surprises.</p>
    </div>

    <div class="rc-subhead">Quick-Reference: API Endpoints</div>

    <div class="rc-card">
      <h3>Essential API Calls for Pause</h3>
      <p><strong>Pause a subscription:</strong> <code>PUT /subscriptions/{subscription_id}/pause</code> — Body: <code>{ "remaining_pause_cycles": 2 }</code></p>
      <p><strong>Resume a paused subscription:</strong> <code>PUT /subscriptions/{subscription_id}/resume</code> — No body required. The subscription immediately returns to active and the next billing date is set.</p>
      <p><strong>Check pause status:</strong> <code>GET /subscriptions/{subscription_id}</code> — The response includes <code>paused_at</code>, <code>remaining_pause_cycles</code>, and the projected <code>current_period_ends_at</code> for resume timing.</p>
      <p><strong>Webhook events to subscribe to:</strong> <code>subscription_paused</code>, <code>subscription_resumed</code>, <code>subscription_pause_modified</code> (if the remaining cycles are adjusted mid-pause).</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Launch Readiness Checklist</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check1">
        <label for="check1">Admin team has tested pausing and resuming a subscription in your Recurly sandbox environment</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check2">
        <label for="check2">API integration is complete and tested (pause, resume, and webhook handling)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check3">
        <label for="check3">Cancel-save flow updated to present pause as a prominent alternative to cancellation</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check4">
        <label for="check4">Email notifications configured for pause initiated, pause ending soon, and subscription resumed</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check5">
        <label for="check5">Maximum pause duration and frequency rules defined and enforced in application logic</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check6">
        <label for="check6">Internal systems (CRM, fulfillment, access control) integrated via webhooks to respond to pause state changes</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check7">
        <label for="check7">Finance and accounting teams briefed on how paused subscriptions affect invoicing and revenue recognition</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="check8">
        <label for="check8">Customer support team trained on how to pause, resume, and troubleshoot paused subscriptions in the admin UI</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Retention Flywheel Connection</strong>
      <p>Pause Subscriptions is most powerful when combined with Recurly's other retention-stage features. Use it alongside <strong>cancel-save flows</strong> to intercept churn intent, <strong>advanced dunning campaigns</strong> to recover subscribers who return from pause with expired payment methods, and <strong>AI/ML revenue recovery</strong> to intelligently retry the first billing attempt when a subscription resumes. Together, these tools form a comprehensive retention strategy that minimizes both voluntary and involuntary churn.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/recurly-s-pause-subscriptions-feature-4" class="rc-btn-prev">← Previous</a>
    <a href="/docs/recurly-s-pause-subscriptions-feature-6" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Pause Subscription Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Pause Subscriptions Video Walkthrough</a>
    <a href="https://docs.recurly.com/reference" class="rc-link-btn">🔗 Recurly API Reference</a>
  </div>

</div></div>
`}</HTMLBlock>

<br />
