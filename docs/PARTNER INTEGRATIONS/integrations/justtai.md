---
title: Justt.AI
deprecated: false
hidden: false
metadata:
  robots: index
---
## Prerequisites

- You must have an active Justt.ai account
- Your Recurly site must be using one of the supported payment gateways: Stripe, Braintree, PayPal Complete, Adyen
- You must have the Justt.ai and Chargeback Management feature flags enabled on your Recurly site (contact Recurly Support to request access)
- You must have a Recurly API key available to share with Justt during setup

## Limitations

- Merchants can only use one chargeback management system at a time — either Recurly's native chargeback handling or Justt.  Once Justt is enabled, Recurly will stop processing gateway chargeback events for supported gateways
- Only credit card chargebacks are processed; non-credit card disputes (such as ACH) are not actioned
- Each merchant site can have one active Justt configuration

## Definition

The Justt.ai integration connects your Recurly account to Justt's AI-powered chargeback dispute platform. Once set up, Justt sends chargeback events to Recurly via webhooks, and Recurly automatically applies the subscription and invoice actions you've configured — such as issuing refunds, pausing subscriptions, or expiring subscriptions — based on the outcome of each dispute.

### Key Benefits

- **Automated chargeback response:** When Justt resolves a dispute, Recurly takes the action you've specified (refund, pause, or expire) without any manual intervention, so your team spends less time on chargeback admin.
- **Full visibility in one place:** A dedicated chargeback index page in Recurly shows every Justt dispute event, its status, and the associated account and invoice — giving you a real-time snapshot of your chargeback activity.
- **Self-serve control:** You can connect, disconnect, and re-enable the Justt integration directly in the Recurly UI, without needing to contact support.

## Key details

### How the integration works

The Justt.ai integration follows this general setup flow:

1. **Create a Recurly API key** — In Recurly, create a dedicated read-only API key and label it for Justt.ai. You'll find the Justt.ai option in the application dropdown when creating a new private API key.
2. **Share the key with Justt** — Log in to Justt and paste the Recurly API key. Justt will use it to fetch Recurly transaction data for chargeback enrichment.
3. **Configure your webhook URL in Justt** — Recurly provides a merchant-specific webhook URL (formatted as [https://callbacks.recurly.com/justt/](https://callbacks.recurly.com/justt/)\<YOUR\_SUBDOMAIN>). Enter this URL in Justt's webhook settings.
4. **Enter your Justt Merchant ID in Recurly** — In the Recurly UI, navigate to Integrations > Justt.ai and enter your Justt Merchant ID. This links incoming webhooks to your site.
5. **Configure your chargeback actions in Recurly** — In the Recurly UI, navigate to Invoice Templates > Invoice Settings and choose what Recurly should do when it receives a chargeback event (see "Chargeback actions" below).

### Supported gateways

The Justt integration processes chargebacks from the following payment service providers (PSPs):

- Stripe
- Braintree
- PayPal Complete
- Adyen

### Chargeback actions

Recurly can be configured to take the following actions when a chargeback dispute is resolved as lost (meaning the subscriber wins the dispute):

- **Create a refund** — Recurly issues a refund invoice against the original transaction
- **Expire the subscription** — Recurly immediately expires the associated subscription
- **Manually process chargebacks** - Recurly will only send a webhook notification&#x20;

Chargeback events with statuses other than lost — such as pending, won, or under\_review — are recorded in the chargeback index for visibility but do not trigger subscription actions.

### Webhook events

Recurly listens for two webhook event types from Justt:

`chargeback.created` — fired when a new chargeback dispute is opened<br />`chargeback.updated` — fired when the status of an existing dispute changes

These events are processed independently and will create a new record in the Justt chargeback index table

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

**What happens to my existing chargebacks if I disable the integration?**<br />Disabling the integration stops the processing of new webhooks from Justt. Existing chargeback records in Recurly are not deleted and remain visible on the index page. If there are pending chargebacks, those will continue to be processed between the banks and gateways, however, updates on those chargebacks will not be persisted in Recurly.

**What does "lost" mean in the context of a Justt chargeback?**<br />A chargeback with a `lost` status means the subscriber's dispute was upheld by their card issuer — the merchant lost the case. This is the status that triggers Recurly to take action (refund and/or expire) based on your configured settings.

**Why do I need to recreate my API key when I re-enable the integration?**
When you disable the Justt integration, Recurly invalidates the API key that was previously shared with Justt. This is a security measure to ensure that a dormant key can't be used to access your Recurly data while the integration is inactive. When you re-enable, you'll need to create a fresh key and update it in your Justt account settings.

**What's the difference between the "Created" date and the "Posting Date" on the chargeback index?**
The "Created" date reflects when Recurly received and recorded the chargeback event. The "Posting Date" is the date the chargeback was formally reported to Justt by the card network — this date comes directly from Justt's webhook payload and may be earlier than the created date in Recurly.
