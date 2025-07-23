---
title: Chargebacks / late failures for direct debit
excerpt: >-
  Efficiently manage and respond to late failure events associated with direct
  debit payments through Recurly’s comprehensive chargeback and late failure
  handling feature.
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

# Definition

Chargebacks and Late Failures for direct debit in Recurly refer to the process where a customer disputes a direct debit payment or does not have sufficient funds, causing either the funds to be returned to the customer by the bank and/or the merchant to be debited. Recurly supports this functionality for SEPA direct debit through GoCardless gateway.

# Key benefits

* **Automated direct debit failure handling:** Simplify your workflow with automated invoicing processing options for Chargebacks and Late Failures.
* **Flexible management options:** Choose between automated or manual chargeback processing based on your business needs.
* **Clear and detailed reporting:** Easily track and manage chargeback refund transactions directly within the Recurly admin UI.

# Key details

Recurly provides robust support for handling chargebacks associated with specific direct debit payment methods, namely SEPA. The gateway that supports this functionality within Recurly include GoCardless presently.

To enhance clarity and aid in decision-making for merchants, it's crucial to distinguish between automated and manual chargeback processing in Recurly. Both methods impact the handling of invoices, transactions, and event notifications differently. Understanding these differences will help merchants choose the approach that aligns best with their operational needs.

#### Automated chargeback handling

* **Invoice Management:** When a chargeback occurs, Recurly automatically updates the original invoice with chargeback details. This ensures clear and accurate reporting within the system.
* **Transaction Updates:** Recurly reflects chargeback events in real-time, maintaining the accuracy of transaction records.
* **Subscription Management:** Automated processing adjusts the status of subscriptions based on predefined settings and choices, streamlining subscription and invoice management.
* **Ideal for:** Merchants who prefer Recurly to manage chargeback events comprehensively, ensuring that their subscription and invoice states are accurately updated with minimal intervention.

#### Manual chargeback processing

* **Notification Handling:** Merchants receive notifications of chargeback events, allowing them to handle these instances in their external systems.
* **Invoice Adjustments:** The responsibility of adjusting the original invoice rests with the merchant. This could involve creating a refund invoice or writing off the charge, based on the business’s practices.
* **Merchant Control:** This method provides greater control to merchants who wish to handle chargebacks personally, often due to specific accounting or customer service strategies.
* **Ideal for:** Merchants seeking to manage chargebacks externally, especially those who require customized handling of each case or who integrate chargeback events into broader financial or customer relationship management systems.

## Chargeback settings

Within Recurly, you can define how you want to manage direct debit failures through settings available on the invoice settings page.

Find this setting at “Configuration → Invoice Templates → Invoice Settings” and scroll down to “Chargebacks”.

<Image align="center" className="border" border={true} width="90% " src="https://files.readme.io/4d7f6fd-image.png" />

There are two primary options available for handling these types of failures:

#### 1. Create a Refund Transaction When a Chargeback is Received (Default)

With this default setting enabled, Recurly automates the invoicing and status process for you. When a late failure or chargeback notification (via webhook) is received from a payment gateway, Recurly will:

* **Maintain the Original Transaction Status:** The status of the original transaction that the chargeback is associated with remains unchanged in most cases. For users who are taking advantage of automatic SEPA retries, transactions that fail due to Insufficient Funds will be marked as Past Due. Read more about Automatic SEPA retries here.
* **Generate a New Refund Transaction:** Recurly will automatically create a new refund invoice. The amount of this transaction will be equal to the chargeback amount. Please note, this does not return funds to your customer via an actual refund transaction request to your gateway, it is indicating that funds were reversed by the customer’s bank.
* **Update the Original Invoice with Failure / Chargeback Information:** The original invoice associated with the transaction will be updated to include detailed information about the chargeback.
* **Automatically Expire the Subscription** Please note, this setting is for Card Subscriptions only. It will not have an effect on non-Card subscriptions.

These chargeback refund transactions are easily accessible and can be found on the Transactions page within the Recurly admin UI. To view them, simply select “Chargeback” in the Status filter, and a list of chargeback refund transactions or invoices will be displayed.

#### 2. Manually Process Chargebacks

If you prefer to have more control over the chargeback process, this setting is for you. When this option is selected:

* **Receive a Webhook Notification:** Recurly will still send a webhook notification when a chargeback is initiated by a payment gateway.
* **No Automatic Refund Transaction:** Recurly will not automatically create a refund transaction in response to the chargeback.
* **No Automatic Action on the Original Invoice:** The original invoice associated with the chargeback will remain unchanged.

With this setting, you will not be able to filter by Chargeback status on the Transactions page since no chargeback refund transactions are created, giving you the flexibility to handle chargebacks in a way that aligns with your internal processes.

## Integration notes

### Webhook notifications

* Ensure that your systems are set up to receive and process these webhook notifications appropriately.
* For manual chargeback processing, these webhooks are essential as they alert you that action may be required.

### Refund transactions

* For automated chargeback handling, Recurly creates a refund transaction equal to the chargeback amount. This is separate from the original transaction and is specifically tied to the chargeback.
* It's crucial to emphasize that this refund transaction is initiated externally to Recurly, and there is no need for an additional action in your gateway. Recurly simply records this event to accurately reflect the chargeback events as they occur.

### Invoice updates

* With automated chargeback handling, Recurly adds chargeback information to the original invoice. This is designed to provide clear and detailed reporting within Recurly.
* If you are using manual chargeback processing, you will need to decide how you want to handle the original invoice based on the chargeback. This may involve creating a refund invoice or writing off the original invoice, depending on your business practices.

### Multi-currency handling

* If your Recurly site is set up to handle multiple currencies, ensure that your chargeback handling settings and processes are compatible with this setup.
* Chargebacks will be processed in the currency of the original transaction.

### API Integration

* If you are using Recurly’s API, consider how chargebacks for direct debit payments will be handled programmatically. You may need to update your API integration to handle chargeback webhooks and take appropriate actions based on those webhooks.