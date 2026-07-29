---
title: Jajajaja
deprecated: false
hidden: false
metadata:
  robots: index
---
{/* Recurly docs — component compendium (brand v2 revamp). Paste this into the ReadMe editor body. Title and meta description go in ReadMe's own fields (see the accompanying chat message). This is a living visual-QA reference: it renders every theme-styled component so you can eyeball the revamp. */}

<div class="rp-page">
  <div class="rp-overview">This page renders every component the docs theme styles, so you can see the brand v2 revamp in one place. Nothing here is a real feature — it's a visual QA reference. Paste it into a hidden or staging page with the revamped theme applied, and every accent, callout, table, and code block below shows exactly how the new palette lands.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#overview-and-header-cluster"><span class="rp-toc-num">1</span>Header cluster</a>
    <a class="rp-toc-pill" href="#callouts"><span class="rp-toc-num">2</span>Callouts</a>
    <a class="rp-toc-pill" href="#definitions-and-content-cards"><span class="rp-toc-num">3</span>Definitions and cards</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">4</span>Key benefits</a>
    <a class="rp-toc-pill" href="#numbered-steps"><span class="rp-toc-num">5</span>Steps</a>
    <a class="rp-toc-pill" href="#buttons"><span class="rp-toc-num">6</span>Buttons</a>
    <a class="rp-toc-pill" href="#tables"><span class="rp-toc-num">7</span>Tables</a>
    <a class="rp-toc-pill" href="#lists"><span class="rp-toc-num">8</span>Lists</a>
    <a class="rp-toc-pill" href="#card-grids"><span class="rp-toc-num">9</span>Card grids</a>
    <a class="rp-toc-pill" href="#code-blocks"><span class="rp-toc-num">10</span>Code</a>
    <a class="rp-toc-pill" href="#accordions"><span class="rp-toc-num">11</span>Accordions</a>
    <a class="rp-toc-pill" href="#tabs"><span class="rp-toc-num">12</span>Tabs</a>
    <a class="rp-toc-pill" href="#images"><span class="rp-toc-num">13</span>Images</a>
    <a class="rp-toc-pill" href="#video-embed"><span class="rp-toc-num">14</span>Video</a>
    <a class="rp-toc-pill" href="#api-reference-badges"><span class="rp-toc-num">15</span>API badges</a>
    <a class="rp-toc-pill" href="#prose-and-typography"><span class="rp-toc-num">16</span>Prose</a>
    <a class="rp-toc-pill" href="#deprecated-legacy-components"><span class="rp-toc-num">17</span>Deprecated</a>
  </div>
</div>

# Overview and header cluster

The header cluster above shows the three fixtures every page opens with: the yellow-barred `rp-overview`, the offblack `rp-plan` pill, and the `rp-toc` pill bar. Below are the plan-pill variants and the additional-cost banner.

<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Not included in Starter or Pro — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to upgrade</div>

<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available as an optional add-on — contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your CSM for more information</div>

<div class="rp-cost"><strong>Additional cost</strong><br/>This feature requires an additional cost. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your Recurly account manager for pricing details. The left bar and links here now read Blue instead of the old tangerine.</div>

# Callouts

The four callouts carry the biggest visible shift in the revamp. Note is Blue, Tip moved to Green, Warning is Yellow, and Important is Poppy — each with its brand semantic tint behind it.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Use a note for neutral, contextual information the reader should keep in mind.</div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Tips now render green — positive, recommended, good-to-know guidance that helps the reader move faster.</div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>Warnings are yellow — a caution the reader should read before acting, but not a hard error.</div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Important uses Poppy — reserved for blockers, destructive actions, and things that break if ignored.</div>
</div>

# Definitions and content cards

The `rp-definition` block anchors a page's opening concept. The `rp-card` groups related prose, lists, or inline code into a bordered surface.

<div class="rp-definition">A definition block explains what a feature is and why it exists in two or three plain sentences. It sits on the OB Tint 2 surface and reads as the calm, authoritative opener before the page gets into specifics.</div>

