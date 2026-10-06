---
title: Elements
excerpt: >-
  Full reference for **Recurly.js Elements**—creating groups and fields,
  attaching them to your DOM, configuring styles, and handling events.
deprecated: false
hidden: false
metadata:
  robots: index
---
Elements are secure, iframed inputs that keep you in PCI SAQ A while giving you complete design control. Create an `Elements` group, add card fields (combined or individual), and interact with them through a consistent JavaScript API.

***

# Key details

## Elements

> **Note – Using Hosted Fields?**<br />Earlier Recurly.js versions rendered payment fields with _Hosted Fields_. That feature is now deprecated. We recommend [upgrading to Elements](#upgrading-from-hosted-fields-to-elements); however, v4 retains backward-compatibility. See the [v4.10.3 documentation](https://docs.recurly.com/v1.2/docs/overview-recurlyjs#/) for Hosted Fields details.

Elements allow sensitive customer payment information to be securely accepted via iframes. They are controlled in groups by an `Elements` instance.

To use Elements, you will first create an Elements instance.

```js
const elements = recurly.Elements();
```

There are several types of Elements which you may wish to use. The most common is the `CardElement`.

```js
const cardElement = elements.CardElement();
```

Recurly.js also provides individual card Elements.

```js
const cardNumberElement = elements.CardNumberElement();
const cardMonthElement  = elements.CardMonthElement();
const cardYearElement   = elements.CardYearElement();
const cardCvvElement    = elements.CardCvvElement();
```

The reference below details the common API for interacting with `Elements` and `Element` instances. While you may be working with different `Element` types, their API is the same.

### Reference

#### **fn** – recurly.Elements

Creates an Elements instance, which associates a group of `Element` instances for tokenization and control. You will use this to create individual Element instances.

```js
const elements = recurly.Elements();
```

##### Returns

A new **Elements** instance.

##### **event** – Emits

See [Events](#events) for usage.

| Event name | Payload | Occurs when                                                                                    |
| ---------- | ------- | ---------------------------------------------------------------------------------------------- |
| **submit** | —       | A user presses <kbd>Enter</kbd> while using an `Element` created with the `Elements` instance. |

***

#### **fn** – elements.CardElement

#### **fn** – elements.CardNumberElement

#### **fn** – elements.CardMonthElement

#### **fn** – elements.CardYearElement

#### **fn** – elements.CardCvvElement

Create an `Element` instance of the type respective of its name.

```js
const cardElement = elements.CardElement({
  style: {
    fontSize: '2em'
  }
});
```

##### Arguments

| Param                     | Type    | Description                                                                                                                                                                                                                   |
| ------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                 | Object  |                                                                                                                                                                                                                               |
| `options.inputType`       | String  | See [Styling Elements](#styling-elements)                                                                                                                                                                                     |
| `options.coBadgeSelector` | Boolean | When `true`, the card field displays a network chooser whenever a co-badged card is detected, letting the customer pick a network in the field. Defaults to `false`. See the [Co-badged cards guide](#co-badged-cards-guide). |
| `options.style`           | Object  | See [Styling Elements](#styling-elements)                                                                                                                                                                                     |

##### Returns

A new **Element** instance.

##### **event** – Emits

See [Events](#events) for usage.

| Event name  | Payload          | Occurs when                                              |
| ----------- | ---------------- | -------------------------------------------------------- |
| **change**  | `ElementState`   | The Element state changes.                               |
| **focus**   | —                | A user focuses on the Element.                           |
| **blur**    | —                | A user removes focus from the Element.                   |
| **submit**  | —                | A user presses <kbd>Enter</kbd> while using the Element. |
| **attach**  | —                | The Element has completed attaching to the DOM.          |
| **remove**  | —                | The Element has been removed from the DOM.               |
| **coBadge** | `CoBadgeResults` | The user enters a valid card number.                     |

***

#### Co-badged card support

For cards belonging to more than one network (e.g. Visa/Cartes Bancaires), you can let
the customer choose their preferred network directly in the field:

```js
const cardElement = elements.CardElement({ coBadgeSelector: true });
```

When a co-badged card number is entered, the supported network marks appear in place of<br />the card brand icon. The network detected from the card's BIN is selected by default; the<br />customer can switch using a pointer, keyboard (<kbd>Tab</kbd> into the selector, then<br /><kbd>←</kbd>/<kbd>→</kbd>), or a screen reader.&#x20;

The selection is included automatically in the token — no additional wiring is required. See the [Co-badged cards guide](#co-badged-cards-guide).

The Element's `change` event state includes the current selection as
`cardNetworkPreference` while a co-badged card is detected.

**Legacy Hosted Fields note**

The `coBadgeSelector` option is also available with legacy `recurly.hostedFields`
(`fields: { number: { coBadgeSelector: true } }` or `fields: { card: … }`).

***

#### **fn** – Element.attach

Attaches an `Element` to the DOM as a child of the specified parent target.

```js
element.attach('#my-element-container');
```

##### Arguments

| Param    | Type                      | Description                                                                                                                   |
| -------- | ------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `parent` | `HTMLElement` or `String` | Target element (or selector) **not** being a [void HTML element](https://www.w3.org/TR/html-markup/syntax.html#void-element). |

##### Returns

The **Element** instance.

***

#### **fn** – Element.configure

Updates the configuration of the Element.

```js
element.configure({
  style: { fontSize: '2em' }
});
```

##### Arguments

| Param                     | Type    | Description                                                                                                                                                                                         |
| ------------------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `options`                 | Object  |                                                                                                                                                                                                     |
| `options.inputType`       | String  | See [Styling Elements](#styling-elements)                                                                                                                                                           |
| `options.coBadgeSelector` | Boolean | When `true`, the card field displays a network chooser whenever a co-badged card is detected, letting the customer pick a network in the field. Defaults to `false`. See the Co-badged cards guide. |
| `options.style`           | Object  | See [Styling Elements](#styling-elements)                                                                                                                                                           |

##### Returns

The **Element** instance.

***

#### **fn** – Element.focus

Moves the user's focus to the Element.

_Safari allows programmatic focus only after prior user interaction._

##### Returns

The **Element** instance.

***

#### **fn** – Element.remove

If attached, removes the Element from the DOM; otherwise does nothing.

##### Returns

The **Element** instance.
