---
title: Create subscription
excerpt: >-
  Dive into the seamless experience of creating subscriptions with Recurly's
  user-centric design and powerful features.
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

A subscription allows customers to access your products or services for a specified period. By creating a subscription with Recurly, you can automate the recurring billing process, offer trials, and customize subscription options tailored to each customer's needs.

# Key benefits

* **Flexibility:** Offer subscriptions that start immediately, with a trial, or at a future date.
* **Customization:** Override the default settings to set up tailor-made subscriptions, including prices, term length, and add-ons.
* **Automation:** Let Recurly handle the billing, freeing you to focus on enhancing your product and serving your customers.
* **Multiple integration options:** Whether it's via the Admin Console, Hosted Payment Pages, or the API, choose the method that best suits your business.
* **Enhanced customer experience:** With features like automatic renewals and multiple currency support, provide a smooth and localized customer journey.

# How to create a subscription

The journey to create a subscription is straightforward, and Recurly offers multiple avenues to do so:

1. **Checkout:** Simplify the buying process for your customers while providing your business with robust, customizable capabilities. [Learn more about Recurly's Checkout experiences.](https://docs.recurly.com/docs/checkout).
2. **Hosted payment pages:** This out-of-the-box solution allows customers to subscribe via a checkout page dedicated to each of your plans. Once a successful subscription is created, Recurly takes care of setting up an account for the customer, embedding their subscription and billing details. [Learn more about Recurly's Hosted Payment Pages](https://docs.recurly.com/docs/hosted-payment-pages).
3. **Admin console:** For a more hands-on approach, the Admin Console lets you either set up a new customer account or leverage an existing one. Navigate to the **Account Actions** dropdown, choose **Add Subscription**, and follow the process.
4. **API integration:** For businesses looking for a more integrated approach, Recurly's API offers a comprehensive method. Dive into the [implementation guide](/docs/implementation-guide) for detailed steps and best practices.

## Creating a subscription in Recurly

1. **Navigate** to “Customers” → Accounts.
2. **Select** an account.

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/286d380-image.png" />

3. **Press** "Add subscription".

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/930c6d6-image.png" />

4. **Fill** in all of the fields, described below:

**Subscription Details**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/0abf905-image.png" />

This section captures the core aspects of the subscription.

* **Plan**: The core subscription model the customer is choosing. This is a mandatory field as it determines the features or services the subscriber will access.
* **Currency**: This is the currency in which the customer will be billed. Essential for businesses operating across different regions.
* **Price per billing period**: Indicates the amount a customer will be charged each cycle. This can be specified per unique subscription created, though Recurly can also auto-populate it based on the chosen plan & respective plan configuration.
* **Quantity**: Represents how many units of the plan the subscriber is opting for. This could correspond to the number of users, licenses, or any other measurable metric relevant to the subscription.
* **Description, billing period, setup fee, and trial length**: These fields auto-populate from the default settings defined during the creation of the subscription. They offer information about the plan, the frequency of billing, any initial fees, and if there's a trial period involved.

**Add-ons**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/4a5ace5-image.png" />

In this section, additional services or features can be added to the main subscription. These could be supplementary tools, extended capacities, or any other value-added elements that aren't part of the core plan.

**Timing**

<Image align="center" width="50% " src="https://files.readme.io/cdb8cbc7e651652fc28050c1ac4998fdc88c16cdb52b6e8db4f3a3cc98ab5304-StartSubPastDate.png" />

This section dictates when and how long the subscription lasts:

* **Start subscription**: Choose to begin the subscription immediately or set a future date for its commencement.
* **Subscription term**: Define the length of the initial subscription in terms of billing periods, e.g., 12 monthly billing cycles would imply a year-long subscription.
* **At the end of the subscription term**: Decide the behavior post the completion of the initial term - whether to automatically renew the subscription or let it expire.
* **Renewal subscription term**: If opting for auto-renewal, specify the length of the renewal term in billing periods.

**Shipping**

For products or services that require physical delivery, **check** the "Include Shipping" box and **enter** a new shipping address to ensure accurate delivery.

<Image align="center" alt="Add a shipping fee if required." border={true} caption="Add a shipping fee if required." src="https://files.readme.io/bf72b16-image.png" width="50% " />

<Image align="center" alt="Fill in the shipping address details." border={true} caption="Fill in the shipping address details." src="https://files.readme.io/1e44366-image.png" width="50% " />

**Coupons & gift cards**

Here, any promotional codes or discounts can be applied. Coupons might offer a percentage off, a fixed amount reduction.

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/9b65d37-image.png" />

Subscribers can redeem gift cards. This could either cover the entire subscription cost or provide a partial offset.

**Invoicing**

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/0f3e081-image.png" />

This section focuses on the billing specifics:

* **Collection method**: Select a payment collection method from the dropdown menu, including direct debit, credit card, online gateways, or other methods.
  * **Automatic collection**: Upon invoice generation, Recurly will attempt to collect payment using the billing information associated with the account.
  * **Manual collection**: Payment collection will not be initiated upon invoice generation. Instead, the merchant will handle payment collection externally (e.g., via check) and will manually update the invoice to "paid" in Recurly once payment is received and processed outside of the platform.
* **PO number**: Fill in the Purchase Order number if it's relevant to the transaction.
* **Note to customer**: Add any specific messages or instructions for the subscriber.
* **Terms and conditions**: Specify the legal clauses, policies, and stipulations that the subscriber agrees to during the transaction.

4. Lastly, always preview the invoice before finalizing. It provides a glimpse into the financial documentation generated for the customer. Not only does it bolster accuracy, but it also fosters confidence in the subscription process. If you need more granular control or face any hiccups, don't hesitate to reach out to Recurly's support team at [support@recurly.com](mailto:support@recurly.com).

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/2ddc27f-image.png" />

## Subscription options considerations

#### Subscription purchase option

If you're integrating with the Purchase API, you can combine one-time charges, subscriptions, and other purchase-related components into a single invoice. This makes it easier for businesses with complex sales cycles to generate one invoice for a customer. See [Purchase API](https://docs.recurly.com/docs/purchase) for further details.

#### Custom fields

Recurly provides the ability to define custom fields at the subscription level. These fields are useful for tracking additional data about a subscription. Maybe you need to track a customer's internal user ID or a specific code associated with the subscription. [Learn more about custom fields](https://docs.recurly.com/docs/custom-fields).

#### Net terms

Depending on the business, sometimes there is a need to allow customers a specific number of days after an invoice date to make a payment. Recurly allows you to set net terms at the subscription level, and this will determine how many days the customer has to pay the invoice before it's considered past due.

#### Backup payment method

Recurly offers businesses the flexibility to have a backup payment method. If the primary payment method fails, Recurly will attempt to collect the payment using the backup payment method. This increases the chances of successful payment collection.

#### Notes on subscription

Allows you to add internal notes to a subscription. These notes are only visible in the admin console and can be useful for internal communication or reminders about a particular subscription.

## Billing information requirement

For automatic collections, Recurly generally mandates valid billing details. However, for manual collections, billing info isn't a prerequisite. If you wish to bypass the billing information requirement for automatic subscriptions, you can either:

1. Opt for a [cardless free trial](https://docs.recurly.com/docs/plans#section-free-trials-without-billing-information).
2. Utilize a [gift card](https://docs.recurly.com/docs/gift-cards#section-billing-information) to start the subscription.

# How to create multiple subscriptions

An account isn't limited to a single subscription. Whether you're aiming to provide multiple access points to the same plan or diverse plans, Recurly has you covered. Here's how:

1. **Adjusting quantity:** Simply tweak the **Quantity** field for a plan to increase the number of subscriptions.
2. **Different renewal periods:** Create multiple iterations of the same plan for varied renewal cycles.
3. **API's Purchase Endpoint:** If you're leaning towards API integration, leverage this to create an array of subscriptions, either similar or different, all culminating in a consolidated invoice. For a detailed overview, check out [Multiple Subscriptions](https://docs.recurly.com/docs/multiple-subscriptions).