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

  <div class="rp-plan"><i class="fa fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#the-design-system"><span class="rp-toc-num">3</span>The design system</a>
    <a class="rp-toc-pill" href="#mdx-components"><span class="rp-toc-num">4</span>MDX components</a>
    <a class="rp-toc-pill" href="#workflow-and-patterns"><span class="rp-toc-num">5</span>Workflow and patterns</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">6</span>FAQs</a>
  </div>
</div>

# Definition

<div class="rp-definition">
  The branding-aligned-product-documentation skill transforms raw documentation drafts into publish-ready MDX page code for ReadMe Refactored. It combines a design system of reusable HTML components with native ReadMe MDX elements, letting authors build polished, on-brand pages without writing CSS. Every page inherits Recurly's brand colors, typography, and layout patterns from a central host theme — no embedded stylesheets, no style drift.
</div>

# Key benefits

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

# The design system

## Page wrapper and typography

Every page wraps its branded top matter — overview, plan pill, TOC — in `<div class="rp-page">`. This single class applies Recurly's font family, line-height, max-width, and color palette to its children. Section headings sit outside the wrapper as native markdown so they register in ReadMe's built-in page TOC sidebar.

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa fa-lightbulb-o" aria-hidden="true"></i> Tip</strong>The rp-page wrapper inherits all typography from the host theme. Your page stays in sync with Recurly's design language even when brand guidelines update.</div>
</div>

## Heading hierarchy

All headings are written as **native markdown** — `#` through `#####`. ReadMe applies its global CSS to these automatically and registers them in the built-in page TOC sidebar. No `rp-h*` classes, no `id` attributes, no `rp-anchor` wrappers needed.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Level</td><td>Use for</td></tr>
  <tr><td><code>#</code> h1</td><td>Top-level sections (Definition, Key benefits, Key details, FAQs)</td></tr>
  <tr><td><code>##</code> h2</td><td>Subsections inside a major section or step body</td></tr>
  <tr><td><code>###</code> h3</td><td>Labels inside grouped content</td></tr>
  <tr><td><code>####</code> h4</td><td>Step titles inside rp-step cards (handled by the card itself)</td></tr>
  <tr><td><code>#####</code> h5</td><td>Lowest-level label — rarely needed</td></tr>
</table>

ReadMe slugifies heading text automatically: "Setting up Adyen" becomes `#setting-up-adyen`. The native page TOC sidebar then registers it.

## Content cards

<div class="rp-card">

### What is rp-card?

A general-purpose container for grouped content. Use it for explanatory boxes, orientation notes, or any content that benefits from visual separation without earning its own heading.

</div>

## Callout types

Four callout flavors handle different levels of urgency and intent:

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong>Neutral callouts for orientation, context, or general guidance. Use when you want to separate content without implying urgency.</div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa fa-lightbulb-o" aria-hidden="true"></i> Tip</strong>Helpful hints and best practices. Use when offering advice that can accelerate the reader's understanding or workflow.</div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa fa-exclamation-triangle" aria-hidden="true"></i> Warning</strong>Important cautions or non-critical restrictions. Use when the reader should proceed with awareness of a limitation or side effect.</div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa fa-exclamation-circle" aria-hidden="true"></i> Important</strong>Critical alerts that require action or carry serious consequences. Use sparingly — only when something could break or fail.</div>
</div>

## Numbered steps

Steps use the `rp-step` card: a yellow-circled number paired with an action title and a brief description. Two patterns apply depending on content density.

**Lightweight pattern** — group brief steps in a single `rp-steps` wrapper:

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

For heavy steps with code blocks, screenshots, or tables, place each step in its own wrapper and let supporting content flow naturally between them.

## Navigation buttons

Three button styles serve different roles:

<div>
  <a class="rp-btn rp-btn-primary" href="#the-design-system">Primary button →</a>
  <a class="rp-btn rp-btn-secondary" href="#the-design-system">Secondary button →</a>
  <a class="rp-btn rp-btn-ghost" href="#the-design-system">Ghost button</a>
</div>

**Primary** handles main navigation and "learn more" links. **Secondary** handles downloads and primary actions. **Ghost** handles supporting or tertiary links.

## Tables

Three table classes cover different data shapes. All use `<tr class="rp-thead-row">` for headers — never `<thead>` or `<th>`, which ReadMe overrides with pale, nearly invisible styling.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Table class</td><td>Use for</td></tr>
  <tr><td>rp-gw-table</td><td>Two-column feature matrices (feature → details). First column is bolded and fixed 35% width.</td></tr>
  <tr><td>rp-params</td><td>Two-column parameter or field references (param name → description). First column is bolded and fixed 28% width.</td></tr>
  <tr><td>rp-pm-table</td><td>Compact multi-column grids where every column is equal-weight. No special first-column treatment.</td></tr>
</table>

## Lists

Use `rp-list` for bulleted or numbered lists that benefit from a contained background:

