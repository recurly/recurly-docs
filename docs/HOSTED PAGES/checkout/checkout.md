---
title: Checkout
excerpt: >-
  Explore Checkout: Streamline your customers' payment experience with
  customizable styles, hostnames, and configurations. Get started easily and
  engage effectively.
deprecated: false
hidden: false
metadata:
  title: Checkout
  description: >-
    Explore Recurly Checkout: Streamline your customers' payment experience with
    customizable styles, hostnames, and configurations. Get started easily and
    engage effectively.
  robots: index
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly subscription plan.

### Prerequisites & limitations

* Recurly's out of the box tax previews are supported on Checkout. Tax previews are not available for Avalara or Vertex.

# Definition

Recurly Checkout offers a seamless consumer checkout experience that adapts to your customers needs. This experience provides additional flexibility in how merchants can manage the customer and developer experience, providing an additional option between a full API/RJS integration, and a standard Hosted Payment page.

# Key benefits

* **Quick setup and deployment**: Activate and deploy swiftly, saving both time and cost, ensuring an efficient and streamlined start.
* **Rich customizable features**: Leverage extensive customizable options to maintain brand consistency and enhance customer engagement.
* **Flexible payment options**: Provide flexible payment solutions that adapt to customer needs, delivering a personalized and dynamic purchasing experience.
* **Highly secure, PCI-compliant**: Uphold the highest security standards with a robust, PCI-compliant system that protects sensitive customer data.

# Key details

## How Checkout works

Recurly's Checkouts are crafted to simplify the buying process for your customers while providing your business with robust, customizable capabilities. These functionalities are designed to efficiently cater to your customers' demands.

### Checkout sessions

Upon accessing your Checkout, customers are presented with a Checkout session that encompasses everything from the visual design to the cart's parameters and contents. This session dynamically adapts based on user actions, such as modifying item counts or choosing a different currency.

You can control these session configurations. For additional information, consult the “Engaging your customers” section.

A Checkout Session's framework is composed of three core components: Checkout Styles, Hostnames, and Configurations.

### Checkout styles

Checkout Styles define your Checkout's visual theme. You have the flexibility to craft various styles that resonate with your brand identity, including incorporating your logo and brand colors.
A standard default style is available for immediate use.

### Checkout hostnames

Hostnames allow your Checkouts to be hosted on your chosen domains, ensuring customers remain within your online ecosystem.

An initial default hostname is ready for use at `<site-subdomain>.recurlycheckout.com.`or you can establish a custom hostname.

### Checkout configurations

Checkout Configurations act as blueprints for determining the structure of your Checkout Session, detailing aspects like the cart's contents and available currencies. Initially, you are equipped with one standard configuration.

### Engaging your customers

* **Direct to Default Hostname**: Guide customers to your site's default Recurly checkout domain (`https://<site-subdomain>.recurlycheckout.com`). This automatically aligns their session with the Checkout Configuration associated with this URL, offering a straightforward path to purchase without requiring additional customization.
* **Use Custom Hostname**: For a more branded experience, direct customers to your custom hostname (`https://<your-checkout-hostname>`). This method initiates a checkout session that matches the Checkout Configuration for your custom domain, enhancing brand consistency and customer trust.
* **Specific Checkout Configuration**: When aiming for a targeted shopping experience, such as for specific promotions or customer segments, use a direct link (`https://<your-checkout-hostname>/c/<checkout-configuration-id>`) that specifies a particular checkout configuration. This approach ensures that the session is precisely tailored to the intended promotion or segment.

### Targeted personalization

#### **Localization**

Checkout determines the customer location and updates the language automatically.

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

#### **Payment method an currency**

Checkout provides the recommended payment method and currency based on the user location.

* **Cards**: credit & debit
* **Direct Debits**: ACH, SEPA, BECS, BACS
* **Wallets**: Apple Pay, Amazon Pay V1 and Amazon Pay V2

**Device responsive**:  Checkout detects the device type and resizes to the optimized layout.

# Landing page configuration

1. To begin, **navigate** to Configuration → Checkout.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/48e3c6088219a15700b9943ea518f755c87844784511d3996c4ff992dd1b0eb7-checkoutHome.png" />

The configuration page offers flexibility with 3 main areas to modify the Checkout configurations. Here you can create different sets of hostnames, modify configurations and styles to create different experiences for customers based on where they are coming from, different promotions, different products or brands.

## Hostname

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/abfd9979ab0f87762e21aa66a811d721ab9899ec019be8d06ba5894e46d4e956-hostname2.png" />

Use the Hostname to specify the locations where your customers will complete their purchases.

### Hostnames come in two forms

#### Recurly-hosted domain

The default hostname which is set up for you out of the box. Your checkout will be available at \<your-subdomain>.recurlycheckout.com.

