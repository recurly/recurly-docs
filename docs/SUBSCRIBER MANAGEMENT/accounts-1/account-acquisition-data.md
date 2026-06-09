---
title: Account acquisition data
excerpt: >-
  Capture and use customer acquisition details in Recurly to measure acquisition
  costs, lifetime value, and marketing channel effectiveness.
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
  <div class="rp-overview">Account acquisition data lets you record key marketing and acquisition details directly on a customer account record in Recurly. By combining acquisition cost data with revenue stored in Recurly, you can measure customer acquisition costs (CAC), calculate lifetime value, and identify which channels and campaigns are driving the most value.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#exports"><span class="rp-toc-num">3</span>Exports</a>
  </div>
</div>

# Definition

<div class="rp-definition">Account acquisition data is a set of fields on the Recurly account record that captures how and at what cost a customer was acquired. When combined with revenue data already in Recurly, these fields give merchants a complete picture of customer acquisition cost (CAC) and lifetime value — without needing to cross-reference external systems manually.</div>

# Key details

## Acquisition fields

The following fields are available on every account record:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
  <tr><td>Cost to acquire a customer</td><td>The total cost incurred through marketing activities to acquire the customer.</td></tr>
  <tr><td>CAC currency</td><td>The currency for the acquisition cost, represented as a 3-letter ISO code.</td></tr>
  <tr><td>Acquisition channel</td><td>The medium through which the customer was acquired (e.g., paid search, organic, referral).</td></tr>
  <tr><td>Acquisition sub-channel</td><td>A flexible field to further detail the acquisition channel.</td></tr>
  <tr><td>Campaign ID</td><td>A unique identifier for the marketing campaign attributed to account conversion. Typically sourced from a marketing automation system and used to measure campaign success.</td></tr>
</table>

## Adding acquisition data

Acquisition data can be submitted <a href="https://developers.recurly.com/api-v2/v2.4/#operation/createAccountAcquisition" target="_blank">via the API</a> or entered manually in the Recurly UI.

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> Using the API is recommended over manual UI entry — it reduces the risk of data entry errors and is faster when integrating data from a marketing automation system at scale.</div>
</div>

When editing an account record in the UI, the acquisition data fields appear as shown below:


<Image src="https://files.readme.io/904f1cd-Screen_Shot_2016-09-07_at_3.33.36_PM.png" align="center" width="75%" border={true} />


Once the account record is updated with acquisition details, the data appears on the right side of the account screen in Recurly. Hover over **Acquisition Data** to view the populated fields.


<Image src="https://files.readme.io/5085df9-Screen_Shot_2016-09-07_at_3.34.03_PM.png" align="center" width="75%" border={true} />


# Exports

Account acquisition data is available through the accounts export in Recurly. See the <a href="https://docs.recurly.com/docs/accounts-export#account_acquisition_cost" target="_blank">account exports page</a> for a full reference of the available fields and how to use them.
