---
title: Christian's journey with Claude
excerpt: >-
  How add-ons work in Recurly, including pricing models, billing options, and
  how to configure them on plans or directly on subscriptions.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">

  <div class="rp-overview">
    This page documents the journey of building Recurly's branded ReadMe documentation system. It showcases every design component, MDX pattern, and workflow refinement that went into transforming raw documentation drafts into polished, on-brand pages. Read through to see the full system in action — every heading, button, callout, table, and interactive element is a working example you can adapt to your own pages.
  </div>

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#the-design-system"><span class="rp-toc-num">3</span>The design system</a>
    <a class="rp-toc-pill" href="#mdx-components"><span class="rp-toc-num">4</span>MDX components</a>
    <a class="rp-toc-pill" href="#workflow-and-patterns"><span class="rp-toc-num">5</span>Workflow and patterns</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">6</span>FAQs</a>
  </div>

  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>
  <div class="rp-definition">
    The branding-aligned-product-documentation skill transforms raw documentation drafts into publish-ready MDX page code for ReadMe Refactored. It combines a design system of reusable HTML components with native ReadMe MDX elements, letting authors build polished, on-brand pages without writing CSS. Every page inherits Recurly's brand colors, typography, and layout patterns from a central host theme — no embedded stylesheets, no style drift.
  </div>

  <div class="rp-h1" id="key-benefits"><a class="rp-anchor" href="#key-benefits">Key benefits</a></div>

  <div class="rp-benefits rp-benefits-2x2">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Consistency at scale</strong>
      <span>Every page shares the same design tokens, spacing, typography, and color palette. No design drift, no one-off styles, no surprises in the final render.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>No CSS required</strong>
      <span>All styling lives in the host theme. Authors paste pure MDX with rp-* classes — no style blocks, no Tailwind, no environment setup.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Rapid iteration</strong>
      <span>The skill bridges content structure (delegated to base skills) and visual rendering. When a base skill updates, branding changes inherit automatically.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">✦</div>
      <strong>Rich interactivity</strong>
      <span>Combine rp-* HTML components with native ReadMe MDX: Accordions, Tabs, Cards, and Columns all render with brand styling automatically.</span>
    </div>
  </div>

  <div class="rp-h1" id="the-design-system"><a class="rp-anchor" href="#the-design-system">The design system</a></div>

  <div class="rp-h2" id="page-wrapper-and-typography"><a class="rp-anchor" href="#page-wrapper-and-typography">Page wrapper and typography</a></div>

  <p>Every page wraps its main content in <code>&lt;div class="rp-page"&gt;</code>. This single class applies Recurly's font family, line-height, max-width, and color palette automatically. No additional setup needed.</p>

  <div class="rp-callout rp-callout-tip">
    <div><strong>Tip</strong>The rp-page wrapper inherits all typography from the host theme. Your page stays in sync with Recurly's design language even when brand guidelines update.</div>
  </div>

  <div class="rp-h2" id="heading-hierarchy"><a class="rp-anchor" href="#heading-hierarchy">Heading hierarchy</a></div>

  <p>Four heading levels, each with distinct visual weight and anchor support:</p>

  <table class="rp-params">
    <tr class="rp-thead-row"><td>Level</td><td>Use for</td></tr>
    <tr><td><code>rp-h1</code></td><td>Top-level sections (Definition, Key benefits, Key details, FAQs)</td></tr>
    <tr><td><code>rp-h2</code></td><td>Subsections inside a major section or step</td></tr>
    <tr><td><code>rp-h3</code></td><td>Labels inside cards, callouts, or grouped content</td></tr>
    <tr><td><code>rp-h4</code></td><td>Step titles inside rp-step cards</td></tr>
  </table>

  <p>Every heading includes an anchor ID and a clickable <code>rp-anchor</code> link. Click any heading to update the URL bar — perfect for sharing direct links to sections.</p>

  <div class="rp-h2" id="content-cards"><a class="rp-anchor" href="#content-cards">Content cards</a></div>

  <div class="rp-card">
    <div class="rp-h3">What is rp-card?</div>
    <p>A general-purpose container for grouped content. Use it for callouts that don't fit the four callout types (note, tip, warning, important), explanatory boxes, or any content that benefits from visual separation without earning its own heading.</p>
  </div>

  <div class="rp-h2" id="callout-types"><a class="rp-anchor" href="#callout-types">Callout types</a></div>

  <p>Four callout flavors handle different levels of urgency and intent:</p>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>Neutral callouts for orientation, context, or general guidance. Use when you want to separate content without implying urgency.</div>
  </div>

  <div class="rp-callout rp-callout-tip">
    <div><strong>Tip</strong>Helpful hints and best practices. Use when offering advice that can accelerate the reader's understanding or workflow.</div>
  </div>

  <div class="rp-callout rp-callout-warning">
    <div><strong>Warning</strong>Important cautions or non-critical restrictions. Use when the reader should proceed with awareness of a limitation or side effect.</div>
  </div>

  <div class="rp-callout rp-callout-important">
    <div><strong>Important</strong>Critical alerts that require action or carry serious consequences. Use sparingly — only when something could break or fail.</div>
  </div>

  <div class="rp-h2" id="numbered-steps"><a class="rp-anchor" href="#numbered-steps">Numbered steps</a></div>

  <p>Steps use the <code>rp-step</code> card: a yellow-circled number paired with an action title and a brief description. Two patterns apply depending on content density.</p>

  <p><strong>Lightweight pattern</strong> — group brief steps in a single <code>rp-steps</code> wrapper:</p>

  <div class="rp-steps">
    <div class="rp-step">
      <div class="rp-step-num">1</div>
      <div><h4>Stack brief steps together</h4><p>Use this pattern when each step is 1–2 sentences with no code, images, or tables. Group all steps in a single rp-steps wrapper.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">2</div>
      <div><h4>Let the wrapper handle spacing</h4><p>The wrapper stacks cards automatically with consistent spacing, creating a unified procedure block.</p></div>
    </div>
    <div class="rp-step">
      <div class="rp-step-num">3</div>
      <div><h4>Keep titles as action verbs</h4><p>No "Step N:" prefix — the yellow circle handles the number. The h4 is just the action.</p></div>
    </div>
  </div>

  <p>For heavy steps with code blocks, screenshots, or tables, place each step in its own wrapper and let supporting content flow naturally between them.</p>

  <div class="rp-h2" id="navigation-buttons"><a class="rp-anchor" href="#navigation-buttons">Navigation buttons</a></div>

  <p>Three button styles serve different roles:</p>

  <div>
    <a class="rp-btn rp-btn-primary" href="#the-design-system" target="_blank">Primary button →</a>
    <a class="rp-btn rp-btn-secondary" href="#the-design-system" target="_blank">Secondary button →</a>
    <a class="rp-btn rp-btn-ghost" href="#the-design-system" target="_blank">Ghost button</a>
  </div>

  <p><strong>Primary</strong> handles main navigation and "learn more" links. <strong>Secondary</strong> handles downloads and primary actions. <strong>Ghost</strong> handles supporting or tertiary links.</p>

  <div class="rp-h2" id="tables"><a class="rp-anchor" href="#tables">Tables</a></div>

  <p>Three table classes cover different data shapes. All use <code>&lt;tr class="rp-thead-row"&gt;</code> for headers — never <code>&lt;thead&gt;</code> or <code>&lt;th&gt;</code>, which ReadMe overrides with pale, nearly invisible styling.</p>

  <table class="rp-gw-table">
    <tr class="rp-thead-row"><td>Table class</td><td>Use for</td></tr>
    <tr><td>rp-gw-table</td><td>Two-column feature matrices (feature → details). First column is bolded and fixed 35% width.</td></tr>
    <tr><td>rp-params</td><td>Two-column parameter or field references (param name → description). First column is bolded and fixed 28% width.</td></tr>
    <tr><td>rp-pm-table</td><td>Compact multi-column grids where every column is equal-weight. No special first-column treatment.</td></tr>
  </table>

  <div class="rp-h2" id="lists"><a class="rp-anchor" href="#lists">Lists</a></div>

  <p>Use <code>rp-list</code> for bulleted or numbered lists that benefit from a contained background:</p>

  <ul class="rp-list">
    <li>Each item is easy to scan</li>
    <li>The container provides visual separation</li>
    <li>Padding and border-radius keep content organized</li>
    <li>Pairs well with step descriptions or prerequisites</li>
  </ul>

  <div class="rp-h2" id="benefits-grid"><a class="rp-anchor" href="#benefits-grid">Benefits grid</a></div>

  <p>Display 3, 4, or 5 benefit cards in a responsive grid. Use <code>rp-benefits-2x2</code> for exactly 4 cards to force a 2×2 layout — otherwise four items would wrap awkwardly.</p>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>The grid in the Key benefits section above uses rp-benefits with the 2x2 variant. On mobile, all grids collapse to a single column automatically.</div>
  </div>

  <div class="rp-h1" id="mdx-components"><a class="rp-anchor" href="#mdx-components">MDX components</a></div>

  <p>MDX components — Accordion, Tabs, Cards, Columns — mix freely with rp-* HTML in the same page. Fenced code blocks also live as native markdown, picking up ReadMe's dark background and syntax highlighting automatically.</p>