<div class="rp-card"><p>A content card groups related prose into a bordered, offwhite surface. Inline <code>code</code> and <a href="https://docs.recurly.com" target="_blank">prose links</a> render here exactly as they do in body copy — links now read Blue.</p></div>

<div class="rp-card"><h3>Card with a heading</h3><p>A card can lead with a heading when the grouped content needs a label. Use it for tips, rules, and small reference blocks that don't warrant a full section.</p></div>

# Key benefits

Benefit grids are the offblack cards with a yellow icon. Three or five benefits use `rp-benefits` (auto-fit); exactly four use `rp-benefits rp-benefits-2x2`.

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Faster to launch</strong>
    <span>Ship a working billing integration in days, not quarters, with prebuilt flows.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-globe" aria-hidden="true"></i></div>
    <strong>Global by default</strong>
    <span>Accept payments in local currencies and methods across every major region.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Revenue you can see</strong>
    <span>Recognize, report, and forecast subscription revenue from a single source.</span>
  </div>
</div>

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Reduce churn</strong>
    <span>Recover failed payments automatically with intelligent retry logic.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Stay compliant</strong>
    <span>PCI-compliant vaulting and 3DS2 support are built in, not bolted on.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge-high" aria-hidden="true"></i></div>
    <strong>Scale cleanly</strong>
    <span>Handle millions of subscribers without re-architecting your billing.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Developer-first</strong>
    <span>A modern API, real SDKs, and webhooks for every lifecycle event.</span>
  </div>
</div>

# Numbered steps

Steps use the `rp-step` card with a yellow-circle number. The lightweight pattern stacks several cards in one `rp-steps` wrapper. Sub-steps render as a plain ordered list.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Navigate to Plans</h4><p>Go to Configuration → Plans in the Recurly dashboard.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create a plan</h4><p>Select New Plan, then set the plan code, name, and pricing.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Review the details and select Save Changes to publish the plan.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Set up the integration</h4><p>Configure the integration using the sub-steps below.</p></div>
  </div>
</div>

<ol>
  <li>Add your private API key to your environment.</li>
  <li>Install the Recurly client library for your language.</li>
  <li>Send a test request against the sandbox.</li>
</ol>

# Buttons

Each button is a single class. Primary and secondary append an arrow. Ghost is transparent with a border that fills yellow on hover.

<a class="rp-btn-primary" href="https://docs.recurly.com" target="_blank">Read the guide →</a>

<a class="rp-btn-secondary" href="https://docs.recurly.com" target="_blank">Start building →</a>

<a class="rp-btn-ghost" href="https://docs.recurly.com" target="_blank">Learn more</a>

<a class="rp-btn-download" href="https://docs.recurly.com" target="_blank"><i class="fa-solid fa-arrow-down-to-line" aria-hidden="true"></i> Download the schema</a>

# Tables

All three `rp-*` tables use a first `rp-thead-row` instead of `<thead>`/`<th>`. Native markdown tables get a dark header via the theme's `:has(thead)` rule.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Feature</td><td>Details</td></tr>
  <tr><td>Supported operations</td><td>Authorize, capture, refund, and void</td></tr>
  <tr><td>Supported card brands</td><td>Visa, Mastercard, Discover, and American Express</td></tr>
  <tr><td>Card on file supported</td><td>Yes</td></tr>
  <tr><td>Currencies</td><td><a href="https://docs.recurly.com/docs/currency-support-by-gateway" target="_blank">All available.</a></td></tr>
</table>

<table class="rp-pm-table">
  <tr class="rp-thead-row"><td>Payment method</td><td>Regions</td><td>Recurring</td></tr>
  <tr><td>Cards</td><td>Global</td><td>Yes</td></tr>
  <tr><td>ACH</td><td>United States</td><td>Yes</td></tr>
  <tr><td>SEPA</td><td>EMEA</td><td>Yes</td></tr>
</table>

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td>plan_code</td><td>The unique code that identifies the plan to subscribe the account to.</td></tr>
  <tr><td>currency</td><td>The three-letter ISO 4217 currency code for the subscription.</td></tr>
  <tr><td>auto_renew</td><td>Whether the subscription renews automatically at the end of each term.</td></tr>
