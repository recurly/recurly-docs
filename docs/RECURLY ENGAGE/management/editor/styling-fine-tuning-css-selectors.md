---
title: Styling/ Fine tuning (CSS selectors)
excerpt: >-
  CSS selector reference for customizing the look and feel of Recurly Engage
  prompts.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

This page provides a structured reference of CSS selectors you can override to style prompts across devices and prompt types.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Familiarity with CSS and your site’s stylesheet.
* Custom styles must be loaded after the default Recurly Engage CSS to take effect.

# Definition

**Prompt Styling** refers to the customization of prompt elements—layout containers, text areas, buttons, and form controls—via CSS selectors.

# Key benefits

* **Full branding control**: Match prompts to your application’s design system.
* **Responsive tweaks**: Adjust styles for desktop, mobile, and TV viewports.
* **Targeted overrides**: Fine-tune individual prompt types without affecting others.

# Key details

## Quick reference

Use these core selectors to modify the default styling of any Recurly Engage prompt.

| Selector                     | Description                    |
| ---------------------------- | ------------------------------ |
| `.rfmodal-content-wrapper`   | Prompt area (outer container)  |
| `.rfmodal-inner-wrapper`     | Prompt text content area       |
| `.rfmodal-backgroundimage`   | Background image/video element |
| `.rfmodal-header`            | Prompt title                   |
| `.rfmodal-header-mobileweb`  | Mobile prompt title            |
| `.rfmodal-message`           | Prompt message body            |
| `.rfmodal-message-mobileweb` | Mobile message body            |
| `.rfmodal-button-yes`        | Primary accept button          |
| `.rfmodal-button-no`         | Secondary button               |
| `.rfmodal-footer`            | Footer container for buttons   |
| `.rfmodal-close`             | Dismiss (close) button         |
| `#rfmodal-close-icon`        | Dismiss icon                   |
| `.rf-radio-group`            | Survey form options wrapper    |
| `.rf-radio-item`             | Individual survey option       |

## Full Reference

Detailed selectors by prompt context and device.

### Desktop (Video(web), retention\_modal(web), ios, android\_os, tv\_os, roku\_os)

| Selector                       | Description               |
| ------------------------------ | ------------------------- |
| `.rfmodal-content.outer-modal` | Modal container           |
| `.rfmodal-backgroundimage`     | Background image or video |
| `.rfmodal-wrapper.inner-modal` | Inner content wrapper     |

### Mobile (Video(web), retention\_modal(web), interstitial(web), ios, android\_os, tv\_os, roku\_os)

| Selector                        | Description                   |
| ------------------------------- | ----------------------------- |
| `.mobileFrameDisplay`           | Mobile interstitial container |
| `.mobileFrameInner`             | Inner frame wrapper           |
| `.rfmodal-backgroundimage`      | Background image for modal    |
| `.mobileWebModalWrapper`        | Mobile modal wrapper          |
| `.mobilewebModalContentWrapper` | Content wrapper               |
| `.videoPosterImgDefault`        | Video poster image            |

### Mobile (widget(web), bottom\_banner(web))

| Selector                        | Description                   |
| ------------------------------- | ----------------------------- |
| `.mweb-widget-container`        | Widget prompt container (web) |
| `.mweb-phone-kit-bg`            | Inner widget frame            |
| `.mweb-canvas-bound`            | Canvas wrapper                |
| `.mweb-widget-wrapper`          | Layout wrapper                |
| `.rfmodal-backgroundimage`      | Widget background image       |
| `.mobilewebModalContentWrapper` | Widget content wrapper        |
| `.mweb-widget-msg-container`    | Message wrapper               |
| `.mweb-widget-spacer`           | Message spacer                |
| `.mweb-widget-content-colm`     | Message content column        |
| `.rfmodal-footer-mobileweb`     | Buttons and countdown wrapper |

### Desktop (widget(web))

| Selector                               | Description          |
| -------------------------------------- | -------------------- |
| `.modal-overlay-style.widget-rf-promo` | Widget modal overlay |
| `.rf-widgetpromo-wrapper`              | Inner frame wrapper  |
| `.rfmodal-backgroundimage`             | Background image     |
| `.rfmodal-wrapper`                     | Content wrapper      |

### Desktop (interstitial(web))

| Selector                                 | Description           |
| ---------------------------------------- | --------------------- |
| `.modal-overlay-style.interstitialModal` | Interstitial overlay  |
| `.rfmodal-content.outer-modal`           | Outer modal container |
| `.rfmodal-wrapper.inner-modal`           | Inner modal wrapper   |

### Desktop (text)

| Selector                        | Description           |
| ------------------------------- | --------------------- |
| `.promo-text-wrapper`           | Prompt text container |
| `.promo-text-wrapper-container` | Text container        |
| `.promo-text-title`             | Text title            |
| `.promo-text-message`           | Text message body     |

### Mobile (text)

| Selector                        | Description           |
| ------------------------------- | --------------------- |
| `.promo-text-wrapper-mobile`    | Prompt text container |
| `.promo-text-wrapper-container` | Text container        |
| `.promo-text-title`             | Text title            |
| `.promo-text-message`           | Text message body     |

### Desktop (horizontal, tile, vertical)

