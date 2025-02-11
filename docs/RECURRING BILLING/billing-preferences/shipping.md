---
title: Shipping fees
excerpt: >-
  Recurly's Shipping Fees feature enables you to charge shipping fees on
  subscriptions through our API and UI and on one-time purchases through our
  API.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Feature Overview

Shipping in one-time [eCommerce](www.websiteadvisor.com/ecommerce/bests/) is simple: a customer places an order and the seller passes the shipping provider's fee along to the customer or charges a flat fee.

Shipping is more complex in a subscription commerce context. Subscriptions are much more long-lived than standalone orders. Recurly makes decisions around shipping costs easy for merchants. 

The concept is simple: you have the ability to record the cost of shipping and the method used to ship the item(s). You can record this method and cost on a subscription, or on a one-time purchase.

> 🚧 Site Requirements
>
> In order to use this feature, your site must be configured with the [Credit Invoices](https://docs.recurly.com/v1.0/docs/credit-invoices-release), [Only Bill What Changed](https://docs.recurly.com/v1.0/docs/only-bill-what-changed), and [Subscription Billing Terms](https://docs.recurly.com/docs/subscription-terms-new) features. Please contact us if you would like more information about upgrading to these features.
>
> Recurly sites created after July 26, 2018 will automatically have these features enabled.

> 📘 Rate Lookups
>
> If you would like Recurly to add the ability to directly integrate with shipping providers (DHL, USPS, etc) we'd love to hear from you! Feel free to [reach out to us](https://recurly.zendesk.com/).

# Configuring Shipping on Your Recurly Site

To begin using Shipping Fees, navigate to Configuration > Shipping.

<Image title="Blank Slate.png" alt={1200} align="center" src="https://files.readme.io/cbd41fa-Blank_Slate.png">
  This is the screen you will see when configuring shipping for the first time.
</Image>

Once you enable shipping on your site, Recurly will create a default shipping method for you. If you do not display the shipping method (e.g. USPS Priority Mail) you use to your customers, or use only one shipping method, there is no further configuration needed.

If you do use multiple shipping methods or would like to show your customers which shipping method you use to ship their item(s), you can configure the method in this section.

# Shipping Methods

Shipping Methods can be useful to display to your customers which method you use to ship their item(s), or differentiate between methods you use in different geographies. To set up a shipping method, navigate to Configuration > Shipping. You can add as many Shipping Methods as your business requires.

<Image title="Create.png" alt={1200} align="center" src="https://files.readme.io/ecd628d-Create.png">
  You can use Shipping Methods to show your customers which method is being used to ship their items.
</Image>

## Changing Shipping Providers

If you are changing your shipping provider, we recommend you change the name on the shipping method. This will ensure that active subscriptions which have that shipping method are migrated to the new shipping method name.

## Removing a Shipping Method

Exercise caution when removing a shipping method. If there are active subscriptions with the shipping method in place, these subscriptions will renew without a shipping method. 

We recommend you to not use this unless you have made a Shipping Method by mistake. If you have changed your shipping provider, we recommend either making a new Shipping Method or changing the name.

To delete a shipping method, click the 3 dots to the right of the shipping method and click Delete Shipping Method. You'll be given a warning, and then to delete you need to enter the name of the Shipping Method to confirm this is the action you'd like to take. Note that this action cannot be undone, and may result in a loss of data.

![](https://files.readme.io/ad681df-Delete.png "Delete.png")

# Adding Shipping Fees to a Subscription

The Shipping feature is built to make charging recurring shipping on a subscription easy.

## Recurly Admin UI

In order to create a subscription with shipping fees, navigate to the account to which you'd like to add the subscription and click Account Actions > Create Subscription. Click the "Include Shipping" checkbox and enter the fee and shipping method you'd like to use.

![](https://files.readme.io/7bc0c8c-Screen_Shot_2019-02-25_at_12.36.27_PM.png "Screen Shot 2019-02-25 at 12.36.27 PM.png")

When you add a shipping fee, you will also need to add a Shipping Address to the subscription. You can either manually enter the address, or copy it from another address on the account.

Once you click *Add Subscription*, you will see the shipping fee has been added to the cost of the subscription on a recurring basis. The tax estimate will include tax on the shipping cost.

![](https://files.readme.io/b74cde9-Screen_Shot_2019-02-25_at_12.43.03_PM.png "Screen Shot 2019-02-25 at 12.43.03 PM.png")

## API

On the subscription PUT call you can insert an amount for shipping\_amount\_in\_cents.

```xml
<subscription>
<plan_code>gold</plan_code>
  <currency>USD</currency>
  <account>
    <account_code>34</account_code>
    <email>verena@example.com</email>
    <first_name>Verena</first_name>
    <last_name>Example</last_name>
    <billing_info>
      <number>4111-1111-1111-1111</number>
      <month>12</month>
      <year>2019</year>
      <address1>123 Main St.</address1>
      <city>San Francisco</city>
      <state>CA</state>
      <zip>94105</zip>
      <country>US</country>
    </billing_info>
  </account>
  <shipping_address>
    <nickname>Work</nickname>
    <first_name>Verena</first_name>
    <last_name>Example</last_name>
    <company>Recurly Inc</company>
    <phone>555-222-1212</phone>
    <email>verena@example.com</email>
    <address1>123 Main St.</address1>
    <address2>Suite 101</address2>
    <city>San Francisco</city>
    <state>CA</state>
    <zip>94105</zip>
    <country>US</country>
  </shipping_address>
  <shipping_amount_in_cents>10000</shipping_amount_in_cents>
  <shipping_method_code>foo</shipping_method_code>
  <renewal_billing_cycles>4</renewal_billing_cycles>
  <auto_renew>true</auto_renew>
</subscription>'
```

You can also preview a subscription with shipping fees using by calling the Subscription Preview endpoint:

```xml
<subscription>
  <plan_code>gold</plan_code>
  <currency>USD</currency>
  <account>
    <account_code>32</account_code>
    <email>verena@example.com</email>
    <first_name>Verena</first_name>
    <last_name>Example</last_name>
    <billing_info>
      <number>4111-1111-1111-1111</number>
      <month>12</month>
      <year>2019</year>
      <address1>123 Main St.</address1>
      <city>San Francisco</city>
      <state>CA</state>
      <zip>94105</zip>
      <country>US</country>
    </billing_info>
  </account>
  <shipping_address>
    <nickname>Work</nickname>
    <first_name>Verena</first_name>
    <last_name>Example</last_name>
    <company>Recurly Inc</company>
    <phone>555-222-1212</phone>
    <email>verena@example.com</email>
    <address1>123 Main St.</address1>
    <address2>Suite 101</address2>
    <city>San Francisco</city>
    <state>CA</state>
    <zip>94105</zip>
    <country>US</country>
  </shipping_address>
  <unit_amount_in_cents>10000</unit_amount_in_cents>
  <shipping_amount_in_cents>1299</shipping_amount_in_cents>
  <shipping_method_code>foo</shipping_method_code>
  <renewal_billing_cycles>4</renewal_billing_cycles>
  <auto_renew>true</auto_renew>
</subscription>
```

# Changing the Shipping Fee or Method on a Subscription

If you change the amount of the Shipping Fee on a subscription immediately versus at renewal, your customer will be issued a full refund for the original shipping amount plus the corresponding tax amount, and will receive a charge invoice for the newly updated shipping amount plus its corresponding tax amount. This can be done via UI or API. 

We recommend making all changes to the Shipping Fee at the next renewal to avoid numerous separate charge and credit invoices. 

# Adding Shipping to a purchase (one-time charge or adjustment)

You can charge a shipping fee on an invoice with only one-time purchases through the Recurly API. The following is an example, and you can find more in our [developer documentation](https://developers.recurly.com/api/latest.html#operation/create_purchase).

```xml
<purchase>
  <account>
    <account_code>c442b36c-c64f-41d7-b8e1-9c04e7a6ff82</account_code>
  </account>
  <shipping_fees>
    <shipping_fee>
      <shipping_amount_in_cents>1000</shipping_amount_in_cents>
      <shipping_method_code>fedex-2-day</shipping_method_code>
      <shipping_address> || <shipping_address_id>
        ...
      </shipping_address> || </shipping_address_id>
    </shipping_fee>
  </shipping_fees>
  <adjustments>
    <adjustment>
      <product_code>foobar</product_code>
      <unit_amount_in_cents>1000</unit_amount_in_cents>
      <description>Thingy</description>
    </adjustment>
  </adjustments>
  <subscriptions>
    <subscription>
      <plan_code>plan1</plan_code>
    </subscription>
  </subscriptions>
</purchase>
```

# Shipping on Invoices

Shipping will appear on invoices as a line item below any other subscription or one-time charges. It will always appear as the last line item on the invoice.

## Taxation

Recurly works with industry-best sales tax providers to ensure that our merchants are in compliance with sales tax regulations. Shipping is taxable in some jurisdictions, and not in others.

If you are using multiple shipping addresses, the VAT number associated to the billing address will be used for invoices. If you need to use reverse VAT charges, we recommend only using one shipping address per invoice. 

For merchants who use Recurly's in-the-box Avalara product, we give options on the Shipping Method to specify the type of tax which should be charged on the fees for that method. The following tax codes are available for out-of-the-box merchants:

| Tax Option                                          | Use Case                                                                                                                                                                      |
| :-------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Common Carrier FOB Destination                      | A common carrier is a provider such as USPS or FedEx. FOB Destination should be used if title of the goods pass to the customer when they are delivered.                      |
| Common Carrier FOB Origin                           | A common carrier is a provider such as USPS or FedEx. FOB Origin should be used if title of the goods pass to the customer when they are shipping.                            |
| Non Common Carrier FOB Destination                  | If you do not use a common carrier (i.e. have a private delivery company). FOB Destination should be used if title of the goods pass to the customer when they are delivered. |
| Non Common Carrier FOB Origin                       | If you do not use a common carrier (i.e. have a private delivery company). FOB Origin should be used if title of the goods pass to the customer when they are shipping.       |
| Delivery by Company Vehicle Before Passage of Title | If you have your own delivery vehicle and staff and still technically own the goods until they are delivered, use this option.                                                |
| Delivery by Company Vehicle After Passage of Title  | If you have your own delivery vehicle and staff and pass title to the goods before they are delivered, use this option.                                                       |
| Non-Taxable                                         | If your shipping costs are not taxable, use this option.                                                                                                                      |

Merchants who have their own Avalara or Vertex account can specify the exact tax code they would like to use for each shipping method to ensure compliance.

## International Shipping Customs & Duties

If you ship across international lines, there are more concerns than sales tax on shipping fees. The solution above will compute sales tax on shipping fees for both domestic and international shipping.

In most cases, if you use a common carrier, they will handle the collection and remittance of shipping fees when you ship internationally. Recurly does not provide the ability to communicate customs fees & duties to your customers. We recommend you reach out to your shipping provider to learn more about how to implement a solution.

## Refunding Shipping Fees

When refunding the shipping fee from an invoice, you have two options: either refund the entire shipping amount, or do not refund the shipping fee. There is currently no ability to refund a partial shipping fee. Refunds for a shipping fee will also issue a refund for the tax amount related to the shipping fee line item. 

To refund shipping in the Admin UI, navigate to the invoice you would like to refund and click Invoice Actions > Refund Invoice.

## Shipping Fees on One-Time Charges

To charge a shipping fee on a purchase with a one-time fee, we recommend using our API. The /purchases endpoint beginning in version 2.20 of the API. See documentation here: [https://developers.recurly.com/api/latest.html#operation/create\_purchase](https://developers.recurly.com/api/latest.html#operation/create_purchase).

## Coupons

Recurly's coupons will not apply to shipping fees. If you would like to discount a shipping fee, we recommend passing in the value you would like to charge to the customer on the API call or UI entry that you make for the subscription or one-time charge.

We are gathering feedback on whether Recurly should offer a coupon for free shipping. If this is something you would like to see, please [let us know](https://recurly.zendesk.com/).

# Exporting Shipping Information

Shipping information is available in the following exports:

* Adjustments
* Subscriptions
* Subscriptions - Churned
