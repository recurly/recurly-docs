---
title: 'Section 6: Phase 1 Review'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif;max-width:960px;margin:0 auto;padding:0 20px 60px}
.rc-hero{background:var(--offblack);border-radius:16px;padding:52px 40px 44px;text-align:center;margin-bottom:0}
.rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 20px;font-size:12px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:18px}
.rc-hero h1{font-size:2.3rem;font-weight:800;line-height:1.15;margin:0 0 12px;color:#fff}
.rc-hero>p{font-size:1rem;max-width:680px;margin:0 auto 28px;color:#CCC9B8;line-height:1.6}
.rc-hero-stats{display:flex;justify-content:center;gap:36px;flex-wrap:wrap}
.rc-num{font-size:1.7rem;font-weight:800;color:var(--yellow)}
.rc-lbl{font-size:.76rem;color:#CCC9B8;text-transform:uppercase;letter-spacing:.5px}
.rc-nav{display:flex;flex-wrap:wrap;gap:8px;margin:22px 0 32px;padding:16px;background:var(--offwhite);border-radius:14px;border:1px solid var(--lightgray)}
.rc-nav a{display:inline-flex;align-items:center;gap:7px;padding:9px 13px;border-radius:10px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.83rem;font-weight:700;transition:all .2s}
.rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.25);color:var(--offblack);text-decoration:none}
.rc-nav a.rc-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
.rc-snum{display:inline-flex;align-items:center;justify-content:center;width:22px;height:22px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:11px;font-weight:800;flex-shrink:0}
.rc-nav a.rc-active .rc-snum{background:rgba(13,13,11,.15);color:var(--offblack)}
.rc-sec{margin-bottom:48px}
.rc-sec-header{display:flex;align-items:flex-start;gap:18px;margin-bottom:28px}
.rc-sec-icon{width:52px;height:52px;border-radius:14px;background:var(--yellow);display:flex;align-items:center;justify-content:center;font-size:24px;flex-shrink:0}
.rc-sec-header h2{font-size:1.45rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
.rc-sec-header p{font-size:.9rem;color:var(--gray);margin:0;line-height:1.6}
.rc-card{background:#fff;border:1px solid var(--lightgray);border-radius:14px;padding:20px 22px;margin-bottom:16px;box-shadow:0 2px 6px rgba(13,13,11,.04)}
.rc-subhead{font-size:.98rem;font-weight:800;color:var(--offblack);margin:0 0 10px}
.rc-recap-row{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:16px}
.rc-recap-card{background:var(--offwhite);border:2px solid var(--yellow);border-radius:13px;padding:16px 18px}
.rc-recap-card h4{font-size:.9rem;font-weight:800;margin:0 0 5px;color:var(--offblack);display:flex;align-items:center;gap:8px}
.rc-recap-card p{font-size:.83rem;color:var(--gray);margin:0;line-height:1.5}
.rc-recap-card .rc-recap-res{font-size:.78rem;color:var(--orange);font-weight:700;margin-top:8px;display:block}
.rc-handoff{background:linear-gradient(135deg,var(--offblack) 50%,#2a1800);border-radius:16px;padding:36px 30px;text-align:center;margin:28px 0}
.rc-handoff-badge{display:inline-block;background:var(--orange);color:#fff;border-radius:20px;padding:5px 16px;font-size:11px;font-weight:800;letter-spacing:1px;text-transform:uppercase;margin-bottom:14px}
.rc-handoff h3{font-size:1.4rem;font-weight:800;color:#fff;margin:0 0 10px}
.rc-handoff p{font-size:.92rem;color:#CCC9B8;margin:0 auto 24px;max-width:540px;line-height:1.6}
.rc-handoff-btn{display:inline-flex;align-items:center;gap:8px;padding:15px 30px;border-radius:12px;background:var(--orange);color:#fff;font-weight:800;font-size:1rem;text-decoration:none;border:none}
.rc-handoff-btn:hover{opacity:.92;text-decoration:none}
.rc-handoff-steps{display:flex;justify-content:center;gap:0;margin-top:22px;flex-wrap:wrap}
.rc-hs{display:flex;align-items:center;gap:0}
.rc-hs-dot{width:32px;height:32px;border-radius:50%;background:var(--orange);color:#fff;font-size:12px;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-hs-lbl{font-size:.76rem;color:#CCC9B8;padding:0 8px;white-space:nowrap}
.rc-hs-arrow{color:#807D73;font-size:14px;margin:0 2px}
.rc-tip{background:#fffde6;border:1px solid var(--yellow);border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-resources-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:16px}
.rc-res-item{background:#fff;border:1px solid var(--lightgray);border-radius:12px;padding:15px 17px}
.rc-res-item h4{font-size:.88rem;font-weight:800;margin:0 0 5px;color:var(--offblack)}
.rc-res-item p{font-size:.82rem;color:var(--gray);margin:0 0 10px;line-height:1.4}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:#fff;color:var(--darkgray)}
.rc-btn-prev:hover{background:var(--brightgray);text-decoration:none}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none}
.rc-link-btn{background:var(--yellow);color:var(--offblack);border-color:var(--yellow);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-recap-row,.rc-resources-grid{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}.rc-handoff{padding:26px 18px}.rc-handoff-steps{flex-direction:column;align-items:center}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate · Launchpad Phase 1</div>
    <h1>Phase 1 Complete — Rewind &amp; Review</h1>
    <p>You've set the foundation for a resilient, optimized Recurly setup. Here's everything you accomplished — and everything you need to carry it forward.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">5</div><div class="rc-lbl">Steps Completed</div></div>
      <div><div class="rc-num">Phase 1</div><div class="rc-lbl">Optimization Done</div></div>
      <div><div class="rc-num">Phase 2</div><div class="rc-lbl">Up Next: Metrics</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review" class="rc-active"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🏆</div>
      <div>
        <h2>What You've Built in Phase 1</h2>
        <p>Each step in Phase 1 addresses a specific revenue risk. Together, they form a complete optimization layer around your Recurly setup — working automatically, around the clock, without manual intervention.</p>
      </div>
    </div>

    <div class="rc-recap-row">
      <div class="rc-recap-card">
        <h4>🧪 Final Production Testing</h4>
        <p>You validated the full subscriber checkout experience, confirmed payment processing, and checked PSD2 compliance — catching issues before real subscribers ever saw them.</p>
        <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing">↩ Review this step</a>
      </div>
      <div class="rc-recap-card">
        <h4>🔄 Dunning Optimization</h4>
        <p>You configured your dunning campaign — window length, email sequence, and expiration behavior. Recurly's built-in Intelligent Retry logic runs automatically to maximize every recovery opportunity.</p>
        <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization">↩ Review this step</a>
      </div>
      <div class="rc-recap-card">
        <h4>💳 Account Updater</h4>
        <p>You enabled proactive card update checks so expired or replaced cards are refreshed before renewal — preventing payment failures from occurring in the first place.</p>
        <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater">↩ Review this step</a>
      </div>
      <div class="rc-recap-card">
        <h4>🎨 Branding</h4>
        <p>Every email and invoice your subscribers receive is now on-brand — building trust, reducing support confusion, and making your Recurly communications feel native to your product.</p>
        <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding">↩ Review this step</a>
      </div>
      <div class="rc-recap-card">
        <h4>🛡️ Gateway Failover</h4>
        <p>You've eliminated the single point of payment failure. If your primary gateway goes down, transactions automatically route to your backup — your revenue stream stays uninterrupted.</p>
        <a class="rc-recap-res" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover">↩ Review this step</a>
      </div>
      <div class="rc-recap-card" style="background:var(--offwhite);border-color:var(--lightgray)">
        <h4>📚 Phase 1 Resources</h4>
        <p>All your Launchpad Phase 1 cheatsheet, guide, and on-demand webinars — saved in one place for ongoing reference.</p>
        <a class="rc-recap-res" href="https://go.recurly.com/Navigate-Resource-Guide.html" target="_blank" rel="noopener noreferrer">⬇ Navigate Resource Guide</a>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Keep it going:</strong> These optimizations don't stop working when you close this page. Dunning runs every billing cycle. Account Updater refreshes cards before every renewal. Gateway Failover monitors every transaction. You've built a system — now let it run.
    </div>

    <!-- PHASE 2 HANDOFF CTA -->
    <div class="rc-handoff">
      <div class="rc-handoff-badge">📊 Phase 2 · Mastering Metrics</div>
      <h3>Ready for Phase 2?</h3>
      <p>Now that your setup is optimized, it's time to understand the data. Phase 2 teaches you the six core benchmark metrics every subscription business should track — and how to use them to grow smarter.</p>
      <a class="rc-handoff-btn" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two">Start Phase 2: Mastering Metrics →</a>
      <div class="rc-handoff-steps">
        <div class="rc-hs"><div class="rc-hs-dot">1</div><span class="rc-hs-lbl">Benchmarks</span></div>
        <span class="rc-hs-arrow">→</span>
        <div class="rc-hs"><div class="rc-hs-dot">2</div><span class="rc-hs-lbl">Acquisition</span></div>
        <span class="rc-hs-arrow">→</span>
        <div class="rc-hs"><div class="rc-hs-dot">3</div><span class="rc-hs-lbl">Churn</span></div>
        <span class="rc-hs-arrow">→</span>
        <div class="rc-hs"><div class="rc-hs-dot">4</div><span class="rc-hs-lbl">Revenue Recovery</span></div>
      </div>
    </div>

    <p class="rc-subhead" style="margin-bottom:14px">📚 Phase 1 Reference Resources</p>
    <div class="rc-resources-grid">
      <div class="rc-res-item">
        <h4>⬇ Launchpad Cheatsheet</h4>
        <p>A one-page reference covering all Phase 1 steps, resources, and key takeaways.</p>
        <a class="rc-link-btn" style="font-size:.8rem;padding:8px 14px" href="https://go.recurly.com/Navigate-Launchpad-Cheatsheet.html" target="_blank" rel="noopener noreferrer">Download Cheatsheet</a>
      </div>
      <div class="rc-res-item">
        <h4>📖 Navigate Resource Guide</h4>
        <p>Your complete reference for Recurly support, documentation, and program links.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.8rem;padding:8px 14px" href="https://go.recurly.com/Navigate-Resource-Guide.html" target="_blank" rel="noopener noreferrer">Download Resource Guide</a>
      </div>
      <div class="rc-res-item">
        <h4>🎧 Navigate Events &amp; Webinars</h4>
        <p>Office Hours, on-demand sessions, and live learning events — bookmark this page and stay connected.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.8rem;padding:8px 14px" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">View All Events</a>
      </div>
      <div class="rc-res-item">
        <h4>✉ Your Customer Success Team</h4>
        <p>Questions about anything in Phase 1 — or ready to discuss your Phase 2 metrics baseline? Reach out.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.8rem;padding:8px 14px" href="mailto:customersuccess@recurly.com">Email Your CSM</a>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover">← Gateway Failover</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/navigate-launch-phase-two" style="background:var(--orange);border-color:var(--orange);color:#fff">Begin Phase 2 →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com" target="_blank" rel="noopener noreferrer">📖 Recurly Documentation</a>
      <a class="rc-link-btn rc-link-sec" href="https://recurly.com/events/" target="_blank" rel="noopener noreferrer">🎧 Navigate Events</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Customer Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />