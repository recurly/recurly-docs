---
title: Pause API Test - Benefits
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
/* 1. MASTER PAGE OVERRIDES - Forces the entire ReadMe page color */
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
    <p class="rc-subtitle">Learn how Recurly's Pause subscriptions feature reduces voluntary churn by giving subscribers a reason to stay instead of leave.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits" class="is-active"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1dQpFxnm38HN6ZNeRBSjP3R4Tt--R_wON" alt="lightbulb" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0;">Why Use It?</h2>
        <p style="margin:4px 0 0; color:#807D73;">The strategic case for offering pause as a retention lever—backed by behavioral science and real business impact.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>The Core Problem: Cancellation Is a One-Way Door</h3>
      <p>When a subscriber clicks "cancel," they cross a psychological threshold that's extremely difficult to reverse. Research consistently shows that re-acquiring a churned customer costs 5–7x more than retaining an existing one. Even with the best win-back campaigns, only 10-20% of churned subscribers ever return.</p>
      <p>The root issue is that most flows present a binary choice: stay or leave. But reasons for canceling are rarely permanent. Financial constraints, travel, or seasonal usage are all temporary states. Pause bridges this gap, preserving the relationship, the payment method, and the behavioral habit of being a subscriber.</p>
    </div>

    <div class="rc-subhead">The Business Case by the Numbers</div>
    <div class="rc-3col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="wallet" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Lower CAC Pressure</h4>
        <p>Retaining a subscriber who pauses eliminates the need to spend acquisition dollars replacing them.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="chart" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Higher LTV</h4>
        <p>A subscriber who pauses for one month then resumes generates far more revenue than one who cancels.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zK3mlZEE50CjiIH_pQo1ytqaz3gVvgjP" alt="goodwill" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Brand Goodwill</h4>
        <p>Offering pause signals that you value your subscribers as people, building trust and referrals.</p>
      </div>
    </div>

    <div class="rc-subhead">Why Pause Outperforms Other Retention Tactics</div>
    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;"><h4>Pause vs. Discount Offers</h4><p style="margin:0; font-size:14px; color:#32312D;">Discounts erode ARPU and train subscribers to expect price reductions. Pause addresses the root cause without devaluing your product.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;"><h4>Pause vs. Plan Downgrade</h4><p style="margin:0; font-size:14px; color:#32312D;">Downgrading often leads to permanent revenue reduction. Pause keeps the subscriber on their original plan, making resumption to full MRR automatic.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;"><h4>Pause vs. Win-Back Campaigns</h4><p style="margin:0; font-size:14px; color:#32312D;">Win-back campaigns target people after they've already left. Pause intervenes before the relationship ends, yielding much higher conversion rates.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;"><h4>Pause vs. Cancel-Save Flows Alone</h4><p style="margin:0; font-size:14px; color:#32312D;">Pause works brilliantly as an offer within a deflection flow, providing a compelling, no-cost-to-you alternative to cancellation.</p></div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Pair Pause with Cancel-Save Flows</strong>
      <p style="margin:8px 0 0;">Merchants who embed pause as a cancel-save offer typically see significantly higher deflection rates compared to discount-only flows.</p>
    </div>

    <div class="rc-subhead">Who Benefits Most from Pause?</div>
    <div class="rc-2col">
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">Seasonal & Lifestyle</h4>
        <p style="font-size:14px;">Fitness, travel, and education apps see natural usage dips. Pause keeps these users in your ecosystem through their natural gaps.</p>
      </div>
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">Budget-Sensitive</h4>
        <p style="font-size:14px;">During tight financial periods, a subscriber who pauses is overwhelmingly likely to resume once their situation stabilizes.</p>
      </div>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Important: Pause Is a Retention Tool, Not a Revenue Strategy</strong>
      <p style="margin:8px 0 0;">While pause improves LTV, it temporarily reduces MRR. Set expectations with leadership that this short-term deferral is an investment in long-term preservation.</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Is Pause Right for Your Business?</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Your voluntary churn exceeds 5% monthly</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Subscribers cite temporary reasons (budget, travel) for leaving</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Your product has seasonal or cyclical usage patterns</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">You want to improve brand perception at the point of cancellation</label></div>
    </div>

    <div class="rc-tip">
      <strong>The Retention Flywheel Effect</strong>
      <p style="margin:8px 0 0;">Every subscriber saved via pause is one fewer you need to replace. This frees up budget to invest in further improvements, creating a positive feedback loop for your base.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 2 of 7</span>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations" class="rc-btn-next">Next: Considerations →</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Documentation</a>
    <a href="https://docs.google.com/videos/d/1pq5dvNPwOEp7mksTP7XSmPjGaebdujtXluiHpebjTKQ/edit?usp=sharing" class="rc-link-btn">🎥 Video Walkthrough</a>
  </div>
</div>
`}</HTMLBlock>

<br />
