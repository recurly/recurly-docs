---
title: LATAM Credit Card integration guide
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  title: LATAM Card Processing & Integration Guide | Recurly
  description: >-
    Accept credit cards across Argentina, Brazil, Mexico, and 10+ LATAM markets
    with Recurly's EBANX integration. Setup guides, API docs, and best
    practices.
  keywords:
    - LATAM card processing
    - EBANX credit card integration
    - WorldPay credit card integration
    - Argentina/Brazil/Mexico card acquiring
    - Recurly LATAM subscriptions
  robots: index
---
# Overview

This guide shows you how to use the [Purchase endpoint](https://developers.recurly.com/api/latest/#tag/purchase) to create new subscriptions using a credit card on Ebanx or WorldPay in the LATAM region.&#x20;

### Prerequisites & limitations

* Familiarity with Recurly’s API  and basic REST concepts
* Familiarity with our 3DS guides:
  * [3D Secure for new cards](https://docs.recurly.com/recurly-subscriptions/docs/3d-secure-20-integration-guide#/)
* [Completed the Quickstart Guide](https://docs.recurly.com/recurly-subscriptions/docs/quick-start-guide#/)
* An Ebanx or WorldPay (WPG) gateway account with credit cards and 3DS enabled in the LATAM region
* Familiarity with our tax integrations, specifically Vertex or Avalara.

### Required and recommended fields&#x20;

* Full first and last name information, billing address, and email for your customer
* In certain regions the Tax ID and Date of Birth of the customer are required. You can use Recurly's API to pass the data to the gateway, and we will store it for renewals and return customer transactions.

***

# Definition

**Creating Purchases** refers to the process of generating new customer accounts alongside subscriptions in a single, consolidated call to the Recurly Purchase endpoint. This streamlines checkout experiences by bundling all required resources into one request.

This is necessary for LATAM regional compliance due to the 3DS requirement for customer-initiated requests. All Subscription Signup requests from Recurly's APIs are customer initiated.

# LATAM Requirements

When processing cards in LATAM, customer tax IDs and birthdates are conditionally required. You will also need to integrate a tax service to handle compliance and region-specific taxation in certain cases.&#x20;

<br />

***

# Creating Purchases

## Step 1: Generate a credit card subscription signup

<br />

<br />

<br />

<br />

<br />
