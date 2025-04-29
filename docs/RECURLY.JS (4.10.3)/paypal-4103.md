---
title: PayPal (4.10.3)
excerpt: Learn about PayPal using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
## PayPal

Use Recurly to process PayPal transactions using PayPal Business or Braintree.

A PayPal transaction is handled entirely within the PayPal checkout flow in a new window. Your customer will authorize a transaction within PayPal. Recurly will then record the authorization and return a Recurly token to you as it does for other payment methods.

You will need to use the token within our API before it expires, and expired tokens cannot be retrieved.

First, place a button on your page specifically for checking out with PayPal.

```html
<button>Checkout with PayPal</button>
```

Next, create a new `recurly.PayPal` instance

```javascript
var paypal = recurly.PayPal({
  display: { displayName: ' My product ' }
});
```

**If you're processing PayPal transactions with Braintree**, you'll pass a client authorization during instantiation:

```javascript
var paypal = recurly.PayPal({
  braintree: { clientAuthorization: MY_CLIENT_AUTHORIZATION }
});
```

Your instance must then be setup to handle error scenarios and start the checkout flow.

```javascript
paypal.on('error', function (err) {
  // err.code
  // err.message
  // [err.cause] if there is an embedded error
});
```

Next we must bind a listener to a user action on the button and have it trigger the `start` function on your `recurly.PayPal` instance. This will open the PayPal checkout flow.

> **Note**: As with the rest of Recurly.js, there are no external dependencies. The example uses jQuery to demonstrate binding events, but this can be done any way you wish.

```javascript
$('#paypal-button').on('click', function () {
  paypal.start();
});
```

> **Note**: The `start` function must be called within a user-initiated event like 'click' or 'touchend'

Finally, add a function to receive the token once your customer completes the checkout flow. At this point you will send the token id to your server to be used in the Recurly API to create a billing info for an account.

```JavaScript
paypal.on('token', function (token) {
  // token.id
});
```

### Reference

### recurly.PayPal

### Arguments

| Param                                 | Type     | Description                                                                                     |
| :------------------------------------ | :------- | :---------------------------------------------------------------------------------------------- |
| options                               | `Object` | Optional.                                                                                       |
| options.braintree                     | `Object` | Optional. Braintree configuration.                                                              |
| options.braintree.clientAuthorization | `String` | If using Braintree to process PayPal transactions, provide your client authorization code here. |

### Returns

A new `PayPal` instance

### payPal.start

### Arguments

| Param               | Type     | Description                                                                                    |
| :------------------ | :------- | :--------------------------------------------------------------------------------------------- |
| options             | `Object` | Optional.                                                                                      |
| options.description | `String` | Optional. In legacy PayPal flows, this description will be displayed during the checkout flow. |

### Returns

Nothing.

### Events

### `error`

This event is emitted when any error is encountered, whether during setup of the PayPal flow, or during the checkout process. It will be useful to display errors to your customer if a problem occurs during PayPal checkout.

### Signature

| Param | Type           | Description                                  |
| :---- | :------------- | :------------------------------------------- |
| error | `RecurlyError` | An error describing the issue that occurred. |

### Error codes

See [Errors](#errors)

### `cancel`

This event is emitted when the customer has canceled the PayPal checkout flow before completion. You may wish to reset parts of your checkout experience if this occurs.

### Signature

None.

### `token`

This event is fired when the customer has completed the PayPal checkout flow. Recurly has received the payment details, and generated this token to be used in our API.

### Signature

| Param      | Type     | Description                            |
| :--------- | :------- | :------------------------------------- |
| token      | `Object` |                                        |
| token.type | `String` | 'paypal'                               |
| token.id   | `String` | Token identifier to be sent to the API |

***