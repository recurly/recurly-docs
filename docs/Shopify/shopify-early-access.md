---
title: Shopify Early Access
excerpt: As of March 2025, Recurly is now available in the Shopify App Store.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Purpose-built for enterprise shops, our Shopify app makes it easy to diversify your revenue and scale with ease. Integrated directly into Shopify admin, the Recurly app enables features like auto-ship, mixed-cart purchases, free trials, customizable coupons, and a customer portal—all with no-code installation. Once integrated, you’ll have access to Recurly’s advanced features like customized dunning, intelligent payment retries, and robust analytics to help you engage and retain your customers.

### Prerequisites

To participate in Early Access, merchants must must first [schedule a demo](https://recurly.com/request-a-demo/). Recurly will answer any questions, and support merchants through the setup and testing.

<br />

# Definition

For merchants selling via a Shopify store, they can now leverage Recurly to offer subscriptions and power a reliable, recurring revenue stream.

# Key benefits

### Simple setup and management to accelerate growth

* Reduce deployment time and technical overhead with our no-code installation
* Streamline setup, billing and customer management with our native admin integration
* Easily create and manage promos with our coupon functionality

### Build loyalty with seamless customer experiences

* Leverage Shopify checkout and ShopPay for a seamless, accelerated checkout experience
* Customers can mix their carts with any combination of subscriptions and one-time purchases
* Our customer portal makes it easy for your subscribers to easily update their information

# Key details

Follow the steps in order, and reach out to Recurly as needed.

## Create a test Shopify store

Utilize one of the two methods below to create a test Shopify store. You are also welcome to use an existing test store.

* Log into your Shopify account [here](https://www.shopify.com/store-login)
  * Click the top right button, which is the name of the current store you are logged into.
  * Select "All stores", and then click "+ Create store"
* If you are a Shopify partner, log in [here](https://partners.shopify.com/organizations) and follow these instructions to create a free test store
  * From your Partner Dashboard, click Stores.
  * Click Add store > Create development store.
  * In the Development store use section, select Create a store to test and build.
  * In the Store details section, enter a name for your store.
  * In “Data and Configurations”, select “Start with an empty store”

## Configure your test Shopify store

**Pre-requisite** Your Shopify store should not have any existing Products, nor Discounts. Recurly will support migrating those very soon.

Navigate to Shopify Admin of your store, and complete the following steps

* In Settings -> Checkout, select “Require first and last name” in “Customer information”
* In Settings -> Payment, activate the test payment provider, or set your payment provider (e.g., Adyen, Shopify Payments) to test mode. For now, let’s activate the test payment provider (bogus gateway) by following [these Shopify instructions](https://help.shopify.com/en/partners/dashboard/managing-stores/test-orders-in-dev-stores#testing-using-bogus-gateway).
  * You can also click “See all other providers”, and navigate to the top entry, which is the bogus gateway.
* Recurly requires that payment info is captured in Shopify Checkout, so that Shopify can successfully charge your customer and vault the payment info.
  * If you are using a manual payment method, reach out to Recurly Support.
  * If payment is not configured, your customer will see “This store can’t accept payments right now.” when trying to checkout.

## Create, and configure a Recurly site

For Early Access merchants, Recurly will take care of this step. There a few required configurations, and feature flags that need to be set for the integration with Shopify. Once created and configured, Recurly will provide you Admin access to your test Recurly site.

## Install the Recurly Shopify app into your test Shopify store

* Click the Shopify App Store URL Recurly provided, to navigate to the Recurly Subscriptions App
* Before you click Install, verify you are in the correct Shopify store by clicking the colored square on the top right of the Recurly application page.
* Click Install
* You will be directed to your Shopify store, and presented a model to Install the app. Review the requested permissions, and click Install

## Configure the embedded Recurly Subscriptions App within Shopify