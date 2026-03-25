---
title: 'What are Bundles? '
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
  .rc-guide{--yellow:#FFD706;--orange:#FF8200;--offblack:#0D0D0B;--darkgray:#32312D;--gray:#807D73;--lightgray:#CCC9B8;--brightgray:#F1EFE3;--offwhite:#FFFDF2;font-family:'Segoe UI',system-ui,sans-serif}
  *{box-sizing:border-box}body{margin:0;font-family:'Segoe UI',system-ui,sans-serif;color:var(--darkgray)}
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
  .rc-nav a.is-active{background:var(--yellow);border-color:var(--yellow);color:var(--offblack)}
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
  .rc-compare{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin-bottom:28px}
  .rc-compare-card{border-radius:16px;overflow:hidden;border:2px solid var(--lightgray)}
  .rc-compare-card.fixed{border-color:var(--offblack)}
  .rc-compare-card.flexible{border-color:var(--yellow)}
  .rc-compare-header{padding:20px 24px;display:flex;align-items:center;gap:12px}
  .rc-compare-header.fixed{background:var(--offblack)}
  .rc-compare-header.flexible{background:var(--yellow)}
  .rc-compare-header.fixed h3{color:var(--yellow);font-size:1rem;font-weight:800;margin:0}
  .rc-compare-header.flexible h3{color:var(--offblack);font-size:1rem;font-weight:800;margin:0}
  .rc-compare-header span{font-size:24px}
  .rc-compare-body{padding:20px 24px;background:var(--offwhite)}
  .rc-compare-tagline{font-size:.82rem;font-weight:700;color:var(--gray);text-transform:uppercase;letter-spacing:.5px;margin:0 0 10px}
  .rc-compare-body p{font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 12px}
  .rc-compare-body p:last-child{margin:0}
  .rc-detail-row{border-top:1px solid var(--brightgray);padding-top:10px;margin-top:10px;font-size:.82rem;color:var(--darkgray);line-height:1.5}
  .rc-detail-row strong{color:var(--offblack)}
  .rc-table{width:100%;border-collapse:collapse;margin-bottom:28px;font-size:.87rem;border-radius:12px;overflow:hidden}
  .rc-table th{background:var(--offblack);color:var(--yellow);padding:13px 16px;text-align:left;font-weight:700;font-size:.78rem;text-transform:uppercase;letter-spacing:.5px}
  .rc-table td{padding:12px 16px;border-bottom:1px solid var(--brightgray);color:var(--darkgray);line-height:1.5;background:#fff}
  .rc-table tr:last-child td{border-bottom:none}
  .rc-table td:first-child{font-weight:600;color:var(--offblack);background:var(--offwhite)}
  .rc-steps{display:flex;flex-direction:column;gap:14px;margin-bottom:24px}
  .rc-step{background:var(--offwhite);border-radius:14px;padding:20px 24px;border:1px solid var(--lightgray);display:flex;gap:18px;align-items:flex-start}
  .rc-sbadge{width:36px;height:36px;border-radius:10px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:14px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h3{font-size:.95rem;font-weight:700;margin:0 0 4px;color:var(--offblack)}
  .rc-step p{font-size:.85rem;color:var(--gray);line-height:1.6;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-compare{grid-template-columns:1fr}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-why"><span class="rc-snum">1</span>Why Bundles?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-what"><span class="rc-snum">2</span>What Are Bundles?</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-see-it"><span class="rc-snum">3</span>See It In Action</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-set-it-up"><span class="rc-snum">4</span>Set It Up</a>
    <a href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-go-live"><span class="rc-snum">✓</span>Go Live</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">📦</div>
      <div>
        <h2>What Are Commerce Bundles?</h2>
        <p>A clear breakdown of how Bundles work and the two pricing models available to you — Fixed Price and Flexible Price.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Commerce Bundles Overview — With Merrell</h3>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/1lFcHAO_yng2CAHZY-87uzCV3cJw0IUS5qVUEawWhO5I/preview" loading="lazy" title="Commerce Bundles Technical Walkthrough" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0;">Merrell, your Recurly Customer Success Manager, walks through what Bundles are and how the two bundle types work.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🧩 The Simple Explanation</h3>
      <p style="font-size:.93rem;color:var(--darkgray);line-height:1.65;margin:0 0 14px;">Bundles are a way for merchants to group products together and offer them to subscribers as a curated, self-build experience. Instead of a preset box, your subscriber <strong>chooses what goes inside</strong> — from a collection <em>you</em> define.</p>
      <p style="font-size:.93rem;color:var(--darkgray);line-height:1.65;margin:0;">You set the rules. They do the fun part.</p>
    </div>

    <h3 class="rc-subhead">⚖️ The Two Bundle Types</h3>
    <div class="rc-compare">
      <div class="rc-compare-card fixed">
        <div class="rc-compare-header fixed"><span>🔒</span><h3>Fixed Price Bundle</h3></div>
        <div class="rc-compare-body">
          <p class="rc-compare-tagline">You define the price. It never changes.</p>
          <p>The price of the bundle is set by <strong>you</strong> on the Shopify bundle product — regardless of which specific items the subscriber selects. Subscribers subscribe at that stated price.</p>
          <div class="rc-detail-row"><strong>Shopify product price:</strong> Set to your desired bundle price</div>
          <div class="rc-detail-row"><strong>Bundle size:</strong> Fixed per variant — e.g. Small = 3 items, Large = 5 items</div>
          <div class="rc-detail-row"><strong>Best for:</strong> Promotions, seasonal boxes, "3 items for $35" style offers</div>
          <div class="rc-detail-row"><strong>Real example:</strong> Taste Ceremony's Puppy Party Box — subscribers pick from pet snacks and toys to fill a 3- or 5-product box at a flat price</div>
        </div>
      </div>
      <div class="rc-compare-card flexible">
        <div class="rc-compare-header flexible"><span>🔓</span><h3>Flexible Price Bundle</h3></div>
        <div class="rc-compare-body">
          <p class="rc-compare-tagline">Price is determined by what's in the box.</p>
          <p>The price updates <strong>dynamically</strong> as subscribers add or change items. The Shopify parent product is set to $0 — the final price is the sum of the individual items selected.</p>
          <div class="rc-detail-row"><strong>Shopify product price:</strong> Set to $0</div>
          <div class="rc-detail-row"><strong>Bundle size:</strong> Min/max range — e.g. minimum 2 items, unlimited max</div>
          <div class="rc-detail-row"><strong>Best for:</strong> Upselling premium products, "build your own" experiences</div>
          <div class="rc-detail-row"><strong>Real example:</strong> Barkwell Essentials — price is generated dynamically based on the specific products the subscriber includes in the box</div>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">📊 Quick Comparison</h3>
    <table class="rc-table">
      <thead>
        <tr><th>Detail</th><th>🔒 Fixed Price</th><th>🔓 Flexible Price</th></tr>
      </thead>
      <tbody>
        <tr><td>How price is set</td><td>Defined on the Shopify product</td><td>Sum of items selected by subscriber</td></tr>
        <tr><td>Shopify product price</td><td>Your desired bundle price</td><td>$0</td></tr>
        <tr><td>Bundle size</td><td>Set per variant (e.g. S=3, L=5)</td><td>Min and optional max item count</td></tr>
        <tr><td>Price when subscriber swaps</td><td>No change — price stays fixed</td><td>Updates to reflect new item prices</td></tr>
        <tr><td>Discounts</td><td>Yes — you can apply a discount on top</td><td>Yes — discount applies to dynamic total</td></tr>
        <tr><td>Variants supported</td><td>Yes — one level only</td><td>Yes — one level only</td></tr>
        <tr><td>Best use case</td><td>Flat-price promotions, gift boxes</td><td>Premium upsells, personalized boxes</td></tr>
      </tbody>
    </table>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Not Sure Which to Pick?</h4><p>Ask: do you want every subscriber to pay the same price, regardless of what they choose? → <strong>Fixed.</strong> Do you want pricing to reflect the actual value of products selected — encouraging premium picks? → <strong>Flexible.</strong> Many merchants launch with Fixed for simplicity and layer in a Flexible bundle later as an upsell offering.</p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🔗 One More Thing: The Building Blocks</h3>
      <p style="font-size:.88rem;color:var(--darkgray);line-height:1.6;margin:0 0 16px;">Every bundle is made up of two Shopify objects you create before configuring anything in Recurly Commerce:</p>
      <div class="rc-steps" style="margin-bottom:0;">
        <div class="rc-step"><div class="rc-sbadge">A</div><div><h3>The Parent Product</h3><p>The "container" product — what appears in your subscriber's cart and what they subscribe to. For Fixed bundles, this carries the price. For Flexible, it's set to $0.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">B</div><div><h3>The Collection</h3><p>The curated library of products your subscribers can choose from to fill their bundle. You control what's in it. These are set up in Shopify and linked to your bundle in Recurly Commerce.</p></div></div>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-why">← Why Bundles?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-see-it">Next: See It In Action →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer">📖 Bundles Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />