---
title: Email templates
excerpt: >-
  Configure, customize, and manage Recurly's automated email templates for
  account actions, billing events, subscription changes, gift cards, and dunning
  scenarios.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Recurly's email templates give you a complete system for automated subscriber communications — from sign-up confirmations and renewal reminders to dunning sequences and gift card delivery. Every template is customizable, brandable, and ready to go out of the box.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#email-notification-templates"><span class="rp-toc-num">3</span>Email notification templates</a>
    <a class="rp-toc-pill" href="#customization"><span class="rp-toc-num">4</span>Customization</a>
    <a class="rp-toc-pill" href="#email-deliverability"><span class="rp-toc-num">5</span>Email deliverability</a>
    <a class="rp-toc-pill" href="#email-preferences"><span class="rp-toc-num">6</span>Email preferences</a>
    <a class="rp-toc-pill" href="#template-management-tools"><span class="rp-toc-num">7</span>Template management tools</a>
    <a class="rp-toc-pill" href="#parameters"><span class="rp-toc-num">8</span>Parameters</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">9</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A valid billing contact email address must be configured on your Recurly site for fallback notifications</li>
  <li>Sender Authentication is strongly recommended before going live with custom from addresses</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Email notifications are only sent to valid email addresses — addresses ending in <code>@test.com</code> or <code>@example.com</code> are treated as invalid</li>
  <li>The Trial Ending email can only be enabled for plans with a trial length greater than three days</li>
  <li>The Gift Card Balance Low reminder is fixed at seven days before renewal and is not configurable</li>
  <li>The Sender Authentication feature is only available to sites that do not have their own paid SendGrid account</li>
</ul>

# Definition

<div class="rp-definition">Email templates in Recurly are predefined layouts and formats used to send automated emails to subscribers at every stage of the subscription lifecycle. They maintain brand consistency, reduce manual effort, and ensure the right message reaches the right person at the right time.</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Compliance notice</strong>To stay compliant with regulations such as PCI-DSS and HIPAA, never include sensitive information — such as protected health information or credit card numbers — in your email templates.</div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Consistent branding</strong>
    <span>Every email your subscribers receive reflects your brand's identity and voice, without manual effort on each send.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Increased efficiency</strong>
    <span>Automating repetitive communications frees your team to focus on higher-value work.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Personalized communication</strong>
    <span>Dynamic parameters let you tailor each email to the individual recipient, making messages feel relevant rather than generic.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Fewer errors</strong>
    <span>Predefined formats reduce the risk of mistakes that come with manually drafted communications.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Stronger engagement</strong>
    <span>Well-structured, on-brand emails give subscribers the information they need and build trust over time.</span>
  </div>
</div>

# Email notification templates

Recurly offers a comprehensive set of email notification templates covering account actions, billing events, subscription changes, gift cards, and dunning scenarios. All templates are in English by default unless you modify them.

When no valid email address is associated with an account, notifications are sent to the site's billing contact instead.


<Image src="https://files.readme.io/51b738ac9318251a7b96502b8da589d573ed105e5c0f96fd48eee958684aa412-Screenshot_2025-10-01_at_8.58.03_AM.png" align="center" width="75%" border={true} />


## Debt collection email notifications

To support compliance with the federal Fair Debt Collection Practices Act (FDCPA), Recurly gives merchants the option to send all payment-related emails between 2:00–4:00 PM ET daily. Emails that would otherwise send outside that window are held and delivered the following day during the same timeframe.

This setting is available on the <a href="https://docs.recurly.com/docs/site-settings#email-settings" target="_blank">Site Settings page</a>. When enabled, it applies to the following templates:

<ul class="rp-list">
  <li>New Invoice</li>
  <li>New Subscription</li>
  <li>Trial Ending</li>
  <li>Bill Date Reminder</li>
  <li>Term Renewal Reminder</li>
  <li>Mastercard Reminder</li>
  <li>SEPA Renewal Reminder</li>
  <li>BACS Renewal Reminder</li>
  <li>Credit Card Expired</li>
  <li>Ramp Price Change</li>
  <li>Gift Card Balance Low</li>
  <li>Payment Declined</li>
  <li>Payment Declined Due to 3D Secure 2</li>
  <li>Invoice Past Due</li>
  <li>Expired for Non-Payment</li>
</ul>

## Header and footer templates

<div class="rp-card">

### Header and footer

- **Email header:** An optional section added to the beginning of all email templates
- **Email footer:** An optional section added to the end of all email templates

</div>

## Account templates

<div class="rp-card">

### Account templates

- **Activate account:** Sent when a customer creates an account using their subscription email address on your account management portal
- **Password reset:** Sent automatically when someone requests a password reset
- **Password has been reset:** Notifies customers that their password was changed, helping maintain account security

</div>

## Invoice templates

<div class="rp-card">

### Invoice templates

- **New invoice:** For manual payment collections — sent when a manual invoice is generated or a new subscription with manual collection is initiated
- **New credit invoice:** Sent when a credit invoice is generated and posted manually
- **Payment confirmation:** Confirms a successful payment transaction, excluding $0 invoices and new subscriptions. Can be configured to send to all customers or only Mastercard users; be sure to include any required cancellation guidelines for Mastercard subscribers
- **Payment refunded:** Notifies subscribers of a refund on a transaction

</div>

## Subscription templates

<div class="rp-card">

### Subscription templates

