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

* **Custom plan configuration**: Shape subscription plans using Recurly, tailoring to your business needs with customizable billing and term options.
* **Trial and pricing flexibility**: Offer attractive trials and select from diverse pricing models to match your revenue goals.
* **Enhanced offerings**: Boost value with supplemental services or products, optimizing customer upsell opportunities.

## Dashboard

Your <a href="https://app.recurly.com/go/plans" target="_blank">plans dashboard</a> contains a list of plans defined in your Recurly account. You can select any plan name to view detailed plan information, edit the plan, or link to that plan's [Checkout](https://docs.recurly.com/docs/checkout) configuration or <a href="/docs/hosted" target="_blank">Hosted Payment Page</a>.

# Creating a plan

1. From your main plan page, navigate to Configuration > Plans. Click on "New Plan."

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/a4a863f-Screenshot_2023-12-04_at_3.57.47_PM.png" />

2. Define the following parameters:

**Plan Details**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/1672628-image.png" />

* **Plan Name**: This name describes your plan and appears on Checkout, the Hosted Payment Page and the subscriber's invoice. Limit to 255 characters. Check with your payment gateway provider before using special characters.
* **Plan Code**: This is your plan's unique identifier on Recurly. It's used in Hosted Payment Page URLs and API fetch requests. Limit to 25 alphanumeric characters.
* **Plan Description**: Describe what the plan includes. This will appear on the subscriber's email invoice, if configured in email templates.

**Plan Configuration**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/e349c91-image.png" />

* **Free Trial**: Define a free period for the plan in days or months. The paid subscription starts after the trial period ends. Choose whether to require billing information at sign-up, offering flexibility to reduce initial barriers for new customers.

* **Setup Fee**: Include a one-time charge that is processed at the time of sign-up.

**Billing Configuration**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/b5efa62-image.png" />

* **Billing Period**: Set how often a subscriber will be billed.

* **Subscription Term Length** : Set the default length of time that customers are committed to a subscription. A subscription to this plan will always renew with this term unless the account’s individual subscription term is modified.

* **Billing Cycles**: Decide to automatically renew or expire the subscription after a set number of billing periods in the “At end of subscription term” section.

**Pricing Model**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/893eb4b-Screenshot_2023-12-04_at_4.00.46_PM.png" />

* **Pricing model**: Set the pricing model that best suits the subscription. Choose from fixed or ramp, accordingly.
* **Price**: Set a fixed price to charge to a plan's subscribers. For Quantity-Based Pricing, use Add-Ons.

**Billing Details**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/3a4c1ee-image.png" />

* **Accounting Code**: Select a unique code to identify plans in your internal invoice exports. This code should be configured based on your specific tax settings and compliance requirements. Limit to 25 lowercase alphanumeric characters.

**Plan Add-ons**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/91a70ab-image.png" />

* **Add-ons**: Optional products that can be included in a recurring subscription's invoices. Also supports Quantity-Based Pricing Models. You can add items from the Item Catalog to a plan.

**Dunning Campaign**

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/ccd4429-image.png" />

* Dunning campaign: Select the dunning campaign for this plan.

**Customer Emails**

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/7cbd8bb-image.png" />

* **Select the emails**: Check the boxes to enable email communication on specific matters. You can also modify and manage your templates on your Email Templates setting page.

**Hosted Payment Pages**

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/c75ae00-image.png" />

* **Plan quantity can be edited**: Determine if subscribers can choose their own quantity on the Hosted Payment Pages.
* **Return URL after Success**: After a successful transaction via the Hosted Page, redirect the customer to a specific URL.
* **Bypass Recurly Confirmation**: If using the Hosted Payment Pages, choose to bypass Recurly's confirmation page and use a custom return URL.

3. Once all parameters are defined, click "Create Plan" to finalize.

# Checkout Configurations

After a plan is configured, you can create [Checkout](https://docs.recurly.com/docs/checkout) configuration to direct customers to purchase your plan(s).

<Image align="center" width="60% " src="https://files.readme.io/5812722bde5118573fa786b4a575e1b615b8688042c796f0ed304b1bcfdb1165-Screenshot_2024-10-14_at_4.57.29_PM.png" />

# Updating plans

1. Navigate to Configuration > Plans.

2. Either from the plan list view (right option hover) or the plan actions drop down menu on a specific plan detail page, select "Edit."

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/089ae61-Screenshot_2023-12-04_at_4.07.51_PM.png" />

3. Make the desired changes and click "Save Changes".

**Note**: Changes will apply to new subscribers only. Existing subscribers will continue with the plan terms present at the time of their signup.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/8413e57-Screenshot_2023-12-04_at_4.09.56_PM.png" />

# Duplicating plans

1. Navigate to Configuration > Plans.

2. Either from the plan list view (right option hover) or the plan actions drop down menu on a specific plan detail page, select "Duplicate."

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/e04262c-Screenshot_2023-12-04_at_4.17.21_PM.png" />

3. All details of the original plan will be copied to the "Create a Plan" page. "-copy" will be appended to the "Plan Name" and "Plan Code" fields.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/3d2bb6b-image.png" />

4. Adjust these field names and modify any other fields as required for the new plan.
5. Click "Create Plan" once you've finished adjusting the details.

   <Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/31fe761-Screenshot_2023-12-04_at_4.11.39_PM.png" />

> **Note:** You can also duplicate plans after creating a plan. On the success info alert once a plan is created, there is an option to duplicate it.

# Deleting plans

1. Navigate to **Configuration** → **Plans**.

2. Either from the plan list view (right-option hover) or the plan actions dropdown on a specific plan detail page, select **Delete**.

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/8d7ec73-Screenshot_2023-12-04_at_4.17.21_PM_copy.png" />

3. Confirm your decision.

<Image align="center" className="border" border={true} width="75% " src="https://files.readme.io/1adb766-Screenshot_2023-12-04_at_4.14.06_PM.png" />

> **Note**:
>
> * Deleting a plan is permanent and will prevent new customers from subscribing to it.
> * Existing subscriptions to this plan will continue to renew, but once a plan is deleted, it cannot be reactivated.
> * Any subscriptions tied to a deleted plan **cannot be edited** (e.g., frequency, price, add-ons) after the plan has been removed.