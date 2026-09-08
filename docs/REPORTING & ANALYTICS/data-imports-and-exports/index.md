---
title: Data imports and exports
excerpt: >-
  Unlock the full potential of your Recurly data through comprehensive data
  imports and exports; a pivotal tool in achieving data-driven insights and
  business intelligence.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">The Data imports and exports section covers how to bring data into your Recurly account and how to export detailed reports across your business — from customer records and subscriptions to invoices, coupons, transactions, and revenue recognition. Use it to populate your account, analyze performance and customer behavior, and keep records for compliance.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">1</span>Key benefits</a>
    <a class="rp-toc-pill" href="#in-this-section"><span class="rp-toc-num">2</span>In this section</a>
    <a class="rp-toc-pill" href="#available-exports"><span class="rp-toc-num">3</span>Available exports</a>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong> Exporting data requires the Analytics user role. Exports are available through the admin console and the Recurly API.</div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Comprehensive insight</strong>
    <span>Pull from a wide range of reports to support data-driven decisions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-download" aria-hidden="true"></i></div>
    <strong>Ease of access</strong>
    <span>Straightforward import and export flows for hassle-free data management.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Customization</strong>
    <span>Tailor reports to your business with a range of filters and options.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Automation</strong>
    <span>Schedule automated exports to streamline reporting and save time.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-shield" aria-hidden="true"></i></div>
    <strong>Compliance & record-keeping</strong>
    <span>Keep detailed records for compliance and reference, including external invoices and revenue recognition schedules.</span>
  </div>
</div>

# In this section

<div class="rp-nav-grid">

<Cards>
  <Card title="Customer data imports" href="https://docs.recurly.com/recurly-subscriptions/docs/customer-imports" target="_blank">
    Import customer data to populate accounts and records across your Recurly account.
  </Card>
  <Card title="Data exports" href="https://docs.recurly.com/recurly-subscriptions/docs/export-overview" target="_blank">
    How to retrieve exports, what each report contains, and tips for using them.
  </Card>
  <Card title="Automated exports" href="https://docs.recurly.com/recurly-subscriptions/docs/automated-exports" target="_blank">
    Schedule and manage exports through the Recurly API to save manual effort.
  </Card>
  <Card title="Custom exports" href="https://docs.recurly.com/recurly-subscriptions/docs/custom-export" target="_blank">
    Build tailored exports that return exactly the fields your business needs.
  </Card>
</Cards>
</div>

# Available exports

## Accounts & billing

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/accounts-export" target="_blank">Accounts</a> — account-level information.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/account-notes-export" target="_blank">Account notes</a> — notes created on accounts.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/adjustments-exports" target="_blank">Adjustments</a> — charge and credit adjustments, with tax broken down by jurisdiction.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/adjustments-coupons" target="_blank">Adjustments — coupons</a> — adjustments broken out by discount per coupon redemption.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/adjustments-taxes-export" target="_blank">Adjustments — taxes</a> — taxes calculated through Vertex and Avalara for Communications (AFC).</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/billing-info-export" target="_blank">Billing info</a> — billing information associated with accounts.</li>
</ul>

## Coupons

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons-export" target="_blank">Coupons</a> — all coupons set up on the site.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons-redemption" target="_blank">Coupon redemptions</a> — all redemptions of coupons.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/coupons-bulk-unique-codes" target="_blank">Coupons — bulk unique codes</a> — all unique codes for a bulk coupon.</li>
</ul>

## Payments & credits

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/credit-payments-export" target="_blank">Credit payments</a> — use of outstanding credit balances to pay invoices.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/transaction-export" target="_blank">Transactions</a> — data sent to the gateway when processing a transaction.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/gift-cards-export" target="_blank">Gift cards</a> — all purchased gift cards.</li>
</ul>

