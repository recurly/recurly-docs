---
title: Plans
excerpt: >-
  Streamline your billing process with Recurly's versatile and customizable
  plans. Establish varied pricing strategies, offer free trials, and create
  seamless user journeys through the Checkout and Hosted Payment Pages.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  image: https://files.readme.io/934dddc-Screenshot_2.png
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Recurly plans are the blueprint for your subscription business, orchestrating the frequency and amount your customers are charged. Whether your model includes free trials, optional add-ons, or initial setup fees, Recurly’s plans are designed to be a perfect match for your distinct business needs—and there’s no limit to the number of plans you can create.

# Key benefit

* **Tailored plan creation**: Mold your subscription plans with Recurly to fit your business like a glove. Configure options like:
  * **Trial periods**: Roll out enticing free or discounted trials to potential customers.
  * **Setup fees**: Implement one-time setup fees where applicable.
  * **Billing cycle lengths**: Specify the intervals for your billing cycles, from weekly to annually.
  * **Subscription term lengths**: Designate the length of subscription commitments.
  * **Renewal options**: Opt for subscriptions that either auto-renew or expire at term end.
  * **Pricing models**: Choose from fixed, ramp, or usage-based pricing to align with your revenue strategy.
  * **Price segments**: Create different price points with a single currency for specific customer segments on a single plan.
  * **Add-on features**: Augment plans with added services or products to upsell and enhance customer value.

## Dashboard

Your <a href="https://app.recurly.com/go/plans" target="_blank">plans dashboard</a> contains a list of plans defined in your Recurly account. You can select any plan name to view detailed plan information, edit the plan, or link to that plan's [Checkout](https://docs.recurly.com/docs/checkout) configuration or <a href="/docs/hosted" target="_blank">Hosted Payment Page</a>.

# Creating a plan

## Step 1: Create a new plan

From your main plan page, navigate to Configuration→Plans. Click on "New Plan."

<Image align="center" border={true} width="80% " src="https://files.readme.io/bc0ddaa4c88b375933ababdc2e75f4af992b177cef51df4efeed8f7f79b4f3f1-image.png" className="border" />

## Step 2:**Define** parameters

### **Plan Details**

<Image align="center" border={true} width="80% " src="https://files.readme.io/085cd9d0ffd02a7545515452a48328200dfbedb1cd74a1c4a6bd6c2444b1fe24-image.png" className="border" />

* **Plan Name**: This name describes your plan and appears on the Hosted Payment Page and the subscriber's invoice. Limit to 255 characters. Check with your payment gateway provider before using special characters.
* **Plan Code**: This is your plan's unique identifier on Recurly. It's used in Hosted Payment Page URLs and API fetch requests. Limit to 25 alphanumeric characters.
* **Plan Description**: Describe what the plan includes. This will appear on the subscriber's email invoice, if configured in email templates.

### **Plan Configuration**

* **Currencies**: Choose which of your **enabled** currencies to include in your plan.

<Image align="center" border={true} width="80% " src="https://files.readme.io/1e6fd5ac40d29b88bed2635fcbed5ad786025c3d2f68fc2cfcb988aa09ab1d4d-planConfiguration_currencyPicker.png" className="border" />

* **Free Trial**: Define a free period for the plan in days or months. The paid subscription starts after the trial period ends. Choose whether to require billing information at sign-up, offering flexibility to reduce initial barriers for new customers.

<Image align="center" border={true} width="80% " src="https://files.readme.io/33e11f60b02b189a65fe8e52c1c763b8bc1d0ae21c433c268c5845d3ebb02443-image.png" className="border" />

* **Setup Fee**: Include a one-time charge that is processed at the time of sign-up.

<Image align="center" border={true} width="80% " src="https://files.readme.io/6cd83f00615d5d2814588ceb461b5f2b7e82903ea10a18f1ff005926ca1d61f2-image.png" className="border" />

### **Billing Configuration**

<Image align="center" width="80% " src="https://files.readme.io/efa80b5db6b52990a9d51eb53785e7e6118dba207eac402e947f614e56352188-billingConfiguration.png" />

