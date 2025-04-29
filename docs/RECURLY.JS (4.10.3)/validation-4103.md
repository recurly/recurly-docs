---
title: Validation (4.10.3)
excerpt: Learn all about Validation  using Recurly.js version 4.10.3.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Validation

Recurly.js bundles a few helpful methods for validating payment information prior to processing. These methods are used when generating tokens, but you can also use them to enhance your form validations and checkout flow.

It is also possible to inspect the validation state of hosted fields as your customer types, by listening to the ['change' event](#events).

### Reference

### recurly.bankAccount.bankInfo

Retrieves bank info based from a given routing number.

```JavaScript
recurly.bankAccount.bankInfo({ routingNumber: '123456780' }, function (err, bankInfo) {
  if (err) {
    // err.code, err.message
  } else {
    // bankInfo.bank_name
  }
});
```

### Arguments

| Param                 | Type     | Description                                     |
| :-------------------- | :------- | :---------------------------------------------- |
| options               | `Object` |                                                 |
| options.routingNumber | `String` | The routing number for a bank (ex: '123456780') |
| callback              | Function |                                                 |

### Callback signature

| Param               | Type                          | Description                                   |
| :------------------ | :---------------------------- | :-------------------------------------------- |
| err                 | `RecurlyError` or `undefined` | Error. Usually `invalid-routing-number`       |
| bankInfo            | `Object`                      |                                               |
| bankInfo.bank\_name | `String`                      | Bank institution name (ex: `Bank of Recurly`) |

***