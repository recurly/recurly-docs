---
title: Bulk unique coupons
excerpt: >-
  Amplify your promotional campaigns with the 'Bulk Unique Coupons' feature of
  Recurly. Efficiently generate, manage, and track thousands of unique coupon
  codes, all under one campaign.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<br />

# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Limitations

* Campaigns exceeding 100,000 codes require an override — contact your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for details
* The synchronous API generation endpoint returns a maximum of 200 codes per call
* Maximum redemptions and redemptions per account settings are not configurable in the Recurly UI for bulk unique codes — these must be set via API
* To extend the redeem-by date on a bulk unique coupon, you must add more codes through the UI. This is not possible once you've reached the 100,000-code limit, so plan ahead
* Custom code templates (e.g., without dashes) are only available via API

***

# Definition

Bulk Unique Coupons is a Recurly feature that lets you create a single coupon campaign made up of thousands of individually unique codes. Each code can be targeted to specific customer segments, tracked individually, and reported on as part of one unified campaign — making large-scale promotions straightforward to manage.

***

# Key benefits

* **Efficiency at scale:** Generate up to 5 million unique codes in a single campaign, eliminating the need to create individual codes one by one.
* **Precision targeting:** Share unique codes with specific customer segments to tailor your promotional campaigns.
* **Insightful reporting:** Track redemptions and discount effectiveness grouped under one campaign to understand what's working.
* **Marketing attribution:** Identify which marketing channels drive the most redemptions by associating unique codes with each method.

***

# Key details

## Maximum redemptions

When the **Bulk unique codes** option is selected, the maximum redemptions field is hidden in the Recurly UI. By default, maximum redemptions are set to unlimited — the number of unique codes acts as the natural limiting factor.

To set a maximum redemptions value, use the API. If you set a maximum lower than the total number of unique codes generated, redemptions will stop once the maximum is reached, even if unused codes remain.

## Redemptions per account

When **Bulk unique codes** is selected, the redemptions per account field is also hidden in the UI. By default, this is set to one — each unique code can only ever be redeemed once.

To allow a customer to redeem more than one unique code on their account, set redemptions per account to a value greater than one via the API.

## Bulk coupon status management

Bulk coupons appear as **Expired** in the UI when all unique codes have been redeemed, even though their underlying API status remains active. This is by design — it reflects that the coupon can't currently be redeemed — and prompts you to add more codes to restore it.

A few things to keep in mind:

* The API status remains active (even with no redeemable codes) so you can hit the generate unique codes endpoint without needing to restore the coupon first. This is important for merchants who generate codes on demand at the time of a redemption request
* If the campaign contains any expired unique codes, the bulk coupon itself will never automatically expire as long as remaining codes are still redeemable. The coupon only expires if you manually expire it, or if the max redemptions count or redeem-by date is reached

To restore a specific unique code within a campaign, navigate to the bulk coupon's overview page and select **Restore Code** from the hover actions in that code's row.

***

## Bulk unique code syntax

### Required prefix

The prefix is the shared identifier for the campaign as a whole.

* Must be unique across all redeemable coupons on your site
* Can be alphanumeric and may include a dash (-), underscore (_), or plus sign (+)

### Generated code format

Defines the character type for the dynamically generated, unique portion of each code.

* Options: alphabetic, alphanumeric, or numeric

### Generated code length

Defines the character length of the dynamically generated portion.

* Minimum length is four characters for alphabetic and alphanumeric formats, and six characters for numeric
* Maximum length is 50 characters
* Does not include the prefix or optional suffix

### Optional suffix

A static string appended to the end of every unique code. Like the prefix, it remains the same across all codes.

* Can be alphanumeric and may include a dash (-), underscore (_), or plus sign (+)

### Unique code preview

A sample code reflecting your current template settings appears in the preview. Note that the prefix and suffix are always separated from the generated portion by dashes — customers must enter the full code, including dashes, at redemption.

To use a different template format or remove dashes, [design your own template via the API](#api).

***

## Creating bulk unique codes

### Via the Recurly UI

1. Navigate to your **Coupons** dashboard and select **New Coupon**
2. Choose **Bulk unique codes** as the code type
3. Configure your code template:
   * **Total number of codes** — enter a value between 1 and 100,000 (numbers only, no commas)
   * **Required prefix** — the shared identifier for all codes in the campaign
   * **Generated code format and length** — defines the style and size of the unique portion
   * **Optional suffix** — a static ending appended to every code
   * **Unique code preview** — review a sample code before proceeding
4. Configure your coupon settings by following the steps in the [Coupons & Discounts guide](https://docs.recurly.com/docs/coupons#creating-and-customizing-coupons)
5. Click **Create Coupon**

### Via the API

Once a bulk coupon template is created, you have two options for generating codes:

**Asynchronous** — [Generate codes](https://recurly.com/developers/api/v2021-02-25/index.html#operation/generate_unique_coupon_codes) via one endpoint, then [retrieve them](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_unique_coupon_codes) via a second. Best when you don't need codes in real time and want to generate a large batch in a single call.

**Synchronous** — [Generate and receive codes](https://recurly.com/developers/api/v2021-02-25/index.html#operation/generate_unique_coupon_codes_sync) immediately in the response. Limited to 200 codes per call. Best when you need a small number of codes on demand as part of a real-time redemption flow.

**Path:** `/coupons/code-20off/generate_sync`

**Request:**

```json
{
  "number_of_unique_codes": 1
}
```

**Response:**

```json
{
    "object": "unique_coupon_code_generation",
    "unique_coupon_codes": [
        {
            "id": "yde3fqeku6ghm",
            "object": "unique_coupon_code",
            "code": "20off-kngm-def",
            "state": "redeemable",
            "bulk_coupon_id": "ywe3dlf0eef5",
            "bulk_coupon_code": "20off",
            "created_at": "2026-04-08T19:57:56Z",
            "updated_at": "2026-04-08T19:57:56Z",
            "redeemed_at": null,
            "expired_at": null
        }
    ]
}
```

***

## Exporting and reporting on redemptions

To generate a report of unique code redemptions for a specific time period:

1. Navigate to the **Coupons — Bulk Unique Codes** export section
2. Select your bulk coupon campaign from the dropdown
3. Set the **Export on** option to **Modified**
4. Set your desired **Time Range**
5. Download the CSV file
6. In the CSV, filter out any rows without a value in the **applied_at** column
7. Sort the **applied_at** date column and remove rows with dates outside your selected time range

For full export instructions, see the [Coupons Export documentation](/docs/export-overview#coupons) and [Coupon Redemptions Export documentation](/docs/export-overview#coupon_redemptions).

***

## Managing your codes

### Expiring codes

You can expire an entire bulk coupon campaign or individual codes at any time from the coupon's overview page.

### Invoice display

Each invoice that includes a redeemed unique code displays both the code itself and the name of the coupon campaign it belongs to, making reconciliation straightforward.

***

## Exports reference

| Export                          | What it contains                                                                           |
| :------------------------------ | :----------------------------------------------------------------------------------------- |
| **Coupons**                     | Identifies bulk unique coupon campaigns. Filter by `"bulk"` under the `coupon_type` column |
| **Coupon redemptions**          | Shows which unique codes have been redeemed and by which accounts                          |
| **Coupons — Bulk unique codes** | A full ledger of all unique codes in a bulk coupon campaign, including redemption details  |
