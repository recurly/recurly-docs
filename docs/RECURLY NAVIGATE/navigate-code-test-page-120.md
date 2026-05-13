---
title: Navigate Code Test Page 120
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Dunning Management 101 — How to Enable It</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"></head><body style="background:#f5f5f0;margin:0;"><style>
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

  <!-- 1. HERO SECTION -->
  <div class="rc-hero">
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;">
    <span class="rc-badge">Subscriptions</span>
    <h1>Dunning Management 101</h1>
    <p class="rc-subtitle">Master dunning configuration to reduce involuntary churn and maximize revenue recovery across your subscription base.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <!-- 2. TAB NAVIGATION -->
  <div class="rc-nav">
    <a href="/docs/dunning-management-101-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/dunning-management-101-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/dunning-management-101-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/dunning-management-101-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/dunning-management-101-5" class="is-active">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/dunning-management-101-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/dunning-management-101-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <!-- 3. SECTION HEADER & CONTENT -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- tool-02.svg (configuration, setup) -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1spkzqq7q_IQuxDwLVmw2tFtrL3XQ3JWp" alt="tool-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>How to Enable It</h2>
        <p>A step-by-step guide to configuring dunning campaigns in Recurly, from extending your dunning window to customizing email templates and setting up Webhooks.</p>
      </div>
    </div>

    <!-- INTRO CARD -->
    <div class="rc-card">
      <h3>Before You Begin: Planning Your Dunning Configuration</h3>
      <p>Configuring dunning in Recurly is not simply a matter of flipping a switch. Effective setup requires alignment between your billing team, your marketing or retention team, and your engineering team. Before touching any settings, gather three critical pieces of information: your current involuntary churn rate (the percentage of subscribers lost to failed payments), your average payment recovery timeline (how many days it typically takes to recover a failed payment today), and the email assets you want to deploy (branded templates, value-reminder copy, urgency-escalation messaging).</p>
      <p>Recurly's dunning engine is designed to give you maximum flexibility. You can create multiple dunning campaigns and assign different plans to different campaigns, which means your premium subscribers can receive a longer, more patient recovery sequence while trial-to-paid conversions might receive a more aggressive cadence. The goal of this section is to walk you through every step so that you can launch or optimize your dunning setup with confidence.</p>
    </div>

    <!-- STEP-BY-STEP: Creating Your Dunning Campaign -->
    <div class="rc-subhead">Step 1: Create and Configure a Dunning Campaign</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Navigate to Dunning Campaigns</h4>
          <p>In your Recurly admin dashboard, go to <strong>Configuration → Dunning Campaigns</strong>. You will see any existing campaigns listed here. If this is your first time, you'll see the default campaign that ships with every Recurly account. Click <strong>"New Dunning Campaign"</strong> to create a custom campaign, or click into the default campaign to modify it.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Set Your Dunning Window Length</h4>
          <p>This is the single highest-impact decision you will make. The dunning window defines how many days Recurly will continue attempting to recover a failed payment before canceling the subscription. Recurly's data shows that extending to a <strong>minimum of 14 days</strong> significantly improves recovery rates—many merchants see optimal results between 14 and 28 days. If you're currently running a window shorter than 14 days, extending it is the single fastest way to recover more revenue. Set the <strong>"Total dunning period"</strong> field to your desired number of days.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Define Your Retry Schedule</h4>
          <p>Within your dunning window, configure the specific days on which Recurly will reattempt the charge. A proven cadence is: Day 0 (initial failure), Day 1, Day 3, Day 5, Day 7, Day 10, and Day 14. This front-loads retries while the card issue is most likely to be resolved quickly (e.g., temporary holds, daily limits), then spaces them out to catch issuer-side corrections like card reissuances. If you're using Recurly's AI-powered Smart Retries, you can let the system intelligently choose optimal retry times—but you still define the overall window and maximum number of attempts.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Assign Plans to the Campaign</h4>
          <p>Under the campaign's <strong>"Plan Assignments"</strong> section, select which subscription plans should use this dunning campaign. This is where segmentation becomes powerful. For example, assign your highest-value annual plans to a campaign with a 28-day window and more personalized emails, while monthly self-serve plans might use a 14-day campaign with a more automated approach. Any plan not explicitly assigned will fall back to the default campaign.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Start with the default campaign</strong>
      <p>If you're optimizing for the first time, start by modifying the default dunning campaign rather than creating multiple campaigns. Extend the window to at least 14 days, add 5–7 retry attempts, and monitor for 30 days. Once you have baseline recovery data, create segmented campaigns for different plan tiers. This phased approach avoids the complexity of managing multiple campaigns before you understand your recovery patterns.</p>
    </div>

    <!-- STEP 2: Email Configuration -->
    <div class="rc-subhead">Step 2: Configure Dunning Email Templates</div>

    <div class="rc-card">
      <h3>Setting Up Your Email Sequence</h3>
      <p>Dunning emails are your primary communication channel with subscribers whose payments have failed. In Recurly, navigate to <strong>Configuration → Dunning Campaigns → [Your Campaign] → Email Settings</strong> to configure the email sequence. You can define which days within the dunning window trigger an email, customize the subject line and body content for each email, and toggle individual emails on or off.</p>
      <p>A best-practice email sequence typically includes three to four emails with escalating urgency. The first email (sent on Day 0 or Day 1) should be informational and helpful—"Your payment didn't go through. Here's how to update your card." The second email (around Day 5) should remind the subscriber of the value they'll lose. The third email (around Day 10) should introduce urgency—"Your subscription will be canceled in X days." If you're running a longer window, a final email one to two days before cancellation serves as a last-chance alert.</p>
    </div>

    <div class="rc-2col">
      <div class="rc-wi">
        <!-- lightbulb-02.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb-02" style="width:28px;height:28px;">
        <h4>Email Best Practices</h4>
        <p>Use your brand's voice and design. Include a direct "Update Payment" link. Remind subscribers what they'll lose (features, content, streaks). Avoid generic "payment failed" language—frame it as helping them keep their subscription.</p>
      </div>
      <div class="rc-wi">
        <!-- dataflow-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1lfc7n8_25KJpRsQRuBvrLmGBgJrUo_T5" alt="dataflow-01" style="width:28px;height:28px;">
        <h4>Email Deliverability</h4>
        <p>Configure SPF, DKIM, and DMARC records for your sending domain. Emails that land in spam folders cannot recover revenue. Work with your engineering team to authenticate your domain and verify delivery rates before going live.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Skip Email Authentication</strong>
      <p>One of the most common reasons dunning campaigns underperform is that emails never reach the subscriber's inbox. If you haven't set up SPF, DKIM, and DMARC records for the domain Recurly sends from, a significant percentage of your dunning emails may be filtered as spam. This is a technical prerequisite that should be completed before you launch any dunning campaign. Coordinate with your engineering team or DNS administrator to add the necessary records—Recurly's documentation provides the exact values to configure.</p>
    </div>

    <!-- STEP 3: Webhooks & In-App -->
    <div class="rc-subhead">Step 3: Set Up Webhooks and In-App Notifications</div>

    <div class="rc-card">
      <h3>Extending Dunning Beyond Email</h3>
      <p>Email alone won't recover every failed payment. Subscribers may not open emails, or the email may not reach them at all. This is where Webhooks and in-app notifications become critical. Recurly fires Webhooks for key dunning lifecycle events, and your engineering team can use these to trigger complementary recovery flows within your application.</p>
      <p>The most important Webhooks to subscribe to are: <strong>past_due_invoice_notification</strong> (fired when an invoice enters past-due status), <strong>subscription_past_due_notification</strong> (fired when a subscription enters the dunning state), and <strong>subscription_canceled_notification</strong> (fired when dunning exhausts and the subscription is canceled). By listening for the <code>subscription_past_due</code> event, your application can display an in-app banner or modal prompting the subscriber to update their payment method. This is especially effective for SaaS and streaming services where subscribers are actively using the product.</p>
    </div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">A</div>
        <div class="rc-step-content">
          <h4>Configure Webhook Endpoints</h4>
          <p>In Recurly, go to <strong>Developers → Webhooks</strong> and add your endpoint URL. Select the dunning-related events you want to receive. Ensure your endpoint returns a 200 status code promptly—Recurly will retry failed deliveries, but a consistently unresponsive endpoint may be disabled. Use HTTPS and validate the webhook signature to ensure authenticity.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">B</div>
        <div class="rc-step-content">
          <h4>Build In-App Payment Update Prompts</h4>
          <p>When your application receives a <code>past_due</code> webhook, display a non-dismissible banner or inline alert on the subscriber's dashboard: "Your payment method needs updating. Update now to keep your subscription active." Link directly to Recurly's hosted payment page or an embedded card-update form. This approach is one of the most effective recovery mechanisms because it reaches subscribers in the moment they're actively engaged with your product.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">C</div>
        <div class="rc-step-content">
          <h4>Decouple Dunning from Product Access</h4>
          <p>A critical product decision: should subscribers in dunning retain access to your product? Recurly gives you this control. By default, a subscription in the <code>past_due</code> state is still active—subscribers can continue using your product until the dunning window expires and the subscription is canceled. This is generally the recommended approach, as cutting access immediately increases voluntary churn (angry subscribers who cancel intentionally). However, you may want to implement a degraded experience—read-only mode, feature gating, or gentle reminders—to motivate payment updates without fully locking users out.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: SMS and Push Notifications</strong>
      <p>If you have subscribers' mobile numbers or a native app with push notification capability, use webhooks to trigger SMS or push alerts in addition to email. Multi-channel dunning campaigns consistently outperform email-only approaches. A simple push notification—"Your subscription payment failed. Tap to update your card"—can recover payments that would otherwise slip through the cracks.</p>
    </div>

    <!-- STEP 4: Advanced Configuration -->
    <div class="rc-subhead">Step 4: Advanced Configuration Options</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- credit-card-refresh.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="credit-card-refresh" style="width:28px;height:28px;">
        <h4>Account Updater</h4>
        <p>Enable Account Updater on all active gateways. This automatically refreshes expired or reissued card details before they cause a decline, preventing many payment failures from entering dunning at all.</p>
      </div>
      <div class="rc-wi">
        <!-- zap-fast.png -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1xtd2ZKYQKsV-6RL5nJKhNoyVhRAdunRG" alt="zap-fast" style="width:28px;height:28px;">
        <h4>Smart Retries</h4>
        <p>If available on your plan, enable Recurly's AI-powered Smart Retries. The ML model analyzes transaction patterns across the Recurly network to select the optimal time and day for each retry attempt, significantly improving recovery rates beyond fixed-schedule retries.</p>
      </div>
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet-01" style="width:28px;height:28px;">
        <h4>Backup Payment Methods</h4>
        <p>Encourage subscribers to add a secondary payment method. Recurly can automatically attempt the backup method when the primary fails, dramatically reducing the number of subscriptions that enter extended dunning cycles.</p>
      </div>
    </div>

    <!-- LAUNCH CHECKLIST -->
    <div class="rc-subhead">Pre-Launch Checklist</div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Complete these items before activating your dunning campaign</div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Dunning window extended to at least 14 days (consider 21–28 days for high-value plans)</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Retry schedule configured with 5–7 attempts spread across the dunning window</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Email templates customized with brand voice, value reminders, and direct "Update Payment" links</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>SPF, DKIM, and DMARC records configured and validated for your sending domain</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Webhook endpoints configured and tested for past_due and subscription_canceled events</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>In-app payment update banner or modal implemented and tested in staging</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Account Updater enabled on all active gateways</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Plans assigned to the appropriate dunning campaigns (segmented by tier if applicable)</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Product access policy during dunning defined and communicated to engineering team</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>Baseline involuntary churn rate documented for before/after comparison</label>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Test Before You Go Live</strong>
      <p>Always test your dunning configuration in Recurly's sandbox environment before applying changes to production. Send test dunning emails to verify formatting, link accuracy, and deliverability. Trigger test webhooks to confirm your application responds correctly. A misconfigured dunning campaign can silently lose revenue for weeks before anyone notices. Schedule a review of your dunning metrics 7, 14, and 30 days after launch to validate performance.</p>
    </div>

  </div>

  <!-- 5. BACK/NEXT NAVIGATION -->
  <div class="rc-sec-nav">
    <a href="/docs/dunning-management-101-4" class="rc-btn-prev">← Previous</a>
    <a href="/docs/dunning-management-101-6" class="rc-btn-next">Next →</a>
  </div>

  <!-- 6. ADDITIONAL RESOURCES -->
  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.google.com/document/d/126f5qxy8Ss4YfFpwZfebQgEHYBgj0f9t6NPOUbhuUBU/edit?tab=t.0" class="rc-link-btn">📄 Dunning Management Documentation</a>
    <a href="https://docs.recurly.com/docs/dunning" class="rc-link-btn">📘 Recurly Dunning Docs</a>
    <a href="https://docs.recurly.com/docs/webhooks" class="rc-link-btn">🔗 Webhook Configuration Guide</a>
    <a href="https://docs.recurly.com/docs/email-settings" class="rc-link-btn">✉️ Email Deliverability Setup</a>
  </div>

</div></body></html>
`}</HTMLBlock>

<br />
