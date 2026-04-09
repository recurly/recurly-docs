---
title: Pause API Test 2
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>1. What Is It? | Pause Subscriptions</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --yellow: #FFD706; --orange: #FF8200; --vermillion: #FF5810; --salmon: #FF9D88;
            --offblack: #0D0D0B; --darkgray: #32312D; --gray: #807D73; --lightgray: #CCC9B8;
            --brightgray: #F1EFE3; --offwhite: #FFFDF2;
        }
        body { margin: 0; background: #f5f5f0; font-family: 'Inter', -apple-system, sans-serif; color: var(--offblack); }
        .rc-guide { max-width: 900px; margin: 20px auto; background: white; border-radius: 16px; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.05); }
        .rc-hero { background: var(--offblack); color: white; padding: 48px 40px; text-align: center; }
        .rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
        .rc-subtitle { color: var(--lightgray); font-size: 16px; }
        .rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
        .rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: var(--salmon); color: var(--offblack); }
        .rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; }
        .rc-stat { color: var(--lightgray); font-size: 14px; }
        .rc-stat-num { color: var(--yellow); font-weight: 700; font-size: 20px; display: block; }
        .rc-nav { display: flex; background: var(--brightgray); overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
        .rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; }
        .rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
        .rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
        .rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
        .rc-sec { padding: 40px; }
        .rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
        .rc-sec-icon { width: 48px; height: 48px; background: var(--yellow); border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 24px; flex-shrink: 0; }
        .rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
        .rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
        .rc-card p { color: var(--darkgray); line-height: 1.7; margin: 0 0 12px; font-size: 15px; }
        .rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; }
        .rc-steps { display: flex; flex-direction: column; gap: 16px; }
        .rc-step { display: flex; gap: 16px; background: var(--offwhite); border-radius: 12px; padding: 20px; }
        .rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }
        .rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
        .rc-2col { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; margin: 20px 0; }
        .rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
        .rc-sec-nav { display: flex; justify-content: space-between; padding: 40px; background: #fafafa; border-top: 1px solid var(--lightgray); }
        .rc-btn-next { background: var(--yellow); color: var(--offblack); padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; }
        .rc-checklist { background: var(--offwhite); border-radius: 12px; padding: 24px; margin: 20px 0; }
        .rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
        .rc-warning { border-left: 4px solid var(--orange); background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
    </style>
</head>
<body>
<div class="rc-guide">
    <div class="rc-hero">
        <span class="rc-badge">Subscriptions</span>
        <h1>Pause, Not Cancel</h1>
        <p class="rc-subtitle">Decrease voluntary churn by offering subscribers a pause option instead of forcing a binary stay-or-cancel decision.</p>
        <div class="rc-flywheel-badge">RETAIN</div>
        <div class="rc-stats">
            <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
            <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
        </div>
    </div>
    <div class="rc-nav">
        <a href="page1.html" class="is-active"><span class="rc-snum">1</span> What Is It?</a>
        <a href="page2.html"><span class="rc-snum">2</span> Why Use It?</a>
        <a href="page3.html"><span class="rc-snum">3</span> Things to Consider</a>
        <a href="page4.html"><span class="rc-snum">4</span> When Not to Use It</a>
        <a href="page5.html"><span class="rc-snum">5</span> How to Enable It</a>
        <a href="page6.html"><span class="rc-snum">6</span> Tracking Impact</a>
        <a href="page7.html"><span class="rc-snum">7</span> Pitch to Leadership</a>
    </div>
    <div class="rc-sec">
        <div class="rc-sec-header">
            <div class="rc-sec-icon">📦</div>
            <div>
                <h2>What Is Pause Subscriptions?</h2>
                <p>Understand how Recurly's Pause feature works and why it's a powerful retention tool in your churn-reduction toolkit.</p>
            </div>
        </div>
        <div class="rc-card">
            <h3>The Pause Concept in a Nutshell</h3>
            <p>Recurly's Pause Subscriptions feature lets you temporarily halt a subscriber's billing cycle without canceling their subscription. Instead of losing a subscriber entirely when they need a break—whether due to travel, seasonal usage patterns, budget constraints, or simply wanting time away—you give them a middle option. The subscription enters a paused state: no invoices are generated, no charges occur, and the subscriber's account remains intact. When the pause period ends (or the subscriber decides to come back early), billing resumes automatically on the next renewal date.</p>
            <p>Think of it this way: cancellation is a door that's hard to reopen. A pause is a bookmark—the subscriber's place is held, their payment method stays on file, and their return path is frictionless. This distinction has a profound impact on your retention metrics and lifetime revenue per subscriber.</p>
        </div>
        <div class="rc-subhead">How the Pause Lifecycle Works</div>
        <div class="rc-steps">
            <div class="rc-step">
                <div class="rc-sbadge">1</div>
                <div>
                    <h4>Pause Is Initiated</h4>
                    <p>A pause can be triggered in multiple ways: by the subscriber through a self-service hosted page, by your team through the Recurly Admin Console, or programmatically via the Recurly API. You specify a <strong>remaining billing cycles</strong> value, which tells Recurly how many renewal periods to skip before automatically resuming.</p>
                </div>
            </div>
            <div class="rc-step">
                <div class="rc-sbadge">2</div>
                <div>
                    <h4>Current Period Completes</h4>
                    <p>Importantly, the pause does not take effect immediately mid-cycle. The subscriber continues to have access through the end of their current billing period. Once that period expires, the subscription transitions into the <strong>paused</strong> state.</p>
                </div>
            </div>
            <div class="rc-step">
                <div class="rc-sbadge">3</div>
                <div>
                    <h4>Subscription Enters Paused State</h4>
                    <p>While paused, Recurly will not generate any invoices. The subscriber's account, plan details, add-ons, and coupons all remain intact. No dunning cycles are triggered.</p>
                </div>
            </div>
            <div class="rc-step">
                <div class="rc-sbadge">4</div>
                <div>
                    <h4>Automatic Resumption</h4>
                    <p>When cycles elapse, Recurly automatically resumes the subscription. A new invoice is generated, the stored payment method is charged, and the cycle continues as if they'd never left.</p>
                </div>
            </div>
        </div>
        <div class="rc-subhead">Pause vs. Cancel: A Critical Distinction</div>
        <div class="rc-2col">
            <div class="rc-wi">
                <h4>⏸️ Pause</h4>
                <p>Billing stops temporarily. Account stays active. Payment method retained. Automatic resumption. Frictionless return.</p>
            </div>
            <div class="rc-wi">
                <h4>❌ Cancel</h4>
                <p>Subscription terminates. Subscriber must re-sign up manually. Payment method may be lost. Reacquisition cost is high.</p>
            </div>
        </div>
        <div class="rc-warning">
            <strong>⚠️ Important: Pause Is Not the Same as a Trial Extension</strong>
            <p>A paused subscription does not extend a trial period. If the subscriber is still in a free trial when pause is initiated, the trial will end as scheduled and the pause will apply to future paid billing cycles.</p>
        </div>
    </div>
    <div class="rc-sec-nav">
        <span></span>
        <a href="page2.html" class="rc-btn-next">Next: Why Use It? →</a>
    </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