* **Billing period**: Set how often a subscriber will be billed.

* **Subscription term length** : Set the default length of time that customers are committed to a subscription. A subscription to this plan will always renew with this term unless the account’s individual subscription term is modified.

* **Billing cycles**: Decide to automatically renew or expire the subscription after a set number of billing periods in the “At end of subscription term” section.

### **Pricing Model**

* **Pricing model**: Set the pricing model that best suits the subscription. Choose from fixed or ramp, accordingly.
* **Price**: Set a fixed price to charge to a plan's subscribers. For Quantity-Based Pricing, use Add-Ons.

<Image align="center" width="80% " src="https://files.readme.io/acf01be91a70711bb406a12ae7e6c942b6c1e50f064a95653ed52b33058b713f-pricingModel.png" />

### **Price segments**

Use price segments to define different price points for a single plan within the same currency. This helps you A/B test pricing and avoid plan sprawl. A **default price** is always required and will be used whenever no segment code is provided.

**Example (by location):**
You own a gym and operating costs are higher in certain cities. Instead of cloning identical plans, create one plan with multiple price segments—e.g., `default`, `nyc`, `la`.

<Image align="center" border={true} width="80% " src="https://files.readme.io/33c2e19de5efdd80e17eec6a136477329165f9326657a0067ad33df32e57a5b1-Screenshot_2025-11-03_at_1.15.33_PM.png" className="border" />

#### How it works

