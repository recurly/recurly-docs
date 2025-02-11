---
title: Shipping addresses
excerpt: >-
  Enhance your customer's experience and streamline your shipping process with
  Recurly's Shipping Addresses feature. Track delivery addresses for individual
  subscriptions, calculate taxes based on shipping locations, and manage
  physical shipments more efficiently.
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

### Limitations

We do not currently have a way for your customers to use Checkout, the Hosted Payment Page or the Hosted Account Management to manage their own shipping addresses.

# Definition

Recurly's "Shipping Addresses" feature allows businesses to associate and manage physical delivery addresses with individual subscriptions. This ensures that any physical goods or services are delivered to the correct location, and the appropriate taxes are applied based on the shipping address.

# Key benefits

* **Accurate tax calculations**: Taxes are determined based on the shipping address, ensuring compliance with regional tax regulations.
* **Enhanced customer experience**: Deliver products to the correct location every time, enhancing customer satisfaction.
* **Streamlined operations**: Easily manage up to 20 different shipping addresses per account, optimizing operations for businesses with multiple subscriptions.

# Key details

Recurly's "Shipping Addresses" feature is designed to simplify the management of physical delivery addresses for individual subscriptions. This ensures that businesses can efficiently handle shipments and apply the correct taxes based on the shipping location. Each customer account can have up to 20 distinct shipping addresses. If multiple subscriptions are enabled for an account, different shipping addresses can be linked to each subscription. When a subscription is tied to a shipping address, the invoice will display the shipping address, and taxes will be calculated based on this address. With a comprehensive set of API endpoints, webhooks, email parameters, and export information, Recurly's shipping address support equips businesses to effectively manage their physical shipments.

<Image title="Screen Shot 2016-08-12 at 5.59.14 PM.png" alt={584} align="center" width="50% " border={true} src="https://files.readme.io/dfc1567-Screen_Shot_2016-08-12_at_5.59.14_PM.png">
  The Account Summary, which appears on the right of the Account Details page. It shows shipping addresses and provides a link to the "manage addresses" page where you can create, edit and delete shipping addresses.
</Image>

<Image title="Screen Shot 2016-08-16 at 6.44.16 PM.png" alt={1505} align="center" width="smart" border={true} src="https://files.readme.io/6ad1499-Screen_Shot_2016-08-16_at_6.44.16_PM.png">
  The Shipping Addresses page showing two shipping addresses, their associated subscriptions, the billing and account addresses, plus ways to create a new shipping address, or edit or delete one of the existing shipping addresses.
</Image>

### Shipping Addresses and Subscriptions

After defining a shipping address, it can be associated with a subscription.

* The correct shipping address is used for shipment
* The shipping address is clearly displayed on the invoice.
* The shipping address is used for tax calculations, where applicable.

The relationship between a subscription and its shipping address can also be managed using the Recurly API. More details are available in [the API documentation](https://docs.recurly.com/v1.0/docs/shipping-addresses#section-managing-addresses-via-the-api).

<Image title="Screen Shot 2016-08-18 at 10.46.37 AM.png" alt={2370} align="center" border={true} src="https://files.readme.io/4564703-Screen_Shot_2016-08-18_at_10.46.37_AM.png">
  The New Subscription page showing the shipping address drop-down and the Summary section on the right which shows the estimated taxes based on the selected shipping address.
</Image>

<Image title="Screen Shot 2016-08-18 at 10.52.02 AM.png" alt={2374} align="center" border={true} src="https://files.readme.io/0a1b00a-Screen_Shot_2016-08-18_at_10.52.02_AM.png">
  The Account Details page showing subscriptions, the shipping address associated with each subscription, and the estimated taxes which are based on the shipping address (when applicable).
</Image>

### Activity Log

All changes related to shipping addresses are logged in the Activity Log of each account. This ensures transparency and traceability for all modifications.

### Email Parameters

Customize your email communications by incorporating information about a subscription's shipping address using the provided email parameters.

#### `{{subscription_has_shipping_address?}}`

Returns `true` if the subscription has a shipping address.

#### `{{subscription_shipping_nickname}}`

#### `{{subscription_shipping_first_name}}`

#### `{{subscription_shipping_last_name}}`

#### `{{subscription_shipping_address1}}`

#### `{{subscription_shipping_address2}}`

#### `{{subscription_shipping_city}}`

#### `{{subscription_shipping_state}}`

#### `{{subscription_shipping_zip}}`

#### `{{subscription_shipping_country}}`

#### `{{subscription_shipping_phone}}`

#### `{{subscription_shipping_email}}`

#### `{{subscription_shipping_vat_number}}`

#### `{{subscription_full_shipping_address}}`

# Managing shipping addresses

1. **Create a Shipping Address:** Navigate to the account detail page in the Admin Console. Click on the "Manage addresses" link to go to the page where you can create a new shipping address.

<Image title="Screen Shot 2016-08-12 at 5.59.14 PM.png" alt={584} align="center" width="50% " border={true} src="https://files.readme.io/dfc1567-Screen_Shot_2016-08-12_at_5.59.14_PM.png">
  The Account Summary, which appears on the right of the Account Details page. It shows shipping addresses and provides a link to the "manage addresses" page where you can create, edit and delete shipping addresses.
</Image>

2. **Edit a Shipping Address:** On the "Manage addresses" page, find the shipping address you want to edit. Click on the "Edit" button to make changes to the shipping address.
3. **Delete a Shipping Address:** On the "Manage addresses" page, find the shipping address you want to delete. Click on the "Delete" button to remove the shipping address.

<Image align="center" className="border" width="smart" border={true} src="https://files.readme.io/6ad1499-Screen_Shot_2016-08-16_at_6.44.16_PM.png" />

4. **Associate a Shipping Address with a Subscription:** Once a shipping address has been created, it can be associated with a subscription. This can be done on the subscription detail page in the Admin Console.
5. **View Shipping Address on an Invoice:** After a shipping address has been associated with a subscription, it will be displayed on the invoice for that subscription.
6. **Use the Recurly API:** The Recurly API can be used to manage shipping addresses programmatically. Refer to the <a href="https://developers.recurly.com/" target="_blank">Recurly Developer Documentation</a> for more information on how to use the API.
