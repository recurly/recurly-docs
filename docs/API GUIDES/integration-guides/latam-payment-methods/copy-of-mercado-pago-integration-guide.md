---
title: Copy of Mercado Pago integration guide
excerpt: Create subscriptions via Purchase API using Mercado Pago with Ebanx.
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
  :root {
    --yellow:     #FFD706;
    --tangerine:  #FF8200;
    --offblack:   #0D0D0B;
    --darkgray:   #32312D;
    --gray:       #807D73;
    --lightgray:  #CCC9B8;
    --offwhite:   #FFFDF2;
    --font:       'Plus Jakarta Sans', 'Segoe UI', system-ui, sans-serif;
  }
  .rp-page { font-family: var(--font); color: var(--offblack); font-size: 15px; line-height: 1.6; max-width: 860px; }

  /* Container */
  .rp-code {
    background: var(--offblack);
    color: var(--offwhite);
    border: 1px solid var(--darkgray);
    border-radius: 10px;
    margin: 16px 0 24px;
    overflow: hidden;
    font-family: 'Menlo', 'Monaco', 'Consolas', 'Courier New', monospace;
    font-size: 13px;
    line-height: 1.55;
  }

  /* Header bar — sits on top of the code body */
  .rp-code-header {
    display: flex; align-items: center; justify-content: space-between;
    gap: 12px; flex-wrap: wrap;
    background: var(--darkgray);
    padding: 8px 14px;
    border-bottom: 1px solid var(--offblack);
    font-family: var(--font);
  }

  /* Language label (used on single snippets) */
  .rp-code-lang {
    color: var(--lightgray);
    font-size: 12px; font-weight: 700;
    text-transform: lowercase; letter-spacing: 0.4px;
  }

  /* Tab list (used on multi-language snippets, replaces the lang label) */
  .rp-code-tablist { display: flex; gap: 4px; flex-wrap: wrap; }
  .rp-code-tab {
    background: transparent; border: 0;
    color: var(--lightgray);
    font-family: inherit; font-size: 12px; font-weight: 700;
    padding: 5px 12px; border-radius: 14px;
    cursor: pointer;
    transition: background 0.12s, color 0.12s;
  }
  .rp-code-tab:hover { background: rgba(255,253,242,0.08); color: var(--offwhite); }
  .rp-code-tab-active,
  .rp-code-tab-active:hover { background: var(--yellow); color: var(--offblack); }

  /* Copy button — ghost style, turns tangerine on hover */
  .rp-code-copy {
    background: transparent;
    border: 1px solid var(--gray);
    color: var(--lightgray);
    font-family: inherit; font-size: 12px; font-weight: 700;
    padding: 4px 12px; border-radius: 6px;
    cursor: pointer; flex-shrink: 0;
    transition: background 0.12s, border-color 0.12s, color 0.12s;
  }
  .rp-code-copy:hover {
    background: var(--tangerine); border-color: var(--tangerine);
    color: var(--offblack);
  }

  /* Code body — dark background, monospace, scrollable on overflow */
  .rp-code-body {
    margin: 0;
    padding: 16px 18px;
    overflow-x: auto;
    font-family: inherit; font-size: inherit; line-height: inherit;
    color: var(--offwhite); background: var(--offblack);
    white-space: pre;
  }
  .rp-code-body code {
    font-family: inherit; font-size: inherit;
    background: transparent; color: inherit; padding: 0;
  }

  /* Show one body for single snippets, only the active body for tabbed snippets */
  .rp-code:not(.rp-code-tabs) .rp-code-body { display: block; }
  .rp-code-tabs .rp-code-body { display: none; }
  .rp-code-tabs .rp-code-body.rp-code-body-active { display: block; }
