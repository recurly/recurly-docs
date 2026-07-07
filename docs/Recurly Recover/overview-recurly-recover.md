---
title: 'Overview: Recurly Recover'
excerpt: >-
  Use Recurly Recover's standalone retry engine to collect on past-due invoices
  from your existing billing platform — without adopting Recurly for
  subscription management.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Recurly Recover is a standalone retry engine for collecting on past-due invoices without requiring Recurly as your primary billing platform. Submit a failed invoice via the Recovery API, and Recurly automatically creates the account objects, calculates an optimized retry schedule, and manages the entire collection lifecycle until the invoice is paid or the retry window closes.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#setup"><span class="rp-toc-num">4</span>Setup</a>
    <a class="rp-toc-pill" href="#faqs"><span class="rp-toc-num">5</span>FAQs</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>An active Recurly account with an API key generated.</li>
  <li>One or more payment gateways configured in Recurly.</li>
  <li>At least one retry window (dunning campaign) configured in the Recurly Admin UI.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Recurly Recover is designed for merchants who don't use Recurly for subscription management — it's not intended to work alongside Recurly Subscriptions.</li>
  <li>Accounts can only be created via the API, not through the Admin UI.</li>
  <li>Each successful API call creates one account with one invoice. Calling the API again with the same account code returns an error.</li>
</ul>

# Definition

<div class="rp-definition">Recurly Recover is a standalone retry engine that collects on past-due invoices without requiring Recurly as your primary billing platform. Submit a failed invoice via the Recovery API and Recurly automatically creates the necessary account objects, calculates an optimized retry schedule, and manages the entire collection lifecycle until the invoice is paid or the retry window closes.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Works with your stack</strong>
    <span>Use Recurly's retry engine without adopting Recurly for subscription management — it integrates with your existing billing system.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexible retry strategies</strong>
    <span>Assign a different dunning campaign per API request, making it easy to A/B test retry windows and strategies across customer segments.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Fully managed collection</strong>
    <span>Recurly handles the entire retry lifecycle — calculating optimal retry dates, managing payment attempts, and firing webhooks when the journey ends.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Minimal setup</strong>
    <span>No need to configure plans, items, or taxes. Setup is limited to payment gateway, retry window, and API integration.</span>
  </div>
</div>

# Key details

## How Recurly Recover works

1. A payment fails on your billing platform.
2. You pause your internal retry logic for that invoice.
3. You call the Recovery API with account details, payment method tokens, prior attempt history, and the retry window you want Recurly to use.
4. Recurly creates an account, a past-due invoice, and a failed transaction.
5. Recurly calculates the first retry date based on your submission and begins retrying per the assigned retry window.
6. When a retry succeeds or the retry window is exhausted, Recurly fires a webhook. You update the invoice state in your system.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong> Pause your internal retry logic before submitting an invoice to Recurly Recover. Running parallel retries on the same payment method risks double-charging your customer.</div>
</div>

# Setup

## Step 1: Connect your payment gateway

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Payment Gateways</h4><p>In the Recurly Admin UI, go to <strong>Configuration → Payment Gateways</strong> and connect your gateway.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Note the gateway code</h4><p>Each gateway connection is assigned a unique <strong>gateway code</strong>. You'll pass this value in API requests to route transactions to the correct gateway. If you need to route different card types or merchant category codes through separate accounts, you can add multiple connections for the same provider — each gets its own gateway code.</p></div>
  </div>
</div>

## Step 2: Configure a retry window

A retry window defines how many days Recurly will attempt to collect on a past-due invoice. Retry windows are configured using Recurly's dunning campaign feature.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Dunning Management</h4><p>In the Recurly Admin UI, go to <strong>Configuration → Dunning Management</strong> and select <strong>Create campaign</strong> (or edit an existing one).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Configure the campaign</h4><p>Set the campaign name and the total retry window length in days. Set email notifications to <strong>disabled</strong> — Recurly Recover doesn't send dunning emails. Use your own system for customer communication.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save and note the campaign ID</h4><p>Save the campaign and copy the campaign ID — this is the value you'll pass as <code>dunning_campaign_id</code> in API requests.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong> Create a distinct retry window for each strategy you want to test. Since each API request specifies its own <code>dunning_campaign_id</code>, you can easily run A/B tests by assigning different campaign codes at submission time.</div>
</div>

## Step 3: Generate your API key

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Copy your private API key</h4><p>In the Recurly Admin UI, go to <strong>Integrations → API Credentials</strong> and copy your private API key. Use this to authenticate all Recovery API requests.</p></div>
  </div>
</div>

## Step 4: Configure webhooks

Recurly fires webhook events at key points in the retry lifecycle. Configure at least one webhook endpoint so your system can respond when a payment is recovered or a retry window closes.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a webhook endpoint</h4><p>In the Recurly Admin UI, go to <strong>Integrations → Webhooks</strong> and add your endpoint URL.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Subscribe to retry lifecycle events</h4><p>At minimum, subscribe to the following events:</p></div>
  </div>
</div>

| Event                | Fires when                                              |
| -------------------- | ------------------------------------------------------- |
| `successful_payment` | A retry attempt successfully collects payment           |
| `failed_payment`     | A retry attempt fails                                   |
| `new_dunning_event`  | A dunning step fires per the retry window configuration |
| `closed_invoice`     | An invoice is marked as paid or failed                  |

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong> The <code>uuid</code> field in payment webhook events is a <strong>transaction ID</strong>, not an invoice ID. Use <code>GET /transactions/uuid-{uuid}</code> to retrieve the transaction, then follow the invoice relationship if you need invoice details. Do not query <code>/invoices/{uuid}</code> with a transaction ID.</div>
</div>

