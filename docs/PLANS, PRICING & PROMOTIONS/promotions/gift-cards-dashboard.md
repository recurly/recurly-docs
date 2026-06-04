---
title: Gift cards dashboard
excerpt: >-
  Use the Gift Cards dashboard to search, view, and manage gift card
  transactions — including status filtering, delivery edits, and exports.
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
  <div class="rp-overview">
    The Gift Cards dashboard is your central hub for locating and managing all gift card activity. Search by redemption code, gifter name, or recipient name — then drill into any card for full transaction details, delivery management, and cancellation controls.
  </div>

  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available when the Gift Cards feature is activated</div>

  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#dashboard"><span class="rp-toc-num">3</span>Dashboard</a>
    <a class="rp-toc-pill" href="#gift-card-details"><span class="rp-toc-num">4</span>Gift card details</a>
    <a class="rp-toc-pill" href="#exports"><span class="rp-toc-num">5</span>Exports</a>
    <a class="rp-toc-pill" href="#image-test"><span class="rp-toc-num">6</span>Image test</a>
  </div>
</div>

# Definition

<div class="rp-definition">
  The Gift Cards dashboard in Recurly provides a centralized interface for managing all gift card transactions. From here you can track purchases, redemptions, and balances — and take action on individual cards without leaving the Admin Console.
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-table-list" aria-hidden="true"></i></div>
    <strong>Centralized management</strong>
    <span>Track every gift card from purchase through redemption in one place, with status filters that surface exactly what you need.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-heart" aria-hidden="true"></i></div>
    <strong>Enhanced customer engagement</strong>
    <span>Gift cards are a flexible, popular option for customers. This dashboard makes it fast to support them — editing delivery details or resending emails in seconds.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Real-time insights</strong>
    <span>See up-to-date gift card usage and trends to inform marketing and operational decisions.</span>
  </div>
</div>

# Dashboard


<Image src="https://files.readme.io/c5a25d6-image.png" align="center" width="75%" border={true} framed={true} />


Navigate to **Customers → Gift Cards** to access the dashboard. Search for any gift card using the redemption code, gifter's name, or recipient's name.

## Gift card status

Use the status filter to narrow results by the current state of each card.


<Image src="https://files.readme.io/22b16b5-image.png" align="center" width="50%" border={true} framed={true} />


<table class="rp-pm-table">
  <tr class="rp-thead-row">
    <td>Status</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>All</td>
    <td>Displays all gift cards regardless of status.</td>
  </tr>
  <tr>
    <td>Not yet redeemed</td>
    <td>Gift cards issued but not yet used by the recipient.</td>
  </tr>
  <tr>
    <td>Redeemed</td>
    <td>Gift cards that have been used by the recipient.</td>
  </tr>
  <tr>
    <td>Has balance remaining</td>
    <td>Gift cards that are partially used but still have a balance.</td>
  </tr>
  <tr>
    <td>No balance remaining</td>
    <td>Gift cards that have been fully used with no remaining balance.</td>
  </tr>
  <tr>
    <td>Canceled</td>
    <td>Gift cards that have been canceled and are no longer valid.</td>
  </tr>
</table>

# Gift card details


<Image src="https://files.readme.io/54081b0-image.png" align="center" width="75%" border={true} framed={true} />


Select a gift card from the list and click its redemption code to open the detail view. From here you can see all associated information for that card.


<Image src="https://files.readme.io/6072a05-image.png" align="center" width="75%" border={true} framed={true} />


Clicking the gifter's name navigates to their account. Clicking the purchase invoice number opens the invoice view.

## Edit delivery information

Click **Edit Details** to modify delivery information. Update the necessary fields and save your changes.

## Resend delivery email

Click **Resend Delivery Email** to resend the gift card delivery email to the recipient. Verify the information and click **Send** to complete.

## Cancel gift card

To cancel the gift card, click **Cancel Gift Card** in the upper-right menu.

# Exports

For full details on available fields and export configuration, see the <a href="https://docs.recurly.com/docs/gift-cards-export" target="_blank">Gift Cards exports</a> page.

# Image test

This section tests native `<Image>` rendering inside a callout and as a standalone image.

<div class="rp-callout rp-callout-note">
<strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Test callout</strong>

This is a dummy callout to test whether a native Image component placed immediately after renders correctly inside and adjacent to a custom rp-\* component.

</div>


<Image src="https://files.readme.io/c5a25d6-image.png" align="center" width="75%" border={true} framed={true} />


<br />
