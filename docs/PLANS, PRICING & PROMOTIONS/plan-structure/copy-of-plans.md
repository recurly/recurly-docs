---
title: Copy of Plans
excerpt: >-
  How to create, configure, update, duplicate, and delete subscription plans in
  Recurly — including billing cycles, pricing models, price segments, and
  add-ons.
deprecated: false
hidden: true
metadata:
  robots: index
---
# ReadMe MDX Renderer Test Page

Paste this entire page into the ReadMe editor. Each test is numbered and labeled.
Check the rendered output against the expected result for each one.

***

## GROUP A — Blank lines inside `<div>` blocks

### A1 — `<div>` with NO blank line before markdown heading

<div class="rp-card">

### Heading inside div — no blank line before it

This is prose directly after the heading, also no blank line.

</div>

**Expected:** Heading renders as a heading. Prose renders as prose. Card styled correctly.

***

### A2 — `<div>` WITH blank line before markdown heading

<div class="rp-card">

### Heading inside div — blank line before it

This is prose after a blank line.

</div>

**Expected:** If this breaks, headings inside divs need no blank lines. If it renders fine, blank lines are safe.

***

### A3 — `<div>` with NO blank line before prose only (no heading)

<div class="rp-card">

This is prose with no heading and no blank lines inside the div.

</div>

**Expected:** Prose renders normally inside the card.

***

### A4 — `<div>` with blank line before prose only

<div class="rp-card">

This is prose with a blank line before it but no heading.

</div>

**Expected:** Tells us if blank lines before prose (not headings) is the trigger.

***

### A5 — Nested `<div>` inside `<div>`, no blank lines

<div class="rp-card">
<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> This callout is inside a card with no blank lines anywhere.</div>
</div>
</div>

**Expected:** Both card and callout render correctly.

***

### A6 — Nested `<div>` inside `<div>`, with blank lines

<div class="rp-card">

<div class="rp-callout rp-callout-note">

<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> This callout is inside a card with blank lines between the divs.</div>

</div>

</div>

**Expected:** Tests whether blank lines between nested divs break rendering.

***

## GROUP B — `<span>` vs `<div>` tolerance

### B1 — `<span>` with blank lines inside (zoom pattern)

<span class="rp-zoom">

  <label onClick={(e)=>{e.currentTarget.nextElementSibling.classList.add('rp-zoom-open');}}>
    <img class="rp-zoom-img"
         src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png"
         alt="Test image"
         style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>

  <div class="rp-zoom-overlay" onClick={(e)=>{e.currentTarget.classList.remove('rp-zoom-open');}}>
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </div>

</span>

**Expected:** Image renders and clicking it opens the lightbox overlay.

***

### B2 — `<span>` with NO blank lines inside (zoom pattern)

<span class="rp-zoom">
  <label onClick={(e)=>{e.currentTarget.nextElementSibling.classList.add('rp-zoom-open');}}>
    <img class="rp-zoom-img"
         src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png"
         alt="Test image"
         style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>
  <div class="rp-zoom-overlay" onClick={(e)=>{e.currentTarget.classList.remove('rp-zoom-open');}}>
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </div>
</span>

**Expected:** Same as B1 — tells us if blank lines inside `<span>` matter.

***

## GROUP C — Markdown headings inside vs outside divs

### C1 — Markdown `###` OUTSIDE any div (baseline)

### This is a plain ### heading outside all divs

**Expected:** Always renders correctly. Baseline reference.

***

### C2 — Markdown `##` heading outside div, between two divs

<div class="rp-callout rp-callout-tip">
<div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> Callout before the heading.</div>
</div>

## This ## heading is between two divs, outside both

<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Callout after the heading.</div>
</div>

**Expected:** Heading renders correctly between two divs.

***

### C3 — `<h3>` raw HTML inside a div (no markdown)

<div class="rp-card">
<h3>This is a raw HTML h3 inside a div</h3>
<p>This is a raw HTML paragraph inside the same div.</p>
</div>

**Expected:** Heading and prose render. Tells us if raw HTML is more reliable than markdown inside divs.

***

## GROUP D — rp-steps inside rp-card (the "Create Plan" card case)

### D1 — `rp-card` containing an `rp-step`, no blank lines

<div class="rp-card">
<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Step inside a card</h4><p>This step is inside an rp-card with no blank lines anywhere.</p></div>
</div>
</div>
</div>

**Expected:** Card and step both render correctly.

