---
title: Line items
excerpt: >-
  Learn how line items are displayed on invoices and how they impact totals,
  taxes, and hosted page displays.
deprecated: false
hidden: false
metadata:
  robots: index
---
Title: Line items
Metadata description: How line items work on Recurly invoices — what they display, how to name them, and compliance best practices for L2/L3 data and HIPAA.

---PASTE INTO EDITOR BELOW---

<div class="rp-page">

  <div class="rp-overview">
    Line items are the individual charges listed on a Recurly invoice — each one representing a product, service, or adjustment applied to a transaction. Understanding how to structure and name them keeps your billing transparent, your subscribers informed, and your data compliant.
  </div>

  <div class="rp-plan"><i class="fa fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>

  ### Prerequisites

  <ul class="rp-list">
    <li>Line items can be named freely but should avoid special characters unless confirmed with your payment gateway.</li>
  </ul>

  ### Limitations

  <ul class="rp-list">
    <li>Invoices display only the first 500 line items in the Admin Console, Hosted Invoice, and PDF views. Subtotals, taxes, and totals always reflect the full set. To access all line items beyond the first 500, use the <a href="https://docs.recurly.com/docs/adjustments-exports" target="_blank">Adjustments Export</a>.</li>
  </ul>

  <nav class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span> Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span> Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span> Key details</a>
  </nav>

</div>

# Definition

<div class="rp-definition">
  Line items are individual charges or components listed on an invoice, each representing a product, service, or adjustment applied to a transaction. They can be associated with subscriptions or exist as stand-alone charges — and they appear across the Admin Console, PDF invoices, Hosted Invoice pages, and Hosted Account Management.
</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon">✦</div>
    <strong>Clear billing breakdown</strong>
    <span>Itemizes every charge on an invoice so subscribers always know exactly what they're paying for.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon">✦</div>
    <strong>Stand-alone charge support</strong>
    <span>Line items don't need to be tied to a subscription — they can be invoiced independently for one-off charges.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon">✦</div>
    <strong>Displayed across channels</strong>
    <span>Visible in the Admin Console, PDF invoices, Hosted Invoice pages, and Hosted Account Management — no matter how your subscribers view their bills.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon">✦</div>
    <strong>Payments compliance</strong>
    <span>Accurate, descriptive line items support lower interchange rates through L2/L3 data programs and are sent to gateways in cases like Klarna usage.</span>
  </div>
</div>

# Key details

## Invoice line items

Every invoice line item displays the following columns:

- **Date**
- **Description**
- **Quantity**
- **Price**
- **Discount** (when applied)
- **Subtotal**
- **Tax** (including rate, when applicable)
- **Total** (only shown if tax is applied)

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa fa-info-circle" aria-hidden="true"></i> Note</strong> Invoices in the Admin Console, Hosted Invoice page, and PDF format show only the first 500 line items. However, the <strong>Subtotal</strong>, <strong>Tax</strong>, and <strong>Total</strong> always reflect all line items — including those beyond the first 500. To download the full set, use the <a href="https://docs.recurly.com/docs/adjustments-exports" target="_blank">Adjustments Export</a>.</div>
</div>

## Description and naming guidelines

Well-named line items matter beyond readability. They're required for Commercial Enhanced Data Program (CEDP) compliance — a Visa program (updated in 2025) that validates L2/L3 transaction data and rewards compliant merchants with reduced interchange rates. Line items are also sent to gateways in certain cases, such as Klarna transactions.

If your gateway is not HIPAA-compliant, do not include protected health information (PHI) in invoice descriptions, product codes, plan names, or line item data.

<Cards columns={4}>
  <Card title="Be specific" icon="fa-check-circle">
    Use clear, descriptive names rather than generic labels like "Item 1" or "Charge."
  </Card>
  <Card title="Match the product" icon="fa-apple-alt">
    If you sell fruit, list "Apple," "Orange," and "Banana" rather than "Fruits."
  </Card>
  <Card title="Avoid business names" icon="fa-building">
    Don't repeat your company name in item names or descriptions — for example, "Fruit Shop Items."
  </Card>
  <Card title="Skip single-character names" icon="fa-font">
    Avoid names that are a single character or all symbols — they confuse customers and fail compliance checks.
  </Card>
  <Card title="Where descriptions appear" icon="fa-file-invoice">
    Subscriber invoices, Hosted Account Management pages, and Hosted Invoice PDFs.
  </Card>
  <Card title="Character limit" icon="fa-text-width">
    Descriptions must be 255 characters or fewer.
  </Card>
  <Card title="Special character tip" icon="fa-info-circle">
    Check with your payment gateway about any restrictions on special characters before using them in names or descriptions.
  </Card>
</Cards>