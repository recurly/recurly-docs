---
title: PayPal
excerpt: >-
  Enhance your Recurly checkout experience with PayPal, offering seamless
  transactions through familiar PayPal services including Express Checkout and
  One Touch™. Discover the prerequisites, limitations, and best case use
  scenarios for this integration below.
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

### Prerequisites & supported gateways

To integrate PayPal with your Recurly account, you'll need to be approved for PayPal's "Reference Transactions" feature through either PayPal Business, PayPal Complete, or Braintree gateways.

### Limitations

Using PayPal as a payment method in Recurly comes with a set of restrictions that are essential to know to ensure a smooth operational flow. Below are those limitations:

#### Availability

* **Recurly Checkout, Hosted Payment Pages, or Recurly.js:** PayPal payments can only be facilitated through these mediums. The Recurly API does not support PayPal checkouts. PayPal Complete is only available in Recurly.js.
* **Facebook's In-App Browser:** The PayPal checkout process is currently not compatible with Facebook's in-app browser due to its lack of support for tabbed browsing, hindering the correct display of the PayPal checkout flow.
* **PayPal Business Account:** The PayPal Business Account is a legacy platform, and Recurly no longer suppports new configurations for this gateway. If the gateway tile is not available on your production site, this indicates the mechanism has been disabled. For further instructions, please reach out to [support@recurly.com](mailto:support@recurly.com).

#### Transaction Details

* **Checkout & Hosted Payment Page Parameters:** If a customer cancels the payment process midway and initiates a new signup, details such as the account code entered during the initial attempt will not be retained.
* **Address Information:** Recurly doesn't automatically obtain address information from PayPal. If you're not utilizing the "Collect PayPal Shipping Address" feature, ensure to gather this information outside of the PayPal checkout form for tax calculations. Note that PayPal uses the billing address stored in their system for payment processing, while Recurly uses the internally stored address for tax computations.

#### Approvals and Compliance

* **Approval for Reference Transactions:** Generally reserved for merchants who have an established operational history with PayPal.
* **VAT Collection:** For guidance on complying with VAT regulations when processing PayPal payments, kindly refer to our [VAT documentation](https://docs.recurly.com/docs/vat-number-validation).

Recurly supports merchants who want to let customers pay using their PayPal account. To use Recurly to process PayPal payments, you can use either PayPal Business or Braintree as the gateway. Recurly helps you get the most from your PayPal customers by supporting the latest Express Checkout and OneTouch experiences.

### Use cases

* Offering familiar and secure PayPal payment options to increase customer trust and satisfaction.
* Leveraging Express Checkout and One Touch™ for a faster and smoother payment experience.
* Allowing customers to manage billing agreements directly through PayPal, or by using Recurly to terminate subscriptions.

# Checkout flows

## PayPal Complete

Recurly supports PayPal’s latest and greatest PayPal offering which is supported for all customers using the latest version of Recurly.js. This new offering allows small businesses access to new features to help them drive payment acceptance and enhance how they run their business. PayPal's complete payments solution now allows consumers to securely save their payment information on a business's ecommerce website for future purchases. This can reduce friction and drive conversion.

## PayPal Express Checkout and One Touch™

Recurly supports the Express Checkout flow and One Touch™ flow for all customers using the latest version of Recurly.js. With Express Checkout and One Touch™, your customers have a more seamless checkout experience. [Learn more about Express Checkout and One Touch](https://www.paypal.com/us/webapps/mpp/one-touch-for-business?utm_source=hs_email\&utm_medium=email\&utm_content=2&_hsenc=p2ANqtz-8nejbQrZ8vp-2ygd1nlveotz94L9LdeP8DCA-acUaIxO6dmjgrJbnPYOkfEFQlnhyYK3GvO60ekMDKFZBkczSnoApWeA&_hsmi=2). 

### The PayPal Express Checkout experience

On desktop browsers, the PayPal checkout is completed in a modal that appears on top of your checkout page (see screen shot at the top of this page).  On tablets and smartphones, buyers access the PayPal payment screens in full-page mode:

![](https://files.readme.io/1de4d4b-uk-ec-step3.png "uk-ec-step3.png")

### The One Touch™ experience

With Express Checkout and One Touch™, customers log into PayPal once, and then can check out without re-entering their password or payment details for up to 6 months.

## Collect PayPal shipping and billing addresses

PayPal users can enter their shipping and billing addresses into their PayPal profile, and Recurly can obtain that information from PayPal. If we collect that address information, then you don't have to separately ask your customers to provide that information during the checkout flow. This allows you to simplify the checkout flow for PayPal users, resulting in higher conversion and more revenue. PayPal calls this feature the "Express Checkout Shortcut" ... read on to learn more.

### PayPal Express checkout shortcut

With the Express Checkout Shortcut, buyers skip the pages on your website that gather shipping and payment details. Instead, the buyer is redirected to PayPal from the shopping cart page. There is no need to collect the buyer's shipping information; Recurly captures the buyer's shipping (and billing, if configured to do so) address, so there is no need to ask the buyer to provide it.

#### The normal PayPal checkout flow

![](https://files.readme.io/cf2e7de-ec-page-flow.png "ec-page-flow.png")

#### The PayPal Express Checkout Shortcut flow

![](https://files.readme.io/f79a756-ec-page-shortcut-flow.png "ec-page-shortcut-flow.png")

Learn more about the [PayPal Express Checkout Shortcut](https://developer.paypal.com/webapps/developer/docs/classic/express-checkout/ec-shortcut/) and the [PayPal UI Requirements](https://developer.paypal.com/docs/classic/express-checkout/integration-guide/ECUIRequirements/).

# FAQs

#### How does One Touch™ work?

One Touch™ allows customers to stay logged into PayPal, facilitating faster purchases in subsequent visits. It stores the necessary information securely, making the checkout process faster and more efficient.

#### Can I choose not to collect shipping addresses?

Yes, in the PayPal Express Checkout Shortcut settings in Recurly, you can choose whether or not to collect shipping addresses from your customers.

#### Are there any security concerns with using PayPal?

PayPal ensures a high level of security, protecting sensitive information through advanced encryption technologies. Moreover, Recurly complies with the stringent industry standards for security, assuring a secure checkout process.

#### Can customers pay with PayPal without a PayPal account?

Yes, customers can use the guest checkout option available in PayPal Express Checkout to pay with their credit or debit cards without creating a PayPal account.

### Troubleshooting tips

#### What to do if the PayPal option is not showing during checkout?

Ensure that you have correctly configured PayPal as a payment option in your Recurly settings. If the problem persists, refer to the Recurly documentation or contact Recurly support for assistance.

#### One Touch™ is not working as expected, what should I do?

Check to ensure that One Touch™ is enabled in your PayPal settings and correctly configured in Recurly. If necessary, consult the PayPal One Touch™ documentation for further guidance.
