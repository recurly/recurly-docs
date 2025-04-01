---
title: Backup payment method
excerpt: >-
  Ensure seamless transactions and reduce involuntary churn with Recurly's
  Backup Payment Method.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Additional cost

There are additional fees to use Wallet. Please reach out to your Account Manager, Account Executive or contact Recurly Support to learn more.

### Prerequisites

* Merchants must have the Wallet feature enabled.
* Merchants should be aware of additional fees associated with using Wallet.
* Subscribers' consent is required before setting their payment method as a backup

# Definition

The Backup Payment Method is a feature in Recurly that allows subscribers to set an alternative payment method to be used when the primary payment method fails during a transaction. This proactive approach aims to reduce the risk of payment failure and involuntary churn.

# Key benefits

* **Reduced churn**: Lower the risk of involuntary churn due to payment failures.
* **Enhanced customer experience**: Ensure uninterrupted service for subscribers by having a backup payment option.
* **Increased revenue recovery**: Improve chances of successful transactions, especially for recurring payments.
* **Automated payment handling**: Automatic switch to the backup method without manual intervention.
* **Flexibility**: Supports a wide range of payment methods across different regions.

# Key details

Recurly's Backup Payment Method is a strategic approach to tackle the common issue of transaction failures. With over 2,000 reasons for a credit card transaction to fail and a 10% decline rate for recurring transactions, having a backup payment method is crucial.

## Wallet integration

With the [Wallet](https://docs.recurly.com/docs/wallet) feature, subscribers can store multiple payment methods. The Backup Payment Method is an extension of this, allowing a specific payment method to be designated as a backup. In the event of a primary payment method decline, Recurly will automatically switch to the backup method, ensuring a higher success rate for transactions.

<Image title="Screen Recording 2021-03-29 at 02.50 PM.gif" alt={1672} align="center" src="https://files.readme.io/db76b76-Screen_Recording_2021-03-29_at_02.50_PM.gif">
  Setting a backup payment method in the Admin Console
</Image>

# Implementation guidelines

### Setting a backup payment method

Subscribers can set a backup payment method through the Admin Console, [API V3](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_billing_info), and [API V2](https://developers.recurly.com/api-v2/v2.29/index.html#operation/createAccountsBillingInfoCreditCard). When using APIs, the backup can be set via several endpoints, including [/billing\_infos](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_billing_info), [/subscriptions](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_subscription), and [/purchases](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_purchase). Always ensure you have the subscriber's consent before setting their payment method as a backup.

### Setting a backup payment method via admin console

1. Log in to your Recurly Admin Console.
2. Navigate to the **Subscribers** section.
3. Select the desired subscriber account.
4. Under the **Billing Information** section, you'll see a list of stored payment methods.
5. Choose the desired payment method and click on the **Set as Backup** option.

### Setting a backup payment method via API

1. Use the appropriate API endpoint, either [API V3](https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_billing_info) or [API V2](https://developers.recurly.com/api-v2/v2.29/index.html#operation/createAccountsBillingInfoCreditCard).
2. Make a POST request to the `/billing_infos` endpoint with the subscriber's account ID and the desired payment method details.
3. Include a parameter or flag indicating that this payment method should be set as a backup.

## Backup payment method usage

The primary use of a backup payment method is to address payment issues for failed subscription renewals. If set, it will be used for any invoice entering dunning. However, it won't be applied for purchase requests and subscription changes (unless the backup payment method is specified in the purchase request).

## Payment method variations

Recurly supports a plethora of payment methods worldwide. Depending on the payment method, the response time from the gateway can vary. For methods providing immediate responses, such as most credit cards, debit cards, and digital wallets, Recurly will instantly retry the backup payment method. For delayed response methods, such as direct debit, Recurly waits for the initial payment decline before initiating the backup attempt.

## Retry mechanism

If both the primary and backup transactions decline, Recurly will retry these transactions during the dunning process. The system will alternate between the initial and backup methods, awaiting a decline response before the next attempt. If a hard decline occurs, that payment method won't be retried for the invoice.

## Merchant and subscriber changes

Merchants need to update their integration to support [Wallet](https://docs.recurly.com/docs/wallet) and ensure they obtain subscriber consent before setting a backup payment method. Subscribers should be provided with a user interface to manage their payment methods and specify which one should act as their backup.

## Analytics

Recurly has updated the Recovered Revenue and Dunning Effectiveness reports to account for recoveries from a backup payment method. Merchants can also use the [billing\_info v5](https://docs.recurly.com/docs/billing-info-export) and [transactions v5](https://docs.recurly.com/docs/transaction-export) exports to gain insights into backup payment method usage.

### Monitoring backup payment method analytics

1. Log in to your Recurly Admin Console.
2. Navigate to the **Reports** section.
3. Access the **Recovered Revenue** and **Dunning Effectiveness** reports to view recoveries from backup payment methods.
4. For more detailed insights, download the [billing\_info v5](https://docs.recurly.com/docs/billing-info-export) and [transactions v5](https://docs.recurly.com/docs/transaction-export) exports.

## Testing

Merchants can test the backup payment method in Development mode against their gateway. This allows for the simulation of both declined and successful payment scenarios. Additionally, the backup payment method can be tested using Recurly's sandbox site with specific [test card numbers](https://docs.recurly.com/docs/test).

### Testing backup payment method in development mode

1. Ensure your Recurly site is in **Development mode**.
2. Create a subscription using a test card number that simulates a declined transaction for the primary payment method.
3. Use another test card number that simulates a successful transaction for the backup payment method.
4. Initiate a transaction. The primary payment method should decline, and Recurly should automatically attempt the backup payment method.

## Considerations

### Obtaining subscriber consent

1. Update your website's terms and conditions to include a clause about using a backup payment method.
2. When subscribers add or update their payment method, display a consent checkbox including terminology similar to: "I authorize [Your Company] to use this as a backup payment method in case of transaction failures." 
3. Ensure the checkbox is unchecked by default, requiring explicit action from the subscriber to give consent.
4. Store the subscriber's consent choice securely for future reference.
5. Compliance is up to each merchant to define and adhere to.

### Handling communication errors with gateways

**Communication errors with a gateway will prevent backup attempts.**

1. If a communication error occurs with the gateway during a transaction, monitor the transaction status in the Admin Console or via API responses.
2. If the transaction status remains pending or unclear, avoid initiating a backup attempt manually.
3. Wait for confirmation from Recurly or the gateway about the transaction's failure before attempting any subsequent transactions.

**Merchants should be aware of certain scenarios and considerations**

* If the primary payment method is also set as the backup, only the primary method will be used for retries.
* Custom Gateway Routing considerations apply to backup payment methods.
* Using two ACH payment methods for both primary and backup is not recommended.
* Only one backup payment method can be set for each account.
* Backup payment method won't be used for purchase requests and subscription changes.
