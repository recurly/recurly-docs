---
title: Implementing Recurly
excerpt: >-
  Recurly offers a suite of versatile integration methods tailored for every
  need, whether you're looking to dive deep with direct API access, enhance your
  website's functionality with Recurly.js, or seamlessly incorporate Recurly
  into your mobile applications. This section provides an overview of each
  integration method, ensuring you choose the right fit for your platform.
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

Recurly is a sophisticated subscription management platform equipped with diverse features and tools, designed to handle subscription billing efficiently. Implementing Recurly involves setting up the necessary technical integrations to accommodate your company’s billing requirements and ensure a seamless payment processing experience for your customers.

# Checkout vs Recurly.js (API-oriented)

When it comes to managing online payments, Recurly provides two robust solutions: [Checkout](https://docs.recurly.com/docs/checkout) and [Recurly.js](https://docs.recurly.com/recurlyjs). Each offers unique features tailored to different needs, ensuring a seamless payment experience. Checkout offers great flexibility and an frictionless customer experience whereas Recurly.js offers more customization and is perfect for those who have a basic understanding of web technologies. The table below provides a straightforward comparison, highlighting key aspects to consider when choosing the solution that best aligns with your requirements.

| Aspect to consider        | Checkout                                                                                                                   | Recurly.js                                                                                                                     |
| :------------------------ | :------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------- |
| **Development Timeframe** | Launches within minutes.                                                                                                   | Setup could range from 1-2 days, depending on web development readiness.                                                       |
| **Location**              | Hosted on your personalized subdomain: your-subdomain.recurly.com or configured to your custom domain.                     | Directly integrated into your website.                                                                                         |
| **Technical Skill**       | Little to no coding knowledge needed.                                                                                      | Requires a basic understanding of APIs and HMAC digital signatures.                                                            |
| **Look and Feel**         | Responsive page design, customizable branding, product selection.                                                          | Offers a fully customizable, pre-built form.                                                                                   |
| **Billing Flexibility**   | Localization of currencies and wide variety of payment methods offered to customers across the globe.                      | Accommodates both regular subscription signups, multiple plans and one-time payments.                                          |
| **Customer Management**   | Seamless purchase experience to select the product(s) in cart, between single plan, multiple plans, or one time purchases. | Recurly.js offers a form to update billing information. Any other account actions would need to be handled via another method. |
| **PCI Compliance**        | All card information is handled directly inside Recurly, making your business eligible for reduced PCI scope.              | All card information is handled directly inside Recurly, making your business eligible for reduced PCI scope.                  |

In addition to these great choices, we also have our [Hosted Payment Pages](https://docs.recurly.com/hosted-payment-pages) (Legacy) but with the power of our new Checkout hosted pages, we highly recommend you explore [Checkout](https://docs.recurly.com/docs/checkout). 

# Dedicated pages

Please, visit our dedicated pages if you would like to know more about our integration methods.

- **REST API Keys**: Direct communication with Recurly's systems using our [RESTful API keys](https://docs.recurly.com/docs/api-keys). Designed for developers seeking precision and control.
- **Recurly.js**: Elevate your website's payment capabilities with [Recurly.js](https://docs.recurly.com/docs/recurlyjs). A streamlined solution offering robust integration with simplicity.
- **Webhooks (JSON & XML)**: Receive real-time notifications about events in your Recurly account. With both [JSON and XML](https://docs.recurly.com/docs/webhooks) support, our webhooks ensure maximum compatibility and adaptability.
- **Native Mobile SDKs**: Integrate Recurly smoothly into your mobile apps using our [native SDKs](https://docs.recurly.com/docs/native-mobile-sdks). Created for iOS and Android platforms to facilitate payments on the move.