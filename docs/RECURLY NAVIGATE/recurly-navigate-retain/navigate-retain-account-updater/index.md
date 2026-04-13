---
title: 'Recurly Navigate: Account Updater'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<HTMLBlock>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero p{font-size:1.05rem;opacity:.8;max-width:700px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}.rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-nav a.is-active .rc-snum{background:var(--offblack);color:var(--yellow)}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-wi{background:var(--offwhite);border-radius:14px;padding:20px;border:1px solid var(--lightgray);text-align:center}
  .rc-wi-icon{font-size:30px;margin-bottom:10px}.rc-wi h4{font-size:.88rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-wi p{font-size:.8rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:38px;height:38px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev,.rc-btn-disabled{border:1px solid var(--lightgray)}
  .rc-btn-prev{background:#fff;color:var(--darkgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-3col{grid-template-columns:1fr}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
</style>
</head>
<body>
<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-badge">💳 Revenue Recovery</div>
    <h1>Account Updater</h1>
    <p>Protect your recurring revenue by automatically keeping card details up to date — before payments ever fail.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">77x</div><div class="rc-lbl">Average ROI</div></div>
      <div><div class="rc-num">18%</div><div class="rc-lbl">Of recovered revenue</div></div>
      <div><div class="rc-num">96M+</div><div class="rc-lbl">Card updates in 2025</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater"><span class="rc-snum">1</span>What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">2</span>Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">3</span>Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">4</span>How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">5</span>Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">✓</span>Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">💳</div>
      <div>
        <h2>What is Account Updater?</h2>
        <p>A plain-language explanation of what Account Updater does and how it works — no prior knowledge required.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The Simple Version</h3>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">When a customer's credit or debit card expires, gets lost or stolen, or is reissued by their bank, the card number or expiration date changes. If you're charging that card on a recurring basis — like a subscription renewal — that charge will simply fail. The customer hasn't cancelled. They still want your product. Their card just changed.</p>
      <p style="font-size:.95rem;color:var(--darkgray);line-height:1.6;margin:0;"><strong>Account Updater (AU) is the solution.</strong> It's a service run by the major card networks — Visa, Mastercard, American Express, and Discover — that automatically pushes updated card details to Recurly whenever a card on file changes. Recurly then stores that fresh information so that your next billing attempt uses the correct card data, without the customer needing to do anything.</p>
    </div>

    <div class="rc-3col">
      <div class="rc-wi"><div class="rc-wi-icon">🔄</div><h4>Standard Account Updater</h4><p>Supported for Visa, Mastercard, American Express, and Discover. Updates are fetched via secure batch files before renewal attempts.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">⚡</div><h4>Real-Time Account Updater (RTAU)</h4><p>Available for Visa, Mastercard, Amex, and Discover. Recurly checks for updates during the transaction attempt to prevent declines before they happen.</p></div>
      <div class="rc-wi"><div class="rc-wi-icon">🏦</div><h4>Cardrefresher</h4><p>Amex's specialized AU service. While many Amex updates now happen via RTAU, Cardrefresher provides a robust fallback for legacy or direct Amex merchant integrations.</p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🗺️ How It Works — Step by Step</h3>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge">1</div><div><h3>A cardholder's bank issues a card change</h3><p>This could be a new card number, updated expiration date, or a card that's been closed or replaced. Common events: annual renewals, fraud replacements, or bank-issued card migrations.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">2</div><div><h3>The card network is notified</h3><p>Visa, Mastercard, Amex, or Discover updates their internal records with the new card details associated with that account.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">3</div><div><h3>Recurly is alerted</h3><p>For standard AU, Recurly checks for updates on a scheduled basis. For Real-Time AU, Recurly requests the update at the exact moment a transaction is attempted.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">4</div><div><h3>Recurly updates the stored payment method</h3><p>The new card details replace the old ones in Recurly's payment vault — silently, automatically, and without any action required from your customer or your team.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">5</div><div><h3>The next renewal charges successfully</h3><p>Because the billing info is already up to date, the subscription renews without interruption. No failed payment. No dunning. No involuntary churn.</p></div></div>
      </div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Note on Digital Wallets:</strong> Account Updater works with cards stored in Recurly's vault. Apple Pay and Google Pay use token-based systems that handle card lifecycle updates natively within the wallet provider's ecosystem rather than via standard AU files.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>The Bottom Line</h4><p>Account Updater quietly fixes outdated card details behind the scenes — reducing failed payments and churn before they ever happen. It's one of the few revenue recovery tools that is entirely proactive rather than reactive. No dunning, no customer action, no friction.</p></div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">🎯 Start</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits">Next: Why Use It? →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable">⚙️ How to Enable It</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Customer Support</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />
