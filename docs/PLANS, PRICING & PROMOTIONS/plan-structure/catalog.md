---
title: Item catalog
excerpt: >-
  If you sell standard offerings or combinations of offerings to many customers,
  organizing those in a Recurly catalog provides many benefits. You'll
  experience faster charge creation, easier management of offerings, and
  analytics about your offerings across all sales channels. Because your
  offerings may be physical, digital, or service-oriented, Recurly collectively
  calls these "Items".
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:html]
{
  "html": "<div></div>\n<iframe width=\"560\" height=\"315\" src=\"https://www.youtube.com/embed/h61lgTgxoRs\" frameborder=\"0\" allow=\"accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture\" allowfullscreen></iframe>\n<style></style>"
}
[/block]


> 🚧 Pre-Requisite Features
> 
> In order to use this feature, your site must be configured with the [Credit Invoices](https://docs.recurly.com/docs/credit-invoices-release), [Only Bill What Changed](https://docs.recurly.com/docs/only-bill-what-changed), and [Subscription Billing Terms](https://docs.recurly.com/docs/subscription-terms-new) features. Please contact us if you would like more information about upgrading to these features.
> 
> Recurly sites created after July 26, 2018 will automatically have these features and Item Catalog enabled.

## Dashboard

Your [Items dashboard][1] contains the list of items defined in your Recurly item catalog. You can select any item name to view detailed item information, edit the item, or disable / re-enable the item.

[1]: https://app.recurly.com/go/items

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a436fec-Items__Recurly.png",
        "Items_—_Recurly.png",
        2238
      ],
      "align": "center",
      "sizing": "100% ",
      "border": true,
      "caption": "Item Dashboard example"
    }
  ]
}
[/block]


<br />

## Creating Items

Under the Configuration menu, select "Items" to access your main Items page. From there, select **Create New Item**. Items can also be created via our <a href="https://dev.recurly.com/docs/create-item" target="_blank">v2</a> and <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_item" target="_blank">v3</a> APIs. If you would like assistance importing a large item catalog into Recurly, our Professional Services organization is available to help or you can leverage our simple <a href="https://developers.recurly.com/guides/multi_item_upload.html" target="_blank">Multi-Item Upload Guide</a>.

To add a new item to your catalog, you'll need to define the following parameters:

#### Item Name

This is the name that will appear on the <a href="https://docs.recurly.com/docs/hosted-pages" target="_blank">Hosted Account Management Page</a> and the subscriber's invoice. (255 character limit. Your payment gateway may also place limitations on charge names, avoid using special characters without checking with your gateway provider first.)

#### Item Code

This is the item's unique Recurly identifier and is used in <a href="https://docs.recurly.com/docs/hosted-pages" target="_blank">Hosted Account Management Page</a> URLs and to fetch items via the <a href="https://developers.recurly.com/api/latest.html#tag/item" target="_blank">API</a>. For merchants using the Product field in Vertex, that value should be entered here. (50 character limit. Accepts numbers, lowercase letters, dashes, pluses, and underscores only.)

#### External SKU

This optional field can be used to associate items in Recurly with other systems/platforms. External SKU can be re-used across items if desired. (50 character limit.)

#### Item Description

A description of the item, this can be displayed to your customers outside Recurly if configured via the API.

#### Accounting Code

This optional field can be used to help identify invoice line items in exports. (25 character limit. Accepts numbers, lowercase letters, dashes, pluses, and underscores only.) 

#### Default Price

The default amount to be charged for this item if a different price isn't specified during charge creation.

#### Revenue Recognition

If the <a href="https://docs.recurly.com/docs/revenue-recognition" target="_blank">Revenue Recognition</a> feature is enabled, this field specifies how invoiced charges from this item should be realized as revenue. The item's default revenue recognition schedule can be modified during charge creation.

#### Taxes

If taxation is enabled, these fields specify whether sales of this item should be taxed, and how they should be taxed. The value(s) specified will carry over to all sales of the item.

### Custom Fields

Recurly's custom fields can be used to track additional item attributes or identifiers beyond those listed above. Use these to capture product variant details, product family/category, and more. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65ddc56-Item_Details__Recurly.png",
        "Item_Details_—_Recurly.png",
        1576
      ],
      "align": "center",
      "border": true,
      "caption": "Custom Fields example"
    }
  ]
}
[/block]


See our <a href="https://docs.recurly.com/docs/custom-fields" target="_blank">Custom Fields</a> documentation for detailed information about creating custom fields in Recurly. To add a custom field to the items in your catalog, simply select "Item" as the Recurly Object when you create a custom field. The next time you create or edit an item in your catalog, you will see the custom field available on the UI form or through the API.

### Item ID

When you look up an item in the API or in exports, you will see a 19-character alphanumeric Item ID. This is a system-generated ID to reference your item and cannot be user-specified or edited.

## Disabling items

Disabling an item will prevent it from being sold going forward. Existing uninvoiced charges with this item (both one-time charges and subscription charges) will not be affected and should be removed manually, if necessary. Disabled items can still be edited, to keep them up to date with your system of record should you choose to enable them again in the future. Once an item is re-enabled, it can be actively sold again. Items can be disabled and re-enabled via the Recurly Admin Console and the API.

## Managing items

Editing an item via the Recurly Admin Console or API will change the item's attributes going forward, but will not impact past sales of the item or existing plans or subscriptions containing the item. For example, if an item's default price is updated, previously-created plans, subscriptions, and one-time charges for the item will remain the same, whether they have been invoiced or not, but new plans and one-time charges for the item will default to the new item price. Exports that show item sales will reflect the item attributes at the time the item was billed.

Here's the content with the link converted to HTML syntax to open in a new window, while retaining the rest of the markdown:

Items in your Catalog can be maintained via the <a href="https://developers.recurly.com/api/latest.html#tag/item" target="_blank">Items</a> API and the Recurly Admin Console. Item alerts are available via our webhook notifications.

### Item management using webhooks

You can use our item-specific webhook notifications in conjunction with the Items API endpoint to help keep your items in Recurly in sync with any downstream systems. Webhooks are available for new item creation, item updates, and item disables and re-enables. Additional information about these item notifications is available in our <a href="https://developers.recurly.com/pages/webhooks.html#item-notifications" target="_blank">webhook documentation</a>.

## Selling Items

Items in your catalog can be sold as one-time charges on Accounts and as recurring charges (called add-ons) on Plans and Subscriptions. Each item can be sold via any channel for maximum flexibility and data tracking; the item itself is not "one-time" or "recurring".

### One-Time Item Sales

Information about creating one-time charges can be found <a href="https://docs.recurly.com/docs/adjustments#section-creating-charges" target="_blank">here</a>. Simply select "Item" as the **Charge Type** when creating a one-time charge via the Admin Console, or send the appropriate Item Code when creating a charge via the API.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c9d0bfa-Add_Charge__Recurly.png",
        "Add_Charge_—_Recurly.png",
        1696
      ],
      "align": "center",
      "border": true,
      "caption": "Creating a One-Time Item Charge"
    }
  ]
}
[/block]


The charge Description, Product Code, Accounting Code, and Tax settings will be auto-populated from the item. The Price and Revenue Recognition for the charge will also be auto-populated from the item, but these fields can be changed to reflect the desired values for this particular charge.

These one-time item charges can be created via the <a href="https://developers.recurly.com/api/latest.html#tag/purchase" target="_blank">Purchases</a> endpoint, the <a href="https://developers.recurly.com/api/latest.html#tag/line_item" target="_blank">Line Items</a> endpoint, or the <a href="https://dev.recurly.com/docs/adjustment-object" target="_blank">Adjustments</a> endpoint in Recurly's API.

### Recurring Item Sales

Items can be sold on a recurring basis via add-ons on plans and subscriptions. If you prefer to have Recurly manage and enforce the specific items that can be sold on a plan, you can configure those available items as plan add-ons. If you do not limit the items that can be sold on a plan, or if you manage those restrictions on your own platform, you can bypass this configuration at the plan level, instead. Both approaches are detailed below.

#### Selling Items as Plan Add-Ons

Configuring items as add-ons on a plan restricts the offerings a subscriber to that plan can select. The only offerings available to the customer will be those add-ons specified on the plan. To sell items from your catalog as plan add-ons, select the desired item(s) from the dropdown in the Plan Add-Ons section of the New Plan page, or send the appropriate Item Code(s) when creating a plan via the API.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f55b784-Plan_Add-Ons.png",
        "Plan_Add-Ons.png",
        1864
      ],
      "align": "center",
      "border": true,
      "caption": "Creating a Recurring Item-Based Add-On"
    }
  ]
}
[/block]


<br />

The Add-On Name, Add-On Code, Accounting Code, Tax settings, and Revenue Recognition for the add-on will be auto-populated from the item. The add-on Price will also be auto-populated from the item, but this value can be changed to reflect the desired price for this plan. More information about creating add-ons can be found <a href="https://docs.recurly.com/docs/plans#section-add-ons" target="_blank">here</a>.

In Recurly's API, item-based plan add-ons can be configured via the <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_plan" target="_blank">Plans</a> or <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_plan_add_on" target="_blank">Plan Add-Ons</a> endpoints and charged via the <a href="https://developers.recurly.com/api/latest.html#tag/purchase" target="_blank">Purchases</a> or <a href="https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_subscription" target="_blank">Subscriptions</a> endpoints. All plan add-on and subscription add-on configuration can also be done via the Recurly Admin Console.

**Quantity-Based Pricing for Item Add-Ons**

Items can be sold with fixed pricing or any of the available [Quantity-Based Pricing](https://docs.recurly.com/docs/billing-models#section-quantity-based) models when added to a plan.  Once you have selected your item, choose your pricing model and configure your tiers, if applicable. You can use the calculator to validate that specific unit amounts will charge as expected. 

Once the pricing model has been saved, the specific tiers and prices can be updated on the plan or subscription to provide more personalized pricing. If you need to change the pricing model, create a new add-on. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3731327-Image_2020-05-28_at_1.36.33_PM.png",
        "Image 2020-05-28 at 1.36.33 PM.png",
        1251
      ],
      "align": "center",
      "sizing": "100",
      "border": true,
      "caption": "Creating an Item-Based Add-On with Quantity-Based Pricing"
    }
  ]
}
[/block]


#### Selling Items Directly on Subscriptions

Depending on your business model, it might make sense to avoid configuring item add-ons on your plans and simply specify the actual item(s) purchased on each individual customer subscription instead. If all of the items in your catalog are available as potential add-ons on a plan, if each of your customers has the ability to configure their own unique subscription offerings, or if you already control item availability in your own platform, this approach can provide much greater efficiency.

To support item sales directly on subscriptions, simply check the box in the Plan Add-Ons section of any plan to **Add all items on subscriptions to this plan** or utilize the **allow_any_item_on_subscriptions** field in our [API](https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_plan).

