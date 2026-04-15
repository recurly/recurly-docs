---
title: Expired card management
excerpt: >-
  Automate the management of expired cards to boost revenue, reduce churn, and
  enhance subscriber experiences.
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

### Limitations

* The success rate of automatic card updates may vary based on the card issuer and network
* Not all credit cards support automatic updates

***

# Definition

Expired Card Management is a Recurly feature that proactively handles expired credit card details to prevent subscription renewals from failing. Rather than waiting for a transaction to decline, Recurly temporarily extends the expiration date on cards approaching expiry — giving subscribers time to update their details without any service disruption.

***

# Key benefits

* **Uninterrupted subscriber experience:** Subscribers keep access to their services without needing to manually update card details.
* **Reduced involuntary churn:** Fewer subscription lapses caused by expired cards means more revenue retained.
* **Revenue protection:** Prevent transaction failures from turning into lost revenue.
* **Recovery insights:** Track the effectiveness of the feature through the Recovered Revenue dashboard in Analytics.

***

# Key details

## How it works

When a credit card is set to expire before an upcoming billing cycle, Recurly temporarily extends the expiration date on file. This reduces the likelihood of hard declines at renewal and gives subscribers a window to update their card details before any service interruption occurs.

This approach is intentionally distinct from [Account Updater](https://docs.recurly.com/docs/account-updater) — rather than automatically replacing card data, Recurly selects a future expiration date to keep the transaction path open. This avoids confusion between the two services and prevents potential conflicts with card network updates.

## Setup

No setup is required. Expired Card Management applies to all accounts automatically once your site is in production.

## Monitoring recovered revenue

You can track how much revenue Expired Card Management has preserved directly in the Recurly Admin Console.

1. Navigate to **Analytics → Churn Management**

<Image align="center" border={true} width="30%" src="https://files.readme.io/923e69675ea298398d1a5765cfa10f7a6ee9978880fea7320649833e1952a036-image.png" className="border" />

2. Open the **Recovered Revenue** dashboard to view the impact of expired card management over time

<Image align="center" border={true} width="75%" src="https://files.readme.io/b42da2c011c01b0cb7cead9274f8c0cad6a47f7bd0b066123402fc0252967248-image.png" className="border" />

Use these metrics to understand recovery rates, identify patterns in card expiration behavior, and refine your broader churn management strategy.

***

# FAQs

**How does Recurly handle expired credit cards?**

Rather than automatically replacing card data, Recurly temporarily extends the expiration date on expiring cards. This reduces the chance of payment failures and hard declines at renewal, while avoiding any overlap or confusion with Account Updater services.

**How does this feature reduce involuntary churn?**

Involuntary churn happens when outdated payment details cause transactions to fail. By keeping expiring cards active through the renewal window, Recurly reduces the number of failed transactions — and the subscriber losses that follow.

**Can I measure the revenue recovered through Expired Card Management?**

Yes. The Recovered Revenue dashboard in Recurly's Analytics section shows recovery rates and the revenue preserved through both expired card management and retry logic, giving you a clear picture of the feature's impact.
