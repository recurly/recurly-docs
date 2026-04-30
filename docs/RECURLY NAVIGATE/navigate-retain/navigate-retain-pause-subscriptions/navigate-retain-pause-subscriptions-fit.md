---
title: Pause API Test - Fit
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. MASTER PAGE OVERRIDES */
body, .theme-doc, .main-content { background-color: #F5F5F0 !important; }
.rc-guide { font-family: "Inter", -apple-system, sans-serif; color: #0D0D0B; max-width: 900px; margin: 0 auto; background: #F5F5F0; }

/* 2. HERO SECTION */
.rc-hero { background: #0D0D0B; color: white; padding: 48px 40px; border-radius: 16px 16px 0 0; text-align: center; position: relative; overflow: hidden; }
.rc-hero-topo { position: absolute; top: 0; left: 0; right: 0; bottom: 0; background-image: url('https://drive.google.com/thumbnail?sz=w1000&id=1gLpfq5s-rR8anlQVCGhpNTPzPopYdPEd'); opacity: 0.1; pointer-events: none; }
.rc-badge { background: #FFD706; color: #0D0D0B; padding: 4px 16px; border-radius: 100px; font-size: 13px; font-weight: 600; display: inline-block; text-transform: uppercase; letter-spacing: 0.5px; position: relative; z-index: 1; }
.rc-hero h1 { font-size: 32px; margin: 16px 0 8px; font-weight: 700; position: relative; z-index: 1; }
.rc-subtitle { color: #CCC9B8; font-size: 16px; margin: 0; position: relative; z-index: 1; }
.rc-flywheel-badge { padding: 4px 12px; border-radius: 100px; font-size: 11px; font-weight: 700; display: inline-block; text-transform: uppercase; letter-spacing: 1px; margin-top: 12px; background: #FF9D88; color: #0D0D0B; position: relative; z-index: 1; }
.rc-stats { display: flex; justify-content: center; gap: 32px; margin-top: 24px; position: relative; z-index: 1; }
.rc-stat { color: #CCC9B8; font-size: 14px; }
.rc-stat-num { color: #FFD706; font-weight: 700; font-size: 20px; display: block; }

/* 3. NAVIGATION */
.rc-nav { display: flex; background: #F1EFE3; padding: 0; overflow-x: auto; border-bottom: 2px solid #CCC9B8; }
.rc-nav a { display: flex; align-items: center; gap: 8px; padding: 14px 20px; text-decoration: none; color: #807D73; font-size: 14px; font-weight: 500; white-space: nowrap; border-bottom: 3px solid transparent; transition: all 0.2s; }
.rc-nav a:hover { color: #0D0D0B; background: #FFFDF2; }
.rc-nav a.is-active { color: #0D0D0B; font-weight: 600; border-bottom-color: #FFD706; background: #F5F5F0; }
.rc-snum { width: 24px; height: 24px; border-radius: 50%; background: #CCC9B8; color: #807D73; display: inline-flex; align-items: center; justify-content: center; font-size: 12px; font-weight: 700; flex-shrink: 0; }
.rc-nav a.is-active .rc-snum { background: #FFD706; color: #0D0D0B; }

/* 4. CONTENT AREA */
.rc-sec { padding: 40px; background: #F5F5F0; }
.rc-sec-header { display: flex; gap: 20px; align-items: flex-start; margin-bottom: 32px; }
.rc-sec-icon { width: 48px; height: 48px; background: #FFD706; border-radius: 12px; display: flex; align-items: center; justify-content: center; flex-shrink: 0; }
.rc-card { background: #F1EFE3; border-radius: 12px; padding: 28px; margin-bottom: 20px; border: 1px solid #CCC9B8; }
.rc-card h3 { font-size: 18px; margin: 0 0 12px; font-weight: 600; }
.rc-card p { color: #32312D; line-height: 1.7; margin: 0 0 12px; font-size: 15px; }

.rc-subhead { font-size: 20px; font-weight: 700; margin: 32px 0 16px; color: #0D0D0B; }
.rc-step { display: flex; gap: 16px; align-items: flex-start; background: #F1EFE3; border-radius: 12px; padding: 20px; margin-bottom: 16px; border: 1px solid #CCC9B8; }
.rc-sbadge { width: 32px; height: 32px; border-radius: 50%; background: #FFD706; color: #0D0D0B; display: flex; align-items: center; justify-content: center; font-weight: 700; flex-shrink: 0; }

.rc-3col { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin: 20px 0; }
.rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin: 20px 0; }
.rc-wi { background: #F1EFE3; border-radius: 12px; padding: 24px; text-align: center; border: 1px solid #CCC9B8; }
.rc-wi h4 { font-size: 16px; margin: 12px 0 8px; font-weight: 600; }
.rc-wi p { font-size: 13px; color: #807D73; margin: 0; }

.rc-checklist { background: #F1EFE3; border-radius: 12px; padding: 24px; margin: 20px 0; border: 1px solid #CCC9B8; }
.rc-cli { display: flex; align-items: flex-start; gap: 12px; padding: 8px 0; }
.rc-cb { width: 18px; height: 18px; border-radius: 4px; border: 2px solid #CCC9B8; flex-shrink: 0; margin-top: 3px; background: white; }

.rc-tip { border-left: 4px solid #FFD706; background: #F1EFE3; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FFD706; }
.rc-warning { border-left: 4px solid #FF8200; background: #FFF8F0; padding: 20px 24px; border-radius: 0 12px 12px 0; margin: 24px 0; border: 1px solid #CCC9B8; border-left-width: 4px; border-left-color: #FF8200; }

.rc-sec-nav { display: flex; justify-content: space-between; padding: 24px 40px 40px; align-items: center; background: #F5F5F0; }
.rc-btn-prev { background: #F1EFE3; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #CCC9B8; }
.rc-btn-next { background: #FFD706; color: #0D0D0B; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; border: 1px solid #FFD706; }

.rc-link-sec { padding: 32px 40px; background: #F1EFE3; border-top: 1px solid #CCC9B8; border-radius: 0 0 16px 16px; }
.rc-link-btn { display: inline-flex; align-items: center; background: #ffffff; border: 1px solid #CCC9B8; padding: 10px 20px; border-radius: 8px; text-decoration: none; color: #0D0D0B; font-size: 14px; font-weight: 500; margin: 4px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain stage" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Learn when the Pause subscriptions feature is the right tool—and when other retention strategies serve you better.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">25</span> min read</div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit" class="is-active"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1wcvg3Ufxub3-78NL1HaxIBh01CLx5f5W" alt="alert" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0;">When Not to Use It</h2>
        <p style="margin:4px 0 0; color:#807D73;">Pause is a powerful retention lever, but it's not a universal fix. Match the right intervention to the right reason.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Pause Is One Tool in a Larger Retention Toolkit</h3>
      <p>Recurly's Pause feature is designed for subscribers who intend to return but need temporary relief. However, if a subscriber is dissatisfied with your product or looking for a better price, offering a pause can feel tone-deaf and simply delay inevitable churn. Matching the intervention to the specific reason for leaving is the key to a robust strategy.</p>
    </div>

    <div class="rc-subhead">Scenarios Where Pause Is the Wrong Move</div>

    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;"><h4>Product Dissatisfaction</h4><p style="margin:0; font-size:14px; color:#32312D;">If the product doesn't meet expectations, a pause won't fix the root cause. Use a cancel-save flow to capture feedback and re-engage them later with a "we've improved" campaign.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;"><h4>Price Sensitivity</h4><p style="margin:0; font-size:14px; color:#32312D;">Subscribers wanting a lower price aren't looking for a break. Offer a plan downgrade or a limited-time discount instead to directly address the price objection.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;"><h4>Mental Churn</h4><p style="margin:0; font-size:14px; color:#32312D;">If a subscriber has already found an alternative, a pause offer can feel manipulative. A graceful exit with a warm offboarding email is often the best long-term play for brand trust.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;"><h4>High Onboarding Costs</h4><p style="margin:0; font-size:14px; color:#32312D;">If your model involves high per-subscriber costs during active periods, a pause may create spikes in reactivation costs. Consider a reduced-service tier instead.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">5</div>
      <div style="flex:1;"><h4>Regulatory Restrictions</h4><p style="margin:0; font-size:14px; color:#32312D;">In industries like insurance or healthcare where continuous service is required, pausing may violate legal or contractual terms. Always consult with compliance teams.</p></div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Use Pause as a Dark Pattern</strong>
      <p style="margin:8px 0 0;">If most subscribers who pause cancel immediately after resumption, it signals pause is being offered to the wrong segment. A pause should never just delay churn; it should recover a relationship.</p>
    </div>

    <div class="rc-subhead">Better Alternatives by Cancellation Reason</div>
    <div class="rc-2col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="price" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Price Objection</h4>
        <p>Offer a plan downgrade, promotional discount, or switch to annual billing.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1_bHnEewv-l9uMxpkMdZvgKyKTiGuc4di" alt="chat" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Dissatisfaction</h4>
        <p>Capture feedback via surveys and route to Success teams for intervention.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1HhXev0Ya9ke3e1IxfytHklXgrvT0taWq" alt="comp" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Competitor Switch</h4>
        <p>Highlight unique value propositions and trigger 60-day win-back sequences.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="needed" width="28" height="28" style="margin-bottom:8px;" />
        <h4>No Longer Needed</h4>
        <p>Allow a graceful exit with an easy reactivation link for the future.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Layer Your Cancel-Save Flow Strategically</strong>
      <p style="margin:8px 0 0;">Use Recurly's cancel-save flows to ask <em>why</em> the subscriber is leaving first. Present pause as the primary option only when they select "traveling" or "seasonal use."</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Decision Framework: Should You Offer Pause?</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Survey data shows 15%+ subscribers citing temporary reasons for leaving</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Business model doesn't incur high costs during idle periods</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">You have a plan to re-engage subscribers before their pause ends</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">You are NOT in a regulated industry requiring continuous service</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">You have other interventions (downgrades) for price/product objections</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">You can track pause-to-reactivation rates specifically</label></div>
    </div>

    <div class="rc-card">
      <h3>The Bottom Line: Pause Complements—It Doesn't Replace</h3>
      <p>Pause is a surgical tool. It works best as part of a layered strategy that addresses every major reason—not just the temporary ones. The result is a measurable reduction in voluntary churn across your entire base.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 4 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable" class="rc-btn-next">Next: How to Enable It →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Video Walkthrough</a>
  </div>
</div>
`}</HTMLBlock>

<br />