For full webhook event details, see the [Webhooks documentation](/docs/overview-webhooks).

## Step 5: Submit a failed invoice

Call `POST /invoices/recovery` to submit a failed invoice for collection. A successful request creates a Recurly account, a past-due invoice, and an initial failed transaction — and immediately begins the retry schedule.

### Endpoint

```
POST https://v3.recurly.com/invoices/recovery
```

### Request

```json
{
  "currency": "str",
  "due_at": "2019-08-24T14:15:22Z",
  "po_number": "string",
  "external_recovery_eligible": true,
  "account": {
    "address": {
      "phone": "string",
      "street1": "string",
      "street2": "string",
      "city": "string",
      "region": "string",
      "postal_code": "string",
      "country": "string"
    },
    "billing_infos": [
      {
        "first_name": "string",
        "last_name": "string",
        "company": "string",
        "address": {
          "phone": "string",
          "street1": "string",
          "street2": "string",
          "city": "string",
          "region": "string",
          "postal_code": "string",
          "country": "string"
        },
        "ip_address": "string",
        "gateway_code": "string",
        "primary_payment_method": true,
        "backup_payment_method": true,
        "payment_gateway_references": [
          {
            "token": "string",
            "reference_type": "stripe_confirmation_token"
          }
        ],
        "network_transaction_id": "string",
        "transactions": [
          {
            "gateway_error_code": "string",
            "merchant_advice_code": "st",
            "attempted_collection_date": "2019-08-24T14:15:22Z"
          }
        ]
      }
    ],
    "code": "string",
    "email": "user@example.com",
    "custom_fields": [
      {
        "name": "string",
        "value": "string"
      }
    ],
    "dunning_campaign_id": "string"
  },
  "line_items": [
    {
      "tax": 0,
      "custom_fields": [
        {
          "name": "string",
          "value": "string"
        }
      ],
      "harmonized_system_code": "string",
      "product_code": "string",
      "quantity": 1,
      "description": "string",
      "unit_amount": 0
    }
  ]
}
```

## Step 6: Handle the response

A successful `201` response confirms that Recurly has created the account and started the retry process. Save the `invoice_id` from the response — you'll need it to stop retries later.

The `attempt_next_collection_at` field in the response shows when Recurly will make its first retry attempt.

### Response

```json
{
  "object": "string",
  "charge_invoice": {
    "id": "string",
    "uuid": "string",
    "object": "string",
    "type": "charge",
    "origin": "carryforward_credit",
    "state": "open",
    "account": {
      "id": "string",
      "object": "string",
      "code": "string",
      "email": "user@example.com",
      "first_name": "string",
      "last_name": "string",
      "company": "string",
      "parent_account_id": "string",
      "bill_to": "parent",
      "dunning_campaign_id": "string"
    },
    "billing_info_id": "string",
    "subscription_ids": ["string"],
    "previous_invoice_id": "string",
    "number": "string",
    "collection_method": "automatic",
    "po_number": "string",
    "net_terms": 0,
    "net_terms_type": "net",
    "currency": "str",
    "discount": 0,
    "subtotal": 0,
    "subtotal_after_discount": 0,
    "tax": 0,
    "total": 0,
    "refundable_amount": 0,
    "paid": 0,
    "balance": 0,
    "dunning_campaign_id": "string",
    "due_at": "2019-08-24T14:15:22Z",
    "closed_at": "2019-08-24T14:15:22Z",
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z"
  }
}
```

## Stopping retries

You can stop all future retry attempts on an invoice at any time while it's in a `past_due` state.

**Mark as paid** — use when payment was collected outside of Recurly:

```
PUT https://v3.recurly.com/invoices/{invoice_id}/mark_successful
```

**Mark as failed** — use when you want to abandon collection:

```
PUT https://v3.recurly.com/invoices/{invoice_id}/mark_failed
```

Use the `invoice_id` returned in the original API response. Once marked, Recurly won't make any further retry attempts on that invoice.

## Payment method wallet

When the Wallet feature is enabled, you can designate payment methods as primary or backup in your API request. You can submit multiple payment methods, but only one can be marked as primary.

# FAQs

<Accordion title="Do I need Recurly Subscriptions to use Recurly Recover?">
  No. Recurly Recover is designed as a standalone retry engine for merchants using other billing platforms. Combining Recurly Recover with Recurly Subscriptions is not recommended.
</Accordion>

<Accordion title="What happens when I submit a past-due invoice via the API?">
  Recurly creates an account (without a subscription), a charge invoice, and one or more failed transactions. Billing information is stored and Recurly automatically calculates the next collection attempt date based on your submission.
</Accordion>

<Accordion title="Can I stop retries on a past-due invoice?">
  Yes. While an invoice is in a past-due state, you can cancel all future collection attempts by marking the invoice as failed or paid using the Recurly Invoice API.
</Accordion>

<Accordion title="What happens when the retry window closes without a successful payment?">
  The invoice is marked as failed and a webhook event fires. No further retries are made. You can then handle the outcome in your system — for example, suspending access or triggering a win-back campaign.
</Accordion>

<Accordion title="What if a customer provides a new payment method outside of Recurly?">
  Mark the in-flight Recurly invoice as successful (if payment was collected) or as failed (to stop the current attempt), then submit a new recovery request with the updated payment method token.
</Accordion>

<Accordion title="Can I use Recurly Recover with existing Recurly Subscriptions customers?">
  Recurly Recover is not intended to work alongside Recurly Subscriptions — payment recovery is already included in your Recurly Subscriptions plan. For questions about which solution fits your needs, contact Recurly Sales or email <a href="mailto:support@recurly.com">support@recurly.com</a>.
</Accordion>

<br />
