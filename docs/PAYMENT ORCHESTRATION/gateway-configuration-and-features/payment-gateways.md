---
title: Gateways & payment methods configuration
excerpt: >-
  Payment gateways are responsible for processing transactions and distributing
  funds into your merchant bank account.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Gateway configuration

If you don't yet have a gateway, please start [here][4] to explore gateway options that Recurly supports. When choosing a gateway, some factors to consider include: region your company is based, region(s) where your customers are based, your customers' payment preferences. If you already have a gateway, follow these steps:

1. From [your gateway configuration page][1], click **Add Gateway**.

2. Select your payment gateway (not seeing the right gateways for your location? Check your company country settings in [your Business Entity][2]).

3. Enter your gateway credentials. These are typically not the credentials you use to access your virtual terminal, but a set of API credentials. Please see our [gateway-specific documentation][3] for more information.

4. Set your accepted card types. Note, you'll also need to ensure that the card types are supported and enabled on your gateway account.

5. Configure your Zero Dollar Authorization (ZDA) settings. Please test updating billing information with every card type you accept after enabling Zero Dollar Authorizations. Please note, not all gateways require or have this setting, and Zero Dollar Authorization support is implied, not requiring configuration.

6. If your payment gateway requires Recurly's IPs to be on an allowlist, see our [IP Allowlist documentation][5] for the full list of IPs to supply to your gateway.

7. If your payment gateway requires webhooks to be set up, see your individual gateway configuration instructions to ensure your transactions are updated appropriately.

[1]: https://app.recurly.com/go/configuration/payment_gateways

[2]: https://app.recurly.com/go/configuration/edit

[3]: https://docs.recurly.com/docs/additional

[4]: https://recurly.com/gateways

[5]: https://docs.recurly.com/docs/ip-allowlist

## Test Configuration

Once a gateway is configured on your Recurly site, the test configuration option can be used for a basic verification check. When your site is in production mode, Recurly recommends running a test transaction (and then voiding the charge) to fully validate your gateway setup before you go live.

## Enabling/Disabling Gateway

A payment gateway can be enabled or disabled at any time to allow transactions to flow to another gateway. Simply enter the gateway edit page and toggle the Gateway Status between Enabled or Disabled. By default, a gateway will be set as Enabled when first added to Recurly.

![](https://files.readme.io/cfee537-Screen_Shot_2019-06-19_at_3.36.49_PM.png "Screen Shot 2019-06-19 at 3.36.49 PM.png")

[6]: https://docs.recurly.com/docs/custom-gateway-routing-configuration

## Payment Routing

For accounts with multiple gateways configured, Recurly will route transactions based on accepted card type and currency. Beyond that, Recurly will send the transaction to the gateway first added to the account. You are able to specify which gateway will be used per transaction by utilizing Recurly's [Custom Gateway Routing][6] functionality.

## Switching Gateways

Because Recurly stores your customers' credit card data, you can easily switch payment gateways at any time. Simply disable/delete the old payment gateway and enable the new one---Recurly will automatically funnel transactions to the new payment gateway as long as it supports the same card types and currencies as your previous gateway account.

Keep in mind, not all payment data can easily migrate to another gateway, especially if the payment instrument is tokenized. Please reach out to Support for your specific use case if you plan on switching gateways.

**Note: Refunds will always process through the gateway account that processed the original charge. Because of this, we recommend keeping your old gateway account active and added to Recurly, but disabled for new transactions, until you no longer need to process refunds for transactions processed through your old gateway or the maximum refund window for your transactions has elapsed.**

## Gateway Downtime

If for any reason your payment gateway is not reachable, Recurly will automatically retry your recurring transactions every 2--4 hours until either the gateway is reached or a maximum of 20 payment failures occurs.

## Zero Dollar Authorizations (ZDA)

Use Zero Dollar Authorizations (ZDA) to verify a customer's payment method without placing a temporary $1.00 hold on their card. This provides a seamless update experience and reduces customer support inquiries.

**Prerequisite:** ZDA must be enabled on your payment gateway account. Please contact your gateway provider to confirm support and activate the feature.

1. In Recurly, navigate to **Configuration → Payment Gateways**.
2. Locate the gateway you want to configure and select **Options → Edit Gateway**.
3. Find the section labeled **“Zero Dollar Authorizations (Advanced)”**.
4. Check the box for each card brand you wish to enable ZDA for.
5. Click **Save Changes**.

<Callout icon="📘" theme="info">
  **Important**

  To verify a card is valid, gateways like Stripe send an authorization request to the issuing bank. By enabling ZDA, you are instructing the gateway to make this request for $0 instead of a higher amount.
</Callout>

## Validations

Recurly works to save you money by passing some basic validations before passing the transaction to your payment gateway. This includes:

1. Validating that the credit card number is a valid number (ie; passes Luhn check)
2. Validating that the CVV format matches the card type selected
3. Validating a future expiration date format
4. Validating the zip code format (when country code is supplied, for limited countries)
5. Validating the entry of address information based on site-level address requirements.

## Fraud Velocity Checks

All transactions are passed through a simple fraud velocity filter before being passed on to your payment gateway. Please see the [transactions documentation](/docs/transactions#section-fraud-velocity-checks) for details on our fraud check system and how you can take full advantage of it.
