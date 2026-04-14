---
title: Site settings
excerpt: >-
  Dive into the Site Settings to configure, customize, and control your Recurly
  platform, ensuring it aligns seamlessly with your business needs.
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

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Limitations

* The Recurly Admin UI supports English natively. Localization and multi-language support are available only for email templates. See [Email Language Support](https://docs.recurly.com/docs/email-template-languages#/) for details.

***

# Definition

Site Settings is the central place in Recurly where you manage your account configuration, company profile, and site customizations. From here, you can fine-tune technical settings, control email communications, and personalize how the platform looks and behaves for your team.

***

# Key benefits

* **Centralized configuration management:** Manage all key site configurations from a single location, making administration straightforward and consistent.
* **Tailored user experience:** Customize the platform's appearance and behavior to match your brand and business requirements.
* **Optimized communication:** Control email settings to ensure customers receive timely, accurate communications from the right sender.

***

# Key details

## Clear test data

The **Clear Test Data** button removes all test data from your Recurly sandbox site — including all test [accounts](https://docs.recurly.com/docs/accounts), their associated [subscriptions](https://docs.recurly.com/docs/subscriptions), and [transactions](https://docs.recurly.com/docs/transactions). This gives you a clean slate for further testing.

<Image align="center" border={true} width="75%" src="https://files.readme.io/20e4e0f9e33ae567afbdb2aba218a16a1496113afbbf24b1ade6acf7b1ec36d5-image.png" className="border" />

This action does **not** affect configuration elements like [subscription plans](https://docs.recurly.com/docs/plans), [coupons](https://docs.recurly.com/docs/coupons), or [email templates](https://docs.recurly.com/docs/email-templates). However, it **will** remove third-party integrations (such as Xero and QuickBooks Online) and any configured webhook endpoints.

> **Warning:** This action is irreversible. Use with caution.

***

## Site details

Site Details is where you manage your company's core information and profile.

### Account information

In **Account Information**, you can update the following fields:

* Site Name
* Recurly Subdomain
* Company DBA Name
* Website URL
* Time Zone

<Image align="center" border={true} width="75%" src="https://files.readme.io/9b17c2c3e398108fe192a2efdee0b27154975883a3ef0321fb1b67bd254a9975-image.png" className="border" />

> **Important:** Changing your subdomain affects webhooks, Checkout, Hosted Payment Pages (HPP), Hosted Account Management (HAM), and API calls. Review and update all integrations after making this change to avoid disruptions.

### Company profile

In **Company Profile**, you can provide additional details about your business, including your industry and estimated annual revenue.

<Image align="center" border={true} width="75%" src="https://files.readme.io/eac1ce76eb47a99d904583ebbda98c9a1dfc14d050907a73508f7d2c7aedca88-image.png" className="border" />

***

## Advanced settings

Advanced Settings is where you configure technical and communication settings for your site, including email preferences, address requirements, IP allowlisting, order number prefixes, and site customizations.

### Email settings

Manage your contact and technical email information from this section. You can:

* Choose whether optional email copies are sent as CC or BCC
* Set the default timezone for dates and timestamps in emails

See the [Email Templates](https://docs.recurly.com/docs/email-templates) documentation for more on managing email copies and templates.

**Billing Contact Email address**

The Billing Contact Email is the default "from" address for all customer communications and the address displayed on Recurly receipts. Keeping this accurate ensures professional, consistent correspondence with your customers. You can override this default for specific accounts on their individual account pages.

If you're on the Recurly Elite plan with multiple business entities configured, you can set a unique billing contact email for [each alternate entity](https://docs.recurly.com/docs/multiple-business-entities#entity-specific-merchant-email-addresses). If you don't set entity-specific addresses, all entities — including the Site Default Entity — will fall back to the address entered here.

<Image align="center" border={true} width="75%" src="https://files.readme.io/ffe009dadb54d4ac3371771be36f61fbf6d113739d0dabb8b29d16087211d357-image.png" className="border" />

#### SendGrid API key

Recurly integrates with SendGrid to give you greater control over email deliverability and analytics. By connecting via SendGrid's SMTP relay, you can ensure your messages reach customers reliably and track performance in detail.

<Image align="center" border={true} width="75%" src="https://files.readme.io/6a13e3d3eb088628fab2063761faa0a13cb29e3574acb05509b054d1960e0dd5-image.png" className="border" />

See the [SendGrid integration documentation](https://docs.recurly.com/docs/sendgrid) to set this up for your site.

#### Debt collection email notifications

The federal Fair Debt Collection Practices Act (FDCPA) restricts when debt collectors can contact customers about money owed — communications between 9 PM and 8 AM are prohibited.

To help merchants stay compliant, Recurly offers the option to send payment-related emails only between 2:00–4:00 PM ET daily. To enable this, check the box next to **"Send payment collection emails between 2:00–4:00 PM ET."**

<Image align="center" width="75%" src="https://files.readme.io/f471ac6b5f46f923964b88a5dfa9ec60a437d7a983e9ef6a45494c24b69dac91-Image_10-3-24_at_3.18_PM.jpeg" />

### Address requirements

Configure the minimum fields required for customer billing addresses. These requirements should align with the Address Validation Service (AVS) rules for your payment gateway.

* Most gateways require Street Address and Postal Code
* PayPal requires a full address
* Beanstream requires a full address and phone number

<Image align="center" border={true} width="75%" src="https://files.readme.io/cda62865c79c165ac21f9ec86449a4cdb1e3931e1e3e8087eed0d89d6469a84c-image.png" className="border" />

> **Recurly recommends collecting postal code at a minimum.**

### Allowlist IP addresses

Use this setting to designate a public IP address or range that bypasses Recurly's fraud checks. This is especially useful when manually processing transactions on behalf of customers.

<Image align="center" border={true} width="75%" src="https://files.readme.io/35a9aadfb9b5295e74584ae21eb4346f347459593374713836cee1375766207d-image.png" className="border" />

IP addresses can be entered in the following formats:

* **Single IP:** `192.168.0.1`
* **IP range:** `192.168.12.0/24` — the range must be narrower than /24

### Order number prefix

If you consolidate multiple billing systems into a single gateway account, an **Order Number Prefix** lets you identify Recurly transactions in your payment gateway's virtual terminal.

> **Note:** This prefix is used on the backend only — it won't appear on invoices. PayPal and Stripe do not support invoice prefixing.

<Image align="center" border={true} width="75%" src="https://files.readme.io/e8a399246d084e824eae630b4f17de007446ee7dbbaba24d37cff02b4c95c7dc-image.png" className="border" />

### Site customizations

Personalize the Recurly sidebar by choosing a sidebar theme that fits your brand. Select from the available style options to create a consistent visual experience for your team.

![](https://files.readme.io/1e05d6c9206082e45c2107b20223a7d0f25b3dcf4aec4f64186b1b65495738d8-image.png)

***

## Additional subdomain

Merchants looking to expand their online presence can add an extra subdomain through Recurly. This dedicated space also allows you to allocate Total Processed Volume (TPV) from another existing subscriber account, offering more flexibility in managing your billing operations.