- **New subscription:** Sent to the customer after a successful sign-up or when a subscription with a future start date is activated
- **Subscription change:** Notifies subscribers of changes made to their existing subscription
- **Subscription pause scheduled:** Sent when a subscription is scheduled to be paused
- **Pause reminder:** Sent \[n] days before an upcoming subscription pause (default: seven days; configurable in template settings)
- **Pause cancellation confirmation:** Sent when a scheduled subscription pause is canceled
- **Subscription resume reminder:** Sent \[n] days before a paused subscription resumes (default: seven days; configurable in template settings)
- **Subscription canceled:** Sent upon subscription cancellation
- **Subscription expired:** Sent when a subscription terminates, either immediately or at the end of a post-cancellation billing cycle
- **Trial ending:** Sent before the trial period ends, informing the customer of the upcoming transition to a paid subscription. Required by law in many regions. Only available for plans with a trial length greater than three days

</div>

## Subscription renewal templates

<div class="rp-card">

### Subscription renewal templates

- **Bill date reminder:** Sent before the upcoming billing date
- **Term renewal reminder:** Sent before the renewal or billing date to keep subscribers informed
- **6-month reminder:** Sent every six months that a subscription is active, in compliance with specific regional regulations
- **Annual reminder:** Sent yearly from the subscription start date, in compliance with specific regional regulations
- **Mastercard reminder:** Sent before the billing date to Mastercard users, including required subscription cancellation instructions per Mastercard policies
- **SEPA renewal reminder:** Sent to customers using the SEPA payment method
- **BACS renewal reminder:** Sent to customers using the BACS payment method
- **Credit card expired:** Sends a one-time reminder before a card's expiration date, ahead of the next billing cycle. Only triggered for cards that are expiring — not cards already expired at import
- **Ramp price change:** Notifies subscribers of an upcoming price change in a ramp pricing model subscription

</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The number of days prior can be configured within the renewal reminder templates.</div>
</div>


<Image src="https://files.readme.io/926ff959b27d50be073c5e2839fe1c582685316f1e649391758efc4c45879b40-Screenshot_2025-10-01_at_9.00.02_AM.png" align="center" width="75%" border={true} />


## Gift card templates

<div class="rp-card">

### Gift card templates

- **Gift card delivery:** Delivered to the recipient immediately after purchase or on a predetermined delivery date
- **Gift card purchase confirmation:** Confirms the purchase to the buyer after a gift card is bought
- **Gift card balance low:** Alerts the customer that their gift subscription is nearing its end, prompting them to update their billing information seven days before renewal (this timing is not configurable)
- **Gift card redemption reminder:** Reminds the recipient to redeem their gift card one month after the delivery date if it remains unused

</div>

## Dunning management templates

This section lets you create email templates to manage failed payment scenarios. You can set different send intervals, choose the number of messages sent, select specific templates, and determine the final status of a subscription and invoice if payment isn't collected.

<div class="rp-card">

### Dunning management templates

- **Post-trial payment declined:** Part of the trial dunning cycle — alerts subscribers to an unsuccessful payment after their trial ends
- **Payment declined:** Notifies customers when a payment fails during the regular billing cycle. Multiple messages can be configured to send at different intervals, giving you control over the cadence of reminders
- **Payment declined due to 3D Secure 2:** Alerts customers to payment declines that require 3DS2 authentication. This email replaces the standard Payment Declined email for applicable transactions and follows the same dunning cycle settings. Supported gateways: Adyen, Worldpay, First Data, Payeezy, and SagePay/Opayo
- **Invoice past due:** Notifies customers of past-due manual invoices as part of the manual invoice dunning cycle
- **Expired for non-payment:** Sent during any dunning cycle to notify subscribers their subscription has expired due to non-payment

</div>

# Customization

Recurly gives you several ways to personalize your email templates — from adding images and dynamic parameters to configuring CC/BCC recipients and custom sender addresses. For a full list of available parameters, see the <a href="#parameters">Parameters</a> section below.

## Adding CC or BCC addresses

Add CC or BCC addresses to any automated email — useful for monitoring customer actions such as cancellations or payment declines.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Go to your Email Templates page</h4><p>Navigate to Email Templates in the admin console.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the template</h4><p>Find the template you want to update and click <strong>Customize</strong>, then <strong>Edit</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enter CC addresses</h4><p>In the <strong>CC Email Address</strong> field, enter the addresses you want to copy. Separate multiple addresses with a comma.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save</h4><p>Click <strong>Update Email Template</strong> to save your changes.</p></div>
  </div>
</div>

To use BCC instead, go to **Advanced Settings → Email Settings** and check **Send email copies as BCC**.

## Changing the from address

By default, your site's primary email address is used for all outgoing emails. Each template can have its own sender address and display name. Use the following format:

```
"Recurly Support" <support@recurly.com>
```

## Configuring HTML emails

Recurly automatically sends both plain-text and HTML versions of every email. Subscribers see the HTML version if their email client supports it; otherwise, they receive the plain-text version. You can customize both versions independently or disable the HTML version for individual email types.

### Adjusting headers and footers

Your emails include default header and footer content. To remove them from a specific template, delete the `{{{header}}}` and `{{{footer}}}` tags from the template body.

### Displaying foreign currencies correctly

To render non-US currency symbols correctly, use three curly braces (`{{{`) instead of two (`{{`). This preserves the raw text and displays the correct symbols.

### Using boolean sections for custom messages

Personalize emails based on subscription conditions using boolean sections. For example, in a New Subscription email you might show different messaging depending on whether a trial period applies:

