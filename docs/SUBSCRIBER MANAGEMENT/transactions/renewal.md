---
title: Renewal
excerpt: How subscription renewals and prerenewal notifications work in Recurly.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Subscription renewals in Recurly automatically generate new recurring invoices and trigger payment attempts through the configured payment gateway. Each renewal maintains billing continuity for ongoing subscriptions and ensures customers are charged based on their active plan or billing cycle.

### Required plan

These features are available to all customers on any Recurly subscription plan.

### Prerequisites & limitations

* **Prerequisites:** Active subscription, valid payment method, and a configured payment gateway.
* **Limitations:**
  * **Boleto payments** do not support direct recurring transactions.
  * **Gateway delays** or **network timeouts** may temporarily mark an invoice as **Past Due** until confirmation.
  * Prerenewal notifications are only sent if **External Subscription Notifications** are enabled on your site.

# Definition

A renewal represents the automatic continuation of a subscription term. When a renewal occurs, Recurly generates a new invoice, processes payment through the gateway, and updates the subscription term and invoice status accordingly.

# Key benefits

* **Automatic billing:** Recurly manages renewals without manual intervention.
* **Gateway integration:** Payments are processed seamlessly using the customer’s saved payment method.
* **Lifecycle visibility:** Notifications track every step—renewal, upgrade, downgrade, and expiration.
* **Localized options:** For payment methods like **Boleto**, Recurly adapts invoice handling automatically.

# Key details

## Renewal process

1. **Detect** an active subscription approaching its renewal date.
2. **Generate** a new recurring invoice based on the subscription plan, billing cycle, and add-ons.
3. **Communicate** with the configured payment gateway to **process payment** automatically.
4. **Update** the invoice and subscription status accordingly:
   1. **Paid:** The renewal succeeded and payment was confirmed.
   2. **Past Due:** Payment failed or is pending (e.g., Boleto).
   3. **Canceled/Expired:** The subscription was not renewed due to failed payments or cancellation.

## Renewals with Boleto

Because **Boleto** does not support direct recurring transactions:

* Recurly **automatically generates** a new recurring invoice at renewal.
* This invoice initially appears as **Past Due** to account for processing time.
* Recurly **issues a new Boleto invoice** for the renewal amount and **sends** a notification email using your **Boleto email template**.
* The email contains a **download link** for the Boleto invoice.
* Once the customer completes payment, the invoice status in Recurly **updates to Paid** automatically.

| Step | Status                | Description                                                         |
| ---- | --------------------- | ------------------------------------------------------------------- |
| 1    | **Invoice generated** | Recurly creates a new renewal invoice for the next billing period.  |
| 2    | **Past Due**          | Awaiting payment while the customer processes Boleto.               |
| 3    | **Paid**              | Recurly receives confirmation from the gateway once payment clears. |

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

## For specific gateways

### UPI

They also receive a pre-renewal push notification 24–48 hours prior to their next billing date, giving them another opportunity to pause or cancel the subscription prior to charging. This push notification occurs for every charge for the lifetime of their subscription.
