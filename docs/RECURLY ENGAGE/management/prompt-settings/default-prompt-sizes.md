---
title: Default prompt sizes
excerpt: >-
  Configuration guide for default prompt sizes and CSS controls in Recurly
  Engage.
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

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **Default Prompt Sizes** table specifies recommended aspect ratios, dimensions, and CSS selectors for each prompt type on desktop and mobile browsers.

# Key benefits

* **Consistent appearance**: Standardize prompt dimensions for a unified look and feel.
* **Responsive design**: Provide optimized sizes for both desktop and mobile environments.
* **Developer-friendly**: Expose CSS selectors to facilitate styling and customization.

# Key details

| Prompt Type   | Supported Aspect Ratios (DESKTOP) | Recommended Size (DESKTOP)                                              | Recommended Size (MOBILE BROWSER) | CSS Controls (DESKTOP)                                                                                                                                                               | CSS Controls (MOBILE BROWSER)                                                                                                                                                                                                                                                                                          |
| ------------- | --------------------------------- | ----------------------------------------------------------------------- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Horizontal    | 2:1, 4:1, 6:1, 8:1, 10:1          | 960 × 300 px                                                            | 300 × 200 px                      | .tile-header-msg-wrp – Text Container\<br>.promo-tile-wrapper-header – Prompt title\<br>.promo-tile-wrapper-body – Prompt message\<br>.promo-tile-wrapper-footer – Buttons Container | **.rtile-mweb-content-msg** – Text Container.                                 **.rtile-mweb-content-footer** – Buttons Container                                                                                                                                                                                       |
| Vertical      | 1:2, 1:3, 1:4                     | 250 × 500 px                                                            | 200 × 300 px                      | .tile-header-msg-wrp – Text Container\<br>.promo-tile-wrapper-header – Prompt title\<br>.promo-tile-wrapper-body – Prompt message\<br>.promo-tile-wrapper-footer – Buttons Container | **.rtile-mweb-content-msg** – Text Container                                        **.rtile-mweb-content-footer** – Buttons Container                                                                                                                                                                                 |
| Tile          | 1:1, 1:2                          | 250 × 500 px                                                            | 375 × 205 px                      | .tile-header-msg-wrp – Text Container\<br>.promo-tile-wrapper-header – Prompt title\<br>.promo-tile-wrapper-body – Prompt message\<br>.promo-tile-wrapper-footer – Buttons Container | **.rtile-mweb-content-msg** – Text Container                                        **.rtile-mweb-content-footer** – Buttons Container                                                                                                                                                                                 |
| Text Only     | 6:1, 8:1, 10:1                    | 100% × auto                                                             | 100% × auto                       | .promo-text-wrapper-container – Text Container\<br>.promo-text-title – Prompt title\<br>.promo-text-message – Prompt message                                                         | **.promo-text-wrapper-mobile** – Text Container                                                                                                                                                                                                                                                                        |
| Notification  | —                                 | 450 × 180 px                                                            | 100% × 120 px                     | .rfmodal-text-container – Text Container\<br>.rfmodal-header – Prompt title\<br>.rfmodal-message – Prompt message\<br>.rfmodal-footer – Buttons Container                            | **.mweb-widget-msg-container** – Text Container                          **.rfmodal-header-mobileweb** – Prompt title                               **.rfmodal-message-mobileweb** – Prompt message                      **.rfmodal-footer-mobileweb** – Buttons Container                                             |
| Interstitial  | —                                 | 1200 × 800 px (text/button area)                                        | —                                 | .rfmodal-text-container – Text Container\<br>.rfmodal-header – Prompt title\<br>.rfmodal-message – Prompt message\<br>.rfmodal-footer – Buttons Container                            | **.mobilewebModalContentWrapper** – Text Container                          **.rfmodal-header-mobileweb**         – Prompt title                                       **.rfmodal-message-mobileweb**           – Prompt message\                    **.rfmodal-footer-mobileweb**                 – Buttons Container |
| Popup         | —                                 | Large: 1200 × 800 px<br />Medium: 960 × 640 px<br />Small: 750 × 500 px | 500 × 800 px                      | .rfmodal-text-container – Text Container\<br>.rfmodal-header – Prompt title\<br>.rfmodal-message – Prompt message\<br>.rfmodal-footer – Buttons Container                            | **.mobilewebModalContentWrapper** – Text Container                                                       **.rfmodal-header-mobileweb** – Prompt title                                     **.rfmodal-message-mobileweb** – Prompt message                           **.rfmodal-footer-mobileweb** – Buttons Container  |
| Video         | —                                 | Large: 1200 × 619 px<br />Medium: 960 × 619 px<br />Small: 750 × 619 px | —                                 | .rfmodal-text-container – Text Container\<br>.rfmodal-header – Prompt title\<br>.rfmodal-message – Prompt message\<br>.rfmodal-footer – Buttons Container                            | .mobilewebModalContentWrapper – Text Container                      .rfmodal-header-mobileweb – Prompt title                              .rfmodal-message-mobileweb – Prompt message                      .rfmodal-footer-mobileweb – Buttons Container                                                               |
| Bottom Banner | —                                 | 1000 × 100 px                                                           | 100% × 120 px                     | .rfmodal-text-container – Text Container\<br>.rfmodal-header – Prompt title\<br>.rfmodal-message – Prompt message\<br>.rfmodal-footer – Buttons Container                            | .mweb-widget-msg-container – Text Container                        .rfmodal-header-mobileweb – Prompt title                             .rfmodal-message-mobileweb – Prompt message                     .rfmodal-footer-mobileweb – Buttons Container                                                                  |