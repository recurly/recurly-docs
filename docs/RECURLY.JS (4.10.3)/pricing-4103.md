---
title: Pricing (4.10.3)
excerpt: Learn about pricing using Recurly.js version 4.10.3
deprecated: false
hidden: false
metadata:
  robots: index
---
## Pricing

Recurly automates complicated subscriptions, with many factors influencing total subscription price. With this in mind, Recurly.js provides a robust `recurly.Pricing` class designed to make determining actual subscription costs as simple and flexible as possible.

A Recurly.js pricing instance can be attached to the form we created above, or to any other section of your page meant to display subscription pricing. Let's get to the specifics!

### Reference

### recurly.Pricing

```javascript
var pricing = recurly.Pricing();
```

Creates a `Pricing` instance.

### No arguments

### Returns

A new `recurly.Pricing` instance

### pricing.attach

Given the following example HTML structure

```html
<section id="pricing">
  <select data-recurly="plan">
    <option value="basic">Basic</option>
    <option value="notbasic">Not Basic</option>
  </select>
  <input type="text" data-recurly="coupon">
</section>
```

Use `pricing.attach` to bind the `<section>` to the pricing calculator.

```JavaScript
var pricing = recurly.Pricing();

pricing.attach(document.querySelector('#pricing'));
```

This is the simplest way to use the pricing module. Simply pass a container element, and the pricing module will use all elements with a valid `data-recurly` attribute to determine price. When a value changes, the pricing module will automatically update its values. This allows your customers to manipulate a pricing form at will, and you will be able to react dynamically in any number of ways.

### Arguments

| Param     | Type          | Description                                           |
| :-------- | :------------ | :---------------------------------------------------- |
| container | `HTMLElement` | Parent element containing all `data-recurly` elements |

### Returns

Nothing.

### Elements

Elements bound to a pricing module may be for either input or output.

Input elements should be user-manipulable elements like `input` or `select`. If you want to input a value but not let a customer manipulate it, use an `<input type="hidden">`.

### Input elements

