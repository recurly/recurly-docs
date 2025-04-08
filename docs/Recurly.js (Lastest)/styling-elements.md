---
title: Styling elements
deprecated: false
hidden: false
metadata:
  robots: index
---
Since elements are within iframes, any style properties within those iframes must be configured on your `Element`. See the code example and table below.

```javascript
const cardElement = elements.CardElement({
  inputType: 'mobileSelect',
  style: {
    fontSize: '1em',
    placeholder: {
      color: 'gray !important',
      fontWeight: 'bold',
      content: {
        number: 'Card number',
        cvv: 'CVC'
      }
    },
    invalid: {
      fontColor: 'red'
    }
  }
});
```

### Styling the card element

Options available to the card element are detailed in the following table.

| Property                         | Default             | Description                                                                                                                                                                                                                                                                                                                                                |
| :------------------------------- | :------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| displayIcon                      | `true`              | If false, the card brand icon will be hidden                                                                                                                                                                                                                                                                                                               |
| inputType                        | `'text'`            | Modifies the input type of the card field: `text` - text input for all fields.  `mobileSelect` - if the user is using a mobile device, a native expiry select interface will appear when entering the expiration date.  `select` - Expiration date will be input using a select field on all devices.  Mobile devices will display an optimized interface. |
| style                            | `{}`                | See **common field style properties** section below.                                                                                                                                                                                                                                                                                                       |
| style.fontColor                  | `'#545457'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) for each input element                                                                                                                                                                                                                                                                |
| style.fontFamily                 | `'Source Sans Pro'` | [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) for each input element                                                                                                                                                                                                                                                         |
| style.fontSize                   | `'16px'`            | [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) for each input element                                                                                                                                                                                                                                                             |
| style.fontWeight                 | `700`               | [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) for each input element                                                                                                                                                                                                                                                         |
| style.placeholder                | `{}`                | Object                                                                                                                                                                                                                                                                                                                                                     |
| style.placeholder.color          | `'#a3a3a7'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to all placeholder text                                                                                                                                                                                                                                                       |
| style.placeholder.content        | `{}`                | Object                                                                                                                                                                                                                                                                                                                                                     |
| style.placeholder.content.number | `'Card number'`     | Placeholder content for the number input.                                                                                                                                                                                                                                                                                                                  |
| style.placeholder.content.expiry | `'MM / YY'`         | Placeholder content for the expiry input.                                                                                                                                                                                                                                                                                                                  |
| style.placeholder.content.cvv    | `'CVV'`             | Placeholder content for the card verification value input.                                                                                                                                                                                                                                                                                                 |
| style.invalid                    | `{}`                | Object. Style to apply to input elements when they contain an invalid value. See **common field style properties** section below.                                                                                                                                                                                                                          |
| style.invalid.fontColor          | `'#a3a3a7'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to invalid input elements.                                                                                                                                                                                                                                                    |
| tabIndex                         |                     | [tabindex](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) property to be applied to the outer iframe.                                                                                                                                                                                                                       |

### Styling the individual card elements

Options unique to the individual card elements are detailed in the following table.

| Property                  | Default | Description                                                                                                                                                                                                                           |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| format                    | `true`  | Enables contextual input formatting, injecting spaces to match the card brand, and forcing numeric input on expiry and cvv.                                                                                                           |
| inputType                 | `text`  | Modifies the input type of the expiry fields. `'text'` - normal text input.  `'mobileSelect'` - if the user is using a mobile device, a native select interface will appear.  `'select'` - A select field will display on all devices |
| style                     | `{}`    | See **common field style properties** section below.                                                                                                                                                                                  |
| style.padding             |         | [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)                                                                                                                                                                   |
| style.placeholder.color   |         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to the placeholder text.                                                                                                                                 |
| style.placeholder.content | `''`    | Placeholder content (e.g. `'Card number'`, `'CVV'`)                                                                                                                                                                                   |
| tabIndex                  |         | [tabIndex](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) property to be applied to the outer iframe.                                                                                                  |

### Common field style properties

| Property                  | Default       | Reference                                                                                       |
| :------------------------ | :------------ | :---------------------------------------------------------------------------------------------- |
| style.fontColor           | `'black'`     | [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color)                                 |
| style.fontFamily          | `'Helvetica'` | [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)                     |
| style.fontFeatureSettings | `'normal'`    | [font-feature-settings](https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings) |
| style.fontKerning         | `'auto'`      | [font-kerning](https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning)                   |
| style.fontSize            | `'normal'`    | [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)                         |
| style.fontSmoothing       | `'normal'`    | [font-smoothing](https://developer.mozilla.org/en-US/docs/Web/CSS/font-smoothing)               |
| style.fontStretch         | `'normal'`    | [font-stretch](https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch)                   |
| style.fontStyle           | `'normal'`    | [font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)                       |
| style.fontVariant         | `'normal'`    | [font-variant](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)                   |
| style.fontWeight          | `'normal'`    | [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)                     |
| style.letterSpacing       | `'normal'`    | [letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)               |
| style.lineHeight          | `'normal'`    | [line-height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)                     |
| style.textAlign           |               | [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)                       |
| style.textDecoration      |               | [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)             |
| style.textRendering       | `'auto'`      | [text-rendering](https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering)               |
| style.textShadow          | `'none'`      | [text-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)                     |
| style.textTransform       | `'none'`      | [text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)               |

### CSS Classes

Since Recurly.js Elements are contained within iframes, the default browser appearance for those fields will likely not match the appearance of the other inputs in your billing form. We provide the following CSS classes to achieve a look and feel similar to your form. Using these classes, you may specify Element size, colors, and a full range of appearance customization to make the injected Elements blend into your payment form.

| Class                   | Description                                                 |
| :---------------------- | :---------------------------------------------------------- |
| recurly-element         | Styles for all Recurly Element containers.                  |
| recurly-element-focus   | Styles applied when a user focuses on an Element.           |
| recurly-element-invalid | Styles applied when an Element contains invalid input.      |
| recurly-element-card    | Styles specific to combined card Element container.         |
| recurly-element-number  | Styles specific to the card number Element container.       |
| recurly-element-month   | Styles specific to the card expiry month Element container. |
| recurly-element-year    | Styles specific to the card expiry year Element container.  |
| recurly-element-cvv     | Styles specific to the card cvv Element container.          |

### Custom Fonts

Custom fonts are sourced from [Google Web Fonts](https://www.google.com/fonts).  Simply use the name of the font as it appears on the Google Web Fonts site.

### Responsive Styles

All of the built in element CSS classes will support and respond to media queries.  You may call `Element.configure` to change style properties for an individual Element -- thus you may change any property according to your responsive needs.