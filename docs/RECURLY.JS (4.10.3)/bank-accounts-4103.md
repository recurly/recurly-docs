---
title: Bank accounts (4.10.3)
excerpt: Learn about Bank Accounts using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Bank accounts

Tokenize your users' bank account information

Just as with a card form, use the `data-recurly` attribute to identify fields to Recurly.js. Since Recurly.js does not need to inject fields for bank accounts, all fields may be displayed as inputs on your payment form.

```html
<form>
  <input type="text" data-recurly="routing_number">
  <input type="text" data-recurly="account_number">
  <input type="text" data-recurly="account_number_confirmation">
  <input type="text" data-recurly="account_type">
  <input type="text" data-recurly="name_on_account">
  <input type="hidden" name="recurly-token" data-recurly="token">
  <button>submit</button>
</form>
```

### Bank account inputs

| Field Name                    | Example                 | Description                               |
| :---------------------------- | :---------------------- | :---------------------------------------- |
| routing\_number               | `123456789`             | Routing number. **Required**              |
| account\_number               | `987654321`             | Account number. **Required**              |
| account\_number\_confirmation | `987654321`             | Account number confirmation. **Required** |
| account\_type                 | `checking` or `savings` | Account type. **Required**                |
| name\_on\_account             | `Pat Smith`             | Full name on account. **Required**        |

## Getting a token

### recurly.bankAccount.token

You may call `recurly.bankAccount.token` with a form element

```javascript
recurly.bankAccount.token(document.querySelector('form'), tokenHandler);
```

Or with an Object

```javascript
const billingInfo = {
  // required attributes
  routing_number: '123456780',
  account_number: '111111111',
  account_number_confirmation: '111111111',
  account_type: 'checking',
  name_on_account: 'Pat Smith',

  // optional attributes
  address1: '123 Main St.',
  address2: 'Unit 1',
  city: 'Hope',
  state: 'WA',
  postal_code: '98552',
  country: 'US',
  vat_number: 'SE0000'
};

recurly.bankAccount.token(billingInfo, tokenHandler);
```

Both methods require using a handler function like this one

```javascript
function tokenHandler (err, token) {
  if (err) {
    // handle error using err.code and err.fields
  } else {
    // handle success using token.id
  }
}
```

This sends bank account billing information to Recurly to store as a token, returning that token id back to you via callback.

### Arguments (form)

| Param    | Type              | Description                                    |
| :------- | :---------------- | :--------------------------------------------- |
| form     | `HTMLFormElement` | Parent form containing `data-recurly` fields   |
| callback | `Function`        | Callback function to accept the returned token |

Alternatively, you can call `recurly.bankAccount.token` with a plain JavaScript object. This allows a more direct interface to the payment flow, eliminating any need to use the DOM.

### Arguments (object)

| Param    | Type       | Description                                                                     |
| :------- | :--------- | :------------------------------------------------------------------------------ |
| options  | `Object`   | An object with billing information properties matching those \[outlined above]. |
| callback | `Function` | Callback function to accept the returned token                                  |

A callback is always required

### Callback arguments

| Param      | Type                     | Description                                              |
| :--------- | :----------------------- | :------------------------------------------------------- |
| err        | `RecurlyError` or `null` | A `RecurlyError` if an error occurred; otherwise `null`. |
| token      | `Object`                 | An object containing a token id.                         |
| token.type | `String`                 | 'bank\_account'                                          |
| token.id   | `String`                 | A token id.                                              |

### Returns

Nothing.

***