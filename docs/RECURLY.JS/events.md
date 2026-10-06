---
title: Events
excerpt: >-
  How to subscribe to and detach Recurly.js element events with `on` / `off`,
  including a working example for the `change` event.
deprecated: false
hidden: false
metadata:
  robots: index
---
Recurly.js Elements, as well as other Recurly.js objects, act as **event emitters**.

Register listeners with `.on(event, handler)` and remove them with `.off(event, handler)` to react to card-entry changes, focus, validation states, and more.

# Key details

```javascript
// 1. Create your Elements group and individual element
const elements = recurly.Elements();
const card = elements.CardElement();

// 2. Attach the element to the DOM
card.attach('#card-container');

// 3. Add an event listener
function changeHandler (state) {
  // `state` contains validity, card brand, last4, etc.
  console.log(state);
}
card.on('change', changeHandler);

// 4. Remove the listener when it's no longer needed
card.off('change', changeHandler);
```

| Common event | Fired when…                                                                  | Payload highlights                              |
| ------------ | ---------------------------------------------------------------------------- | ----------------------------------------------- |
| `change`     | Field value changes or validity updates                                      | `state.valid`, `state.brand`, `state.empty`     |
| `coBadge`    | A valid card number is entered and the networks it can run on are determined | `state.coBadgeSupport`, `state.supportedBrands` |
| `focus`      | Element gains focus                                                          | —                                               |
| `blur`       | Element loses focus                                                          | —                                               |
| `ready`      | Element is fully rendered and interactive                                    | —                                               |

> **Tip**<br />Keep a reference to the exact handler you passed to `.on()`; you must supply the same function reference to `.off()` to successfully detach the listener.

## Co-badged card state

For cards that can run on more than one network, the `change` event state includes:

| State field                                                                                                      | Type      | Description                                                                                              |
| ---------------------------------------------------------------------------------------------------------------- | --------- | -------------------------------------------------------------------------------------------------------- |
| `state.coBadgeSupport`                                                                                           | `Boolean` | Whether the entered card supports more than one network.                                                 |
| `state.supportedBrands`                                                                                          | `Array`   | Networks the card can run on, e.g. `["visa", "cartes_bancaires"]`. Empty when the card is not co-badged. |
| `state.cardNetworkPreference`                                                                                    | `String`  | The selected network, e.g. `"cartes_bancaires"`. Present when the built-in network selector is enabled   |
| (`coBadgeSelector: true`) and a co-badged card is detected; `null` once the card is removed or is not co-badged. |           |                                                                                                          |

```javascript
card.on('change', state => {
  if (state.cardNetworkPreference) {
    console.log('Processing on', state.cardNetworkPreference);
  }
});
```

> **Note**<br />The `coBadge` event fires whenever a valid card number is entered and reports
> the detected networks regardless of whether you render your own selection UI. See the
> <Anchor target="_blank" href="/docs/co-badged-cards-guide">Co-badged cards guide</Anchor> for the complete flow.
