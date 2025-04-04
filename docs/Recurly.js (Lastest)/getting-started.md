---
title: Getting Started
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
It provides some helpful default styles to Recurly Elements.

### Self-Hosting Recurly.js

The Recurly-hosted version of recurly.js is designed and updated to maintain compatibility
with system update deployments that take place from time-to-time. Locally hosted versions of
recurly.js run the risk of encountering issues with system interaction and incompatibility which
may result in avoidable service interruptions on your client page. It is for this reason, we highly
recommend against and do not support locally hosted copies of recurly.js.

### Configure

Simply call `recurly.configure` anywhere on your page, passing your public key.\
This identifies your site to Recurly servers. You can find your public key in the
[API Access section](https://app.recurly.com/go/developer/api_access) of your admin app.

```js
recurly.configure('sc-ABCDEFGHI123456789');
```

<div class="alert alert--info" markdown="1">
  ### Use Your Site's Public Key

  Be sure to replace `sc-ABCDEFGHI123456789` with [your own public key](https://app.recurly.com/go/developer/api_access).
</div>

`recurly.configure` accepts other options not detailed here. You may refer to the [source](https://github.com/recurly/recurly-js/blob/master/lib/recurly.js#L48) for more detail.

### Build a Payment Form With Elements

To collect card payment information from your customers, you may build an HTML form however you wish, collecting all user data that you require.  Use the `data-recurly` attribute to identify any non-card billing fields to Recurly.js. Card fields are built using Elements

```html
<form id="my-form">
  <input type="text" data-recurly="first_name">
  <input type="text" data-recurly="last_name">

  <div id="recurly-elements">
    <!-- Recurly Elements will be attached here -->
  </div>

  <!-- Recurly.js will update this field automatically -->
  <input type="hidden" name="recurly-token" data-recurly="token">

  <button>submit</button>
</form>
```

### The Card Element

<div data-recurly="card" />

This is the simplest and most streamlined way to accept customer card data.  Recurly will inject a single field that will accept the card number, expiry, and cvv.  This field is responsive and includes helpful UX enhancements to make card entry as smooth as possible on a multitude of devices.

```js
const elements = recurly.Elements();
const cardElement = elements.CardElement();
cardElement.attach('#recurly-elements');
```

### Other Elements

Recurly.js has Elements for individual card fields as well. Use these fields when you would like to display card fields separately from each other.  This is helpful when the combined field does not fit your design needs.

<div class="alert alert--warning" markdown="1">
  See [Elements](#elements) for more details on creating and interacting with Elements
</div>

The example forms above contain the minimum required input fields, and **the tables below document all possible input fields.**

### Billing fields

| Field Name            | Example                           | Description                                                                                                                                                                                                                                                                                                     |    |
| :-------------------- | :-------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :- |
| first\_name           | `Ben`                             | Cardholder first name. **Required**                                                                                                                                                                                                                                                                             |    |
| last\_name            | `du Monde`                        | Cardholder last name. **Required**                                                                                                                                                                                                                                                                              |    |
| address1              | `1313 Main St.`                   | First line of a street address.                                                                                                                                                                                                                                                                                 |    |
| address2              | `Unit 1`                          | Second line of a street address.                                                                                                                                                                                                                                                                                |    |
| city                  | `Hope`                            | Town or locality.                                                                                                                                                                                                                                                                                               |    |
| state                 | `WA`                              | Province or region.                                                                                                                                                                                                                                                                                             |    |
| postal\_code          | `98552`                           | Postal code.                                                                                                                                                                                                                                                                                                    |    |
| country               | `US`                              | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code.                                                                                                                                                                                                                            |    |
| phone                 | `555-867-5309`                    | Phone number.                                                                                                                                                                                                                                                                                                   |    |
| vat\_number           | `SE0000`                          | Customer VAT number. Used for VAT exclusion                                                                                                                                                                                                                                                                     |    |
| tax\_identifier       | `972.791.615-53`, `20-12345678-6` | A valid [CPF](https://en.wikipedia.org/wiki/Cadastro_de_Pessoas_F%C3%ADsicas) or [CUIT](https://es.wikipedia.org/wiki/Clave_%C3%9Anica_de_Identificaci%C3%B3n_Tributaria). Required if it is a consumer card in Brazil [**early access**](https://docs.recurly.com/docs/primeiropay-via-adyen) or in Argentina. |    |
| tax\_identifier\_type | `cpf`, `cuit`                     | `cpf` and `cuit` are the only accepted values for this field. Required if it is a consumer card in Brazil [**early access**](https://docs.recurly.com/docs/primeiropay-via-adyen) or in Argentina.                                                                                                              |    |

Depending on how you've configured your [billing address requirements](https://docs.recurly.com/site-settings#address_requirements), some of the fields in the table above may be required.

<div class="alert alert--info" markdown="1">
  ### Try it now

  This page includes recurly.js. Try it out now it your browser's developer console.
</div>