```
{{#subscription_has_trial?}}
  Your account will be billed {{{subscription_total_amount}}} in 10 days.
{{/subscription_has_trial?}}

{{^subscription_has_trial?}}
  Your mandate ID is: {{direct_debit_mandate_id}}.
{{/subscription_has_trial?}}
```

The `^` character tests that a variable is false — the second block runs only if the customer is not in a trial period.

You can also use this technique to suppress content when a value is absent — for example, hiding the next payment date if none exists:

```
{{#subscription_next_payment_date}}
  Next Payment Date: {{subscription_next_payment_date}}
{{/subscription_next_payment_date}}
```

The same pattern works for customizing renewal reminders for Direct Debit customers based on whether a mandate ID is present:

```
{{#subscription_has_trial?}}
  Your account will be billed {{{subscription_total_amount}}} in 10 days.
{{/billing_has_active_mandate?}}

{{^subscription_has_trial?}}
  Your mandate ID is: {{direct_debit_mandate_id}}.
{{/billing_has_active_mandate?}}
```

### Invoice line items

In templates such as New Subscription, Payment Confirmation, Payment Declined, New Invoice, and Invoice Past Due, you can list the invoice line items for your customers:

```
{{#invoice_line_items}}
{{{line_amount}}} -- {{line_description}}
{{{line_date}}}
{{/invoice_line_items}}
```

### Subscription add-ons

To display the add-ons a customer has subscribed to:

```
{{#subscription_add_ons}}
{{add_on_name}}
{{add_on_price}}
{{/subscription_add_ons}}
```

### Coupons and discounts

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

### Adding images

To add an image such as your company logo, insert the following HTML in your email header:

```html
<body>
<div style="border-bottom:1px solid #E8E8E8; margin:0px 14px;">
<img style="padding:0px 0px 6px 0px;" src="http://mycompanylogo.gif"/>
</div>
```

# Email deliverability

## Sender Authentication

Recurly's Sender Authentication feature lets you verify your DNS records directly from the Email Templates page — the most reliable way to ensure your emails are delivered successfully.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Copy the DNS values</h4><p>From the Email Templates page, copy the DNS values shown in Recurly.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add them to your DNS provider</h4><p>Paste the values into your DNS provider's settings.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Verify</h4><p>Return to Recurly and click <strong>Verify DNS</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f9ae7908b31c93c5d9b93bbc5da5b9238f175ff39395c7108c41aa74e1a56773-Screenshot_2026-02-04_at_1.52.21_PM.png" align="center" width="75%" border={true} />


If a template has a specific "from" address configured, that template name appears under the associated domain in the Sender Authentication panel. Templates using the default sender address are listed as **Default Sender**.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Sender Authentication is only available to sites that do not have their own paid SendGrid account. If you're using a paid SendGrid integration, refer to the <a href="https://docs.recurly.com/docs/sendgrid" target="_blank">SendGrid documentation</a> instead.</div>
</div>

# Email preferences

Recurly supports email preference management at both the site level and the plan level.

## Site-level preferences

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Go to Email Templates</h4><p>Navigate to the Email Templates page in the admin console.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select the templates to update</h4><p>Check the enabled templates you want to modify.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Edit settings</h4><p>Click <strong>Edit</strong> next to <strong>Settings</strong> and toggle the status to your desired setting.</p></div>
  </div>
</div>

Disabling an email at the site level deactivates it across all plans.

## Plan-level preferences

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Confirm the template is active at the site level</h4><p>Plan-level settings only take effect when the template is enabled site-wide.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Go to the plan</h4><p>Navigate to <strong>Customization → Plans</strong> and find the plan you want to update.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Disable the template for this plan</h4><p>Uncheck the email template box to disable it for that plan only.</p></div>
  </div>
</div>

# Template management tools

## Live email preview

While editing a template, click the **Preview** button to see a real-time view of your changes before saving.

## Sending test emails

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the template editing page</h4><p>Navigate to the email template you want to test.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Send a test</h4><p>Click <strong>Send Test Email</strong>, located next to the <strong>Preview</strong> button.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0894ff2fab671614c1286921899ad30bcb49c709f75fee4e80576081e3d59dbb-Screenshot_2025-10-01_at_9.05.33_AM.png" align="center" width="75%" border={true} />


If the test email doesn't arrive shortly, check your spam or junk folder.

## Resetting templates

Recurly periodically updates its default email templates. These updates won't overwrite your customizations, but you can revert any template to the Recurly default:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the template</h4><p>Click <strong>Customize</strong> on the appropriate email template.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter edit mode</h4><p>Click <strong>Edit</strong> in the "Plain-text Body" or "HTML Body" section.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Reset</h4><p>Scroll to the bottom and click <strong>Reset Template</strong> (shown in red; only visible if you've customized the template). Confirm the reset.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Resetting a template does not affect the HTML Enabled flag, TO address, BCC address, or subject line.</div>
</div>

# Parameters

Email parameters are placeholders that automatically pull in personalized details when an email is generated.

<div class="rp-card">

### Best practices

- Use parameters consistently across templates to avoid confusion
- Only use a parameter where it adds clear context
- Always send a test email after adding new parameters to confirm they render correctly

</div>

