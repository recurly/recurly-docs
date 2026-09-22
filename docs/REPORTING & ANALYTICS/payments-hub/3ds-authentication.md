---
title: 3DS Authentication
excerpt: >-
  See how your payments perform through 3D Secure authentication and the
  issuer's final decision, broken out by outcome, gateway, and country.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page"> <div class="rp-overview">The 3DS Authentication dashboard shows you how your payments move through 3D Secure (3DS) — and what happens after. It lives in Payments Hub alongside the other payments analytics you already use. It's especially useful if you're on a gateway integrated through Hyperswitch, where 3DS activity doesn't show up in the gateway's own reporting at all.</div> <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div> <div class="rp-card">

</div> <div class="rp-toc"> <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a> <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a> <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a> <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">4</span>FAQs</a> </div> </div>

# Limitations

<ul class="rp-list"> <li>The dashboard shows 3DS outcomes on individual transactions. It doesn't yet show how 3DS authentication on an initial checkout affects the approval rate of later recurring charges — that comparison is planned for a future release.</li> <li>A frictionless-versus-full-challenge breakdown isn't available yet, since not all gateways report that distinction consistently.</li> </ul>

# Definition

<div class="rp-definition">Every card payment that requires Strong Customer Authentication (SCA) resolves to one of three states: approved, declined, or declined with a 3DS requirement. The 3DS Authentication dashboard tracks what happens from that point on — whether the customer completed the 3DS challenge, which of eight outcome categories the attempt landed in, and, separately, whether the bank ultimately approved or declined the payment. Those are two different things: a payment can authenticate successfully through 3DS and still be declined by the issuing bank, and this dashboard keeps that distinction visible instead of collapsing it into a single pass/fail number.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2"> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>See your SCA exposure at a glance</strong> <span>Track how many of your transaction attempts are being challenged for 3DS and how that rate trends over time.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Tell 3DS problems apart from bank declines</strong> <span>The gateway and country grids separate authentication outcomes from the issuer's final decision, so you can see exactly where a payment is lost — during 3DS, or after.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Get full coverage on Hyperswitch gateways</strong> <span>If you're on Checkout.com or Nuvei through Hyperswitch, this dashboard is your only source for 3DS analytics, since those gateways don't report 3DS events themselves.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Drill into gateway and country performance</strong> <span>Compare completion and approval rates across your gateways and markets to find where 3DS is costing you the most revenue.</span> </div> </div>

# Key details

## <br />Accessing the dashboard

The 3DS Authentication dashboard is a new, read-only page under Analytics > Payments Hub in Recurly Admin. It requires no setup — if your account processes 3DS transactions, the dashboard is available to you automatically.

## Filters

All metrics, trends, and grids respond to the filters at the top of the dashboard:

<ul class="rp-list"> <li><strong>Date range</strong> — the period the dashboard reports on.</li> <li><strong>Country</strong> — cardholder country.</li> <li><strong>Gateway</strong> — the payment gateway processing the transaction.</li> <li><strong>Currency</strong> — transaction currency.</li> <li><strong>Initiated by</strong> — customer-initiated (CIT) or merchant-initiated (MIT) transactions. Defaults to Customer Initiated.</li> <li><strong>Card brand</strong> — for example, Visa or American Express. Defaults to any value.</li> </ul> <div class="rp-callout rp-callout-note"> <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Use the Initiated by filter to check whether renewal payments (MIT) are being challenged for 3DS when they shouldn't be.</div> </div>

## 3DS challenges and completions

At the top of the dashboard, two metrics summarize your overall 3DS activity:

<ul class="rp-list"> <li><strong>3DS challenges</strong> — how many of your transaction attempts were challenged for 3DS, and what share of total attempts that represents, with a daily trend. This count is inferred as the sum of the eight outcome categories described below, since there's no single direct counter for it.</li> <li><strong>3DS completions</strong> — how many of those challenges returned a 3DS result (rather than going unanswered), and the completion rate as a share of challenges, with a daily trend.</li> </ul>


<Image src="https://files.readme.io/13a8c9598802d5af22f124f7403f01b9a34d93c56457efa6338cd608deb717fc-image.png" align="center" border={true} />


## 3DS outcome breakdown

Every 3DS challenge resolves to exactly one of eight categories. Six are result states returned when a 3DS check completes; two are decline reasons used when no result comes back at all. Together, the eight always add up to 100% of your challenges.


<Image src="https://files.readme.io/fdf61ccd3a60ae6d53d4b344a296793508234b1e90404e17767928b76e27be42-image.png" align="center" border={true} framed={true} />


