---
title: Account Updater
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Preview: Account Updater</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"><style>*, *::before, *::after { box-sizing: border-box; }body { margin: 0; background: #f5f5f0; font-family: Inter, -apple-system, sans-serif; }.pv-bar { position: sticky; top: 0; z-index: 1000; background: #0D0D0B; padding: 10px 16px; display: flex; gap: 6px; overflow-x: auto; align-items: center; }.pv-bar::before { content: "PREVIEW"; color: #FFD706; font-size: 11px; font-weight: 700; letter-spacing: 1px; margin-right: 8px; flex-shrink: 0; }.pv-tab { padding: 7px 14px; border-radius: 6px; color: #CCC9B8; background: transparent; border: 1px solid transparent; cursor: pointer; font-size: 12px; font-family: Inter, sans-serif; white-space: nowrap; transition: all 0.15s; }.pv-tab:hover { background: #32312D; color: #FFFDF2; }.pv-tab.active { background: #FFD706; color: #0D0D0B; font-weight: 600; border-color: #FFD706; }.pv-panel { display: none; padding: 32px 16px; }.pv-panel.active { display: block; }</style></head><body><div class="pv-bar"><button class="pv-tab active" data-tab="pv-0">1. What Is It?</button><button class="pv-tab" data-tab="pv-1">2. Why Use It?</button><button class="pv-tab" data-tab="pv-2">3. Things to Consider</button><button class="pv-tab" data-tab="pv-3">4. When Not to Use It</button><button class="pv-tab" data-tab="pv-4">5. How to Enable It</button><button class="pv-tab" data-tab="pv-5">6. Tracking Impact</button><button class="pv-tab" data-tab="pv-6">7. Pitch to Leadership</button></div><div id="pv-0" class="pv-panel active"><style>
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
    <span class="rc-badge">Recurly Subscriptions</span>
    <h1>Save Your Revenue: Account Updater</h1>
    <p class="rc-subtitle">Learn how Account Updater automatically keeps payment credentials current, reducing involuntary churn and protecting your recurring revenue.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
  </div>

  <!-- 2. TAB NAVIGATION -->
  <div class="rc-nav">
    <a href="/docs/account-updater-1" class="is-active">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/account-updater-2">
      <span class="rc-snum">2</span> Why Use It?
    </a>
    <a href="/docs/account-updater-3">
      <span class="rc-snum">3</span> Things to Consider
    </a>
    <a href="/docs/account-updater-4">
      <span class="rc-snum">4</span> When Not to Use It
    </a>
    <a href="/docs/account-updater-5">
      <span class="rc-snum">5</span> How to Enable It
    </a>
    <a href="/docs/account-updater-6">
      <span class="rc-snum">6</span> Tracking Impact
    </a>
    <a href="/docs/account-updater-7">
      <span class="rc-snum">7</span> Pitch to Leadership
    </a>
  </div>

  <!-- 3. SECTION HEADER & CONTENT -->
  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- credit-card-refresh.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="credit-card-refresh" style="width:28px;height:28px;"></div>
      <div>
        <h2>What Is Account Updater?</h2>
        <p>Understand the feature, how it works behind the scenes, and why it's a critical part of your retention toolkit.</p>
      </div>
    </div>

    <!-- MAIN CONTENT -->

    <div class="rc-card">
      <h3>Account Updater in Plain Terms</h3>
      <p>Every year, hundreds of millions of credit and debit cards are replaced. Cards expire on schedule. Banks reissue cards after fraud detection. Financial institutions merge and reassign account numbers. For subscription businesses, every one of these events is a ticking time bomb: the next time you attempt to charge that subscriber, the transaction will decline — not because the customer wants to leave, but because their payment details are stale.</p>
      <p><strong>Account Updater</strong> is a service offered by major card networks (Visa, Mastercard, American Express, and Discover) that automatically refreshes stored card credentials before a payment failure ever occurs. When enabled in Recurly, Account Updater proactively queries the card networks for updated card numbers, expiration dates, and card status changes, then silently applies those updates to your subscribers' billing information.</p>
      <p>The result? Payments that would have failed instead succeed on the first attempt. Your subscribers remain active. Your revenue keeps flowing. And your support team never has to chase a customer down to ask for a new card number.</p>
    </div>

    <div class="rc-subhead">How It Works: The Lifecycle</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Recurly Sends a Batch Request</h4>
          <p>On a regular cadence, Recurly compiles a list of stored card credentials across your active subscriber base and submits them to the card networks' Account Updater services via your payment gateway. This happens automatically — no action is required from you or your subscribers.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Card Networks Respond with Updates</h4>
          <p>The card networks check their records and return one of several responses: an updated card number, a new expiration date, a notification that the account has been closed, or confirmation that no changes are needed. Visa Account Updater (VAU), Mastercard Automatic Billing Updater (ABU), Amex Cardrefresher, and Discover Network Account Updater each handle this slightly differently, but Recurly normalizes all responses into a single workflow.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Recurly Applies the Updates Silently</h4>
          <p>When fresh credentials are returned, Recurly updates the billing information stored on the subscriber's account automatically. The subscriber is never interrupted, never emailed about a card change, and never asked to log in and re-enter payment details. The update happens entirely behind the scenes.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Next Invoice Charges Successfully</h4>
          <p>When the subscriber's next billing cycle arrives, Recurly charges the updated card credentials. Because the details are current, the transaction succeeds on the first attempt — avoiding a decline that would otherwise trigger your dunning campaign and potentially result in involuntary churn.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Key Insight</strong>
      <p>Account Updater is <em>proactive</em>, not reactive. Unlike dunning campaigns — which kick in <em>after</em> a payment fails — Account Updater prevents the failure from ever happening in the first place. Think of it as the first line of defense in your retention strategy, working upstream of dunning, retry logic, and cancel-save flows.</p>
    </div>

    <div class="rc-subhead">What Gets Updated?</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <h4>Card Number</h4>
        <p>When a bank reissues a card with a new PAN (Primary Account Number), Account Updater captures and applies the replacement number automatically.</p>
      </div>
      <div class="rc-wi">
        <h4>Expiration Date</h4>
        <p>When a card is renewed with a new expiration date — the most common update — the new date is applied so future charges succeed.</p>
      </div>
      <div class="rc-wi">
        <h4>Account Status</h4>
        <p>If a card account has been permanently closed by the issuing bank, Account Updater returns a "closed" status so Recurly can handle it appropriately.</p>
      </div>
    </div>

    <div class="rc-subhead">Where Account Updater Fits in Your Retention Stack</div>

    <div class="rc-card">
      <h3>Part of a Layered Retention Strategy</h3>
      <p>Recurly's retention capabilities are designed to work together as a layered defense against churn. Account Updater sits at the very top of this stack — it's the <strong>preventive</strong> layer that stops problems before they start. Here's how it relates to the other tools in your arsenal:</p>
      <p><strong>Layer 1 — Account Updater (Preventive):</strong> Keeps credentials current so charges succeed on the first attempt. No subscriber friction whatsoever.</p>
      <p><strong>Layer 2 — Intelligent Retries (Reactive - Automated):</strong> If a charge does fail, Recurly's machine-learning-powered retry engine determines the optimal time and conditions to reattempt the transaction, maximizing recovery without manual intervention.</p>
      <p><strong>Layer 3 — Dunning Campaigns (Reactive - Communication):</strong> For transactions that continue to fail, dunning emails notify subscribers and prompt them to update their payment details. Recurly allows you to customize the timing, frequency, and messaging of these campaigns.</p>
      <p><strong>Layer 4 — Cancel-Save Flows (Last Resort):</strong> If a subscriber's payment cannot be recovered, cancel-save offers — such as plan downgrades, pauses, or discounts — give them a reason to stay before their subscription is terminated.</p>
      <p>Account Updater reduces the volume of failures that ever reach Layers 2–4, which means your dunning emails fire less often, your support load decreases, and more subscribers stay active without ever knowing there was a potential problem.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important Limitation</strong>
      <p>Account Updater only works with card-based payment methods (credit and debit cards). It does not update ACH bank account details, PayPal tokens, Amazon Pay, Apple Pay, or other alternative payment methods. If a significant portion of your subscriber base pays via non-card methods, Account Updater will not cover those accounts. We'll discuss this more in the "When Not to Use It" section.</p>
    </div>

    <div class="rc-subhead">Supported Card Networks</div>

    <div class="rc-2col">
      <div class="rc-wi">
        <h4>Visa & Mastercard</h4>
        <p>Full support via Visa Account Updater (VAU) and Mastercard Automatic Billing Updater (ABU). These two networks represent the vast majority of card-on-file updates globally.</p>
      </div>
      <div class="rc-wi">
        <h4>American Express & Discover</h4>
        <p>Amex Cardrefresher and Discover Network Account Updater are also supported. Coverage varies by gateway and region — consult your gateway's documentation for specifics.</p>
      </div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Recap: Key Takeaways from This Section</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="ck1">
        <label for="ck1">Account Updater automatically refreshes stored card credentials by querying the card networks on a regular cadence.</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="ck2">
        <label for="ck2">It updates card numbers, expiration dates, and account statuses — silently, with zero subscriber friction.</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="ck3">
        <label for="ck3">It is a preventive tool that reduces payment failures before they trigger dunning or retries.</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="ck4">
        <label for="ck4">It supports Visa, Mastercard, American Express, and Discover — but not non-card payment methods.</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="ck5">
        <label for="ck5">It works best as part of a layered retention strategy alongside intelligent retries, dunning, and cancel-save flows.</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Ready to learn more?</strong>
      <p>Now that you understand what Account Updater is and how it works, head to the next section to explore <strong>why</strong> enabling it can have a measurable impact on your revenue retention and subscriber longevity.</p>
    </div>

  </div>

  <!-- 5. BACK/NEXT NAVIGATION -->
  <div class="rc-sec-nav">
    <a href="#" class="rc-btn-prev rc-btn-disabled">← Previous</a>
    <a href="/docs/account-updater-2" class="rc-btn-next">Next: Why Use It? →</a>
  </div>

  <!-- 6. ADDITIONAL RESOURCES -->
  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" class="rc-link-btn">📄 Account Updater Documentation</a>
    <a href="https://share.synthesia.io/2c1e1470-aa37-4474-a9d2-e6e1ef1e33e7" class="rc-link-btn">🎬 Account Updater Video Walkthrough</a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-link-btn">📅 Navigate Weekly Global Office Hours</a>
    <a href="mailto:support@recurly.com" class="rc-link-btn">💬 Contact Support</a>
  </div></div></div>
`}</HTMLBlock>

<br />