| Field Name       | Example Value      | Description                                                                                                                |
| :--------------- | :----------------- | :------------------------------------------------------------------------------------------------------------------------- |
| plan             | `basic`            | Plan code.                                                                                                                 |
| plan\_quantity   | `1`                | Plan quantity. Defaults to 1 if not specified.                                                                             |
| coupon           | `15_off`           | Coupon code.                                                                                                               |
| addon            | `1`                | Addon quantity. To identify the addon being modified, use the `data-recurly-addon` attribute to set the addon code.        |
| currency         | `USD`              | [ISO-4217 currency code](https://docs.recurly.com/currencies).                                                             |
| country          | `US`               | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code.                                       |
| postal\_code     | `90210`            | Customer postal code. Used primarily to compute taxes.                                                                     |
| tax\_code        | `digital`          | Product tax code.                                                                                                          |
| vat\_number      | `SE0000`           | Customer VAT number. Used for VAT exclusion.                                                                               |
| tax\_amount.now  | '0.99'             | Specific tax amount to apply to the amount due now. Supplying this value will disable automated tax calculations.          |
| tax\_amount.next | '1.99'             | Specific tax amount to apply to the next billing cycle cost. Supplying this value will disable automated tax calculations. |
| gift\_card       | `518822D87268C142` | Gift card's redemption code.                                                                                               |

Output elements should be plain text elements like `output`, `span`, or `div`.

### Output elements

| Field Name       | Example Value | Description                                                              |
| :--------------- | :------------ | :----------------------------------------------------------------------- |
| total\_now       | `100.00`      | Total subscription cost due now.                                         |
| subtotal\_now    | `90.00`       | Subtotal of the following pricing components.                            |
| addons\_now      | `10.00`       | Total addon cost.                                                        |
| discount\_now    | `5.00`        | Amount discounted with coupon use.                                       |
| setup\_fee\_now  | `5.00`        | Subscription setup fee total.                                            |
| tax\_now         | `15.00`       | Total subscription taxation.                                             |
| gift\_card\_now  | `75.00`       | The gift card amount that will be applied to the purchase today.         |
| gift\_card\_next | `25.00`       | The remainder gift card amount that will be applied to the next renewal. |
| currency\_code   | `USD`, `EUR`  | ISO-4217 currency code.                                                  |
| currency\_symbol | `$`, `€`      | Symbolic representation of `currency_code`.                              |

> **Note**:  `data-recurly` values ending in `_now` like `subtotal_now` have counterparts ending in `_next`. As you might expect, these correspond to the next billing cycle cost.  These values are especially useful for plans with trial periods.

### Events

Pricing instances emit events when various values are set or the price changes.

A `Pricing` instance itself behaves as an event emitter, where events can be attached using the `pricing.on` method and removed using `pricing.off`, similar to how events are managed on `recurly`.

### `change`

This event is emitted whenever a pricing module has updated any of its pricing values. You can use this event to update your pricing display, compute total shopping costs, aggregate to analytics, etc.

Change emits a price object, shown in detail to the right.

### `set.*`

`set.*` events are emitted when specific pricing objects change on a pricing module. For example, when a customer changes their plan, the pricing module will send `set.plan`. This is especially useful for updating checkout previews based on what the customer has selected as one example.

| Param           | Type              |
| :-------------- | :---------------- |
| `set.plan`      | Plan object.      |
| `set.price`     | Price object.     |
| `set.addon`     | Addon object.     |
| `set.coupon`    | Coupon object.    |
| `set.address`   | Address object.   |
| `set.currency`  | Currency code.    |
| `set.tax`       | Tax object.       |
| `set.gift_card` | Gift card object. |

### Pricing API

```javascript
var pricing = recurly.Pricing();

pricing
  .plan('basic', { quantity: 1 })
  .currency('USD')
  .addon('addon1', { quantity: 2 })
  .coupon('coop')
  .giftcard('518822D87268C142')
  .address({
    country: 'US',
    postal_code: '90210'
  })
  .tax({
    tax_code: 'digital',
    vat_number: '',
    amounts: {
      now: '0.99',
      next: '1.99'
    }
  })
  .catch(function (err) {
    // err.code
  })
  .done(function (price) {
    // price object as emitted by 'change' event
  });
```

The pricing module can be manipulated with a set of direct method calls. This is useful if you would like to set up a complex pricing schema for your customers, or would just like to use a more programmatic method of determining subscription price. Events fire just as they normally would when using `pricing.attach`.

Note that Recurly.js's DOM binding is one-way. Thus if you use the Pricing API on a pricing instance already attached to a container, the elements within will not update with your Pricing API calls. If you would like two-way DOM binding, we suggest using a framework such as [AngularJS](https://angularjs.org/) and using the Pricing API without attaching it to a container.

> **Note**:  The example to the right demonstrates all the ways that a pricing module can be manipulated directly.

### PricingPromise

Each Pricing API method will return a `PricingPromise`. This allows you to chain many asynchronous calls together without having to manage a complex chain of callbacks.

You don't need to worry much about the internals of a `PricingPromise`, as it is designed to stay out of your way and facilitate asynchronous calls for you.

The `catch` method, as shown in the example, is used to handle error scenarios, such as when an addon cannot be applied to the selected plan.

> **Note**: At the end of a chain of pricing method calls, be sure to call `.done()` as this tells the pricing module to begin calculating, and gives you the subscription price.

### Example pricing state object

emitted by the **change** event

```javascript
{
  now: {
    subtotal: '25.00',
    addons: '0.00',
    discount: '0.00',
    setup_fee: '25.00',
    tax: '0.00',
    total: '25.00'
  },
  next: {
    subtotal: '10.00',
    addons: '0.00',
    discount: '0.00',
    tax: '0.00',
    total: '10.00'
  },
  base: {
    plan: {
      setup_fee: '25.00',
      unit: '10.00'
    },
    addons: {
      thing1: '14.00', // cost of one 'thing1' addon
      thing2: '8.00'
    },
  },
  currency: {
    code: 'USD',
    symbol: '$'
  }
}
```