<table class="rp-params"> <tr class="rp-thead-row"><td>Category</td><td>Type</td><td>What it means</td></tr> <tr><td>Authenticated</td><td>3DS result</td><td>The 3DS check passed, and a result was returned.</td></tr> <tr><td>Exempted</td><td>3DS result</td><td>3DS was exempted — for example, a granted exemption or a recurring/MOTO transaction — and a result was still recorded.</td></tr> <tr><td>Attempt acknowledged</td><td>3DS result</td><td>The issuer acknowledged the attempt without fully authenticating it — a partial pass.</td></tr> <tr><td>Failed</td><td>3DS result</td><td>The 3DS check ran and didn't pass.</td></tr> <tr><td>Processing error</td><td>3DS result</td><td>A technical error occurred during the 3DS check. This isn't the customer's fault.</td></tr> <tr><td>Not supported</td><td>3DS result</td><td>3DS wasn't supported for this card or issuer.</td></tr> <tr><td>3DS action required</td><td>3DS decline reason</td><td>Declined because 3DS was required but never completed, and no result was returned.</td></tr> <tr><td>3DS technical error</td><td>3DS decline reason</td><td>Declined because of a technical error during authentication, with no usable result returned.</td></tr> </table>

Each category shows a count, its share of challenges, and how it's trending versus the prior period.

## Gateway and country detail

Two grids break performance down by where the payment ran — Gateway detail and Country detail — using the same set of columns:


<Image src="https://files.readme.io/617574a26567b6d5c9892667a19f0096cf9b854cf4b4a23f623dd364253ff394-image.png" align="center" border={true} />


<br />


<Image src="https://files.readme.io/5e874c383fc1921552a67821340e50e98898ec24e89cc7f78cb13c422f59b4a3-image.png" align="center" border={true} />


<table class="rp-gw-table"> <tr class="rp-thead-row"><td>Column</td><td>What it shows</td></tr> <tr><td>Completed</td><td>Challenges that returned a 3DS result.</td></tr> <tr><td>Approved</td><td>Completed transactions the bank approved.</td></tr> <tr><td>Declined</td><td>Completed transactions the bank declined.</td></tr> <tr><td>Voided</td><td>Completed transactions the bank voided.</td></tr> <tr><td>Approval rate</td><td>Approved ÷ (approved + declined). Voided and pending transactions are excluded.</td></tr> <tr><td>Authenticated but declined</td><td>Transactions that passed 3DS authentication but were still declined by the bank.</td></tr> <tr><td>Authenticated decline rate</td><td>Authenticated-and-declined ÷ (authenticated and either approved or declined).</td></tr> <tr><td>Not completed</td><td>Challenges that never returned a 3DS result.</td></tr> <tr><td>Not completed rate</td><td>Not completed ÷ (completed + not completed).</td></tr> </table> <div class="rp-callout rp-callout-note"> <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The three rate columns use different denominators, so they won't add up to 100% — each one is answering a different question about your funnel.</div> </div>

### 3DS outcome versus bank decision

These grids exist because 3DS success and the bank's decision are two separate things. A transaction can authenticate cleanly through 3DS and still be declined by the issuing bank for reasons that have nothing to do with authentication — insufficient funds, fraud rules, or card restrictions, for example. When you see a high authenticated decline rate for a gateway or country, that's a bank-side issue to investigate with your acquirer or issuer, not a 3DS problem.

<div class="rp-callout rp-callout-note"> <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>If you process through Checkout.com or Nuvei via Hyperswitch, your 3DS challenge is delivered through Recurly.js using JusPay's white-labeled 3DS service rather than the gateway's native flow. Your checkout experience isn't affected, but this dashboard is your authoritative source for 3DS data on those gateways — the gateway's own reporting won't show it.</div> </div>

### Zero-state

If your account has no 3DS activity in the selected date range, the dashboard shows a message instead of empty charts and grids, so you know there's nothing to troubleshoot.

## FAQs

<Accordion title="Why does my 3DS challenge count say 'inferred'?">
  There's no single counter that directly tracks 3DS challenges. Instead, the dashboard calculates it as the sum of all eight outcome categories — the six 3DS result states plus the two 3DS-specific decline reasons. We label it as inferred so it's clear how the number is derived.
</Accordion>

<Accordion title="Why don't the three rate columns in the gateway and country grids add up to 100%?">
  Each rate uses a different denominator. Approval rate compares approved to approved-plus-declined. Authenticated decline rate looks only at authenticated transactions. Not-completed rate compares completed to completed-plus-not-completed. They answer three different questions, so there's no reason for them to sum to one total.
</Accordion>

<Accordion title="My gateway shows no 3DS data of its own — is that a bug?">
  Not if you're on Checkout.com or Nuvei through Hyperswitch. Recurly runs your 3DS challenge through JusPay's white-labeled service and delivers it via Recurly.js, so the gateway itself never sees the 3DS event. This dashboard is the authoritative source for that data.
</Accordion>

<Accordion title="What's the difference between 'Failed' and '3DS action required'?">
  Failed means the 3DS check ran and the issuer didn't approve it — you got a result. 3DS action required means no result ever came back at all, usually because the challenge screen never rendered or the customer didn't complete it. Both end in a decline, but only one of them reflects an actual 3DS outcome.
</Accordion>

<Accordion title="Can I see how 3DS on a customer's first purchase affects later renewal approvals?">
  Not yet. Recurly stores the Network Transaction ID (NTID) from the original customer-initiated transaction and links it to later merchant-initiated renewals, which will make that comparison possible in a future release.
</Accordion>
