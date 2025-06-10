---
title: Errors
excerpt: Learn all about Errors  using Recurly.js
deprecated: false
hidden: false
metadata:
  robots: index
---
## Errors

Errors are encapsulated by a `RecurlyError`, which contains a few standard properties to help you diagnose error cases and inform your customers accordingly.

Errors will be thrown if the exception will prevent proper execution. If an error can be recovered, it will be passed to the proper error handling event listener, callback, or `PricingPromise` handler for you to inspect.

### Best practices

The `message` property contains diagnostic information intended to help you diagnose problems with the form, and we do not recommend displaying its contents to your customers.

To provide the best customer experience, we recommend that you provide your own error text to be displayed, based on the error code you receive.

### Error codes

#### Configuration

| Code                        | Description                                                                                                                                                                                                                                        |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| not-configured              | This error appears when you try to perform an operation without first calling `recurly.configure`.                                                                                                                                                 |
| missing-public-key          | When you call `recurly.configure`, you must do so with a `publicKey` property.                                                                                                                                                                     |
| invalid-public-key          | Check the `publicKey` to ensure it matches that of your admin app's [API Access section](https://app.recurly.com/go/developer/api_access).                                                                                                         |
| missing-hosted-field-target | This is thrown when the target element for a hosted payment field cannot be found on the page. Check the error message to check the selector being used, then check your page to ensure the element is present when `recurly.configure` is called. |

#### Tokenization

| Code              | Description                                                                                                                                                                                |
| :---------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| validation        | A request validation error has occurred. This can indicate many possible issues, and you should check the fields property to determine which `fields` caused the error.                    |
| invalid-parameter | Occurs when a tokenization parameter does not pass our internal validations. Check the `fields` property to determine which fields caused the error.                                       |
| api-error         | A request to the Recurly API has encountered an issue. This too can indicate many possible issues, and we recommend inspecting the `message` and `fields` properties for more information. |

#### Pricing

| Code                        | Description                                                                                                                                             |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| not-found                   | This happens when a nonexistent plan is requested.                                                                                                      |
| missing-plan                | A `Pricing` instance will emit this if a plan has not been specified before trying to set a proeprty that depends on a plan, such as a coupon or addon. |
| invalid-addon               | Occurs when an addon is added to a `Pricing` instance but is not valid for the instance's selected plan.                                                |
| invalid-currency            | Similarly, if a currency is requested which is not valid for the selected plan.                                                                         |
| gift-card-currency-mismatch | Occurs when a gift card is redeemed with a currency that doesn't match the instance's configured currency.                                              |

#### Apple Pay

| Code                                | Description                                                                                                                            | Additional Properties                 |
| :---------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------ |
| apple-pay-init-error                | A configuration issue has prevented initialization                                                                                     | `err` the originating `RecurlyError`. |
| apple-pay-not-configured            | Your site does not have a gateway which supports Apple Pay                                                                             |                                       |
| apple-pay-configuration-invalid     | There is an issue with your Apple Pay authentication information. Check your certificate and key values in your gateway configuration. |                                       |
| apple-pay-merchant-validation-error | Apple encountered an error validating your merchant credentials                                                                        |                                       |
| apple-pay-payment-failure           | An error has occurred during tokenization, preventing the payment authorization                                                        |                                       |

#### PayPal

| Code                   | Description                                                                                       |
| :--------------------- | :------------------------------------------------------------------------------------------------ |
| paypal-not-configured  | In order to perform a PayPal transaction, your site must be configured to accept PayPal reference |
| paypal-canceled        | The customer canceled the PayPal agreement flow.                                                  |
| paypal-error           | A generic PayPal error has occurred. Inspect `message` to learn more.                             |
| invalid-routing-number | The bank routing number is not valid                                                              |

#### 3-D Secure

| Code                          | Description                                                                                                                                              | Additional Properties                   |
| :---------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------- |
| 3ds-auth-error                | 3-D Secure authentication has failed because the customer could not be authenticated. We recommend prompting the user to try a different payment method. | `cause` the originating `Error`.        |
| 3ds-result-tokenization-error | An error occurred while attempting to tokenize the 3-D Secure authentication result.                                                                     | `cause` the originating `RecurlyError`. |
| 3ds-vendor-load-error         | A third-party dependency had an issue loading. Dependencies are utilized when required by your payment gateway.                                          | `vendor` the dependency provider.       |
| 3ds-auth-determination-error  | The authentication method necessary to fulfill 3-D Secure requirements could not be determined                                                           |                                         |

### Example RecurlyError object

```javascript
{
  name: 'validation',
  code: 'validation',
  message: 'There was an error validating your request.',
  fields: [
    'number',
    'year'
  ]
}
```