</div>

```javascript
// Example: syntax-highlighted code block sitting between rp-* HTML
const example = {
  component: "lives as native markdown",
  styling: "picked up by host theme automatically",
  tokens: "yellow, tangerine, salmon, and friends"
};
```

<div class="rp-page">

  <div class="rp-h2" id="tabs-and-code-alternatives"><a class="rp-anchor" href="#tabs-and-code-alternatives">Tabs and code alternatives</a></div>

  <p>Use <code>&lt;Tabs&gt;</code> to show alternative views of the same task: multi-language code, by-environment instructions, or by-integration workflows. The active tab displays the yellow brand pill.</p>

</div>

<Tabs>
  <Tab title="JavaScript">
  ```javascript
  // JavaScript example
  const pageData = {
    title: "Christian's Journey",
    components: ["tabs", "cards", "accordions"],
    brand: "Recurly"
  };

  console.log(pageData);
  ```
  </Tab>
  <Tab title="Python">
  ```python
  # Python example
  page_data = {
      "title": "Christian's Journey",
      "components": ["tabs", "cards", "accordions"],
      "brand": "Recurly"
  }

  print(page_data)
  ```
  </Tab>
  <Tab title="cURL">
  ```bash
  # cURL example
  curl -X GET https://docs.recurly.com/docs/christians-journey \
    -H "Accept: application/json" \
    -H "User-Agent: Documentation"
  ```
  </Tab>
