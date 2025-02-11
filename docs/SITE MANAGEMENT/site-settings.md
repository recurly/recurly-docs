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
# Definition

The Site Settings section in Recurly provides a centralized location for users to manage and modify various configurations related to their account, company profile, and site customizations. It offers tools to fine-tune technical settings, manage email communications, and personalize the platform's appearance.

# Key benefits

- **Centralized configuration management:** Exercise centralized control over various site configurations, streamlining the administration process.
- **Tailored user experience:** Leverage enhanced customization options to create a user-centric experience that meets individual preferences and business requirements.
- **Optimized communication:** Efficiently manage email settings to improve communication, ensuring timely and accurate information exchange.

# Key details

## Clear test data

To remove all test data from your Recurly sandbox site, simply utilize the **Clear Test Data** button. This action will delete all test **<a href="https://docs.recurly.com/docs/accounts" target="_blank">accounts</a>**, along with their associated **<a href="https://docs.recurly.com/docs/subscriptions" target="_blank">subscriptions</a>** and **<a href="https://docs.recurly.com/docs/transactions" target="_blank">transactions</a>**, ensuring a clean slate for further testing and experimentation.

![](https://files.readme.io/82abc75-Screenshot_1.png)

**It's important to note** that this action will not affect any configuration elements like **<a href="https://docs.recurly.com/docs/plans" target="_blank">subscription plans</a>**, **<a href="https://docs.recurly.com/docs/coupons" target="_blank">coupons</a>**, or **<a href="https://docs.recurly.com/docs/email-templates" target="_blank">Email Templates</a>**. However, it will remove third-party integrations such as Xero and QuickBooks Online, as well as any configured webhook endpoints. It's crucial to exercise caution when using this irreversible action.

## Site details

The Side Details section serves as a hub for your company's main information and profile. It puts you in control, allowing you to effortlessly modify and manage these details.

### Account information

In the **Account Information** section, take full control of your account by customizing essential details. Update the Site Name, Recurly Subdomain, Company DBA Name, Website URL, and Time Zone to ensure accurate representation and seamless integration with your business.

**Important:** If you decide to change your subdomain in Recurly, it's important to note that it will impact various integrations and configurations. This includes webhooks, Checkout, Hosted Payment Pages (HPP), Hosted Account Management (HAM), and API calls. Remember to update these settings accordingly to ensure everything continues to work smoothly. Take the time to review your integrations and make the necessary adjustments to avoid any interruptions in your subscription management processes.

![](https://files.readme.io/2b24c48-image.png)

### Company profile

In the **Company Profile** section, enhance your site profile by providing additional details about your company. Specify the industry in which your business operates and indicate the estimated annual revenue to further customize your site's profile.

![](https://files.readme.io/c5242a2-image.png)

## Advanced settings

Fine-tune the technical configurations of your site to meet your specific requirements. Customize your email settings to ensure effective communication with your customers. Define address requirements to ensure accurate and complete customer information. Manage IP allowlist addresses to control access to your site. Utilize invoice prefixing to add unique identifiers to your invoices.

Additionally, leverage the Site Customization subsection to easily personalize the colors of your site. Choose colors that align with your brand identity and create a cohesive visual experience for your customers.

### Email settings

Customize your email settings by managing your contact and technical email information. Choose whether optional email copies are sent as CC or BCC. Set the default timezone for dates and timestamps in your emails. Refer to the **<a href="https://docs.recurly.com/docs/email-templates" target="_blank">Email Templates</a>** documentation for more information on managing email copies and templates. 

Maintaining an accurate Billing Contact Email Address is crucial as this is the default address for all Recurly receipts and acts as the 'from' address for all customer communications. By correctly specifying this email, you ensure seamless, prompt, and professional correspondence with your customers, further enhancing their trust and experience with your business. Always remember to override these default settings for specific accounts on their respective pages to uphold personalized communication based on your unique needs and preferences.

If you are on the Recurly Elite plan and have multiple business entities configured, you can set a unique billing contact email address for [each alternate entity](https://docs.recurly.com/docs/multiple-business-entities#entity-specific-merchant-email-addresses) if you wish to based on your organization’s needs. This will ensure that when multiple business entities are configured on your Recurly site, your customer will always see the correct merchant business email address on communications they receive. If you do not set unique email addresses on any of your alternate entities, the billing contact email address used will fall back to the one entered on the Site Settings page. Your Site Default Entity will always use the email address configured on the Site Settings page as well.

![](https://files.readme.io/ac2b217-image.png)

#### SendGrid API Key

Recurly's integration with SendGrid empowers you with complete command over your customer emails. By leveraging SendGrid's powerful SMTP server relays, you unlock unparalleled email deliverability and extensive analytics, guaranteeing that your messages reach their intended recipients accurately and efficiently.

![](https://files.readme.io/2299ba1-image.png)

Please refer to our documentation on **<a href="https://docs.recurly.com/docs/sendgrid" target="_blank">SendGrid</a>** to implement this for your site.

#### Debt Collection Email notifications

The federal Fair Debt Collection Practices Act (FDCPA) provides key protections to consumers. These include rules for how debt collectors can communicate with debtors and third parties.  
To support FDCPA, merchants will have the opportunity to choose whether or not they wish to opt into sending their emails that are payment-related between the hours of 2-4 PM ET daily to adhere to the federal law about not communicating with customers about money owed to their business between the hours of 9 pm and 8 am.

To choose to opt into sending payment-related emails between the hours of 2-4 PM ET daily, check the box next to "Send payment collection emails between 2:00-4:00 PM ET."

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f471ac6b5f46f923964b88a5dfa9ec60a437d7a983e9ef6a45494c24b69dac91-Image_10-3-24_at_3.18_PM.jpeg",
        null,
        "screenshot site setting debt collection email]"
      ],
      "align": "center"
    }
  ]
}
[/block]


### Address requirements

Configure the minimum fields required for the billing address of your customers. Ensure that these address requirements align with the Address Validation Service requirements of your chosen gateway. Most gateways typically require the Street Address and Postal Code, while specific gateways like PayPal may require a full address, and others like Beanstream may ask for a full address and phone number. Verify and adjust the address requirements accordingly to ensure compatibility with your gateway's validation service.

![](https://files.readme.io/a41c57b-image.png)

**_Recurly recommends collecting postal code at a minimum._**

### Allowlist IP addresses

This feature enables you to designate a public IP address or range that will bypass Recurly's fraud checks. It is particularly beneficial when you manually process transactions on behalf of your customers.

![](https://files.readme.io/674a1a7-image.png)

**IP addresses can be entered in the following formats:**

**Single IP**: 192.168.0.1  
**IP Range**: 192.168.12.0/24 (**_The range must be narrower than /24_**).

By specifying the desired IP addresses or range, ensure that transactions originating from those sources are exempted from Recurly's fraud checks.

### Invoice prefixing

If you have multiple billing systems consolidating into a single gateway account, you can define an **Order Number Prefix **within Recurly. This allows you to easily identify Recurly transactions in your payment gateway's virtual terminal. It's important to note that this prefix is only used on the backend and will not be displayed on the invoice.

Please be aware that **PayPal Payment Gateways do not support invoice prefixing**.

![](https://files.readme.io/7dd13ea-image.png)

### Site customizations

Add your personal touch to the Recurly Sidebar by customizing its look. With the "sidebar theme" option, you can choose a style that perfectly matches your company's unique personality and vibe. Explore the different options available and select the one that resonates with your brand.

![](https://files.readme.io/2e186a0-image.png)

## Additional subdomain

Merchants seeking to expand their online presence can invest in an extra subdomain through our platform. This feature not only provides them with a dedicated space but also allows them to seamlessly allocate the Total Processed Volume (TPV) from another existing subscriber account. This integration ensures streamlined operations and offers more flexibility in managing their online assets