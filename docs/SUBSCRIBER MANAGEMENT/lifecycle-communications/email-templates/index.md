---
title: Email templates
excerpt: >-
  Learn how to configure, customize, and manage email templates in Recurly to
  keep subscribers informed at every stage of their subscription lifecycle.
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

### Prerequisites

* A valid billing contact email address must be configured on your Recurly site for fallback notifications
* Sender Authentication is strongly recommended before going live with custom from addresses

### Limitations

* Email notifications are only sent to valid email addresses; addresses ending in `@test.com` or `@example.com` are treated as invalid
* The Trial Ending email can only be enabled for plans with a trial length greater than three days
* The Gift Card Balance Low reminder is fixed at seven days before renewal and is not configurable
* The Sender Authentication feature is only available to sites that do not have their own paid SendGrid account

# Definition

Email templates in Recurly are predefined layouts and formats that businesses use to send automated or scheduled emails to their subscribers. These templates maintain brand consistency, streamline communication, and ensure the right information reaches customers at every stage of the subscription lifecycle.

> **Important:** To stay compliant with regulations and standards such as PCI-DSS and HIPAA, avoid including sensitive information — such as protected health information or credit card numbers — in your email templates.

# Key benefits

* **Consistent branding:** Every email your subscribers receive reflects your brand's identity and voice, without requiring manual effort on each send.
* **Increased efficiency:** Automating repetitive communications frees your team to focus on higher-value work.
* **Personalized communication:** Dynamic parameters let you tailor each email to the individual recipient, making messages feel relevant rather than generic.
* **Fewer errors:** Predefined formats reduce the risk of mistakes that come with manually drafted communications.
* **Stronger engagement:** Well-structured, on-brand emails give subscribers the information they need and build trust over time.

# Key details

## Email notification templates

Recurly offers a comprehensive set of email notification templates covering account actions, billing events, subscription changes, gift cards, and dunning scenarios. All templates are in English by default unless you modify them.

When no valid email address is associated with an account, notifications are sent to the site's billing contact instead.

<Image align="center" border={true} width="75%" src="https://files.readme.io/51b738ac9318251a7b96502b8da589d573ed105e5c0f96fd48eee958684aa412-Screenshot_2025-10-01_at_8.58.03_AM.png" className="border" />

### Debt collection email notifications

To support compliance with the federal Fair Debt Collection Practices Act (FDCPA), Recurly gives merchants the option to send all payment-related emails between 2:00 – 4:00 PM ET daily. Emails that would otherwise send outside that window are held and delivered the following day during the same timeframe.

