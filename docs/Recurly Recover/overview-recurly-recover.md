---
title: 'Overview: Recurly Recover'
excerpt: "Retry failed invoice collection independently of your billing platform using \tRecurly Recover — a flexible and intelligent API-driven retry engine that works alongside your existing subscription infrastructure."
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Recurly Recover is a standalone retry engine that lets you collect on past due invoices without using Recurly as your primary subscription management or billing platform. It's purpose-built for merchants who need a dedicated, flexible retry engine that works independently of the rest of Recurly's infrastructure and independently of a merchant’s billing stack. 

When you submit a past-due invoice via the Recovery API, Recurly automatically creates the necessary account objects, calculates an optimized retry schedule, and manages the full collection lifecycle — until the invoice is paid or the retry window is exhausted. 

Note: There is no need to configure plans, items, or taxes. Setup is limited to what's described in the Prerequisites section above.

If you are already a Recurly Subscriptions customer, payment recovery is included in your existing plan — you do not need Recurly Recover. For questions about which solution is right for you, contact Recurly Sales or reach out to [support@recurly.com](mailto:support@recurly.com).

### Prerequisites

* An active Recurly account with an API key generated.
* A supported payment gateway configured — currently Stripe,  Braintree, CommerceHub only.
* At least one retry window (dunning campaign) configured in the Recurly Admin UI.

### Limitations 

* Recurly Recover is intended for merchants using a subscription management and billing solution **other than** Recurly's. It is not intended to be combined with Recurly's full subscription management product. 
* Accounts can only be created via the API — not through the Admin U.
* Each successful API call creates one account with one invoice. Calling the API with an existing account code returns an error.
* Only Stripe, Braintree, and CommerceHub are supported as payment gateways at this time.

### Key benefits 

* Independent of your billing stack: You don't need Recurly for subscription management to use its retry engine. Recurly Recover integrates with your existing infrastructure and is entirely self-serve. 
* Flexible dunning campaign control: Assign specific dunning campaigns per API request, giving you the ability to run A/B tests across different retry windows and strategies.

# Key details

## How it works

1. A payment fails on your platform.
2. You pause your own retry attempts for that invoice.
3. You call the Recovery API (POST /invoices/recovery) with the account details, payment method tokens, prior attempt history, and the retry window you want Recurly to use.
4. Recurly creates an account, a past-due invoice, and the corresponding failed transaction. 
5. Recurly calculates the first retry date based on the attempt history you've provided and begins retrying according to the assigned retry window.
6. When a retry succeeds or the retry window is exhausted, Recurly fires a webhook event and you can update the invoice state in your own system.

**Important**: Pause your own retry attempts before submitting an invoice to Recurly Recover. Running parallel retries against the same payment method risks double-charging your customer.

### Step 1: Connect your payment gateway

Recurly Recover currently supports **Stripe**, **Braintree**, and **CommerceHub**. You must connect at least one gateway before submitting invoices.

1. In the Recurly Admin UI, go to **Configuration → Payment Gateways**
2. Select your gateway and follow the connection steps: 
   1. **Stripe**: Connect via OAuth or enter a restricted API key. If a publishable key is not required for your integration, a placeholder value is accepted. 
   2. **Braintree**: Enter your merchant ID, public key, and private key. 
3. Once connected, note the **gateway code** assigned to each connection. You will pass this value in your API requests to route transactions to the correct gateway.

If you need to route different card types or merchant category codes through separate gateway accounts (for example, separate Stripe connections per MCC), you can add multiple connections for the same gateway provider. Each connection receives a unique gateway code.

