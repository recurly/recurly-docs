---
title: 'Shopify integration: best practices'
excerpt: >-
  A comprehensive overview of best practices, tips, and important considerations
  when integrating Shopify with Recurly.
deprecated: false
hidden: true
metadata:
  robots: index
---
The Shopify-Recurly integration combines Shopify’s powerful storefront and checkout features with Recurly’s advanced subscription billing and management capabilities. Although the integration handles most processes seamlessly, there are several important details and limitations to be aware of when setting up and managing your storefront.

## Key best practices

### 1. Install the Recurly App before creating products and discounts

Install the Recurly Subscriptions app in Shopify prior to adding products or discounts to your store. This helps ensure that both new products and discounts are properly tracked and recognized by the Recurly integration from the start.

### 2. Require first and last names at checkout

Configure Shopify Checkout to require both first and last names. Recurly needs a first name to successfully create subscriptions. If a checkout is submitted without this information, the integration will fail to create the corresponding Recurly subscription.

### 3. Ensure valid payment methods

Make sure shoppers are required to provide valid payment information at checkout. If a subscription is created without a valid payment method, the integration will fail to import or maintain that subscription in Recurly.

### 4. Avoid custom order edits and items

When editing an unfulfilled order, refrain from:

* Adding custom discounts not tied to a legitimate Shopify discount code.
* Inserting custom items that do not exist in Recurly.

These actions are not compatible with the integration and may not register correctly in Recurly.

### 5. Adhere to character limits

Recurly enforces certain character limits to maintain consistency:

* Coupon codes: 50 characters or fewer
* Combined product and variant titles: 255 characters or fewer
* external\_sku for products: 50 characters or fewer

Exceeding these limits can cause issues when creating or syncing items.

### 6. Manage discounts and coupons carefully

The following discount-related features are currently not supported or have limitations in the Recurly-Shopify integration:

* “Buy X, Get Y” coupons
* Free shipping discounts
* Automatic discounts within Shopify
* Bulk coupon code creation
* Setting a future activation date, minimum purchase requirements, or restricted eligibility (e.g., specific customers)

For coupons to work properly, ensure they apply to subscriptions and meet Recurly’s character and syntax restrictions. Coupons also must be active immediately (no delayed start date).

### 7. Understand Revenue Recovery limitations

Certain Recurly revenue recovery features do not apply in the Shopify model, including:

* Account updater for stored payment methods
* Expiration date changes
* Backup payment methods

Additionally, net terms are effectively zero, and if a renewal payment fails, dunning begins 24 hours later by default.

### 8. Enable multiple subscriptions to the same plan (If Needed)

If you want customers to be able to purchase multiple subscriptions to the same plan (for example, multiple monthly subscriptions of a single product), you must enable the “Allow multiple subscriptions to the same plan” setting in your Recurly site.

### 9. Keep inventory in mind for renewals

The integration does not perform an inventory check prior to renewal billing attempts. Even if an item is out of stock, the integration will proceed with the renewal order in Shopify.

### 10. Provide a customer portal link and allow pop-ups

To give customers an easy way to manage their subscriptions, add the “Customer Portal Link” block to the Orders section within Shopify’s theme customizer. In addition, browsers must allow pop-ups to view Recurly subscription details directly from Shopify Admin. When customers click “View Subscription,” Shopify will open the Recurly embedded app and then redirect in a new tab, which some browsers may block.

### 11. Avoid changing the app proxy URL

Do not modify the App Proxy URL assigned to the Recurly Subscriptions app within Shopify. This URL is crucial for handling subscription management requests. Changing it may break the integration or disable the customer portal link.

### 12. Recognize inherent model differences

Some actions, such as reactivating canceled or expired subscriptions, are not natively supported by Shopify. Once a subscription is canceled in Shopify, you cannot reactivate it using Recurly’s reactivation feature; a new subscription must be created instead.

### 13. Requesting access to a merchant store

If you need direct access to a merchant’s Shopify store (for troubleshooting or additional configuration), use the Shopify Partner Dashboard to request access. This ensures your team can effectively set up and support the store.