---
title: Implementing Shopify
excerpt: >-
  The Recurly Subscriptions App connects Recurly to Shopify to power your
  subscriptions
deprecated: false
hidden: true
metadata:
  robots: index
---
# Prerequisites

Merchants must reach out to their Recurly Account Manager, or <a href="https://support.recurly.com/hc/en-us/requests/new?ticket_form_id=360000302852" target="_blank" rel="noopener noreferrer">create a ticket</a>. Recurly will answer any questions, and support merchants through the setup and testing.

# Key details

Follow the steps in order, and reach out to Recurly as needed.

## Create a test Shopify store

Utilize one of the two methods below to create a test Shopify store. You are also welcome to use an existing test store.

* As a Shopify partner, you can create test stores for free which is the recommended path. To become a Shopify partner, sign up via [this link](https://partners.shopify.com/signup?locale=en) . Log in as a Shopify partner [here](https://partners.shopify.com/organizations), and then follow the below steps.
  * From your Partner Dashboard, click Stores.
  * Click Add store > Create development store.
  * In the Development store use section, select Create a store to test and build.
  * In the Store details section, enter a name for your store.
  * In “Data and Configurations”, you can either select “Start with an empty store” or "Start with test data" depending on your preference.
* An alternate method is to log into your Shopify account, and create a store. Please note that this method many incur a cost. Log into your Shopify account [here](https://www.shopify.com/store-login), and then follow the below steps.
  * Click the top right button, which is the name of the current store you are logged into.
  * Select "All stores", and then click "+ Create store".

## Configure your test Shopify store

Navigate to Shopify Admin of your store, and complete the following steps

* In Settings -> Checkout, select “Require first and last name” in “Customer information”
* In Settings -> Payment, activate the test payment provider, or set your payment provider (e.g., Adyen, Shopify Payments) to test mode. For now, let’s activate the test payment provider (bogus gateway) by following [these Shopify instructions](https://help.shopify.com/en/partners/dashboard/managing-stores/test-orders-in-dev-stores#testing-using-bogus-gateway).
  * You can also click “See all other providers”, and navigate to the top entry, which is the bogus gateway.
  * If you created your store with test data, the bogus gateway should already be configured.
* Recurly requires that payment info is captured in Shopify Checkout, so that Shopify can successfully charge your customer and vault the payment info.
  * If you are using a manual payment method, reach out to Recurly.
  * If payment is not configured, your customer will see “This store can’t accept payments right now.” when trying to checkout.

## Create, and configure a Recurly site

For now, Recurly will take care of this step. There a few required configurations, and feature flags that need to be set for the integration with Shopify. Once created and configured, Recurly will provide you Admin access to your test Recurly site.

## Install the Recurly Shopify app into your test Shopify store

* Click the Shopify App Store URL Recurly provided, to navigate to the Recurly Subscriptions App
* Before you click Install, verify you are in the correct Shopify store by clicking the colored square on the top right of the Recurly application page.
* Click Install
* You will be directed to your Shopify store, and presented a modal to Install the app. Review the requested permissions, and click Install

## Configure the embedded Recurly Subscriptions App within Shopify

Note: You can click the Pin icon to pin the Recurly Subscriptions app to your left navigation

* Follow the Setup guide and connect your Recurly site by adding an API key from Recurly
* Once connected with Recurly, navigate to Products and create at least one test product if you do not already have published products within your Shopify product catalog. Be sure the product is published to the “Online Store” sales channel, and has available inventory.
* Resume with the Recurly Setup guide, and create a subscription plan with one of those test products
* Continue with the Setup guide, and install the Recurly subscription widget into your theme. The widget will be dropped into the “Default product” page. You can move it around as desired within that page.

Once done with the configuration of the embedded app, follow these steps to provide a link within the default Shopify portal to direct customers to the Recurly portal to manage their subscription.

* Navigate within Shopify Admin to Settings -> Checkout. Click Customize next to your Configuration.
* Click Checkout in the top center, change to Orders
* Click Section from the far left nav.
* Click Add app block, and add the "Customer Portal Link". It should look like the attached screenshot in the next thread post.

## Run a test order to demonstrate a successful subscription purchase

By completing the steps above, the install and configuration steps are complete. Let's now run a test order.

* Click the eye icon to the right of Online Store from the left navigation, and go into your online store
* Find the product, and check out.
* For the credit card, use the following for the credit card number (assuming you are using the bogus gateway)
  * 1 - To Simulate an Approved Transaction
  * 2 - To Simulate a Declined Transaction
  * 3 - To Simulate a Gateway Failure
  * Any three numbers can be used as the "Card Security Code" and any expiry date in the future will work.

Once the purchase is complete, log into your Recurly site and look at the latest Subscription in Customers. If you can see a subscription related to the test order (aka: purchase), you have completed the configuration. The subscription should have customer data, charges and credits, invoices, transactions, and activity.

## Additional testing information

If you run into issues or have suggestions, be sure to talk with your Recurly contact about those. It is important to test several different scenarios (e.g., mixed cart purchase of a hardware product and software subscription) to be sure everything is working as expected.

In addition to testing, it is important to read the FAQs below.

While you are testing, Recurly will request partner access to your test Shopify store. This allows Recurly to better support you.

## Next Steps

When testing is complete, you will work closely with Recurly for next steps regarding customer communication and timeline. Recurly will help ensure the transition is seamless. Even after you are live with Shopify and Recurly, Recurly remains with you to ensure success and help if any issues arise.

## FAQs

### Is there anything else I need to know regarding testing?

Yes, two things.

1. When testing the Recurly subscription portal, the portal will open in another tab. Some browsers may block the popup by default, so check your popup settings if the portal does not appear.
2. The app proxy URL associated with the Recurly Subscription app should not change. This URL is pre-defined for the Recurly Subscription app within your Shopify Admin settings.

### Are there any known limitations with this Early Access release?

Given this is an early release, there are some limitations. These will be addressed over time.

* Google Pay, Apple Pay, PayPal, and ShopPay are not yet supported. They will be very soon. Recurly currently supports credit card payments via Shopify Checkout.
* Pre-paid (e.g., bill annually, delivery monthly) subscriptions are not yet supported.
* There are certain types of Shopify discounts that are not yet supported on Recurly. The following two, “Buy X get Y” and “Free Shipping”, are not supported.
* There are certain discount requirements that are not supported. These requirements will be shared soon.
* There are character limitations to be mindful of between Shopify and Recurly
  * Coupon codes need to 50 character or less
  * Product title and Variant title need to be 255 characters or less when combined
  * external\_sku for a Product needs to be 50 characters or less
* The following Recurly revenue recovery features do not apply in the Shopify model. In this partnership with Shopify, Shopify is handling those features given Shopify owns the customer payment information.
  * Account updater, expiration date changes, backup payment method

### If a subscriber subscribes via Shopify, and also Recurly, are they duplicated in Recurly?

No. If a Recurly account (aka: customer) is already present with the same e-mail address as the new Shopify customer, Recurly will match that subscriber with the existing Recurly account.

### What changes from Recurly sync back to Shopify?

For Early Access, only these subscription changes (cancel, pause, expire) are synced back to Recurly. In future releases, Recurly will sync back additional pertinent information.

### Is there one customer portal for everything?

No. Shopify always provides a default customer portal, focused on order information, profile information, and billing information. That portal will continue to exist. Recurly also provides a portal, but more focused on the subscription management aspects (e.g., cancel subscription). When logged into the Recurly customer portal, the customer can see information about their active subscription, and past orders.

In a future release, the portals will be more integrated and Recurly will continue to add more valuable features (e.g., change quantity of products in an active subscription) over time.