***

### D2 — `rp-card` containing markdown prose and a heading, no blank lines

<div class="rp-card">

### Card heading — no blank lines

After creating a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration.

</div>

**Expected:** Tests the exact pattern from the broken Plans page card.

***

### D3 — `rp-card` containing markdown prose and a heading, WITH blank lines

<div class="rp-card">

### Card heading — with blank lines

After creating a plan, you can set up a <a href="https://docs.recurly.com/docs/checkout" target="_blank">Checkout</a> configuration.

</div>

**Expected:** Directly compares with D2.

***

## GROUP E — rp-plan pill and rp-toc inside rp-page

### E1 — Full rp-page header block (condensed, no blank lines)

<div class="rp-page">
<div class="rp-overview">

This is the overview paragraph. No blank lines inside the rp-page div.

</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
</div>
</div>

**Expected:** Overview, plan pill, and TOC pills all render correctly.

***

### E2 — Full rp-page header block WITH blank lines between children

<div class="rp-page">

<div class="rp-overview">

This is the overview paragraph. Blank lines between children inside rp-page.

</div>

<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
</div>

</div>

**Expected:** Compares with E1.

***

## GROUP F — Tables (rp-gw-table)

### F1 — rp-gw-table standalone, no surrounding divs

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Plan name</strong></td><td>Test value one.</td></tr>
  <tr><td><strong>Plan code</strong></td><td>Test value two.</td></tr>
</table>

**Expected:** Table renders with dark header row and branded styling.

***

### F2 — rp-gw-table immediately after a `<span class="rp-zoom">` block (no blank line)

<span class="rp-zoom">
  <label onClick={(e)=>{e.currentTarget.nextElementSibling.classList.add('rp-zoom-open');}}>
    <img class="rp-zoom-img" src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="Test" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>
  <div class="rp-zoom-overlay" onClick={(e)=>{e.currentTarget.classList.remove('rp-zoom-open');}}>
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </div>
</span>
<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Field A</strong></td><td>No blank line between zoom span and table.</td></tr>
</table>

**Expected:** Both image and table render correctly back to back.

***

### F3 — rp-gw-table immediately after a `<span class="rp-zoom">` block (WITH blank line)

<span class="rp-zoom">
  <label onClick={(e)=>{e.currentTarget.nextElementSibling.classList.add('rp-zoom-open');}}>
    <img class="rp-zoom-img" src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="Test" style={{display:"block", width:"90%", margin:"16px auto", border:"1px solid #CCC9B8", borderRadius:"8px"}} />
  </label>
  <div class="rp-zoom-overlay" onClick={(e)=>{e.currentTarget.classList.remove('rp-zoom-open');}}>
    <img src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" alt="" />
  </div>
</span>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td><strong>Field A</strong></td><td>Blank line between zoom span and table.</td></tr>
</table>

**Expected:** Compares with F2.

***

***

## GROUP G — `rp-benefit` blank line cases

### G1 — `rp-benefit` tight (no blank lines, icon + strong + span all consecutive)

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Benefit title</strong>
    <span>Benefit description — tight layout, no blank lines inside rp-benefit.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Benefit title two</strong>
    <span>Benefit description two — also tight.</span>
  </div>
</div>

**Expected:** Both benefit cards render with icon, bold title, and description text.

***

### G2 — `rp-benefit` with blank line between icon div and strong/span

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon">
      <i class="fa-solid fa-circle-check" aria-hidden="true"></i>
    </div>

```
<strong>Benefit title</strong>
<span>Blank line between icon div and strong/span — mirrors the broken pattern.</span>
```

  </div>
</div>

**Expected:** SHOULD break — strong and span render as code blocks. Confirms the cause.

***

### G3 — `rp-benefit` icon div on one line, tight, strong/span on next lines

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Benefit title</strong>
    <span>Icon div is on one line, strong and span follow with no blank lines.</span>
  </div>
</div>

**Expected:** Renders correctly — confirms single-line icon div is fine.

***

_End of test page. Record which tests pass and which fail, then report back._

<br />


<Image src="https://files.readme.io/2f3c920e039599c79b0f1043f4e070b1b9c301e1763d874dee8a144909d38b62-image.png" align="center" width="75%" border={true} framed={true} />


<br />


<Image src="https://files.readme.io/4668ce08bf74d2e6aa59d9af19e99331f16302712f96806ef77c9867a51b92b8-image.png" align="center" />


<br />
