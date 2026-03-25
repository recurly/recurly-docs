---
title: See Bundles in action
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
  .rc-demo-label{display:inline-flex;align-items:center;gap:8px;background:var(--offblack);color:var(--yellow);border-radius:8px;padding:6px 14px;font-size:.78rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;margin-bottom:14px}
  .rc-callouts{display:flex;flex-direction:column;gap:10px;margin-bottom:4px}
  .rc-callout{display:flex;gap:12px;align-items:flex-start;background:#fff;border-radius:10px;padding:12px 14px;border:1px solid var(--brightgray)}
  .rc-callout-icon{font-size:18px;flex-shrink:0;margin-top:1px}
  .rc-callout-text{font-size:.85rem;color:var(--darkgray);line-height:1.5}
  .rc-callout-text strong{color:var(--offblack)}
  .rc-divider{height:1px;background:var(--lightgray);margin:32px 0}
  .rc-screenshot{border-radius:12px;border:1px solid var(--lightgray);width:100%;display:block;margin-bottom:8px}
  .rc-screenshot-cap{font-size:.78rem;color:var(--gray);margin-bottom:20px;line-height:1.4}
  .rc-2col-screens{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-bottom:16px}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-warning{background:#FFF8E6;border:1px solid var(--orange);border-radius:14px;padding:16px 20px;display:flex;gap:14px;align-items:flex-start;margin-bottom:24px}
  .rc-wicon{font-size:20px;flex-shrink:0}
  .rc-warning p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-2col-screens{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-why"><span class="rc-snum">1</span>Why Bundles?</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-what"><span class="rc-snum">2</span>What Are Bundles?</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-see-it"><span class="rc-snum">3</span>See It In Action</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-set-it-up"><span class="rc-snum">4</span>Set It Up</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-go-live"><span class="rc-snum">✓</span>Go Live</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎬</div>
      <div>
        <h2>See It In Action</h2>
        <p>Watch live demos of both bundle types — Fixed and Flexible — using a real Recurly Commerce test store, with key callouts to help you understand what you're seeing.</p>
      </div>
    </div>

    <!-- FIXED PRICE DEMO -->
    <div class="rc-card">
      <div class="rc-demo-label">🔒 Fixed Price Bundle Demo</div>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/1mTlp5Tf1c7ofZ-k6dpDaTlMZQJKo592WQTKKkktDH2A/preview" loading="lazy" title="Fixed Price Bundle Demo" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0 0 20px;">Merrell demos a Fixed Price Bundle using Taste Ceremony's "Puppy Party Box."</p>

      <h3 class="rc-subhead">👀 What to Notice in This Demo</h3>
      <div class="rc-callouts">
        <div class="rc-callout"><span class="rc-callout-icon">🗂️</span><div class="rc-callout-text"><strong>Collections in the left sidebar:</strong> Categories like "Pet Snacks" and "Pet Toys" — these are Shopify collections you curate and control. Subscribers browse and pick from these.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">💰</span><div class="rc-callout-text"><strong>Fixed price on the right ($35, discounted from $42):</strong> The merchant has defined this price. Notice it does <em>not</em> change as products are added — that's the defining feature of a Fixed Price Bundle.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">📦</span><div class="rc-callout-text"><strong>Two size variants:</strong> The "Puppy Party Box" (3 products) and a 5-product option. Each variant has a defined item count — subscribers fill their box to that count.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">🔢</span><div class="rc-callout-text"><strong>Quantity limits per item:</strong> When a subscriber tries to add more than 2 of the same item, they see a "quantity limit reached" message. You configure this per product to manage inventory and variety.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">✅</span><div class="rc-callout-text"><strong>Dynamic cart summary:</strong> On the right side, the selected items and quantities update in real time as the subscriber builds their box — clear, intuitive UX.</div></div>
      </div>
    </div>

    <div class="rc-divider"></div>

    <!-- FLEXIBLE PRICE DEMO -->
    <div class="rc-card">
      <div class="rc-demo-label">🔓 Flexible Price Bundle Demo</div>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/10XOS_Pop2O9Kk12d3h00JLbMdXQapksH1C-BBkbzFxc/preview" loading="lazy" title="Flexible Price Bundle Demo" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0 0 20px;">Merrell demos a Flexible Price Bundle using the "Barkwell Essentials" box.</p>

      <h3 class="rc-subhead">👀 What to Notice in This Demo</h3>
      <div class="rc-callouts">
        <div class="rc-callout"><span class="rc-callout-icon">💰</span><div class="rc-callout-text"><strong>Price starts at $0 in the top right:</strong> This is the most important visual cue. The Shopify parent product is set to $0 — the price will be calculated based on what the subscriber picks.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">📈</span><div class="rc-callout-text"><strong>Price updates as products are added:</strong> Watch the price change dynamically with each item added. This is real-time pricing based on individual product prices from your Shopify catalog.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">🔢</span><div class="rc-callout-text"><strong>Quantity limits still apply:</strong> Even in Flexible pricing, you can set per-item quantity limits. The same guardrails from Fixed Price Bundles are available here.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">🏷️</span><div class="rc-callout-text"><strong>Discounts still work:</strong> You can still offer a subscription discount on top of the flexible price — e.g. 10% off for subscribe & save — applied to the dynamic total.</div></div>
        <div class="rc-callout"><span class="rc-callout-icon">🛒</span><div class="rc-callout-text"><strong>Cart shows the dynamically generated total:</strong> In the cart, the subscriber sees "Barkwell Essentials" with a price that reflects exactly what they picked — transparent, value-based pricing.</div></div>
      </div>
    </div>

    <!-- Screenshots -->
    <h3 class="rc-subhead">📸 Screenshots from the Admin</h3>
    <div class="rc-2col-screens">
      <div>
        <img src="https://files.readme.io/45242452438455d627e0e1ca480305d35df8ea4f3f47140d41777e771a9ec573-Create_Bundle_-_name.png" alt="Create Bundle — name and description" class="rc-screenshot">
        <p class="rc-screenshot-cap">Step 1 in Recurly Commerce: give your bundle an internal name and description</p>
      </div>
      <div>
        <img src="https://files.readme.io/b149528a97229bdd3ff87341f6084cfbe674a1ff7ea6b194b2221f34c082927f-Bundle_Type-_flexible.png" alt="Bundle Type selection" class="rc-screenshot">
        <p class="rc-screenshot-cap">Choose Fixed or Flexible, link your Shopify parent product, and set size constraints</p>
      </div>
      <div>
        <img src="https://files.readme.io/be243a969395b71b9e41b185876a66d8bd5923e8c0813e8440e40af8f00a2ffc-Select_bundle_product.png" alt="Select Bundle Product" class="rc-screenshot">
        <p class="rc-screenshot-cap">Select your Shopify parent product — each product can only belong to one bundle</p>
      </div>
      <div>
        <img src="https://files.readme.io/d2387a62bfe6a50b66f6415ce0f5c363ef4a0f6a0b3b1eff67ec0765753dd48b-Select_collections.png" alt="Select Collections" class="rc-screenshot">
        <p class="rc-screenshot-cap">Select the Shopify collection(s) that populate the bundle builder for subscribers</p>
      </div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Both Types Share the Same Core Experience</h4><p>From the subscriber's perspective, Fixed and Flexible bundles look and feel nearly identical — they browse collections, pick items, and see a live cart summary. The difference is entirely in how the <em>price</em> behaves. This makes it easy to run both types simultaneously as different offers.</p></div>
    </div>

    <div class="rc-warning">
      <span class="rc-wicon">⚠️</span>
      <p><strong>Nested variants are not supported.</strong> You can use one level of variants on your bundle product (e.g. Small, Medium, Large) but not multiple option types simultaneously (e.g. both Size and Color). Plan your Shopify product structure before creating the product.</p>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-what">← What Are Bundles?</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-set-it-up">Next: Set It Up →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer">📖 Bundles Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="https://help.shopify.com/en/manual/products/collections" target="_blank" rel="noopener noreferrer">🛍️ Shopify Collections Guide</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