## General parameters

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{user_name}}</code></td><td>The customer's name</td></tr>
  <tr><td><code>{{user_email}}</code></td><td>The customer's email address</td></tr>
  <tr><td><code>{{subscription_start_date}}</code></td><td>The start date of the subscription</td></tr>
  <tr><td><code>{{subscription_end_date}}</code></td><td>The end date of the subscription</td></tr>
  <tr><td><code>{{payment_method}}</code></td><td>The payment method chosen by the customer (e.g., credit card, PayPal)</td></tr>
  <tr><td><code>{{payment_due_date}}</code></td><td>The upcoming payment due date</td></tr>
  <tr><td><code>{{past_due_amount}}</code></td><td>The overdue amount, if applicable</td></tr>
  <tr><td><code>{{total_due}}</code></td><td>The total amount due</td></tr>
  <tr><td><code>{{invoice_due_date}}</code></td><td>The deadline for invoice payment</td></tr>
</table>

## Company information

For merchants using Multiple Business Entities, the company value merged into each email parameter reflects the Business Entity applied to the associated invoice, or the overriding Business Entity applied to the customer's account.

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td></tr>
  <tr><td><code>{{company_name}}</code></td></tr>
  <tr><td><code>{{company_email}}</code></td></tr>
  <tr><td><code>{{company_url}}</code></td></tr>
  <tr><td><code>{{company_hosted_account_management_enabled?}}</code></td></tr>
  <tr><td><code>{{company_hosted_account_management_full_access?}}</code></td></tr>
  <tr><td><code>{{company_hosted_account_management_allow_pay_invoice?}}</code></td></tr>
  <tr><td><code>{{company_address1}}</code></td></tr>
  <tr><td><code>{{company_address2}}</code></td></tr>
  <tr><td><code>{{company_city}}</code></td></tr>
  <tr><td><code>{{company_state}}</code></td></tr>
  <tr><td><code>{{company_zip}}</code></td></tr>
  <tr><td><code>{{company_country}}</code></td></tr>
  <tr><td><code>{{company_full_address}}</code></td></tr>
  <tr><td><code>{{company_phone_number}}</code></td></tr>
  <tr><td><code>{{company_vat_number}}</code></td></tr>
  <tr><td><code>{{company_registration_number}}</code></td></tr>
</table>

## Subscription plan details

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{plan_name}}</code></td><td></td></tr>
  <tr><td><code>{{plan_code}}</code></td><td></td></tr>
  <tr><td><code>{{plan_description}}</code></td><td></td></tr>
  <tr><td><code>{{plan_per_interval}}</code></td><td>The billing period interval, e.g., "per month" or "per 2 weeks"</td></tr>
  <tr><td><code>{{plan_trial_interval}}</code></td><td>The trial period, e.g., "1 month" or "2 weeks"</td></tr>
</table>

## Shipping address

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{subscription_has_shipping_address?}}</code></td><td>Returns <code>true</code> if the subscription has a shipping address</td></tr>
  <tr><td><code>{{subscription_shipping_nickname}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_first_name}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_last_name}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_address1}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_address2}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_city}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_state}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_zip}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_country}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_phone}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_email}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_shipping_vat_number}}</code></td><td></td></tr>
  <tr><td><code>{{subscription_full_shipping_address}}</code></td><td>Full shipping address in one string, separated by commas</td></tr>
</table>

## Subscription alteration

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{change_at_renewal?}}</code></td><td>Returns <code>true</code> if the change timeframe is renewal or term_end, or if the timeframe is bill_date and total_billing_cycles is one</td></tr>
  <tr><td><code>{{change_at_bill_date?}}</code></td><td>Returns <code>true</code> if the change timeframe is bill_date AND total_billing_cycles is greater than one</td></tr>
  <tr><td><code>{{change_plan_name}}</code></td><td></td></tr>
  <tr><td><code>{{change_plan_description}}</code></td><td></td></tr>
  <tr><td><code>{{change_plan_per_interval}}</code></td><td></td></tr>
  <tr><td><code>{{change_subscription_quantity}}</code></td><td></td></tr>
  <tr><td><code>{{change_subscription_total_amount}}</code></td><td></td></tr>
  <tr><td><code>{{change_subscription_unit_amount}}</code></td><td></td></tr>
  <tr><td><code>{{change_subscription_add_ons}}</code></td><td></td></tr>
</table>

