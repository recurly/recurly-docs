---
title: iDEAL
excerpt: >-
  Navigate through the seamless integration of iDEAL, the predominant online
  payment method in the Netherlands, into your Recurly checkout flow, offering
  your customers a familiar and trusted payment platform while enhancing your
  business prospects in the region.
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

<Callout icon="📘" theme="info">
  i**Deal | Wero Logo Update**

  Prior to March 31st, 2026, Recurly will be updating all visible logos in our platform to display iDeal's new branding combination of "iDeal | Wero". You will see your integrations automatically update depending on which platform you are using (Adyen or Stripe), as well as logos inside the Recurly admin portal for billing infos, Recurly Wallet, and transaction details and reporting.

  There are no integration changes necessary on your end.
</Callout>

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites & supported gateways

* Recurly currently supports iDeal transactions through the [Adyen ](https://docs.recurly.com/docs/adyen) and [Stripe](https://docs.recurly.com/docs/stripe#/) (via [Third Party Checkout](https://recurly.com/developers/guides/3rd-party-checkout.html)) gateways.

* Remember to set up [SEPA ](https://docs.recurly.com/docs/sepa-1)Direct Debit for recurring payments and enable EUR as the currency.

### Limitations

* Free trials: iDEAL cannot facilitate free trials; opt for SEPA Direct Debit in such scenarios.
* Future start date: Subscriptions initiated via iDEAL cannot have a future commencement date.
* Chargeback handling: This feature is unsupported by iDEAL.
* Recurly Checkout and Hosted Payment Pages: iDEAL integration is unavailable on these pages.
* iDEAL payments cannot be reversed.

# Description

iDEAL is the leading online payment method in the Netherlands, accounting for over half of all online transactions in the region. By integrating iDEAL into your Recurly checkout flow, you allow your customers to choose their bank from a list of iDEAL-supported banks, logging into their bank’s website, and concluding their payment there. A demo of this payment flow can be seen [here](https://www.ideal.nl).

It should be noted that while iDEAL can facilitate the initial payment, recurring payments are managed through SEPA, owing to iDEAL’s inability to support recurring transactions. Ensure you have SEPA enabled in order to support this flow.

### Use cases

* One-time payments: Ideal for initial payments of subscriptions.
* Netherlands market: Enhance your market presence by offering the most popular payment method in the Netherlands.

# Checkout flow

Incorporate the iDEAL payment option in your checkout process, directing customers to select their bank from the available list of iDEAL-friendly banks and complete their payment on the bank's official site.
