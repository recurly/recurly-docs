---
title: Set Bundles up
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
  .rc-phase-block{margin-bottom:32px}
  .rc-phase-label{display:flex;align-items:center;gap:12px;margin-bottom:18px}
  .rc-phase-num{width:40px;height:40px;border-radius:12px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:16px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-phase-text h3{font-size:1rem;font-weight:800;color:var(--offblack);margin:0 0 2px}
  .rc-phase-text p{font-size:.82rem;color:var(--gray);margin:0}
  .rc-steps{display:flex;flex-direction:column;gap:12px;margin-bottom:0}
  .rc-step{background:#fff;border-radius:12px;padding:16px 20px;border:1px solid var(--brightgray);display:flex;gap:16px;align-items:flex-start}
  .rc-sbadge{width:32px;height:32px;border-radius:8px;background:var(--offblack);color:var(--yellow);font-weight:800;font-size:13px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .rc-step h4{font-size:.9rem;font-weight:700;margin:0 0 4px;color:var(--offblack)}
  .rc-step p{font-size:.84rem;color:var(--gray);line-height:1.55;margin:0}
  .rc-step code{background:var(--brightgray);padding:1px 6px;border-radius:4px;font-family:monospace;font-size:.82rem;color:var(--darkgray)}
  .rc-important{background:#FFF8E6;border:1px solid var(--orange);border-radius:12px;padding:14px 18px;display:flex;gap:12px;margin-bottom:12px}
  .rc-important-icon{font-size:18px;flex-shrink:0}
  .rc-important p{font-size:.85rem;color:var(--darkgray);line-height:1.5;margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-checklist{background:var(--offwhite);border-radius:16px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:28px}
  .rc-cl-header{padding:14px 22px;display:flex;align-items:center;gap:10px;background:var(--offblack)}
  .rc-cl-header h3{font-size:.85rem;font-weight:700;text-transform:uppercase;letter-spacing:.5px;color:var(--yellow);margin:0}
  .rc-cli{padding:13px 22px;border-bottom:1px solid var(--brightgray);display:flex;gap:14px;align-items:flex-start;background:#fff}
  .rc-cli:nth-child(even){background:var(--offwhite)}
  .rc-cli:last-child{border-bottom:none}
  .rc-cb{font-size:16px;flex-shrink:0;margin-top:1px}
  .rc-clab{font-size:.87rem;color:var(--darkgray);line-height:1.4}
  .rc-clab span{display:block;font-size:.78rem;color:var(--gray);margin-top:2px}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-next,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-next{background:var(--yellow);color:var(--offblack);border:1px solid var(--yellow)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-see-it"><span class="rc-snum">3</span>See It In Action</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-set-it-up"><span class="rc-snum">4</span>Set It Up</a>
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-go-live"><span class="rc-snum">✓</span>Go Live</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">⚙️</div>
      <div>
        <h2>Set It Up</h2>
        <p>Everything you need to configure Commerce Bundles — from Shopify setup through your first published subscription plan. Watch Merrell walk through it, then follow the step-by-step guide.</p>
      </div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Bundles Admin Walkthrough — With Merrell</h3>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/117LzmD0rP5ZYTAiCvcIqnBfjDGa79DuAiPcT_j5WE_U/preview" loading="lazy" title="Bundles Admin Setup" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0;">Merrell walks through the Bundles admin in Recurly Commerce — creating both a Fixed and Flexible bundle from scratch, linking products and collections, and assigning to a subscription plan.</p>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">📋</span>
      <div><h4>Before You Begin: Two Key Reminders</h4><p>Setup spans Shopify and Recurly Commerce. You'll work across both tools. And as Merrell highlights: <strong>every bundle must be assigned to a subscription plan</strong> — a bundle without a plan cannot be subscribed to by customers.</p></div>
    </div>

    <!-- PHASE 1 -->
    <div class="rc-phase-block">
      <div class="rc-phase-label">
        <div class="rc-phase-num">1</div>
        <div class="rc-phase-text"><h3>Shopify Storefront — Add the Bundle Builder</h3><p>One-time setup · ~15 minutes · No coding required</p></div>
      </div>
      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">a</div><div><h4>Open your Shopify Theme Editor</h4><p>Go to <code>Online Store → Themes → Edit theme</code>.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">b</div><div><h4>Create a new Product template</h4><p>Select <code>Home page → Products → + Create template</code>. Base it on <strong>Default product</strong> and save.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">c</div><div><h4>Add the Commerce Bundle App section</h4><p>In the Template area, click <strong>Add section → Apps → Commerce Bundle Builder</strong>.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">d</div><div><h4>Set Width and Height to Full</h4><p>Select the Commerce Bundle App section and set <strong>Width: Full</strong> and <strong>Height: Full screen</strong> for the best display.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">e</div><div><h4>Disable "Reveal sections on scroll"</h4><p>In Theme Settings, turn off <strong>Reveal sections on scroll</strong> for a smoother subscriber experience. Save.</p></div></div>
      </div>
    </div>

    <!-- PHASE 2 -->
    <div class="rc-phase-block">
      <div class="rc-phase-label">
        <div class="rc-phase-num">2</div>
        <div class="rc-phase-text"><h3>Shopify — Create Your Bundle Product & Collection</h3><p>Done once per bundle offering</p></div>
      </div>
      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">a</div><div><h4>Create the Parent Bundle Product</h4><p>Add a new product in Shopify. For <strong>Fixed</strong>: set the price to your desired bundle total. For <strong>Flexible</strong>: set the price to <strong>$0</strong>. Add variants (e.g. Small, Medium, Large) if needed — one level only, no nested variants.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">b</div><div><h4>Assign it to your Bundle Builder template</h4><p>On the product page in Shopify, scroll to Theme templates and assign it to the bundle template you created in Phase 1. This makes the Bundle Builder UI appear on that product's page.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">c</div><div><h4>Create your Bundle Collection</h4><p>Create a Shopify collection and add all the products subscribers can choose from. <strong>Manual collections are recommended</strong> for full, predictable control. Automated collections work but cannot use custom metafields as conditions.</p></div></div>
      </div>
      <div class="rc-important" style="margin-top:14px;">
        <span class="rc-important-icon">⚠️</span>
        <p>A product can only belong to <strong>one bundle at a time</strong>. If a product is already linked to another bundle, it won't appear in the selection list when creating a new one.</p>
      </div>
    </div>

    <!-- PHASE 3 -->
    <div class="rc-phase-block">
      <div class="rc-phase-label">
        <div class="rc-phase-num">3</div>
        <div class="rc-phase-text"><h3>Recurly Commerce — Create the Bundle</h3><p>Navigate to Bundles in the Recurly Commerce app</p></div>
      </div>
      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">a</div><div><h4>Go to Bundles → + Create Bundle</h4><p>In the Recurly Commerce admin, navigate to the <strong>Bundles</strong> tab and click <strong>+ Create Bundle</strong>.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">b</div><div><h4>Enter a name and description</h4><p>These are for internal tracking only — customers never see them. In the demo, you saw names like "Puppy Party Box" and "Barkwell Essentials" used here.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">c</div><div><h4>Select your bundle type</h4><p>Choose <strong>Fixed Price</strong> or <strong>Flexible Price</strong>. This determines the pricing logic — see Tab 2 if you're still deciding.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">d</div><div><h4>Link your Shopify Parent Product</h4><p>Click <strong>+ Select Product</strong> and choose the parent product you created. If you're building a Fixed bundle with variants, you'll also define the item count per variant here (e.g. 3-product box, 5-product box).</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">e</div><div><h4>For Flexible bundles: set min/max size</h4><p>Enter the <strong>minimum number of products</strong> required and an optional <strong>maximum</strong>. If no maximum is set, it defaults to unlimited.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">f</div><div><h4>Select bundle contents (collections)</h4><p>Choose the Shopify collection you created. This populates the bundle builder with selectable products. You can select multiple collections if needed.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">g</div><div><h4>(Optional) Set single product limits</h4><p>Set a per-item quantity limit to prevent subscribers from filling the entire box with the same product. In the demo, this was set to max 2 of any one item.</p></div></div>
      </div>
    </div>

    <!-- PHASE 4 -->
    <div class="rc-phase-block">
      <div class="rc-phase-label">
        <div class="rc-phase-num">4</div>
        <div class="rc-phase-text"><h3>Recurly Commerce — Create the Subscription Plan</h3><p>Required — bundles must be assigned to a plan to be subscribable</p></div>
      </div>
      <div class="rc-steps">
        <div class="rc-step"><div class="rc-sbadge">a</div><div><h4>Go to Subscription Plans → + Create Offer</h4><p>Enter an internal name and description for the offer group.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">b</div><div><h4>Add your bundle's Parent Product</h4><p>Click <strong>Add Product</strong> and select your bundle parent product. Bundle products must stand alone — you cannot add non-bundle products to the same plan.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">c</div><div><h4>Configure purchase options</h4><p>Bundles support <strong>One-time purchase</strong> and <strong>Subscribe & Save</strong>. Set your delivery frequency options and any subscription discounts.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">d</div><div><h4>Configure add-ons, discounts, shipping & cancellation flow</h4><p>Set up product swaps, one-time or recurring add-ons, free shipping rules, contract terms, and a cancellation flow with retention offers if desired.</p></div></div>
        <div class="rc-step"><div class="rc-sbadge">e</div><div><h4>Click Publish Offer</h4><p>Your bundle subscription is now live. Subscribers can find it on your storefront and start building their box.</p></div></div>
      </div>
    </div>

    <div class="rc-checklist">
      <div class="rc-cl-header"><h3>✅ Setup Checklist</h3></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Bundle Builder template created in Shopify theme<span>Online Store → Themes → Edit theme → Create template → Commerce Bundle Builder section added</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Parent Bundle Product created in Shopify with correct pricing<span>$0 for Flexible · desired price for Fixed · one level of variants only</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Parent Product assigned to Bundle Builder template in Shopify<span>Product page → Theme templates → select your bundle template</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Bundle Collection created in Shopify<span>Manual collections recommended · add all products subscribers can choose from</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Bundle created in Recurly Commerce with type, product, and collection configured<span>Recurly Commerce → Bundles → + Create Bundle</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Subscription plan created and bundle product attached<span>Subscription Plans → + Create Offer · bundle product added</span></div></div>
      <div class="rc-cli"><span class="rc-cb">☐</span><div class="rc-clab">Offer published<span>Click Publish Offer — bundle is now live for subscribers</span></div></div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-see-it">← See It In Action</a>
      <a class="rc-btn-next" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-go-live">Next: Go Live →</a>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer">📖 Bundles Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-commerce/docs/create-a-subscription-plan" target="_blank" rel="noopener noreferrer">📋 Create a Subscription Plan</a>
    <a class="rc-link-btn rc-link-sec" href="https://help.shopify.com/en/manual/products/add-update-products" target="_blank" rel="noopener noreferrer">🛍️ Shopify: Add a Product</a>
    <a class="rc-link-btn rc-link-sec" href="mailto:customersuccess@recurly.com">🎧 Contact Customer Success</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
