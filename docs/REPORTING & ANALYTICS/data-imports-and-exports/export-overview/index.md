---
title: Data exports
excerpt: >-
  Recurly offers a variety of ways to export your data. This page will give you
  a high-level overview of how to retrieve exports, what each export does, and
  some tips on how to use them. If you're interested in learning about each
  export in detail, please see below.
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

### Prerequisites

* Users must have Analytics user role permission.

# Exports overview

* All of the exports listed in the below table  are available through the [admin console](https://app.recurly.com/go/async_exports) and the Recurly API.

* Exports will use the site timezone (under Site Settings) rather than the users timezone when determining what data will be exported. Additionally, the days that are requested will be exported in their entirety rather than potentially having missing data for current day.

* See [New Versions](https://docs.recurly.com/v1.0/docs/export-overview#section-export-versions) for information about how changes to individual exports will create new versions of that export.

* See [Automated Exports](https://docs.recurly.com/v1.0/docs/export-overview#section-automated-exports) for more information about access via the Recurly API.

* See our **Recurly Exports ERD**:

<HTMLBlock>{`
<div class="image-zoomer-container">
  <img src="https://files.readme.io/1ad2b7e0c37b5d737bf6bd38c8740318f482cf2ced06df506d105f32233ebc6e-recurly_exports_erd_20241120.svg" alt="Zoomable Image" id="zoom-image">
</div>
`}</HTMLBlock>

<br />

* <HTMLBlock>{`
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Download Button</title>
      <style>
          .download-button {
              display: inline-block;
              padding: 5px 10px;
              text-align: center;
              text-decoration: none;
              color: #1C2833FF; 
              background-color: #F8F8F8FF; 
              border-radius: 5px;
              font-weight: normal;
              transition: background-color 0.5s ease, transform 0.3s ease;
            	transition: 0.4s !important;
              font-family: 'Proxima-nova', Arial, sans-serif;
              max-width: 100%; 
          }

          .download-button:hover {
              background-color: #FFFFFFFF; 
              transform: scale(1.02); 
          }
        	a:hover {
            	color: #888888FF;
            	text-decoration: underline !important;
          }
        </style>
  </head>
  <body>
      <a href="https://files.readme.io/1ad2b7e0c37b5d737bf6bd38c8740318f482cf2ced06df506d105f32233ebc6e-recurly_exports_erd_20241120.svg" class="download-button">Download the image</a>
  </body>
  </html>
  `}</HTMLBlock>
  <br />
* <HTMLBlock>{`
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Download Button</title>
      <style>
          .download-button {
              display: inline-block;
              padding: 5px 10px;
              text-align: center;
              text-decoration: none;
              color: #1C2833FF; 
              background-color: #F8F8F8FF; 
              border-radius: 5px;
              font-weight: normal;
              transition: background-color 0.5s ease, transform 0.3s ease;
            	transition: 0.4s !important;
              font-family: 'Proxima-nova', Arial, sans-serif;
              max-width: 100%; 
          }

          .download-button:hover {
              background-color: #FFFFFFFF; 
              transform: scale(1.02); 
          }
        	a:hover {
            	color: #888888FF;
            	text-decoration: underline !important;
          }
        </style>
  </head>
  <body>
      <a href="https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx" class="download-button">Download our complete export schema</a>
  </body>
  </html>
  `}</HTMLBlock>
  <br />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Export Name
      </th>

      <th>
        Export Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        [Accounts](https://docs.recurly.com/docs/accounts-export)
      </td>

      <td>
        Account-level information.
      </td>
    </tr>

    <tr>
      <td>
        [Account Notes](https://docs.recurly.com/docs/account-notes-export)
      </td>

      <td>
        Account notes that have been created on accounts.
      </td>
    </tr>

    <tr>
      <td>
        [Adjustments](https://docs.recurly.com/docs/adjustments-exports#section-adjustments)
      </td>

      <td>
        Each charge and credit adjustment, including tax information broken down by jurisdiction (country, state/province, county, city, special).
      </td>
    </tr>

    <tr>
      <td>
        [Adjustments - Coupons](https://docs.recurly.com/docs/adjustments-exports#section-adjustments-coupons)
      </td>

      <td>
        Each charge and credit adjustment broken out by discount per coupon redemption.

        _This export will only show on the Exports page if you have Multiple Coupons Per Account enabled under Coupon Settings._
      </td>
    </tr>

    <tr>
      <td>
        [Adjustments - Taxes](https://docs.recurly.com/docs/adjustments-taxes-export)
      </td>

      <td>
        The Adjustments - Taxes export is for reporting on taxes calculated through Vertex and Avalara for Communications (AFC).
      </td>
    </tr>

    <tr>
      <td>
        [Billing Info](https://docs.recurly.com/docs/billing-info-export)
      </td>

      <td>
        Billing information associated with accounts.
      </td>
    </tr>

    <tr>
      <td>
        [Coupons](https://docs.recurly.com/docs/coupons-export)
      </td>

      <td>
        All coupons that are set-up on the site.
      </td>
    </tr>

    <tr>
      <td>
        [Coupons - Bulk Unique Codes](https://docs.recurly.com/docs/coupons-export#section-coupons-bulk-unique-codes)
      </td>

      <td>
        All unique codes for a bulk coupon.
      </td>
    </tr>

    <tr>
      <td>
        [Coupon Redemptions](https://docs.recurly.com/docs/coupons-export#section-coupon-redemptions)
      </td>

      <td>
        All redemptions of coupons.
      </td>
    </tr>

    <tr>
      <td>
        [Credit Payments](https://docs.recurly.com/docs/credit-payments-export)
      </td>

      <td>
        All credit payments, encompassing the use of outstanding credit balances to pay invoices.
      </td>
    </tr>

    <tr>
      <td>
        [Gift Cards](https://docs.recurly.com/docs/gift-cards-export)
      </td>

      <td>
        All purchased gift cards.
      </td>
    </tr>

    <tr>
      <td>
        [Invoices — Accounts Receivable](https://docs.recurly.com/docs/accounts-receivable-export)
      </td>

      <td>
        All customers who have yet to settle their invoices and gives a detailed report on the aging of all unsettled receivables.
      </td>
    </tr>

    <tr>
      <td>
        [Invoices — External](https://docs.recurly.com/docs/invoices-external)
      </td>

      <td>
        All external invoices that are generated for accounts with subscriptions created on third-party platforms such as the Apple App Store or Google Play Store.
      </td>
    </tr>

    <tr>
      <td>
        [Invoices — Summary](https://docs.recurly.com/docs/invoices-summary)
      </td>

      <td>
        Invoice header information and summary totals.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        [Invoices - Unused Numbers](https://docs.recurly.com/docs/invoices-exports#section-invoices-unused-numbers)
      </td>

      <td>
        All invoice numbers not used for generated invoices.
      </td>
    </tr>

    <tr>
      <td>
        [Items — Associated Plans](doc:items-associated-plans)
      </td>

      <td>
        All plan add-ons created from a saved item in your Item Catalog.
      </td>
    </tr>

    <tr>
      <td>
        [Items — Associated Subscriptions](doc:items-associated-subscriptions)
      </td>

      <td>
        All subscription add-ons created from a saved item in your Item Catalog.-
      </td>
    </tr>

    <tr>
      <td>
        [Revenue Recognition Schedules](https://docs.recurly.com/docs/revenue-recognition-export)
      </td>

      <td>
        A Revenue waterfall for your charges on a monthly basis.

        _This export will only show on the Exports page if the site has the[Revenue Recognition feature](https://docs.recurly.com/v1.0/docs/revenue-recognition) enabled._
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions](https://docs.recurly.com/docs/subscriptions-exports)
      </td>

      <td>
        Your customers' subscriptions to your plans.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions Add-Ons](https://docs.recurly.com/docs/subscription-add-ons-export)
      </td>

      <td>
        All the detailed information about all the subscription add-ons created within a specific timeframe.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions Add-Ons — History](https://docs.recurly.com/docs/subscriptions-add-ons-history-export)
      </td>

      <td>
        All the changes made to a subscription add-on over time.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions — Churned](https://docs.recurly.com/docs/subscriptions-exports#section-subscriptions-churned)
      </td>

      <td>
        Subscriptions that have expired and are no longer active.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions — External](https://docs.recurly.com/docs/subscriptions-external)
      </td>

      <td>
        All the detailed information on external subscriptions stored on third-party platforms like the Apple App Store or Google Play Store.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions — History](https://docs.recurly.com/docs/subscription-history-export)
      </td>

      <td>
        The history of each subscription including all versions created following any change to a subscription.
      </td>
    </tr>

    <tr>
      <td>
        [Subscription — Usage Records](https://docs.recurly.com/docs/usages-records-export)
      </td>

      <td>
        Usage records logged for your customer's usage-based subscription add-ons.
      </td>
    </tr>

    <tr>
      <td>
        [Subscriptions — Ramp Pricing](https://docs.recurly.com/docs/subscription-ramp-pricing-export)
      </td>

      <td>
        All data on each subscription operating under a ramp priced billing model.
      </td>
    </tr>

    <tr>
      <td>
        [Transactions](https://docs.recurly.com/docs/transaction-export)
      </td>

      <td>
        Data sent to the payment gateway when processing a transaction.
      </td>
    </tr>
  </tbody>
</Table>

**Deprecated Exports**

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Export Name
      </th>

      <th>
        Export Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        [Invoices](https://docs.recurly.com/docs/invoices-exports#section-invoices-deprecated-) (Deprecated)
      </td>

      <td>
        * *Note:** this export is no longer actively maintained. It has now been replaced by two exports: Invoices - Summary and Adjustments

        Once your site has the Credit Invoices feature enabled, this export will no longer be available.
      </td>
    </tr>
  </tbody>
</Table>

## Exporting data via the admin console

Exports can be generated [through the admin console](https://app.recurly.com/go/exports). When you generate an export, you can also select a date range for the information you want to receive. Once you request the export, the request will begin processing. You can view the status of your request on the export page. Once your request is completed you'll see a "Download" link that you can then click to get the export.

All exports default to using ZIP compression.

### Examples: All accounts created in May

1. Navigate to **Analytics-> Exports.**
2. Change the date range to be **May 1 - May 31st.**
3. Select **Accounts** and leave _All_ chosen.
4. Click **Request Export**

### Example: All subscriptions that have expired

1. Navigate to **Analytics -> Exports.**
2. Leave the date range as **All Time.**
3. Select **Subscriptions - Churned.**
4. Click **Request Export**

### Example: All coupons redeemed in July

1. Navigate to **Analytics -> Exports.**
2. Change the date range to be **July 1 - July 31st**
3. Select **Coupon Redemptions.**
4. Click **Request Export.**

## Helpful tips: combining exports

Sometimes, the information you need will be split across more than one export. Excel will allow you to perform a join, and combine the exports. For instructions on combining exports, please see [this video][2].

[2]: https://www.youtube.com/watch?v=3tk_Mif7040
