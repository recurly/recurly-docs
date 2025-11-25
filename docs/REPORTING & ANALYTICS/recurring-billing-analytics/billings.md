---
title: Billings
excerpt: >-
  This meticulous financial tracker segregates each category over a specified
  timeframe, equipping you with granular insights and the true state of your
  cash flow. Take charge of your financial decisions, decode customer behaviors,
  and shape your revenue strategies with absolute confidence.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites

* Users must have Analytics user role permission.

# Understanding the Billings dashboards

The Billings Dashboard is your guide to understanding payments, refunds, and net billings from all customers. It exclusively displays successful gateway transactions. Other invoice activities (e.g. manual & credit invoices, wire transfers) are not included. This comprehensive tool offers a transparent snapshot of your financial activities over a chosen duration, enabling you to grasp your cash flow, make enlightened decisions, and sculpt potent revenue strategies.

Furthermore, the dashboard's regional breakdown equips you with the specificity needed to tailor your approach by region. Available regional views are:

* Billings (Global)
* Billings (North America)
* Billings (Europe)
* Billings (Asia)
* Billings (South America)
* Billings (Oceania)
* Billings (Africa)

> **Note:** It's essential to note the distinction between a subscriber and a subscription. While a single subscriber might hold multiple active subscriptions, this dashboard focuses on counting the individual subscriber, not the number of subscriptions they possess.
>
> **For additional guidance on navigating and utilizing filter tools, consult our documentation<a href="https://docs.recurly.com/docs/recurly-analytics-overview#navigation-features" target="_blank">here</a>.**

# Billings dashboards

## Billing key performance indicators (KPIs)

<Image align="center" border={true} src="https://files.readme.io/fb1eba6-image.png" className="border" />

A great widget presenting a detailed breakdown of your payment totals to date. Track how current totals compare to last month, the previous month, three months ago, and even one year ago. Arrowheads under each total provide visual representation of how current figures vary from the 'to-date' total.

### Summary

<Image align="center" border={true} width="75% " src="https://files.readme.io/cd99ffa-image.png" className="border" />

A comprehensive visualization that brings together new and renewing customer payments and refunds over your chosen date range. Witness the dynamics of your billing cycle as new transactions come in and refunds go out.

## New vs renewing detail

<Image align="center" border={true} width="75% " src="https://files.readme.io/e73afb2-image.png" className="border" />

The Net Billings Dashboard offers a meticulous comparative analysis, differentiating between net new and net renewing payments. Here's how it works:

* **Net New**: Derived by taking the new payments and subtracting any new refunds.
* **Net Renewing**: Calculated by deducting renewing refunds from renewing payments.  
  The culmination of these two values presents the Total Net Billings.

**For clarity**, within this dashboard:

* “New” refers to the inaugural payment made by a subscriber.
* “Renewing” encompasses any subsequent payments made after the initial one.

## Billing Drills

In the Summary and New vs Renewing detail you can click any bar or number and there are 2 drills  

* “Product Details” provides a summarized view of the invoice line items, including a breakdown of the products that contribute to the total for the selected billing record. Please note that minor differences may occur between this total and the value displayed on the dashboard due to currency conversion and tax-related rounding.  If more details are required there is an additional drill to view the Transaction and Invoice Details on each product total.
* “Transaction and Invoice Details” displays all transactions and their associated invoices that contribute to the total for the selected billing record. All totals are presented in the transaction currency.

## Billings by country

<Image align="center" border={true} width="75% " src="https://files.readme.io/98e77e0-image.png" className="border" />

An expanded version of the 'By state' map, taking the geographical scope to a global level. Click on an individual country to view its total payments. Transactions without an assigned country are grouped together in the 'Amount Unmapped' box below the map. Understand your international reach and uncover areas of untapped potential.

**Note:** The only-Europe map is also available.

## Billings by state

This dashboard provides a geographic representation of payment amounts, organized by state. The location is determined based on the account's billing information or, when that's unavailable, the IP address. It's a straightforward tool for understanding regional revenue distribution.

<Image align="center" border={true} width="60% " src="https://files.readme.io/582ba9a-image.png" className="border" />

The current version focuses on:

* **Billings by State**: Displaying revenue distribution across different states.
* **Billings by Country in Europe**: Showing revenue distribution across European countries.  
  Adjacent widgets display the percentage of Global Billings for each region. Additionally, a tabular breakdown is provided below, listing each country or state within its respective region.

# Use the geographic charts

1. **Interacting with geographic charts:** The Billings Dashboard includes territorial-shaped charts representing different geographical areas. By selecting specific territories on the maps, you can see the total payments, refunds, and net billings for that particular state or country displayed in hover text.
2. **Understanding mapped and unmapped amounts:** Below the geographical maps, you'll find two boxes detailing 'Mapped' and 'Unmapped' amounts. The 'Mapped' box corresponds to transactions that have been assigned to a specific state or country, while the 'Unmapped' box includes transactions with no assigned state or country. This allows you to see not only where your transactions are coming from but also to identify any transactions that might not be categorized correctly.