![](https://files.readme.io/e43c396e7df2ea7334c33b3be6c520f42af025dfdab81b0305922019dfa27101-image.png)

This will make all of the **active** items in your catalog available as possible add-ons on subscriptions to that plan. Any items you add to your catalog in the future will automatically be available to use as a subscription add-on, and any items you disable in your catalog will be blocked from purchase on new subscriptions. When each individual subscription is created, simply select (via the Recurly Admin Console) or provide (via the [API](https://developers.recurly.com/api/v2019-10-10/index.html#operation/create_subscription)) the items that should be included in that subscription as recurring charges.

With this functionality enabled, it is still possible to configure both item-based and non-item-based add-ons on the plan, in addition to selling item-based add-ons directly on each subscription. Upon creating a subscription, you will be able to add the same item-based add-on up to twice, with one instance tied to the plan add-on and one instance configured directly on the subscription. This can support item sales at multiple prices, if desired. While item-based add-ons configured on the plan and on the subscription will look the same in the Recurly Admin Console, the **add_on_source** in the Recurly API will distinguish one from the other, if necessary.

When using the items direction on subscriptions capability, items can only be sold at a fixed price. If you want to leverage quantity-based pricing models, configure the item on the plan, and provide the quantity with the subscription. To help our product team prioritize supporting quantity-based pricing models for items directly on subscriptions, reach out to [support@recurly.com](mailto:support@recurly.com) and ask to be added to the feature request. 

## Items in our API and client libraries

In our API, all functionality for the Catalog feature is on **<a href="https://developers.recurly.com/api/v2019-10-10/index.html" target="_blank">version 2019-10-10</a>** and above.

- Ruby Client version is <a href="https://github.com/recurly/recurly-client-ruby/releases/tag/3.9.0" target="_blank">3.9.0</a>
- Node Client version is <a href="https://github.com/recurly/recurly-client-node/releases/tag/3.10.0" target="_blank">3.10.0</a>
- Python Client version is <a href="https://github.com/recurly/recurly-client-python/releases/tag/3.8.0" target="_blank">3.8.0</a>
- Dotnet Client version is <a href="https://github.com/recurly/recurly-client-dotnet/releases/tag/3.10.0" target="_blank">3.10.0</a>
- Go Client version is <a href="https://github.com/recurly/recurly-client-go/releases/tag/v3.4.0" target="_blank">3.4.0</a>
- Java Client version is <a href="https://github.com/recurly/recurly-client-java/releases/tag/3.9.0" target="_blank">3.9.0</a>
- PHP Client version is <a href="https://github.com/recurly/recurly-client-php/releases/tag/3.4.0" target="_blank">3.4.0</a>

For sites using our older v2 API, functionality for item creation and one-time item charges is on **<a href="https://dev.recurly.com/v2.24" target="_blank">version 2.24</a>** and above. Functionality for item-based plan add-ons is on **<a href="https://dev.recurly.com/v2.25" target="_blank">version 2.25</a>** and above. Flexibility around selling items directly on subscriptions is supported on **<a href="https://dev.recurly.com/v2.27" target="_blank">version 2.27</a>** and above.

- Ruby Client version is <a href="https://github.com/recurly/recurly-client-ruby/releases/tag/2.18.10" target="_blank">2.18.10</a>
- Python Client version is <a href="https://github.com/recurly/recurly-client-python/releases/tag/2.9.17" target="_blank">2.9.17</a>
- PHP Client version is <a href="https://github.com/recurly/recurly-client-php/releases/tag/2.12.14" target="_blank">2.12.14</a>
- Dotnet Client version is <a href="https://github.com/recurly/recurly-client-net/releases/tag/1.17.5" target="_blank">1.17.5</a>

However, we recommend always updating to the latest version of the API so that you have the most up-to-date functionality.

## Item data

For easy analysis, you can pull information about items and item sales from our API and exports.

### Item usage across plans and subscriptions

For easy visibility and analytics, you can see which plans and subscriptions contain a specific item from your catalog via the [Items — Associated Plans](doc:items-associated-plans) and [Items — Associated Subscriptions](doc:items-associated-subscriptions) exports. Use these to identify the impact of disabling or editing an item, analyze pricing & packaging of an item across your sales channels, and more!

### Item sales data

Information about item sales can be pulled from the Adjustments exports (Adjustments, Adjustments - Coupons, and Adjustments - Taxes) and from the [Line Items][33] and [Adjustments][34] API endpoints. Version details for the exports are listed below, and version details for the API endpoints are listed [above][35].

- Adjustments export version is [3][30]
- Adjustments - Coupons export version is [2][31]
- Adjustments - Taxes export version is [3][32]

For any purchases that include an item from your catalog, the Item Code, External SKU, and [Recurly's Item ID][36] for that item will be displayed. The Item Code is also replicated in the Product Code field to support the analysis of item sales across all sales channels.

[30]: https://docs.recurly.com/docs/adjustments-exports#section-adjustments

[31]: https://docs.recurly.com/docs/adjustments-exports#section-adjustments-coupons

[32]: https://docs.recurly.com/docs/adjustments-taxes-export

[33]: https://developers.recurly.com/api/latest.html#tag/line_item

[34]: https://dev.recurly.com/docs/adjustment-object

[35]: https://docs.recurly.com/docs/catalog#section-managing-items-via-the-api

[36]: https://docs.recurly.com/docs/catalog#section-item-id

### Limitations

- Items are not supported for usage-based add-ons. Charges for items can be added to the next invoice, but when you have a high-volume of usage use case, we recommend using usage based billing. If you need to log usage and have Recurly charge for that usage on the subsequent invoice, use our [usage-based add-ons](https://docs.recurly.com/docs/usage-based-billing).