* Recurly **stores** all segment prices and the default price on the plan.
* **You decide** which price to show or apply (geography, campaign, experiment bucket, etc.). Recurly does not choose the segment for you.
* Segment price data (segment **code** and **price**) is returned in our v3 **[APIs](https://recurly.com/developers/api/v2021-02-25/index.html#tag/price_segment)** and **[Recurly.js](https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/)** so your app or checkout can pick and display the intended price.

#### Implement it (quick path)

1. **Add segments on the plan.**
   In the plan’s Pricing section, create one or more segments and set a default.
2. **Decide your selection rule.**
   For example: if `city=NYC` use segment `nyc`; if user is in test group `B`, use segment `exp-b`.
3. **Expose the right price in your UI.**
   **Fetch** the plan’s price segments via the **[API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/get_plan)** or **[Recurly.js](https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/)** and **render** the price that matches your rule.
4. **Use the matching price at checkout.**
   When creating the purchase/subscription, **apply the chosen segment’s price**. If you don’t provide a segment, the **default** price is used.

> Tip: For A/B tests, name segments clearly (for example, `exp-a`, `exp-b`) and log the chosen segment code with your analytics event.

#### Notes and limits for price segmentation

* No limit to the number of price segments per currency.
* Available **only on plans** (fixed and ramp).
* **Not available** on setup fees, add-ons, items, or **Recurly Checkout**.
* You can **add** segments to existing plans at any time.
* After creation, **only the price** within a segment can be edited; the segment code stays the same.
* The **segment code** is **not** shown on invoices or in email templates (it’s for your internal selection logic).

#### Developer references

* **v3 APIs:** Use the plan pricing returned by **[APIs](https://recurly.com/developers/api/v2021-02-25/index.html)** to select and apply the correct price segment.
* **Recurly.js:** Surface the right price segment in your front end with **[Recurly.js](https://docs.recurly.com/recurly-subscriptions/docs/recurlyjs#/)**.

### **Billing details**

<Image align="center" width="80% " src="https://files.readme.io/74aa52e78f94702312f92e6fcafbbb00e8e7528eaacb5095a12d1c12261e4700-image.png" />

* **Accounting code**: Select a unique code to identify plans in your internal invoice exports. This code should be configured based on your specific tax settings and compliance requirements. Limit to 25 lowercase alphanumeric characters.
* **HS code/Commodity code**:  Enter a Harmonized System (HS) code or Commodity Code to meet invoice compliance requirements for traded products. Generally, HS Code consists of at least six digits, with countries adding more digits for further national or regional classification. Recurly limits to 25 lowercase alphanumeric characters.

### **Plan Add-ons**

<Image align="center" border={true} width="80% " src="https://files.readme.io/ace61210674443e1e3313351841cff1758a81a7db38f410e62a65578db65c699-image.png" className="border" />

* **Add-ons**: Optional products that can be included in a recurring subscription's invoices. Also supports Quantity-Based Pricing Models. You can add items from the Item Catalog to a plan.

### **Dunning Campaign**

<Image align="center" border={true} width="80% " src="https://files.readme.io/2016200d6fed0e474767bb6da138c4ad3f2091dd3b4783dfe1431da5c86ac551-dunningCampaign.png" className="border" />

* **Dunning campaign:** Select the dunning campaign for this plan.

### **Customer Emails**

<Image align="center" border={true} width="80% " src="https://files.readme.io/36c3e1eec931e2d3b84a0a1ca45bba5cb9601a358df9d48ac2f79672a58bb00c-customerEmails.png" className="border" />

* **Select the emails**: Check the boxes to enable email communication on specific matters. You can also modify and manage your templates on your Email Templates setting page.

### **Hosted Payment Pages**

* **Plan quantity can be edited**: Determine if subscribers can choose their own quantity on the Hosted Payment Pages.
* **Return URL after Success**: After a successful transaction via the Hosted Page, redirect the customer to a specific URL.
* **Bypass Recurly Confirmation**: If using the Hosted Payment Pages, choose to bypass Recurly's confirmation page and use a custom return URL.

<Image align="center" border={true} width="80% " src="https://files.readme.io/13991f75755f5e278537208a94c860cdb87a6801883974fac520d0d1ef2334f9-legacyHPP.png" className="border" />

3. Once all parameters are defined, **click** "Create Plan" to finalize.

# Checkout configurations

After a plan is configured, you can create [Checkout](https://docs.recurly.com/docs/checkout) configuration to direct customers to purchase your plan(s).

<Image align="center" border={true} width="30% " src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" className="border" />

# Updating plans

1. **Navigate** to Configuration→Plans.

2. Either from the plan list view (right option hover) or the plan actions drop down menu on a specific plan detail page, **select** "Edit."

<Image align="center" border={true} width="80% " src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" className="border" />

3. **Make** the desired changes and click "Save Changes".

**Note**: Changes will apply to new subscribers only. Existing subscribers will continue with the plan terms present at the time of their signup.

# Duplicating plans

1. **Navigate** to Configuration→Plans.

2. **Hover over** any row to reveal 3 additional options, then **select** "Duplicate".

<Image align="center" border={true} width="80% " src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" className="border" />

3. All details of the original plan will be copied to the "Create a Plan" page. "-copy" will be appended to the "Plan Name" and "Plan Code" fields.

<Image align="center" border={true} width="80% " src="https://files.readme.io/3b6b286cc277c222905012f1fcd013f9235bdcb54decb84f7d011e2cad611e78-dup_planDetails.png" className="border" />

4. **Adjust** these field names and modify any other fields as required for the new plan.
5. **Click** "Create Plan" once you've finished adjusting the details.

> **Note:** You can also duplicate plans after creating a plan. On the success info alert once a plan is created, there is an option to duplicate it.

# Deleting plans

1. Navigate to **Configuration** → **Plans**.

2. Either from the plan list view (right-option hover) or the plan actions dropdown on a specific plan detail page, select **Delete**.

<Image align="center" border={true} width="80% " src="https://files.readme.io/be953bbb65864484f35eb5cb51428ed06b2c966e5fe83ceacc2696557e976bb6-image.png" className="border" />

3. **Confirm** your decision.

<Image align="center" border={true} width="80% " src="https://files.readme.io/ced811d9006f4cb407e9866bc6bbb04513fa104e2f3ec05dfc31d00f16acaca3-delete.png" className="border" />

> **Notes**:
>
> * Deleting a plan is permanent and will prevent new customers from subscribing to it.
> * Existing subscriptions to this plan will continue to renew, but once a plan is deleted, it cannot be reactivated.
> * Any subscriptions tied to a deleted plan **cannot be edited** (e.g., frequency, price, add-ons) after the plan has been removed.
