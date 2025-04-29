---
title: Events (4.10.3)
excerpt: Learn about Events for Recurly.js version 4.10.3
deprecated: false
hidden: false
metadata:
  robots: index
---
## Events

Listen to events using the Emitter methods

```javascript
// Listen to the 'change' event
recurly.on('change', changeHandler);

// But we're feeling indecisive today. Let's detach this event
recurly.off('change', changeHandler);

// .once will listen for one event then detach itself
recurly.once('field:submit', function () {
  $('#my-payment-form').submit();
});

function changeHandler (state) {
  // state.fields
}
```

A `Recurly` instance is an event emitter, and will emit events throughout the lifecycle of your customer's interaction with your payment form. Events can be attached using the `recurly.on` method and removed using `recurly.off`. The example to the right shows the various ways that you can attach and remove events.

## `change`

This event is emitted whenever a customer changes the state of hosted card fields, those that you may not otherwise observe directly with DOM events. For example, if your customer types '4' into the number field, then the state of the number field will change, and the `change` event will emit.

The `change` event emits a `RecurlyState` object, whose values are demonstrated to the right. This will give you useful insight into the entire state of the recurly-controlled components of your payment form.

## `field:submit`

This event is emitted when a user presses the `enter` key while they are focused on a hosted field. Since this action typically submits a form, we recommend performing a payment form submission when this event is emitted.

Note that you can detect the brand of the credit card entered using the "brand" field in the state object above.

### Example RecurlyState object

```json
{
  fields: {
    card: {
      brand: 'visa',
      cvv: {
        empty: false,
        focus: false,
        valid: true
      },
      empty: true,
      expiry: {
        empty: false,
        focus: false,
        valid: true
      },
      firstSix: '411111',
      focus: false,
      lastFour: '1111',
      number: {
        empty: false,
        focus: false,
        valid: true
      },
      valid: false
    },
    number: {
      valid: false,
      firstSix: '',
      lastFour: '',
      brand: 'unknown',
      empty: true,
      length: 0,
      focus: false
    },
    month: {
      valid: false,
      empty: true,
      length: 0,
      focus: false
    },
    year: {
      // same as month
    },
    cvv: {
      // same as month
    }
  }
}
```

***