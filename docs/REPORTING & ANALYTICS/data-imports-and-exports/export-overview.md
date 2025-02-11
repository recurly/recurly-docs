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

- Users must have Analytics user role permission.

# Exports overview

- All of the exports listed in the below table  are available through the [admin console](https://app.recurly.com/go/async_exports) and the Recurly API. 

- Exports will use the site timezone (under Site Settings) rather than the users timezone when determining what data will be exported. Additionally, the days that are requested will be exported in their entirety rather than potentially having missing data for current day.

- See [New Versions](https://docs.recurly.com/v1.0/docs/export-overview#section-export-versions) for information about how changes to individual exports will create new versions of that export. 

- See [Automated Exports](https://docs.recurly.com/v1.0/docs/export-overview#section-automated-exports) for more information about access via the Recurly API.

- See our **Recurly Exports ERD**:

[block:html]
{
  "html": "<div class=\"image-zoomer-container\">\n  <img src=\"https://files.readme.io/1ad2b7e0c37b5d737bf6bd38c8740318f482cf2ced06df506d105f32233ebc6e-recurly_exports_erd_20241120.svg\" alt=\"Zoomable Image\" id=\"zoom-image\">\n</div>"
}
[/block]


<br />

- [block:html]{"html":"<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #888888FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://files.readme.io/1ad2b7e0c37b5d737bf6bd38c8740318f482cf2ced06df506d105f32233ebc6e-recurly_exports_erd_20241120.svg\" class=\"download-button\">Download the image</a>\n</body>\n</html>\n\n"}[/block]
  <br />
- [block:html]{"html":"<!DOCTYPE html>\n<html lang=\"en\">\n<head>\n    <meta charset=\"UTF-8\">\n    <meta http-equiv=\"X-UA-Compatible\" content=\"IE=edge\">\n    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">\n    <title>Download Button</title>\n    <style>\n        .download-button {\n            display: inline-block;\n            padding: 5px 10px;\n            text-align: center;\n            text-decoration: none;\n            color: #1C2833FF; \n            background-color: #F8F8F8FF; \n            border-radius: 5px;\n            font-weight: normal;\n            transition: background-color 0.5s ease, transform 0.3s ease;\n          \ttransition: 0.4s !important;\n            font-family: 'Proxima-nova', Arial, sans-serif;\n            max-width: 100%; \n        }\n\n        .download-button:hover {\n            background-color: #FFFFFFFF; \n            transform: scale(1.02); \n        }\n      \ta:hover {\n          \tcolor: #888888FF;\n          \ttext-decoration: underline !important;\n        }\n      </style>\n</head>\n<body>\n    <a href=\"https://docs.google.com/spreadsheets/d/1U0_Wl_NMScJqKBZoBKMmQnybmLEr0gFi6r7dfNiP9Qc/export?format=xlsx\" class=\"download-button\">Download our complete export schema</a>\n</body>\n</html>\n\n"}[/block]
  <br />

[block:parameters]
{
  "data": {
    "h-0": "Export Name",
    "h-1": "Export Description",
    "0-0": "[Accounts](https://docs.recurly.com/docs/accounts-export)",
    "0-1": "Account-level information.",
    "1-0": "[Account Notes](https://docs.recurly.com/docs/account-notes-export)",
    "1-1": "Account notes that have been created on accounts.",
    "2-0": "[Accounts Receivable](https://docs.recurly.com/docs/accounts-receivable-export)",
    "2-1": "All unpaid invoices and associated aging of receivables.",
    "3-0": "[Adjustments](https://docs.recurly.com/docs/adjustments-exports#section-adjustments)",
    "3-1": "Each charge and credit adjustment, including tax information broken down by jurisdiction (country, state/province, county, city, special).",
    "4-0": "[Adjustments - Coupons](https://docs.recurly.com/docs/adjustments-exports#section-adjustments-coupons)",
    "4-1": "Each charge and credit adjustment broken out by discount per coupon redemption.  \n  \n_This export will only show on the Exports page if you have Multiple Coupons Per Account enabled under Coupon Settings._",
    "5-0": "[Adjustments - Taxes](https://docs.recurly.com/docs/adjustments-taxes-export)",
    "5-1": "The Adjustments - Taxes export is for reporting on taxes calculated through Vertex and Avalara for Communications (AFC).",
    "6-0": "[Billing Info](https://docs.recurly.com/docs/billing-info-export)",
    "6-1": "Billing information associated with accounts.",
    "7-0": "[Coupons](https://docs.recurly.com/docs/coupons-export)",
    "7-1": "All coupons that are set-up on the site.",
    "8-0": "[Coupons - Bulk Unique Codes](https://docs.recurly.com/docs/coupons-export#section-coupons-bulk-unique-codes)",
    "8-1": "All unique codes for a bulk coupon.",
    "9-0": "[Coupon Redemptions](https://docs.recurly.com/docs/coupons-export#section-coupon-redemptions)",
    "9-1": "All redemptions of coupons.",
    "10-0": "[Credit Payments](https://docs.recurly.com/docs/credit-payments-export)",
    "10-1": "All credit payments, encompassing the use of outstanding credit balances to pay invoices.",
    "11-0": "[Invoices — Accounts Receivable](https://docs.recurly.com/docs/accounts-receivable-export)",
    "11-1": "All customers who have yet to settle their invoices and gives a detailed report on the aging of all unsettled receivables.",
    "12-0": "[Invoices — External](https://docs.recurly.com/docs/invoices-external)",
    "12-1": "All external invoices that are generated for accounts with subscriptions created on third-party platforms such as the Apple App Store or Google Play Store.",
    "13-0": "[Invoices — Summary](https://docs.recurly.com/docs/invoices-summary)",
    "13-1": "Invoice header information and summary totals.",
    "14-0": "[Gift Cards](https://docs.recurly.com/docs/gift-cards-export)",
    "14-1": "All purchased gift cards.",
    "15-0": "[Invoices - Unused Numbers](https://docs.recurly.com/docs/invoices-exports#section-invoices-unused-numbers)",
    "15-1": "All invoice numbers not used for generated invoices.",
    "16-0": "[Items — Associated Plans](doc:items-associated-plans)",
    "16-1": "All plan add-ons created from a saved item in your Item Catalog.",
    "17-0": "[Items — Associated Subscriptions](doc:items-associated-subscriptions)",
    "17-1": "All subscription add-ons created from a saved item in your Item Catalog.-",
    "18-0": "[Revenue Recognition Schedules](https://docs.recurly.com/docs/revenue-recognition-export)",
    "18-1": "A Revenue waterfall for your charges on a monthly basis.  \n  \n_This export will only show on the Exports page if the site has the [Revenue Recognition feature](https://docs.recurly.com/v1.0/docs/revenue-recognition) enabled._",
    "19-0": "[Subscriptions](https://docs.recurly.com/docs/subscriptions-exports)",
    "19-1": "Your customers' subscriptions to your plans.",
    "20-0": "[Subscriptions Add-Ons](https://docs.recurly.com/docs/subscription-add-ons-export)",
    "20-1": "All the detailed information about all the subscription add-ons created within a specific timeframe.",
    "21-0": "[Subscriptions Add-Ons — History](https://docs.recurly.com/docs/subscriptions-add-ons-history-export)",
    "21-1": "All the changes made to a subscription add-on over time.",
    "22-0": "[Subscriptions — Churned](https://docs.recurly.com/docs/subscriptions-exports#section-subscriptions-churned)",
    "22-1": "Subscriptions that have expired and are no longer active.",
    "23-0": "[Subscriptions — External](https://docs.recurly.com/docs/subscriptions-external)",
    "23-1": "All the detailed information on external subscriptions stored on third-party platforms like the Apple App Store or Google Play Store.",
    "24-0": "[Subscriptions — History](https://docs.recurly.com/docs/subscription-history-export)",
    "24-1": "The history of each subscription including all versions created following any change to a subscription.",
    "25-0": "[Subscription — Usage Records](https://docs.recurly.com/docs/usages-records-export)",
    "25-1": "Usage records logged for your customer's usage-based subscription add-ons.",
    "26-0": "[Subscriptions — Ramp Pricing](https://docs.recurly.com/docs/subscription-ramp-pricing-export)",
    "26-1": "All data on each subscription operating under a ramp priced billing model.",
    "27-0": "[Transactions](https://docs.recurly.com/docs/transaction-export)",
    "27-1": "Data sent to the payment gateway when processing a transaction."
  },
  "cols": 2,
  "rows": 28,
  "align": [
    "left",
    "left"
  ]
}
[/block]


**Deprecated Exports** 

[block:parameters]
{
  "data": {
    "h-0": "Export Name",
    "h-1": "Export Description",
    "0-0": "[Invoices](https://docs.recurly.com/docs/invoices-exports#section-invoices-deprecated-) (Deprecated)",
    "0-1": "**Note:** this export is no longer actively maintained. It has now been replaced by two exports: Invoices - Summary and Adjustments  \n  \nOnce your site has the Credit Invoices feature enabled, this export will no longer be available."
  },
  "cols": 2,
  "rows": 1,
  "align": [
    "left",
    "left"
  ]
}
[/block]


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