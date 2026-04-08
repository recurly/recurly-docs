---
title: 'Why use it? '
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<div id="pv-1" class="pv-panel"><style>
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
    <span class="rc-badge">Recurly Subscriptions</span>
    <h1>Save Your Revenue: Account Updater</h1>
    <p class="rc-subtitle">Learn how Account Updater helps reduce involuntary churn by automatically keeping card details current, so you never lose a subscriber to an expired or reissued card.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <div class="rc-nav">
    <a href="/docs/account-updater-1">
      <span class="rc-snum">1</span> What Is It?
    </a>
    <a href="/docs/account-updater-2" class="is-active">
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

  <div class="rc-sec">
    <div class="rc-sec-header">
      <!-- lightbulb-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb icon" style="width:28px;height:28px;"></div>
      <div>
        <h2>Why Use Account Updater?</h2>
        <p>Understand the business impact of outdated payment credentials and how Account Updater turns a retention liability into recovered revenue.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Hidden Revenue Leak You Can't Afford to Ignore</h3>
      <p>Every year, hundreds of millions of credit and debit cards are reissued worldwide. Banks replace cards when they expire, when fraud is detected, when accounts are upgraded, or simply as part of routine security cycles. Each time this happens, the card number, expiration date, or both change — and the billing information your subscription platform has on file becomes instantly outdated.</p>
      <p>For subscription businesses, outdated card details are the single largest driver of <strong>involuntary churn</strong>. Unlike voluntary churn — where a subscriber makes a conscious decision to cancel — involuntary churn happens silently. The subscriber still wants your product. They're still engaged. But their renewal payment fails because the card on file no longer works, and unless you recover that payment quickly, you lose the subscriber entirely.</p>
      <p>Industry data shows that involuntary churn accounts for <strong>20–40% of all subscriber losses</strong> for the average subscription business. That's revenue walking out the door with zero intent from the customer to leave. Account Updater addresses this problem at the source by proactively obtaining refreshed card credentials from card networks <em>before</em> the next billing cycle, so the payment processes successfully without subscriber intervention.</p>
    </div>

    <div class="rc-subhead">The Revenue Impact by the Numbers</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- wallet-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet icon" style="width:28px;height:28px;">
        <h4>Up to 12% Revenue Recovered</h4>
        <p>Merchants using Account Updater typically recover 8–12% of revenue that would otherwise be lost to failed payments from outdated cards.</p>
      </div>
      <div class="rc-wi">
        <!-- heart-hand.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="heart hand icon" style="width:28px;height:28px;">
        <h4>Reduced Subscriber Friction</h4>
        <p>Subscribers never have to manually update their card details, leading to seamless renewals and higher customer satisfaction scores.</p>
      </div>
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer icon" style="width:28px;height:28px;">
        <h4>Lower Dunning Load</h4>
        <p>Fewer failed transactions mean fewer dunning emails, fewer support tickets, and less operational overhead for your billing team.</p>
      </div>
    </div>

    <div class="rc-subhead">How Account Updater Fits Into Your Retention Strategy</div>

    <div class="rc-card">
      <h3>A Proactive Layer in Your Churn-Prevention Stack</h3>
      <p>Think of your retention toolkit as a series of safety nets. Dunning campaigns catch failed payments after they happen. Cancel-save flows intercept subscribers who are actively trying to leave. But Account Updater works <em>upstream</em> of both — it prevents the payment failure from occurring in the first place. This is why it's one of the highest-ROI retention features available in the Recurly platform.</p>
      <p>When Account Updater is enabled, Recurly periodically sends your stored card-on-file data to the card networks (Visa, Mastercard, American Express, and Discover). The networks check their databases for updated credentials — new card numbers, new expiration dates, or contact status changes — and return the refreshed information to Recurly. Your subscriber's billing info is updated automatically, with no action required from the subscriber or your team.</p>
      <p>This means your dunning campaigns only need to handle the <em>genuinely</em> problematic transactions — insufficient funds, fraud holds, or bank declines — rather than wasting cycles on simple expired-card scenarios. The result is a cleaner, more effective dunning process and a significantly lower involuntary churn rate.</p>
    </div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Prevents the Decline Before It Happens</h4>
          <p>Unlike reactive retry logic, Account Updater proactively refreshes card credentials days or weeks before a scheduled renewal. This means the transaction is submitted with valid details from the start, dramatically increasing first-attempt authorization rates.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Eliminates the "Update Your Card" Experience</h4>
          <p>Sending emails asking subscribers to log in and update their payment method creates friction and drop-off. Many subscribers never complete the update — not because they want to cancel, but because life gets in the way. Account Updater removes this hurdle entirely, keeping renewals seamless and invisible.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Compounds Over Time with Your Subscriber Base</h4>
          <p>The larger your subscriber base grows, the more cards expire each month, and the more revenue Account Updater protects. A business with 50,000 active subscribers can expect thousands of card updates per quarter — each one representing a renewal that would have otherwise required manual intervention or been lost.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Works Alongside Recurly's Revenue Recovery Suite</h4>
          <p>Account Updater complements Recurly's AI-powered revenue recovery, intelligent retries, and advanced dunning campaigns. Together, these tools form a comprehensive involuntary churn prevention system. Account Updater handles outdated credentials, while intelligent retries and dunning handle transient payment failures.</p>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Quantify Your Opportunity</strong>
      <p>To estimate how much revenue Account Updater could save you, look at your current decline rate for "card expired" or "invalid card number" reason codes in your Recurly dashboard. Multiply that transaction count by your average revenue per transaction. This gives you a rough floor for the revenue you're currently leaving on the table each month. Most merchants are surprised by how large this number is.</p>
    </div>

    <div class="rc-subhead">Real-World Retention Scenarios</div>

    <div class="rc-2col">
      <div class="rc-card">
        <h3>Scenario A: Annual Subscriber Renewal</h3>
        <p>A subscriber signed up 12 months ago with a credit card that has since been reissued by their bank due to a data breach. Without Account Updater, their $199/year renewal would fail. They'd receive a dunning email, but because it's a large annual charge, they might hesitate and never update — resulting in a lost subscriber worth $199+ in lifetime value.</p>
        <p>With Account Updater, Recurly already has the new card number. The renewal charges successfully on the first attempt. The subscriber doesn't even notice. Revenue retained.</p>
      </div>
      <div class="rc-card">
        <h3>Scenario B: Monthly SaaS at Scale</h3>
        <p>A SaaS company with 100,000 monthly subscribers processes renewals each billing cycle. Statistically, 2–3% of cards will have been reissued or expired in any given month. That's 2,000–3,000 potential failed transactions. At an average of $29/month, that represents $58,000–$87,000 in at-risk monthly revenue.</p>
        <p>With Account Updater recovering even 80% of those, the company saves $46,000–$70,000 per month — or over <strong>$550,000–$840,000 annually</strong> — with zero manual effort.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Confuse Account Updater with Payment Retries</strong>
      <p>Account Updater and intelligent payment retries are complementary but solve different problems. Account Updater fixes <em>credential</em> issues (expired/reissued cards) before the transaction is attempted. Payment retries address <em>transient</em> issues (insufficient funds, temporary bank holds) by reattempting the charge at optimal times. For maximum retention, you should have both enabled. Learn more about configuring dunning campaigns in the <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" style="color:var(--vermillion);font-weight:600;">Dunning Management documentation</a>.</p>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Self-Assessment: Is Account Updater Right for You?</div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c1">
        <label for="c1">You bill subscribers on a recurring basis (monthly, quarterly, or annually)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c2">
        <label for="c2">Your decline reports show "expired card" or "invalid card number" as a top decline reason</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c3">
        <label for="c3">You have subscribers on annual or multi-year plans (higher risk of card changes between renewals)</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c4">
        <label for="c4">Your dunning email open/click rates are declining, making manual card updates unreliable</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c5">
        <label for="c5">You're looking to reduce involuntary churn without adding engineering resources</label>
      </div>
      <div class="rc-cli">
        <input type="checkbox" class="rc-cb" id="c6">
        <label for="c6">You accept Visa, Mastercard, American Express, or Discover (Account Updater supports all four networks)</label>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Ready to See the Impact?</strong>
      <p>If you checked three or more boxes above, Account Updater is very likely to deliver meaningful revenue recovery for your business. Continue to the next section to learn about important considerations before enabling the feature, or skip ahead to <a href="/docs/account-updater-5" style="color:var(--vermillion);font-weight:600;">How to Enable It</a> if you're ready to get started right away.</p>
    </div>

  </div>

  <div class="rc-sec-nav">
    <a href="/docs/account-updater-1" class="rc-btn-prev">← Previous</a>
    <a href="/docs/account-updater-3" class="rc-btn-next">Next →</a>
  </div>

  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" class="rc-link-btn">📄 Account Updater Documentation</a>
    <a href="https://share.synthesia.io/2c1e1470-aa37-4474-a9d2-e6e1ef1e33e7" class="rc-link-btn">🎬 Account Updater Video Walkthrough</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/dunning-management" class="rc-link-btn">📄 Dunning Management Docs</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/revenue-recovery" class="rc-link-btn">📄 Revenue Recovery Overview</a>
    <a href="https://navigate.recurly.com/event-hub/" class="rc-link-btn">📅 Navigate Weekly Global Office Hours</a>
    <a href="mailto:support@recurly.com" class="rc-link-btn">✉️ Contact Support</a>
  </div>

</div></div>
`}</HTMLBlock>

<br />
