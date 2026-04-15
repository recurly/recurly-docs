---
title: Subscriber wallet implementation guide
excerpt: >-
  Get set for a seamless payment management experience! Dive into our
  comprehensive guide on effectively leveraging the Subscriber Wallet on your
  Recurly site.
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

# Required plan

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

The "Subscriber Wallet" is an innovative payment management feature in Recurly that provides users the flexibility to maintain multiple payment methods and define their subscription-specific preferences.

# Key benefits

* **Simplified subscription management**: Effortlessly set or alter your primary payment method, and associate specific payment methods to particular subscriptions.
* **Enhanced user experience**: Accommodate up to 20 distinct payment methods, catering to diverse financial preferences and needs.
* **Optimized payment flow**: With automatic fallback to the primary method, ensure continuous service even when a specific payment mode fails.
* **Robust integration support**: Impeccably integrated with both Recurly's Product and API Documentation, promising an intuitive and comprehensive user experience.

# Step-by-step implementation

### **1. Setting a primary payment method**

Every Recurly account needs to have a primary payment method set up. This acts as the default method for any transactions where a specific payment mode isn't defined.  
**Steps**:

* **Initial Setup**: By default, the first payment method added to an account will be considered primary. If you're looking to set another method as primary later, you'll need to update the method's primary status.
* **Subsequent Additions**: When adding further payment methods, you can designate them as primary right at the moment of their creation. Remember, only one payment method can be primary at any given time.

### **2. Adding additional payment methods**

To give users flexibility, Recurly permits up to 20 payment methods per account. Each method has a distinct identifier to streamline subscription and payment linkages.  
**Steps**:

* Navigate to the "Add Payment Method" section within your Recurly dashboard.
* Enter the required payment details. This can range from credit card data, bank account details, or digital wallet specifics.
* Once added, the system will generate a unique `billing_info_id`. This ID can be used to set on specific subscriptions or purchase requests..

### **3. Using specific payment methods for subscriptions/purchases**

The power of the Subscriber Wallet lies in its capacity to allow users to link individual subscriptions to specific payment methods, providing exceptional control over financial transactions.  
**Steps**:

* **View Payment Methods**: First, fetch the list of available payment methods on your account. Each method will have its unique `billing_info_id`.
* **Link to Subscription**: While creating or updating a subscription, provide the desired `billing_info_id` to tether the subscription to that specific payment method.

### **4. Assigning a Payment Method to a Subscription**

Over time, subscribers may want to switch the payment method linked with specific subscriptions, either for better financial management or due to expiry of the current method.  
**Steps**:

* Navigate to the "My Subscriptions" tab on your dashboard.
* Select the subscription you wish to modify.
* Use the "Change Payment Method" option and provide the `billing_info_id` of your chosen payment method.

### 5. Managing multiple payment methods

Efficient management of multiple payment methods is crucial for subscribers to seamlessly switch between them as needed.  
**Steps**:

* **Accessing Payment Methods**: Use the `/accounts/billing_infos` endpoint to view all payment methods associated with an account.
* **Update or Delete**: Update details or delete a payment method using its `billing_info_id`. To update, send a PUT request to `/accounts/billing_infos/<billing_info_id>` with the necessary changes to the payment method's information, such as card or account number, and address details.
* **Changing the Primary Payment Method**: To set a payment method as primary, use a PUT request to `/accounts/billing_infos/<billing_info_id>` with `primary_payment_method=true`. This will also relegate the current primary method to a non-primary status.
* **Updating Billing Info During Transactions**: When making a purchase or creating a subscription via the `/purchases` or `/subscriptions` endpoints, billing info can be updated for accounts with existing billing infos. Follow these guidelines:
  * If `primary_payment_method` is true, the existing primary billing info will be updated.
  * If `primary_payment_method` is false, a new non-primary billing info will be created.
  * If `primary_payment_method` is not included, the existing primary billing info will be updated.

### **6. Modifying specific payment methods on the account**

There may be instances where specific payment details change, such as a new card's issuance or a change in billing address.  
**Steps**:

* Locate the desired payment method in your Subscriber Wallet.
* Use the “Edit” option and modify the necessary details. For significant modifications, like changing from one card to another, you may need the specific `billing_info_id`.
* Ensure to save any changes made to retain modifications.  
  Remember, every business has unique needs. Tailor these steps according to your operational priorities for a seamless implementation of the Subscriber Wallet.  
  By adhering to this guide, Recurly users can fully harness the capabilities of the Subscriber Wallet, ensuring an optimal subscription management experience. Always keep a close eye on the latest updates to stay ahead of the curve.

### Managing payment methods

* **Avoid repetition**: Do not repeatedly input identical billing info for the same account when creating subscriptions or making one-time purchases. Doing so will create duplicate payment methods on the account. An error message will appear once the account reaches 20 payment methods.  To help prevent duplicate entries, consider using Recurly's [blocking feature](https://docs.recurly.com/recurly-subscriptions/docs/payment-settings#duplicate-billing-infos-prevention). 
* **Opt for reference**: Add unique billing info only once per account. For future purchases or subscriptions, refer to this information using the `billing_info_id`.