</Tabs>

<div class="rp-page">

  <div class="rp-h2" id="cards-for-navigation"><a class="rp-anchor" href="#cards-for-navigation">Cards for navigation</a></div>

  <p>Use <code>&lt;Cards&gt;</code> to build small navigation grids — 3 to 6 clickable destination tiles with icons, titles, and one-sentence blurbs. Below, you'll see a Cards component linking to related resources.</p>

</div>

<Cards>
  <Card title="Design system" href="#the-design-system" icon="fa-palette">
  Explore all rp-* components and typography rules.
  </Card>
  <Card title="Workflow guide" href="#workflow-and-patterns" icon="fa-gears">
  Learn the step-by-step process for creating pages.
  </Card>
  <Card title="Recurly docs" href="https://docs.recurly.com/docs" icon="fa-book" target="_blank">
  Browse the full Recurly documentation library.
  </Card>
</Cards>

<div class="rp-page">

  <div class="rp-h2" id="columns-for-comparison"><a class="rp-anchor" href="#columns-for-comparison">Columns for comparison</a></div>

  <p>Use <code>&lt;Columns&gt;</code> to display content side by side. Perfect for before/after pairs, request/response examples, or don't/do comparisons.</p>

</div>

<Columns columns={2}>
  <Column>
  **Don't** — single monolithic code block with no alternatives.
  </Column>
  <Column>
  **Do** — Tabs with cURL, JavaScript, Python, and other languages the reader might need.
  </Column>
