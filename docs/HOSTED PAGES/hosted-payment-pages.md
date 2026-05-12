---
title: Hosted payment page
excerpt: >-
  Set up and customize Recurly's Hosted Payment Pages to collect subscriptions
  securely with minimal technical integration.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

> ⚠️ **Deprecated**
>
> Hosted Payment Pages are deprecated and only supported for legacy purposes. No further updates will be made to this feature. For new implementations, use [Recurly Checkout](/docs/checkout) instead.

### Video

<iframe class="embedly-embed" src="//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FFEfoB7miNVk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DFEfoB7miNVk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FFEfoB7miNVk%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube" width="800" height="580" scrolling="no" title="YouTube embed" frameborder="0" allow="autoplay; fullscreen; encrypted-media; picture-in-picture;" allowfullscreen="true" />

### Required plan

This feature is available to all customers on any Recurly subscription plan.

### Limitations

* Hosted Payment Pages don't support iframes due to PCI compliance and security requirements.
* reCAPTCHA activates after three failed transaction attempts from the same IP address within a 24-hour window.

# Definition

Recurly's Hosted Payment Pages are pre-built, secure checkout experiences where your customers sign up for subscriptions without leaving your domain. Paired with Account Management Pages, they give you a PCI-compliant, customizable, and friction-free way to collect payments and subscriber data.

# Key benefits

* **Minimal setup**: No complex integration required — point customers to a URL and you're done.
* **Customizable branding**: Choose between Classic or Modern designs and add your company colors and logo.
* **Global reach**: Support for 14 languages and automatic currency detection based on customer location.
* **Built-in security**: reCAPTCHA protection and Recurly's PCI-compliant infrastructure keep fraud at bay.
* **Flexible data collection**: Gather basic contact info or advanced fields like company name, VAT number, and shipping address.

# Key details

## Look and feel

Personalize your Hosted Payment Pages with your brand. Choose between two design templates:

* **Classic**: A traditional, proven design that works everywhere.
* **Modern**: A responsive, mobile-optimized design with support for shipping address collection.

To change your design, colors, or other styling, visit the [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages) in your Recurly account.

