---
title: 3D Secure (4.10.3)
excerpt: Learn all about 3D Secure using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
# 3D Secure

Strong customer authentication for your users.

Recurly.js provides a set of utilities that allow you to support 3-D Secure authentication on your checkout page seamlessly. For more information on 3-D Secure, see our [introduction to Strong Customer Authentication](https://docs.recurly.com/docs/revised-payment-services-directive-psd2).

Recurly's support for 3-D Secure utilizes both Recurly.js and our API. For a complete guide to this integration and get started, start with our [Strong Customer Authentication (SCA) Integration Guide](/developers/guides/3ds2.html).

### Reference

### recurly.Risk

### Arguments

None.

### Returns

A new `Risk` instance

### recurly.ThreeDSecure

### Arguments

| Param                 | Type     | Description                                                                                                               |
| :-------------------- | :------- | :------------------------------------------------------------------------------------------------------------------------ |
| options               | `Object` |                                                                                                                           |
| options.actionTokenId | `String` | `three_d_secure_action_token_id` returned by the Recurly API when 3-D Secure authentication is required for a transaction |

### Returns

A new `ThreeDSecure` instance.

### threeDSecure.attach

### Arguments

| Param     | Type          | Description                                                                                                                                                                                                                                                                                            |
| :-------- | :------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| container | `HTMLElement` | A DOM element to contain any UI elements necessary to fulfill the 3-D Secure authentication process. We recommend this element be a minimum size of 250px (W) x 400px (H), and contain an interstitial message to explain that 3-D Secure authentication will be required to complete the transaction. |

### Returns

Nothing

### EVENTS

### `token`

This event is fired when your customer has completed the 3-D Secure flow. Recurly has received the authentication details, and generated this token to be used in our API.

### Signature

| Param      | Type     | Description                            |
| :--------- | :------- | :------------------------------------- |
| token      | `Object` |                                        |
| token.type | `String` | 'three\_d\_secure\_action\_result'     |
| token.id   | `String` | Token identifier to be sent to the API |

### `error`

This event is emitted when any error is encountered, whether during setup of the 3-D Secure flow, or during authentication. It will be useful to display errors to your customer if a problem occurs during the 3-D Secure flow.

### Signature

| Param | Type           | Description |                                              |
| :---- | :------------- | :---------- | :------------------------------------------- |
| error | `RecurlyError` |             | An error describing the issue that occurred. |

### Error codes

See [Errors](https://docs.recurly.com/v1.2/docs/errors-4103#/)

### Example

```javascript
var risk = recurly.Risk();
var threeDSecure = risk.ThreeDSecure({
  actionTokenId: myActionTokenId
});

threeDSecure.on('token', function (token) {
  // handle passing the action result
  // token back to your server

  // token.type => 'three_d_secure_action_result'
  // token.id

  // optionally, you may call threeDSecure.remove() to remove the element
});

threeDSecure.on('error', function (error) {
  // handle error scenarios.

  // error.code
  // error.message

  // optionally, you may call threeDSecure.remove() to remove the element
});

threeDSecure.attach(document.querySelector('#my-auth-container'));
```