</Columns>

<div class="rp-page">

  <div class="rp-h1" id="workflow-and-patterns"><a class="rp-anchor" href="#workflow-and-patterns">Workflow and patterns</a></div>

  <div class="rp-h2" id="pre-generation-discovery"><a class="rp-anchor" href="#pre-generation-discovery">Pre-generation discovery</a></div>

  <p>Before generating a page, scan the source and ask one consolidated question batch about items that would otherwise block publishing:</p>

  <ul class="rp-list">
    <li><strong>Plan availability</strong> — Which Recurly plans does this feature live on?</li>
    <li><strong>Missing URLs</strong> — Are all links complete, or should some be left as TODO?</li>
    <li><strong>Empty code blocks</strong> — Do you have examples for languages with placeholder fences?</li>
    <li><strong>Images</strong> — Are all image URLs provided, or should they be flagged as TODO?</li>
    <li><strong>Key benefits</strong> — If the source has no benefits, should we infer them?</li>
  </ul>

  <div class="rp-callout rp-callout-tip">
    <div><strong>Tip</strong>Asking questions first keeps the user engaged and means generation produces something publish-ready in one pass — not a TODO list that surfaces after a long wait.</div>
  </div>

  <div class="rp-h2" id="section-weight-and-hierarchy"><a class="rp-anchor" href="#section-weight-and-hierarchy">Section weight and hierarchy</a></div>

  <p>Not every source heading becomes a section. Apply judgment based on content density:</p>

  <div class="rp-card">
    <div class="rp-h3">Demote if:</div>
    <p>One or two sentences, no steps, no image, no table. Fold into a neighbor or convert to an inline <code>rp-card</code>.</p>
  </div>

  <div class="rp-card">
    <div class="rp-h3">Promote if:</div>
    <p>Multiple sibling subsections of the same shape (CRUD actions), or content with its own steps, screenshots, and a distinct outcome from siblings.</p>
  </div>

  <div class="rp-h2" id="image-placement-and-lightbox"><a class="rp-anchor" href="#image-placement-and-lightbox">Image placement and lightbox</a></div>

  <p>Every image goes inline at the exact position it appears in the source — never grouped at the end. The lightbox pattern wraps every image so readers can click to expand full-screen without leaving the page. The pattern is JavaScript-free, using just a checkbox and labels.</p>

  <div class="rp-callout rp-callout-important">
    <div><strong>Important</strong>Correct image placement is critical because non-technical authors cannot manually reintegrate images after generation. If an image should illustrate step 3, it must appear between step 2 and step 3 in the output.</div>
  </div>

  <div class="rp-h2" id="anchor-ids-and-toc"><a class="rp-anchor" href="#anchor-ids-and-toc">Anchor IDs and TOC pills</a></div>

  <p>Every <code>rp-h1</code> section gets an <code>id</code> attribute and an <code>rp-anchor</code> link. The TOC pill bar at the top of the page lists all major sections and links to their anchors. Readers jump directly to any section without scrolling.</p>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>The anchor ID is generated by slugifying the heading text: "Setting up Adyen" becomes <code>id="setting-up-adyen"</code>. Strip punctuation, lowercase, replace spaces with hyphens.</div>
  </div>

  <div class="rp-h2" id="mixing-html-and-mdx"><a class="rp-anchor" href="#mixing-html-and-mdx">Mixing HTML and MDX</a></div>

  <p>Output is pure MDX. Write rp-* HTML divs and MDX components (<code>&lt;Accordion&gt;</code>, <code>&lt;Tabs&gt;</code>, <code>&lt;Cards&gt;</code>, <code>&lt;Columns&gt;</code>) in any order. Wrap the main content in <code>&lt;div class="rp-page"&gt;</code> so it inherits brand typography from the host theme. No <code>&lt;style&gt;</code> blocks, no HTMLBlock wrappers, no special syntax — just clean, readable content.</p>

  <table class="rp-pm-table">
    <tr class="rp-thead-row"><td>What goes where</td><td>Example</td></tr>
    <tr><td>rp-* HTML divs</td><td>Headings, callouts, cards, tables, benefits grids</td></tr>
    <tr><td>Native MDX components</td><td>Accordion, Tabs, Cards, Columns, Callout, Image</td></tr>
    <tr><td>Fenced code blocks</td><td>Triple-backtick markdown with language tag</td></tr>
    <tr><td>Always omitted</td><td>style blocks, Tailwind classes, inline CSS hacks</td></tr>
  </table>

  <div class="rp-h2" id="the-two-layers"><a class="rp-anchor" href="#the-two-layers">The two layers</a></div>

  <p>The skill has two layers: content (delegated to base skills) and rendering (this skill). Base skills control section structure, tone, grammar, and word choice. This skill controls HTML components, MDX layout, and brand visuals.</p>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong>If there's ever a conflict between a base skill's content rule and a rendering rule, the base skill wins. This skill only has authority over how things look, not what they say.</div>
  </div>

  <div class="rp-h1" id="faqs"><a class="rp-anchor" href="#faqs">FAQs</a></div>

