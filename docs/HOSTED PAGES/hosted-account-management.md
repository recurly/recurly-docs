---
title: Hosted account management
excerpt: >-
  Simplify customer experience with Recurly's Hosted Account Management. Deliver
  white-labeled subscription pages or support your customers with pre-built
  hosted pages.
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

Hosted Account Management, an offering by Recurly, facilitates businesses in offering a seamless subscription experience on their websites. You can either host the entire process with Recurly’s API or choose Recurly’s pre-configured hosted pages for customers to manage their subscriptions.

> 👍 New Recurly Checkout!
>
> The new Checkout capability is now available to all Recurly customers. With quick setup and deployment, rich customizable features, and flexible payment options, Checkout is the new standard for fast and frictionless consumer checkout, powering subscription purchases for your business. [Learn more](https://docs.recurly.com/docs/checkout).

# Key benefits

* **Seamless customer experience:** Offer your subscribers an uninterrupted experience by letting them manage, update, or cancel their subscriptions on your website.
* **Flexibility:** Choose between custom built  pages using the Recurly APIor use Recurly’s hosted pages.
* **Enhanced security:** Unique and secret tokens ensure only authorized access to each customer’s account information.

# Key details

Recurly's Hosted Account Management provides businesses the flexibility to tailor the subscription experience to their preference. You can let your customers view their account status, modify their billing details, retrieve past invoices, or make choices regarding their subscription.

## Access

Customers use pre-defined URLs to access their account management tools. To be able to provide those URLs:

1. **Navigate** to **Customers** -> **Accounts**.
2. **Select** an account.

<Image align="center" border={true} src="https://files.readme.io/162e97316690eaf43d395e6b3525620a1d8c90911d985ec61b54bf19f9518a06-image.png" className="border" />

3. **Navigate** to the right side of the screen where it says "Hosted Pages". You will find two options: **Account Management URL** and **Edit Billing Information URL**.

<Image align="center" border={true} width="80% " src="https://files.readme.io/c6e9fd55c77f2e7f0198bc1a199dfee3ae282e1590334649796df8fbd3a2af2b-image.png" className="border" />

4. Share either one or both URLs with your customer.

> **Note:** Bare in mind that doable actions by the customers depend on their access level. You can configure the access level to account login and guest view only types of accesses. Continue reading to learn how to configure it.

> ❗️ **Security Alert:**
>
> Safeguard this URL and token. Unauthorized access means they can log in as the actual customer!

### Account Management URL

The customer will automatically authenticate, and they will be able to see all invoices and subscriptions. Furthermore, they can also change their payment method, cancel subscriptions, edit their billing information and redeem gift cards.

<Image align="center" border={true} src="https://files.readme.io/f7ac0d55789a6315f80bb5344b81ef612b61775cb088805e049d7b1cbb081329-image.png" className="border" />

They can also change their email and password by clicking on their name and selection an option from the drop down menu.

<Image align="center" border={true} src="https://files.readme.io/db99fa9a3dbb472288b2e164c09f82d6017e007e0a0ed6fd9aa5e499fee89439-image.png" className="border" />

### Edit Billing Information URL

With this URL, the customer will be able to change their billing information more easily.

<Image align="center" border={true} width="80% " src="https://files.readme.io/066cb8da6a7e2b7308d16d5546db252dd7f31900f727488f0506be43040f847b-image.png" className="border" />

## Customer access

Two primary settings dictate how your customers access the Hosted Account Management: "Account Login" and "Guest View Only". You can either let your customers register and gain full access to the portal or provide them with specific hosted invoices. The default setting is "Guest View Only".

### **Account Login**

The full spectrum of the Hosted Account Management portal becomes available with this setting. Once authenticated:

* Customers land on a login page which also contains a sign-up segment, facilitated by your unique Vanity URL.
* Customers can create an account and login using the email address that is their Account Info email address in your Recurly admin.
* Each customer gets a distinct and confidential Hosted Account Management Login Token URL under the Edit Account in Recurly admin. Handle with care: this link offers direct access!

You can incorporate the **account_hosted_maintenance_url** parameter in your Recurly emails, directing users straight to their accounts. For a deeper dive into editing email templates, check our [Email Templates documentation](/docs/email-templates).

### **Guest view only**

This setting leverages Hosted Account Management to display limited customer details without needing an account. It caters primarily to hosted invoice pages and the billing info page.

### Configuration

1. **Login to your Recurly admin account.**
2. **Navigate** to **Configuration** and select **Hosted Pages Settings** and scroll to **Account Management Pages**.
3. **Click** enabled to activate.
4. **Choose** between **Account Login** and **Guest View Only** based on your preference.
5. Below are options for what a customer can view on their account management page. **Select** only those options you wish your customers to view/modify on their account management page

<Image align="center" border={true} src="https://files.readme.io/916a6727a581f61f59ccc2790f816dcff9e2b068275a72f84d089ca5ea696594-image.png" className="border" />

## **Online payments**

Recurly's Professional or Elite plan users can harness "Online Payments". It empowers customers to settle manual invoices via credit card, PayPal, Amazon account, or ACH. Incorporated within Hosted Account Management, Online Payments introduce a "Make a Payment" option on the hosted invoice page.

<Image alt="319" border={false} src="https://files.readme.io/q0n6EYxvRFSPllhMBsYT_online-pay-button.png" title="online-pay-button.png" />

<Image alt="328" border={false} src="https://files.readme.io/7FWLL1DTD2vK3eWSYfjO_online-pay-history.png" title="online-pay-history.png" />

If the invoice contains a recurring subscription, an opt-in checkbox appears for customers to allow the chosen payment method for automatic renewal payments. If this option is not chosen, the next invoice will continue to be manual.

### Enable online payments

Visit the Hosted Page Settings in your Recurly site, and under Customer Options, activate the "Pay invoices online" checkbox. If the "Make a Payment" button doesn't appear, ensure the gateways are set up correctly.

### Experience the customer's perspective

To test  the hosted invoice experience with Online Payments, issue a manual invoice. In your Recurly Admin, on the specific invoice's page, there's a "Hosted Invoice" button. Clicking this unique link showcases the Guest View version of the client's hosted invoice.

## **Display settings**

Both Hosted Account Management and Hosted Payment Pages derive branding options from the same source.

## Setting up hosted account management

1. **Login to your Recurly admin account.**
2. **Navigate** to **Configuration** and select **Hosted Pages Settings** and scroll to **Account Management Pages**.
3. **Click** enabled to activate.
4. **Choose** between **Account Login** and **Guest View Only** based on your preference.
5. Below are options for what a customer can view on their account management page. **Select** only those options you wish your customers to view/modify on their account management page.

<Image align="center" border={true} width="50% " src="https://files.readme.io/3e445f6-image.png" className="border" />

## Customization

The customization settings are for both the hosted payment pages and the account management pages so adjust accordingly.

1. Under display options, **adjust** your branding preferences.
2. Under Google Analytics, **enter** your code to have the hosted payment pages report back to your Google Analytics.
3. **Save** your settings.

<Image align="center" border={true} src="https://files.readme.io/83f7bfe9a947a7d30eb2e888f1fc8ae57007a47e72219ae128845de425b14132-image.png" className="border" />

Remember always to ensure the security of unique token links and consistently review your settings to ensure optimal customer experience.
