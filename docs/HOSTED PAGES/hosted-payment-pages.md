---
title: Hosted payment page
excerpt: >-
  Elevate your subscription process with Recurly's Hosted Payment Pages,
  ensuring a smooth, secure, and localized user experience while adhering to PCI
  compliance standards.
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

### Video

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FFEfoB7miNVk%3Ffeature%3Doembed&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DFEfoB7miNVk&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FFEfoB7miNVk%2Fhqdefault.jpg&key=02466f963b9b4bb8845a05b53d3235d7&type=text%2Fhtml&schema=youtube\" width=\"800\" height=\"580\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/embed/FEfoB7miNVk",
  "title": "Hosted Pages Overview",
  "favicon": "https://www.youtube.com/favicon.ico",
  "image": "https://i.ytimg.com/vi/FEfoB7miNVk/hqdefault.jpg",
  "provider": "https://www.youtube.com/",
  "href": "https://www.youtube.com/embed/FEfoB7miNVk",
  "typeOfEmbed": "youtube"
}
[/block]


### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Recurly's Hosted Payment Pages are specially designed platforms where merchants can initiate user subscriptions with minimal hassle. In conjunction with Account Management Pages, these platforms provide an inclusive user experience, all within a PCI-compliant and user-friendly environment.

> 👍 New Recurly Checkout!
> 
> The new Checkout capability is now available to all Recurly customers. With quick setup and deployment, rich customizable features, and flexible payment options, Checkout is the new standard for fast and frictionless consumer checkout, powering subscription purchases for your business. [Learn more.](https://docs.recurly.com/docs/checkout)

# Key benefits

- **Streamlined user experience**: A blend of aesthetics and efficiency, including customizable designs (Classic and Modern) to cater to varying user preferences.
- **Localized interactions**: Support for multiple languages, ensuring your international customers always feel at home.
- **Uncompromised security**: Features such as reCAPTCHA and a thorough testing environment, ensuring malicious threats stay at bay.
- **Flexibility**: Advanced sign-up options that allow pre-population of fields and specific URL parameters for more refined user interactions.
- **Comprehensive integration**: Compatibility with Google Analytics, multi-currency options, and other third-party services ensures a broad-reaching impact.

# Key details

### Look and feel

Personalize your Hosted Payment Pages by integrating your company's branding elements. Choose from the Classic or Modern design, the latter optimized and responsive on mobile screens and equipped with an additional feature to capture Shipping Addresses. To alter designs or customize further, visit the [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages) page. For intricate configurations, refer to [Recurly.js](https://docs.recurly.com/js/).

### Site subdomain

Your custom subdomain (`:your_subdomain.recurly.com`) and requires admins to sign in again to apply the changes. If you wish to change the subdomain, contact the Support team.

### Accessing hosted payment pages

Each subscription plan is associated with a unique Hosted Payment Page, accessible via `:your_subdomain.recurly.com/subscribe/:plan_code`.

### Security

Recurly prioritizes security by employing **reCAPTCHA** on all Hosted Payment Pages. This mechanism kicks in after **3 failed transactions** from a single **IP address** within a **24-hour window**, ensuring bots and malicious attempts are curbed.

### Testing

When in Sandbox mode, utilize Recurly's test gateway alongside specific test credit card numbers to simulate the subscription process. For a detailed guide, consult the [Test Gateway](/docs/test) documentation.

### Signup basics & advanced sign-up

Gather essential details from your customers during the sign-up phase, ranging from basic contact and billing information to additional data like Company Name, VAT Number, coupon codes, or Shipping Address. Advanced sign-up also allows for URL customization to auto-fill certain fields or set default parameters.

### Confirmation

Post a successful sign-up, direct your customers to a custom URL for confirmation. This feature also allows for the inclusion of plan codes and account codes in the URL, enhancing the user's clarity.

### Google analytics

For those keen on tracking funnel conversions, Recurly's integration with Google Analytics will prove invaluable. Set it up from the configuration page, and it will automatically track visits and checkouts on your hosted payment pages.

### Multi-currency

Adaptability is key in today's global market. Recurly's Hosted Payment Pages identify and default to the most appropriate currency based on a user's geographical location, ensuring ease of transaction for international customers. Customers are able to select a different currency before order completion. If the most suitable currency isn't available, your default currency will be used. It is possible to specify a currency by appending a currency parameter.

### Internationalized hosted payment pages

In today's global market, a multilingual approach is essential. Recurly's Hosted Payment Pages come ready with support for fourteen languages, with a display preference based on a user's browser settings.

## ReCAPTCHA

ReCAPTCHA is a free service that safeguards your site against spam, malicious activities, and other forms of bot attacks. By determining whether a user is human or not, it acts as a filter to ensure only legitimate activities pass through.  
The reCAPTCHA service presents users with images of distorted text, typically hard for OCR software to interpret. When users enter the text they see, this input is validated against the expected result, ensuring the user is indeed human.

### **How reCAPTCHA Works on Hosted Payment Pages**

1. **Activation Trigger:** After 3 failed transaction attempts from the same IP address within a 24-hour rolling period, reCAPTCHA is activated.
2. **User Prompt:** The user will see a distorted text image and will be required to input what they interpret from the image.
3. **Validation:** Their input is then validated against the expected result. If it matches, the transaction process continues.
4. **Continuous Protection:** For any subsequent failed transactions, the reCAPTCHA challenge will be presented again, ensuring continuous protection against malicious activity.

## Interacting with reCAPTCHA

Users typically see a checkbox saying "I'm not a robot". By ticking this box, most genuine users are let through. In cases where reCAPTCHA cannot determine the legitimacy of the user, the distorted text challenge is presented for further verification.

# Localization

With Recurly's Hosted Pages, businesses can cater to a diverse global audience. The pages support a plethora of languages, ensuring that subscribers have a native and intuitive experience. The languages offered are:

1. **English** - Catering to a broad audience worldwide.
2. **Danish** - For the businesses operating in Denmark.
3. **German** - Making inroads into the German-speaking markets.
4. **Spanish** - Reaching out to Spain, Latin America, and other Spanish-speaking regions.
5. **French** - For France, Canada, and other French-speaking territories.
6. **Hindi** - Connecting with the vast audience in India.
7. **Japanese** - Addressing the tech-savvy Japanese market.
8. **Dutch** - For businesses in the Netherlands and Flemish-speaking Belgians.
9. **Portuguese** - Targeting both Portugal and Brazil.
10. **Russian** - For companies expanding into the Russian Federation.
11. **Turkish** - Reaching out to the dynamic market in Turkey.
12. **Chinese** - Simplified Chinese for the vast Chinese market.
13. **Swedish** - For the businesses in Sweden.
14. **Polish** - Engaging with the Polish-speaking audience.

Each language rendition is meticulously crafted, ensuring that nuances and specific regional dialects are considered, providing subscribers with a seamless and localized experience based on their browser's language preferences.

# Implementation

Implementing Recurly's Hosted Pages is straightforward. For new sign-ups, businesses can define a Plan's return URL, ensuring customers are redirected back post sign-up. However, for security reasons, it's paramount to understand that Hosted Pages **do not support iframes**. This ensures Recurly maintains its commitment to the highest security standards and PCI compliance. As a result, iframes, though convenient, aren't permissible due to their potential security vulnerabilities when integrating Recurly's secure pages.

With Recurly's Hosted Pages, businesses can ensure a smooth, secure, and localized experience for their subscribers, leading to heightened satisfaction and retention.

# Configuration

- **Log into** your Recurly account.
- **Navigate **to the [Hosted Page Settings](https://app.recurly.com/go/configuration/hosted_pages) to customize the look and feel.
- **Choose **between the Classic or Modern design based on your preference.

2. **Setting up the subdomain**:

- In your Recurly dashboard, **find **the [Site Settings](https://app.recurly.com/go/configuration/edit) page.
  - **Update **the subdomain if required (a re-login will be necessary to view changes).

3. **Access & linking**:
   - For each subscription plan, **generate **its respective Hosted Payment Page link.
   - This link will follow the format: `:your_subdomain.recurly.com/subscribe/:plan_code`.
4. **Security**:
   - By default, reCAPTCHA will be enabled on all pages. **Ensure **you're familiar with its functioning to address any customer queries.
5. **Testing**:
   - **Shift **to Sandbox mode.
   - **Use **the [Test Gateway](/docs/test) for simulating the subscription process, ensuring every step works flawlessly.
6. **Signup customization**:
   - **Collect **necessary data from users during sign-up.

- For advanced sign-up, generate custom URLs to auto-fill certain fields, leveraging the documentation below.

## Advanced sign-up examples

- **Default plan quantity**

If you want to set the default Plan quantity for a subscription, you may append a `quantity` parameter to the URL. For example, use the following URL to set the quantity to 5 for a plan with plan code `gold`:

```
https://:your_subdomain.recurly.com/subscribe/gold?quantity=5
```

- **Default quantity for add-ons and items**

If you want to set the default quantity for an add-on or item associated with the plan, you may append an `add_on_code` and `add_on_quantity` parameter to the URL. For example, use the following URL for the gold plan to set the quantity of "seats" to 3 and "support" to 2.

```
https://:your_subdomain.recurly.com/subscribe/gold?add_on_code=seats,support&add_on_quantity=3,2
```

- **Account code & username**

If you are directing the user from your web application, you should customize the URL to submit the account code and optionally the username. The hosted payment page parameters are:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code/:account_code/:username
```

The account code should be a URL-encoded version of the unique ID you use to identify an account. This might be an auto-incrementing ID, a GUID, their email address, etc. The username optionally identifies the user. The username might be their online handle or email address. Usually the username is the username or email address required for the user to log into your application.

**_Account codes are unique within your Recurly account_; usernames are not.**

If you do not specify an account code, the user's email address will be used as the account code. If you do not specify a username, it will be left blank.

If you do specify an account code for which there is already an existing account and that account has an email address defined, that existing email address will not be changed.

> **Note: **If you include an account code and email, first, or last name, you must pass this value in the following format:

```
https://:your_subdomain.recurly.com/subscribe/:plan_code?account_code=:account_code&first_name=Verena&last_name=Example&email=verena%40example.com
```

- **First name, last name & email**

You may also pre-populate the subscription form by passing `first_name`, `last_name`, and `email` parameters in the URL. Here's an example:

```
https://example.recurly.com/subscribe/:plan_code?first_name=Verena&last_name=Example&email=verena%40example.com
```

- **Payment method ordering**

f you would like to display your payment methods in a specific order, you may do so using the `payment_methods` URL parameter. This parameter is structured as an array. For example:

```
https://example.recurly.com/subscribe/:plan_code?payment_methods[]=ach&payment_methods[]=credit_card
```

Your payment page will display available payment methods in this order first. If there are more payment methods available that aren't specified in this parameter, then the remaining payment methods will proceed in their default order.  
Possible values, in their default order, are `credit_card`, `ach`, `sepa`, `paypal`, and `amazon`.

### Coupon code

- You can pre populate the field by setting it in the URL, e.g. `?subscription[coupon_code]=10off`.

**Confirmation**:

Optionally, Recurly can return the plan code and account code in the URL. If you rely on these parameters, be sure to use the API to verify the new plan code to prevent URL tampering. Here's an example return URL:

```
http://example.com/signup/success?account={{account_code}}&plan={{plan_code}}
```

Both `{{account_code}}` and `{{plan_code}}` will be replaced with the new subscriber's account code and plan code, respectively.

7. **Google analytics integration**:

- Access the [configuration page](https://app.recurly.com/go/configuration/hosted_pages) on Recurly.
- Enter your Google Analytics tracking code in the designated section.

8. **Currency settings**:
   - If your business supports multiple currencies, Recurly will automatically select the most appropriate one based on the user's location.
   - Ensure you've enabled the required currencies in your Recurly account.
9. **Language preferences**:
   - Hosted Payment Pages will default to the language based on user browser settings. Ensure that all necessary languages are supported in your Recurly settings.