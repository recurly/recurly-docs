---
title: How to go live
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
  .rc-complete{background:var(--offblack);border-radius:16px;padding:40px;text-align:center;margin-bottom:28px}
  .rc-complete h2{font-size:1.8rem;font-weight:800;margin:12px 0 10px;color:var(--yellow)}
  .rc-complete p{color:var(--lightgray);font-size:.95rem;margin:0;line-height:1.6;max-width:560px;margin:0 auto}
  .rc-card{background:var(--offwhite);border-radius:16px;padding:28px;border:1px solid var(--lightgray);margin-bottom:24px}
  .rc-subhead{font-size:1rem;font-weight:700;margin:0 0 16px;color:var(--offblack)}
  .rc-video-wrap{position:relative;overflow:hidden;aspect-ratio:16/9;border-radius:14px;margin-bottom:14px}
  .rc-video-wrap iframe{position:absolute;width:100%;height:100%;top:0;left:0;border:none}
  .rc-faq{border-radius:14px;border:1px solid var(--lightgray);overflow:hidden;margin-bottom:12px}
  .rc-faq-q{background:var(--offwhite);padding:15px 20px;font-weight:700;font-size:.9rem;color:var(--offblack);display:flex;align-items:flex-start;gap:12px}
  .rc-faq-q span{font-size:18px;flex-shrink:0;margin-top:1px}
  .rc-faq-a{background:#fff;padding:13px 20px 15px 50px;font-size:.87rem;color:var(--darkgray);line-height:1.6;border-top:1px solid var(--brightgray)}
  .rc-2col{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:24px}
  .rc-next-card{border-radius:14px;border:1px solid var(--lightgray);overflow:hidden}
  .rc-next-header{background:var(--offblack);padding:14px 18px;display:flex;align-items:center;gap:10px}
  .rc-next-header h4{color:var(--yellow);font-size:.88rem;font-weight:700;margin:0}
  .rc-next-header span{font-size:18px}
  .rc-next-body{padding:14px 18px;background:var(--offwhite)}
  .rc-next-body p{font-size:.84rem;color:var(--darkgray);line-height:1.55;margin:0 0 10px}
  .rc-next-body p:last-child{margin:0}
  .rc-tip{background:var(--offwhite);border:2px solid var(--yellow);border-radius:14px;padding:20px 24px;display:flex;gap:16px;align-items:flex-start;margin-bottom:24px}
  .rc-tipicon{font-size:24px;flex-shrink:0}
  .rc-tip h4{font-size:.82rem;font-weight:700;color:var(--offblack);text-transform:uppercase;letter-spacing:.5px;margin:0 0 4px}
  .rc-tip p{font-size:.87rem;color:var(--darkgray);line-height:1.55;margin:0}
  .rc-sec-nav{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-top:24px;flex-wrap:wrap}
  .rc-btn-prev,.rc-btn-disabled,.rc-link-btn{display:inline-flex;align-items:center;justify-content:center;padding:11px 18px;border-radius:10px;font-weight:700;font-size:.88rem;text-decoration:none}
  .rc-btn-prev{background:#fff;color:var(--darkgray);border:1px solid var(--lightgray)}
  .rc-btn-disabled{background:var(--brightgray);color:var(--gray);cursor:default;border:1px solid var(--lightgray)}
  .rc-link-btn{gap:8px;background:var(--yellow);color:var(--offblack);margin:0 8px 8px 0}
  .rc-link-sec{background:var(--offwhite);color:var(--darkgray);border:1px solid var(--lightgray)}
  @media(max-width:640px){.rc-hero h1{font-size:1.7rem}.rc-hero{padding:36px 20px 32px}.rc-hero-stats{gap:20px}.rc-2col{grid-template-columns:1fr}.rc-nav,.rc-sec-nav,.rc-sec-header{flex-direction:column}.rc-sec-nav{align-items:stretch}}
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
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-set-it-up"><span class="rc-snum">4</span>Set It Up</a>
    <a class="is-active" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-go-live"><span class="rc-snum">✓</span>Go Live</a>
  </nav>

  <div class="rc-sec">
    <div class="rc-sec-header">
      <div class="rc-sec-icon">🎉</div>
      <div>
        <h2>Go Live — And What Comes Next</h2>
        <p>Your bundle is published. Here's what the subscriber experience looks like, what to expect after launch, and answers to the most common questions.</p>
      </div>
    </div>

    <div class="rc-complete">
      <div style="font-size:40px;">🚀</div>
      <h2>You're Ready to Go!</h2>
      <p>Once your bundle is live, subscribers can build their own box on your storefront, subscribe, and manage their selections from their customer portal — all without any intervention from your team.</p>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">📹 Wrapping Up — From Merrell</h3>
      <div class="rc-video-wrap">
        <iframe src="https://drive.google.com/file/d/1DBAmraU45gM5AhDQw_Qaflkv9KTxuf45Qv6QaHWJoYg/preview" loading="lazy" title="Bundles Outro" allowfullscreen allow="encrypted-media; fullscreen;"></iframe>
      </div>
      <p style="font-size:.85rem;color:var(--gray);margin:0;">Merrell wraps up the Bundles walkthrough — what happens once bundles are live on your storefront, and where to go for additional support.</p>
    </div>

    <h3 class="rc-subhead">🔄 The Ongoing Subscriber Experience</h3>

    <div class="rc-2col">
      <div class="rc-next-card">
        <div class="rc-next-header"><span>🔀</span><h4>Subscribers can swap before each renewal</h4></div>
        <div class="rc-next-body">
          <p>From their customer portal, subscribers can change any item in their bundle for another item from the approved collection — keeping the experience fresh without cancelling.</p>
          <p><strong>Fixed:</strong> Price stays constant regardless of what they pick. <strong>Flexible:</strong> Price updates to reflect the new selection.</p>
        </div>
      </div>
      <div class="rc-next-card">
        <div class="rc-next-header"><span>📦</span><h4>Inventory syncs automatically</h4></div>
        <div class="rc-next-body">
          <p>When a product in your collection goes out of stock in Shopify, it's automatically labeled "Out of Stock" in the bundle builder — no manual intervention needed.</p>
          <p>If a subscribed item becomes unavailable, Recurly Commerce can trigger an automated notification prompting the subscriber to select a replacement before their next renewal.</p>
        </div>
      </div>
      <div class="rc-next-card">
        <div class="rc-next-header"><span>⏸️</span><h4>Pause & skip work as normal</h4></div>
        <div class="rc-next-body">
          <p>If you've enabled Pause or Skip in your Customer Portal settings, subscribers can pause or skip their bundle subscription just like any other subscription plan.</p>
        </div>
      </div>
      <div class="rc-next-card">
        <div class="rc-next-header"><span>🎁</span><h4>Gifting is supported</h4></div>
        <div class="rc-next-body">
          <p>Bundles are fully compatible with Recurly Commerce gifting. To enable gift options for bundle subscriptions, contact <a href="mailto:support@recurly.com" style="color:var(--orange);">support@recurly.com</a> for setup assistance.</p>
        </div>
      </div>
    </div>

    <h3 class="rc-subhead">❓ Common Questions</h3>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>💰</span>Can I apply discounts to bundle subscriptions?</div>
      <div class="rc-faq-a">Yes. You can apply Subscribe & Save discounts on top of any bundle price — both Fixed and Flexible. For Flexible bundles, the discount applies to the dynamically calculated total. You can also configure special order-based discounts (e.g. 50% off the first 3 orders) within the subscription plan settings.</div>
    </div>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>🔄</span>Can subscribers add add-ons to their bundle?</div>
      <div class="rc-faq-a">Yes. You can configure one-time or recurring add-ons within the subscription plan settings. These are billed alongside the bundle. Note: add-ons must be configured in the plan — you cannot add non-bundle products directly to the same subscription plan as the bundle product.</div>
    </div>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>📦</span>What if a product in my collection goes out of stock?</div>
      <div class="rc-faq-a">For new subscribers: the item is automatically labeled "Out of Stock" in the bundle builder and cannot be selected — no action needed from you. For existing subscribers who already have that item in their bundle: Recurly Commerce can send an automated notification prompting them to swap it for something else before their next renewal.</div>
    </div>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>🛒</span>Can I sell bundles as a one-time purchase (not just a subscription)?</div>
      <div class="rc-faq-a">Yes. When setting up your subscription plan, you can configure it to support both One-time purchase and Subscribe & Save, so customers can choose how they want to buy.</div>
    </div>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>🔗</span>Can a Shopify product be in multiple bundles?</div>
      <div class="rc-faq-a">No. A Shopify product can only be linked to one bundle at a time. If a product is already assigned to another bundle, it will not appear in the selection list. Plan your catalog structure before creating bundles if you're building several offerings.</div>
    </div>

    <div class="rc-faq">
      <div class="rc-faq-q"><span>🧩</span>Can I use automated (smart) Shopify collections for my bundle?</div>
      <div class="rc-faq-a">Yes — but with a limitation. Automated collections only recognize standard Shopify product fields (Product Type, Tag, Price, etc.) as conditions. Custom metafields cannot be used. For the most predictable results, manual collections are recommended.</div>
    </div>

    <div class="rc-tip">
      <span class="rc-tipicon">💡</span>
      <div><h4>Pro Tip: Refresh Your Collections Seasonally</h4><p>One of the most effective ongoing strategies is rotating your bundle collection seasonally — adding new products, removing older ones, or creating themed collections (holiday, spring, summer). This gives subscribers a reason to re-engage with their bundle before each renewal and introduces them to new products they might not have discovered on their own.</p></div>
    </div>

    <div class="rc-card">
      <h3 class="rc-subhead">🆘 Need More Help?</h3>
      <p style="font-size:.9rem;color:var(--darkgray);line-height:1.6;margin:0 0 14px;">As Merrell noted at the end of the walkthrough: if you have additional questions after reviewing this learning path, you have a few great options:</p>
      <div style="display:flex;flex-direction:column;gap:10px;">
        <div style="display:flex;gap:12px;align-items:flex-start;font-size:.88rem;color:var(--darkgray);line-height:1.5;"><span style="font-size:18px;flex-shrink:0;">📖</span><div><strong>Recurly Documentation</strong> — the full technical reference for Bundles, including edge cases and advanced configuration: <a href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce</a></div></div>
        <div style="display:flex;gap:12px;align-items:flex-start;font-size:.88rem;color:var(--darkgray);line-height:1.5;"><span style="font-size:18px;flex-shrink:0;">🤖</span><div><strong>AI Support</strong> — available at <a href="https://recurly.com" target="_blank" rel="noopener noreferrer" style="color:var(--orange);">recurly.com</a> for quick answers while you're in the platform.</div></div>
        <div style="display:flex;gap:12px;align-items:flex-start;font-size:.88rem;color:var(--darkgray);line-height:1.5;"><span style="font-size:18px;flex-shrink:0;">📧</span><div><strong>Support team</strong> — email <a href="mailto:support@recurly.com" style="color:var(--orange);">support@recurly.com</a> for technical setup questions.</div></div>
        <div style="display:flex;gap:12px;align-items:flex-start;font-size:.88rem;color:var(--darkgray);line-height:1.5;"><span style="font-size:18px;flex-shrink:0;">🎧</span><div><strong>Your Customer Success Manager</strong> — reach out to your CSM at <a href="mailto:customersuccess@recurly.com" style="color:var(--orange);">customersuccess@recurly.com</a> for strategic guidance on how to make the most of Bundles for your business.</div></div>
      </div>
    </div>

    <div class="rc-sec-nav">
      <a class="rc-btn-prev" href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-bundles-set-it-up">← Set It Up</a>
      <span class="rc-btn-disabled">🎉 You're Ready to Go!</span>
    </div>

    <h3 class="rc-subhead" style="margin-top:28px;">📚 Additional Resources</h3>
    <a class="rc-link-btn" href="https://docs.recurly.com/recurly-commerce/docs/bundles-in-recurly-commerce" target="_blank" rel="noopener noreferrer">📖 Bundles Documentation</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-commerce/docs/customer-portal-management" target="_blank" rel="noopener noreferrer">👤 Customer Portal Management</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-commerce/docs/cancellation-and-churn-prevention-flows" target="_blank" rel="noopener noreferrer">🔄 Cancellation & Churn Prevention</a>
    <a class="rc-link-btn rc-link-sec" href="https://docs.recurly.com/recurly-commerce/docs/recurly-navigate-bundles-why">🔁 Start Over</a>
  </div>

</div>
</body>
</html>
`}</HTMLBlock>

<br />