## Account details

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{account_code}}</code></td><td></td></tr>
  <tr><td><code>{{account_username}}</code></td><td></td></tr>
  <tr><td><code>{{account_first_name}}</code></td><td></td></tr>
  <tr><td><code>{{account_last_name}}</code></td><td></td></tr>
  <tr><td><code>{{account_full_name}}</code></td><td></td></tr>
  <tr><td><code>{{account_company_name}}</code></td><td></td></tr>
  <tr><td><code>{{account_email}}</code></td><td></td></tr>
  <tr><td><code>{{account_full_address}}</code></td><td></td></tr>
  <tr><td><code>{{account_address1}}</code></td><td></td></tr>
  <tr><td><code>{{account_address2}}</code></td><td></td></tr>
  <tr><td><code>{{account_city}}</code></td><td></td></tr>
  <tr><td><code>{{account_state}}</code></td><td>State or province</td></tr>
  <tr><td><code>{{account_zip}}</code></td><td>Zip or postal code</td></tr>
  <tr><td><code>{{account_country}}</code></td><td></td></tr>
  <tr><td><code>{{account_hosted_maintenance_url}}</code></td><td>URL with an embedded authorization token to automatically log in to your hosted account management page. If hosted account management is set to "Guest View Only," this returns the Guest View Edit Billing Info URL. If disabled, this URL returns a 404. To generate the Guest View Edit Billing Info URL correctly, remove the <code>{{#company_hosted_account_management_full_access?}}</code> and <code>{{/company_hosted_account_management_full_access?}}</code> conditional tags from the template</td></tr>
  <tr><td><code>{{coupons}}</code></td><td>Returns coupon information if the account has active coupons</td></tr>
  <tr><td><code>{{account_vat_number}}</code></td><td>Relevant for customers issued manual invoices or when your Tax Settings are configured to use the Account Info address on the invoice</td></tr>
</table>

## Coupon parameters

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{coupon_code}}</code></td><td></td></tr>
  <tr><td><code>{{coupon_name}}</code></td><td></td></tr>
  <tr><td><code>{{coupon_lifetime}}</code></td><td>A string of either: <code>Forever</code>, <code>Single use</code>, or <code>#months</code></td></tr>
  <tr><td><code>{{coupon_discount_percent?}}</code></td><td>Returns <code>true</code> if this coupon is a percentage-off discount</td></tr>
  <tr><td><code>{{coupon_discount_amount?}}</code></td><td>Returns <code>true</code> if this coupon is an amount-off discount</td></tr>
  <tr><td><code>{{coupon_discount_percent}}</code></td><td></td></tr>
  <tr><td><code>{{coupon_discount_amount}}</code></td><td></td></tr>
  <tr><td><code>{{coupon_description}}</code></td><td></td></tr>
</table>

## Billing information

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{billing_payment_method}}</code></td><td>e.g., Credit Card, PayPal, Amazon Pay, ACH</td></tr>
  <tr><td><code>{{billing_cc_type}}</code></td><td>Credit card type, e.g., Visa, Mastercard. Returns nothing if payment was made through PayPal</td></tr>
  <tr><td><code>{{billing_last_four}}</code></td><td>Last four digits of the credit card number</td></tr>
  <tr><td><code>{{billing_first_name}}</code></td><td></td></tr>
  <tr><td><code>{{billing_last_name}}</code></td><td></td></tr>
  <tr><td><code>{{billing_address1}}</code></td><td></td></tr>
  <tr><td><code>{{billing_address2}}</code></td><td></td></tr>
  <tr><td><code>{{billing_city}}</code></td><td></td></tr>
  <tr><td><code>{{billing_state}}</code></td><td>State or province</td></tr>
  <tr><td><code>{{billing_zip}}</code></td><td>Zip or postal code</td></tr>
  <tr><td><code>{{billing_country}}</code></td><td></td></tr>
  <tr><td><code>{{billing_full_address}}</code></td><td></td></tr>
  <tr><td><code>{{billing_ip_address}}</code></td><td>The account's IP address at the time of the last billing info update</td></tr>
  <tr><td><code>{{billing_vat_applicable?}}</code></td><td>Returns <code>true</code> if the account charges VAT</td></tr>
  <tr><td><code>{{billing_vat_number}}</code></td><td>The account's VAT number</td></tr>
  <tr><td><code>{{billing_has_active_mandate}}</code></td><td>Use to conditionally display a sentence containing <code>{{direct_debit_mandate_id}}</code> only when a mandate exists</td></tr>
</table>

## Invoice details

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{invoice_number}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_date}}</code></td><td>Date the invoice was created. May differ from <code>{{transaction_date}}</code> if the initial transaction failed. <code>{{transaction_date}}</code> may be empty if no transaction was required</td></tr>
  <tr><td><code>{{invoice_subtotal}}</code></td><td>Total amount after discounts are applied</td></tr>
  <tr><td><code>{{{invoice_discount_amount}}}</code></td><td>Dollar amount of discount applied to the invoice. Requires three curly braces</td></tr>
  <tr><td><code>{{invoice_total_paid}}</code></td><td>Total amount of payments applied to the invoice</td></tr>
  <tr><td><code>{{invoice_total_due}}</code></td><td>Total amount outstanding on the invoice; zero if paid</td></tr>
  <tr><td><code>{{invoice_line_items}}</code></td><td>Collection of line items on the invoice. Requires a leading pound sign</td></tr>
  <tr><td><code>{{invoice_po_number}}</code></td><td>Invoice PO number for manual invoicing</td></tr>
  <tr><td><code>{{invoice_net_terms}}</code></td><td>Invoice net terms for manual invoicing</td></tr>
  <tr><td><code>{{invoice_has_tax?}}</code></td><td>Returns <code>true</code> if the invoice has taxes applied</td></tr>
  <tr><td><code>{{invoice_tax_amount}}</code></td><td>Total tax amount applied to the invoice</td></tr>
  <tr><td><code>{{invoice_tax_rate}}</code></td><td>Percentage tax rate, e.g., "7.25%"</td></tr>
  <tr><td><code>{{invoice_tax_region}}</code></td><td>The region for which taxes were collected, e.g., "CA" or "DE"</td></tr>
  <tr><td><code>{{invoice_customer_notes}}</code></td><td>Notes from the Customer Notes field on the invoice</td></tr>
  <tr><td><code>{{invoice_terms_and_conditions}}</code></td><td>Notes from the Terms and Conditions field on the invoice</td></tr>
  <tr><td><code>{{invoice_vat_reverse_charge_notes}}</code></td><td>Notes from the VAT Reverse Charge Notes field. Relevant for EU VAT Reverse Charge scenarios only</td></tr>
  <tr><td><code>{{invoice_bill_to_full_name}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_company}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_full_address}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_address1}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_address2}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_city}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_state}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_zip}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_country}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_bill_to_phone}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_full_name}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_company}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_full_address}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_address1}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_address2}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_city}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_state}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_zip}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_country}}</code></td><td></td></tr>
  <tr><td><code>{{invoice_ship_to_phone}}</code></td><td></td></tr>