</table>

| Field    | Type    | Description                                            |
| :------- | :------ | :----------------------------------------------------- |
| `id`     | string  | Unique identifier for the subscription                 |
| `state`  | string  | Current lifecycle state — active, canceled, or expired |
| `amount` | integer | Amount charged per billing cycle, in cents             |

# Lists

The `rp-list` is a bordered, offwhite list container — used for Prerequisites and Limitations. Plain markdown lists render inline in body copy.

### Prerequisites

<ul class="rp-list">
  <li>An active Recurly site with a configured payment gateway</li>
  <li>A private API key with write access</li>
  <li>At least one published plan</li>
</ul>

Plain unordered list:

- First item in a standard bulleted list
- Second item, with a <a href="https://docs.recurly.com" target="_blank">prose link</a>
- Third item

Plain ordered list:

1. First numbered item
2. Second numbered item
3. Third numbered item

# Card grids

Two wrappers, two purposes. `rp-sdk-grid` is the compact offblack split-pill for title-only links (SDKs, integrations). `rp-nav-grid` is the yellow card with body text for hub navigation and reference tiles.

<div class="rp-sdk-grid">

<Cards>
  <Card title="Ruby" href="https://github.com/recurly/recurly-client-ruby" target="_blank"></Card>
  <Card title="Node.js" href="https://github.com/recurly/recurly-client-node" target="_blank"></Card>
  <Card title="Python" href="https://github.com/recurly/recurly-client-python" target="_blank"></Card>
  <Card title="Java" href="https://github.com/recurly/recurly-client-java" target="_blank"></Card>
  <Card title="C#" href="https://github.com/recurly/recurly-client-dotnet" target="_blank"></Card>
  <Card title="PHP" href="https://github.com/recurly/recurly-client-php" target="_blank"></Card>
</Cards>
</div>

<div class="rp-nav-grid">

<Cards>
  <Card title="Subscription lifecycle" href="https://docs.recurly.com" target="_blank">
    Follow a subscription from trial through renewal, pause, and cancellation.
  </Card>
  <Card title="Payment methods" href="https://docs.recurly.com" target="_blank">
    Set up cards, ACH, SEPA, and digital wallets across every region you sell in.
  </Card>
  <Card title="Webhooks" href="https://docs.recurly.com" target="_blank">
    Subscribe to lifecycle events and verify signatures for secure delivery.
  </Card>
</Cards>
</div>

# Code blocks

A single fenced block renders as one dark panel. Consecutive fences with no blank line between them form a CodeTabs switcher. Syntax highlighting now reads yellow keywords, Blue definitions, Green strings, and Poppy numbers on offblack.

```json
{
  "id": "abc123def456",
  "object": "subscription",
  "state": "active",
  "plan_code": "pro",
  "currency": "USD",
  "quantity": 1
}
```

```bash cURL
curl -X POST https://v3.recurly.com/subscriptions \
  -u YOUR_PRIVATE_API_KEY: \
  -H "Content-Type: application/json"
```
```ruby Ruby
client = Recurly::Client.new(api_key: ENV['RECURLY_PRIVATE_KEY'])
sub = client.create_subscription(body: { plan_code: 'pro', currency: 'USD', quantity: 1 })
```
```javascript Node.js
const client = new recurly.Client(process.env.RECURLY_PRIVATE_KEY)
const sub = await client.createSubscription({ planCode: 'pro', currency: 'USD', quantity: 1 })
```
```python Python
client = recurly.Client(os.environ['RECURLY_PRIVATE_KEY'])
sub = client.create_subscription({ 'plan_code': 'pro', 'currency': 'USD', 'quantity': 1 })
```

# Accordions

Native `<Accordion>` components collapse Q\&A content. The chevron rotates open, and the border and hover tint follow the theme.

<Accordion title="How long does it take to set up billing?">
  Most teams have a working integration in a few days. Prebuilt hosted flows handle the front end, so you can go live without building a payment form from scratch.
</Accordion>

