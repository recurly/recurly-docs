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

* **Adyen**
* **Chase**
* **Stripe**

More gateways will be available in the future.

## Recurly chargeback process

1. Shoppers issue a chargeback with their issuing bank. Merchant can dispute or accept a chargeback through their gateway.
2. When chargeback is in the final state (lost or accepted) Recurly receives a “Chargeback Completed” event from a gateway.
3. Recurly creates an external refund invoice and a chargeback transaction
4. Recurly expires a shopper subscription.
   1. **Note:** If supported by gateway Recurly will only expire subscription only for fraud and service chargebacks.

NOTE: Recurly does not process chargeback reversals

## How to enable card chargebacks

* Request chargeback management feature from support
* Select `Create a refund transaction when a chargeback is received (default)` option in the chargeback setting on the `Invoice Settings` page

![](https://files.readme.io/3a53754-invoice_settings.png)

## Special gateways setup or management

#### Adyen

1. Enable Adyen webhooks\
   [https://docs.recurly.com/docs/adyen#configuring-adyen-notifications-for-recurly](https://docs.recurly.com/docs/adyen#configuring-adyen-notifications-for-recurly)
   1. (CHARGEBACK, SECOND\_CHARGEBACK, DISPUTE\_DEFENSE\_PERIOD\_ENDED)
2. Enable chargeback Adyen event: originalReference for CHARGEBACK\_REVERSED\
   [https://docs.adyen.com/risk-management/disputes-api/dispute-notifications#enable-webhooks](https://docs.adyen.com/risk-management/disputes-api/dispute-notifications#enable-webhooks)
3. Read more about [managing Adyen Disputes in their documentation](https://docs.adyen.com/risk-management/manage-disputes/). Certain webhook status options will not be triggered without gateway management. For example: In order to ever receive a webhook with disputeStatus: "Accepted", you must go to your Adyen Dashboard and accept the chargeback.

#### Chase Orbital

To enable chargeback management with Chase Orbital gateway you need to provide Recurly access to Chase chargeback file reports. Please reach out to your Recurly contact for more information.

## Service and Fraud Chargeback Code

Card brands have unique Fraud codes for each network. These codes include:

#### Fraud Chargeback Codes

| Visa                         | MasterCard                               | Cartes Bancaires | Discover                     | UnionPay         | Diners                  | JCB                     | Elo    | American Express                                                                                 |
| :--------------------------- | :--------------------------------------- | :--------------- | :--------------------------- | :--------------- | :---------------------- | :---------------------- | :----- | :----------------------------------------------------------------------------------------------- |
| 10.1, 10.2, 10.3, 10.4, 10.5 | 4837, 4840, 4849, 4863, 4870, 4871, 4999 | 45               | 4752, 4866, 4867, 7010, 7030 | 4515, 4514, 4562 | C46, C41, C42, C53, C54 | 534, 546, 526, 526, 527 | 75, 83 | 4526, 4527, 4534, 4540, 4755, 4763, 4798, 4799, F10, F14, F24, F29, F30, F31, FR2, FR4, FR5, FR6 |

#### Service Chargeback Codes

| Visa                                    | MasterCard                         | Cartes Bancaires | Discover            | UnionPay       | Diners          | JCB                         | Elo      | American Express                                                  |
| :-------------------------------------- | :--------------------------------- | :--------------- | :------------------ | :------------- | :-------------- | :-------------------------- | :------- | :---------------------------------------------------------------- |
| 13.1 13.2 13.3 13.4 13.5 13.6 13.7 13.8 | 4841 4853 4854 4855 4859 4860 6305 | 30, 41, 53       | 4755 4553 4541 8002 | 4502 4532 4544 | D62 D66 D69 D70 | 502 513 516 544 554 537 538 | 30 41 53 | 4513 4515 4544 4553 4554 4754 C02 C04 C05 C08 C14 C18 C28 C31 C32 |

You can reference these codes on the Gateway's documentation pages:

* Adyen: [Adyen Dispute Reasons and Defense Requirements](https://docs.adyen.com/risk-management/understanding-disputes/dispute-reason-codes/)
* In the case of Stripe, the chargeback status and code will be available in your Recurly Admin UI. [Stripe dispute reasons](https://docs.stripe.com/disputes/reason-codes-defense-requirements) are available in Stripe's documentation as well.

<Image align="center" src="https://files.readme.io/973cc8453fd49fe6b23321b0f83ce4e02e27af1dc570e83d74b2a07ff8a43488-Stripe_Chargeback_Reasons.png" />