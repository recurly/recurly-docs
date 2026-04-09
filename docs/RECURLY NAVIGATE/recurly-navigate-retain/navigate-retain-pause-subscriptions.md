---
title: Pause Subscription - API Test
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pause Subscriptions: 1. What Is It?</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root { --yellow: #FFD706; --orange: #FF8200; --vermillion: #FF5810; --salmon: #FF9D88; --offblack: #0D0D0B; --darkgray: #32312D; --gray: #807D73; --lightgray: #CCC9B8; --brightgray: #F1EFE3; --offwhite: #FFFDF2; }
        body { margin: 0; background: #f5f5f0; font-family: 'Inter', -apple-system, sans-serif; }
        .rc-guide { color: var(--offblack); max-width: 900px; margin: 0 auto; background: white; border-radius: 16px; overflow: hidden; box-shadow: 0 4px 20px rgba(0,0,0,0.05); }
        .rc-hero { background: var(--offblack); color: white; padding: 48px 40px; text-align: center; }
        .rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; }
        .rc-subtitle { color: var(--lightgray); font-size: 16px; }
        .rc-badge { background: var(--yellow); color: var(--offblack); padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; }
        .rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: var(--salmon); color: var(--offblack); }
        .rc-nav { display: flex; background: var(--brightgray); overflow-x: auto; border-bottom: 2px solid var(--lightgray); }
        .rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: var(--gray); font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; }
        .rc-nav a.is-active { color: var(--offblack); font-weight: 600; border-bottom-color: var(--yellow); background: var(--offwhite); }
        .rc-snum { width: 24px; height: 24px; border-radius: 50%; background: var(--lightgray); color: var(--gray); display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; }
        .rc-nav a.is-active .rc-snum { background: var(--yellow); color: var(--offblack); }
        .rc-sec { padding: 40px; }
        .rc-card { background: var(--offwhite); border-radius: 12px; padding: 28px; margin-bottom: 20px; }
        .rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; }
        .rc-step { display: flex; gap: 16px; background: var(--offwhite); border-radius: 12px; padding: 20px; margin-bottom: 16px; }
        .rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: var(--yellow); color: var(--offblack); display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }
        .rc-tip { border-left: 4px solid var(--yellow); background: var(--offwhite); padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 20px 0; }
        .rc-sec-nav { display: flex; justify-content: space-between; padding: 40px; border-top: 1px solid var(--lightgray); }
        .rc-btn-next { background: var(--yellow); color: var(--offblack); padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; }
        .rc-wi { background: var(--offwhite); border-radius: 12px; padding: 24px; text-align: center; }
        .rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0; }
    </style>
</head>
<body>
<div class="rc-guide">
    <div class="rc-hero">
        <span class="rc-badge">Subscriptions</span>
        <h1>Pause, Not Cancel</h1>
        <p class="rc-subtitle">Decrease voluntary churn by offering a middle option.</p>
        <div class="rc-flywheel-badge">RETAIN</div>
    </div>
    <div class="rc-nav">
        <a href="#" class="is-active"><span class="rc-snum">1</span> What Is It?</a>
        <a href="#"><span class="rc-snum">2</span> Why Use It?</a>
        <a href="#"><span class="rc-snum">3</span> Considerations</a>
        <a href="#"><span class="rc-snum">4</span> When Not to Use</a>
        <a href="#"><span class="rc-snum">5</span> Enable It</a>
        <a href="#"><span class="rc-snum">6</span> Tracking</a>
        <a href="#"><span class="rc-snum">7</span> Leadership Pitch</a>
    </div>
    <div class="rc-sec">
        <h2>What Is Pause Subscriptions?</h2>
        <div class="rc-card">
            <h3>The Pause Concept</h3>
            <p>Recurly's Pause feature lets you temporarily halt billing without canceling. The subscription enters a paused state: no invoices generate, and the account remains intact.</p>
        </div>
        <div class="rc-subhead">How the Lifecycle Works</div>
        <div class="rc-step">
            <div class="rc-sbadge">1</div>
            <div>
                <h4>Pause Is Initiated</h4>
                <p>Triggered by API, Admin Console, or Hosted Pages by setting a remaining billing cycle value.</p>
            </div>
        </div>
        <div class="rc-step">
            <div class="rc-sbadge">2</div>
            <div>
                <h4>Current Period Completes</h4>
                <p>Pause takes effect at the end of the current cycle. No partial refunds needed.</p>
            </div>
        </div>
        <div class="rc-step">
            <div class="rc-sbadge">3</div>
            <div>
                <h4>Automatic Resumption</h4>
                <p>When cycles reach zero, Recurly restarts billing automatically. No friction.</p>
            </div>
        </div>
    </div>
    <div class="rc-sec-nav">
        <span></span>
        <a href="/docs/pause-subscriptions-2" class="rc-btn-next">Next: Why Use It? →</a>
    </div>
</div>
</body>
</html>
`}</HTMLBlock>

<br />