</style>
<script>
/*
 * NOTE: scripts don't execute inside ReadMe HTMLBlocks. These helpers are
 * included as a reference for the intended interaction behavior — devs
 * should wire equivalent handlers into ReadMe's theme.
 *
 *   rpTab(btn, idx)  — switch the active tab + body inside a tabbed snippet
 *   rpCopy(btn)      — copy the visible code body to the clipboard,
 *                      with a fallback for older browsers
 */
function rpTab(btn, idx) {
  var wrap = btn.closest('.rp-code-tabs');
  if (!wrap) return;
  var tabs = wrap.querySelectorAll('.rp-code-tab');
  var bodies = wrap.querySelectorAll('.rp-code-body');
  for (var i = 0; i < tabs.length; i++) tabs[i].classList.toggle('rp-code-tab-active', i === idx);
  for (var i = 0; i < bodies.length; i++) bodies[i].classList.toggle('rp-code-body-active', i === idx);
}
function rpCopy(btn) {
  var wrap = btn.closest('.rp-code');
  if (!wrap) return;
  var body = wrap.classList.contains('rp-code-tabs')
    ? wrap.querySelector('.rp-code-body.rp-code-body-active')
    : wrap.querySelector('.rp-code-body');
  if (!body) return;
  var text = body.textContent.replace(/\\s+$/, '');
  if (navigator.clipboard && navigator.clipboard.writeText) {
    navigator.clipboard.writeText(text).then(function () { rpFlashCopied(btn); }).catch(function () {});
  } else {
    var ta = document.createElement('textarea');
    ta.value = text;
    ta.setAttribute('readonly', '');
    ta.style.position = 'absolute'; ta.style.left = '-9999px';
    document.body.appendChild(ta);
    ta.select();
    try { document.execCommand('copy'); rpFlashCopied(btn); } catch (e) {}
    document.body.removeChild(ta);
  }
}
function rpFlashCopied(btn) {
  if (!btn.dataset.label) btn.dataset.label = btn.textContent;
  btn.textContent = 'Copied';
  setTimeout(function () { btn.textContent = btn.dataset.label; }, 1500);
}
</script>
<div class="rp-page">

  <h3>Single snippet — language label on the left</h3>

  <div class="rp-code">
    <div class="rp-code-header">
      <span class="rp-code-lang">json</span>
      <button class="rp-code-copy" type="button" onclick="rpCopy(this)">Copy</button>
    </div>
    <pre class="rp-code-body"><code>{
  "subscription": {
    "plan_code": "monthly-coffee",
    "currency": "USD",
    "account": {
      "code": "user_42",
      "email": "user@example.com"
    }
  }
}</code></pre>
  </div>

  <h3>Tabbed snippet — multiple languages, active tab in yellow</h3>

  <div class="rp-code rp-code-tabs">
    <div class="rp-code-header">
      <div class="rp-code-tablist">
        <button type="button" class="rp-code-tab rp-code-tab-active" onclick="rpTab(this,0)">cURL</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,1)">Ruby</button>
        <button type="button" class="rp-code-tab" onclick="rpTab(this,2)">JavaScript</button>
      </div>
      <button class="rp-code-copy" type="button" onclick="rpCopy(this)">Copy</button>
    </div>
    <pre class="rp-code-body rp-code-body-active"><code>curl https://v3.recurly.com/subscriptions \\
  -u "API_KEY:" \\
  -H "Accept: application/vnd.recurly.v2021-02-25" \\
  -H "Content-Type: application/json" \\
  -d '{ "plan_code": "monthly-coffee", "currency": "USD" }'</code></pre>
    <pre class="rp-code-body"><code>subscription = @client.create_subscription(body: {
  plan_code: "monthly-coffee",
  currency:  "USD",
  account:   { code: "user_42", email: "user@example.com" }
})</code></pre>
    <pre class="rp-code-body"><code>const subscription = await client.createSubscription({
  plan_code: "monthly-coffee",
  currency:  "USD",
  account:   { code: "user_42", email: "user@example.com" }
});</code></pre>
  </div>

</div>
`}</HTMLBlock>