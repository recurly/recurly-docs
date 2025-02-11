---
title: Ramp pricing
excerpt: >-
  Ramp up your subscription strategy with flexible, future-proof pricing models
  with Recurly's Ramp Pricing feature. Strategically define price adjustments
  over time to cater to diverse customer acquisition and retention needs.
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

This feature is only available to customers on the Professional and/or Elite subscription plan. To request to upgrade to this plan, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

### Prerequisites

Feature **Only Bill What Changed** must be enabled to use the Ramp Pricing feature. If your account was created before May, 2018, the feature **Credit Invoices** must also be enabled. Contact [support](mailto:support@recurly.com) to have these features added to your account.

# Definition

Ramp Pricing is a unique feature provided by Recurly that allows businesses to define price increases or decreases for a subscription over specific billing periods. This helps in implementing introductory pricing or customer loyalty schemes more seamlessly.

# Key benefits

* **Customer acquisition & retention**: Utilize Ramp Pricing to create attractive introductory prices, which can increase over time, making it an efficient customer acquisition strategy. Similarly, reward loyal customers with a pricing model that decreases over time, boosting customer retention.
* **Future price adjustments**: Establish a plan with a single price point and add future price ramps when necessary, giving you the flexibility to adapt to market changes or business strategies.

# Key details

Ramp Pricing is a unique feature in Recurly's repertoire that brings innovative pricing strategies to your fingertips. With Ramp Pricing, you can define a series of prices that change over time, creating 'ramps'. The introductory price can be lower at the start to attract new customers, and the price can incrementally increase over time. On the contrary, to reward loyal customers, prices can decrease over a certain period.

With this flexible pricing model, you can devise strategies that cater to different customer segments, business models, or market situations. From customer acquisition to customer retention, Ramp Pricing has you covered.

# Creating a plan with ramp pricing

1. **Navigate** to the 'Plans' activity on your Recurly Admin Console and click on 'New Plan'.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/0d6fd0e-Step_1.png" />

2. **Fill out** all the necessary fields. Under ‘Billing Configuration,’ whichever you select for end-of-subscription-term behavior–either ‘auto renew term’ or ‘expire subscription’–will not affect the ramp for the length of the subscription. In the 'Pricing Model' section, select 'Ramp' from the dropdown menu.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/776f024-Step_2.png" />

3. **Enter** the price per billing period for your first ramp. The price can be set to increase or decrease depending on your strategy.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/feaf205-Step_3.png" />

4. To add more ramps, **click on** 'Add another ramp'. You can add up to 12 ramps to a single plan.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/2885fbc-Step_4.png" />

5. Once your plan is created, **you can view** it in the 'Plans' section. The price displayed will be the initial price of the first ramp interval.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/a5cf870-Step_5.png" />

6. To **edit** your ramp priced plan, **navigate** to it and select 'Edit Plan'. Here you can modify the ramp intervals and pricing as necessary.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/113d4a9-Step_6.png" />

> 👍 A note on multiple currencies
>
> If your site has multiple currencies enabled, you can specify a price on each ramp for each currency.
>
> <Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/d297244-Plan_with_Multiple_Currencies.png" />

# Creating a subscription with ramp pricing

1. Within the Recurly Admin Console, **click** 'Add Subscription' on an account.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/0f60395-sub_create_-_step1.png" />

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/3840d4e-sub_create_-_step1a.png" />

2. **Select** the ramp priced plan you'd like to add to the subscription.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/026956a-sub_create_-_step2.png" />

3. By default, the subscription will use the ramp pricing schedule from the plan.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/be53cb3-sub_create_-_step3.png" />

4. If you need to change the ramp pricing schedule, **click** the 'Edit Pricing' link.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/e1fa048-sub_create_-_step4.png" />

5. **You can modify** the price changes in the side dialog. These changes will be unique to this subscription.
6. **Click** 'Apply Changes' and you'll see the updates reflected in the Pricing Schedule.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/307ffa0-sub_create_-_step6.png" />

7. **Save** the Subscription Edit form for the changes to take effect.

With Ramp Pricing, you are set to transform your pricing strategy, offering dynamic pricing options that evolve with your customers and business needs.

# Editing a subscription with ramp pricing

1. **Start** by clicking “Edit Subscription”.

<Image align="center" width="75% " src="https://files.readme.io/39f09af-edit_-_step_1.png" />

2. **Note** that only immediate changes can be made to the ramp pricing schedule. To initiate these changes, select “Edit Pricing”.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/4144501-edit_-_step_2.png" />

3. At this point, **you can add** more price changes or alter the price and duration of an upcoming price change. You also have the option to adjust the price for the current billing period.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/322092c-edit_-_step_3.png" />

4. After making the desired changes, **click** "Apply Changes". This will reflect your updates in the Pricing Schedule. **Note** that if you've modified the price of the current billing period, a prorated invoice will be generated.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/eb31281-edit_-_step_4.png" />

5. Finally, **save** the edited Subscription form to apply these changes.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/929dcb7-edit_-_step_5.png" />

## Changing plans on a subscription