For detailed gateway setup instructions, see the [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe), [Braintree](https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd), and [CommerceHub](https://docs.recurly.com/recurly-subscriptions/docs/commerce-hub#configuring-commerce-hub-gateway-in-recurly) documentation.

### Step 2: Configure a retry window

A retry window defines how many days Recurly will attempt to collect on a past due invoice. You can create multiple retry windows and assign one per API request — this makes it straightforward to test different retry strategies across different segments of your invoices.

Retry windows are configured using Recurly's dunning campaign feature.

1. In the Recurly Admin UI, go to **Configuration → Dunning Management**
2. Select **Create campaign** (or edit an existing one)
3. Set the campaign name and the total retry window length in days
4. Set email notifications to disabled — Recurly Recover does not send dunning emails; customer-facing communications should be made through your own system
5. Save the campaign and note the campaign ID — this is the value you will pass as `dunning_campaign_id` in your API requests

**Tip**: Create a distinct retry window for each retry strategy you want to test. Since each API request specifies its own `dunning_campaign_id`, you can run A/B tests across different window lengths by assigning different campaign codes at submission time.

### Step 3: Generate your API key 

1. In the Recurly Admin UI, go to **Integrations → API Credentials**
2. Copy your **private API key** — this is the credential you'll use to authenticate Recovery API requests

### Step 4: Configure webhooks

Recurly fires webhook events at key points in the retry lifecycle. Configure at least one webhook endpoint to receive these events so your system can respond when a payment is recovered or a retry window is exhausted.

1. In the Recurly Admin UI, go to **Integrations → Webhooks**
2. Add your endpoint URL
3. Subscribe to the following events:

| Event                   | Fires when                                              |
| :---------------------- | :------------------------------------------------------ |
| `payment_succeeded`     | A retry attempt successfully collects payment           |
| `payment_failed`        | A retry attempt fails                                   |
| `dunning_event_created` | A dunning step fires per the retry window configuration |
| `invoice_closed`        | An invoice is marked as paid or failed                  |

**Important**: The uuid field in payment webhook events is a **transaction ID,** not an invoice ID. Use `GET /transactions/uuid-{uuid}` to retrieve the transaction, then follow the invoice relationship if you need the invoice details. Do not query `/invoices/{uuid}` with a transaction ID.

For full webhook event details, see the [Webhooks documentation](https://docs.recurly.com/recurly-subscriptions/docs/overview-webhooks).

### Step 5: Submit a failed invoice

Call `POST /invoices/recovery` to submit a failed invoice for collection. A successful request creates a Recurly account, a past-due invoice, and an initial failed transaction — and immediately begins the retry schedule.

Endpoint:` POST https://v3.recurly.com/invoices/recovery`

Request:

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

### Step 6: Handle the response

A successful `201` response confirms that Recurly has created the account and has started the retry process. Save the `invoice_id` from the response — you'll need it if you wish to stop retries later.

Response:

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
    "subscription_ids": [
      "string"
    ],
    "previous_invoice_id": "string",
    "number": "string",
    "collection_method": "automatic",
    "po_number": "string",
    "net_terms": 0,
    "net_terms_type": "net",
    "address": {
      "name_on_account": "string",
      "company": "string",
      "phone": "string",
      "street1": "string",
      "street2": "string",
      "city": "string",
      "region": "string",
      "postal_code": "string",
      "country": "string",
      "geo_code": "string",
      "first_name": "string",
      "last_name": "string"
    },
    "shipping_address": {
      "id": "string",
      "object": "string",
      "account_id": "string",
      "nickname": "string",
      "first_name": "string",
      "last_name": "string",
      "company": "string",
      "email": "string",
      "vat_number": "string",
      "phone": "string",
      "street1": "string",
      "street2": "string",
      "city": "string",
      "region": "string",
      "postal_code": "string",
      "country": "string",
      "geo_code": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z"
    },
    "currency": "str",
    "discount": 0,
    "subtotal": 0,
    "subtotal_after_discount": 0,
    "tax": 0,
    "reference_only_currency_conversion": {
      "currency": "str",
      "subtotal_in_cents": 0,
      "tax_in_cents": 0,
      "rate": "string",
      "source": "string",
      "date": "2019-08-24"
    },
    "total": 0,
    "refundable_amount": 0,
    "paid": 0,
    "balance": 0,
    "tax_info": {
      "type": "string",
      "region": "string",
      "rate": 0,
      "tax_details": [
        {
          "type": "string",
          "region": "string",
          "rate": 0,
          "tax": 0,
          "name": "string",
          "level": "string",
          "billable": true
        }
      ]
    },
    "used_tax_service": true,
    "vat_number": "string",
    "vat_reverse_charge_notes": "string",
    "terms_and_conditions": "string",
    "customer_notes": "string",
    "line_items": [
      {
        "id": "string",
        "object": "string",
        "uuid": "string",
        "type": "charge",
        "item_code": "string",
        "item_id": "string",
        "external_sku": "string",
        "revenue_schedule_type": "at_invoice",
        "state": "invoiced",
        "legacy_category": "applied_credit",
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
        "bill_for_account_id": "string",
        "subscription_id": "string",
        "plan_id": "string",
        "plan_code": "string",
        "add_on_id": "string",
        "add_on_code": "string",
        "invoice_id": "string",
        "invoice_number": "string",
        "previous_line_item_id": "string",
        "original_line_item_invoice_id": "string",
        "origin": "add_on",
        "accounting_code": "string",
        "product_code": "string",
        "credit_reason_code": "general",
        "currency": "str",
        "amount": 0,
        "description": "string",
        "quantity": 1,
        "quantity_decimal": "string",
        "unit_amount": 0,
        "unit_amount_decimal": "string",
        "tax_inclusive": true,
        "subtotal": 0,
        "discount": 0,
        "liability_gl_account_code": "string",
        "revenue_gl_account_code": "string",
        "performance_obligation_id": "string",
        "tax": 0,
        "taxable": true,
        "tax_exempt": true,
        "avalara_transaction_type": 0,
        "avalara_service_type": 0,
        "vertex_transaction_type": "sale",
        "tax_code": "string",
        "harmonized_system_code": "string",
        "tax_info": {
          "type": "string",
          "region": "string",
          "rate": 0,
          "tax_details": [
            {
              "type": "string",
              "region": "string",
              "rate": 0,
              "tax": 0,
              "name": "string",
              "level": "string",
              "billable": true
            }
          ]
        },
        "origin_tax_address_source": "origin",
        "destination_tax_address_source": "destination",
        "proration_rate": 0,
        "refund": true,
        "refunded_quantity": 0,
        "refunded_quantity_decimal": "string",
        "credit_applied": 0,
        "shipping_address": {
          "id": "string",
          "object": "string",
          "account_id": "string",
          "nickname": "string",
          "first_name": "string",
          "last_name": "string",
          "company": "string",
          "email": "string",
          "vat_number": "string",
          "phone": "string",
          "street1": "string",
          "street2": "string",
          "city": "string",
          "region": "string",
          "postal_code": "string",
          "country": "string",
          "geo_code": "string",
          "created_at": "2019-08-24T14:15:22Z",
          "updated_at": "2019-08-24T14:15:22Z"
        },
        "start_date": "2019-08-24T14:15:22Z",
        "end_date": "2019-08-24T14:15:22Z",
        "custom_fields": [
          {
            "name": "string",
            "value": "string",
            "source_record_type": "account",
            "source_record_id": "string"
          }
        ],
        "created_at": "2019-08-24T14:15:22Z",
        "updated_at": "2019-08-24T14:15:22Z"
      }
    ],
    "has_more_line_items": true,
    "transactions": [
      {
        "id": "string",
        "object": "string",
        "uuid": "string",
        "original_transaction_id": "string",
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
        "initiator": "customer",
        "invoice": {
          "id": "string",
          "object": "string",
          "number": "string",
          "business_entity_id": "string",
          "type": "charge",
          "state": "open"
        },
        "merchant_reason_code": "none",
        "voided_by_invoice": {
          "id": "string",
          "object": "string",
          "number": "string",
          "business_entity_id": "string",
          "type": "charge",
          "state": "open"
        },
        "subscription_ids": [
          "string"
        ],
        "type": "authorization",
        "origin": "api",
        "currency": "str",
        "amount": 0,
        "status": "chargeback",
        "success": true,
        "backup_payment_method_used": true,
        "refunded": true,
        "billing_address": {
          "first_name": "string",
          "last_name": "string",
          "phone": "string",
          "street1": "string",
          "street2": "string",
          "city": "string",
          "region": "string",
          "postal_code": "string",
          "country": "string",
          "geo_code": "string"
        },
        "collection_method": "automatic",
        "payment_method": {
          "object": "acss",
          "card_type": "American Express",
          "first_six": "string",
          "last_four": "stri",
          "last_two": "st",
          "exp_month": 0,
          "exp_year": 0,
          "gateway_token": "string",
          "issuing_country": "string",
          "funding_source": "credit",
          "gateway_code": "string",
          "gateway_attributes": {
            "account_reference": "string"
          },
          "card_network_preference": "Bancontact",
          "billing_agreement_id": "string",
          "name_on_account": "string",
          "account_type": "checking",
          "routing_number": "string",
          "routing_number_bank": "string",
          "username": "string"
        },
        "payment_gateway_references": [
          {
            "token": "string",
            "reference_type": "stripe_confirmation_token"
          }
        ],
        "ip_address_v4": "string",
        "ip_address_country": "string",
        "status_code": "string",
        "status_message": "string",
        "customer_message": "string",
        "customer_message_locale": "string",
        "payment_gateway": {
          "id": "string",
          "object": "string",
          "type": "string",
          "name": "string"
        },
        "gateway_message": "string",
        "gateway_reference": "string",
        "gateway_approval_code": "string",
        "gateway_response_code": "string",
        "gateway_response_time": 0,
        "gateway_response_values": {},
        "cvv_check": "D",
        "avs_check": "A",
        "created_at": "2019-08-24T14:15:22Z",
        "updated_at": "2019-08-24T14:15:22Z",
        "voided_at": "2019-08-24T14:15:22Z",
        "collected_at": "2019-08-24T14:15:22Z",
        "action_result": {},
        "vat_number": "string",
        "fraud_info": {
          "object": "string",
          "score": 1,
          "decision": "approve",
          "reference": "string",
          "risk_rules_triggered": [
            {
              "code": "string",
              "message": "string"
            }
          ]
        },
        "next_action": {
          "type": "qr_code",
          "value": "string"
        }
      }
    ],
    "credit_payments": [
      {
        "id": "string",
        "object": "string",
        "uuid": "string",
        "action": "payment",
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
        "applied_to_invoice": {
          "id": "string",
          "object": "string",
          "number": "string",
          "business_entity_id": "string",
          "type": "charge",
          "state": "open"
        },
        "original_invoice": {
          "id": "string",
          "object": "string",
          "number": "string",
          "business_entity_id": "string",
          "type": "charge",
          "state": "open"
        },
        "currency": "str",
        "amount": 0,
        "original_credit_payment_id": "string",
        "refund_transaction": {
          "id": "string",
          "object": "string",
          "uuid": "string",
          "original_transaction_id": "string",
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
          "initiator": "customer",
          "invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "merchant_reason_code": "none",
          "voided_by_invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "subscription_ids": [
            "string"
          ],
          "type": "authorization",
          "origin": "api",
          "currency": "str",
          "amount": 0,
          "status": "chargeback",
          "success": true,
          "backup_payment_method_used": true,
          "refunded": true,
          "billing_address": {
            "first_name": "string",
            "last_name": "string",
            "phone": "string",
            "street1": "string",
            "street2": "string",
            "city": "string",
            "region": "string",
            "postal_code": "string",
            "country": "string",
            "geo_code": "string"
          },
          "collection_method": "automatic",
          "payment_method": {
            "object": "acss",
            "card_type": "American Express",
            "first_six": "string",
            "last_four": "stri",
            "last_two": "st",
            "exp_month": 0,
            "exp_year": 0,
            "gateway_token": "string",
            "issuing_country": "string",
            "funding_source": "credit",
            "gateway_code": "string",
            "gateway_attributes": {
              "account_reference": "string"
            },
            "card_network_preference": "Bancontact",
            "billing_agreement_id": "string",
            "name_on_account": "string",
            "account_type": "checking",
            "routing_number": "string",
            "routing_number_bank": "string",
            "username": "string"
          },
          "payment_gateway_references": [
            {
              "token": "string",
              "reference_type": "stripe_confirmation_token"
            }
          ],
          "ip_address_v4": "string",
          "ip_address_country": "string",
          "status_code": "string",
          "status_message": "string",
          "customer_message": "string",
          "customer_message_locale": "string",
          "payment_gateway": {
            "id": "string",
            "object": "string",
            "type": "string",
            "name": "string"
          },
          "gateway_message": "string",
          "gateway_reference": "string",
          "gateway_approval_code": "string",
          "gateway_response_code": "string",
          "gateway_response_time": 0,
          "gateway_response_values": {},
          "cvv_check": "D",
          "avs_check": "A",
          "created_at": "2019-08-24T14:15:22Z",
          "updated_at": "2019-08-24T14:15:22Z",
          "voided_at": "2019-08-24T14:15:22Z",
          "collected_at": "2019-08-24T14:15:22Z",
          "action_result": {},
          "vat_number": "string",
          "fraud_info": {
            "object": "string",
            "score": 1,
            "decision": "approve",
            "reference": "string",
            "risk_rules_triggered": [
              {}
            ]
          },
          "next_action": {
            "type": "qr_code",
            "value": "string"
          }
        },
        "created_at": "2019-08-24T14:15:22Z",
        "updated_at": "2019-08-24T14:15:22Z",
        "voided_at": "2019-08-24T14:15:22Z"
      }
    ],
    "created_at": "2019-08-24T14:15:22Z",
    "updated_at": "2019-08-24T14:15:22Z",
    "due_at": "2019-08-24T14:15:22Z",
    "closed_at": "2019-08-24T14:15:22Z",
    "dunning_campaign_id": "string",
    "business_entity_id": "string",
    "custom_fields": [
      {
        "name": "string",
        "value": "string",
        "source_record_type": "account",
        "source_record_id": "string"
      }
    ]
  },
  "credit_invoices": [
    {
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
      "subscription_ids": [
        "string"
      ],
      "previous_invoice_id": "string",
      "number": "string",
      "collection_method": "automatic",
      "po_number": "string",
      "net_terms": 0,
      "net_terms_type": "net",
      "address": {
        "name_on_account": "string",
        "company": "string",
        "phone": "string",
        "street1": "string",
        "street2": "string",
        "city": "string",
        "region": "string",
        "postal_code": "string",
        "country": "string",
        "geo_code": "string",
        "first_name": "string",
        "last_name": "string"
      },
      "shipping_address": {
        "id": "string",
        "object": "string",
        "account_id": "string",
        "nickname": "string",
        "first_name": "string",
        "last_name": "string",
        "company": "string",
        "email": "string",
        "vat_number": "string",
        "phone": "string",
        "street1": "string",
        "street2": "string",
        "city": "string",
        "region": "string",
        "postal_code": "string",
        "country": "string",
        "geo_code": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "updated_at": "2019-08-24T14:15:22Z"
      },
      "currency": "str",
      "discount": 0,
      "subtotal": 0,
      "subtotal_after_discount": 0,
      "tax": 0,
      "reference_only_currency_conversion": {
        "currency": "str",
        "subtotal_in_cents": 0,
        "tax_in_cents": 0,
        "rate": "string",
        "source": "string",
        "date": "2019-08-24"
      },
      "total": 0,
      "refundable_amount": 0,
      "paid": 0,
      "balance": 0,
      "tax_info": {
        "type": "string",
        "region": "string",
        "rate": 0,
        "tax_details": [
          {
            "type": "string",
            "region": "string",
            "rate": 0,
            "tax": 0,
            "name": "string",
            "level": "string",
            "billable": true
          }
        ]
      },
      "used_tax_service": true,
      "vat_number": "string",
      "vat_reverse_charge_notes": "string",
      "terms_and_conditions": "string",
      "customer_notes": "string",
      "line_items": [
        {
          "id": "string",
          "object": "string",
          "uuid": "string",
          "type": "charge",
          "item_code": "string",
          "item_id": "string",
          "external_sku": "string",
          "revenue_schedule_type": "at_invoice",
          "state": "invoiced",
          "legacy_category": "applied_credit",
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
          "bill_for_account_id": "string",
          "subscription_id": "string",
          "plan_id": "string",
          "plan_code": "string",
          "add_on_id": "string",
          "add_on_code": "string",
          "invoice_id": "string",
          "invoice_number": "string",
          "previous_line_item_id": "string",
          "original_line_item_invoice_id": "string",
          "origin": "add_on",
          "accounting_code": "string",
          "product_code": "string",
          "credit_reason_code": "general",
          "currency": "str",
          "amount": 0,
          "description": "string",
          "quantity": 1,
          "quantity_decimal": "string",
          "unit_amount": 0,
          "unit_amount_decimal": "string",
          "tax_inclusive": true,
          "subtotal": 0,
          "discount": 0,
          "liability_gl_account_code": "string",
          "revenue_gl_account_code": "string",
          "performance_obligation_id": "string",
          "tax": 0,
          "taxable": true,
          "tax_exempt": true,
          "avalara_transaction_type": 0,
          "avalara_service_type": 0,
          "vertex_transaction_type": "sale",
          "tax_code": "string",
          "harmonized_system_code": "string",
          "tax_info": {
            "type": "string",
            "region": "string",
            "rate": 0,
            "tax_details": [
              {}
            ]
          },
          "origin_tax_address_source": "origin",
          "destination_tax_address_source": "destination",
          "proration_rate": 0,
          "refund": true,
          "refunded_quantity": 0,
          "refunded_quantity_decimal": "string",
          "credit_applied": 0,
          "shipping_address": {
            "id": "string",
            "object": "string",
            "account_id": "string",
            "nickname": "string",
            "first_name": "string",
            "last_name": "string",
            "company": "string",
            "email": "string",
            "vat_number": "string",
            "phone": "string",
            "street1": "string",
            "street2": "string",
            "city": "string",
            "region": "string",
            "postal_code": "string",
            "country": "string",
            "geo_code": "string",
            "created_at": "2019-08-24T14:15:22Z",
            "updated_at": "2019-08-24T14:15:22Z"
          },
          "start_date": "2019-08-24T14:15:22Z",
          "end_date": "2019-08-24T14:15:22Z",
          "custom_fields": [
            {
              "name": "string",
              "value": "string",
              "source_record_type": "account",
              "source_record_id": "string"
            }
          ],
          "created_at": "2019-08-24T14:15:22Z",
          "updated_at": "2019-08-24T14:15:22Z"
        }
      ],
      "has_more_line_items": true,
      "transactions": [
        {
          "id": "string",
          "object": "string",
          "uuid": "string",
          "original_transaction_id": "string",
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
          "initiator": "customer",
          "invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "merchant_reason_code": "none",
          "voided_by_invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "subscription_ids": [
            "string"
          ],
          "type": "authorization",
          "origin": "api",
          "currency": "str",
          "amount": 0,
          "status": "chargeback",
          "success": true,
          "backup_payment_method_used": true,
          "refunded": true,
          "billing_address": {
            "first_name": "string",
            "last_name": "string",
            "phone": "string",
            "street1": "string",
            "street2": "string",
            "city": "string",
            "region": "string",
            "postal_code": "string",
            "country": "string",
            "geo_code": "string"
          },
          "collection_method": "automatic",
          "payment_method": {
            "object": "acss",
            "card_type": "American Express",
            "first_six": "string",
            "last_four": "stri",
            "last_two": "st",
            "exp_month": 0,
            "exp_year": 0,
            "gateway_token": "string",
            "issuing_country": "string",
            "funding_source": "credit",
            "gateway_code": "string",
            "gateway_attributes": {
              "account_reference": "string"
            },
            "card_network_preference": "Bancontact",
            "billing_agreement_id": "string",
            "name_on_account": "string",
            "account_type": "checking",
            "routing_number": "string",
            "routing_number_bank": "string",
            "username": "string"
          },
          "payment_gateway_references": [
            {
              "token": "string",
              "reference_type": "stripe_confirmation_token"
            }
          ],
          "ip_address_v4": "string",
          "ip_address_country": "string",
          "status_code": "string",
          "status_message": "string",
          "customer_message": "string",
          "customer_message_locale": "string",
          "payment_gateway": {
            "id": "string",
            "object": "string",
            "type": "string",
            "name": "string"
          },
          "gateway_message": "string",
          "gateway_reference": "string",
          "gateway_approval_code": "string",
          "gateway_response_code": "string",
          "gateway_response_time": 0,
          "gateway_response_values": {},
          "cvv_check": "D",
          "avs_check": "A",
          "created_at": "2019-08-24T14:15:22Z",
          "updated_at": "2019-08-24T14:15:22Z",
          "voided_at": "2019-08-24T14:15:22Z",
          "collected_at": "2019-08-24T14:15:22Z",
          "action_result": {},
          "vat_number": "string",
          "fraud_info": {
            "object": "string",
            "score": 1,
            "decision": "approve",
            "reference": "string",
            "risk_rules_triggered": [
              {}
            ]
          },
          "next_action": {
            "type": "qr_code",
            "value": "string"
          }
        }
      ],
      "credit_payments": [
        {
          "id": "string",
          "object": "string",
          "uuid": "string",
          "action": "payment",
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
          "applied_to_invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "original_invoice": {
            "id": "string",
            "object": "string",
            "number": "string",
            "business_entity_id": "string",
            "type": "charge",
            "state": "open"
          },
          "currency": "str",
          "amount": 0,
          "original_credit_payment_id": "string",
          "refund_transaction": {
            "id": "string",
            "object": "string",
            "uuid": "string",
            "original_transaction_id": "string",
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
            "initiator": "customer",
            "invoice": {
              "id": "string",
              "object": "string",
              "number": "string",
              "business_entity_id": "string",
              "type": "charge",
              "state": "open"
            },
            "merchant_reason_code": "none",
            "voided_by_invoice": {
              "id": "string",
              "object": "string",
              "number": "string",
              "business_entity_id": "string",
              "type": "charge",
              "state": "open"
            },
            "subscription_ids": [
              "string"
            ],
            "type": "authorization",
            "origin": "api",
            "currency": "str",
            "amount": 0,
            "status": "chargeback",
            "success": true,
            "backup_payment_method_used": true,
            "refunded": true,
            "billing_address": {
              "first_name": "string",
              "last_name": "string",
              "phone": "string",
              "street1": "string",
              "street2": "string",
              "city": "string",
              "region": "string",
              "postal_code": "string",
              "country": "string",
              "geo_code": "string"
            },
            "collection_method": "automatic",
            "payment_method": {
              "object": "acss",
              "card_type": "American Express",
              "first_six": "string",
              "last_four": "stri",
              "last_two": "st",
              "exp_month": 0,
              "exp_year": 0,
              "gateway_token": "string",
              "issuing_country": "string",
              "funding_source": "credit",
              "gateway_code": "string",
              "gateway_attributes": {},
              "card_network_preference": "Bancontact",
              "billing_agreement_id": "string",
              "name_on_account": "string",
              "account_type": "checking",
              "routing_number": "string",
              "routing_number_bank": "string",
              "username": "string"
            },
            "payment_gateway_references": [
              {}
            ],
            "ip_address_v4": "string",
            "ip_address_country": "string",
            "status_code": "string",
            "status_message": "string",
            "customer_message": "string",
            "customer_message_locale": "string",
            "payment_gateway": {
              "id": "string",
              "object": "string",
              "type": "string",
              "name": "string"
            },
            "gateway_message": "string",
            "gateway_reference": "string",
            "gateway_approval_code": "string",
            "gateway_response_code": "string",
            "gateway_response_time": 0,
            "gateway_response_values": {},
            "cvv_check": "D",
            "avs_check": "A",
            "created_at": "2019-08-24T14:15:22Z",
            "updated_at": "2019-08-24T14:15:22Z",
            "voided_at": "2019-08-24T14:15:22Z",
            "collected_at": "2019-08-24T14:15:22Z",
            "action_result": {},
            "vat_number": "string",
            "fraud_info": {
              "object": "string",
              "score": 1,
              "decision": "approve",
              "reference": "string",
              "risk_rules_triggered": [
                null
              ]
            },
            "next_action": {
              "type": "qr_code",
              "value": "string"
            }
          },
          "created_at": "2019-08-24T14:15:22Z",
          "updated_at": "2019-08-24T14:15:22Z",
          "voided_at": "2019-08-24T14:15:22Z"
        }
      ],
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z",
      "due_at": "2019-08-24T14:15:22Z",
      "closed_at": "2019-08-24T14:15:22Z",
      "dunning_campaign_id": "string",
      "business_entity_id": "string",
      "custom_fields": [
        {
          "name": "string",
          "value": "string",
          "source_record_type": "account",
          "source_record_id": "string"
        }
      ]
    }
  ],
  "verification_transactions": [
    {
      "id": "string",
      "object": "string",
      "uuid": "string",
      "original_transaction_id": "string",
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
      "initiator": "customer",
      "invoice": {
        "id": "string",
        "object": "string",
        "number": "string",
        "business_entity_id": "string",
        "type": "charge",
        "state": "open"
      },
      "merchant_reason_code": "none",
      "voided_by_invoice": {
        "id": "string",
        "object": "string",
        "number": "string",
        "business_entity_id": "string",
        "type": "charge",
        "state": "open"
      },
      "subscription_ids": [
        "string"
      ],
      "type": "authorization",
      "origin": "api",
      "currency": "str",
      "amount": 0,
      "status": "chargeback",
      "success": true,
      "backup_payment_method_used": true,
      "refunded": true,
      "billing_address": {
        "first_name": "string",
        "last_name": "string",
        "phone": "string",
        "street1": "string",
        "street2": "string",
        "city": "string",
        "region": "string",
        "postal_code": "string",
        "country": "string",
        "geo_code": "string"
      },
      "collection_method": "automatic",
      "payment_method": {
        "object": "acss",
        "card_type": "American Express",
        "first_six": "string",
        "last_four": "stri",
        "last_two": "st",
        "exp_month": 0,
        "exp_year": 0,
        "gateway_token": "string",
        "issuing_country": "string",
        "funding_source": "credit",
        "gateway_code": "string",
        "gateway_attributes": {
          "account_reference": "string"
        },
        "card_network_preference": "Bancontact",
        "billing_agreement_id": "string",
        "name_on_account": "string",
        "account_type": "checking",
        "routing_number": "string",
        "routing_number_bank": "string",
        "username": "string"
      },
      "payment_gateway_references": [
        {
          "token": "string",
          "reference_type": "stripe_confirmation_token"
        }
      ],
      "ip_address_v4": "string",
      "ip_address_country": "string",
      "status_code": "string",
      "status_message": "string",
      "customer_message": "string",
      "customer_message_locale": "string",
      "payment_gateway": {
        "id": "string",
        "object": "string",
        "type": "string",
        "name": "string"
      },
      "gateway_message": "string",
      "gateway_reference": "string",
      "gateway_approval_code": "string",
      "gateway_response_code": "string",
      "gateway_response_time": 0,
      "gateway_response_values": {},
      "cvv_check": "D",
      "avs_check": "A",
      "created_at": "2019-08-24T14:15:22Z",
      "updated_at": "2019-08-24T14:15:22Z",
      "voided_at": "2019-08-24T14:15:22Z",
      "collected_at": "2019-08-24T14:15:22Z",
      "action_result": {},
      "vat_number": "string",
      "fraud_info": {
        "object": "string",
        "score": 1,
        "decision": "approve",
        "reference": "string",
        "risk_rules_triggered": [
          {
            "code": "string",
            "message": "string"
          }
        ]
      },
      "next_action": {
        "type": "qr_code",
        "value": "string"
      }
    }
  ]
}
```

The `attempt_next_collection_at` field shows when Recurly will make its first retry attempt.

### Stopping retries

You can stop all future retry attempts on an invoice at any time while it is in a `past_due` state.

**Mark as paid** (use when payment was collected outside of Recurly):

`PUT https://v3.recurly.com/invoices/\{invoice_id}/mark_successful`