<ul class="rp-list">
  <li>Each item is easy to scan</li>
  <li>The container provides visual separation</li>
  <li>Padding and border-radius keep content organized</li>
  <li>Pairs well with step descriptions or prerequisites</li>
</ul>

## Benefits grid

Display 3, 4, or 5 benefit cards in a responsive grid. Use `rp-benefits-2x2` for exactly 4 cards to force a 2×2 layout — otherwise four items would wrap awkwardly.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong>The grid in the Key benefits section above uses rp-benefits with the 2×2 variant. On mobile, all grids collapse to a single column automatically.</div>
</div>

# MDX components

MDX components — Accordion, Tabs, Cards, Columns — mix freely with rp-* HTML in the same page. Fenced code blocks also live as native markdown, picking up ReadMe's dark background and syntax highlighting automatically.

```javascript
// Example: syntax-highlighted code block sitting alongside rp-* HTML
const example = {
  component: "lives as native markdown",
  styling: "picked up by host theme automatically",
  tokens: "yellow, tangerine, salmon, and friends"
};
```

## Tabs and code alternatives

Use `<Tabs>` to show alternative views of the same task: multi-language code, by-environment instructions, or by-integration workflows. The active tab displays the yellow brand pill.

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

## Cards for navigation

Use `<Cards>` to build small navigation grids — 3 to 6 clickable destination tiles with icons, titles, and one-sentence blurbs.

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

## Columns for comparison

Use `<Columns>` to display content side by side. Perfect for before/after pairs, request/response examples, or don't/do comparisons.

<Columns columns={2}>
  <Column>
    **Don't** — single monolithic code block with no alternatives.
  </Column>

  <Column>
    **Do** — Tabs with cURL, JavaScript, Python, and other languages the reader might need.
  </Column>
</Columns>

# Workflow and patterns

## Pre-generation discovery

Before generating a page, scan the source and ask one consolidated question batch about items that would otherwise block publishing:

<ul class="rp-list">
  <li><strong>Plan availability</strong> — Which Recurly plans does this feature live on?</li>
  <li><strong>Missing URLs</strong> — Are all links complete, or should some be left as TODO?</li>
  <li><strong>Empty code blocks</strong> — Do you have examples for languages with placeholder fences?</li>
  <li><strong>Images</strong> — Are all image URLs provided, or should they be flagged as TODO?</li>
  <li><strong>Key benefits</strong> — If the source has no benefits, should we infer them?</li>
</ul>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa fa-lightbulb-o" aria-hidden="true"></i> Tip</strong>Asking questions first keeps the user engaged and means generation produces something publish-ready in one pass — not a TODO list that surfaces after a long wait.</div>
</div>

## Section weight and hierarchy

Not every source heading becomes a section. Apply judgment based on content density:

<div class="rp-card">

### Demote if:

One or two sentences, no steps, no image, no table. Fold into a neighbor or convert to an inline `rp-card`.

</div>

<div class="rp-card">

### Promote if:

Multiple sibling subsections of the same shape (CRUD actions), or content with its own steps, screenshots, and a distinct outcome from siblings.

</div>

## Image placement and lightbox

Every image goes inline at the exact position it appears in the source — never grouped at the end. The lightbox pattern wraps every image so readers can click to expand full-screen without leaving the page. The pattern is JavaScript-free, using just a checkbox and labels.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa fa-exclamation-circle" aria-hidden="true"></i> Important</strong>Correct image placement is critical because non-technical authors cannot manually reintegrate images after generation. If an image should illustrate step 3, it must appear between step 2 and step 3 in the output.</div>
</div>

## Anchor IDs and the TOC pill bar

Every native `#` heading gets an anchor ID automatically — ReadMe slugifies the heading text and registers it in the built-in page TOC sidebar. No `id` attributes, no `rp-anchor` wrappers required. On top of the native sidebar, every page also includes an `rp-toc` pill bar at the top of the content, giving readers an immediate visual map of the page structure.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong>The rp-toc pill bar is required on every page with two or more <code>#</code> h1 sections. Omit it only when a page has a single <code>#</code> h1.</div>
</div>

## Mixing HTML and MDX

Output is pure MDX. Write rp-* HTML divs and MDX components (`<Accordion>`, `<Tabs>`, `<Cards>`, `<Columns>`) in any order. The `<div class="rp-page">` wrapper holds the branded top matter (overview, plan pill, TOC); native `#` headings and the rest of the content flow outside it. No `<style>` blocks, no HTMLBlock wrappers, no special syntax — just clean, readable content.

<table class="rp-pm-table">
  <tr class="rp-thead-row"><td>What goes where</td><td>Example</td></tr>
  <tr><td>rp-* HTML divs</td><td>Callouts, cards, tables, benefits grids, step cards</td></tr>
  <tr><td>Native MDX components</td><td>Accordion, Tabs, Cards, Columns, Callout, Image</td></tr>
  <tr><td>Native markdown headings</td><td>All section headings — # through #####</td></tr>
  <tr><td>Fenced code blocks</td><td>Triple-backtick markdown with language tag</td></tr>
  <tr><td>Always omitted</td><td>style blocks, Tailwind classes, rp-h* divs, rp-anchor wrappers</td></tr>
