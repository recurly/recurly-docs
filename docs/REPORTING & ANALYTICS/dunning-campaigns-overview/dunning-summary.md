---
title: Dunning summary
excerpt: >-
  See how Recurly's dunning mechanisms recover revenue from declined
  transactions, broken down by recovery method.
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
  <div class="rp-overview">The Dunning Summary dashboard shows how Recurly recovers revenue from declined transactions. It brings together the tools that reduce payment failures and improve your collection rates, so you can see exactly where your dunning strategy is working.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#recovered-revenue"><span class="rp-toc-num">3</span>Recovered revenue</a>
    <a class="rp-toc-pill" href="#dunning-recovery"><span class="rp-toc-num">4</span>Dunning recovery</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have the Analytics user role permission.</li>
</ul>

# Definition

<div class="rp-definition">The Dunning Recovery dashboard shows how Recurly recovers revenue from declined transactions. It gives you the tools you need to reduce payment failures and improve your collection rates.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Effectiveness</strong>
    <span>See how effective your dunning strategy is at recovering failed invoices.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Insights</strong>
    <span>Gain insight into how your dunning recovery rate is trending over time.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Actionable reporting</strong>
    <span>Track recovered revenue and invoice counts by recovery method, so you know exactly where to focus your efforts.</span>
  </div>
</div>

# Recovered revenue

## Recovered revenue KPI

These indicators give you a real-time snapshot of your revenue dynamics. They help you measure the effectiveness of your dunning recovery strategies by comparing your current payment amounts with totals from last month, the month before, three months ago, and a year ago — so you can identify trends, track progress, and proactively manage involuntary churn.

## Dunning recovery chart

This bar chart visualizes the revenue Recurly has helped you recover by minimizing involuntary churn from declined invoices, giving you an at-a-glance view of the financial impact of Recurly's services for forecasting and resource allocation. These charts display as either total revenue saved or a count of invoices recovered.

## Dunning recovery detail

This breakdown shows the amount recovered through each process — Account Updater, Customer Updates, Intelligent Retries, and Manual Collection — so you can see which tools are most effective and focus your efforts on the most productive areas. These charts display as either total revenue saved or a count of invoices recovered.

# Dunning recovery

The Dunning Recovery dashboard gives you a detailed view of the revenue you've successfully recaptured through Recurly's dunning system. It's a focused part of the broader Recovered Revenue dashboard, concentrating on invoices that fail their initial payment attempt and subsequently enter dunning. The dashboard draws on several recovery methods to maximize the collection of payments.

## Recovery methods

<ul class="rp-list">
  <li><strong>Account Updater</strong> — Proactively updates credit card information ahead of subscription renewals, one-time invoice payments, or re-subscription attempts that would otherwise result in a hard decline, keeping payment details current and minimizing failed transactions.</li>
  <li><strong>Customer updates (dunning)</strong> — Prompts customers to update their payment method after a failed transaction, through dunning emails or other integrated notifications, helping you recover potential lost revenue.</li>
  <li><strong>Intelligent Retries</strong> — Uses data-driven timing and logic to optimize retry attempts, converting failed payments into successes and reducing involuntary churn.</li>
  <li><strong>Forced collection</strong> — Lets merchants manually initiate a collection attempt on a past-due invoice when automated processes don't succeed.</li>
  <li><strong>Manual</strong> — Any manually created invoice that entered dunning and was successfully recovered, including collection attempts merchants make directly on a failed invoice.</li>
  <li><strong>Other</strong> — Invoices recovered through any other method not listed above, including expiration date forwarding on retries and external recoveries.</li>
</ul>

By understanding these dunning recovery features, you can maximize their use and significantly reduce involuntary churn, strengthening your revenue recovery.

## Dunning summary


<Image src="https://files.readme.io/c2e70156cae6ce44ef88fb0225b46ead2728dd589f8c7cb400506d1f6378221b-image.png" align="center" width="75%" border={true} />


## Recovered invoice revenue


<Image src="https://files.readme.io/f20b9b50d38201cf173ed03cfcc0637abf10da1da43d31a83f966a6da04ec4da-image.png" align="center" width="75%" border={true} />


## Recovered invoice counts


<Image src="https://files.readme.io/21b1a96dc44c09e9309007d79c1a7c0be7016ad498b7bc995598084590ce3b1c-image.png" align="center" width="75%" border={true} />


***

📋 TODO before publishing:

- [ ] **Recovery methods list reconciled** — The source gave two lists of dunning recovery categories: one with 6 items (including "Forced Collection" and "Manual" as separate entries) and one with 5 more detailed items (using "Manual Collection" instead). I merged these into a single 6-item list; please confirm "Forced Collection" and "Manual" are meant to be distinct categories and not overlapping descriptions of the same thing.
- [ ] **Key benefits** — Source only provided 2 benefits (Effectiveness, Insights); I drafted a third ("Actionable reporting") to meet the 3-benefit minimum. Please confirm, refine, or replace.
- [ ] **Empty image removed** — The source included a stray `![]()` with no image URL at the end of the page; it's been dropped. Add it back with a real source if there's a missing screenshot.