</table>

## Line item details

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{{line_date}}}</code></td><td>Line item date or date range. Requires three curly braces</td></tr>
  <tr><td><code>{{line_description}}</code></td><td></td></tr>
  <tr><td><code>{{{line_amount}}}</code></td><td>Line item total amount. Requires three curly braces</td></tr>
  <tr><td><code>{{line_amount_is_zero?}}</code></td><td>Returns <code>true</code> if the line item has a zero amount</td></tr>
  <tr><td><code>{{{line_unit_amount}}}</code></td><td>Line item unit amount. Requires three curly braces</td></tr>
  <tr><td><code>{{{line_quantity}}}</code></td><td>Line item quantity. Requires three curly braces</td></tr>
  <tr><td><code>{{line_quantity_is_one?}}</code></td><td>Returns <code>true</code> if the line item quantity is one</td></tr>
  <tr><td><code>{{line_accounting_code}}</code></td><td>Accounting code of the line item's charge</td></tr>
  <tr><td><code>{{line_discount_amount}}</code></td><td>The line item's discount amount, if one exists; otherwise returns zero. Purchase discounts return as positive values; refund discounts return as negative values. Wrap in an <code>invoice_has_discount</code> check to display only when at least one line item has a discount. Not included in any default templates — you'll need to add it manually</td></tr>
  <tr><td><code>{{line_external_sku}}</code></td><td>Used with Item Catalog only. Displays the External SKU of the item sold</td></tr>
  <tr><td><code>{{line_product_code}}</code></td><td>Displays the Plan Code, Add-on Code, or Item Code of the line item</td></tr>
</table>

## Subscription and add-on information

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{subscription_expires_at_with_time}}</code></td><td>Date and time (timezone-adjusted) when the subscription expires, if canceled</td></tr>
  <tr><td><code>{{subscription_canceled_at_with_time}}</code></td><td>Date and time (timezone-adjusted) when the subscription was canceled</td></tr>
  <tr><td><code>{{subscription_trial_ends_at_with_time}}</code></td><td>Date and time (timezone-adjusted) when the current trial period ends</td></tr>
  <tr><td><code>{{subscription_paused_at}}</code></td><td>Date when the current subscription pauses</td></tr>
  <tr><td><code>{{subscription_active?}}</code></td><td>Returns <code>true</code> if the subscription is currently active</td></tr>
  <tr><td><code>{{subscription_quantity}}</code></td><td>Subscription quantity</td></tr>
  <tr><td><code>{{subscription_quantity_is_one?}}</code></td><td>Returns <code>true</code> if the subscription quantity is one</td></tr>
  <tr><td><code>{{{subscription_total_amount}}}</code></td><td>Subscription total renewal amount. Requires three curly braces</td></tr>
  <tr><td><code>{{subscription_unit_amount}}</code></td><td>Subscription per-unit amount</td></tr>
  <tr><td><code>{{subscription_has_trial?}}</code></td><td>Returns <code>true</code> if the subscription has a trial period</td></tr>
  <tr><td><code>{{subscription_has_no_trial?}}</code></td><td>Returns <code>true</code> if the subscription does not have a trial period</td></tr>
  <tr><td><code>{{subscription_trial_without_billing_info?}}</code></td><td>Returns <code>true</code> if billing info is empty and the reason is <code>no_billing_info_reason?</code> = <code>plan_free_trial</code>. Useful for Trial Ending emails on free trials that don't require billing info</td></tr>
  <tr><td><code>{{subscription_expires_at}}</code></td><td>Date when the subscription expires, if canceled</td></tr>
  <tr><td><code>{{subscription_current_period_started_at}}</code></td><td>Date when the current billing period started</td></tr>
  <tr><td><code>{{subscription_current_period_ends_at}}</code></td><td>Date when the current billing period ends, including trial periods</td></tr>
  <tr><td><code>{{subscription_current_period_ends_at_with_time}}</code></td><td>Date and time (UTC) when the current billing period ends, including trial periods</td></tr>
  <tr><td><code>{{subscription_next_payment_date}}</code></td><td>Date when the next payment will be charged</td></tr>
  <tr><td><code>{{subscription_customer_notes}}</code></td><td>Customer notes saved on the subscription. Returns the site's default customer notes if none are set on the subscription</td></tr>
  <tr><td><code>{{subscription_add_ons}}</code></td><td>Lists any add-ons on the subscription</td></tr>
  <tr><td><code>{{add_on_name}}</code></td><td>Within a <code>subscription_add_ons</code> block, returns the name of the add-on</td></tr>
  <tr><td><code>{{add_on_price}}</code></td><td>Within a <code>subscription_add_ons</code> block, returns the price of the add-on. For usage-based add-ons with a percentage pricing model, returns a percentage</td></tr>
  <tr><td><code>{{add_on_usage_based?}}</code></td><td>Returns <code>true</code> if the add-on is usage-based</td></tr>
  <tr><td><code>{{add_on_percentage?}}</code></td><td>Returns <code>true</code> if the add-on is usage-based with a percentage pricing model</td></tr>
  <tr><td><code>{{add_on_measured_unit_display_name}}</code></td><td>Within a <code>subscription_add_ons</code> block, returns the measured unit display name for usage-based add-ons</td></tr>
  <tr><td><code>{{add_on_external_sku}}</code></td><td>Used with Item Catalog only. Displays the External SKU of an item sold as an add-on</td></tr>
  <tr><td><code>{{subscription_total_billing_cycles}}</code></td><td>Number of billing periods in the current subscription term</td></tr>
  <tr><td><code>{{subscription_current_term_started_at}}</code></td><td>Date when the current subscription term started</td></tr>
  <tr><td><code>{{subscription_current_term_ends_at}}</code></td><td>Date when the current subscription term ends. Use instead of <code>current_billing_period_ends_at</code> to accurately reflect the term renewal date</td></tr>
  <tr><td><code>{{subscription_renewal_billing_cycles}}</code></td><td>If the subscription is auto-renewing, the number of billing periods in the next term</td></tr>
  <tr><td><code>{{subscription_term_auto_renew?}}</code></td><td>Returns <code>true</code> if the subscription is configured to auto-renew after the current term</td></tr>
  <tr><td><code>{{subscription_term_balance}}</code></td><td>For subscriptions with multiple billing periods, the remaining amount due</td></tr>
  <tr><td><code>{{subscription_remaining_billing_cycles}}</code></td><td>Remaining billing periods in the current subscription term</td></tr>
  <tr><td><code>{{subscription_total_term_amount}}</code></td><td>Total cost of the subscription, excluding usage charges and setup fees</td></tr>
  <tr><td><code>{{subscription_shipping_cost}}</code></td><td>Amount charged to the customer for shipping</td></tr>
  <tr><td><code>{{subscription_shipping_method}}</code></td><td>Shipping method used on the charge</td></tr>
  <tr><td><code>{{subscription_remaining_pause_cycles}}</code></td><td>Number of pause cycles remaining on the subscription</td></tr>
  <tr><td><code>{{subscription_resume_at}}</code></td><td>Date when a paused subscription will resume</td></tr>
