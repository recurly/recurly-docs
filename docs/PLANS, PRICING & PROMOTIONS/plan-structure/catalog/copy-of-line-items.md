---
title: Copy of Line items
excerpt: >-
  Line items are the individual charges and components listed on a Recurly
  invoice, representing products, services, or adjustments applied to a
  transaction.
deprecated: false
hidden: true
metadata:
  robots: index
---
```html
<div class="rp-page">

  <div class="rp-plan">✦ Available on all Recurly plans</div>

  <!-- TOC -->
  <nav class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span> Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span> Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span> Key details</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">4</span> FAQs</a>
  </nav>

  <!-- Prerequisites & Limitations -->
  <div class="rp-h3" id="prerequisites">Prerequisites</div>
  <ul class="rp-list">
    <li>Line item names can be chosen freely, but check with your payment gateway before using special characters.</li>
  </ul>

  <div class="rp-h3" id="limitations">Limitations</div>
  <ul class="rp-list">
    <li>Invoices display only the first 500 line items in the Admin Console, Hosted Invoice, and PDF views. The subtotal, tax, and total always reflect all line items, including those beyond the first 500.</li>
    <li>To access line items beyond 500, use the <a href="https://docs.recurly.com/docs/adjustments-exports" target="_blank">Adjustments Export</a>.</li>
  </ul>

  <!-- Definition -->
  <div class="rp-h1" id="definition"><a class="rp-anchor" href="#definition">Definition</a></div>
  <div class="rp-definition">
    Line items are individual charges or components listed on an invoice. Each one represents a product, service, or adjustment applied to a transaction — and they can be tied to a subscription or stand alone as one-off charges.
  </div>

  <!-- Key benefits -->
  <div class="rp-h1" id="key-benefits"><a class="rp-anchor" href="#key-benefits">Key benefits</a></div>
  <div class="rp-benefits rp-benefits-2x2">
    <div class="rp-benefit">
      <div class="rp-benefit-icon">🧾</div>
      <strong>Clear billing breakdown</strong>
      <span>Every charge is itemized, giving subscribers full visibility into what they're being billed for and why.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">⚡</div>
      <strong>Supports stand-alone items</strong>
      <span>Line items don't need to be tied to a subscription — you can invoice one-off charges independently.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">📡</div>
      <strong>Displayed across channels</strong>
      <span>Line items are visible in the Admin Console, PDF invoices, Hosted Invoice pages, and Hosted Account Management.</span>
    </div>
    <div class="rp-benefit">
      <div class="rp-benefit-icon">🔒</div>
      <strong>Payments compliance</strong>
      <span>Line items are sent to gateways in specific cases — such as Klarna usage — and well-formed descriptions can qualify transactions for lower interchange rates.</span>
    </div>
  </div>

  <!-- Key details -->
  <div class="rp-h1" id="key-details"><a class="rp-anchor" href="#key-details">Key details</a></div>

  <div class="rp-h2" id="invoice-line-items"><a class="rp-anchor" href="#invoice-line-items">Invoice line items</a></div>
  <p>Every line item on an invoice displays the following columns:</p>
  <table class="rp-params">
    <tr class="rp-thead-row"><td>Column</td><td>Details</td></tr>
    <tr><td>Date</td><td>The date the charge or adjustment was applied.</td></tr>
    <tr><td>Description</td><td>The name or label of the product, service, or adjustment.</td></tr>
    <tr><td>Quantity</td><td>The number of units billed.</td></tr>
    <tr><td>Price</td><td>The per-unit price.</td></tr>
    <tr><td>Discount</td><td>Any discount applied to the line item. Only shown when a discount exists.</td></tr>
    <tr><td>Subtotal</td><td>Quantity × price, after any applicable discount.</td></tr>
    <tr><td>Tax</td><td>Tax amount and rate, when applicable.</td></tr>
    <tr><td>Total</td><td>Final amount including tax. Only shown when tax is applied.</td></tr>
  </table>

  <div class="rp-callout rp-callout-note">
    <div><strong>Note</strong> Invoices in the Admin Console, Hosted Invoice, and PDF format show only the first 500 line items. However, the subtotal, tax, and total always reflect the full set — even items beyond the first 500. To download all line items, use the <a href="https://docs.recurly.com/docs/adjustments-exports" target="_blank">Adjustments Export</a>.</div>
  </div>

  <div class="rp-h2" id="description-and-naming-guidelines"><a class="rp-anchor" href="#description-and-naming-guidelines">Description and naming guidelines</a></div>
  <p>Well-written line item descriptions matter beyond aesthetics. They appear on subscriber invoices, Hosted Account Management pages, and Hosted Invoice PDFs — and in certain cases they're sent directly to your payment gateway.</p>
  <p>Following these guidelines also supports <strong>Commercial Enhanced Data Program (CEDP)</strong> compliance. CEDP is a Visa program (updated in 2025) that validates transaction data quality. Merchants with compliant line item data can qualify for reduced interchange rates.</p>

  <div class="rp-callout rp-callout-warning">
    <div><strong>HIPAA reminder</strong> If your payment gateway is not HIPAA-compliant, do not include Protected Health Information (PHI) in invoice descriptions, product codes, plan names, or line item data.</div>
  </div>

  <table class="rp-pm-table">
    <tr class="rp-thead-row"><td>Guideline</td><td>What to do</td></tr>
    <tr><td>Be specific</td><td>Use clear, descriptive names rather than generic labels like "Item 1" or "Charge."</td></tr>
    <tr><td>Match the product</td><td>If you sell fruit, list "Apple," "Orange," and "Banana" — not "Fruits."</td></tr>
    <tr><td>Avoid business names</td><td>Don't repeat your company name in item names (e.g., "Fruit Shop Items").</td></tr>
    <tr><td>Skip single-character names</td><td>Avoid names that are a single character or made up entirely of symbols — they confuse subscribers.</td></tr>
    <tr><td>Character limit</td><td>Descriptions must be 255 characters or fewer.</td></tr>
    <tr><td>Special characters</td><td>Check with your payment gateway about any restrictions before using special characters.</td></tr>
  </table>

  <!-- FAQs heading inside the HTMLBlock -->
  <div class="rp-h1" id="faqs"><a class="rp-anchor" href="#faqs">FAQs</a></div>

</div>
```

<Accordion title="What happens to line items beyond the first 500 on an invoice?">
Invoices in the Admin Console, Hosted Invoice, and PDF views display only the first 500 line items. That said, the invoice subtotal, tax, and total always reflect every line item — including those beyond the limit. To view or download the full set, use the [Adjustments Export](https://docs.recurly.com/docs/adjustments-exports).
</Accordion>

<Accordion title="Do line item descriptions affect how transactions are processed by payment gateways?">
Yes, in certain cases. Line items are sent to payment gateways for transactions like Klarna payments. Accurate, descriptive names can also help your transactions qualify for lower interchange rates under Visa's Commercial Enhanced Data Program (CEDP). Keep descriptions specific to the product or service being billed — and make sure they don't include PHI if your gateway isn't HIPAA-compliant.
</Accordion>

<Accordion title="Can I create a line item that isn't tied to a subscription?">
Yes. Line items can be stand-alone charges — they don't need to be associated with a subscription to appear on an invoice. This makes them useful for one-off fees, adjustments, or any ad hoc charges you need to bill outside of a recurring plan.
</Accordion>