You can change the base plan of your customers' subscriptions at your convenience. This change can be implemented immediately, at the billing date, or at renewal.

When altering a plan, you can modify the ramp interval schedule for the new plan. This enables you to remove any introductory ramp price intervals and switch directly to the full price, without creating a new plan or saving the subscription first and making a subsequent change.

*Example: If a customer is on a lower-priced plan and has completed the intro ramp interval pricing, and is now paying full price for their subscription. If the customer wishes to upgrade their subscription to a higher-priced plan, you can switch them to that subscription at the full price point, bypassing the initial ramp intervals.*

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/34de9d9-Changing_plans_on_a_subscription.png" />

## Additional insights and factors

Ramp Pricing is fully compatible with all other Recurly features including coupons, gift cards, trials, aligning renewals, pausing/resuming subscriptions, changing plans, and modifying subscriptions. Here are some specific considerations to be aware of:

### Pausing subscriptions

* Subscriptions with ramp pricing can be scheduled for pause or paused directly. 
* The ramp interval schedule pauses along with the subscription, and will resume once the subscription is unpaused. 
* Scheduled pauses will be canceled and subscriptions will be unpaused if the pricing schedule is modified. This aligns with how pauses are applied to fixed price subscriptions.
* Modifying the pricing schedule triggers the subscription to unpause and an invoice for the next billing cycle is created.

### Trials for subscriptions

Trials can be offered in tandem with Ramp Pricing. 

* Set up the duration of the trial.
* The price of the first ramp interval will be charged once the trial period ends.

<Image align="center" className="border" width="75% " border={true} src="https://files.readme.io/45e601c-Ramp_Sub_with_Trial.png" />

### Ramp price change: Renewal email notification template

An email template is available to inform customers about upcoming price changes.

* You can set up the Ramp Price Change email template under Subscription Renewal templates in your email configuration.
* This email will be dispatched when a new ramp interval is commencing.
* New email parameters supporting this template include: \{\{next\_ramp\_interval\_start\_date}}, and \{\{next\_ramp\_interval\_price}}.
* If the Ramp Price Change email is scheduled for the same day as other reminder templates, it will be prioritized.

### Support for exports

We've added and updated exports to aid in reporting subscriptions with ramp pricing.

* The new export titled 'Subscriptions - Ramp Pricing Export' provides detailed information for each ramp interval per subscription. [See the documentation](https://docs.recurly.com/docs/subscription-ramp-pricing-export).
* Exports 'Subscriptions', 'Subscription - History', and 'Subscriptions - Churned' now include two new columns, namely: pricing\_model and current\_ramp\_id.

### Recurly analytics

* Assess the performance of your ramp priced plans via dashboards within the Plans, Promotions & Pricing section of Analytics.

### Activity logs

* Activity logs give a comparison of before and after changes were made to a ramp priced subscription.
* This facilitates customer service representatives in determining if a price change has already been made to the pricing schedule, and if another change should be made.

### Checkout and Hosted Pages

* Checkout and Hosted Payment Page will show the "Starting Price" of the subscription, which is the price of the first ramp interval. Additional pricing details need to be displayed on your page where the customer is directed from.
* The Hosted Account Management Page will show the cost of the next ramp interval at the next invoice date.

### Salesforce integration

* Ramp priced subscriptions can be created via Salesforce, using the default ramp intervals from the plan.

### Transitioning from test mode to production mode

Ramp Pricing can be tested on all Recurly sites in sandbox or development mode, but is only available in production for sites on Recurly's Professional or Elite plans.

Upon conversion from a sandbox or development site to a production site on our Core plan, all Ramp Priced plans will be deleted. These deleted plans cannot be edited or re-enabled while on the Core plan. However, once upgraded to a Pro or Elite plan, Ramp Priced plans can be created and used for subscriptions.

# Migrating existing subscribers

If you plan on using Ramp Pricing for all your plans and subscriptions, the following options will help you do so:

### New subscribers

* **Step 1**: Generate new ramp-priced plans for new and/or existing subscribers. 
* **Step 2**: Offer these new ramp-priced plans to new subscription sign-ups. This lets your new subscribers enjoy automatic price changes on their subscription, eliminating any previous workarounds.

### Existing subscribers

* **Step 1**: Develop new ramp-priced plans for new and/or existing subscribers. 
* **Step 2**: Use the subscription change <a href="https://developers.recurly.com/api/v2021-02-25/index.html#operation/create_subscription_change" target="_blank">endpoint</a> to shift existing subscribers to a new ramp-priced plan. This change will cause the subscription to adopt the base ramp pricing schedule from the plan. After the subscription is on a ramp plan, you can modify the pricing schedule as necessary.

### General considerations about ramp pricing

* Ramp intervals can be an increase or decrease in price.
* A maximum of 12 intervals can be assigned to plans and subscriptions.
* Prices for ramp intervals can be set in all currencies configured on your site.
* A subscription must be created from a plan that already has ramp intervals to have ramp intervals itself.
* Ramp intervals can extend beyond the subscription term.
* Ramp intervals can exceed a subscription term when the term is set to auto-renew. In this case, intervals will continue at the configured interval once a new subscription term starts.
