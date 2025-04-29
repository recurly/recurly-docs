---
title: Getting started (4.10.3)
deprecated: false
hidden: false
metadata:
  robots: index
---
## Getting Started

To begin, you'll include the Recurly.js script on your page.

```html
<script src="https://js.recurly.com/v4/recurly.js"></script>
<link href="https://js.recurly.com/v4/recurly.css" rel="stylesheet" type="text/css">
```

This exposes a single global object, `recurly`.

It is not necessary to include recurly.css, but we highly recommend it while you're getting set up.\
It provides some helpful default styles to Recurly payment fields.

### Self-Hosting Recurly.js

The Recurly-hosted version of recurly.js is designed and updated to maintain compatibility
with system update deployments that take place from time-to-time. Locally hosted versions of
recurly.js run the risk of encountering issues with system interaction and incompatibility which
may result in avoidable service interruptions on your client page. It is for this reason, we highly
recommend against and do not support locally hosted copies of recurly.js.

### Framework Support

Due to the necessity of gathering customer payment data within iframe elements, and the nature of
reactive framework re-rendering requirements, Recurly does not at this time provide native support
for reactive frameworks like React and Angular.

### Configure

Simply call `recurly.configure` anywhere on your page, passing your public key.\
This identifies your site to Recurly servers. You can find your public key in the
[API Access section](https://app.recurly.com/go/developer/api_access) of your admin app.

```js
recurly.configure('sc-ABCDEFGHI123456789');
```

### Use Your Site's Public Key

Be sure to replace `sc-ABCDEFGHI123456789` with your own public key.

`recurly.configure` accepts other options not detailed here. You may refer to the [source](https://github.com/recurly/recurly-js/blob/master/lib/recurly.js#L48) for more detail.

### Build a card form

Build a form however you like. Use the `data-recurly` attribute to identify input\
field targets to Recurly.js. For this, we recommend using simple div elements.

There are two ways to display card fields to your customers: a combined card field, and individual card fields.

### Combined card field

This is the simplest and most streamlined way to accept customer card date. Recurly will inject\
a single field that will accept all card data. This field is responsive to various device widths
and includes helpful UX enhancements to make card entry as smooth as possible.

```html
<form id="recurly-js-sample-combined-card-form">
  <div data-recurly="card"></div>
</form>
```

```html
<form>
  <input type="text" data-recurly="first_name">
  <input type="text" data-recurly="last_name">
  <div data-recurly="card"></div>
  <input type="hidden" name="recurly-token" data-recurly="token">
  <button>submit</button>
</form>
```

### Individual card fields

If you would like to display card fields separately from each other. This is helpful\
when the combined field does not fit your design needs.

```html
<form>
  <input type="text" data-recurly="first_name">
  <input type="text" data-recurly="last_name">
  <div data-recurly="number"></div>
  <div data-recurly="month"></div>
  <div data-recurly="year"></div>
  <div data-recurly="cvv"></div>
  <input type="hidden" name="recurly-token" data-recurly="token">
  <button>submit</button>
</form>
```

To collect card payment information from your customers, you'll create a form similar to this one.\
Recurly.js uses the `data-recurly` attributes on the input tags to gather customer
information before sending it to our servers.

> **Note**: In order for recurly.js to inject the card payment hosted fields into your form, the target elements must be present in the document at the time you make the `recurly.configure` call.

**Note** that card data is not present in the form but merely given a placeholder element.  This is because Recurly.js must inject those fields onto the page within iframes to ensure strict security of customer card data.

This particular form contains the minimum required input fields, and **the table below documents all possible input fields.**

### Card fields

| Field Name  | Example                         | Description                                                                     |
| :---------- | :------------------------------ | :------------------------------------------------------------------------------ |
| card        | `4111-1111-1111-1111 08/22 123` | Combined card field. **Required** if using the combined card field              |
| number      | `4111-1111-1111-1111`           | Credit card number. **Required** if using individual card fields                |
| month       | `8` or `08`                     | Card expiration month as a number. **Required** if using individual card fields |
| year        | `22` or `2022`                  | Card expiration year as a number. **Required** if using individual card fields  |
| first\_name | `Ben`                           | Cardholder first name. **Required**                                             |
| last\_name  | `du Monde`                      | Cardholder last name. **Required**                                              |
| cvv         | `123`                           | Card security code                                                              |

Depending on how you've configured your [billing address requirements](https://docs.recurly.com/site-settings#address_requirements), some of the following fields may be required.

### Billing address fields

| Field Name   | Example         | Description                                                                          |
| :----------- | :-------------- | :----------------------------------------------------------------------------------- |
| address1     | `1313 Main St.` | First line of a street address.                                                      |
| address2     | `Unit 1`        | Second line of a street address.                                                     |
| city         | `Hope`          | Town or locality.                                                                    |
| state        | `WA`            | Province or region.                                                                  |
| postal\_code | `98552`         | Postal code.                                                                         |
| country      | `US`            | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code. |
| phone        | `555-867-5309`  | Phone number.                                                                        |
| vat\_number  | `SE0000`        | Customer VAT number. Used for VAT exclusion                                          |