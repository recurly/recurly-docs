---
title: Styling card fields
excerpt: Learn about Styling Card Fields in Recurly.js version
deprecated: false
hidden: false
metadata:
  robots: index
---
## Styling card fields

### Style configuration

Since card fields must be injected within iframes, any style properties within those iframes must be passed to `recurly.configure`. See the code example at right.

### Styling the combined card field

Options unique to the combined card field are detailed in the following table. When passed into your `recurly.configure` call, each property must be nested within `fields.card`.

### Combined card field properties

| Property                         | Default             | Description                                                                                                                                                                                                                                                                                                                                                |
| :------------------------------- | :------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| displayIcon                      | `true`              | If false, the card brand icon will be hidden                                                                                                                                                                                                                                                                                                               |
| inputType                        | `'text'`            | Modifies the input type of the card field: `text` - text input for all fields.  `mobileSelect` - if the user is using a mobile device, a native expiry select interface will appear when entering the expiration date.  `select` - Expiration date will be input using a select field on all devices.  Mobile devices will display an optimized interface. |
| selector                         |                     | Specify a custom target selector (e.g. `'#recurly-card'`)                                                                                                                                                                                                                                                                                                  |
| style                            | `{}`                | See **common field style properties** section below.                                                                                                                                                                                                                                                                                                       |
| style.fontColor                  | `'#545457'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) for each input element                                                                                                                                                                                                                                                                |
| style.fontFamily                 | `'Source Sans Pro'` | [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) for each input element                                                                                                                                                                                                                                                         |
| style.fontSize                   | `'16px'`            | [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) for each input element                                                                                                                                                                                                                                                             |
| style.placeholder                | `{}`                | Object                                                                                                                                                                                                                                                                                                                                                     |
| style.placeholder.color          | `'#a3a3a7'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to all placeholder text                                                                                                                                                                                                                                                       |
| style.placeholder.content        | `{}`                | Object                                                                                                                                                                                                                                                                                                                                                     |
| style.placeholder.content.number | `'Card number'`     | Placeholder content for the number input.                                                                                                                                                                                                                                                                                                                  |
| style.placeholder.content.expiry | `'MM / YY'`         | Placeholder content for the expiry input.                                                                                                                                                                                                                                                                                                                  |
| style.placeholder.content.cvv    | `'CVV'`             | Placeholder content for the card verification value input.                                                                                                                                                                                                                                                                                                 |
| style.invalid                    | `{}`                | Object. Style to apply to input elements when they contain an invalid value. See **common field style properties** section below.                                                                                                                                                                                                                          |
| style.invalid.fontColor          | `'#a3a3a7'`         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to invalid input elements.                                                                                                                                                                                                                                                    |
| tabIndex                         |                     | [tabindex](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) property to be applied to the outer iframe.                                                                                                                                                                                                                       |

### Styling the individual card fields

Options unique to the individual card fields are detailed in the following table. When passed into your `recurly.configure` call, each property must be nested within `fields.all` or a respective `fields.number`, `fields.month`, `fields.year`, or `fields.cvv` object.

### Individual card field properties

| Property                  | Default | Description                                                                                                                                                                                                                           |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| format                    | `true`  | Enables contextual input formatting, injecting spaces to match the card brand, and forcing numeric input on expiry and cvv.                                                                                                           |
| inputType                 | `text`  | Modifies the input type of the expiry fields. `'text'` - normal text input.  `'mobileSelect'` - if the user is using a mobile device, a native select interface will appear.  `'select'` - A select field will display on all devices |
| selector                  |         | Specify a custom target selector (e.g. `'#recurly-number'`)                                                                                                                                                                           |
| style                     | `{}`    | See **common field style properties** section below.                                                                                                                                                                                  |
| style.padding             |         | [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)                                                                                                                                                                   |
| style.placeholder.color   |         | Font [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) applied to the placeholder text.                                                                                                                                 |
| style.placeholder.content | `''`    | Placeholder content (e.g. `'Card number'`, `'CVV'`)                                                                                                                                                                                   |
| tabIndex                  |         | [tabIndex](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) property to be applied to the outer iframe.                                                                                                  |

