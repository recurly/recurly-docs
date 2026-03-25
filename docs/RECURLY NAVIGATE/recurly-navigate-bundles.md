---
title: Recurly Commerce Bundles
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<style>
  .rc-guide{
    --yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;
    --gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;
    font-family:'Segoe UI',system-ui,sans-serif;
  }
  *{box-sizing:border-box}
  body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
  .rc-hero{background:var(--offblack);color:#fff;padding:56px 40px 48px;text-align:center;border-radius:16px}
  .rc-badge{display:inline-block;background:var(--yellow);color:var(--offblack);border-radius:20px;padding:6px 18px;font-size:13px;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:20px}
  .rc-hero h1{font-size:2.4rem;font-weight:800;line-height:1.15;margin:0 0 14px;color:var(--offwhite)}
  .rc-hero>p{font-size:1.05rem;opacity:.8;max-width:680px;margin:0 auto 32px;color:var(--lightgray)}
  .rc-hero-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap}
  .rc-num{font-size:1.8rem;font-weight:800;color:var(--yellow)}
  .rc-lbl{font-size:.8rem;color:var(--lightgray);text-transform:uppercase;letter-spacing:.5px}
  .rc-nav{display:flex;flex-wrap:wrap;gap:10px;margin:24px 0 28px}
  .rc-nav a{display:inline-flex;align-items:center;gap:8px;padding:10px 14px;border-radius:12px;border:1px solid var(--lightgray);background:#fff;color:var(--darkgray);text-decoration:none;font-size:.88rem;font-weight:700;transition:border-color .2s,box-shadow .2s}
  .rc-nav a:hover{border-color:var(--yellow);box-shadow:0 2px 8px rgba(255,215,6,.2);color:var(--offblack)}
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack);box-shadow:0 2px 10px rgba(255,215,6,.25)}
  .rc-snum{display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;border-radius:50%;background:var(--offblack);color:var(--yellow);font-size:12px;font-weight:700;flex-shrink:0}
  .rc-sec{margin-bottom:56px}
  .rc-sec-header{display:flex;align-items:flex-start;gap:20px;margin-bottom:32px}
  .rc-sec-icon{width:56px;height:56px;border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:26px;flex-shrink:0;background:var(--yellow)}
  .rc-sec-header h2{font-size:1.7rem;font-weight:800;margin:0 0 6px;color:var(--offblack)}
  .rc-sec-header>div>p{color:var(--gray);font-size:.95rem;line-height:1.5;margin:0}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-video-wrap{position:relative;overflow:hidden;aspect-ratio:16/9;border-radius:14px;margin-bottom:14px}
  .rc-video-wrap iframe{position:absolute;width:100%;height:100%;top:0;left:0;border:none}
  .rc-3col{display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px;margin-bottom:28px}
  .rc-value-card{border-radius:16px;overflow:hidden;border:1px solid var(--lightgray)}
  .rc-value-header{background:var(--offblack);padding:18px 20px;display:flex;align-items:center;gap:12px}
  .rc-value-header span{font-size:22px}
  .rc-value-header h3{color:var(--yellow);font-size:.95rem;font-weight:800;margin:0}
  .rc-value-body{padding:18px 20px;background:var(--offwhite)}
  .rc-value-body p{font-size:.86rem;color:var(--darkgray);line-height:1.6;margin:0 0 10px}
  .rc-value-body p:last-child{margin:0}
  .rc-example{background:#fff;border-left:3px solid var(--yellow);border-radius:0 8px 8px 0;padding:10px 14px;margin-top:12px;font-size:.82rem;color:var(--gray);line-height:1.5;font-style:italic}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-right-for-me{background:var(--offblack);border-radius:16px;padding:32px;margin-bottom:28px}
  .rc-right-for-me h3{color:var(--yellow);font-size:1.1rem;font-weight:800;margin:0 0 20px}
  .rc-rfm-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
  .rc-rfm-item{background:rgba(255,255,255,.07);border-radius:12px;padding:14px 16px;border:1px solid rgba(255,255,255,.1)}
  .rc-rfm-item h4{font-size:.85rem;font-weight:700;color:var(--yellow);margin:0 0 4px}
  .rc-rfm-item p{font-size:.8rem;color:var(--lightgray);line-height:1.5;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-disabled,.rc-btn-next,.rc-btn-prev,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);border:1px solid var(--lightgray);cursor:default}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){
    .rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}
    .rc-3col,.rc-rfm-grid{grid-template-columns:1fr}
    .rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}
  }
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-hero">
    <div class="rc-badge">📦 Navigate · Commerce Bundles</div>
    <h1>Commerce Bundles</h1>
    <p>Let subscribers build their own box — and watch your AOV, retention, and product discovery grow with every selection.</p>
    <div class="rc-hero-stats">
      <div><div class="rc-num">↑ AOV</div><div class="rc-lbl">Higher Order Value</div></div>
      <div><div class="rc-num">2</div><div class="rc-lbl">Bundle Types</div></div>
      <div><div class="rc-num">↓ Churn</div><div class="rc-lbl">Subscriber Retention</div></div>
    </div>
  </div>

  <nav class="rc-nav">
    <a class="is-active" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-why"><span class="rc-snum">1</span>Why Bundles?</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-what"><span class="rc-snum">2</span>What Are Bundles?</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-see-it"><span class="rc-snum">3</span>See It In Action</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-set-it-up"><span class="rc-snum">4</span>Set It Up</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-go-live"><span class="rc-snum">✓</span>Go Live</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🚀</div>
      <div>
        <h2>Why Bundles?</h2>
        <p>Before diving into how Bundles work, let's ground ourselves in why they matter — and what they can do for your business.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 The Value of Bundles</h3>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/1uDB4T69J0oOJjC7IbjDK-H78G4N2U3zS-6cuCmTxudo/preview" loading="lazy" title="The Value of Bundles" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0;">Kat from Recurly's product marketing team explains the business case for Commerce Bundles.</p>
    </div>

    <h3 class="rc-subhead">💡 Three Reasons Bundles Move the Needle</h3>
    <div class="rc-3col">
      <div class="rc-value-card">
        <div class="rc-value-header"><span>📈</span><h3>Increase Average Order Value</h3></div>
        <div class="rc-value-body">
          <p>When subscribers choose their own items, they naturally add more — because they're picking what they <em>actually</em> want, not settling for a preset box.</p>
          <div class="rc-example">A coffee brand offers "pick any 3 for $45." Customers are subtly nudged to explore and fill their box — driving higher order value without heavy discounting.</div>
        </div>
      </div>
      <div class="rc-value-card">
        <div class="rc-value-header"><span>🔍</span><h3>Drive Product Discovery</h3></div>
        <div class="rc-value-body">
          <p>Instead of relying on customers to find newer or slower-moving products on their own, you put those items directly in the path of purchase — inside the bundle.</p>
          <div class="rc-example">A wellness brand lets subscribers build their own supplement stack. Vitamin K and D get discovered together because they're presented as a natural pairing in the bundle.</div>
        </div>
      </div>
      <div class="rc-value-card">
        <div class="rc-value-header"><span>🛡️</span><h3>Reduce Voluntary Churn</h3></div>
        <div class="rc-value-body">
          <p>Subscribers stay longer when they feel in control. When a customer can swap items before each renewal, they have no reason to cancel — the subscription evolves as their tastes change.</p>
          <div class="rc-example">"If I can swap what's in my box from my customer portal, I'm much less likely to cancel because I know the subscription will evolve as my tastes change." — Kat, Recurly PMM</div>
        </div>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">🎯</span>
      <div><h4>You Stay in Control</h4><p>You define the products available, set the pricing model, and control the guardrails — quantity limits, bundle sizes, which collections are included. Bundles give your subscribers agency within a structure <em>you</em> design.</p></div>
    </div>

    <div class="rc-right-for-me">
      <h3>📋 Is This Right for My Business?</h3>
      <div class="rc-rfm-grid">
        <div class="rc-rfm-item"><h4>✅ You sell a catalog of complementary products</h4><p>Flavors, scents, sizes, styles — products that naturally go together and benefit from being mixed and matched.</p></div>
        <div class="rc-rfm-item"><h4>✅ You run a subscription box model</h4><p>You already curate boxes for subscribers and want to give them input into what's inside — improving satisfaction and reducing churn.</p></div>
        <div class="rc-rfm-item"><h4>✅ You want to surface slower-moving products</h4><p>Bundles put new or underperforming products in the path of purchase without requiring customers to seek them out.</p></div>
        <div class="rc-rfm-item"><h4>✅ You want higher AOV without heavy discounting</h4><p>The "build your own" experience naturally drives more items per order. It's value-led, not discount-led growth.</p></div>
        <div class="rc-rfm-item"><h4>⚠️ You sell only one or two products</h4><p>Bundles need variety to create a meaningful choice experience. A single-SKU catalog won't benefit from this feature.</p></div>
        <div class="rc-rfm-item"><h4>⚠️ Your subscriptions are purely digital or B2B</h4><p>Commerce Bundles is built for physical product subscriptions on Shopify. It's not designed for SaaS or digital-only offers.</p></div>
      </div>
    </div>

    <div class="rc-sec-nav">
      <span class="rc-btn-disabled">← Back</span>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-what">Next: What Are Bundles? →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer">📖 Bundles Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>
