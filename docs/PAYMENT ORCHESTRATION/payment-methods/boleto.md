---
title: Boleto
excerpt: >-
  Accept Boleto Bancário payments on Recurly via Adyen for the Brazilian market
  — generating barcode invoices payable at ATMs, banks, online banking, or
  retail stores.
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
  <div class="rp-overview">Boleto Bancário is one of Brazil's most widely used payment methods, particularly among customers without bank accounts. Customers receive a barcode invoice they can pay at ATMs, bank branches, online banking, or retail stores. Recurly supports Boleto via Adyen.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#checkout-flow"><span class="rp-toc-num">3</span>Checkout flow</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An <a href="https://docs.recurly.com/docs/adyen#adyen-boleto" target="_blank">Adyen</a> gateway connection with Boleto enabled.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Every Boleto generated via Recurly creates a new invoice.</li>
  <li>Boleto is not a recurring payment method — customers must return to session for every payment. The subscription remains active while the invoice is in a Past Due state until the customer pays.</li>
  <li>Boleto does not support refunds. External refunds must be handled outside of Recurly.</li>
</ul>

# Definition

<div class="rp-definition">Boleto Bancário (Boleto) is a widely used Brazilian payment method that generates a barcode invoice customers can pay at ATMs, bank branches, online banking platforms, or retail stores. It's particularly common among customers without traditional bank accounts. Boleto is a one-time payment method — each transaction requires the customer to actively return and pay the invoice.</div>

# Key details

<div class="rp-card">

### Use cases

**Broader Brazilian customer reach** — Boleto reaches customers without bank accounts or credit cards, expanding your accessible market in Brazil.

**Flexible payment option** — Gives Brazilian customers multiple channels to pay — online or in person — on their own schedule.

**Non-urgent transactions** — Well-suited for transactions where immediate payment confirmation is not required, given Boleto's extended payment window.

</div>

# Checkout flow

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Boleto invoice is generated</h4><p>When a customer selects Boleto at checkout, a Boleto invoice with a barcode is created. The invoice enters a Past Due state immediately and remains there for up to 10 business days.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Customer receives the barcode</h4><p>The customer can view the barcode directly on the checkout page or download the Boleto invoice.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Customer pays the invoice</h4><p>The customer pays the Boleto invoice online (via internet banking) or in person at an ATM, bank branch, or retail store.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Recurly is notified</h4><p>Upon successful payment, Adyen sends a webhook event to Recurly, which marks the invoice as <strong>Paid</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Invoice expires if unpaid</h4><p>If the invoice is not paid within the allowed window, the transaction and invoice move to a Failed state.</p></div>
  </div>
</div>

<br />
