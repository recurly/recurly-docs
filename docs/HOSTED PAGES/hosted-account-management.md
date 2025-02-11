---
title: Account management
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

### Video

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FFEfoB7miNVk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DFEfoB7miNVk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FFEfoB7miNVk%2Fhqdefault.jpg&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=FEfoB7miNVk",
  "title": "Hosted Pages Overview",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/FEfoB7miNVk/hqdefault.jpg",
  "provider": "youtube.com",
  "href": "https://www.youtube.com/watch?v=FEfoB7miNVk",
  "typeOfEmbed": "youtube"
}
[/block]


### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Hosted Account Management, an offering by Recurly, facilitates businesses in offering a seamless subscription experience on their websites. You can either host the entire process with Recurly’s API or choose Recurly’s pre-configured hosted pages for customers to manage their subscriptions.

> 👍 New Recurly Checkout!
> 
> The new Checkout capability is now available to all Recurly customers. With quick setup and deployment, rich customizable features, and flexible payment options, Checkout is the new standard for fast and frictionless consumer checkout, powering subscription purchases for your business. [Learn more](https://docs.recurly.com/docs/checkout).

# Key benefits

- **Seamless customer experience:** Offer your subscribers an uninterrupted experience by letting them manage, update, or cancel their subscriptions on your website.
- **Flexibility:** Choose between custom built  pages using the Recurly APIor use Recurly’s hosted pages.
- **Enhanced security:** Unique and secret tokens ensure only authorized access to each customer’s account information.

# Key details

Recurly's Hosted Account Management provides businesses the flexibility to tailor the subscription experience to their preference. You can let your customers view their account status, modify their billing details, retrieve past invoices, or make choices regarding their subscription.

## Customer access

Two primary settings dictate how your customers access the Hosted Account Management: "Account Login" and "Guest View Only". You can either let your customers register and gain full access to the portal or provide them with specific hosted invoices. The default setting is "Guest View Only".

### **Account Login**

The full spectrum of the Hosted Account Management portal becomes available with this setting. Once authenticated:

- Customers land on a login page which also contains a sign-up segment, facilitated by your unique Vanity URL.
- Customers can create an account and login using the email address that is their Account Info email address in your Recurly admin. 
- Each customer gets a distinct and confidential Hosted Account Management Login Token URL under the Edit Account in Recurly admin. Handle with care: this link offers direct access!

You can incorporate the **account_hosted_maintenance_url** parameter in your Recurly emails, directing users straight to their accounts. For a deeper dive into editing email templates, check our [Email Templates documentation](/docs/email-templates).

### **Guest view only**

This setting leverages Hosted Account Management to display limited customer details without needing an account. It caters primarily to hosted invoice pages and the billing info page.

## **Guest view**

Be it "Account Login" or "Guest View Only", the Guest View grants merchants the ability to present a hosted version of a customer's invoice through email or a hosted page to update payment details. If "Account Login" is activated, login or sign-up options appear on the page's top right.

In case of filled subscription custom fields, they will be showcased in the subscription detail section.

### **Hosted invoice links**

Upon activation of Hosted Account Management, all Recurly email templates containing invoice details will possess a unique secret link to the invoice's hosted version. Through this, customers can effortlessly download their invoice as a PDF.

Note the confidential hosted invoice link for any invoice on its respective page in your Recurly admin.  
URL format: `:your_subdomain.recurly.com/account/invoices/:invoice_number?ht=:hosted_login_token`

> ❗️ **Security Alert:**
> 
> Safeguard this URL and token. Unauthorized access means they can log in as the actual customer!

### **Hosted billing information**

If a situation arises where a subscriber  needs to modify their billing info without Hosted Account Management login access, merchants can activate "Guest View Only" and give subscribers  a unique Guest View "Edit Billing Info" URL. Find this URL on the Edit Account page.  
URL format: `:your_subdomain.recurly.com/account/billing_info/edit?ht=:hosted_login_token`

## **Customer options**

Once Hosted Account Management is set to Account Login, two more options become available for the clientele: canceling subscriptions and modifying their account email ID.

#### **Cancel subscriptions**

When enabled, a "Cancel" option appears for every subscription in the portal. If a subscription is canceled via this, it remains active till its term end. If it's paused, canceling terminates it instantly.

#### **Update account email address**

This feature introduces an "Edit Email" option in the account dropdown visible after logging into the portal. Any email change here updates the Recurly subscribers  Account Info email.

### **Online payments**

Recurly's Professional or Elite plan users can harness "Online Payments". It empowers customers to settle manual invoices via credit card, PayPal, Amazon account, or ACH. Incorporated within Hosted Account Management, Online Payments introduce a "Make a Payment" option on the hosted invoice page.

![319](https://files.readme.io/q0n6EYxvRFSPllhMBsYT_online-pay-button.png "online-pay-button.png")

![328](https://files.readme.io/7FWLL1DTD2vK3eWSYfjO_online-pay-history.png "online-pay-history.png")

If the invoice contains a recurring subscription, an opt-in checkbox appears for customers to allow the chosen payment method for automatic renewal payments. If this option is not chosen, the next invoice will continue to be manual.

**Enable online payments:**

Visit the Hosted Page Settings in your Recurly site, and under Customer Options, activate the "Pay invoices online" checkbox. If the "Make a Payment" button doesn't appear, ensure the gateways are set up correctly.

**Experience the customer's perspective:**

To test  the hosted invoice experience with Online Payments, issue a manual invoice. In your Recurly Admin, on the specific invoice's page, there's a "Hosted Invoice" button. Clicking this unique link showcases the Guest View version of the client's hosted invoice.

## **Display settings**

Both Hosted Account Management and Hosted Payment Pages derive branding options from the same source. For an in-depth look, refer to our [Hosted Pages][10] article.

# Setting up hosted account management

1. **Login to your Recurly admin account.**
2. **Navigate **to **Configuration** and select **Hosted Pages Settings** and scroll to **Account Management Pages**.
3. **Click **enabled to activate.
4. **Choose **between **Account Login** and **Guest View Only** based on your preference.
5. Below are options for what a customer can view on their account management page. **Select **only those options you wish your customers to view/modify on their account management page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3e445f6-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "50% ",
      "border": true
    }
  ]
}
[/block]


## Customization

The customization settings are for both the hosted payment pages and the account management pages so adjust accordingly.

1. Under display options, **adjust **your branding preferences.
2. Under Google Analytics, **enter **your code to have the hosted payment pages report back to your Google Analytics.
3. **Save** your settings.

Remember always to ensure the security of unique token links and consistently review your settings to ensure optimal customer experience.