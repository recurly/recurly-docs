---
title: Gift cards
excerpt: >-
  Increase customer acquisitions with a gift card program. Add gift card
  purchases to your checkout and allow gift card recipients to redeem the gift
  card for credit towards any of your products.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

# Definition

Enhance your customer engagement and business growth with Recurly's gift card program. This feature allows you to integrate gift card purchases at your checkout and enables gift card recipients to redeem them as credit towards your products.

The gift card feature in Recurly allows your business to offer virtual or physical gift cards to your customers. These gift cards, once purchased, generate a unique code which can be redeemed by the recipient for credit towards any of your products.

# Key benefits

* **Customer acquisition:** Gift cards can serve as a marketing tool that drives new customers to your business.
* **Increased revenue:** Gift cards often lead to additional spending beyond the value of the card.
* **Brand exposure:** Gift cards expose your brand to new potential customers through the recipients.
* **Customer retention:** They can be used as a tool to retain existing customers by offering them as rewards or incentives.

# Creating a gift card

Before setting up your gift card program, we recommend you consult with a legal and financial advisor. Compliance with federal and state gift card regulations, which include rules around expiration dates, dormant account fees, cash payouts, and escheatment, Recurly Gift Cards can aid in setting up a gift card program, however, it doesn't manage your compliance requirements.

Also, consider how you will account for unused card balances in relation to revenue recognition. Additionally, be aware that the introduction of gift card sales may heighten your fraud risk, as these cards are often bought with stolen credit cards and then resold. To mitigate this risk, we recommend that you review your fraud management tools and processes.

## Building your gift card product

To develop your gift card product on Recurly, follow these steps:

1. **Navigate** to Configuration→Gift Cards Settings

2. **Select** "Get Started"

3. **Enter** the desired Amount and click "Add".  
   ![](https://files.readme.io/2c1c783-image.png)

4. **Align** your gift card amounts with your subscription plans/tiers. **Use** a higher amount to cover potential taxes and incentivize customers to purchase more of your products or services.

5. **You can enter** additional amounts if desired. To **remove** an amount, hover over the dots at the end of the row and click "Remove". Merchants with multiple currency support will have the option to select the currency of the Amount.  
   ![](https://files.readme.io/858978a-image.png)

6. **Specify** a Display Name for the gift card; this will appear on the purchase charge and redemption credit line items.

7. **Enter** a Product Code (this is the product SKU).

8. **Enter** an Accounting Code (this will serve as the general ledger for your gift card purchase charge and redemption credit accounting).

   <Image align="center" border={true} src="https://files.readme.io/3b5021a-image.png" className="border" />

9. **Upload** a design image for your gift card by clicking "Choose File" and selecting the image from your computer. This image will be displayed in the Gift Card Delivery email template.

   <Image align="center" border={true} src="https://files.readme.io/bd0a7c4-image.png" className="border" />

10. **Click** "Create Gift Card" or "Save Changes". Once the gift card product is created, you can access the details anytime from the Gift Cards page.

Remember to remove any private data from your images before uploading as Recurly does not remove Exif data from uploaded images.

# Locating a gift card

There are 3 ways to locate a gift card:

1. **Through the Gift Cards Dashboard**: Navigating to Customer → Gift Cards and entering the redemption code,  the gifter's name or the recipient’s name.
2. **Through the Invoices Dashboard**: By using the purchase invoice number.
3. **Navigating through the customer's account:** By directly going to the customer's account.

## Navigating free trials and gift card scenarios

Recurly demands billing information for free trial sign-ups, with exceptions for gift card scenarios. Given most free trial invoices equal zero dollars before credits (unless a setup fee applies), distinguishing if the subscription began with a gift is critical. This differentiation allows the system to bypass billing information collection at the free trial stage.

If you choose to collect billing information during free trial sign-ups and the first invoice is paid with a gift card credit, Recurly logs this as a gift-started subscription, enabling accurate tracking of such subscriptions.

# Canceling a gift card

Canceling a gift card effectively inactivates its redemption code, preventing any future redemption attempts. This action cannot be reversed, meaning a canceled card cannot be reactivated.

This feature should be employed in situations such as fraudulent gift card purchase, or refunding a gift card. It's important to note that a gift card can only be canceled if it has not yet been redeemed. In the case of refunding a gift card, refund the invoice directly, and Recurly will automatically cancel the card for you (feature under development). If you encounter a fraudulent purchase or a chargeback, you can manually cancel the card. In the case of a chargeback, avoid issuing a refund through Recurly, as the funds would have already been refunded outside Recurly's system.

Upon successful cancellation, Recurly will display an activity for the cancellation on the gifter's account and will issue a `canceled_gift_card_notification` webhook.

## How to cancel a gift card

1. Access the gifter's account and locate the Gift Card Purchases table. Here, you'll find a link to the specific gift card.

2. On the Gift Card Details page, you'll find a red button at the top right corner labeled "Cancel Gift Card".

3. Click "Cancel Gift Card" and confirm the action in the popup.

# Modifying a gift card product

To modify your gift card product, navigate to Configuration → Gift Cards Settings and select "Edit Gift Card". Any changes made will immediately update the gift card. Any new purchases will use the updated version of the gift card, whereas existing purchases will respect the original purchase amount.

# Purchasing a gift card

Upon creating the gift card product, customers, aka gifters, can purchase gift cards for their friends and family, aka recipients. A unique redemption code will be generated in Recurly for each gift card purchase. The gift card will be initially associated with the gifter's account and will be associated with the recipient's account upon redemption.

A gift card can be purchased by a new or existing customer. If the gifter is a new customer, a new account will be created for them at the time of purchase. This account will contain the purchase invoice, billing information, and transaction details. Gift cards can be delivered via email or post.

With email delivery, Recurly will automatically send the recipient the Gift Card Delivery email containing the redemption code and other gift card details. Alternatively, you can disable the automatic email and send your own email to the recipient.

The post delivery method is available for businesses wishing to offer a physical version of the gift card. Recurly will generate the gift card redemption code and collect shipping details. The business is responsible for printing the code on a physical card and delivering it to the recipient.

### Future send date

Gifters can schedule a future date for the Gift Card Delivery email to be sent to the recipient. This date must be at least an hour in the future and less than a year from the purchase date.

### Personal message

Recurly provides two message fields for the gift card delivery information: a personal message and a gifter name. The personal message is a 255 character field for a personalized message from the gifter to the recipient. The gifter name is an optional field to collect a signature name for the gifter.

### Taxes and discounts

Gift card purchases are not taxed as they are considered payment for future purchases, however, the purchase of a gift card is still sent to your tax partner.  You may choose to bypass this using either version of the API. Currently, discounts on gift card purchases are not supported.

### Fighting fraudulent purchases

To deter fraudulent purchases, Recurly does not permit purchasing a gift card with another gift card credit. Additional fraud prevention tactics are recommended, such as using the Kount integration and requiring additional address information for billing verification.

### Purchase confirmation

Upon successful purchase, the gifter will receive a Gift Card Purchase Confirmation email containing details about the gift purchase, such as the amount, personal message, and purchase invoice.

# Redeeming a gift card

A gift card can be redeemed during subscription sign-up or directly on an existing account. Once redeemed, the recipient's account will be linked to the gift card in Recurly, and a gift card credit will be created for the full purchase amount. This credit is available to use across multiple subscriptions, invoices, and billing cycles until the credit balance is depleted.

### Redemption code

The redemption code is a unique identifier for each gift card, generated at the time of purchase. It's alphanumeric and not case-sensitive. In case the recipient encounters any difficulty during redemption, Recurly provides a feature to regenerate the code.

### Taxes

It's crucial to note that gift card credits are applied after the tax calculation. If you're collecting taxes and the redeemer does not have a payment method on file, you should ensure to store the customer's taxable address in the account information.

### Discounts

Gift card credits can be used on invoices with coupon discounts. The discounts are applied first, and then the gift card credit. If the invoice total is zero after applying the discounts, the remaining gift card credit will be left on the account for future use.

### Credit balance

Recurly tracks the credit balance once a gift card is redeemed. This balance can be viewed through the Recurly API, Gift Cards export, or on the customer's account page in the Admin Console.

### Billing information

As a business, you can choose to require or not require billing information from gift card redeemers at subscription sign-up. By default, Recurly requires billing information for all subscription sign-ups. However, this can be changed from the Gift Cards page under the Configuration menu. Note that if you're using Recurly's Checkout or Hosted Pages and collecting taxes, billing information is necessary, irrespective of your configuration setting.

For a free trial sign-up, billing information is required unless the subscription started with a gift. If a gift card redeemer starts a subscription with a free trial, the subscription will convert to a paid subscription after the trial ends. You can track when a gift card subscription converts to a paid subscription and encourage customers to add billing information to prevent service interruption at renewal when additional payment is required.

**Note:** Recurly's [Checkout](https://docs.recurly.com/docs/checkout) and [Hosted Pages](https://docs.recurly.com/v1.0/docs/hosted-pages) represent a cornerstone of the payment processing system. One of the essential aspects of these pages is the collection of [taxes](https://docs.recurly.com/v1.0/docs/tax). The system captures billing information to validate the billing address, a crucial factor in the taxation process. Without this information, determining appropriate tax rates could be imprecise and problematic.

# Refunding a gift card purchase

The process of refunding a gift card purchase involves certain steps. Primarily, it's recommended to block the associated credit from being used and then perform a full refund to the gifter. Bear in mind that Recurly won't automatically carry out this process, so you'll have to manually do it. Refunding partially or once the card has been redeemed isn't recommended because it would disrupt the balance between your gift card charges and credits, affecting your accounting accuracy.

## Refund process for redeemed gift card

In a scenario where a subscription purchase paid with gift card credit requires a refund, the gift card credit is returned to the customer's account as general credit. This process preserves the value for the customer, even in the event of a refund.

### When the gift card has not been Redeemed

* First, cancel the gift card, which will prevent its redemption.
* Then, issue a full refund on the purchase invoice. You can locate this invoice on the Gift Card Details page.

### When the gift card has been redeemed

* Track down the remaining gift card credit on the recipient's account and delete it.
* Issue a refund on the purchase invoice equal to the deleted credit. It could be either the full amount or a remaining sum.
* Note that this won't decrease the gift card balance. Hence, manually tracking that the gift card has been refunded becomes essential.

# Delivery issues

In an online gift card program, some recipients might encounter delivery issues. To manage these issues, Recurly provides your customer service reps with Admin Console tools such as editing delivery information, regenerating the redemption code, and resending the Gift Card Delivery email. All three options can be utilized if the gift card has not been redeemed.

To locate a gift card, either visit the Gift Cards index page under the Customers section of the Admin Console and search using the redemption code, gifter, or recipient. Alternatively, visit the gifter's account and find the Gift Card Purchases table listing the gift cards that account has purchased.

Each gift card has its own Gift Card Details page, linking to both the gifter and recipient account. Once the recipient redeems the gift card, on this page, you can find the redemption status of the gift card, the delivery information, and the links to perform the below actions.

### Edit delivery information

If the delivery information provided by the gifter was incorrect, you can access the Recurly Admin Console to edit it before resending the gift card. The editable fields include:

* First Name
* Last Name
* Send Date
* Email Address
* Street Address
* Address 2
* City
* State
* Zip
* Country
* Phone Number
* Gifter Name
* Personal Message

#### Address changes

If the email address is edited, the new address will be used when resending the Gift Card Delivery email. If the physical address is edited, the responsibility of physically sending a new gift card to the recipient lies with you or your fulfillment team, especially if the gift card hasn't been dispatched. Recurly will issue an `updated_gift_card_notification` webhook to notify you when the gift card delivery information is changed.

#### Send date changes

The future send date can only be edited if the send day is yet to come. When edited, you can select a future day, up to a year from the purchase date. You'll also see a dropdown of hour send windows. Both date and time will be in the timezone of your user profile.

# Regenerating a redemption code

In case the gift card redemption code may have been mistakenly delivered to the wrong person, you can regenerate the redemption code. This action will invalidate the original code and generate a new one to prevent any misuse. The recipient can only redeem this new code.

To regenerate the code, navigate to the Gift Card Details page and click on the "Regenerate Redemption Code" button. A new code will be automatically generated, and Recurly will notify you via the `updated_gift_card_notification` webhook. You can then provide this new code to the recipient or resend the Gift Card Delivery email with the updated code.

### Resend gift card delivery email

You can resend the Gift Card Delivery email to the recipient. This feature is especially useful if you've made changes to the delivery information, regenerated the redemption code, or if the recipient didn't receive the original email. To resend the email, navigate to the Gift Card Details page and click the "Resend Email" button. This option only appears if the gift card has not been redeemed and its send date is not in the future. Once clicked, Recurly will issue a `resend_gift_card_email_notification` webhook.

# Billing information collection for gift card recipients

The versatility of Recurly's system is also evident in the handling of gift card transactions. If you've set your gift card settings to not require billing information, this system will bypass collecting such data for gift card recipients. This bypass takes place when a subscription begins as a gift, and the invoice cost after applying credits is zero dollars. It ensures a frictionless experience for gift card recipients who aren't directly involved in the payment process.

# Tracking of gift-initiated subscriptions

To provide companies with granular data regarding gift subscriptions, Recurly has devised a sophisticated tracking system. This system identifies and records when a subscription starts via a gift card. As a result, companies can discern when billing information isn't needed, leading to more accurate reporting. This invaluable information will be made accessible in the Subscriptions export soon.

Recurly identifies a gift-initiated subscription if the initial subscription invoice was paid using one or more gift card credits, or if a gift card redemption code was redeemed during the sign-up process.

# Hosted pages

**Gift Card Hosted Payment Page Configurations**  
Hosted page settings allow you to control the settings for your hosted gift card purchase page. There are three optional payment form fields that do not apply to the gift card purchase page: Editable Quantities, Coupon Codes, and Gift Card Code. The absence of these options on the gift card purchase page is because customers can only purchase one gift card at a time, and coupons or gift card redemption aren't allowed for gift card purchases.

**Gift Card Hosted Payment Page**  
Customers can buy a gift card through Recurly's Hosted Payment Pages, which offers a specific hosted page for gift card purchases. The gift card can be delivered using an email address as the delivery method. It's important to note that coupon and gift card redemption is not permitted when buying a gift card.

**Gift Card Redemption on Plan Checkout and Hosted Payment Page**  
You can allow gift card redemption on the Plan Checkout and Hosted Payment Pages. Even if you do not require billing information for gift card redemption, billing information fields will still be displayed on the gift card purchase page. Enhancements to this user experience are underway.

**Hosted Account Management**  
Customers can redeem a gift card through Hosted Account Management. Gift card purchase history can be found by examining invoice history.

## Multicurrency support

Recurly's Gift Cards support multiple currencies, and if you are using the Multicurrency feature, you can define a list of preset gift card amounts for each currency. Each currency can have a different number of amounts, and you don't need to define amounts for all supported currencies. However, a gift card can only be redeemed on a subscription that uses the same currency as the purchase amount.

### Configuring multicurrency support

If using the Multicurrency feature, define a list of preset gift card amounts for each currency on the gift card product settings.

## InComm and other 3rd party gift cards

It's possible to use another system, such as InComm, to generate and sell gift cards, and then redeem the corresponding gift credit in Recurly to apply to a subscription purchase. This approach enables selling physical gift cards in stores like Walmart and Best Buy.

**Gift Card Purchase with 3rd Party**

The purchase event occurs outside of Recurly when using a third party like InComm to generate and sell gift cards. While Recurly's custom adjustments can record a third-party gift card purchase, it won't create a purchased gift card in Recurly. Instead, you'll only see the invoice and adjustment for the purchase in Recurly.

**Gift Card Redemption with 3rd Party**

Once a third-party gift card is validated and redeemed in the third-party system, you can create a corresponding credit in Recurly for the same amount. This should be marked with an origin of `external_gift_card`, which allows bypassing the billing information requirement for gift subscription purchases when nothing is due at sign-up. This can currently only be done via the Adjustments API.

To apply the gift card credit to the subscription sign-up, you must create the credit before creating the subscription. This involves making separate API calls to create the account, the credit, and then the subscription.

If you don't want to require billing information from customers redeeming a third-party gift card when nothing is due at sign-up, you can change the "Require Billing Information?" setting on the Gift Card Settings page under Configuration.

## Using Recurly and a 3rd party vendor together

If you want to use both Recurly for online gift card purchases and a third-party vendor for physical gift card purchases, ensure your redemption code lengths are different to avoid duplicates. For instance, if InComm gift cards are typically 16 to 19 characters and Recurly gift cards are 16 characters by default, you could adjust your Recurly gift cards to have a length of 15 or 20 characters.

To change your Recurly gift card redemption code length, contact Recurly Support with your desired length and the Recurly site subdomain you want it on.

# Gift card balance

To display a customer's gift card balance, you can use the API to check their account for uninvoiced external_gift_card credits and sum the amount. You can do this by using the List Account's Adjustments API call, filtering for `external_gift_card` origin and `pending` status, and then summing the `unit_amount_in_cents` to get the balance total.

Your finance team can track unused balances by identifying all adjustments with a status of "pending" and `external_gift_card` origin in the Invoices - Line Items export.

## Seamless transition from gift subscriptions to paying subscriptions

No matter your preference for billing information collection, Recurly is designed to record the transition from a gift-initiated subscription to a regular, paying subscription. This occurs when a subscription undergoes its first successful payment transaction, signifying a shift in the customer's status.

## Encouraging subscription renewals and upgrades

For customers who don't supply billing information at sign-up, it's crucial to encourage them to add it before a subscription renewal, preventing service disruptions. For subscription upgrades, Recurly uses the billing information on the account to cover the upgrade cost, ensuring a seamless customer experience.

# Additional details

### Comprehensive email notifications

Recurly's Gift Cards system supports four email notifications for either the purchaser or the recipient of the gift. These notifications—Gift Card Purchase Confirmation, Gift Card Delivery, Gift Card Balance Low, and Gift Card Redemption Reminder—ensure all parties stay informed about the gift card status, providing a smooth customer experience.

### Exports for insightful analytics

Recurly offers a new "Gift Cards" export and adds data to existing exports. It provides insights into aspects like gift card usage, popular amounts, redemption rates, and more, helping you fine-tune your marketing strategies.

### Integration with webhooks and API

Recurly's Gift Cards offer six possible notification events, allowing you to customize your customer interaction as needed. Furthermore, gift cards can be purchased and redeemed using the Recurly API, providing a convenient and automated way to manage gift card transactions.

### Seamless Recurly.js integration

Recurly.js allows for seamless integration of the gift card purchase and redemption processes into your system. While purchasing doesn't require any new updates, the redemption process leverages Recurly.js Pricing to preview a gift card credit applied to a new subscription, enhancing transparency for your customers.