</div>

<Accordion title="Can I embed a style block inside my page output?">
No — never embed CSS in the output. All styling lives in Recurly's host theme on ReadMe. The output stays clean and copy-pasteable: just MDX with rp-* classes, plus native MDX components.
</Accordion>

<Accordion title="What if my page needs a component that doesn't exist in the design system?">
Surface it as part of the pre-gen Q&A batch and wait for approval. The "New Section Alert" format lets you propose a new component, its purpose, rendering, and rules. The user approves, and you add it to the registry.
</Accordion>

<Accordion title="Do I need to understand ReadMe's MDX parser?">
Only enough to know that MDX components (Accordion, Tabs, Cards, Columns) and fenced code blocks can sit anywhere in the content flow. The host theme handles all brand styling automatically — no configuration needed.
</Accordion>

<Accordion title="How do I handle multi-language code examples?">
Use `<Tabs>` with one `<Tab>` per language. Inside each Tab, add a fenced code block with the language tag. ReadMe applies syntax highlighting and the brand color scheme automatically. The yellow pill marks the active tab.
</Accordion>

<Accordion title="What's the difference between rp-card and the Card MDX component?">
rp-card is an HTML container for static grouped content. `<Card>` is a clickable navigation tile that lives inside a `<Cards>` grid. Use rp-card for explanatory boxes, callouts, or asides. Use `<Card>` for navigation grids of 3–6 destinations.
</Accordion>

<Accordion title="Can I use Tailwind classes in my output?">
No. Avoid any ad-hoc inline styles or Tailwind classes. All styling comes from the rp-* design system or the host theme. This keeps pages consistent and future-proof.
</Accordion>

<Accordion title="What happens to my images if I move them around the page?">
Non-technical authors can't reintegrate images manually. Images must appear at their exact position in the source. If an image should illustrate a step, place it immediately after that step — never move it to the end of the page.
</Accordion>

<Accordion title="Do I need to ask the user about every missing detail?">
No — ask only about items that materially change what gets published. Skip routine tone tightening, stylistic choices, and metadata descriptions (just draft one). Ask about plan availability, missing URLs, empty code blocks, and new structural sections.
</Accordion>