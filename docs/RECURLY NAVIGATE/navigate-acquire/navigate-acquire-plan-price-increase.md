---
title: Plan Changes
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
html{scroll-behavior:smooth;scroll-padding-top:80px}
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
.rc-guide *{box-sizing:border-box}
body{margin:0;background:#fff}
.rc-guide a,.rc-guide a:link,.rc-guide a:visited,.rc-guide a:hover,.rc-guide a:active{border-bottom:0!important;text-decoration:none!important}
.rc-top-nav{padding:20px 40px 16px;max-width:1200px;margin:0 auto}
.rc-back-link{color:var(--gray);font-weight:700;font-size:.9rem;display:inline-flex;align-items:center;gap:6px;transition:color .2s}
.rc-back-link:hover{color:var(--orange)}
.rc-content-wrap{max-width:1200px;margin:0 auto;padding:0 40px}
.rc-announce-bar{display:none;background:var(--yellow);color:var(--offblack);align-items:center;justify-content:space-between;padding:10px 20px;font-size:.88rem;font-weight:600;border-radius:10px;margin-bottom:16px;gap:12px;line-height:1.4}
.rc-announce-bar.rc-active{display:flex}
.rc-announce-inner{display:flex;align-items:center;gap:12px;flex:1;flex-wrap:wrap}
.rc-guide a.rc-announce-link{color:var(--offblack)!important;font-weight:800;white-space:nowrap;padding:4px 12px;background:rgba(0,0,0,0.10);border-radius:6px;transition:background .2s}
.rc-guide a.rc-announce-link:hover{background:rgba(0,0,0,0.20)}
.rc-announce-close{background:none;border:none;font-size:1.4rem;line-height:1;cursor:pointer;color:var(--offblack);padding:0 2px;opacity:.45;transition:opacity .2s;flex-shrink:0}
.rc-announce-close:hover{opacity:1}
.rc-hero{background:linear-gradient(rgba(13,13,11,0.82),rgba(13,13,11,0.82)),url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;background-color:var(--offblack);background-size:cover;color:#fff;padding:48px 40px 44px;text-align:center;border-radius:16px;margin-bottom:0}
.rc-lp-pillar-tag{display:inline-flex;align-items:center;gap:7px;background:rgba(255,215,6,0.20);border:1px solid rgba(255,215,6,0.45);color:#FFD706;font-size:.75rem;font-weight:800;letter-spacing:1px;text-transform:uppercase;padding:6px 14px;border-radius:20px;margin-bottom:20px}
.rc-lp-pillar-tag img{width:13px;height:13px;object-fit:contain}
.rc-lp-hero-title{text-align:center;margin:0 0 14px}
.rc-lp-hero-title h1{font-size:2.4rem;font-weight:800;line-height:1.15;color:var(--offwhite);margin:0}
.rc-hero>p{font-size:1rem;opacity:.85;max-width:640px;margin:0 auto 32px;color:var(--lightgray);line-height:1.6}
.rc-hero-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:0;border-top:1px solid rgba(255,255,255,0.12);padding-top:24px;margin-top:4px}
.rc-hero-stat{text-align:center;padding:0 16px}
.rc-hero-stat+.rc-hero-stat{border-left:1px solid rgba(255,255,255,0.12)}
.rc-hero-stat-num{font-size:1.9rem;font-weight:800;color:var(--yellow);line-height:1;margin-bottom:6px}
.rc-hero-stat-label{font-size:.72rem;font-weight:600;letter-spacing:.8px;text-transform:uppercase;color:var(--lightgray);line-height:1.3}
details.rc-sticky-nav-wrap{position:sticky;top:0;z-index:100;background-color:var(--yellow);box-shadow:0 4px 12px rgba(0,0,0,0.08);margin:24px 0 48px;border-radius:12px;border:1px solid rgba(0,0,0,0.08);overflow:hidden}
details.rc-sticky-nav-wrap>summary{list-style:none;display:flex;align-items:center;padding:15px 24px;cursor:pointer;user-select:none}
details.rc-sticky-nav-wrap>summary::-webkit-details-marker{display:none}
details.rc-sticky-nav-wrap>summary::marker{display:none}
.rc-nav-toggle-label{display:inline-flex;align-items:center;gap:8px;font-weight:800;font-size:.88rem;letter-spacing:.6px;text-transform:uppercase;color:var(--offblack)}
.rc-nav-chevron{font-size:.72rem;color:var(--offblack);opacity:.55;line-height:1;transition:transform .25s ease}
details.rc-sticky-nav-wrap[open] .rc-nav-chevron{transform:rotate(180deg)}
.rc-nav-drawer{display:grid;grid-template-rows:0fr;transition:grid-template-rows .3s ease}
details.rc-sticky-nav-wrap[open] .rc-nav-drawer{grid-template-rows:1fr}
.rc-nav-drawer-inner{overflow:hidden;border-top:1px solid rgba(0,0,0,0.10)}
.rc-nav-links{display:flex;flex-wrap:wrap;gap:6px 4px;padding:12px 20px 18px}
.rc-sticky-link{color:var(--offblack)!important;text-decoration:none!important;font-weight:700;font-size:.83rem;letter-spacing:.4px;text-transform:uppercase;padding:7px 14px;border-radius:7px;transition:all .18s;white-space:nowrap;display:inline-flex;align-items:center;gap:6px}
.rc-sticky-link:hover{background:var(--offblack);color:var(--yellow)!important}
.rc-sticky-link img{width:15px;height:15px;object-fit:contain}
.rc-step-badge{display:inline-flex;align-items:center;justify-content:center;width:20px;height:20px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:.65rem;font-weight:800;flex-shrink:0;line-height:1}
.rc-sticky-link:hover .rc-step-badge{background:var(--yellow);color:var(--offblack)}
.rc-sticky-link-active{background:rgba(0,0,0,0.12);font-weight:800}
.rc-sticky-link-active:hover{background:var(--offblack);color:var(--yellow)!important}
.rc-lp-section{margin-bottom:48px}
.rc-lp-section h2{font-size:1.5rem;font-weight:800;margin:0 0 20px;color:var(--offblack);display:flex;align-items:center;gap:12px}
.rc-lp-section h2::after{content:"";flex-grow:1;height:1px;background:var(--lightgray)}
.rc-lp-section p{font-size:.95rem;line-height:1.65;color:var(--darkgray);margin:0 0 16px}
.rc-card{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;padding:24px 28px;margin:0 0 20px}
.rc-card-title{font-size:1rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-card p{font-size:.92rem;color:var(--darkgray);line-height:1.65;margin:0 0 10px}
.rc-card p:last-child{margin-bottom:0}
.rc-tile-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin:0 0 24px}
.rc-tile{background:var(--offwhite);border:1px solid var(--lightgray);border-radius:12px;padding:20px;text-align:center}
.rc-tile-icon{font-size:1.6rem;margin-bottom:10px}
.rc-tile h4{font-size:.9rem;font-weight:800;color:var(--offblack);margin:0 0 6px}
.rc-tile p{font-size:.82rem;color:var(--gray);line-height:1.5;margin:0}
.rc-steps{display:flex;flex-direction:column;gap:0;margin:0}
.rc-step{display:grid;grid-template-columns:40px 1fr;gap:16px;align-items:flex-start;padding:18px 0;border-bottom:1px solid var(--brightgray)}
.rc-step:last-child{border-bottom:none}
.rc-step-num{width:36px;height:36px;border-radius:50%;background:var(--offblack);color:var(--yellow);display:flex;align-items:center;justify-content:center;font-size:.85rem;font-weight:800;flex-shrink:0;margin-top:2px}
.rc-step-content h4{font-size:1.02rem;font-weight:800;color:var(--offblack);margin:0 0 6px;line-height:1.3}
.rc-step-content p{font-size:.92rem;color:var(--gray);line-height:1.6;margin:0}
.rc-step-content strong{color:var(--darkgray)}
.rc-step-content a{color:var(--orange);font-weight:600}
.rc-guide .rc-step-content a:hover{text-decoration:underline!important}
.rc-callout{border-radius:10px;padding:16px 20px;margin:20px 0;display:flex;gap:14px;align-items:flex-start}
.rc-callout+.rc-callout{margin-top:12px}
.rc-callout-icon{font-size:1.1rem;line-height:1.4;flex-shrink:0}
.rc-callout-body{flex:1}
.rc-callout-body>strong{font-size:.88rem;font-weight:800;display:block;margin-bottom:4px}
.rc-callout-body p{font-size:.9rem;line-height:1.55;margin:0;color:var(--darkgray)}
.rc-callout-tip{background:var(--brightgray);border-left:4px solid var(--offblack)}
.rc-callout-tip .rc-callout-body>strong{color:var(--offblack)}
.rc-callout-caution{background:rgba(255,130,0,0.08);border-left:4px solid var(--orange)}
.rc-callout-caution .rc-callout-body>strong{color:var(--darkgray)}
.rc-lp-nav{display:flex;align-items:center;justify-content:space-between;gap:16px;margin:40px 0 16px}
.rc-lp-nav-indicator{font-size:.8rem;font-weight:600;color:var(--lightgray);letter-spacing:.5px}
.rc-btn-start{background:var(--brightgray);color:var(--gray);padding:13px 24px;border-radius:10px;font-weight:700;font-size:.9rem;border:2px solid var(--lightgray);cursor:default;display:inline-flex;align-items:center;gap:8px}
.rc-guide a.rc-btn-path{background:var(--yellow);color:var(--offblack)!important;padding:13px 28px;border-radius:10px;font-weight:800;font-size:.95rem;display:inline-flex;align-items:center;gap:8px;transition:all .2s;border:2px solid var(--yellow);border-bottom:2px solid var(--yellow)!important}
.rc-guide a.rc-btn-path:hover{background:transparent!important;color:var(--offblack)!important;border:2px solid var(--yellow)!important;border-bottom:2px solid var(--yellow)!important}
.rc-resources{background:var(--brightgray);border-left:4px solid var(--yellow);border-radius:10px;padding:20px 24px;margin:32px 0 0}
.rc-resources h3{font-size:.75rem;font-weight:700;text-transform:uppercase;letter-spacing:.9px;color:var(--gray);margin:0 0 12px}
.rc-resource-links{display:flex;flex-wrap:wrap;gap:4px 20px}
.rc-resource-link{color:var(--gray)!important;text-decoration:underline!important;text-underline-offset:3px;text-decoration-color:var(--lightgray)!important;font-weight:500;font-size:.88rem;transition:all .18s;display:inline-flex;align-items:center;gap:6px}
.rc-guide .rc-resource-link:hover{color:var(--offblack)!important;text-decoration-color:var(--yellow)!important}
.rc-footer-nav{border-top:1px solid var(--lightgray);padding-top:32px;margin-top:32px;text-align:center}
.rc-footer-links{display:flex;flex-wrap:wrap;gap:16px 24px;justify-content:center;align-items:center}
.rc-footer-link{color:var(--gray);font-weight:600;font-size:.9rem;transition:color .2s;display:inline-flex;align-items:center;gap:5px}
.rc-footer-link:hover{color:var(--offblack)}
.rc-footer-link img{width:13px;height:13px;object-fit:contain;opacity:.55}
@media(max-width:768px){
  .rc-content-wrap{padding:0 20px}.rc-top-nav{padding:16px 20px}
  .rc-hero{padding:36px 20px 36px}.rc-lp-hero-title h1{font-size:1.8rem}
  .rc-hero-stats{grid-template-columns:1fr;gap:16px;border-top:none;padding-top:0}
  .rc-hero-stat+.rc-hero-stat{border-left:none;border-top:1px solid rgba(255,255,255,0.12);padding-top:16px;margin-top:0}
  .rc-tile-row{grid-template-columns:1fr}
  .rc-lp-nav{flex-wrap:wrap;justify-content:center}.rc-lp-nav-indicator{width:100%;text-align:center}
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-back-link">← Back to Acquire</a>
  </div>
  <div class="rc-content-wrap">

    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">🗓️ <strong>Upcoming:</strong> Join our CSMs for a live pricing strategy session.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/d92be816a9e838fb46356e2547d5f8bb663dddb7b4a77cac37434efbd825e216-Acquire-icon-white.png" alt="Acquire"> Acquire
      </div>
      <div class="rc-lp-hero-title"><h1>Plan Price Increase</h1></div>
      <p>Confidently raise plan prices without losing subscribers — with the right timing, tools, and communication.</p>
      <div class="rc-hero-stats">
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">3–8%</div><div class="rc-hero-stat-label">Avg. revenue uplift from a well-executed price increase</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">~70%</div><div class="rc-hero-stat-label">Subscribers retained after a communicated increase</div></div>
        <div class="rc-hero-stat"><div class="rc-hero-stat-num">2–4 wks</div><div class="rc-hero-stat-label">Typical time to plan and execute a price change</div></div>
      </div>
    </div>

    <details class="rc-sticky-nav-wrap">
      <summary><span class="rc-nav-toggle-label">Navigate Quick Links <span class="rc-nav-chevron">▲</span></span></summary>
      <div class="rc-nav-drawer"><div class="rc-nav-drawer-inner"><div class="rc-nav-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-sticky-link rc-sticky-link-active">
          <img src="https://files.readme.io/8e6d7690e1683e5627378d61ec2a127d950fa23c8eeb18b7ef0c6511dc927d45-Return_icon.png" alt=""> Plan Price Increase
        </a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-sticky-link"><span class="rc-step-badge">1</span> Why increase prices?</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-sticky-link"><span class="rc-step-badge">2</span> Things to consider</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-sticky-link"><span class="rc-step-badge">3</span> How to execute it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-sticky-link"><span class="rc-step-badge">4</span> Communicate it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-sticky-link"><span class="rc-step-badge">5</span> Track the impact</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">
          <img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Navigate Home
        </a>
      </div></div></div>
    </details>

    <div class="rc-lp-section">
      <h2>💰 What is a Plan Price Increase?</h2>
      <p>A structured approach to raising the price of one or more subscription plans — capturing more revenue from existing subscribers while preserving retention and trust. In Recurly, a <strong>Plan</strong> is the pricing template all subscriptions are built from. Updating a plan's price immediately applies to new subscribers; existing subscribers need to be explicitly migrated.</p>

      <div class="rc-card">
        <div class="rc-card-title">🧩 Why it matters</div>
        <p>Most subscription businesses undercharge relative to the value they deliver. Costs rise, features ship, and the market shifts — yet plans stay frozen at launch-era pricing. A price increase isn't just a revenue event; it's a signal that your product has grown and your pricing should reflect it.</p>
        <p>Recurly gives you full control over how and when price changes take effect. You can update a plan's unit amount in the UI, configure whether the change hits at next renewal or immediately, and lock specific subscribers at their current price indefinitely — all without engineering support.</p>
      </div>

      <div class="rc-tile-row">
        <div class="rc-tile"><div class="rc-tile-icon">🏷️</div><h4>Plan-level update</h4><p>Update the base price once; all future new subscribers get the new price immediately.</p></div>
        <div class="rc-tile"><div class="rc-tile-icon">🔄</div><h4>Subscriber migration</h4><p>Explicitly move existing subscribers to the new price — at renewal or with a bulk import.</p></div>
        <div class="rc-tile"><div class="rc-tile-icon">🔒</div><h4>Grandfathering</h4><p>Lock specific subscribers at their current price indefinitely with a subscription-level override.</p></div>
      </div>

      <div class="rc-callout rc-callout-caution">
        <div class="rc-callout-icon">⚠️</div>
        <div class="rc-callout-body">
          <strong>Updating the plan price alone is not enough</strong>
          <p>Existing subscribers will not automatically move to the new price. They need to be explicitly migrated — either via API, bulk import, or manually — otherwise they continue renewing at the old amount indefinitely.</p>
        </div>
      </div>
    </div>

    <div class="rc-lp-section">
      <h2>🗺️ Your learning path</h2>
      <p>Five steps covering everything from the business case to post-change reporting.</p>
      <div class="rc-steps">
        <div class="rc-step">
          <div class="rc-step-num">1</div>
          <div class="rc-step-content"><h4>Why increase prices?</h4><p>Build the business case: revenue impact, value alignment, and how to justify the decision internally and to subscribers.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">2</div>
          <div class="rc-step-content"><h4>Things to consider</h4><p>Timing, subscriber segments, grandfathering logic, contract obligations, and what to do with legacy plans.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">3</div>
          <div class="rc-step-content"><h4>How to execute it</h4><p>Update the plan price in the UI, then migrate existing subscribers via API, bulk import, or individual override.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">4</div>
          <div class="rc-step-content"><h4>Communicate it</h4><p>Notification timeline, email templates, and how to use Recurly webhooks to trigger subscriber-facing messages at the right moment.</p></div>
        </div>
        <div class="rc-step">
          <div class="rc-step-num">5</div>
          <div class="rc-step-content"><h4>Track the impact</h4><p>Which Recurly reports to watch, KPIs to monitor, and how to build a 30/60/90-day baseline comparison after the change.</p></div>
        </div>
      </div>
    </div>

    <div class="rc-lp-nav">
      <span class="rc-btn-start">🏁 Start</span>
      <span class="rc-lp-nav-indicator">Overview</span>
      <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-btn-path">Next: Why increase prices? →</a>
    </div>

    <div class="rc-resources">
      <h3>📚 Resources</h3>
      <div class="rc-resource-links">
        <a href="https://docs.recurly.com/docs/plans" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Plans</a>
        <a href="https://docs.recurly.com/docs/subscriptions" target="_blank" rel="noopener noreferrer" class="rc-resource-link">📖 Recurly Docs: Subscriptions</a>
        <a href="mailto:support@recurly.com" class="rc-resource-link">🎧 Contact Recurly Support</a>
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" rel="noopener noreferrer" class="rc-resource-link">🌐 Join Global Office Hours</a>
      </div>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-footer-link"><img src="https://files.readme.io/27c852ebfd8736eb0017ee9442030e66cd19e7db48c7e791ec5d8e092162ca48-White_Navigate_Home_Pin_1.png" alt=""> Navigate Home</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase" class="rc-footer-link">Path Overview</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-why" class="rc-footer-link">1 · Why increase prices?</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-considerations" class="rc-footer-link">2 · Things to consider</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-how" class="rc-footer-link">3 · How to execute it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-communicate" class="rc-footer-link">4 · Communicate it</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire-plan-price-increase-impact" class="rc-footer-link">5 · Track the impact</a>
        <a href="mailto:support@recurly.com" class="rc-footer-link">support@recurly.com</a>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />
