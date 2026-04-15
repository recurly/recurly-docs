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
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Bulk Unique Coupons is a powerful feature provided by Recurly. It enables businesses to create a single coupon campaign consisting of numerous unique codes. These codes can be specifically targeted to customer segments and their redemption can be tracked and reported.

# Key benefits

* **Efficiency and scale:** Generate up to 5M unique codes in one campaign, significantly reducing the effort of creating individual codes.
* **Precision targeting:** Tailor your promotional campaigns by sharing unique codes with specific customer segments.
* **Insightful reporting:** Track code redemptions and discount effectiveness grouped under one campaign to understand the success of your marketing initiatives.
* **Improved marketing:** Understand which marketing methods lead to the most redemptions by tracking unique codes associated with each method.

# Generate codes in bulk

Create thousands of unique codes effortlessly for a single campaign, making large-scale promotions smooth and simple. Think big - we have you covered.

> **Note:** Any amount of coupons above 100K will require an override. Please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

### Maximum redemptions

Maximum redemptions will not show as an option in the Recurly UI when you select the "Bulk unique codes" option. By default, maximum redemptions are set to unlimited in order to allow your number of unique codes to be the limiting factor in redemptions. If you would like to set a maximum redemptions for your bulk coupon, you can do so through the API. If you set a maximum redemptions that is less than the number of unique codes generating, you are saying that not all unique codes can be redeemed, only those redeemed until the maximum redemptions are reached for the coupon.

### Redemptions per account

Redemptions per account will not show as an option in the Recurly UI when you select the "Bulk unique codes" option. By default, redemptions per account are set to "1". A unique code can only ever be redeemed once. If you want a customer to take part in the campaign more than once, you could set the redemptions per account to a number greater than one. This would allow a customer to redeem more than one unique code on their account. You can set redemptions per account to a number other than "1" through the API.

### Bulk coupon status management

Bulk coupons with all unique codes redeemed will be considered Expired in the UI, even though their true status is active in the API. In this case, you will be asked to add additional unique codes to the bulk coupon in order to restore the coupon through the UI.

* Bulk coupons are treated as expired in the UI when all unique codes are redeemed because they technically cannot be redeemed and we would like to reflect them as such in your Coupon tables.
* Bulk coupons require two separate API calls to be created. One to create the bulk coupon and one to generate the unique codes. We need to keep the status of the bulk coupon active when there are no redeemable unique codes so you can hit the generate unique codes endpoint without having to restore the bulk coupon each time. This is important for merchants who only want to create unique codes on the fly when a customer initiates a redemption request.
* If there are expired unique codes within the bulk coupon campaign, the bulk coupon will never expire if the remaining codes are all redeemed. The coupon will only expire if you manually expire the campaign or if the max redemptions or redeem by date are reached.

**To restore** a unique code within a bulk coupon campaign, **find the bulk coupon's overview page** and select "**Restore Code**" in the right hover actions in the row of the unique code.

# Bulk unique codes syntax

### Required prefix

Specify a prefix that will be the same across all unique codes.

* The prefix is the coupon code for the campaign as a whole.
* It must be unique across all redeemable coupons on your site.
* The prefix can be alphanumeric and may include a dash (-), underscore (_), or a plus sign (+).

### Generated code format

Specify the format of the dynamically generated portion of the code.

* This is the unique portion of the code.
* Format can be alphabetic, alphanumeric, or numeric.

### Generated code length

Specify the character length of the dynamically generated portion of the code.

* This is the unique portion of the code.
* Length does not include the prefix or optional suffix.
* Length must be at least 4 characters for alphabetic and alphanumeric formats, and 6 characters for numeric.
* Length cannot be longer than 50 characters.

### Optional suffix

You can choose to include a suffix at the end of each unique code. The suffix isn't dynamic and will remain across all unique codes.

* The suffix can be alphanumeric and may include a dash (-), underscore (_), or a plus sign (+).

### Unique code preview

The preview will show you a sample generated unique code reflecting your template choices. Note that the prefix and suffix are always separated from the dynamically generated portion with dashes. Your customers will need to enter the entire code, with dashes, at redemption. If you would like a different unique code template, or do not want to include dashes, you can <a href="#api">design your own template through the API</a>.

# Creating bulk unique codes

> **Note:**To extend the redeem-by date for your bulk unique coupon codes, you'll need to add more codes through the user interface. This is necessary even if you've generated a large number of codes already. It's important to note that there's a maximum limit of 100,000 unique codes. If you reach this limit, you won't be able to extend the redeem-by date further. It's advisable to plan ahead to manage your coupon codes within these constraints. If you need to extend the redeem-by date, it's better to do so before nearing the maximum code limit.

### Generate bulk coupons through the API

Once a bulk coupon template has been created, there are two options to create the bulk coupons codes.

1. **Asynchronous process:**  [Generate the bulk codes](https://recurly.com/developers/api/v2021-02-25/index.html#operation/generate_unique_coupon_codes) through one endpoint and then [retrieve those codes](https://recurly.com/developers/api/v2021-02-25/index.html#operation/list_unique_coupon_codes) through a second endpoint.  This process is great if you do not need the codes in real-time and want all codes generated with a single call.
2. **Synchronous process:** Generate bulk codes and receive those codes immediately in the response.  The number of codes that can be returned is limited to 200.  This is great if you do not want to create all of the codes in a single call and need just a few codes in real-time as you manage your coupon campaign.

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

### Generate bulk coupons through the Recurly UI

**Step 1: Start your campaign creation**

* Begin by navigating to your **Coupons Dashboard** in the **Recurly UI**.
* Here, select **'New Coupon'** and choose **'Bulk unique codes'** as your code type.

**Step 2: Design your codes**

* **Total number of codes**: Decide how many unique codes you want. You can choose anywhere from 1 to 100,000. Use numbers only in this field, no commas.
* **Required prefix**: Pick a starting set of letters or numbers that all your codes will have. This helps you recognize them easily.
* **Generated code format & length**: Choose the style and size of the unique part of each code.
* **Optional suffix**: Think of a fun or memorable ending for each code, if you like.
* **Unique code preview**: Check out a preview of what your codes will look like. Change anything if needed.

**Step 3: Tailor your campaign**

* **Configure Coupon**: Follow steps in the “Coupons & Discounts” in <a href="https://docs.recurly.com/docs/coupons#creating-and-customizing-coupons" target="_blank"><strong>this guide</strong></a>.

**Step 4: Launch Your Campaign**

* After setting all the details, click **'Create Coupon'**.

# Exporting and reporting on unique code redemptions

**Step 1: Access the Export Feature**

* Start by navigating to the **Coupons - Bulk Unique Codes** export section.
* Select your desired bulk coupon campaign from the dropdown menu.

**Step 2: Set Your Parameters**

* Change the **Export on** option to **"Modified"**. This ensures you're reviewing the most updated data.

**Step 3: Define Your Time Range**

* Set the **Time Range** to the specific dates you want to analyze. You choose the period that’s most relevant for you.

**Step 4: Download and Open Your Data**

* Click to **Download the CSV** file. This file is a treasure trove of data, ready for you to explore.

**Step 5: Filter Your Results**

* Open the CSV file and filter out all rows without a value in the **applied_at** column. This cleans your data by removing irrelevant entries.

**Step 6: Refine Your Data**

* Sort the **applied_at** date column and remove rows with dates outside of your set time range. This ensures your report is precise and focused.

With these steps, you've crafted a detailed report showcasing the redemptions of your unique codes within your chosen timeframe. This data is your key to understanding your campaign’s impact and to planning future promotional strategies that are even more successful.

Now, with the knowledge on how to create and track the results of your bulk coupon campaign, you are prepared to connect with your customers in meaningful ways.

# Manage and analyze your codes

### Export your unique codes

Need to dive deep into the data? Export a comprehensive list of your unique codes and their redemption history. Filter and focus on specific date ranges to understand your campaign’s impact over time.

### Expire coupons or specific codes

Have full control over your campaign's timeline. Retire all unique codes in a bulk, or selectively turn off specific codes when needed. You're in the driver's seat.

## Clear and detailed invoice insights

### Clarity in every transaction

Build trust with transparent billing. Each invoice neatly displays the redeemed unique codes, paired with the name of the coupon campaign, for easy and clear reconciliations.

## Comprehensive exports

### Coupons

Identify bulk unique coupon campaigns in your Coupons export. Search for “bulk” under the "coupon_type" column.

### Coupon redemptions

Track which unique codes have been redeemed, and by whom, in your Coupon Redemptions export.

### Coupons - bulk unique codes

For a detailed ledger of all unique codes in a bulk coupon, including redemption details, explore the Coupons - Bulk Unique Codes export.

For detailed instructions on exports, please consult our [Coupons Export Documentation](/docs/export-overview#coupons) and [Coupon Redemptions Export Documentation](/docs/export-overview#coupon_redemptions).