<Accordion title="Can I test without charging real cards?">
  Yes. Every Recurly site includes a sandbox with test card numbers, so you can run the full subscription lifecycle before switching to production keys.
</Accordion>

# Tabs

Native `<Tabs>` handle parallel non-code variants — environments, platforms, or prose choices. The active tab carries a yellow underline. Never use tabs for multi-language code; use CodeTabs instead.

<Tabs>
  <Tab title="Sandbox">
    Point your client at the sandbox and use a test private API key. Nothing here touches real money, so it's the right place to build and verify.
  </Tab>

  <Tab title="Production">
    Swap in your production key and live gateway credentials. Run a single low-value transaction end to end before you flip traffic over.
  </Tab>
</Tabs>

# Images

Images use ReadMe's native `<Image>` component — never the deprecated `rp-zoom` pattern. Standard screenshots are `width="75%"` with a border; narrow UI (sidebars, dropdowns) uses `width="40%"`. Both center and support click-to-zoom natively.


<Image src="[TODO: Add screenshot URL]" align="center" width="75%" border={true} />



<Image src="[TODO: Add narrow UI screenshot URL]" align="center" width="40%" border={true} />


# Video embed

Wistia videos use the JSX inline-style wrapper at a fixed 56.25% (16:9) ratio. Swap in a real media ID to preview playback. Videos always sit at the very top of a real page, immediately after the overview.

<div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
  <iframe src="https://fast.wistia.net/embed/iframe/MEDIA_ID"
    title="Sample video"
    allow="autoplay; fullscreen"
    allowtransparency="true"
    frameBorder="0"
    scrolling="no"
    allowFullScreen
    style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
</div>

# API reference badges

These normally render automatically on ReadMe's API Reference pages from your OpenAPI spec — you don't author them by hand. They're shown here as inline HTML only so you can check the revamped colors: GET is Green, POST is Blue, PUT is Yellow, PATCH is Teal, DELETE is Poppy. HTTP status chits follow the same success/error logic.

<div style={{display: "flex", gap: "8px", flexWrap: "wrap", marginBottom: "16px"}}>
  <span class="rm-APIMethod APIMethod_get">GET</span>
  <span class="rm-APIMethod APIMethod_post">POST</span>
  <span class="rm-APIMethod APIMethod_put">PUT</span>
  <span class="rm-APIMethod APIMethod_patch">PATCH</span>
  <span class="rm-APIMethod APIMethod_delete">DELETE</span>
  <span class="rm-APIMethod APIMethod_head">HEAD</span>
</div>

<div style={{display: "flex", gap: "8px", flexWrap: "wrap"}}>
  <span class="HTTPStatus HTTPStatus_1">100</span>
  <span class="HTTPStatus HTTPStatus_2">200</span>
  <span class="HTTPStatus HTTPStatus_4">404</span>
  <span class="HTTPStatus HTTPStatus_5">500</span>
</div>

# Prose and typography

Body copy is Figtree. Markdown headings carry the brand styling — the top-level `#` gets the yellow underline, and lower levels step down in weight and color.

## This is an h2 subsection

Body prose sits at a comfortable measure with **bold text**, _italic text_, and inline `code` tokens. A <a href="https://docs.recurly.com" target="_blank">prose link</a> reads Blue and underlines on hover.

### This is an h3 sub-subsection

The h3 uses OB Tint 5 for a softer step below the h2.

#### This is an h4 label

The h4 is the lowest-level label — used sparingly for small groupings.

# Deprecated legacy components

These still exist in the theme for older pages, but new pages should not use them. The div-based headings below are replaced by markdown `#`/`##`/`###`, and the `rp-zoom` lightbox is replaced by the native `<Image>` component shown above. They're included here only so legacy pages can be QA'd against the revamp.

<div class="rp-h1">rp-h1 — legacy div heading (use markdown # instead)</div>

<div class="rp-h2">rp-h2 — legacy div heading (use markdown ## instead)</div>

<div class="rp-h3">rp-h3 — legacy div heading (use markdown ### instead)</div>

<div class="rp-h4">rp-h4 — legacy div heading (use markdown #### instead)</div>

<br />