| Selector                        | Description           |
| ------------------------------- | --------------------- |
| `.promo-tile-wrapper`           | Prompt tile container |
| `.promo-tile-backgroundimage`   | Tile background image |
| `.promo-tile-wrapper-container` | Alignment wrapper     |
| `.tile-header-msg-wrp`          | Message wrapper       |

### Mobile (horizontal, tile, vertical)

| Selector                      | Description           |
| ----------------------------- | --------------------- |
| `.rtile-mweb-content-wrapper` | Inline tile container |
| `.rtile-mweb-content`         | Content wrapper       |
| `.rfmodal-backgroundimage`    | Background image      |
| `.rtile-mweb-content-msg`     | Message wrapper       |

### Desktop, Mobile (email)

| Selector              | Description            |
| --------------------- | ---------------------- |
| `.pr-email-logo`      | Email logo             |
| `.pr-email-wrapper`   | Email content wrapper  |
| `.pr-email-container` | Email container        |
| `.pr-email-image`     | Email image            |
| `.pr-email-msg`       | Message container      |
| `.pr-email-msg-title` | Message title          |
| `.pr-email-msg-body`  | Message body           |
| `.pr-email-btn`       | Buttons wrapper        |
| `.pr-email-footer`    | Footer links container |

### Desktop (bottom\_banner)

| Selector                                  | Description             |
| ----------------------------------------- | ----------------------- |
| `.modal-overlay-style.banner-rf-promo`    | Banner overlay          |
| `.rfmodal-content.rf-bannerpromo-wrapper` | Banner layout wrapper   |
| `.rfmodal-backgroundimage`                | Banner background image |
| `.rfmodal-wrapper`                        | Content wrapper         |

## Basic Components

### Buttons

| Selector                              | Description              |
| ------------------------------------- | ------------------------ |
| `.rfmodal-button-yes.primary-btn-p`   | Primary confirm button   |
| `.rfmodal-button-yes.secondary-btn-p` | Secondary confirm button |
| `.rfmodal-button-no`                  | Cancel/decline button    |

### Tile Buttons

| Selector                                  | Description           |
| ----------------------------------------- | --------------------- |
| `.promo-tile-wrapper-btn-accept`          | Primary tile button   |
| `.promo-tile-wrapper-btn-accept.btn-ac-2` | Secondary tile button |
| `.promo-tile-wrapper-btn-no`              | Cancel tile button    |

### Survey input

| Selector                               | Description             |
| -------------------------------------- | ----------------------- |
| `.survey-wrapper` (.center-align-mode) | Survey wrapper (center) |
| `.survey-wrapper` (.right-align-mode)  | Survey wrapper (right)  |
| `.rf-radio-group`                      | Radio buttons wrapper   |
| `.rf-radio-item`                       | Individual radio item   |

### Input

| Selector                    | Description         |
| --------------------------- | ------------------- |
| `.rfmodal-input-wrapper`    | Input container     |
| `.rfmodal-input-label`      | Input label         |
| `.rfmodal-input-inputfield` | Input field element |

### Close button

| Selector              | Description        |
| --------------------- | ------------------ |
| `.rfmodal-close`      | Modal close button |
| `#rfmodal-close-icon` | Close icon         |

### TOS

| Selector             | Description           |
| -------------------- | --------------------- |
| `.modal-privacy-tos` | Terms of service link |

### Mobile header and body

| Selector                     | Description           |
| ---------------------------- | --------------------- |
| `.rfmodal-header-mobileweb`  | Mobile header text    |
| `.rfmodal-body-mobileweb`    | Mobile body container |
| `.rfmodal-message-mobileweb` | Mobile message text   |

### Mobile footer

| Selector                    | Description                   |
| --------------------------- | ----------------------------- |
| `.rfmodal-footer-mobileweb` | Buttons and countdown wrapper |
| `.rfmodal-countdown`        | Countdown timer label         |

### Desktop Retention Message

| Selector                                    | Description                   |
| ------------------------------------------- | ----------------------------- |
| `.video-volume-control`                     | Video volume control button   |
| `.rfmodal-inner-wrapper`                    | Inner content container       |
| `.rfmodal-content-wrapper` (.b-left-align)  | Left alignment wrapper        |
| `.rfmodal-content-wrapper` (.b-right-align) | Right alignment wrapper       |
| `.rfmodal-text-container`                   | Text content container        |
| `.rfmodal-header`                           | Content header                |
| `.rfmodal-body`                             | Content body                  |
| `.rfmodal-message`                          | Content message               |
| `.rfmodal-footer`                           | Footer container              |
| `.rf-button-wrapper`                        | Buttons and countdown wrapper |
| `.rf-buttons-inner`                         | Button wrapper                |
| `.rfmodal-countdown`                        | Countdown label               |

### Prompt Content

| Selector                     | Description     |
| ---------------------------- | --------------- |
| `.promo-tile-wrapper-header` | Message header  |
| `.promo-tile-wrapper-body`   | Message body    |
| `.promo-tile-wrapper-footer` | Message footer  |
| `.promo-tile-wrapper-btn`    | Buttons wrapper |

## Fine Tuning

For advanced scenarios—absolute positioning, delay handling, and responsive resizing—review the fine-tuning guide to optimize prompt performance and appearance.

## Tools and Resources

Recurly Engage offers:

1. Live Tool and Live Preview for style testing.
2. Custom CSS overrides and HTML enhancements.
3. Direct support from the Recurly technical team.