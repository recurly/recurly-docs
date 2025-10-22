---
title: Verification
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Subscription Trials and Billing information updates in Recurly will typically trigger an invoice-less, zero-dollar **verification** attempt (where supported) through the configured payment gateway. Verifications are important for validating bank information, performing 3DS without charging the customer, and collecting valid payment method information during a trial signup for mid-cycle payment method update.

Verifications can also check for valid CVV and Address Information, so be sure to include CVV and Physical Billing Address details for all of your transactions, where possible.

### Required plan

These features are available to all customers on any Recurly subscription plan.

### Prerequisites & limitations

* **Prerequisites:** Active subscription, valid payment method, and a configured payment gateway. Some gateways will require additional configuration for verifications. See each individual gateway page for details.
* **Limitations:**
  * Certain payment methods do not support verifications by nature. Please ask support for details if you are unable to find this information in our documentation.
  * Some gateways do not support a **truly** zero dollar authorization, and so we may perform a 1.00 authorization behind the scenes to obtain AVS and CVV verification results, recurring NTIDs for subscriptions, and 3DS authentication. 
  * In certain cases, a Verification is representative of an enrollment, and not an actual transaction event.

# Definition

A verification represents the beginning of a consumer's relationship with your business, and a powerful authentication tool for ensuring only valid billing information is on file and validating consumer authentication through 3DS where necessary. In the case of a trial, the Verification serves as the customer-initiated transaction where Recurly obtains the required NTID for the eventual conversion from Trial to Renewal. The first charge on a Trial Subscription will be a **purchase** for the amount associated with their subscription and plan.

# Key benefits

* **Automatic verification:** Recurly manages verification logic based on your interactions with our API. Account creations, Billing Info Updates, and Trials will generate a verification where supported, and if a payment method is provided.
* **Gateway integration:** Payments are processed seamlessly using the customer’s payment details provided in the transaction request. Verifications can also use stored payment details. See our [CVV and Billing Info verification endpoints via API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_infos_cvv).
* **Address and CVV Verifications:** If you collect Address and CVV info from your customers, verifications can return details results from their bank to confirm they've entered the correct information. Certain gateways support rejecting transactions if the address and CVV details do not fully match. See [Payments Settings](https://docs.recurly.com/recurly-subscriptions/docs/payment-settings#/) documentation for more details.

# Key details

## Renewal process

1. **Detect** an active subscription approaching its renewal date.
   1. If **Account Updater** is active, a pre-renewal update will occur if applicable to avoid renewal failures.
2. **Generate** a new recurring invoice based on the subscription plan, billing cycle, and add-ons.
3. **Communicate** with the configured payment gateway to **process the payment** automatically.
4. **Update** the invoice and subscription status accordingly:
   1. **Paid:** The renewal succeeded and payment was confirmed. The subscription remains **active**.
   2. **Past Due:** Payment failed or has a payment-method-specific caveat (e.g., Boleto). The Invoice will enter dunning to collect on the past due amount. Subscription remains **active**.
   3. **Pending**: Payment is asynchronous and has not received a status update yet (e.g. ACH, SEPA, UPI). Subscription remains **active.**
   4. **Failed:** Retries have failed to collect on the invoice and the invoice has moved into a Failed state. Dunning settings will determine the subscription's final state.

## External subscription notifications

External Subscription Notifications (ESNs) inform your system about **subscription lifecycle changes**, including:

* **Creation**
* **Renewal**
* **Cancellation**
* **Upgrades**
* **Downgrades**
* **Expirations**

Each ESN includes full subscription details in **JSON or XML** format and can be integrated into your system for downstream processing or CRM synchronization.

> See the full list of prerenewal and renewal notifications in [Prerenewal notifications](https://docs.recurly.com/recurly-subscriptions/docs/prerenewal-notifications#/)  .

## Example: Prerenewal workflow

| Step | Action                           | Description                                                                            |
| ---- | -------------------------------- | -------------------------------------------------------------------------------------- |
| 1    | **Prerenewal notification sent** | Alerts your system or customer of an upcoming renewal.                                 |
| 2    | **Invoice generated**            | Recurly creates a new invoice and attempts to charge the saved payment method.         |
| 3    | **Transaction created**          | Payment gateway processes the transaction.                                             |
| 4    | **Invoice updated**              | Recurly updates the invoice to **Paid** or **Past Due** depending on gateway response. |

## Monitoring renewals

* Use the **Invoices** section to **track renewal invoices** and statuses.
* Use the **Subscriptions** section to **view renewal history** and upcoming renewal dates.
* Enable **Webhooks** or **External Subscription Notifications** to integrate renewals into your own system.

## Troubleshooting

* **Invoice stuck as Past Due:** For Boleto, wait for the customer to pay; for card or ACH payments, check gateway or bank response.
* **Payment declined:** Ensure the payment method is valid and retry the charge manually if needed.
* **No renewal triggered:** Confirm subscription status is active and next renewal date is set.