**Please note:** if your subdomain is changed, the Checkout URLs will still be set to the original subdomain that was configured and will not be updated. To update your Checkout pages, please contact [Support]().

#### Custom Checkout domain(s)

A custom Checkout domain allow you to operate a Checkout on your own domain. Setting up a custom Checkout domain involves some domain configuration on your part, outside of Recurly.

Note: there is no limit to the number of hostnames that can be configured for production sites. Sandbox sites can have up to 5 hostnames.

To create a new hostname, select **Create new Hostname**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/71b0fb5650a90df387b74e8d90eac8a55c5c9d80621520a87121ddb10bb420df-hostname.png" />

**Location details** - URL is where you specify the hostname location (domain and optional subdomain) where your customers will access your Checkouts..In order to use a custom domain:

* You must own the domain.
* You must be able to set the Domain Name System (DNS) settings for the domain.

Prior to saving a custom checkout domain in Recurly, you will need to configure the DNS settings for your domain to set up a CNAME record for the hostname you wish to use for Checkout. How this step is performed will vary based on your DNS provider, which may be your domain registrar or hosting provider. Here are a few links to DNS providers which explain how you can go about setting a CNAME record on your domain: [CloudFlare](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-dns-records/), [Namecheap](https://www.namecheap.com/support/knowledgebase/article.aspx/9646/2237/how-to-create-a-cname-record-for-your-domain/), [GoDaddy](https://www.godaddy.com/help/add-a-subdomain-record-19236).

Depending on which Data Center you use, you will set the CNAME record for your custom domain accordingly:

| Data Center        | CNAME value                      |
| ------------------ | -------------------------------- |
| United States (US) | `checkout.recurlycheckout.com`   |
| Europe (EU)        | `checkout.recurlycheckouteu.com` |

Once you have input the correct information in the hostname field and exited the hostname field, Recurly will automatically validate the hostname. If we detect a valid CNAME entry, you will see a message indicating that your hostname is ready for Checkout. If it is not correct, you will receive an error message. You will still be able to save a hostname that does not pass this validation.

Recurly will provision an SSL certificate for your custom domain. The provisioning process usually takes 30 minutes or less, but may take several hours in some cases.

* You will receive an email when certificate provisioning is complete.
* While your SSL certificate is pending, the hostname will display a yellow status dot label. Once provisioned, the status dot will turn green.

**Configuration - access:** set to enabled by default, and can be set to disabled if you wish to discontinue access to that specific hostname.

**Configuration - default checkout configuration:** initially, this will be set to the default checkout configuration, but can be configured to include any checkout configuration.

## Configurations

Configuration is where you set up the products to sell and configure additional Checkout capabilities.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/215cf0c29ad49d10876d11887c91cf67cd28f64d4ac169b2ece4f1c90d7f790c-aboutThisConfig.png" />

**About this configuration**

* The starter configuration is enabled by default, You can add additional configurations for any mix of subscriptions and add-ons you wish.
* The name and description are for internal use only and will help you identify the products the configuration is targeting.

Note: there is no limit to the number of configurations that can be created.

### Appearance and Behaviors

For the selected configuration, you are able to choose the style you wish to apply to this configuration To modify styles, see Styles section below.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e6debf576d86113b5772285cf3a0d74eea19d41ab137150f509ea4f974c4070e-appearanceBehaviors.png" />

* **Cancellation URL** - If a cancellation URL is set, a back button will be added to your Checkout which will redirect users to this URL.
* **Finish URL** - If a Finish URL is set, a link will be added to the bottom of the order confirmation page allowing your customers to proceed to this URL.
* **Confirmation URL** - When a user has completed their purchase, we will redirect them to this URL. If this is left blank, a confirmation page will be displayed.Upon purchase, the user will be taken to this URL.  Without a URL, the customer will receive the standard confirmation page upon purchase.
* **Accept coupons** - Enabling this will add an optional field in the Order Summary of your checkout where a user can enter a gift card code or promo code.  Any specific coupon used for checkout will need to be set up in Recurly’s coupon configurations.
* **Accept shipping address** - Enabling this will add required form fields for the user's shipping address.
* **Treat multiple subscriptions as choices** - If your checkout configuration has more than one subscription, you may want to enable this setting so that a user can choose which subscription they would like to purchase.
* **Display subscription details and require acceptance of recurring charges before entering billing information** - This setting will generate and display greater details about the recurring charges in the checkout.  The user must click "Agree & Continue" before they can enter their information and complete the purchase.
* The additional fields **Company name**, **Phone number**, and **VAT number / Tax identifier** will display as optional fields if enabled.

### Agreements

These additional URL fields give you the flexibility to offer your subscribers the resources they may need to self-serve their subscription.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/76381dd290b6315e5bb35de3519a754a4ddcfef6ae8a47bd03428068bca7813b-agreements.png" />

If you choose to use your own account management site, you will need to provide the URL.  Otherwise, you can use Recurly's Hosted Account Management page where an unique URL is generated for each account automatically.

* **Account Management URL** - If account management URL is set, a link will be provided in checkout confirmation emails that allow your customers to view and manage their account.
* **Support URL** - If a support URL is set, the Checkout page displays a link to a page where customers can contact support.
* **Privacy Policy URL** - If a support URL is set, the Checkout page displays a link to a page where customers can contact support.
* **Terms of Service URL** - If a Terms of Service URL is set, a link to it will be provided at the bottom of a Checkout, and your users must accept the Terms of Service in order to complete a purchase.

## Cart

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d0f83848bb668fead95b017fa08cd867a818b144aed5b25a38e7fc813d74f677-cart.png" />

### Currencies

Choose the currencies that you want to make available in this particular checkout.  Note that only your site's enabled currencies will be available to choose from.

* Only plans that match the selected currencies will be available to choose from when selecting a plan from the _Add Subscription_ dropdown.
* By default, your default site currency is added. Or, if all currencies are removed, it will default to the default site currency.
* Create a configuration with only one currency to lock that currency as what is displayed to the user. This prevents users from searching for the best price across currencies.

### Products

The products your customer can purchase using this Checkout Configuration.

* Specify the plan(s), as a subscription, you would like to apply to the configuration.
* Adding multiple subscriptions to the cart configuration allows you to bundle multiple subscriptions together in the same purchase.  Or if the **Treat multiple subscriptions as choices** option is on, the user will be able to choose one subscription.
* Specify the quantity of the plan that a customer can purchase, and optionally enable the customer to edit the quantity they wish to purchase.
* Any plans with add-ons can have the add-ons configured to be able to be sold along with the subscription sign up, and define if they are able to be added, specify the quantity, or allow the customer to edit the quantity.
  * Add-ons may be plan based or item based.
* Specify the one-time purchases you would like to add to the checkout configuration.  Additionally, one-time purchases can be sold as a standalone product without a subscription.
  * One-time purchases must be in the item catalog.

## Styles

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f8ab4b4661c1f7e545519641681867e827b7b2095c763d9f6406cb21d4bbdfe8-style.png" />

Customize the appearance of your checkout pages to match your brand identity. To begin, click edit on the starter style or click new style to create your own.

* **Brand color**: Select different color formats (Hex, RGB, or HSL), or by using the browsers default color picker. This will update the styling of interactive elements (including links and buttons) on the checkout experience.
* Add a **Logo**, which will display in the header. Logo file size cannot exceed 256 KB. The logo will be autoscaled based on the viewport size of the device.
* Add **Icon**, which will display as the browser favicon.
* **Styles** can be added to a configuration (one style per configuration).
* **Enable** as many styles as needed to match each configuration.

# Checkout pages - view checkout (preview)

Checkout Pages configuration allows you to mix and match different host names and configurations on the fly.

<Image align="center" className="border" border={true} width="30% " src="https://files.readme.io/20ed25317da24f07409a5f7bc92887726bf511d3c5f59ce39671ae2cdf3a816b-checkoutPreview.png" />

**Select** a host name and a configuration, then click **View Checkout** to view your checkout page in real time.

# Analytics

Checkout includes a robust analytics dashboard where you can dive deep into Recurly Checkout data to analyze performance at driving cart conversion to acquire subscribers and sell products. [Learn more](https://docs.recurly.com/docs/checkout-dashboard) abut the Checkout analytics dashboard.

# Checkout capabilities compared to Hosted Payment Page

This chart outlines the new capabilities that Checkout offers, that were not available on HPP.

<Image align="center" className="border" border={true} src="https://files.readme.io/46165ffb350940c995d866e523e27fd69a6c239c3b1774cd658ca9b97040e0f8-Screenshot_2024-10-30_at_8.24.29_PM.png" />

# FAQs

### Enablement and access

**Q: How can I access this feature?**
**A:**All sites created after May of 2024 will have Checkout automatically. Please contact support to enable it on your site if not already enabled. If you have Checkout, this feature is under Configuration→Checkout in the Recurly App navigation.

### Requirements for use

**Q: What are the minimum requirements for using this feature?**
**A:** At least one plan must be set up, with required or optional add-ons, a default currency, and coupons configured if you plan to accept coupons.

### Minimum checkout configuration

**Q: What is the minimum Checkout configuration needed?**
**A**:

* At least one Hostname - can use the default.
* One Configuration.
* One Style - can use the default Starter Style.

### Testing

**Q: How do I test checkout using payment methods?**
**A:** Refer to the Recurly test gateway [documentation](https://docs.recurly.com/docs/test) for testing your checkout experience in Sandbox. Use gateway test cards for Dev Mode or Production.

<br />
