---
title: Refund
excerpt: >-
  Refund invoices or transactions from the UI or API—full, partial, or by line
  item.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Use refunds to return money to a customer from a transaction or invoice. In Recurly Subscriptions, you can refund the entire amount, a specific amount, or selected line items—with options to prorate subscription charges and control how credits are applied.

### Required plan

These features are available to all customers on any Recurly subscription plan.

### Prerequisites & limitations

* **Prerequisites:** Staff access to **Invoices** and **Transactions** in the Recurly Admin UI, or API credentials with scope to refund invoices.
* **Limitations:**
  * Refunds are always issued back to the **original payment method** (e.g., the same card or bank account for ACH). They are also tied to the original gateway used for the authorization or payment and cannot presently be routed to a different payment method or gateway.
  * **Unsettled** transactions can be **[voided](https://docs.recurly.com/recurly-subscriptions/docs/void-transaction#/)** instead of **refunded**. Some gateways also allow refunds against unsettled transactions, but this is not recommended.
  * **[Voided](https://docs.recurly.com/recurly-subscriptions/docs/void-transaction#/)** and **[Uncaptured Authorization](https://docs.recurly.com/recurly-subscriptions/update/docs/auth-and-capture#/)**transactions cannot be refunded.
  * Percentage refunds on invoices require the **Credit Memos** feature flag to be enabled.

# Definition

A refund reverses all or part of a previously collected charge. In Recurly, refunding an invoice or its underlying transaction creates a **refund invoice** and a **refund transaction**, and can optionally return account credit before issuing money back.

# Key benefits

* **Work from one place:** Refund from the invoice, the transaction, or via API.
* **Fine-grained control:** Refund by **full amount**, **specific amount** (dollar or percentage of an invoice), or **selected line items**.
* **Accurate billing math:** Respect proration, taxes, discounts, and quantities on the refund preview.
* **Consistent accounting:** Recurly generates refund documents for audit and reconciliation.

# Key details

## Refund from the Admin UI

1. **Open** the customer’s account and **select** the original **transaction** (in **Transactions**) or the **invoice** (in **Invoices**).
2. If you chose a transaction, **go** to **Transaction details** and **select** **Refund transaction**.
   If you chose an invoice, **go** to **Invoice details** and **select** **Refund invoice**.
3. **Choose** what to refund:
   * **Line items:** **Select** specific charge lines; **optionally prorate** subscription charges or **select quantities**.
   * **Specific amount:** **Click** **Refund a partial item or specific amount?** and **enter** a custom amount (cannot exceed the original).
   * **Unsettled** transactions: only full refund (void) is available.
4. If the invoice contains **credit line items** and you’re doing a **partial refund**, **choose** how to apply value:
   * **Credit first (default):** Return credit to the account first, then create a transaction for any remaining amount.
   * **Transaction first:** Issue money back to the customer first, then return any remaining amount as account credit.
     **Tip:** **Change** this using the radio buttons at the top of the page.
5. **Click** **Preview refund** to review discounts, taxes, credits, and totals.
6. **Click** **Refund charges** to complete. Recurly **creates** a refund invoice and a refund transaction.

## Refund types at a glance

| Type       | What it does                                                   | Typical use                                             |
| ---------- | -------------------------------------------------------------- | ------------------------------------------------------- |
| Full       | Returns the entire original charge.                            | Billing error or immediate cancellation.                |
| Amount     | Returns an exact currency amount.                              | Goodwill or partial service issue.                      |
| Line items | Returns selected lines with optional proration and quantities. | Plan swaps, partial periods, or item-level adjustments. |

## Credit handling options

| Option                     | Result                                                                        |
| -------------------------- | ----------------------------------------------------------------------------- |
| **Credit first** (default) | Refund consumes/returns account credit before sending money back.             |
| **Transaction first**      | Refund sends money back first; any remainder becomes/consumes account credit. |

## How taxes, discounts, and proration work

* **Preview** shows calculated **taxes**, **discounts**, and **proration** impacts based on what you selected to refund.
* **Line-item refunds** respect original taxability and discount allocation.
* **Proration** applies to subscription charges when you select it on the refund screen.

## Refund via API

### Python example (refund by amount)

```python
import recurly

client = recurly.Client(api_key="YOUR_API_KEY")
invoice_id = "YOUR_INVOICE_ID"  # e.g., "e28zov4fw0v2" or "number-1000" or "number-TEST-FR1001"

try:
    refund_body = {
        "type": "amount",   # "amount" | "percentage" | "line_items"
        "amount": 10.00
    }
    invoice = client.refund_invoice(invoice_id, body=refund_body)
    print(f"Invoice {invoice_id} refunded successfully.")
except recurly.errors.NotFoundError as e:
    print(f"Error: Invoice not found: {e}")
except recurly.errors.ValidationError as e:
    print(f"Error: Validation error: {e}")
except recurly.errors.ApiError as e:
    print(f"Error: API error: {e}")
```

### Request fields

| Field        | Type    |                 Required | Description                                                                |
| ------------ | ------- | -----------------------: | -------------------------------------------------------------------------- |
| `type`       | string  |                        ✓ | Refund mode: `"amount"`, `"percentage"`, or `"line_items"`.                |
| `amount`     | number  |     when `type="amount"` | Currency amount to refund.                                                 |
| `percentage` | number  | when `type="percentage"` | Percent of the invoice total to refund. Requires **Credit Memos** enabled. |
| `line_items` | array   | when `type="line_items"` | Specific lines to refund (IDs/quantities as applicable).                   |
| `prorate`    | boolean |                 optional | Apply proration to subscription lines when refunding line items.           |
| `quantity`   | integer |                 optional | Quantity to refund for a given line item (when supported).                 |

> **Invoice identifiers:** You may pass the invoice UUID (e.g., `e28zov4fw0v2`) or the invoice **number** using `number-` (e.g., `number-1000`, `number-TEST-FR1001`).

## What gets created

* A **refund invoice** reflecting the reversal (with taxes/discounts allocation).
* A **refund transaction** against the **original payment method**.

## Troubleshooting

* **Can’t refund—transaction unsettled:** The only option is a **void** (full refund) until the gateway settles the charge.
* **Gateway/bank blocked refund:** You may be **outside the gateway’s window** (often 30–60 days) or the payment method is no longer able to receive the refund. Consider issuing an **offline credit** outside the processor and record adjustments in Recurly.
* **Validation errors (API):** Confirm `type` and required fields. For line-item refunds, ensure line IDs and quantities are valid for the original invoice.