This setting is available on the [Site Settings page](https://docs.recurly.com/docs/site-settings#email-settings). When enabled, it applies to the following templates:

* New Invoice
* New Subscription
* Trial Ending
* Bill Date Reminder
* Term Renewal Reminder
* Mastercard Reminder
* SEPA Renewal Reminder
* BACS Renewal Reminder
* Credit Card Expired
* Ramp Price Change
* Gift Card Balance Low
* Payment Declined
* Payment Declined Due to 3D Secure 2
* Invoice Past Due
* Expired for Non-Payment

### Header and footer templates

* **Email header:** An optional section that can be added to the beginning of all email templates
* **Email footer:** An optional section that can be added to the end of all email templates

### Account templates

* **Activate account:** Sent when a customer creates an account using their subscription email address on your account management portal
* **Password reset:** Sent automatically when someone requests a password reset
* **Password has been reset:** Notifies customers that their password was changed, helping maintain account security

### Invoice templates

* **New invoice:** For manual payment collections — sent when a manual invoice is generated or a new subscription with manual collection is initiated
* **New credit invoice:** Sent when a credit invoice is generated and posted manually
* **Payment confirmation:** Confirms a successful payment transaction, excluding $0 invoices and new subscriptions. Can be configured to send to all customers or only Mastercard users; be sure to include any required cancellation guidelines for Mastercard subscribers
* **Payment refunded:** Notifies subscribers of a refund on a transaction

### Subscription templates

* **New subscription:** Sent to the customer after a successful sign-up or when a subscription with a future start date is activated
* **Subscription change:** Notifies subscribers of changes made to their existing subscription
* **Subscription pause scheduled:** Sent when a subscription is scheduled to be paused
* **Pause reminder:** Sent [n] days before an upcoming subscription pause (default: seven days; configurable in template settings)
* **Pause cancellation confirmation:** Sent when a scheduled subscription pause is canceled
* **Subscription resume reminder:** Sent [n] days before a paused subscription resumes (default: seven days; configurable in template settings)
* **Subscription canceled:** Sent upon subscription cancellation
* **Subscription expired:** Sent when a subscription terminates, either immediately or at the end of a post-cancellation billing cycle
* **Trial ending:** Sent before the trial period ends, informing the customer of the upcoming transition to a paid subscription. Required by law in many regions. Only available for plans with a trial length greater than three days

### Subscription renewal templates

* **Bill date reminder:** Sent before the upcoming billing date
* **Term renewal reminder:** Sent before the renewal or billing date to keep subscribers informed
* **6-month reminder:** Sent every six months that a subscription is active, in compliance with specific regional regulations
* **Annual reminder:** Sent yearly from the subscription start date, in compliance with specific regional regulations
* **Mastercard reminder:** Sent before the billing date to Mastercard users, including required subscription cancellation instructions per Mastercard policies
* **SEPA renewal reminder:** Sent to customers using the SEPA payment method
* **BACS renewal reminder:** Sent to customers using the BACS payment method
* **Credit card expired:** Sends a one-time reminder before a card's expiration date, ahead of the next billing cycle. Only triggered for cards that are expiring — not cards already expired at import
* **Ramp price change:** Notifies subscribers of an upcoming price change in a ramp pricing model subscription

> **Note:** The number of days prior can be configured within the renewal reminder templates.
>
> <Image align="center" border={true} width="75%" src="https://files.readme.io/926ff959b27d50be073c5e2839fe1c582685316f1e649391758efc4c45879b40-Screenshot_2025-10-01_at_9.00.02_AM.png" className="border" />

### Gift card templates

* **Gift card delivery:** Delivered to the recipient immediately after purchase or on a predetermined delivery date
* **Gift card purchase confirmation:** Confirms the purchase to the buyer after a gift card is bought
* **Gift card balance low:** Alerts the customer that their gift subscription is nearing its end, prompting them to update their billing information seven days before renewal (this timing is not configurable)
* **Gift card redemption reminder:** Reminds the recipient to redeem their gift card one month after the delivery date if it remains unused

### Dunning management templates

This section lets you create email templates to manage failed payment scenarios. You can set different send intervals, choose the number of messages sent, select specific templates, and determine the final status of a subscription and invoice if payment isn't collected.

* **Post-trial payment declined:** Part of the trial dunning cycle — alerts subscribers to an unsuccessful payment after their trial ends
* **Payment declined:** Notifies customers when a payment fails during the regular billing cycle. Multiple messages can be configured to send at different intervals, giving you control over the cadence of reminders
* **Payment declined due to 3D Secure 2:** Alerts customers to payment declines that require 3D Secure 2 (3DS2) authentication. This email replaces the standard Payment Declined email for applicable transactions and follows the same dunning cycle settings. Supported gateways: Adyen, Worldpay, First Data, Payeezy, and SagePay/Opayo
* **Invoice past due:** Notifies customers of past-due manual invoices as part of the manual invoice dunning cycle
* **Expired for non-payment:** Sent during any dunning cycle to notify subscribers their subscription has expired due to non-payment

***

## Customization

Recurly gives you several ways to personalize your email templates — from adding images and dynamic parameters to configuring CC/BCC recipients and custom sender addresses. For a full list of available parameters, see the [Parameters](#parameters) section below.

### Adding CC or BCC addresses

You can add CC or BCC addresses to any automated email — useful for monitoring customer actions such as cancellations or payment declines.

**To add a CC address:**

1. Go to your Email Templates page
2. Find the template you want to update and click **Customize**
3. Click **Edit**
4. In the **CC Email Address** field, enter the email addresses you want to copy (separate multiple addresses with a comma)
5. Click **Update Email Template** to save

To use BCC instead, go to **Advanced Settings → Email Settings** and check the **Send email copies as BCC** option.

### Changing the from address

By default, your site's primary email address is used for all outgoing emails. Each template can have its own sender address and display name. Use the following format:

```
"Recurly Support" <support@recurly.com>
```

### Configuring HTML emails

Recurly automatically sends both plain-text and HTML versions of every email. Subscribers see the HTML version if their email client supports it; otherwise, they receive the plain-text version. You can customize both versions independently or disable the HTML version for individual email types.

#### Adjusting headers and footers

Your emails include default header and footer content. To remove them from a specific template, delete the `{{{header}}}` and `{{{footer}}}` tags from the template body.

#### Displaying foreign currencies correctly

To render non-US currency symbols correctly, use three curly braces (`{{{`) instead of two (`{{`). This preserves the raw text and displays the correct symbols.

#### Using boolean sections for custom messages

You can personalize emails based on subscription conditions using boolean sections. For example, in a New Subscription email, you might want to show different messaging depending on whether a trial period applies:

```
{{#subscription_has_trial?}}
  Your account will be billed {{{subscription_total_amount}}} in 10 days.
{{/subscription_has_trial?}}

{{^subscription_has_trial?}}
  Your mandate ID is: {{direct_debit_mandate_id}}.
{{/subscription_has_trial?}}
```

The `^` character tests that a variable is false. The second block runs only if the customer is not in a trial period.

You can also use this technique to hide content when a value is absent — for example, suppressing the next payment date if none exists:

```
{{#subscription_next_payment_date}}
  Next Payment Date: {{subscription_next_payment_date}}
{{/subscription_next_payment_date}}
```

You can apply the same pattern to customize renewal reminders for Direct Debit customers based on whether a mandate ID is present:

```
{{#subscription_has_trial?}}
  Your account will be billed {{{subscription_total_amount}}} in 10 days.
{{/billing_has_active_mandate?}}

{{^subscription_has_trial?}}
  Your mandate ID is: {{direct_debit_mandate_id}}.
{{/billing_has_active_mandate?}}
```

#### Invoice line items

In templates such as New Subscription, Payment Confirmation, Payment Declined, New Invoice, and Invoice Past Due, you can list the invoice line items for your customers:

```
{{#invoice_line_items}}
{{{line_amount}}} -- {{line_description}}
{{{line_date}}}
{{/invoice_line_items}}
```

#### Subscription add-ons

To display the add-ons a customer has subscribed to:

```
{{#subscription_add_ons}}
{{add_on_name}}
{{add_on_price}}
{{/subscription_add_ons}}
```

#### Coupons and discounts

To display coupon details and discount amounts on invoices:

```
{{#invoice_has_discount?}}
  {{#invoice_discounts}}
  Coupon: {{coupon_code}} // Good For {{coupon_lifetime}}
  {{/invoice_discounts}}
  Discount: {{{invoice_discount_amount}}}
{{/invoice_has_discount?}}
```

To display active coupon redemptions on a customer's account:

```
{{#account_has_coupon?}}
 {{#coupons}}Coupon: {{coupon_code}} // Good For {{coupon_lifetime}}{{/coupons}}
{{/account_has_coupon?}}
```

Note: This won't show single-use coupons that have already been redeemed. Use the invoice discount template above for those cases.

#### Adding images

To add an image such as your company logo, insert the following HTML in your email header:

```html
<body>
<div style="border-bottom:1px solid #E8E8E8; margin:0px 14px;">
<img style="padding:0px 0px 6px 0px;" src="http://mycompanylogo.gif"/>
</div>
```

***

## Email deliverability

### Sender Authentication

Recurly's **Sender Authentication** feature lets you verify your DNS records directly from the Email Templates page — the most reliable way to ensure your emails are delivered successfully.

To set it up:

1. Copy the DNS values shown in Recurly
2. Add them to your DNS provider
3. Return to Recurly and click **Verify DNS**

<Image align="center" border={true} width="75%" src="https://files.readme.io/f9ae7908b31c93c5d9b93bbc5da5b9238f175ff39395c7108c41aa74e1a56773-Screenshot_2026-02-04_at_1.52.21_PM.png" className="border" />

If a template has a specific "from" address configured, that template name appears under the associated domain in the Sender Authentication panel. Templates using the default sender address are listed as **Default Sender**.

> **Note:** Sender Authentication is only available to sites that do not have their own paid SendGrid account. If you're using a paid SendGrid integration, refer to the [SendGrid documentation](https://docs.recurly.com/docs/sendgrid) instead.

***

## Customizing email preferences

Recurly supports email preference management at both the site level and the plan level.

**Site-level customization:**

1. Go to the Email Templates page
2. Select the enabled templates you want to update
3. Click **Edit** next to **Settings**
4. Toggle the status to your desired setting

Disabling an email at the site level deactivates it across all plans.

**Plan-level customization:**

1. Confirm the email template is active at the site level
2. Go to **Customization → Plans**
3. Find the plan you want to update
4. Uncheck the email template box to disable it for that plan

***

## Template management tools

### Live email preview

While editing a template, click the **Preview** button to see a real-time view of your changes before saving.

### Sending test emails

To see exactly how an email will appear to your subscribers:

1. Open the email template editing page
2. Click **Send Test Email** (located next to the **Preview** button)

<Image align="center" border={true} width="75%" src="https://files.readme.io/0894ff2fab671614c1286921899ad30bcb49c709f75fee4e80576081e3d59dbb-Screenshot_2025-10-01_at_9.05.33_AM.png" className="border" />

If the test email doesn't arrive shortly, check your spam or junk folder.

### Resetting templates

Recurly periodically updates its default email templates. These updates won't overwrite your customizations, but if you want to revert a template to the Recurly default:

1. Click **Customize** on the appropriate email template
2. Click **Edit** in the "Plain-text Body" or "HTML Body" section
3. Scroll to the bottom and click **Reset Template** (shown in red; only visible if you've customized the template)
4. Confirm the reset

Resetting a template does not affect the HTML Enabled flag, TO address, BCC address, or subject line.

***

## Parameters

Email parameters are placeholders that automatically pull in personalized details when an email is generated. Use them to make your communications more relevant and accurate.

**Best practices:**

* Use parameters consistently across templates to avoid confusion
* Only use a parameter where it adds clear context
* Always send a test email after adding new parameters to confirm they render correctly

### Basic parameters

| Parameter                     | Description                        |
| ----------------------------- | ---------------------------------- |
| `{{user_name}}`               | The customer's name                |
| `{{user_email}}`              | The customer's email address       |
| `{{subscription_start_date}}` | The start date of the subscription |
| `{{subscription_end_date}}`   | The end date of the subscription   |

### Advanced parameters

| Parameter              | Description                                                           |
| ---------------------- | --------------------------------------------------------------------- |
| `{{payment_method}}`   | The payment method chosen by the customer (e.g., credit card, PayPal) |
| `{{payment_due_date}}` | The upcoming payment due date                                         |
| `{{past_due_amount}}`  | The overdue amount, if applicable                                     |
| `{{total_due}}`        | The total amount due                                                  |
| `{{invoice_due_date}}` | The deadline for invoice payment                                      |

### Template parameters

#### Company information

For merchants using Multiple Business Entities, the company value merged into each email parameter reflects the Business Entity applied to the associated invoice, or the overriding Business Entity applied to the customer's account.

| Parameter                                                  |
| ---------------------------------------------------------- |
| `{{company_name}}`                                         |
| `{{company_email}}`                                        |
| `{{company_url}}`                                          |
| `{{company_hosted_account_management_enabled?}}`           |
| `{{company_hosted_account_management_full_access?}}`       |
| `{{company_hosted_account_management_allow_pay_invoice?}}` |
| `{{company_address1}}`                                     |
| `{{company_address2}}`                                     |
| `{{company_city}}`                                         |
| `{{company_state}}`                                        |
| `{{company_zip}}`                                          |
| `{{company_country}}`                                      |
| `{{company_full_address}}`                                 |
| `{{company_phone_number}}`                                 |
| `{{company_vat_number}}`                                   |
| `{{company_registration_number}}`                          |

#### Subscription plan details

| Parameter                 | Description                                                     |
| ------------------------- | --------------------------------------------------------------- |
| `{{plan_name}}`           |                                                                 |
| `{{plan_code}}`           |                                                                 |
| `{{plan_description}}`    |                                                                 |
| `{{plan_per_interval}}`   | The billing period interval, e.g., "per month" or "per 2 weeks" |
| `{{plan_trial_interval}}` | The trial period, e.g., "1 month" or "2 weeks"                  |

#### Shipping address parameters for subscriptions

| Parameter                                | Description                                               |
| ---------------------------------------- | --------------------------------------------------------- |
| `{{subscription_has_shipping_address?}}` | Returns `true` if the subscription has a shipping address |
| `{{subscription_shipping_nickname}}`     |                                                           |
| `{{subscription_shipping_first_name}}`   |                                                           |
| `{{subscription_shipping_last_name}}`    |                                                           |
| `{{subscription_shipping_address1}}`     |                                                           |
| `{{subscription_shipping_address2}}`     |                                                           |
| `{{subscription_shipping_city}}`         |                                                           |
| `{{subscription_shipping_state}}`        |                                                           |
| `{{subscription_shipping_zip}}`          |                                                           |
| `{{subscription_shipping_country}}`      |                                                           |
| `{{subscription_shipping_phone}}`        |                                                           |
| `{{subscription_shipping_email}}`        |                                                           |
| `{{subscription_shipping_vat_number}}`   |                                                           |
| `{{subscription_full_shipping_address}}` | Full shipping address in one string, separated by commas  |

#### Subscription alteration parameters

| Parameter                              | Description                                                                                                                     |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `{{change_at_renewal?}}`               | Returns `true` if the change timeframe is renewal or term_end, or if the timeframe is bill_date and total_billing_cycles is one |
| `{{change_at_bill_date?}}`             | Returns `true` if the change timeframe is bill_date AND total_billing_cycles is greater than one                                |
| `{{change_plan_name}}`                 |                                                                                                                                 |
| `{{change_plan_description}}`          |                                                                                                                                 |
| `{{change_plan_per_interval}}`         |                                                                                                                                 |
| `{{change_subscription_quantity}}`     |                                                                                                                                 |
| `{{change_subscription_total_amount}}` |                                                                                                                                 |
| `{{change_subscription_unit_amount}}`  |                                                                                                                                 |
| `{{change_subscription_add_ons}}`      |                                                                                                                                 |

#### Account details

| Parameter                            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `{{account_code}}`                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_username}}`               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_first_name}}`             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_last_name}}`              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_full_name}}`              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_company_name}}`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_email}}`                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_full_address}}`           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_address1}}`               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_address2}}`               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_city}}`                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_state}}`                  | State or province                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `{{account_zip}}`                    | Zip or postal code                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `{{account_country}}`                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `{{account_hosted_maintenance_url}}` | URL with an embedded authorization token to automatically log in to your hosted account management page. If hosted account management is set to "Guest View Only," this returns the Guest View Edit Billing Info URL. If disabled, this URL returns a 404. To generate the Guest View Edit Billing Info URL correctly, remove the `{{#company_hosted_account_management_full_access?}}` and `{{/company_hosted_account_management_full_access?}}` conditional tags from the template |
| `{{coupons}}`                        | Returns coupon information if the account has active coupons                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `{{account_vat_number}}`             | Relevant for customers issued manual invoices or when your Tax Settings are configured to use the Account Info address on the invoice                                                                                                                                                                                                                                                                                                                                                |

#### Coupon parameters

| Parameter                      | Description                                                |
| ------------------------------ | ---------------------------------------------------------- |
| `{{coupon_code}}`              |                                                            |
| `{{coupon_name}}`              |                                                            |
| `{{coupon_lifetime}}`          | A string of either: `Forever`, `Single use`, or `#months`  |
| `{{coupon_discount_percent?}}` | Returns `true` if this coupon is a percentage-off discount |
| `{{coupon_discount_amount?}}`  | Returns `true` if this coupon is an amount-off discount    |
| `{{coupon_discount_percent}}`  |                                                            |
| `{{coupon_discount_amount}}`   |                                                            |
| `{{coupon_description}}`       |                                                            |

#### Billing information

| Parameter                        | Description                                                                                                 |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `{{billing_payment_method}}`     | e.g., Credit Card, PayPal, Amazon Pay, ACH                                                                  |
| `{{billing_cc_type}}`            | Credit card type, e.g., Visa, Mastercard. Returns nothing if payment was made through PayPal                |
| `{{billing_last_four}}`          | Last four digits of the credit card number                                                                  |
| `{{billing_first_name}}`         |                                                                                                             |
| `{{billing_last_name}}`          |                                                                                                             |
| `{{billing_address1}}`           |                                                                                                             |
| `{{billing_address2}}`           |                                                                                                             |
| `{{billing_city}}`               |                                                                                                             |
| `{{billing_state}}`              | State or province                                                                                           |
| `{{billing_zip}}`                | Zip or postal code                                                                                          |
| `{{billing_country}}`            |                                                                                                             |
| `{{billing_full_address}}`       |                                                                                                             |
| `{{billing_ip_address}}`         | The account's IP address at the time of the last billing info update                                        |
| `{{billing_vat_applicable?}}`    | Returns `true` if the account charges VAT                                                                   |
| `{{billing_vat_number}}`         | The account's VAT number                                                                                    |
| `{{billing_has_active_mandate}}` | Use to conditionally display a sentence containing `{{direct_debit_mandate_id}}` only when a mandate exists |

#### Invoice details

| Parameter                              | Description                                                                                                                                                                |
| -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{{invoice_number}}`                   |                                                                                                                                                                            |
| `{{invoice_date}}`                     | Date the invoice was created. May differ from `{{transaction_date}}` if the initial transaction failed. `{{transaction_date}}` may be empty if no transaction was required |
| `{{invoice_subtotal}}`                 | Total amount after discounts are applied                                                                                                                                   |
| `{{{invoice_discount_amount}}}`        | Dollar amount of discount applied to the invoice. _Requires three curly braces_                                                                                            |
| `{{invoice_total_paid}}`               | Total amount of payments applied to the invoice                                                                                                                            |
| `{{invoice_total_due}}`                | Total amount outstanding on the invoice; zero if paid                                                                                                                      |
| `{{invoice_line_items}}`               | Collection of line items on the invoice. _Requires a leading pound sign_                                                                                                   |
| `{{invoice_po_number}}`                | Invoice PO number for manual invoicing                                                                                                                                     |
| `{{invoice_net_terms}}`                | Invoice net terms for manual invoicing                                                                                                                                     |
| `{{invoice_has_tax?}}`                 | Returns `true` if the invoice has taxes applied                                                                                                                            |
| `{{invoice_tax_amount}}`               | Total tax amount applied to the invoice                                                                                                                                    |
| `{{invoice_tax_rate}}`                 | Percentage tax rate, e.g., "7.25%"                                                                                                                                         |
| `{{invoice_tax_region}}`               | The region for which taxes were collected, e.g., "CA" or "DE"                                                                                                              |
| `{{invoice_customer_notes}}`           | Notes from the Customer Notes field on the invoice                                                                                                                         |
| `{{invoice_terms_and_conditions}}`     | Notes from the Terms and Conditions field on the invoice                                                                                                                   |
| `{{invoice_vat_reverse_charge_notes}}` | Notes from the VAT Reverse Charge Notes field. Relevant for EU VAT Reverse Charge scenarios only                                                                           |
| `{{invoice_bill_to_full_name}}`        |                                                                                                                                                                            |
| `{{invoice_bill_to_company}}`          |                                                                                                                                                                            |
| `{{invoice_bill_to_full_address}}`     |                                                                                                                                                                            |
| `{{invoice_bill_to_address1}}`         |                                                                                                                                                                            |
| `{{invoice_bill_to_address2}}`         |                                                                                                                                                                            |
| `{{invoice_bill_to_city}}`             |                                                                                                                                                                            |
| `{{invoice_bill_to_state}}`            |                                                                                                                                                                            |
| `{{invoice_bill_to_zip}}`              |                                                                                                                                                                            |
| `{{invoice_bill_to_country}}`          |                                                                                                                                                                            |
| `{{invoice_bill_to_phone}}`            |                                                                                                                                                                            |
| `{{invoice_ship_to_full_name}}`        |                                                                                                                                                                            |
| `{{invoice_ship_to_company}}`          |                                                                                                                                                                            |
| `{{invoice_ship_to_full_address}}`     |                                                                                                                                                                            |
| `{{invoice_ship_to_address1}}`         |                                                                                                                                                                            |
| `{{invoice_ship_to_address2}}`         |                                                                                                                                                                            |
| `{{invoice_ship_to_city}}`             |                                                                                                                                                                            |
| `{{invoice_ship_to_state}}`            |                                                                                                                                                                            |
| `{{invoice_ship_to_zip}}`              |                                                                                                                                                                            |
| `{{invoice_ship_to_country}}`          |                                                                                                                                                                            |
| `{{invoice_ship_to_phone}}`            |                                                                                                                                                                            |

#### Line item details

| Parameter                   | Description                                                                                                                                                                                                                                                                                                                                  |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{{{line_date}}}`           | Line item date or date range. _Requires three curly braces_                                                                                                                                                                                                                                                                                  |
| `{{line_description}}`      |                                                                                                                                                                                                                                                                                                                                              |
| `{{{line_amount}}}`         | Line item total amount. _Requires three curly braces_                                                                                                                                                                                                                                                                                        |
| `{{line_amount_is_zero?}}`  | Returns `true` if the line item has a zero amount                                                                                                                                                                                                                                                                                            |
| `{{{line_unit_amount}}}`    | Line item unit amount. _Requires three curly braces_                                                                                                                                                                                                                                                                                         |
| `{{{line_quantity}}}`       | Line item quantity. _Requires three curly braces_                                                                                                                                                                                                                                                                                            |
| `{{line_quantity_is_one?}}` | Returns `true` if the line item quantity is one                                                                                                                                                                                                                                                                                              |
| `{{line_accounting_code}}`  | Accounting code of the line item's charge                                                                                                                                                                                                                                                                                                    |
| `{{line_discount_amount}}`  | The line item's discount amount, if one exists; otherwise returns zero. Purchase discounts return as positive values; refund discounts return as negative values. Wrap in an `invoice_has_discount` check to display only when at least one line item has a discount. Not included in any default templates — you'll need to add it manually |
| `{{line_external_sku}}`     | Used with Item Catalog only. Displays the External SKU of the item sold                                                                                                                                                                                                                                                                      |
| `{{line_product_code}}`     | Displays the Plan Code, Add-on Code, or Item Code of the line item                                                                                                                                                                                                                                                                           |

#### Subscription and add-on information

| Parameter                                           | Description                                                                                                                                                                            |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{{subscription_expires_at_with_time}}`             | Date and time (timezone-adjusted) when the subscription expires, if canceled                                                                                                           |
| `{{subscription_canceled_at_with_time}}`            | Date and time (timezone-adjusted) when the subscription was canceled                                                                                                                   |
| `{{subscription_trial_ends_at_with_time}}`          | Date and time (timezone-adjusted) when the current trial period ends                                                                                                                   |
| `{{subscription_paused_at}}`                        | Date when the current subscription pauses                                                                                                                                              |
| `{{subscription_active?}}`                          | Returns `true` if the subscription is currently active                                                                                                                                 |
| `{{subscription_quantity}}`                         | Subscription quantity                                                                                                                                                                  |
| `{{subscription_quantity_is_one?}}`                 | Returns `true` if the subscription quantity is one                                                                                                                                     |
| `{{{subscription_total_amount}}}`                   | Subscription total renewal amount. _Requires three curly braces_                                                                                                                       |
| `{{subscription_unit_amount}}`                      | Subscription per-unit amount                                                                                                                                                           |
| `{{subscription_has_trial?}}`                       | Returns `true` if the subscription has a trial period                                                                                                                                  |
| `{{subscription_has_no_trial?}}`                    | Returns `true` if the subscription does not have a trial period                                                                                                                        |
| `{{subscription_trial_without_billing_info?}}`      | Returns `true` if billing info is empty and the reason is `no_billing_info_reason?` = `plan_free_trial`. Useful for Trial Ending emails on free trials that don't require billing info |
| `{{subscription_expires_at}}`                       | Date when the subscription expires, if canceled                                                                                                                                        |
| `{{subscription_current_period_started_at}}`        | Date when the current billing period started                                                                                                                                           |
| `{{subscription_current_period_ends_at}}`           | Date when the current billing period ends, including trial periods                                                                                                                     |
| `{{subscription_current_period_ends_at_with_time}}` | Date and time (UTC) when the current billing period ends, including trial periods                                                                                                      |
| `{{subscription_next_payment_date}}`                | Date when the next payment will be charged                                                                                                                                             |
| `{{subscription_customer_notes}}`                   | Customer notes saved on the subscription. Returns the site's default customer notes if none are set on the subscription                                                                |
| `{{subscription_add_ons}}`                          | Lists any add-ons on the subscription                                                                                                                                                  |
| `{{add_on_name}}`                                   | Within a `subscription_add_ons` block, returns the name of the add-on                                                                                                                  |
| `{{add_on_price}}`                                  | Within a `subscription_add_ons` block, returns the price of the add-on. For usage-based add-ons with a percentage pricing model, returns a percentage                                  |
| `{{add_on_usage_based?}}`                           | Returns `true` if the add-on is usage-based                                                                                                                                            |
| `{{add_on_percentage?}}`                            | Returns `true` if the add-on is usage-based with a percentage pricing model                                                                                                            |
| `{{add_on_measured_unit_display_name}}`             | Within a `subscription_add_ons` block, returns the measured unit display name for usage-based add-ons                                                                                  |
| `{{add_on_external_sku}}`                           | Used with Item Catalog only. Displays the External SKU of an item sold as an add-on                                                                                                    |
| `{{subscription_total_billing_cycles}}`             | Number of billing periods in the current subscription term                                                                                                                             |
| `{{subscription_current_term_started_at}}`          | Date when the current subscription term started                                                                                                                                        |
| `{{subscription_current_term_ends_at}}`             | Date when the current subscription term ends. Use instead of `current_billing_period_ends_at` to accurately reflect the term renewal date                                              |
| `{{subscription_renewal_billing_cycles}}`           | If the subscription is auto-renewing, the number of billing periods in the next term                                                                                                   |
| `{{subscription_term_auto_renew?}}`                 | Returns `true` if the subscription is configured to auto-renew after the current term                                                                                                  |
| `{{subscription_term_balance}}`                     | For subscriptions with multiple billing periods, the remaining amount due                                                                                                              |
| `{{subscription_remaining_billing_cycles}}`         | Remaining billing periods in the current subscription term                                                                                                                             |
| `{{subscription_total_term_amount}}`                | Total cost of the subscription, excluding usage charges and setup fees                                                                                                                 |
| `{{subscription_shipping_cost}}`                    | Amount charged to the customer for shipping                                                                                                                                            |
| `{{subscription_shipping_method}}`                  | Shipping method used on the charge                                                                                                                                                     |
| `{{subscription_remaining_pause_cycles}}`  | Number of pause cycles remaining on the subscription                                                                                                                                    |
| `{{subscription_resume_at}}`               | Date when a paused subscription will resume                                                                                                                                             |

#### Subscriptions

| Parameter                           | Description                                                                                                                                                                                                                                                                                                                |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{{subscriptions_list}}`            | An array listing all subscriptions for a given invoice. Each subscription contains the same properties as the subscription fields above, plus two additional properties: **First?** (returns `true` if first in list) and **Last?** (returns `true` if last in list). Useful for checkouts with more than one subscription |
| `{{subscriptions_has_many}}`        | Returns `true` if there is more than one subscription in `subscriptions_list`                                                                                                                                                                                                                                              |
| `{{subscriptions_includes_trial}}`  | Returns `true` if any subscription in `subscriptions_list` is a trial                                                                                                                                                                                                                                                      |
| `{{subscriptions_includes_active}}` | Returns `true` if any subscription in `subscriptions_list` is active                                                                                                                                                                                                                                                       |
| `{{subscriptions_empty}}`           | Returns `true` if `subscriptions_list` contains no subscriptions                                                                                                                                                                                                                                                           |

#### Gift card fields

| Parameter                              | Description                                                                                                                                                                                                |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `{{gift_card_redemption_code}}`        | The current redemption code of the gift card                                                                                                                                                               |
| `{{gift_card_amount}}`                 | The amount of the gift card                                                                                                                                                                                |
| `{{gift_card_currency}}`               | The currency of the gift card amount                                                                                                                                                                       |
| `{{gift_card_delivery_first_name}}`    | The first name of the gift recipient                                                                                                                                                                       |
| `{{gift_card_delivery_last_name}}`     | The last name of the gift recipient                                                                                                                                                                        |
| `{{gift_card_personal_message}}`       | The personal message for the gift recipient                                                                                                                                                                |
| `{{gift_card_gifter_name}}`            | The gifter's name specified for delivery messaging                                                                                                                                                         |
| `{{{gift_card_image}}}`                | The gift card product's image. _Requires three curly braces_                                                                                                                                               |
| `{{gift_card_delivery_method}}`        | Whether the gift card delivery method is `email` or `post`                                                                                                                                                 |
| `{{gift_card_delivery_email_address}}` | The recipient's email address                                                                                                                                                                              |
| `{{gift_card_delivery_address1}}`      |                                                                                                                                                                                                            |
| `{{gift_card_delivery_address2}}`      |                                                                                                                                                                                                            |
| `{{gift_card_delivery_city}}`          |                                                                                                                                                                                                            |
| `{{gift_card_delivery_state}}`         |                                                                                                                                                                                                            |
| `{{gift_card_delivery_zip}}`           |                                                                                                                                                                                                            |
| `{{gift_card_delivery_country}}`       |                                                                                                                                                                                                            |
| `{{gift_card_delivery_phone}}`         |                                                                                                                                                                                                            |
| `{{gift_card_delivery_deliver_at}}`    | The future delivery date of the gift card                                                                                                                                                                  |
| `{{#gift_card_has_personal_message?}}` | Returns `true` if the gift card has a personal message. Useful for hiding the message display if not included at purchase                                                                                  |
| `{{#gift_card_has_gifter_name?}}`      | Returns `true` if the gift card has a gifter name. Useful for hiding the display if not included at purchase                                                                                               |
| `{{#gift_card_has_image?}}`            | Returns `true` if the gift card product has an image uploaded. Useful for hiding image display if no image exists                                                                                          |
| `{{#gift_card_has_deliver_at?}}`       | Returns `true` if the gift card has a future delivery date                                                                                                                                                 |
| `{{#gift_card_delivery_city?}}`        | Returns `true` if the gift card has a city in the delivery address. Useful for hiding an address comma when no city is present                                                                             |
| `{{#subscription_is_gift?}}`           | Returns `true` if the subscription started with a gift card. Useful with `account_has_billing_info?` in subscription emails to show special messaging to gift card customers about adding a payment method |
| `{{^account_has_billing_info?}}`       | Returns `true` if no billing information exists on the account. Useful nested under `subscription_is_gift?` to prompt gift card customers to add a payment method                                          |

#### Transaction fields

| Parameter                         | Description                                                                                  |
| --------------------------------- | -------------------------------------------------------------------------------------------- |
| `{{transaction_id}}`              | Transaction UUID: 32 characters, alphanumeric                                                |
| `{{transaction_amount}}`          | Transaction dollar amount                                                                    |
| `{{transaction_date}}`            | Transaction date                                                                             |
| `{{transaction_date_and_time}}`   | Transaction date and time (timezone-adjusted)                                                |
| `{{transaction_declined?}}`       | Returns `true` if the transaction was declined                                               |
| `{{transaction_success?}}`        | Returns `true` if the transaction was successful                                             |
| `{{transaction_voided?}}`         | Returns `true` if the transaction was voided                                                 |
| `{{#transaction_ach?}}`           | Returns `true` if the transaction was paid via ACH                                           |
| `{{transaction_decline_details}}` | A brief explanation of why the transaction was declined and how the customer can resolve it  |
| `{{transaction_payment_method}}`  | e.g., Credit Card, PayPal, Amazon Pay, ACH                                                   |
| `{{transaction_cc_type}}`         | Credit card type, e.g., Visa, Mastercard. Returns nothing if payment was made through PayPal |
| `{{transaction_cc_last_four}}`    | Last four digits of the credit card number                                                   |

#### Direct debit fields

| Parameter                              | Description                                                               |
| -------------------------------------- | ------------------------------------------------------------------------- |
| `{{direct_debit_mandate_id}}`          | Mandate information for direct debit transactions made through GoCardless |
| `{{direct_debit_creditor_identifier}}` | Creditor information for direct debit charges through GoCardless          |

#### Ramp pricing fields

| Parameter                                        | Description                                                  |
| ------------------------------------------------ | ------------------------------------------------------------ |
| `{{subscription_next_ramp_interval_start_date}}` | The date when the customer's next pricing interval begins    |
| `{{subscription_next_ramp_interval_price}}`      | The price that will apply at the start of that next interval |

#### Custom fields

Recurly supports email parameters for custom fields on Accounts, Plans, Subscriptions, Items, and Charges. This lets you merge custom field values directly into your email templates.

> **Note:** Custom field names may only contain alphanumeric characters and underscores. Special characters in field names are automatically converted to underscores, and sequences of underscores are reduced to a single underscore.

**Parameter format:**

* **Field value:** `{{account_custom_field_<name>}}`
  * Example: `{{account_custom_field_has_professional_services_engagement}}` merges the value of the custom field "Has professional services engagement" from the account object
* **Boolean (yes/no):** `{{account_custom_field_<name>_<value?>}}`
  * Example: `{{account_custom_field_does_customer_have_professional_services_engagement}}` returns true/false for the field "Does customer have professional services engagement?"

# FAQs

**How does overriding the `trial_ends_at` date via API affect emails?** If the trial end date is set within three days, the Trial Ending email won't be sent.

**Does setting a future start date trigger the Renewal Reminder?** Yes, if the date is more than two days out.

**What happens if there's no email address on file for an account?** The site's default billing contact email is used. Make sure you're collecting or passing the subscriber's email address to Recurly.

**Can the Renewal Reminder and Trial Ending emails be configured via API?** Currently, these can only be configured through the admin console.

**Will changes to email templates affect existing subscribers?** Yes — as long as the subscriber's subscription meets the criteria for those emails, they'll receive the updated version.

**Can upcoming invoice or subscription details be included in Renewal Reminder or Trial Ending emails?** No. These emails reference data available at the time they're generated.

**If both the Term Renewal Reminder and the Annual Reminder are enabled and a subscription is renewing at the 12-month mark, which template gets sent?** If both templates are configured to trigger on the same number of days prior, only one will send — the Term Renewal Reminder takes priority. To send both, configure them to different day values.

**If a merchant enables the Annual Renewal Reminder, will it apply to existing subscriptions?** Yes. Once enabled, the Annual Renewal Reminder applies to all subscriptions — both new and existing — for any plans that have the template enabled.
