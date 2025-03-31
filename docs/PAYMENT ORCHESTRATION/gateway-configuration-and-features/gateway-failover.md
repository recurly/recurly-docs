---
title: Gateway failover
excerpt: >-
  Ensure seamless transaction processing during primary gateway downtimes with
  Recurly's Gateway Failover feature, which automatically routes transactions to
  a backup gateway and reverts back post resolution.
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

![](https://files.readme.io/c688578-Recurly-Gateway-Failover-Routing-Blog.gif "Recurly-Gateway-Failover-Routing-Blog.gif")

### Required plan

This feature is only available on advanced plans. If you’re currently on Pro or Starter, you may need to upgrade your plan to access it. Please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) for more information.

### Prerequisites

* Merchants should have multiple gateways configured for each credit card type and currency they accept.
* Merchants should be on the Recurly's Professional plan to access this feature.

### Limitations

* Transactions tied to a specific gateway via a `gateway_code` will always route to the specified gateway, despite a failover scenario.
* The Auth and Capture feature may not be compatible with Gateway Failover as captures need to be completed on the same gateway as the original authorization.
* If using Stripe with Gateway Failover, ensure that both gateways support the same currency and card type.
* Testing Gateway Failover in sandbox mode is not supported; the feature is functional only in production mode.

# Definition

Gateway Failover is a feature designed to provide a safety net for merchants by automatically routing transactions to a backup gateway whenever there's a detected outage or downtime with the primary gateway. This not only ensures the continuous processing of transactions but also significantly diminishes the financial and operational impact of gateway outages.

# Key benefits

* **Continuity in transactions processing**: Ensures transactions are processed without interruption even during primary gateway outages.
* **Minimized financial impact**: By rerouting transactions, financial losses due to gateway outages are substantially reduced.
* **Operational resilience**: Enhances operational resilience by providing a backup plan for payment processing, thereby maintaining a good customer experience.

# Enable gateway failover

1. Navigate to the [Recurly gateway configuration page](https://app.recurly.com/go/configuration/payment_gateways) and select "Enable" from the Gateway Failover modal on the right.

![Enable Gateway Failover](https://files.readme.io/9e4f0fb-gwr1_revised.png "Enable Gateway Failover")

2. Confirm feature enablement on the modal that appears.

![Confirmation Modal](https://files.readme.io/976d8cc-gwr2_revised.png "Confirmation Modal")

3. A banner indicating successful feature enablement will be displayed on the gateway configuration page.

![Confirmation Banner](https://files.readme.io/6211791-gwr3_revised.png "Confirmation Banner")

### Exclude a Gateway from Failover

**TO EXCLUDE A GATEWAY**, follow these steps:

1. Go to the [Recurly gateway configuration page](https://app.recurly.com/go/configuration/payment_gateways).
2. Select (1) Options > (2) Edit Gateway on the desired gateway entry to edit.

![Exclude Step 1](https://files.readme.io/fd8975b-gwr_exclude_1.png "Exclude Step 1")

3. Check the box for: "**Exclude from Gateway Failover**."

![Exclude Step 2](https://files.readme.io/d66aa88-gwr_exclude_2.png "Exclude Step 2")

This exclusion is crucial for merchants utilizing [Custom Gateway Routing](https://docs.recurly.com/docs/custom-gateway-routing-configuration) who wish to prevent failover transactions from being routed to a gateway designated for specific purposes.

## Gateway Failover implementation details

* Merchants will be able to [enable](https://docs.recurly.com/docs/gateway-failover#section-enable-gateway-failover) Gateway Failover from their gateway configuration page, by designating a primary and backup gateway for each credit card type and currency. Recurly will default to the first gateway added or set default gateway for the specific card type and currency. Gateway(s) added to the site after will then be used for failover scenarios (prioritizing the earlier addition(s) first). 
* Recurly will track gateway error code responses to detect potential outages or downtime, specifically targeting communication error type responses. This will be calculated on a rolling time period. 
* When gateway errors are detected and reach a certain velocity, Recurly will failover to the backup gateway, routing transactions to that gateway. 
* The calculation will also be able to inform Recurly when the primary gateway has recovered, so Recurly can revert back to the primary gateway. 
* Initial signup transactions that were routed to a backup gateway will be initiated as recurring transactions on the primary gateway, even if they were originally routed to the backup gateway.
* Merchants will be notified on their gateway configuration page that a gateway failover scenario was detected and a secondary gateway was used.
* Recurring transactions will be paused, so that these transactions are not attempted on the gateway that is down. When Recurly identifies that the gateway has recovered, Recurly will release the queue of recurring transactions to be routed to the primary gateway.
