---
title: PayPal Complete
excerpt: ''
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

This payment gateway or setting is available to all customers on any Recurly subscription plan.

### Limitations

Please be aware of the following limitations of PayPal Complete:

* PayPal Complete does not support Hosted Payment Pages (HPP) for PayPal specifically. Credit Cards are fully supported. PayPal is supported on Checkout.
* Subscriptions initiated on PayPal Complete cannot migrate to PayPal Business due to the PPC’s vaulting features differing from the PP Business’s Billing Agreement IDs.
* Existing Billing Agreement IDs will still function if migrating subscriptions from PayPal Business Account to a PayPal Complete gateway.
* PayPal Complete is only supported in certain regions.
* JCB is only available to Canadian Merchants.\*
* Check [PayPal's list of prohibited activities/businesses ](https://www.paypal.com/us/legalhub/acceptableuse-full?locale.x=en_US)to see if you qualify for a PayPal complete account.

# Definition

PayPal Complete is the latest and greatest payment gateway solution by PayPal that simplifies the payment process by accommodating a variety of PayPal payment methods within one single integration. Incorporating PayPal Complete into Recurly is swift and hassle-free, eliminating the need to acquire a separate merchant account.

# Key details

| Services                        | Description                                                                                   |
| :------------------------------ | :-------------------------------------------------------------------------------------------- |
| Supported Recurly services      | PayPal Complete                                                                               |
| Supported operations            | Payment, Refund                                                                               |
| Supported payment types         | Credit and Debit Cards, PayPal                                                                |
| Supported card brands           | Visa, Mastercard, American Express, Discover, JCB, Diner Club                                 |
| Gateway specific 3DS2 supported | N/A                                                                                           |
| Card on File Supported          | N/A                                                                                           |
| Regions                         | United States, Australia, Canada, United Kingdom                                              |
| Currencies                      | USD, AUD, CAD, CHF, CZK, DKK, EUR, MYR, GBP, HUF, JPY, NOK, NZD, PLN, SEK, SGD, TWD, and PHP. |

## Required PayPal Setup

Before processing using your PayPal Complete gateway, you must contact your PayPal Account Executive or CSM and enable the Referenced Transactions flag. All accounts must have this feature enabled prior to processor, or errors will be encountered. If there is no CSM/sales contact assigned to your account, please call customer service at 1-888-221-1161.

## Differences between eCheck and other PayPal transactions

* Transactions funded by bank accounts function similarly to direct debits (such as ACH in the United States), requiring 3-6 days for funds to clear in a customer’s PayPal account. Similarly, if you process a refund directly from your bank account—especially when there's no balance in your PayPal account—it may also take 3-6 days (or longer) for the customer to see a credit.
* During this waiting period, PayPal labels the transaction as "pending" until the involved banks finalize the transaction.
* Once settled, PayPal sends an "Instant Payment Notification" (or webhook) signaling the transaction's conclusion. If the funds aren't received, a similar notification indicates the transaction was declined.

## Bank account funded transactions in Recurly

* **Processing Status**:
  * Upon receiving and initiating a transaction request from Recurly, PayPal communicates a "pending" status back to Recurly. This status, visible in the Recurly App, exports, and API, simultaneously updates both the transaction and the related invoice to "processing."
  * Concurrently, Recurly dispatches a "processing payment" webhook to any designated endpoints and, if enabled, sends a "payment processing" email to the customer.
* **Status Updates**:
  * As PayPal updates transaction statuses—like successful payment reception—it informs Recurly. Depending on the update, Recurly then adjusts the transaction and invoice statuses, marking them as "successful" and "paid" respectively.
  * Simultaneously, Recurly sends out relevant webhooks, like a successful payment or an overdue invoice, and if activated, emails the customer with either a payment confirmation or a decline notice.

### PayPal eChecks with Recurly's dunning and retries

Due to the asynchronous nature of PayPal eChecks, Recurly treats related "past due" invoices distinctively from instant payment methods like credit cards. If a PayPal eCheck is the payment method, when Recurly automatically retries a payment, the invoice status switches to "processing" until PayPal's response. Based on PayPal's feedback, the invoice either reverts to "past due" (if still within the dunning cycle) or updates to "failed" (post dunning cycle).

Here's a sample scenario of status updates:

| Event                                                                                                                                   | PayPal Transaction Status | Recurly Transaction Status | Recurly Invoice Status |
| :-------------------------------------------------------------------------------------------------------------------------------------- | :------------------------ | :------------------------- | :--------------------- |
| 1. Payment request by Recurly, acknowledged and processed by PayPal.                                                                    | Pending                   | Processing                 | Processing             |
| 2. Days later, PayPal indicates payment failure, Recurly starts dunning.                                                                | Failed                    | Declined                   | Past Due               |
| 3. Recurly's dunning schedule triggers a dunning email after some days.                                                                 | No change                 | No change                  | No change              |
| 4. Retry #1: Following Recurly's retry logic, a new payment attempt with PayPal is made after several days.                             | Pending                   | Processing                 | Processing             |
| 5. Days later, PayPal flags the payment as declined. Recurly notes the invoice's **dunning period is ongoing**.                         | Failed                    | Declined                   | Past Due               |
| 6. Retry #2: Recurly tries another payment with PayPal after a few more days.                                                           | Pending                   | Processing                 | Processing             |
| 7. After several days, PayPal reports payment failure. Recurly updates the status after verifying the **dunning period has concluded**. | Failed                    | Declined                   | Failed                 |

# Integrating PayPal complete with Recurly

1. **Gateway Initialization:** To integrate PayPal Complete, navigate to Recurly Admin UI → Configuration → Payment Gateways → Add Payment Gateway. Log in using your PayPal credentials to activate the gateway.

2. **Gateway Verification:** Post gateway addition, your PayPal account will undergo a verification process. Track this progression using the admin UI.

3. **Gateway Status Updates:** Occasionally, your application might not gain instant approval, marking it as 'Incomplete Configuration'. The Payment Gateways page will provide real-time status updates. Statuses can range from email confirmation requisites to application reviews or denials. In case of any alert, it’s advisable to connect directly with PayPal through the seller portal, as Recurly support might not possess detailed insights about your account.

<Image align="center" className="border" border={true} src="https://files.readme.io/5ba78d3-PPC.Seller.AccountStatus-ConfirmEmail.png" />

4. **Post-Integration Setup:** Post successful integration, define specific settings on Recurly:

* Currencies
* Card brands

Ensure that the 'reference transaction flag' is active on your PayPal account.

## Verification

* Once the gateway is added, verify your PayPal account.
* Monitor the verification status on the Admin UI.
* If the application isn't approved instantly, check for status updates on the "Payment Gateways" page. Refresh the status if needed.

## **Status alerts**

* Be attentive to various status messages such as email confirmation requirements, application reviews, and any account restrictions.
* If you encounter multiple alerts, address each one as the application progresses.
* Existing PayPal Business account holders that support credit and debit cards might bypass these alerts.

## **Recurly configuration**

* After gateway integration, define the desired settings, especially the supported currencies and card brands.

## **PayPal settings**

* Ensure the "reference transaction" flag is enabled in your account. You will not be able to enable this on your own, contact your PayPal Account manager or PayPal customer service to enable this for you.

## **Handling eCheck transactions**

* Set up your PayPal account to dispatch "IPNs" to Recurly for optimal eCheck transaction processing. [Refer to the detailed instructions here.](https://docs.recurly.com/docs/paypal-payments#section-configuring-pay-pal-to-send-recurly-the-status-updates)

# PayPal's eCheck feature

PayPal transactions financed or refunded via a bank account, or eChecks, are crucial for comprehensive PayPal functionalities in Recurly. Hence, setting up IPNs (Instant Payment Notifications) on your PayPal account becomes imperative. Here's a concise guide for setting up IPNs:

1. Sign into your merchant account on [PayPal](https://www.paypal.com).
2. Navigate through the profile icon → Profile and Settings → My selling tools.
3. Update 'Instant payment notifications' under the 'Getting paid and managing my risk' section.
4. Enable the listener by choosing IPN Settings and inserting the URL: [https://callbacks.recurly.com/paypal/\_recurly\_subdomain\_here\_](https://callbacks.recurly.com/paypal/_recurly_subdomain_here_).
5. Activate 'Receive IPN messages' and save your settings.\
   **Important:** For Recurly sites hosted within the European Union (EU) data centers, use the base URL as callbacks.eu.recurly.com.

### Setting Up PayPal to relay status updates to Recurly

To ensure that the transaction status from PayPal syncs accurately with Recurly, follow the steps below. Detailed guidelines can also be found on [PayPal's developer page](https://developer.paypal.com/docs/classic/ipn/integration-guide/IPNSetup/):

1. **Accessing your PayPal merchant account**:
   * Navigate to [www.paypal.com](https://www.paypal.com) and sign in to your merchant account.
2. **Navigating to the profile settings**:
   * Click on the profile icon, located on the top right corner of the page. From the dropdown Business Profile menu, choose **Profile and Settings**.
   * If you can't locate the profile icon, follow this path: **My Account** → **Profile** → **My Selling Tools**.
3. **Updating instant payment notifications (IPN)**:

   * Within the **My Selling Tools** section, locate the **Instant payment notifications** row under the **Getting paid and managing my risk** category. Click on the **Update** link adjacent to it.
4. **Configuring IPN settings**:
   * Opt for **Choose IPN Settings**. This lets you set your listener's URL and activate it.
   * Insert the following URL: `https://callbacks.recurly.com/paypal/_recurly_subdomain_here_`. For instance, if your subdomain is "kalekrate", the URL would be [https://callbacks.recurly.com/paypal/kalekrate](https://callbacks.recurly.com/paypal/kalekrate).
5. **Enabling IPN messages**:
   * Select the **Receive IPN messages (Enabled)** option to activate your listener.
6. **Saving and exiting**:
   * Click on the **Save** button to preserve the changes.
   * To return to the main profile, select **Back to Profile Summary**.