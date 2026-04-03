---
title: 'Launchpad Phase 1: Optimize'
deprecated: false
hidden: true
metadata:
  robots: index
next:
  description: |
    Click "Section 1: Final Production Testing" to continue the course. 
  pages:
    - slug: final-production-testing
      title: 'Section 1: Final Production Testing'
      type: basic
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
.rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:16px}
.rc-phase-banner{background:var(--offblack);border-radius:14px;padding:22px 24px;margin-bottom:14px;display:flex;align-items:flex-start;gap:16px}
.rc-phase-icon{font-size:26px;flex-shrink:0;margin-top:2px}
.rc-phase-banner h3{font-size:.98rem;font-weight:800;margin:0 0 6px;color:var(--yellow)}
.rc-phase-banner p{font-size:.87rem;color:#CCC9B8;margin:0;line-height:1.5}
.rc-phase-step{display:flex;align-items:center;gap:10px;padding:6px 0;border-bottom:1px solid rgba(255,255,255,.07);font-size:.85rem;color:#CCC9B8}
.rc-phase-step:last-child{border-bottom:none}
.rc-phase-dot{width:24px;height:24px;border-radius:50%;background:var(--yellow);color:var(--offblack);font-size:11px;font-weight:800;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.rc-phase-dot.orange{background:var(--orange);color:#fff}
.rc-tip{background:#fffde6;border:1px solid var(--yellow);border-radius:12px;padding:15px 17px;margin-bottom:16px;font-size:.87rem;color:var(--darkgray);line-height:1.6}
.rc-tip strong{color:var(--offblack)}
.rc-video-wrap{position:relative;width:100%;padding-bottom:56.25%;height:0;overflow:hidden;border-radius:10px;margin-bottom:8px;background:var(--offblack)}
.rc-video-wrap iframe{position:absolute;top:0;left:0;width:100%;height:100%;border:0}
.rc-video-cap{font-size:.8rem;color:var(--gray);text-align:center;margin-bottom:4px;font-style:italic}
.rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
.rc-btn-prev,.rc-btn-next,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.87rem;text-decoration:none;border:1px solid var(--lightgray)}
.rc-btn-prev{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-prev:hover{opacity:.92;text-decoration:none}
.rc-btn-next{background:var(--yellow);color:var(--offblack);border-color:var(--yellow)}
.rc-btn-next:hover{opacity:.92;text-decoration:none}
.rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;pointer-events:none;border-color:var(--lightgray)}
.rc-link-btn{background:var(--yellow);color:var(--offblack);border-color:var(--yellow);margin:0 8px 8px 0}
.rc-link-btn:hover{opacity:.9;text-decoration:none}
.rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
.rc-link-sec:hover{background:var(--brightgray);text-decoration:none}
.rc-resources{margin-top:32px}
.rc-resources h3{font-size:.84rem;font-weight:800;text-transform:uppercase;letter-spacing:.5px;color:var(--gray);margin:0 0 12px}
@media(max-width:640px){.rc-hero{padding:30px 16px 26px}.rc-hero h1{font-size:1.65rem}.rc-2col{grid-template-columns:1fr}.rc-hero-stats{gap:14px}.rc-sec-header{flex-direction:column}.rc-sec-nav{flex-direction:column;align-items:stretch}.rc-phase-banner{flex-direction:column}}
</style>

<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">🚀 Navigate · Launchpad</div>
    <h1>Welcome to Launchpad</h1>
    <p>Your step-by-step guide to optimizing Recurly, mastering your metrics, and building a thriving subscription business — starting right now.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">2</div><div class="rc-lbl">Phases</div></div>
      <div><div class="rc-num">90</div><div class="rc-lbl">Days to Complete</div></div>
      <div><div class="rc-num">Self-Paced</div><div class="rc-lbl">Step by Step</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one" class="rc-active"><span class="rc-snum">🏠</span>Welcome</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing"><span class="rc-snum">1</span>Production Testing</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-dunning-optimization"><span class="rc-snum">2</span>Dunning</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-account-updater"><span class="rc-snum">3</span>Account Updater</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-branding"><span class="rc-snum">4</span>Branding</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-gateway-failover"><span class="rc-snum">5</span>Gateway Failover</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-review"><span class="rc-snum">✓</span>Review &amp; Resources</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎉</div>
      <div>
        <h2>You're Live — Now Let's Optimize</h2>
        <p>Going live is just the beginning. Launchpad is your guided program to make sure Recurly is working as hard as possible for your business from day one.</p>
      </div>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">🧭 What is Navigate Launchpad?</p>
      <p style="font-size:.9rem;color:var(--darkgray);line-height:1.7;margin:0 0 12px">Navigate Launchpad is Recurly's self-paced optimization program for new merchants. It's designed to be completed within 90 days of going live in production — walking you through the most impactful configurations, best practices, and data insights, one step at a time.</p>
      <p style="font-size:.9rem;color:var(--darkgray);line-height:1.7;margin:0">You don't need to rush. Each module builds on the last. Work through them at your own pace and come back anytime.</p>
    </div>

    <div class="rc-card">
      <p class="rc-subhead">▶ Trail Guide: Welcome &amp; UI Walkthrough</p>
      <div class="rc-video-wrap">
        <iframe src="https://share.synthesia.io/embeds/videos/ee258c32-42a5-4b28-81f9-47b13ec52fe2" loading="lazy" title="Navigate Launchpad — Welcome &amp; UI Walkthrough" allow="encrypted-media; fullscreen;" allowfullscreen></iframe>
      </div>
      <p class="rc-video-cap">Get oriented with Recurly's UI, admin navigation, and key support resources.</p>
    </div>

    <p class="rc-subhead" style="margin-bottom:12px">📅 Your Two-Phase Journey</p>

    <div class="rc-phase-banner">
      <div class="rc-phase-icon">⚙️</div>
      <div style="flex:1">
        <h3>Phase 1: Optimization</h3>
        <p style="margin-bottom:12px">Lock in the configurations that protect your revenue and deliver a polished subscriber experience.</p>
        <div class="rc-phase-step"><div class="rc-phase-dot">1</div>Final Production Testing</div>
        <div class="rc-phase-step"><div class="rc-phase-dot">2</div>Optimize Your Dunning Strategy</div>
        <div class="rc-phase-step"><div class="rc-phase-dot">3</div>Enable Account Updater</div>
        <div class="rc-phase-step"><div class="rc-phase-dot">4</div>Brand Your Emails &amp; Invoices</div>
        <div class="rc-phase-step"><div class="rc-phase-dot">5</div>Set Up Gateway Failover</div>
      </div>
    </div>

    <div class="rc-phase-banner">
      <div class="rc-phase-icon">📊</div>
      <div style="flex:1">
        <h3 style="color:var(--orange)">Phase 2: Mastering Metrics</h3>
        <p style="margin-bottom:12px">Understand the six core KPIs that drive subscription growth, retention, and revenue recovery.</p>
        <div class="rc-phase-step"><div class="rc-phase-dot orange">1</div>Benchmarks Dashboard &amp; Reporting Tools</div>
        <div class="rc-phase-step"><div class="rc-phase-dot orange">2</div>Subscriber Acquisition &amp; Sign-Up Decline Rate</div>
        <div class="rc-phase-step"><div class="rc-phase-dot orange">3</div>Voluntary &amp; Involuntary Churn</div>
        <div class="rc-phase-step"><div class="rc-phase-dot orange">4</div>Renewal Invoice Paid Rate &amp; Recovered Revenue</div>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 How to use Launchpad:</strong> Each module includes a Trail Guide video, step-by-step setup guidance, best practices, and a completion checklist. Use the navigation above to move between modules — you can return to any step at any time.
    </div>

    <div class="rc-2col">
      <div class="rc-card">
        <p class="rc-subhead">📞 Your Customer Support Team</p>
        <p style="font-size:.87rem;color:var(--gray);line-height:1.6;margin:0 0 10px">Have questions as you work through Launchpad? Recurly Support is here to help.</p>
        <a class="rc-link-btn" style="font-size:.82rem;padding:9px 14px" href="mailto:support@recurly.com">✉ support@recurly.com</a>
      </div>
      <div class="rc-card">
        <p class="rc-subhead">📥 Download Your Resource Guide</p>
        <p style="font-size:.87rem;color:var(--gray);line-height:1.6;margin:0 0 10px">A quick-reference guide to all Recurly support links, documentation, and program resources.</p>
        <a class="rc-link-btn rc-link-sec" style="font-size:.82rem;padding:9px 14px" href="https://go.recurly.com/recurly_navigate_resource_guide.html" target="_blank" rel="noopener noreferrer">⬇ Navigate Resource Guide</a>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing">🎯 Start Course</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch-phase-one-production-testing">Step 1: Production Testing →</a>
    </div>

    <div class="rc-resources">
      <h3>Additional Resources</h3>
      <a class="rc-link-btn" href="https://docs.recurly.com/recurly-subscriptions/" target="_blank" rel="noopener noreferrer">📖 Recurly Documentation</a>
      <a class="rc-link-btn rc-link-sec" href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer">🎧 Navigate Events &amp; Webinars</a>
      <a class="rc-link-btn rc-link-sec" href="mailto:support@recurly.com">✉ Contact Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
