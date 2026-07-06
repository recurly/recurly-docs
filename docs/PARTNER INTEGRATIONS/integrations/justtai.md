---
title: Justt.AI
deprecated: false
hidden: false
metadata:
  robots: index
---
## Required plan

This feature may not be included in the Starter or Pro plans. If you are interested, please contact Recurly Sales to discuss upgrade options.

## Prerequisites

You must have an active Justt.ai account
Your Recurly site must be using one of the supported payment gateways: Stripe, Braintree, PayPal Complete, Adyen, Cybersource, Ebanx, CommerceHub by Fiserv, Vantiv, Worldpay, or Chase Paymentech Orbital
You must have the Justt.ai feature flag enabled on your Recurly site (contact Recurly Support to request access)
You must have a Recurly API key available to share with Justt during setup

## Limitations

Merchants can only use one chargeback management system at a time — either Recurly's native chargeback handling or Justt. Once Justt is enabled, Recurly will stop processing gateway chargeback events for supported gateways
Only credit card chargebacks are processed; non-credit card disputes (such as ACH) are acknowledged but not actioned
Each merchant site can have one active Justt configuration

## Definition

The Justt.ai integration connects your Recurly account to Justt's AI-powered chargeback dispute platform. Once set up, Justt sends chargeback events to Recurly via webhooks, and Recurly automatically applies the subscription and invoice actions you've configured — such as issuing refunds, pausing subscriptions, or expiring subscriptions — based on the outcome of each dispute.

## Key benefits

Automated chargeback response: When Justt resolves a dispute, Recurly takes the action you've specified (refund, pause, or expire) without any manual intervention, so your team spends less time on chargeback admin.
Full visibility in one place: A dedicated chargeback index page in Recurly shows every Justt dispute event, its status, and the associated account and invoice — giving you a real-time snapshot of your chargeback activity.
Self-serve control: You can connect, disconnect, and re-enable the Justt integration directly in the Recurly UI, without needing to contact support.

## Key details

### How the integration works

The Justt.ai integration follows this general setup flow:

**Create a Recurly API key** — In Recurly, create a dedicated read-only API key and label it for Justt.ai. You'll find the Justt.ai option in the application dropdown when creating a new private API key.
**Share the key with Justt** — Log in to Justt and paste the Recurly API key. Justt will use it to fetch Recurly transaction data for chargeback enrichment.
**Configure your webhook URL in Justt** — Recurly provides a merchant-specific webhook URL (formatted as [https://callbacks.recurly.com/justt/](https://callbacks.recurly.com/justt/)\<YOUR\_SUBDOMAIN>). Enter this URL in Justt's webhook settings.
**Enter your Justt Merchant ID in Recurly** — In the Recurly UI, navigate to Integrations > Justt.ai and enter your Justt Merchant ID. This links incoming webhooks to your site.
**Configure your chargeback actions in Recurly** — On the same page, choose what Recurly should do when it receives a chargeback event (see "Chargeback actions" below).

### Supported gateways

The Justt integration processes chargebacks from the following payment service providers (PSPs):

- Stripe
- Braintree
- PayPal Complete
- Adyen<br />

Webhooks from PSPs not on this list are acknowledged but not actioned.

### Chargeback actions

Recurly can be configured to take the following actions when a chargeback dispute is resolved as lost (meaning the subscriber wins the dispute):

- **Create a refund** — Recurly issues a refund invoice against the original transaction
- **Pause the subscription** — Recurly pauses the associated subscription
- **Expire the subscription** — Recurly immediately expires the associated subscription

For fraud and service-related chargebacks (as determined by the reason code and card scheme, or Justt's reasonGroup field when Recurly can't make its own determination), Recurly will expire the associated subscription immediately when the dispute is lost.

Chargeback events with statuses other than lost — such as pending, won, or under\_review — are recorded in the chargeback index for visibility but do not trigger subscription actions.

### Webhook events

Recurly listens for two webhook event types from Justt:

`chargeback.created` — fired when a new chargeback dispute is opened<br />`chargeback.updated` — fired when the status of an existing dispute changes

Recurly processes each event independently. If a webhook doesn't include enough data to match a Recurly transaction (for example, no transaction ID is present), the event is stored in a pending state and reconciled through a nightly sync job that queries Justt's chargeback API directly.

### Chargeback index page

Once the integration is active, you'll see a chargeback index table on the Justt integration page under **Integrations > Justt.ai**. The table displays:

- Account (subscriber display name)
- Invoice number
- Chargeback ID
- Status
- Created date
- Posting date (the date the chargeback was reported to Justt, which may differ from when Recurly received the webhook)

The table is sortable by account, invoice, and date columns. You can also search by keyword or phrase across non-date columns to quickly locate specific chargebacks.

### Refund transactions

When Recurly creates a refund as a result of a Justt chargeback, the refund transaction will display "Processed by Justt" in the transaction summary. The transaction detail page also shows the reason code, chargeback reason message, and merchant reference from the original Justt webhook payload.

### Disabling and re-enabling the integration

You can disable the Justt integration at any time from the Justt integration page in Recurly. Disabling it stops Recurly from processing new Justt webhooks. If you want to remove the integration entirely, contact Recurly Support to turn off the feature flag.

To re-enable a previously disabled integration, click the Re-enable button on the integration page. Note that re-enabling the integration will require you to recreate your Recurly API key and share it with Justt again, as the previous key is invalidated on disable.

## FAQs

**Can I use Recurly's native chargeback handling and Justt at the same time?**
No. Recurly can only use one chargeback management system per site at a time. When the Justt integration is active, Recurly stops processing gateway-level chargeback events and relies solely on Justt webhooks instead.

**What happens if Justt sends a webhook for a transaction Recurly can't find?**
If the initial transaction lookup fails (for example, if the webhook doesn't include a Recurly transaction ID), Recurly stores the event in a pending state. A nightly reconciliation job queries Justt's chargeback API for the past 24 hours and attempts to match any unresolved events. Once a match is found, the chargeback is processed normally.

**What happens to my existing chargebacks if I disable the integration?**
Disabling the integration stops the processing of new webhooks from Justt. Existing chargeback records in Recurly are not deleted and remain visible on the index page. Recurly will not re-process those chargebacks through native gateway handling.

**Does the Justt integration support multi-currency merchants?**
Yes. Recurly uses the transaction's own currency when creating chargeback records, regardless of what currency the Justt webhook payload includes.

**What card networks are supported for fraud and service reason code mapping?**
Recurly maps fraud and service reason codes for Visa, Mastercard, American Express, Discover, Diners Club, Elo, JCB, and other major card networks. When a reason code and card scheme can't be mapped internally, Recurly falls back to Justt's reasonGroup field (fraud, service, processingError, or general) to determine the appropriate subscription action.
