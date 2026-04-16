---
title: Dunning - API TEST
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><title>Dunning Management 101 — What Is It?</title><link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet"></head><body style="background:#f5f5f0;margin:0;"><style>
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
    <p class="rc-subtitle">Master the art and science of recovering failed payments to reduce involuntary churn and protect your recurring revenue.</p>
    <div class="rc-flywheel-badge rc-flywheel-retain">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
  </div>

  <!-- 2. TAB NAVIGATION -->
  <div class="rc-nav">
    <a href="/docs/dunning-management-101-1" class="is-active">
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
    <a href="/docs/dunning-management-101-5">
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
      <!-- graduation-hat-02.svg -->
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1mpEetd7RMUJzX9FlSiPMxbwe0myetA1e" alt="graduation-hat-02" style="width:28px;height:28px;"></div>
      <div>
        <h2>What Is Dunning Management?</h2>
        <p>Understand the fundamentals of dunning, why payment failures happen, and how Recurly's dunning campaigns systematically recover revenue that would otherwise be lost.</p>
      </div>
    </div>

    <!-- INTRO CARD -->
    <div class="rc-card">
      <h3>The Silent Revenue Killer: Involuntary Churn</h3>
      <p>Not every lost subscriber chooses to leave. In fact, a significant portion of churn — often estimated between 20% and 40% of total churn for subscription businesses — is <strong>involuntary</strong>. These are subscribers who never clicked "cancel." Instead, their payment simply failed. An expired credit card, a maxed-out spending limit, a temporary bank hold, or an incorrect billing address quietly disrupted the billing cycle, and without intervention, the subscription lapses.</p>
      <p>This is the problem that <strong>dunning management</strong> solves. The term "dunning" comes from the 17th-century English word "dun," meaning to make persistent demands for payment. In the context of modern subscription commerce, dunning management is the automated process of detecting a failed payment, retrying the transaction at strategic intervals, notifying the subscriber, and ultimately either recovering the payment or gracefully handling the subscription's end.</p>
      <p>Without a well-configured dunning strategy, every failed transaction is essentially a coin flip: either the subscriber happens to update their payment method on their own, or they churn silently — often without even realizing their subscription has lapsed. For businesses operating at scale, that coin flip can translate to millions of dollars in lost annual recurring revenue (ARR).</p>
    </div>

    <!-- HOW DUNNING WORKS: STEPS -->
    <div class="rc-subhead">How Dunning Works: The Lifecycle of a Failed Payment</div>

    <div class="rc-steps">
      <div class="rc-step">
        <div class="rc-sbadge">1</div>
        <div class="rc-step-content">
          <h4>Payment Failure Detected</h4>
          <p>When a recurring billing attempt fails — whether due to insufficient funds, an expired card, a hard decline from the issuing bank, or a fraud flag — Recurly captures the decline code and categorizes the failure type. This classification is critical because different failure types require different recovery strategies. A "soft decline" (temporary issue) should be retried quickly, while a "hard decline" (card permanently invalid) may require immediate subscriber outreach.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">2</div>
        <div class="rc-step-content">
          <h4>Dunning Campaign Activates</h4>
          <p>The subscription enters a <strong>dunning cycle</strong> — a pre-configured sequence of retry attempts and subscriber communications. In Recurly, this is managed through <strong>Dunning Campaigns</strong>, which define the total dunning window (how many days to keep trying), the retry schedule (which days to re-attempt the charge), and which email notifications to send at each stage. You can create multiple campaigns and assign them to specific plans, giving you granular control over how different subscriber segments are handled.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">3</div>
        <div class="rc-step-content">
          <h4>Automated Retries Execute</h4>
          <p>Recurly's retry logic attempts the charge again on the days you've specified in your dunning campaign. For merchants leveraging Recurly's <strong>AI/ML-powered revenue recovery</strong> (sometimes called "intelligent retries" or "Revenue Optimization"), the system goes further: it uses machine learning models trained on billions of transactions to determine the <em>optimal time and day</em> to retry each individual transaction, significantly increasing the probability of success compared to a static schedule.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">4</div>
        <div class="rc-step-content">
          <h4>Subscriber Notifications Sent</h4>
          <p>Throughout the dunning window, the subscriber receives email communications alerting them to the payment issue. These emails serve two purposes: first, they prompt the subscriber to update their payment information if the issue is on their end (e.g., an expired card); second, they create a sense of urgency to prevent lapsed access to the product. Effective dunning emails are not generic payment reminders — they are branded, empathetic, and escalate in tone from gentle notification to urgent final warning.</p>
        </div>
      </div>
      <div class="rc-step">
        <div class="rc-sbadge">5</div>
        <div class="rc-step-content">
          <h4>Resolution: Recovery or Expiration</h4>
          <p>The dunning cycle ends in one of two outcomes. <strong>Recovery:</strong> the payment succeeds on a retry attempt, or the subscriber manually updates their payment method and the charge goes through — the subscription continues seamlessly. <strong>Expiration:</strong> the dunning window closes without a successful payment, and the subscription is either canceled or paused based on your configuration. In Recurly, you control what happens at end-of-dunning: full cancellation, a move to a paused state, or a downgrade to a free tier.</p>
        </div>
      </div>
    </div>

    <!-- KEY CONCEPTS -->
    <div class="rc-subhead">Key Concepts You Need to Know</div>

    <div class="rc-3col">
      <div class="rc-wi">
        <!-- credit-card-refresh.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=12qo_Yniga9UwiJZatUOP62u7SRF9Yqno" alt="credit-card-refresh" style="width:28px;height:28px;">
        <h4>Dunning Window</h4>
        <p>The total number of days Recurly will continue retrying a failed payment before taking final action. Recurly supports windows up to 49 days. Longer windows generally recover more revenue.</p>
      </div>
      <div class="rc-wi">
        <!-- bell-ringing-01.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="bell-ringing-01" style="width:28px;height:28px;">
        <h4>Dunning Campaign</h4>
        <p>A named configuration that defines your retry schedule, email cadence, and end-of-dunning behavior. You can create multiple campaigns and assign each to different subscription plans.</p>
      </div>
      <div class="rc-wi">
        <!-- speedometer-04.svg -->
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="speedometer-04" style="width:28px;height:28px;">
        <h4>Recovery Rate</h4>
        <p>The percentage of failed transactions that are ultimately collected during the dunning cycle. This is the primary metric for measuring dunning effectiveness and should be tracked over time.</p>
      </div>
    </div>

    <!-- VOLUNTARY VS INVOLUNTARY CHURN -->
    <div class="rc-subhead">Voluntary vs. Involuntary Churn</div>

    <div class="rc-2col">
      <div class="rc-card">
        <h3>Voluntary Churn</h3>
        <p>The subscriber <strong>actively decides</strong> to cancel. They may be dissatisfied with the product, found a competitor, or simply no longer need the service. Addressing voluntary churn requires product improvements, retention offers, and cancel-save flows.</p>
        <p>Dunning management does <strong>not</strong> address voluntary churn directly. However, a poorly handled dunning process can <em>convert</em> an involuntary churn event into voluntary churn — if subscribers feel frustrated or confused by payment failure communications, they may choose not to re-subscribe.</p>
      </div>
      <div class="rc-card">
        <h3>Involuntary Churn</h3>
        <p>The subscriber's payment fails and the subscription lapses <strong>without the subscriber's intent</strong>. Common causes include expired cards, insufficient funds, bank-initiated declines, and outdated billing information. This is entirely preventable with the right dunning strategy.</p>
        <p>Involuntary churn typically accounts for <strong>20–40% of total churn</strong> for subscription businesses. Because these subscribers never intended to leave, the recovery potential is enormous — and it's where dunning management delivers its highest ROI.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Dunning Is a Retention Strategy, Not Just a Billing Feature</strong>
      <p>Think of dunning as the first line of defense in your retention toolkit. It sits alongside cancel-save flows and win-back campaigns as a core mechanism for reducing churn. The best-performing merchants treat dunning emails as branded touchpoints — not transactional system messages — and coordinate their dunning strategy with their broader customer lifecycle communications.</p>
    </div>

    <!-- WHAT MAKES RECURLY'S APPROACH DIFFERENT -->
    <div class="rc-subhead">What Makes Recurly's Dunning Different?</div>

    <div class="rc-card">
      <h3>Beyond Static Retries: AI/ML-Powered Revenue Recovery</h3>
      <p>Most billing platforms offer basic dunning: set a retry schedule, send some emails, and hope for the best. Recurly goes significantly further with its <strong>machine learning-powered revenue recovery engine</strong>. Trained on data from thousands of merchants and billions of transactions, Recurly's AI models analyze patterns across decline codes, card types, issuing banks, geographic regions, time of day, and day of week to determine the <em>optimal moment</em> to retry each individual failed transaction.</p>
      <p>This means two subscribers with the exact same plan could have their retries executed at different times — because the model identified that one subscriber's issuing bank has higher approval rates on Tuesday mornings, while the other's tends to clear holds by Friday afternoons. This level of intelligence is not something you can replicate with a manual retry schedule, no matter how carefully you craft it.</p>
      <p>In addition to intelligent retries, Recurly's dunning system supports <strong>multiple concurrent dunning campaigns</strong>, allowing you to tailor the dunning experience by plan, subscriber segment, or revenue tier. A $9.99/month consumer subscriber might receive a friendly 14-day dunning sequence, while a $499/month enterprise account might trigger an immediate internal alert and a personalized outreach cadence managed by your Customer Success team.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Common Misconception: "Our Default Settings Are Good Enough"</strong>
      <p>Many merchants never customize their dunning configuration beyond Recurly's defaults. While the defaults are a reasonable starting point, they are not optimized for your specific subscriber base, payment mix, or business model. Throughout this course, you'll learn how extending your dunning window, customizing your email cadence, and leveraging advanced features can materially increase your recovery rate — often by several percentage points, which at scale translates to significant recovered revenue.</p>
    </div>

    <!-- QUICK REFERENCE CHECKLIST -->
    <div class="rc-checklist">
      <div class="rc-cl-header">Quick Reference: Dunning Fundamentals Checklist</div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I understand the difference between voluntary and involuntary churn</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I can define "dunning window" and explain why its length matters</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I know that Recurly supports multiple dunning campaigns for different plans</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I understand how AI/ML-powered retries differ from static retry schedules</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I recognize that dunning emails are a retention touchpoint, not just a system notification</label>
      </div>
      <div class="rc-cli">
        <div class="rc-cb"></div>
        <label>I know the five stages of the dunning lifecycle: detect, activate, retry, notify, resolve</label>
      </div>
    </div>

  </div>

  <!-- 5. BACK/NEXT NAVIGATION -->
  <div class="rc-sec-nav">
    <a href="#" class="rc-btn-prev rc-btn-disabled">&larr; Previous</a>
    <a href="/docs/dunning-management-101-2" class="rc-btn-next">Next &rarr;</a>
  </div>

  <!-- 6. ADDITIONAL RESOURCES -->
  <div class="rc-link-sec">
    <h3>Additional Resources</h3>
    <a href="https://docs.google.com/document/d/126f5qxy8Ss4YfFpwZfebQgEHYBgj0f9t6NPOUbhuUBU/edit?tab=t.0" class="rc-link-btn">📄 Dunning Management Documentation</a>
    <a href="https://recurly.com/research/churn-rate-guide/" class="rc-link-btn">📊 Recurly Churn Rate Guide</a>
    <a href="https://docs.recurly.com/docs/dunning" class="rc-link-btn">🔧 Recurly Dunning Configuration Docs</a>
  </div>

</div></body></html>
`}</HTMLBlock>

<br />