</table>

## Subscriptions list

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{subscriptions_list}}</code></td><td>An array listing all subscriptions for a given invoice. Each subscription contains the same properties as the subscription fields above, plus two additional properties: First? (returns <code>true</code> if first in list) and Last? (returns <code>true</code> if last in list). Useful for checkouts with more than one subscription</td></tr>
  <tr><td><code>{{subscriptions_has_many}}</code></td><td>Returns <code>true</code> if there is more than one subscription in <code>subscriptions_list</code></td></tr>
  <tr><td><code>{{subscriptions_includes_trial}}</code></td><td>Returns <code>true</code> if any subscription in <code>subscriptions_list</code> is a trial</td></tr>
  <tr><td><code>{{subscriptions_includes_active}}</code></td><td>Returns <code>true</code> if any subscription in <code>subscriptions_list</code> is active</td></tr>
  <tr><td><code>{{subscriptions_empty}}</code></td><td>Returns <code>true</code> if <code>subscriptions_list</code> contains no subscriptions</td></tr>
</table>

## Gift card fields

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{gift_card_redemption_code}}</code></td><td>The current redemption code of the gift card</td></tr>
  <tr><td><code>{{gift_card_amount}}</code></td><td>The amount of the gift card</td></tr>
  <tr><td><code>{{gift_card_currency}}</code></td><td>The currency of the gift card amount</td></tr>
  <tr><td><code>{{gift_card_delivery_first_name}}</code></td><td>The first name of the gift recipient</td></tr>
  <tr><td><code>{{gift_card_delivery_last_name}}</code></td><td>The last name of the gift recipient</td></tr>
  <tr><td><code>{{gift_card_personal_message}}</code></td><td>The personal message for the gift recipient</td></tr>
  <tr><td><code>{{gift_card_gifter_name}}</code></td><td>The gifter's name specified for delivery messaging</td></tr>
  <tr><td><code>{{{gift_card_image}}}</code></td><td>The gift card product's image. Requires three curly braces</td></tr>
  <tr><td><code>{{gift_card_delivery_method}}</code></td><td>Whether the gift card delivery method is <code>email</code> or <code>post</code></td></tr>
  <tr><td><code>{{gift_card_delivery_email_address}}</code></td><td>The recipient's email address</td></tr>
  <tr><td><code>{{gift_card_delivery_address1}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_address2}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_city}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_state}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_zip}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_country}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_phone}}</code></td><td></td></tr>
  <tr><td><code>{{gift_card_delivery_deliver_at}}</code></td><td>The future delivery date of the gift card</td></tr>
  <tr><td><code>{{#gift_card_has_personal_message?}}</code></td><td>Returns <code>true</code> if the gift card has a personal message. Useful for hiding the message display if not included at purchase</td></tr>
  <tr><td><code>{{#gift_card_has_gifter_name?}}</code></td><td>Returns <code>true</code> if the gift card has a gifter name. Useful for hiding the display if not included at purchase</td></tr>
  <tr><td><code>{{#gift_card_has_image?}}</code></td><td>Returns <code>true</code> if the gift card product has an image uploaded. Useful for hiding image display if no image exists</td></tr>
  <tr><td><code>{{#gift_card_has_deliver_at?}}</code></td><td>Returns <code>true</code> if the gift card has a future delivery date</td></tr>
  <tr><td><code>{{#gift_card_delivery_city?}}</code></td><td>Returns <code>true</code> if the gift card has a city in the delivery address. Useful for hiding an address comma when no city is present</td></tr>
  <tr><td><code>{{#subscription_is_gift?}}</code></td><td>Returns <code>true</code> if the subscription started with a gift card. Useful with <code>account_has_billing_info?</code> in subscription emails to show special messaging to gift card customers about adding a payment method</td></tr>
  <tr><td><code>{{^account_has_billing_info?}}</code></td><td>Returns <code>true</code> if no billing information exists on the account. Useful nested under <code>subscription_is_gift?</code> to prompt gift card customers to add a payment method</td></tr>
</table>

## Transaction fields

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{transaction_id}}</code></td><td>Transaction UUID: 32 characters, alphanumeric</td></tr>
  <tr><td><code>{{transaction_amount}}</code></td><td>Transaction dollar amount</td></tr>
  <tr><td><code>{{transaction_date}}</code></td><td>Transaction date</td></tr>
  <tr><td><code>{{transaction_date_and_time}}</code></td><td>Transaction date and time (timezone-adjusted)</td></tr>
  <tr><td><code>{{transaction_declined?}}</code></td><td>Returns <code>true</code> if the transaction was declined</td></tr>
  <tr><td><code>{{transaction_success?}}</code></td><td>Returns <code>true</code> if the transaction was successful</td></tr>
  <tr><td><code>{{transaction_voided?}}</code></td><td>Returns <code>true</code> if the transaction was voided</td></tr>
  <tr><td><code>{{#transaction_ach?}}</code></td><td>Returns <code>true</code> if the transaction was paid via ACH</td></tr>
  <tr><td><code>{{transaction_decline_details}}</code></td><td>A brief explanation of why the transaction was declined and how the customer can resolve it</td></tr>
  <tr><td><code>{{transaction_payment_method}}</code></td><td>e.g., Credit Card, PayPal, Amazon Pay, ACH</td></tr>
  <tr><td><code>{{transaction_cc_type}}</code></td><td>Credit card type, e.g., Visa, Mastercard. Returns nothing if payment was made through PayPal</td></tr>
  <tr><td><code>{{transaction_cc_last_four}}</code></td><td>Last four digits of the credit card number</td></tr>
</table>

## Direct debit fields

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{direct_debit_mandate_id}}</code></td><td>Mandate information for direct debit transactions made through GoCardless</td></tr>
  <tr><td><code>{{direct_debit_creditor_identifier}}</code></td><td>Creditor information for direct debit charges through GoCardless</td></tr>
</table>

## Ramp pricing fields

<table class="rp-params">
  <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr>
  <tr><td><code>{{subscription_next_ramp_interval_start_date}}</code></td><td>The date when the customer's next pricing interval begins</td></tr>
  <tr><td><code>{{subscription_next_ramp_interval_price}}</code></td><td>The price that will apply at the start of that next interval</td></tr>
</table>

## Custom fields

Recurly supports email parameters for custom fields on Accounts, Plans, Subscriptions, Items, and Charges. This lets you merge custom field values directly into your email templates.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Custom field names may only contain alphanumeric characters and underscores. Special characters in field names are automatically converted to underscores, and sequences of underscores are reduced to a single underscore.</div>
</div>

<table class="rp-params">
  <tr class="rp-thead-row"><td>Format</td><td>Description</td></tr>
  <tr><td><code>{{account_custom_field_&lt;name&gt;}}</code></td><td>Merges the value of the named custom field from the account object. Example: <code>{{account_custom_field_has_professional_services_engagement}}</code></td></tr>
  <tr><td><code>{{account_custom_field_&lt;name&gt;_&lt;value?&gt;}}</code></td><td>Returns <code>true</code> or <code>false</code> for the named boolean custom field. Example: <code>{{account_custom_field_does_customer_have_professional_services_engagement}}</code></td></tr>
</table>

# FAQs

<Accordion title="How does overriding the trial_ends_at date via API affect the Trial Ending email?">
  If the trial end date is set within three days, the Trial Ending email won't be sent.
</Accordion>

<Accordion title="Does setting a future start date trigger the Renewal Reminder?">
  Yes, if the date is more than two days out.
</Accordion>

<Accordion title="What happens if there's no email address on file for an account?">
  The site's default billing contact email is used. Make sure you're collecting or passing the subscriber's email address to Recurly.
</Accordion>

<Accordion title="Can the Renewal Reminder and Trial Ending emails be configured via API?">
  Currently, these can only be configured through the admin console.
</Accordion>

<Accordion title="Will changes to email templates affect existing subscribers?">
  Yes — as long as the subscriber's subscription meets the criteria for those emails, they'll receive the updated version.
</Accordion>

<Accordion title="Can upcoming invoice or subscription details be included in Renewal Reminder or Trial Ending emails?">
  No. These emails reference data available at the time they're generated.
</Accordion>

<Accordion title="If both the Term Renewal Reminder and the Annual Reminder are enabled and a subscription renews at 12 months, which template gets sent?">
  If both templates are configured to trigger on the same number of days prior, only one will send — the Term Renewal Reminder takes priority. To send both, configure them to different day values.
</Accordion>

<Accordion title="If a merchant enables the Annual Renewal Reminder, will it apply to existing subscriptions?">
  Yes. Once enabled, the Annual Renewal Reminder applies to all subscriptions — both new and existing — for any plans that have the template enabled.
</Accordion>

<br />