</table>

## The two layers

The skill has two layers: content (delegated to base skills) and rendering (this skill). Base skills control section structure, tone, grammar, and word choice. This skill controls HTML components, MDX layout, and brand visuals.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong>If there's ever a conflict between a base skill's content rule and a rendering rule, the base skill wins. This skill only has authority over how things look, not what they say.</div>
</div>

## Proposing new components with the New Section Alert

When you encounter a source section that doesn't fit the standard registry — a top-level structural section with distinct purpose, visual treatment, and expected recurrence — don't skip it or fold it into Key details. Instead, propose it formally using the New Section Alert.

The process happens **during pre-generation discovery (Step 1)**. When you spot a genuinely novel section, surface it as one numbered item in your consolidated Q&A batch, alongside questions about plan availability and missing URLs. Use this format:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🆕 NEW SECTION IDENTIFIED — YOUR APPROVAL REQUIRED
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The source content contains a structural section not found in the
current registry for the [DOC TYPE] base skill.

Section name:   [Proposed name]
Found in:       [Page title]
Purpose:        [What it does and why it's structurally distinct
                 from content inside Key details]
Position:       [Where in the page flow it would sit]

Proposed canonical instruction block:
──────────────────────────────────────
### SECTION: [Name]
Doc types:  [Which types use this]
Purpose:    [One-line purpose]
Rendering:  [Component name from library / new component]
Component:  [HTML template to add to the component library]
Rules:
- [Rule 1]
- [Rule 2]
──────────────────────────────────────

Reply with one of:
  "Yes, add it"              → approve, add to registry, continue generating
  "No, skip it"              → omit this section, continue generating
  "No, treat as Key details" → fold content into Key details, continue generating
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

**What you're proposing:** The `Component` field should contain the HTML template to add to the component library — the rp-* class name, structure, and CSS hooks needed for the new section to render with brand styling. Consult the design system reference section to pick a non-colliding class name and reuse existing color tokens (`--yellow`, `--tangerine`, `--offblack`, etc.) rather than inventing new hex values.

**What the user decides:** They reply with one of three paths. "Yes, add it" means you'll add the section to the skill's registry and generate the page with the new section included. "No, skip it" means you omit the section and continue. "No, treat as Key details" means you fold the section's content into an existing Key details area instead.

**Key distinction:** A new section is NOT just a heading under Key details — that's content organization. A new section is a standalone block with its own purpose, rendering, and rules that would appear on other pages of the same doc type in the future. Only propose when the section truly earns its weight.

# FAQs

<Accordion title="Can I embed a style block inside my page output?">
  No — never embed CSS in the output. All styling lives in Recurly's host theme on ReadMe. The output stays clean and copy-pasteable: just MDX with rp-\* classes, plus native MDX components.
</Accordion>

<Accordion title="Do I need to add id attributes or rp-anchor wrappers to my headings?">
  No. ReadMe slugifies native markdown headings automatically and registers them in the built-in page TOC sidebar. Just write `# Heading text` and the rest is handled for you.
</Accordion>

<Accordion title="Is the rp-toc pill bar required?">
  Yes — include it on every page with two or more `#` h1 sections. It gives readers an immediate visual map at the top of the content and complements ReadMe's native TOC sidebar.
</Accordion>

<Accordion title="What if my page needs a component that doesn't exist in the design system?">
  Surface it as part of the pre-gen Q\&A batch and wait for approval. The "New Section Alert" format lets you propose a new component, its purpose, rendering, and rules. The user approves, and you add it to the registry.
</Accordion>

<Accordion title="How do I handle multi-language code examples?">
  Use `<Tabs>` with one `<Tab>` per language. Inside each Tab, add a fenced code block with the language tag. ReadMe applies syntax highlighting and the brand color scheme automatically. The yellow pill marks the active tab.
</Accordion>

<Accordion title="What's the difference between rp-card and the Card MDX component?">
  rp-card is an HTML container for static grouped content. `<Card>` is a clickable navigation tile that lives inside a `<Cards>` grid. Use rp-card for explanatory boxes, callouts, or asides. Use `<Card>` for navigation grids of 3–6 destinations.
</Accordion>

<Accordion title="Can I use Tailwind classes in my output?">
  No. Avoid any ad-hoc inline styles or Tailwind classes. All styling comes from the rp-\* design system or the host theme. This keeps pages consistent and future-proof.
</Accordion>

<Accordion title="What happens to my images if I move them around the page?">
  Non-technical authors can't reintegrate images manually. Images must appear at their exact position in the source. If an image should illustrate a step, place it immediately after that step — never move it to the end of the page.
</Accordion>

<Accordion title="Do I need to ask the user about every missing detail?">
  No — ask only about items that materially change what gets published. Skip routine tone tightening, stylistic choices, and metadata descriptions (just draft one). Ask about plan availability, missing URLs, empty code blocks, and new structural sections.
</Accordion>