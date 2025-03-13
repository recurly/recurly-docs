---
title: Shopify Integration
excerpt: >-
  Shopify Integration: Your comprehensive guide to integrating Shopify with
  Recurly for seamless recurring billing and subscription management.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Prerequisites

* Active Shopify account (or a free test store via the Shopify Partner Dashboard)
* Active Recurly account with a non-Production site configured
* Basic understanding of API integrations and webhooks
* Required access to the Recurly Shopify App and appropriate permissions

### Limitations

* **Payment Support**: Only credit card payments via Shopify Checkout are supported.
* **Subscription Types**: Pre-paid subscriptions (e.g., billing annually with monthly delivery) are not supported for both existing and new subscriptions.
* **Discounts**: Shopify discounts such as “Buy X get Y” and “Free Shipping” are not supported.
* **Character Restrictions**:
  * Coupon codes must be 50 characters or less.
  * Combined Product and Variant titles must not exceed 255 characters.
  * The external\_sku for a Product must be 50 characters or less.
* **Revenue Recovery Features**: Account updater, expiration date changes, and backup payment methods are not applicable in the Shopify model.

# Definition

Shopify Integration with Recurly enables merchants to automate recurring billing by connecting their Shopify store to Recurly’s subscription management platform. The integration capitalizes on Shopify Checkout for payment processing while using Recurly’s backend for subscription handling, ensuring a smooth and efficient customer experience.

# Key Benefits

* **Seamless Integration**: Easily connect your Shopify storefront with Recurly for a streamlined recurring billing experience.
* **Optimized Checkout Process**: Leverage Shopify Checkout to capture payment details securely while using Recurly’s robust billing engine.
* **Efficient Subscription Management**: Automate subscription processes, reducing manual tasks and ensuring consistency across platforms.

# Setup Shopify and Recurly

Follow the steps below in the order shown to set up your integration:

1. **Create or Utilize a Test Shopify Store**
   * **For Standard Merchants**: Log into your Shopify account [here](https://www.shopify.com/login).
   * **For Shopify Partners**:
     * Log in to your Partner Dashboard.
     * Navigate to **Stores** and click **Add store** → **Create development store**.
     * Select **Create a store to test and build**.
     * Enter your store’s name and select **Start with an empty store**.
   * **Note**: Do not create any Products or Discounts at this stage.

2. **Configure Shopify Checkout**
   * In your Shopify Admin, go to **Settings → Checkout**.
   * Under **Customer Information**, select **Require first and last name**.
   * Verify the setting by scrolling to the Customer Information section.

3. **Set Up Payment Provider**
   * Navigate to **Settings → Payment** in Shopify Admin.
   * Activate the test payment provider (such as the bogus gateway) or set your existing provider (e.g., Adyen, Shopify Payments) to test mode.
   * Ensure payment information is captured so that Shopify can successfully charge and vault customer details.
   * **Important**: If payment isn’t properly configured, customers will see “This store can’t accept payments right now.”

4. **Configure Your Recurly Site**
   * **Custom Fields**:

     In **Configuration → Custom Fields**, create a new custom field with:

     * **API Field Name**: `subscription_source`
     * **Recurly Object**: Subscription
     * **Admin Console Field Name**: Subscription Source
   * **Currencies**:

     In **Configuration → Currencies**, enable any additional currencies you plan to transact in.
   * **Coupons**:

     Under **Coupons → Coupon Settings**, enable:

     * **Multiple Coupons Per Account**
     * **One-Time Charges**: (For any configuration not available through the Admin Console, contact Recurly Support via the #support Slack channel.)
   * **Site Settings**: Enable **Allow multiple subscriptions to the same plan** and activate the feature flag **tax\_inclusive\_pricing**.

5. **Install the Recurly Shopify App**
   * Visit the [Recurly Shopify app listing](https://apps.shopify.com/recurly-subscriptions) (ensure you are in the correct Shopify store by verifying the colored square at the top right).
   * Click **Install** and review the requested permissions.
   * After installation, locate the embedded Recurly app under **Apps** and consider pinning it for easy access.
   * Follow the in-app Setup guide:
     * Connect your Recurly site by adding an API key.
     * Create at least one test product (ensure it’s published to the “Online Store” sales channel and has available inventory).
     * Create a subscription plan linked to the test product.
     * Install the Recurly subscription widget into your theme—by default, it is added to the “Default product” page (you may reposition it as needed).

6. **Configure the Customer Portal Link**
   * In Shopify Admin, navigate to **Settings → Checkout** and click **Customize** next to your Checkout configuration.
   * Switch to the **Orders** view.
   * From the left navigation, click **Section**, then **Add app block**.
   * Add the **Customer Portal Link** block to provide customers with a direct link to the Recurly portal for managing subscriptions.

7. **Run a Test Order**
   * From Shopify Admin, click the eye icon next to **Online Store** to preview your storefront.
   * Locate your test product and proceed to checkout.
   * For credit card testing (using the bogus gateway), use:
     * **1** to simulate an approved transaction.
     * **2** to simulate a declined transaction.
     * **3** to simulate a gateway failure.
     * Use any three-digit number for the Card Security Code and any future expiry date.
   * Finally, log into your Recurly site to confirm the creation of the related Account and Subscription.

8. **Supplemental: Using Adyen as the Test Payment Provider**
   * Find Adyen in the list of payment providers and click **Install**.
   * When prompted, select **Test account** and provide the necessary username, account, and password details.

<Cards columns={2}>
  <Card title="Do Not Change the App Proxy URL" icon="fa-lock">
    In Shopify Admin, go to **Settings → Apps and sales channels**, click on the Recurly Subscriptions app, and locate the **App Proxy URL**. This URL must remain unchanged to avoid breaking the subscription customer portal.
  </Card>

  <Card title="Customer Portal Access" icon="fa-external-link-alt">
    Customers must enable popups in their browsers to access the Recurly customer portal from Shopify.
  </Card>
</Cards>

## FAQs

#### **Q**: **If a subscriber subscribes via both Shopify and Recurly, are they duplicated in Recurly?**

No, the systems match subscribers based on their email address.

#### **Q: What changes from Recurly sync back to Shopify?**

Only subscription status changes, such as cancellations or pauses, are synced back.

#### **Q: Is there one customer portal for everything?**

No. Shopify provides one portal for profile updates, while Recurly manages subscription-related actions.

* Customers should use the Shopify portal for updating their profile information and the Recurly portal for managing subscriptions.

#### **Q: Can we reactivate a canceled or expired subscription?**

No. Although Recurly supports reactivation, Shopify does not support this natively. Instead, a new subscription is created.