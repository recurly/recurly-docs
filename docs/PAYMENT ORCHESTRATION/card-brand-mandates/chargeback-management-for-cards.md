---
title: Chargeback management for cards
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
> 🚧 Early access
> 
> Chargeback management for cards is available in the early access. Please reach out to [Recurly support](https://support.recurly.com/hc/en-us) or your account manager to enable this feature.

Recurly provides chargeback management capabilities for card transactions. Once chargeback is completed (accepted, lost, or expired) Recurly creates an external refund invoice and expires subscription.

## Gateways supported

- **Adyen**
- **Chase**

More gateways will be available in the future.

## Recurly chargeback process

1. Shoppers issue a chargeback with their issuing bank. Merchant can dispute or accept a chargeback through their gateway.
2. When chargeback is in the final state (lost or accepted) Recurly receives a “Chargeback Completed” event from a gateway.
3. Recurly creates an external refund invoice and a chargeback transaction
4. Recurly expires a shopper subscription. If supported by gateway Recurly will expire subscription only for fraud and service chargebacks.

NOTE: Recurly does not process chargeback reversals

## How to enable card chargebacks

- Request chargeback management feature from support
- Select `Create a refund transaction when a chargeback is received (default)` option in the chargeback setting on the `Invoice Settings` page

![](https://files.readme.io/3a53754-invoice_settings.png)

## Special gateways setup or management

#### Adyen

1. Enable Adyen webhooks  
   <https://docs.recurly.com/docs/adyen#configuring-adyen-notifications-for-recurly>
   1. (CHARGEBACK, SECOND_CHARGEBACK, DISPUTE_DEFENSE_PERIOD_ENDED)
2. Enable chargeback Adyen event: originalReference for CHARGEBACK_REVERSED  
   <https://docs.adyen.com/risk-management/disputes-api/dispute-notifications#enable-webhooks>
3. Read more about [managing Adyen Disputes in their documentation](https://docs.adyen.com/risk-management/manage-disputes/). Certain webhook status options will not be triggered without gateway management. For example: In order to ever receive a webhook with disputeStatus: "Accepted", you must go to your Adyen Dashboard and accept the chargeback.

#### Chase Orbital

To enable chargeback management with Chase Orbital gateway you need to provide Recurly access to Chase chargeback file reports. Please reach out to your Recurly contact for more information.