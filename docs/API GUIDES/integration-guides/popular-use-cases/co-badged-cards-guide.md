---
title: Co-badged cards guide
excerpt: >-
  A quick guide to implementing co-badged card support in Recurly.js, enabling
  customers to choose their preferred network at checkout.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

### Prerequisites & limitations

* Supported on [Adyen](https://docs.recurly.com/recurly-subscriptions/docs/adyen) and [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe)
  * Requires **Recurly.js v4.45.0]+** (built-in selector), or any current v4 release for the custom UI flow
* You must have a working **Recurly.js** card integration to use this guide effectively.
* See [Recurly.js documentation](https://recurly.com/developers/reference/recurly-js/#getting-started) for setup details.
* For more information on co-badged card compliance, refer to our [Recurly Docs](https://docs.recurly.com/recurly-subscriptions/credit-cards#dual--co-badged-card-support).

***

This guide explains how to support co-badged cards in a Recurly.js environment, allowing customers to choose which network to use at checkout. There are two approaches:

* [Option A – Built-in network selector](#option-a-built-in-network-selector) (**recommended**): the card field renders the choice UI for you, and the selection is tokenized automatically.
* [Option B – Custom selection UI](#option-b-custom-selection-ui): you listen for the `coBadge` event and render your own selection UI.

***

# Option A: Built In Selector&#x20;

Use this option if you want a low-lift pre-built selector.

Enable `coBadgeSelector` on your card field:

```js
const elements = recurly.Elements();
const cardElement = elements.CardElement({ coBadgeSelector: true });
```

Or, on individual card fields:

```js
const cardNumberElement = elements.CardNumberElement({ coBadgeSelector: true });
```

**Behavior when a co-badged card number is entered:**

* The supported network marks (e.g. Visa and Cartes Bancaires) appear in place of the card
  brand icon.
* The network detected from the card's BIN is selected by default, so the customer can
  proceed without any additional action.
* The customer can switch networks by clicking or tapping a mark, or by keyboard: <kbd>Tab</kbd> into the selector, then <kbd>←</kbd>/<kbd>→</kbd> to choose.
* The selected network is included automatically in the token during tokenization as the
  card network preference — no `data-recurly` attributes or event handling are required.

> **Note**<br />The detected network is preselected and included in the token even if the
> customer does not interact with the selector. If your integration requires an explicit
> choice, use Option B.

# Option 2: Custom Selector

Use this approach if you want full control over where and how the choice is presented.

### Step 1: Listen for the `coBadge` Event

Set up an event listener for `coBadge` on your Recurly.js `CardElement`. For more on
handling events, see the [Recurly.js events documentation](https://recurly.com/developers/reference/recurly-js/#events).

```js
const elements = recurly.Elements();
const cardElement = elements.CardElement();

cardElement.on('coBadge', handleCoBadgeEvent);

function handleCoBadgeEvent(payload) {
  // handle event, e.g., show selection UI if coBadgeSupport is true
}
```

***

### Step 2: Handle the `coBadge` Event Payload

When the `coBadge` event fires, you'll receive a payload with:

| **Field**         | **Type**  | **Description**                                                                                                         |
| ----------------- | --------- | ----------------------------------------------------------------------------------------------------------------------- |
| `coBadgeSupport`  | `Boolean` | Indicates whether the card supports co-badged options.                                                                  |
| `supportedBrands` | `Array`   | List of brands the customer can choose from (e.g., `["visa", "cartes_bancaires"]`). Empty if `coBadgeSupport` is false. |

***

### Step 3: Display Brand Selection to the Customer

Use the `supportedBrands` array to present a UI that allows the customer to select one brand.
This could be radio buttons, a dropdown, or a toggle.

Include the `data-recurly="card_network_preference"` attribute so Recurly.js can capture
the customer's selection:

```html
<div id="co-badge-div">
  <input
    type="radio"
    value="brand1"
    id="co-badge-id-0"
    name="co-badge"
    data-recurly="card_network_preference"
  />
  <label for="co-badge-id-0">brand1</label>

  <input
    type="radio"
    value="brand2"
    id="co-badge-id-1"
    name="co-badge"
    data-recurly="card_network_preference"
  />
  <label for="co-badge-id-1">brand2</label>
</div>
```

> **Warning**<br />Ensure the customer **chooses a brand** before you proceed to tokenize or<br />submit the form.

### Step 4: Tokenize the Payment Information

After the customer selects a brand, follow the [Getting a Token](https://recurly.com/developers/reference/recurly-js/#getting-a-token)
guide to tokenize their card details with Recurly.js. The card network preference is
automatically included during tokenization, allowing Recurly to process the customer's
chosen brand.

> **Note**<br />The customer's selection is also available in the Element's `change` event
> state as `cardNetworkPreference`, so you can display or validate the chosen network before
> submitting. If both the built-in selector and a custom `data-recurly="card_network_preference"`
> input are present, the built-in selector's selection takes precedence.
