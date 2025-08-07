---
title: PayPal Complete
excerpt: >-
  PayPal Complete is the latest and greatest payment gateway solution by PayPal
  that simplifies the payment process by accommodating a variety of PayPal
  payment methods within one single integration. Incorporating PayPal Complete
  into Recurly is swift and hassle-free, eliminating the need to acquire a
  separate merchant account
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

[PayPal Complete](https://recurly.com/partner/paypal-recurly/) is the latest and greatest payment gateway solution by PayPal that simplifies the payment process by accommodating a variety of PayPal payment methods within one single integration. Incorporating PayPal Complete into Recurly is swift and hassle-free, eliminating the need to acquire a separate merchant account.

PayPal can be used in a META (Facebook / Instagram) environment when limited by WebView browsers. See our [PayPal Recurly.js documentation](https://docs.recurly.com/v1.2/docs/paypal#/) for more information.

***

> 👍 Upgrade to PayPal Complete Today!
>
> If you're using PayPal Payflow Pro, PayPal Payment Pro (US), or PayPal Business, now’s the time to switch! All new Recurly + PayPal features will be available only on PayPal Complete.
>
> Upgrading is free, fast, and seamless—your subscriptions carry over with no disruption. [Click here for migration instructions.](https://docs.recurly.com/docs/paypal-complete#integrating-paypal-complete-with-recurly)

***

# Key details

| Services                        | Description                                                                                   |
| :------------------------------ | :-------------------------------------------------------------------------------------------- |
| Supported Recurly services      | PayPal Complete                                                                               |
| Supported operations            | Payment, Refund                                                                               |
| Supported payment types         | Credit and Debit Cards, PayPal                                                                |
| Supported card brands           | Visa, Mastercard, American Express, Discover, JCB, Diner Club                                 |
| Gateway specific 3DS2 supported | N/A                                                                                           |
| Card on File Supported          | N/A                                                                                           |
| Regions                         | United States, EMEA, Canada, United Kingdom/EU, APAC                                          |
| Currencies                      | USD, AUD, CAD, CHF, CZK, DKK, EUR, MYR, GBP, HUF, JPY, NOK, NZD, PLN, SEK, SGD, TWD, and PHP. |

## Required PayPal Setup

### Differences between eCheck and other PayPal transactions

* Transactions funded by bank accounts function similarly to direct debits (such as ACH in the United States), requiring 3-6 days for funds to clear in a customer’s PayPal account. Similarly, if you process a refund directly from your bank account—especially when there's no balance in your PayPal account—it may also take 3-6 days (or longer) for the customer to see a credit.
* During this waiting period, PayPal labels the transaction as "pending" until the involved banks finalize the transaction.
* You must enable PayPal status update webhooks in your site developer settings to allow status updates to occur.

### Bank account funded transactions in Recurly

* **Processing Status**:
  * Upon receiving and initiating a transaction request from Recurly, PayPal communicates a "pending" status back to Recurly. This status, visible in the Recurly App, exports, and API, simultaneously updates both the transaction and the related invoice to "processing."
  * Concurrently, Recurly dispatches a "processing payment" webhook to any designated endpoints and, if enabled, sends a "payment processing" email to the customer.
* **Status Updates**:
  * As PayPal updates transaction statuses—like successful payment reception—it informs Recurly. Depending on the update, Recurly then adjusts the transaction and invoice statuses, marking them as "successful" and "paid" respectively.
  * Simultaneously, Recurly sends out relevant webhooks, like a successful payment or an overdue invoice, and if activated, emails the customer with either a payment confirmation or a decline notice.

### PayPal eChecks with Recurly's dunning and retries

Due to the asynchronous nature of PayPal eChecks, Recurly treats related "past due" invoices distinctively from instant payment methods like credit cards. If a PayPal eCheck is the payment method, when Recurly automatically retries a payment, the invoice status switches to "processing" until PayPal's response. Based on PayPal's feedback, the invoice either reverts to "past due" (if still within the dunning cycle) or updates to "failed" (post dunning cycle).

Here's a sample scenario of status updates:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Event
      </th>

      <th>
        PayPal Transaction Status
      </th>

      <th>
        Recurly Transaction Status
      </th>

      <th>
        Recurly Invoice Status
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1. Payment request by Recurly, acknowledged and processed by PayPal.
      </td>

      <td>
        Pending
      </td>

      <td>
        Processing
      </td>

      <td>
        Processing
      </td>
    </tr>

    <tr>
      <td>
        2. Days later, PayPal indicates payment failure, Recurly starts dunning.
      </td>

      <td>
        Failed
      </td>

      <td>
        Declined
      </td>

      <td>
        Past Due
      </td>
    </tr>

    <tr>
      <td>
        3. Recurly's dunning schedule triggers a dunning email after some days.
      </td>

      <td>
        No change
      </td>

      <td>
        No change
      </td>

      <td>
        No change
      </td>
    </tr>

    <tr>
      <td>
        4. Retry #1: Following Recurly's retry logic, a new payment attempt with PayPal is made after several days.
      </td>

      <td>
        Pending
      </td>

      <td>
        Processing
      </td>

      <td>
        Processing
      </td>
    </tr>

    <tr>
      <td>
        5. Days later, PayPal flags the payment as declined. Recurly notes the invoice's **dunning period is ongoing**.
      </td>

      <td>
        Failed
      </td>

      <td>
        Declined
      </td>

      <td>
        Past Due
      </td>
    </tr>

    <tr>
      <td>
        6. Retry #2: Recurly attempts another payment with PayPal after a few more days.
      </td>

      <td>
        Pending
      </td>

      <td>
        Processing
      </td>

      <td>
        Processing
      </td>
    </tr>

    <tr>
      <td>
        7. After several days, PayPal reports payment failure. Recurly updates the status after verifying the **dunning period has concluded**.
      </td>

      <td>
        Failed
      </td>

      <td>
        Declined
      </td>

      <td>
        Failed
      </td>
    </tr>
  </tbody>
</Table>

# Integrating PayPal complete with Recurly

1. **Gateway Initialization:** To integrate PayPal Complete, navigate to Recurly Admin UI → Configuration → Payment Gateways → Add Payment Gateway. Log in using your PayPal credentials to activate the gateway.

2. **Gateway Verification:** Post gateway addition, your PayPal account will undergo a verification process. Track this progression using the admin UI.

3. **Gateway Status Updates:** Occasionally, your application might not gain instant approval, marking it as 'Incomplete Configuration'. The Payment Gateways page will provide real-time status updates. Statuses can range from email confirmation requisites to application reviews or denials. In case of any alert, it’s advisable to connect directly with PayPal through the seller portal, as Recurly support might not possess detailed insights about your account.

<Image align="center" className="border" border={true} src="https://files.readme.io/5ba78d3-PPC.Seller.AccountStatus-ConfirmEmail.png" />

4. **Post-Integration Setup:** Post successful integration, define specific settings on Recurly:

* Currencies
* Card brands

## Verification

* Once the gateway is added, verify your PayPal account.
* Monitor the verification status on the Admin UI.
* If the application isn't approved instantly, check for status updates on the "Payment Gateways" page. Refresh the status if needed.

## **Status alerts**

* Be attentive to various status messages such as email confirmation requirements, application reviews, and any account restrictions.
* If you encounter multiple alerts, address each one as the application progresses.
* Existing PayPal Business account holders that support credit and debit cards might bypass these alerts.

## Billing and Shipping Data

If you are not passing billing information or shipping data to us directly, you can have Recurly consume data received from PayPal by enabling one or both of two feature flags:

* Save PayPal billing address
* Save PayPal shipping address

Please work with support to enable these feature flags for your site.