For advanced customization beyond the UI settings, refer to the [Recurly.js documentation](https://docs.recurly.com/js/).

## Site subdomain

Your Hosted Payment Pages live at a custom subdomain: `:your_subdomain.recurly.com`

Changing your subdomain requires your admins to sign in again to apply the changes. To modify your subdomain, contact Recurly Support.

## Accessing your pages

Each subscription plan has a unique Hosted Payment Page. Access it with this URL:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code
```

Replace `:your_subdomain` with your custom subdomain and `:plan_code` with your subscription plan's code.

## Security with reCAPTCHA

Recurly uses reCAPTCHA to protect your pages from bot attacks and fraudulent activity.

### How reCAPTCHA works on your pages

reCAPTCHA activates after three failed transaction attempts from the same IP address within a rolling 24-hour window. When triggered, customers see a "I'm not a robot" checkbox. Most legitimate users pass through immediately. If reCAPTCHA can't confirm their legitimacy, they'll see a distorted text challenge to complete.

The service validates that the user is human before allowing the transaction to proceed. If additional failed attempts occur, the challenge appears again.

## Testing in Sandbox mode

Before going live, test your subscription flow in Sandbox mode using Recurly's test gateway and test credit card numbers. For a complete guide with card numbers and test scenarios, see the [Test Gateway documentation](/docs/test).

## Collecting customer data

### Basic sign-up

By default, your Hosted Payment Pages collect:

* First and last name
* Email address
* Billing address
* Payment method

### Advanced sign-up

Pre-populate fields and customize data collection by adding URL parameters. See [Advanced sign-up examples](#advanced-sign-up-examples) below.

## Confirming sign-ups

After a successful subscription, redirect your customers to a confirmation page. You can pass account and plan codes in the URL to provide clear confirmation details:

```
http://example.com/signup/success?account={{account_code}}&plan={{plan_code}}
```

Recurly automatically replaces `{{account_code}}` and `{{plan_code}}` with the new subscriber's values.

## Google Analytics integration

Track your checkout funnel by connecting Google Analytics to your Hosted Payment Pages.

1. Go to [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages) in Recurly.
2. Enter your Google Analytics tracking code.
3. Recurly automatically tracks visits and checkouts.

## Multi-currency

Hosted Payment Pages automatically detect your customer's location and display the most appropriate currency. Customers can select a different currency before completing checkout.

If you want to specify a currency manually, add a `currency` parameter to your URL:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code?currency=EUR
```

If your preferred currency isn't available, your account's default currency displays instead.

## Language support

Your Hosted Payment Pages support 14 languages, detected automatically from your customer's browser settings:

English, Danish, German, Spanish, French, Hindi, Japanese, Dutch, Portuguese, Russian, Turkish, Simplified Chinese, Swedish, and Polish.

Each language is localized for regional nuances, giving your international customers a native experience.

## Advanced sign-up examples

### Set a default plan quantity

To pre-fill the quantity field for a plan, add a `quantity` parameter:

```
https://:your_subdomain.recurly.com/subscribe/gold?quantity=5
```

### Set default quantities for add-ons or items

Pre-fill quantities for add-ons or items associated with your plan. Use `add_on_code` and `add_on_quantity` parameters, separated by commas:

```
https://:your_subdomain.recurly.com/subscribe/gold?add_on_code=seats,support&add_on_quantity=3,2
```

This example sets "seats" to 3 and "support" to 2 for the gold plan.

### Pass account code and username

When directing users from your application, include their account code and optionally their username:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code/:account_code/:username
```

* **Account code**: A URL-encoded unique identifier for the account (auto-incrementing ID, GUID, email, etc.). Required and must be unique in your Recurly account.
* **Username**: Optional identifier like their online handle or email. Doesn't need to be unique.

If you don't specify an account code, the customer's email address is used instead. If you don't specify a username, it remains blank.

If the account code already exists and has an email on file, that existing email won't be changed.

### Pre-populate name and email

Add `first_name`, `last_name`, and `email` parameters to pre-fill the form:

```
https://example.recurly.com/subscribe/:plan_code?first_name=Verena&last_name=Example&email=verena%40example.com
```

When including account code with name and email, use this format:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code?account_code=:account_code&first_name=Verena&last_name=Example&email=verena%40example.com
```

### Specify payment method order

Control the order payment methods appear on your checkout page using the `payment_methods` parameter:

```
https://example.recurly.com/subscribe/:plan_code?payment_methods[]=ach&payment_methods[]=credit_card
```

The page displays methods in the order you specify first. Any additional payment methods available on your account display in their default order after your specified list.

Available payment methods (in default order): `credit_card`, `ach`, `sepa`, `paypal`, `amazon`.

### Pre-populate a coupon code

Add a coupon code to the URL so it's already entered when customers land on your page:

```
https://example.recurly.com/subscribe/:plan_code?subscription[coupon_code]=10off
```

# Configuration guide

## Step 1: Customize your design

1. Log into your Recurly account.
2. Go to [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages).
3. Choose between Classic or Modern design.
4. Add your company's branding elements (logo, colors).

## Step 2: Set your subdomain

1. Navigate to [Site Settings](https://app.recurly.com/go/configuration/edit).
2. Update your subdomain if needed.
3. Admins will need to sign in again to see the changes take effect.

## Step 3: Generate your payment page URL

For each subscription plan, create the Hosted Payment Page URL:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code
```

Add any advanced parameters as needed (quantity, add-ons, pre-filled fields, etc.).

## Step 4: Secure your pages

reCAPTCHA is enabled by default. Familiarize yourself with how it works so you can answer customer questions.

## Step 5: Test in Sandbox mode

1. Switch to Sandbox mode in your account settings.
2. Use the [Test Gateway](/docs/test) and test credit card numbers to simulate the complete subscription flow.
3. Verify each step works as expected.

## Step 6: Customize data collection

Configure what customer data you want to collect during sign-up (basic contact info, company name, VAT number, shipping address, etc.). For advanced configuration, use URL parameters to pre-fill fields or set defaults.

## Step 7: Set up confirmation

Define a confirmation URL where customers land after successfully signing up. Optionally include plan and account codes for enhanced clarity.

## Step 8: Connect Google Analytics (optional)

1. Go to [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages).
2. Enter your Google Analytics tracking code.
3. Recurly automatically tracks visits and checkout conversions.

## Step 9: Enable required currencies

If your business operates in multiple currencies:

1. Enable the currencies you support in your Recurly account.
2. Recurly automatically selects the best currency for each customer based on location.
3. Customers can manually select a different currency if needed.

## Step 10: Confirm language support

Hosted Payment Pages detect and display in your customer's browser language. Review the 14 supported languages and ensure they're enabled in your account settings.

# FAQs

**Can I use an iframe to embed Hosted Payment Pages?**

No. Hosted Payment Pages don't support iframes because of PCI compliance and security requirements. Instead, direct customers to your Hosted Payment Page URL via a button or link.

**What happens if a customer fails multiple checkout attempts?**

After three failed transaction attempts from the same IP address in a 24-hour window, reCAPTCHA activates. The customer must complete a distorted text challenge to prove they're human before continuing.

**Can I customize which data fields appear on the page?**

Yes. You can collect basic information (name, email, billing address) or add advanced fields like company name, VAT number, and shipping address. Configure this in Hosted Page Settings.

**How does currency selection work?**

Recurly automatically detects the customer's location and displays the most appropriate currency. Customers can choose a different currency before completing checkout. You can also manually specify a currency using the `currency` URL parameter.

**Which languages are supported?**

Hosted Payment Pages support 14 languages: English, Danish, German, Spanish, French, Hindi, Japanese, Dutch, Portuguese, Russian, Turkish, Simplified Chinese, Swedish, and Polish. The page defaults to the customer's browser language.

**Can I pre-populate form fields with customer data?**

Yes. Use URL parameters to pre-fill name, email, account code, coupon codes, plan quantity, and add-on quantities. See [Advanced sign-up examples](#advanced-sign-up-examples) for full details.

**What happens if I change my subdomain?**

Changing your subdomain requires admins to sign in again for changes to take effect. All URLs pointing to your old subdomain will stop working. Plan this change carefully and update any links in your application.
