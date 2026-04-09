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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

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

1. Navigate to the [Recurly gateway configuration page](https://app.recurly.com/go/configuration/payment_gateways).

<Image align="center" border={true} width="30% " src="https://files.readme.io/c2627568961fe4b5ed3117049d7e24811e9e4a6a9da228aaeb2ae41fbb7d11e2-image.png" className="border" />

2. Select "Enable" from the Gateway Failover modal on the right.

<Image align="center" border={true} width="50% " src="https://files.readme.io/28bba94d64a5532330afc8ee668481eb7a5275dfb331b78f6148ec3c3351cbdb-image.png" className="border" />

2. Confirm feature enablement on the modal that appears.

<Image align="center" border={true} width="80% " src="https://files.readme.io/7cddbd21bd2cd87e83b4ac8cf59331e087a762162ec5ad9f1973dda69102e782-image.png" className="border" />

### Exclude a Gateway from Failover

1. Go to the [Recurly gateway configuration page](https://app.recurly.com/go/configuration/payment_gateways).
2. Select (1) Options→(2) Edit Gateway on the desired gateway entry to edit.

<Image align="center" border={true} width="80% " src="https://files.readme.io/aba15e1d67cf5cecadafdb82a32e00eb6d64b3af2961cd05c0c99ae0a29e3624-image.png" className="border" />

<Image align="center" border={true} width="30% " src="https://files.readme.io/f523d1bef3731ffa53da799c3af2184be022733bf04966576e418b4e3a989d2e-image.png" className="border" />

3. Check the box for: "**Exclude from Gateway Failover**."

<Image align="center" border={true} width="80% " src="https://files.readme.io/a2aed17cfbeecf9a486970c79a8e8fd784bf0e0ab64c747b3b12863cc31f2f08-image.png" className="border" />

This exclusion is crucial for merchants utilizing [Custom Gateway Routing](https://docs.recurly.com/docs/custom-gateway-routing-configuration) who wish to prevent failover transactions from being routed to a gateway designated for specific purposes.

## Gateway Failover implementation details

* Merchants will be able to [enable](https://docs.recurly.com/docs/gateway-failover#section-enable-gateway-failover) Gateway Failover from their gateway configuration page, by designating a primary and backup gateway for each credit card type and currency. Recurly will default to the first gateway added or set default gateway for the specific card type and currency. Gateway(s) added to the site after will then be used for failover scenarios (prioritizing the earlier addition(s) first).
* Recurly will track gateway error code responses to detect potential outages or downtime, specifically targeting communication error type responses. This will be calculated on a rolling time period.
* When gateway errors are detected and reach a certain velocity, Recurly will failover to the backup gateway, routing transactions to that gateway.
* The calculation will also be able to inform Recurly when the primary gateway has recovered, so Recurly can revert back to the primary gateway.
* Initial signup transactions that were routed to a backup gateway will be initiated as recurring transactions on the primary gateway, even if they were originally routed to the backup gateway.
* Merchants will be notified on their gateway configuration page that a gateway failover scenario was detected and a secondary gateway was used.
* Recurring transactions will be paused, so that these transactions are not attempted on the gateway that is down. When Recurly identifies that the gateway has recovered, Recurly will release the queue of recurring transactions to be routed to the primary gateway.