**Mark as failed** (use when you want to abandon collection):

`PUT https://v3.recurly.com/invoices/\{invoice_id}/mark_failed`

Use the `invoice_id` returned in the original API response. Once marked, Recurly will not make any further retry attempts on that invoice.

## Wallet

When the Wallet feature is enabled, payment methods are designated as primary or backup based on your specifications in the API request. Multiple payment methods can be submitted, but only one can be marked as primary.

## FAQs

Do I need to use Recurly as my subscription management platform to use Recurly Recover? No. Recurly Recover is designed to work independently — you can retry failed invoice collection even if Recurly isn't your subscription management or billing platform. We don't recommend combining Recurly Recover with Recurly's full subscription management product at this time. What happens when a past due invoice is submitted via the API? Recurly creates an account (without a subscription), along with a charge, a past due invoice, and one or more failed transactions. Billing information is stored on the account, and Recurly automatically calculates the next collection attempt date based on the data in the request. Can I stop retry attempts on a past due invoice? Yes. While an invoice is in a Past Due state, you can cancel all future collection attempts at any time by marking the invoice as Failed or Paid using the Recurly Invoice API.

What happens when the retry window is exhausted without a successful payment?

The invoice is marked as failed and a webhook event fires. No further retry attempts are made. You can then handle the outcome in your own system — for example, cancelling the subscriber's access or triggering a win-back flow.

What if a customer updates their payment method in my system?

If a customer provides a new payment method externally, mark the in-flight Recurly invoice as successful (if payment was collected) or as failed (to abandon the current attempt), then submit a new recovery request with the updated payment method token.