### Common field style properties

| Property                  | Default                        | Reference                                                                                       |
| :------------------------ | :----------------------------- | :---------------------------------------------------------------------------------------------- |
| style.fontColor           | `'black'`                      | [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color)                                 |
| style.fontFamily          | `'source sans pro'`            | [font-family](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)                     |
| style.fontFeatureSettings | `'normal'`                     | [font-feature-settings](https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings) |
| style.fontKerning         | `'auto'`                       | [font-kerning](https://developer.mozilla.org/en-US/docs/Web/CSS/font-kerning)                   |
| style.fontSize            | `'normal'`                     | [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size)                         |
| style.fontSmoothing       | `'normal'`                     | [font-smoothing](https://developer.mozilla.org/en-US/docs/Web/CSS/font-smooth)                  |
| style.fontStretch         | `'100%'`                       | [font-stretch](https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch)                   |
| style.fontStyle           | `'normal'`                     | [font-style](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)                       |
| style.fontVariant         | `'normal'`                     | [font-variant](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)                   |
| style.fontWeight          | `400`                          | [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)                     |
| style.letterSpacing       | `'normal'`                     | [letter-spacing](https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing)               |
| style.lineHeight          | `'normal'`                     | [line-height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)                     |
| style.textAlign           | `'start'`                      | [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)                       |
| style.textDecoration      | `'none solid rgb(84, 84, 87)'` | [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration)             |
| style.textRendering       | `'auto'`                       | [text-rendering](https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering)               |
| style.textShadow          | `'none'`                       | [text-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)                     |
| style.textTransform       | `'none'`                       | [text-transform](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)               |

### Example style configuration

```javascript
recurly.configure({
  publicKey: 'my-public-key',
  fields: {
    // affects all fields
    all: {
      style: {
        fontFamily: 'Helvetica, sans-serif'
      }
    },

    // affects the combined card field
    card: {
      displayIcon: true,
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
    },

    // affects individual card field types
    number: {
      // Custom target selector
      selector: '#recurly-number',
      // Format the card number
      format: true
    },
    month: {
      // Display a month select on mobile devices
      inputType: 'mobileSelect',
      style: {
        placeholder: {
          content: 'MM'
        }
      }
    },
    year: {
      style: {
        placeholder: {
          content: 'YYYY'
        }
      }
    },
    cvv: {}
  }
});
```

### CSS classes

Since Recurly.js must inject card data fields into iframes, the default browser appearance for those fields will likely not match the appearance of the other fields in your payment form. We provide the following CSS classes to achieve a look and feel similar to your form. Using these classes, you may specify field size, colors, and a full range of appearance customization to make the injected card fields blend into your payment form.

| Class Name                  | Description                                                            |
| :-------------------------- | :--------------------------------------------------------------------- |
| recurly-hosted-field        | Default styles for the div surrounding each field iframe.              |
| recurly-hosted-field-focus  | Applied when the user focuses on a field.                              |
| recurly-hosted-field-card   | Default styles for the div surrounding the combined card field iframe. |
| recurly-hosted-field-number | Default styles for the div surrounding the number field iframe.        |
| recurly-hosted-field-month  | Default styles for the div surrounding the month field iframe.         |
| recurly-hosted-field-year   | Default styles for the div surrounding the year field iframe.          |
| recurly-hosted-field-cvv    | Default styles for the div surrounding the cvv field iframe.           |

### Custom fonts

You may specify font and placeholder text for card fields through `recurly.configure`. The example call above demonstrates all available style attributes you may send to `recurly.configure`.

Custom fonts are sourced from [Google Web Fonts](https://www.google.com/fonts). Simply use the name of the font as it appears on the Google Web Fonts site.

### Responsive styles

All of the built in field classes will support and respond to media queries. You may call `recurly.configure` again to change style properties within each field -- thus you may change any property if the window size changes.