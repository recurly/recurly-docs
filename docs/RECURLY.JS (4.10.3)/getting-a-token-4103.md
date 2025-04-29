---
title: Getting a token (4.10.3)
excerpt: Learn how to get a token using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Getting a token

Interrupt the form submit to send billing info to Recurly and get a secure token in exchange. Once you have the token, submit the form to your server.

```javascript
$('form').on('submit', function (event) {
  var form = this;
  event.preventDefault();
  recurly.token(form, function (err, token) {
    if (err) {
      // handle error using err.code and err.fields
    } else {
      // recurly.js has filled in the 'token' field, so now we can submit the
      // form to your server; alternatively, you can access token.id and do
      // any processing you wish
      form.submit();
    }
  });
});
```

Recurly.js works with tokens, which represent secure and temporary storage for your customer's sensitive billing information. They are stored directly on Recurly servers to reduce your PCI exposure.

When your customers submit your billing form, you'll need to interrupt the submit and ask Recurly.js to create a token from the form. You may have noticed an additional hidden field in the form above, `token`. When you ask Recurly.js for a token during submit, it will automatically populate this field for you. After you get the token, you will submit it to your servers and use it there to talk to any endpoint in our API that accepts a `billing_info`.

> **Notes**: This example demonstrates jQuery as an event-binding and DOM library; however, you may use any library you choose, or interact directly with the DOM (hard mode).

### Reference

#### recurly.token

You must call `recurly.token` with your form element.

```javascript
  recurly.token(document.querySelector('form'), tokenHandler);
```

Using a handler function like this one:

```javascript
function tokenHandler (err, token) {
  if (err) {
    // handle error using err.code and err.fields
  } else {
    // handle success using token.id
  }
}
```

Sends billing information to Recurly to store as a token, sending that token id back to you.

| Param    | Type              | Description                                     |
| :------- | :---------------- | :---------------------------------------------- |
| form     | `HTMLFormElement` | Parent form containing `data-recurly` fields.   |
| callback | `Function`        | Callback function to accept the returned token. |

A callback is always required.

#### Callback arguments

| Param      | Type                     | Description                                              |
| :--------- | :----------------------- | :------------------------------------------------------- |
| err        | `RecurlyError` or `null` | A `RecurlyError` if an error occurred; otherwise `null`. |
| token      | `Object`                 | An object containing a token id.                         |
| token.type | `String`                 | 'credit\_card'                                           |
| token.id   | `String`                 | A token id.                                              |

#### Returns

Nothing.