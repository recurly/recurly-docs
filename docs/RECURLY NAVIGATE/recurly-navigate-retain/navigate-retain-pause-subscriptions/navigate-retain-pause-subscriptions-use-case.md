---
title: Pause API Test - Use Case
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
.rc-btn-next-dis { background: #CCC9B8; color: #807D73; padding: 12px 24px; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 14px; opacity: 0.5; pointer-events: none; }

.rc-link-sec { padding: 32px 40px; background: #F1EFE3; border-top: 1px solid #CCC9B8; border-radius: 0 0 16px 16px; }
.rc-link-btn { display: inline-flex; align-items: center; background: #ffffff; border: 1px solid #CCC9B8; padding: 10px 20px; border-radius: 8px; text-decoration: none; color: #0D0D0B; font-size: 14px; font-weight: 500; margin: 4px; }
</style>

<div class="rc-guide">
  <div class="rc-hero">
    <div class="rc-hero-topo"></div>
    <img src="https://drive.google.com/thumbnail?sz=w200&id=1rpQ40zAs49C7xuFkSau7-UimkPNxwMa2" alt="Retain" style="width:36px;height:36px;margin-bottom:8px;display:block;margin-left:auto;margin-right:auto;position:relative;z-index:1;" />
    <span class="rc-badge">Subscriptions</span>
    <h1>Pause, Not Cancel</h1>
    <p class="rc-subtitle">Build a compelling business case and secure buy-in across your organization.</p>
    <div class="rc-flywheel-badge">RETAIN</div>
    <div class="rc-stats">
      <div class="rc-stat"><span class="rc-stat-num">7</span> sections</div>
      <div class="rc-stat"><span class="rc-stat-num">24</span> min read</div>
    </div>
  </div>

  <nav class="rc-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions"><span class="rc-snum">1</span> What Is It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-benefits"><span class="rc-snum">2</span> Why Use It?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-considerations"><span class="rc-snum">3</span> Things to Consider</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-fit"><span class="rc-snum">4</span> When Not to Use It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-enable"><span class="rc-snum">5</span> How to Enable It</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data"><span class="rc-snum">6</span> Tracking Impact</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-use-case" class="is-active"><span class="rc-snum">7</span> Pitch to Leadership</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon"><img src="https://drive.google.com/thumbnail?sz=w200&id=1HhXev0Ya9ke3e1IxfytHklXgrvT0taWq" alt="pitch" width="28" height="28" /></div>
      <div>
        <h2 style="margin:0;">Pitch to Leadership</h2>
        <p style="margin:4px 0 0; color:#807D73;">Secure stakeholder buy-in by framing Pause as a strategic investment in LTV and churn reduction.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3>Why This Conversation Matters</h3>
      <p>Introducing a pause option may initially feel counterintuitive — a paused subscriber stops paying, after all. But forcing a binary "stay or cancel" decision pushes people to leave permanently. Pause transforms friction into a retention opportunity, keeping credentials on file and maximizing reactivation probability.</p>
    </div>

    <div class="rc-subhead">The Executive Summary Framework</div>
    <div class="rc-step">
      <div class="rc-sbadge">1</div>
      <div style="flex:1;"><h4>Open With the Churn Problem</h4><p style="margin:0; font-size:14px; color:#32312D;">Lead with your voluntary churn MRR. Highlight that many cancellations are "soft" (temporary intent) and could be recovered.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">2</div>
      <div style="flex:1;"><h4>Present the Pause Value Prop</h4><p style="margin:0; font-size:14px; color:#32312D;">Focus on three pillars: preserved relationships, zero re-acquisition friction, and automatic reactivation logic.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">3</div>
      <div style="flex:1;"><h4>Show the Financial Model</h4><p style="margin:0; font-size:14px; color:#32312D;">Compare re-acquisition costs (5-7x higher) vs retention costs ($0). Even recovering 10% of churners is high ROI.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">4</div>
      <div style="flex:1;"><h4>Address the Revenue Gap</h4><p style="margin:0; font-size:14px; color:#32312D;">Frame it correctly: the alternative isn't a paying user, it's a cancelled user generating zero revenue forever.</p></div>
    </div>
    <div class="rc-step">
      <div class="rc-sbadge">5</div>
      <div style="flex:1;"><h4>Close With Competitive Context</h4><p style="margin:0; font-size:14px; color:#32312D;">Pause is becoming a standard feature. Not offering it puts your brand at a competitive disadvantage.</p></div>
    </div>

    <div class="rc-subhead">Key Metrics for the Pitch</div>
    <div class="rc-3col">
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1zog70GXF8MGG0LH8XR1pClQj4Xp41PBe" alt="cac" width="28" height="28" style="margin-bottom:8px;" />
        <h4>CAC Savings</h4>
        <p>Retaining a paused user costs $0 vs. your current marketing CAC.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=18clYe_73mC2yDcICqfLcwtDvAXSiuAN4" alt="mrr" width="28" height="28" style="margin-bottom:8px;" />
        <h4>Recovered MRR</h4>
        <p>Projected revenue from resumed users over a 12-month window.</p>
      </div>
      <div class="rc-wi">
        <img src="https://drive.google.com/thumbnail?sz=w200&id=1IvV473EacJuzoqsAw0D-wrs4MY-gx2SI" alt="ltv" width="28" height="28" style="margin-bottom:8px;" />
        <h4>LTV Delta</h4>
        <p>Projected LTV of a resumed user vs. a cancelled user.</p>
      </div>
    </div>

    <div class="rc-subhead">Tailoring by Stakeholder</div>
    <div class="rc-2col">
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">CFO / Finance</h4>
        <p style="font-size:14px;">Focus on ARR impact and the net benefit of recovered revenue over marketing re-spend.</p>
      </div>
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">CPO / Product</h4>
        <p style="font-size:14px;">Emphasize delight and how Recurly handles the billing logic natively (low engineering effort).</p>
      </div>
    </div>
    <div class="rc-2col" style="margin-top:0;">
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">CMO / Growth</h4>
        <p style="font-size:14px;">Position pause as a warm-lead channel for reactivation campaigns instead of cold win-backs.</p>
      </div>
      <div class="rc-wi" style="text-align:left;">
        <h4 style="margin:0 0 8px;">CTO / Engineering</h4>
        <p style="font-size:14px;">Highlight platform-native webhooks and API simplicity for quick implementation.</p>
      </div>
    </div>

    <div class="rc-tip">
      <strong>💡 Pro Tip: Propose a Pilot Program</strong>
      <p style="margin:8px 0 0;">Roll out pause for a single plan for 60-90 days. Use those internal results to prove the resume rate before a full launch.</p>
    </div>

    <div class="rc-subhead">Common Objections</div>
    <div class="rc-card" style="padding:20px;">
      <h4 style="margin:0 0 8px;">"Will subscribers abuse this?"</h4>
      <p style="margin:0; font-size:14px;">Abuse is negligible. Users most likely to pause are those who would have cancelled anyway. You control frequency limits.</p>
    </div>
    <div class="rc-card" style="padding:20px;">
      <h4 style="margin:0 0 8px;">"We lose revenue during the gap."</h4>
      <p style="margin:0; font-size:14px;">Resumed users stay longer and pay full price. A paused user who stays 12 more months is 12x more valuable than a churner.</p>
    </div>

    <div class="rc-warning">
      <strong>⚠️ Don't Pitch Pause in Isolation</strong>
      <p style="margin:8px 0 0;">Frame it as part of a holistic retention strategy alongside cancel-save flows and advanced dunning for the best impact.</p>
    </div>

    <div class="rc-checklist">
      <h3 style="font-size:18px; margin:0 0 16px;">Pitch Deck Template Items</h3>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Current voluntary churn MRR impact</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Conservative recovered MRR projection</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Implementation timeline (minimal engineering)</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Success KPIs (Adoption & Resume Rates)</label></div>
      <div class="rc-cli"><div class="rc-cb"></div><label style="font-size:14px;">Risk mitigation (Max duration caps)</label></div>
    </div>

    <div class="rc-tip" style="background:#0D0D0B; color:white; border-left-color:#FFD706;">
      <strong style="color:#FFD706;">Final Thought: Start the Conversation Today</strong>
      <p style="margin:8px 0 0;">The best time to enable pause is before your next churn spike. Giving subscribers choices at the point of cancellation creates long-term brand equity.</p>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions-data" class="rc-btn-prev">← Previous</a>
    <span style="color:#807D73; font-weight:600; font-size:14px;">● Page 7 of 7</span>
    <a href="#" class="rc-btn-next-dis">Course Complete ✓</a>
  </div>

  <div class="rc-link-sec">
    <h3 style="font-size:18px; margin:0 0 16px;">Additional Resources</h3>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/pause-subscription" class="rc-link-btn">📄 Documentation</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain-pause-subscriptions" class="rc-link-btn">🔄 Restart Course</a>
  </div>
</div>
`}</HTMLBlock>

<br />
