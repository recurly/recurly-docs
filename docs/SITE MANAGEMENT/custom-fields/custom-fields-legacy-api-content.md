---
title: Custom fields - API
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Recurly Account API

The API for custom fields will be available to your site regardless of whether or not you allow the custom field to be viewed or edited in the Recurly UI.

You can read custom fields on an individual account with a GET call. This functionality is available beginning in [API version 2.14](https://dev.recurly.com/v2.14).

You can write custom field data to an individual account with a PUT or POST call through the API.

```json
<account>
  <custom_fields type="array">
    <custom_field>
      <name>foo</name>
      <value>asdf</value>
    </custom_field>
  </custom_fields>
</account>
```

## Custom Fields on Charges

Use this option to create custom field values for the Charge object when you wish to set a custom value on non-subscription line item charges/credits. This value can be set through a Line Item (charge or credit) or through a Purchase. Defining and setting a value for a Charge object also enables a merchant to trigger off this field for sending more tailored email communications.

### Recurly Charges UI

When defining the custom field object, if you selected the option for 'Able to set...', you can set those values via the UI by pulling up a customer's account, selecting to Add Charge/Item or Add Credit and scroll to the bottom of the page, just above the Add Another Charge button. The name will be whatever you defined for Admin Console Field Name. In the example below it was CHARGECUSTOMFIELD. Once set, the data will only be viewable via an API call.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f842535-Screen_Shot_2023-02-22_at_8.38.14_AM.png" />

### Recurly Charges API

The API for custom fields will be available to your site regardless of whether or not you allow the custom field to be set in the Recurly UI.

You can write custom field data to a line item with a POST to Line Items or Purchases.

You can read custom fields data in GET calls for Line Items, Purchases and Invoices. You will see a Custom Fields array as part of the Line Items array. Below is sample code for the v3 API.

```text
"line_items":[
    {
    "currency": "USD",
    "unit_amount": "1.05",
    "type": "charge",
    "quantity": 1,
  "custom_fields": [
    {
      "name": "Foo",
      "value": "bar"
    }
  ]
}
```

[Learn more v3 api](https://recurly.com/developers/api/v2019-10-10/index.html).

[Learn more v2 api](https://recurly.com/developers/api-v2/v2.29/index.html).

## Custom Fields on a Subscription

Use this option to create custom field values for the Subscription object when the information you need is subscription-specific. Examples of custom fields on subscriptions:

* Customer device ID (for IOT businesses)
* Acquisition channel
* Customer segment
* Subscription ID from other systems (can be used to do payouts on a subscription basis)
* Partner ID who helped to acquire the customer

Note: When subscription custom fields are populated, they will display on the subscription detail on Hosted Account Management.

### Recurly Subscription UI

When defining the custom field object, if you selected the option to it editable in the UI, you can set those values via the UI when creating or editing a subscription:

<Image align="center" className="border" border={true} src="https://files.readme.io/ea506fd-Screen_Shot_2018-07-12_at_5.06.54_PM.png" />

After editing these field values, you will be able to see them on the subscription screen in the Recurly UI. This information is also available on the subscription view on the account screen.

<Image align="center" className="border" border={true} src="https://files.readme.io/ce2ed0f-Screen_Shot_2018-07-12_at_5.10.50_PM.png" />

### Recurly Subscription API

The API for custom fields will be available to your site regardless of whether or not you allow the custom field to be viewed or edited in the Recurly UI.

You can read custom fields on an individual subscription with a GET call.

You can write custom field data to an individual subscription with a PUT or POST call through the API.

The subscription POST call can be made while creating the subscription. This functionality is available beginning in [API version 2.14](https://recurly.com/developers/api-v2/v2.14/).

```json
<subscription>
  <custom_fields type="array">
    <custom_field>
      <name>foo</name>
      <value>asdf</value>
    </custom_field>
  </custom_fields>
</subscription>
```

The subscription PUT call functions through the subscriptions/notes route so that it will not collide with other changes being made on the subscription. This functionality is available beginning in [API version 2.14](https://dev.recurly.com/v2.14).

```json
<subscription>
 <terms_and_conditions>Payment can be sent to Acme Cloud, Inc.</terms_and_conditions>
 <customer_notes>Thanks for your business!</customer_notes>
 <vat_reverse_charge_notes>No VAT was applied on this invoice. Please reference this legislation.  </vat_reverse_charge_notes>
 <custom_fields>
  <custom_field>
    <name>food</name> <!-- set to the appropriate name -->
    <value>taco</value>
  </custom_field>
 </custom_fields>
</subscription>
```

## Custom Fields on an Item

Use this feature to create custom field values for the Item object if you need to collect additional item information. Examples of custom fields on items:

* Product variant information (e.g. size, color)
* Product family / category
* Sales channel
* Sales region

### Recurly Item UI

When defining the custom field object, if you selected the option to it editable in the UI, you can set those values via the UI when creating or editing an item:

![](https://files.readme.io/ae3addf-Edit_Item__Recurly.png "Edit_Item_—_Recurly.png")

When defining the item object, if you selected the label as read-only in the UI, the field values will be readable via the view item screen but will not present on the edit item screen.

### Recurly Item API

The API for custom fields will be available to your site regardless of whether or not you allow the custom field to be viewed or edited in the Recurly UI.

You can read custom fields on an individual item with a \[GET call]\[1].

You can write custom field data to an individual item with a \[POST]\[2] or \[PUT]\[3] call through the API.

[1]: https\://developers.recurly.com/api/v2019-10-10/index.html#operation/get_item

[2]: https\://developers.recurly.com/api/v2019-10-10/index.html#operation/create_item

[3]: https\://developers.recurly.com/api/v2019-10-10/index.html#operation/update_item

```json
<item>
  <custom_fields>
    <custom_field>
      <name>foo</name>
      <value>asdf</value>
    </custom_field>
  </custom_fields>
</item>
```

## Custom Fields on a Plan

Use this option to create custom field values for the Plan object when the information you need is account-specific. Examples of custom fields on a plan:

* Customer region or location (US vs Europe or California vs New York)
* Specific Customer Channel
* New or returning customer
* Tax purposes

### Recurly Plan UI

When defining the custom field object, if you selected the option to be *editable in the UI*, you can set those values via the Admin UI when creating or editing a plan:

<Image align="center" alt={2595} border={true} caption="Creation of a custom field on a plan" title="docs image export3x.png" src="https://files.readme.io/7e8662a-docs_image_export3x.png" width="smart" />

When defining the plan object, if you selected the option for as *read-only in the UI,* the field values will be readable when viewing the plan but will not be present on the edit plan screen.

### Recurly Plan API

The API for custom fields will be available to your site regardless of whether or not you allow the custom field to be viewed or edited in the Recurly UI.

You can write custom field data to an individual account with a PUT or POST to plans.

You can read custom fields on all plans or an individual plan a GET plans call.

[Learn more v2 api](https://recurly.com/developers/api-v2/v2.29/#tag/plans)\
[Learn more v3 api](https://recurly.com/developers/api/v2019-10-10/index.html#tag/plan)

```
<plan>
  <custom_fields>
    <custom_field>
      <name>region</name>
      <value>central</value>
    </custom_field>
  </custom_fields>
</plan>

```

## FAQ

* Emojis are not allowed and will be stripped in the API or will pass an error in the UI. If you pass an emoji, Recurly will not save that emoji to our database but will save all other characters.
* There is not currently support for searching in the Recurly UI for custom field values.
* The Recurly for Salesforce integration does not currently support passing custom field values from Salesforce to Recurly.
* Recurly will delete any values which appear to be credit card numbers or CVV codes which are entered in custom fields. These values will never be stored in order to maintain PCI compliance.
* An Item and Plan export is not currently offered; therefore custom field data on Items or Plans is not available via export.