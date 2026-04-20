---
title: 'Section 2: Things to consider'
excerpt: >-
  Before enabling Account Updater, review key compatibility factors:
  tokenization setup, gateway overlap, bank participation limits, and prepaid
  card exclusions. Confirm readiness with a pre-enablement checklist.
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
  .rc-nav a{display:inline-flex;align-items:center;gap:10px;padding:10px 18px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}.rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;background:var(--yellow);flex-shrink:0}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}.rc-sec-header>div>p{margin:0;color:var(--gray);font-size:.95rem;line-height:1.5}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;margin-bottom:24px;display:flex;gap:16px;align-items:flex-start}
  .rc-tipicon{font-size:24px;flex-shrink:0}.rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}.rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}.rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:16px;margin-bottom:28px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:22px 26px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge-dark{width:38px;height:38px;border-radius:10px;background:var(--darkgray);color:var(--yellow);font-weight:800;font-size:15px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.98rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-step p{font-size:.87rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-divider{border:none;border-top:2px solid var(--brightgray);margin:36px 0}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:26px}
  .rc-opt{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:14px;padding:18px}
  .rc-oicon{font-size:22px;margin-bottom:8px}.rc-opt h4{font-size:.92rem;font-weight:700;margin:0 0 5px;color:var(--offblack)}.rc-opt p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
  .rc-tag{display:inline-block;margin-top:10px;padding:3px 10px;border-radius:20px;font-size:11px;font-weight:700;background:var(--offblack);color:var(--yellow)}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:16px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.88rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;align-items:flex-start;gap:14px}.rc-cli:last-child{border-bottom:none}
  .rc-cb{width:22px;height:22px;border-radius:6px;border:2px solid var(--lightgray);flex-shrink:0;background:#fff;display:flex;align-items:center;justify-content:center;font-size:12px;color:var(--gray)}
  .rc-clab{font-size:.88rem;color:var(--darkgray);line-height:1.4}.rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}.rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-2col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater">Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits"><span class="rc-snum">1</span>Why use it?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-considerations"><span class="rc-snum">2</span>Things to consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable"><span class="rc-snum">3</span>How to enable it</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-data"><span class="rc-snum">4</span>Tracking impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-use-case"><span class="rc-snum">5</span>Pitch to leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🔍</div>
      <div>
        <h2>Is Account Updater right for you?</h2>
        <p>Confirm technical readiness by reviewing tokenization compatibility and understanding bank-level participation rules.</p>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Good news: Most merchants are already set up</h4><p>For the majority of Recurly customers, enabling Account Updater (AU) is a simple configuration toggle. Recurly's Real-Time Account Updater (RTAU) now covers major networks globally—including American Express (AMEX) and Discover—on supported gateways.</p></div>
    </div>

    <h3 class="rc-subhead">🔑 Key questions to ask before you enable</h3>
    <div class="rc-steps">
      <div class="rc-step"><div class="rc-sbadge-dark">1</div><div><h3>How are you tokenizing payment data?</h3><p>Recurly Account Updater (AU) works seamlessly with Recurly.js and Recurly-hosted checkouts. If you use external gateway tokenization, Recurly can still run AU as long as the token is managed within the Recurly vault.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">2</div><div><h3>Is your gateway already running AU?</h3><p>Running Account Updater (AU) in both Recurly and your gateway can be redundant. However, many merchants choose to run <strong>Recurly AU alongside gateway RTAU</strong> to ensure coverage across all regions.</p></div></div>
      <div class="rc-step"><div class="rc-sbadge-dark">3</div><div><h3>Are you an American Express merchant?</h3><p>Modern Real-Time Account Updater (RTAU) now handles American Express (AMEX) globally for many gateways. Legacy "Cardrefresher" is only required for specific direct-AMEX configurations.</p></div></div>
    </div>

    <div class="rc-card" style="border-left: 4px solid var(--orange);">
      <h3 class="rc-subhead">⚠️ Understanding network & issuer limitations</h3>
      <p style="font-size:.92rem;color:var(--darkgray);line-height:1.6;margin-bottom:12px;">While Account Updater (AU) is highly effective, success is subject to card network participation and rules. A card may not update due to the following:</p>
      <ul style="font-size:.88rem;color:var(--gray);line-height:1.7;padding-left:20px;margin:0;">
        <li><strong>Bank participation:</strong> Not all global issuing banks participate in the automated update network.</li>
        <li><strong>Card type exclusions:</strong> Prepaid cards and certain specialized debit cards are typically ineligible for automated updates.</li>
        <li><strong>Closed accounts:</strong> Updates are only available for <em>replacement</em> cards. If a customer closes an account entirely, no new data is generated.</li>
        <li><strong>Visa opt-out:</strong> Specifically for Visa, some issuers allow cardholders to manually "opt-out" of sharing updated details with merchants.</li>
      </ul>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Stored billing info required:</strong> Account Updater (AU) requires a <strong>Billing Info</strong> object to exist in the Recurly vault. It will not run on "guest checkouts" where card details are not saved for future use.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📋 A note on Adyen Users</h3>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0;">Recurly supports a dedicated Adyen Real-Time Account Updater (RTAU) integration. For maximum efficiency, we recommend enabling both Adyen RTAU and Recurly Account Updater (AU) to ensure comprehensive global coverage.</p>
    </div>

    <h3 class="rc-subhead">⚡ Quick diagnostic</h3>
    <div class="rc-2col">
      <div class="rc-opt"><div class="rc-oicon">✅</div><h4>Enable AU in Recurly if…</h4><p>You have credit/debit cards stored in the Recurly vault and want to proactively ensure they remain valid, regardless of gateway-level services.</p><span class="rc-tag">Recommended</span></div>
      <div class="rc-opt"><div class="rc-oicon">🔀</div><h4>Check gateway config if…</h4><p>You are using a third-party hosted checkout that does not pass card metadata or tokens back to Recurly for storage.</p><span class="rc-tag">Gateway Focus</span></div>
    </div>

    <hr class="rc-divider">

    <h3 class="rc-subhead" style="margin-top:4px;">✅ Pre-enablement checklist</h3>
    <div class="rc-checklist">
      <div class="rc-cl-header"><span>✅</span><h3>Before you enable</h3></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Stored billing info (Credit/Debit) exists in the Recurly vault<span>Tokens and raw cards are both eligible</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Identified if you need legacy AMEX Cardrefresher or modern RTAU<span>RTAU is preferred for global AMEX support</span></div></div>
      <div class="rc-cli"><div class="rc-cb"></div><div class="rc-clab">Coordinated with payment ops to avoid overlapping gateway fees<span>Verify if your gateway's AU is "Always On"</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-benefits">← Section 1: Why use it?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-account-updater-enable">Next: Section 3: How to enable it →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater" target="_blank" rel="noopener noreferrer">📖 Recurly Docs: Account Updater</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">🎧 Contact Recurly Support</a>
    <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/">🌐 Join Global Office Hours</a>
  </div>
</div>
</body>
</html>
</HTMLBlock>
`}</HTMLBlock>

<br />