## Invoices

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/accounts-receivable-export" target="_blank">Invoices — accounts receivable</a> — aging report of all unsettled receivables.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/invoices-external" target="_blank">Invoices — external</a> — invoices for subscriptions created on third-party platforms.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/invoices-summary" target="_blank">Invoices — summary</a> — invoice header information and summary totals.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/invoices-unused-numbers" target="_blank">Invoices — unused numbers</a> — invoice numbers not used for generated invoices.</li>
</ul>

## Items & products

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/items-associated-plans" target="_blank">Items — associated plans</a> — plan add-ons created from a saved item.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/items-associated-subscriptions" target="_blank">Items — associated subscriptions</a> — subscription add-ons created from a saved item.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/products-catalog-export" target="_blank">Product catalog</a> — all product offerings, add-ons, and items, active or inactive.</li>
</ul>

## Subscriptions

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-exports" target="_blank">Subscriptions</a> — your customers' subscriptions to your plans.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-add-ons-export" target="_blank">Subscription add-ons</a> — detailed information on subscription add-ons.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-add-ons-history-export" target="_blank">Subscription add-ons — history</a> — changes made to a subscription add-on over time.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-churned" target="_blank">Subscriptions — churned</a> — subscriptions that have expired and are no longer active.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-external" target="_blank">Subscriptions — external</a> — external subscriptions stored on third-party platforms.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-history-export" target="_blank">Subscriptions — history</a> — every version created following a change to a subscription.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscriptions-pending-changes-export" target="_blank">Subscriptions — pending changes</a> — active subscriptions with a change pending at renewal.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/subscription-ramp-pricing-export" target="_blank">Subscriptions — ramp pricing</a> — subscriptions on a ramp-priced billing model.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/usages-records-export" target="_blank">Subscriptions — usage records</a> — usage logged for usage-based subscription add-ons.</li>
</ul>

## Revenue recognition

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Sunset</strong> The <a href="https://docs.recurly.com/recurly-subscriptions/docs/revenue-recognition-export" target="_blank">Revenue recognition schedules export</a> was sunset on October 31, 2025 and is now read-only. For revenue recognition going forward, see <a href="https://docs.recurly.com/recurly-revrec/docs/recurly-revenue-recognition-standalone" target="_blank">Recurly Revenue Recognition Standalone</a>.</div>
</div>

## Site & users

<ul class="rp-list">
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/account-activities-export-an" target="_blank">Account activities</a> — account activity records.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/site-activities-export-an" target="_blank">Site activities</a> — site activity records.</li>
  <li><a href="https://docs.recurly.com/recurly-subscriptions/docs/users-export-an" target="_blank">Users</a> — user information for your site.</li>
</ul>

{/*
📋 TODO before publishing:
- [x] Links verified against the live left-nav and the Reporting & Analytics section index (docs.recurly.com/recurly-subscriptions/docs/...). All 35 import/export slugs confirmed current. Note "customer-imports" (not "customer-data-imports"), and the activities/users exports use the "-an" variants that live under the Data exports tree.
- [ ] Added current export pages that weren't in the draft: Custom exports, Account activities, Site activities, Users. Remove any you don't want listed here.
- [ ] "Dashboards & reports" — the draft listed this, but it isn't part of the Data imports and exports tree in the live IA. Omitted; add a link if one was intended.
- [ ] "Account acquisition data export" — the draft listed this with no link, and there's no dedicated export page in the current structure. Omitted; confirm the intended target (the account-acquisition-data feature page, or coverage inside the Accounts export).
- [ ] Revenue recognition export — verified the slug resolves, but the page was sunset 2025-10-31 (read-only, noindex, replaced by RevRec Standalone). Now shown as a sunset callout rather than a current export. Remove entirely if you'd rather not surface it.
- [ ] Deprecated "Invoices" export — export-overview flags a deprecated combined Invoices export replaced by Invoices — Summary and Adjustments. Left out intentionally; add under a "Deprecated" note if you want it visible.
*/}
