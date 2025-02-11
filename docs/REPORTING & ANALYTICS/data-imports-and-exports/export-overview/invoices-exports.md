---
title: Invoices - export
excerpt: >-
  Hidden page - please visit the following page for the most up to date
  information https://docs.recurly.com/docs/invoices-summary
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Recurly provides two exports to help you retrieve data related to invoices: Invoices - Summary and Invoices - Unused Numbers. These exports complement each other to provide details about different subsets of invoice numbers.

## Version Change Log

### Invoices- Accounts Receivable

#### Version 2 - 7/25/2023

- Net term type column expanded to include new End of Month terms

### Invoices- Summary

#### Version 4 - 7/25/2023

- Net term type column expanded to include new End of Month terms

### Invoices- (Deprecated)

#### 7/25/2023

- Net term type column expanded to include new End of Month terms

# Invoices - Summary

The invoice summary export contains the invoice header information and the summary totals for each of your successfully-generated invoices. 

### Invoice Status Filter

#### All

Every invoice generated within your Recurly site, regardless of status.

#### Open

All invoices that have not received a payment attempt. This status has a value of 'pending' in the export and does not include invoices with a 'past_due' status. This status only exists for manual invoices. If you see this status for an automatically collected invoice, it may mean that the payment attempt had a transaction communication error.

#### Processing

All invoices that have an ACH bank payment in progress. This status will only exist for ACH bank payments. The status means the associated payment transaction has not settled. An ACH invoice with the Processing status that reaches the due date will not move to Past Due or Paid until the transaction has settled.

#### Closed

All successfully collected invoices. This status has a value of 'paid' in the export and does not include the 'failed' status. It is important to note that the associated credit card, PayPal, or Amazon transaction with a paid invoice may not be settled with the gateway. Allow at least 1 to 3 business days for transaction settlement with the gateway.

#### Past Due

All automatic invoices that attempted collection, but the payment failed, or manual invoices that have reached their due date. Payment for automatic invoices will be retried automatically through <a href='/docs/dunning-management'>the dunning process</a>.

#### Failed

All invoices that have either experienced 20 declines or have been through the dunning process without successful payment. These invoices will not be retried. It is important to note that failed invoices will clear the owed balance from the account and will not attempt any future collections, but the charge line items will still exist in the account history.

#### Voided

All credit invoices that have been voided. These invoices will not be retried. It is important to note that voided invoices will clear the owed balance from the account and will not attempt any future collections, but the credit line items will still exist in the account history.

### Date Range Filters

#### Created

Shows invoices created during the selected time range. Uses the 'billed_date' column in the export.

#### Modified

Shows invoices last modified during the selected time range. An invoice is only modified when its 'status' changes. Uses the 'modified_at' column in the export.

### Export Contents

[block:parameters]
{
  "data": {
    "h-0": "Column Name",
    "h-1": "Example",
    "h-2": "Description",
    "0-0": "<span id=\"id\">id</span>",
    "0-1": "b964b5439c2548a489b3a136e75aee9f",
    "0-2": "Unique internal identifier for the invoice. This is also called the 'invoice_id' or 'uuid' for the invoice in the API.",
    "1-0": "<span id=\"invoice_number\">invoice_number</span>",
    "1-1": "1291",
    "1-2": "External invoice identifier.",
    "2-0": "<span id=\"billed_date\">billed_date</span>",
    "2-1": "2012-02-19 12:01:33 PST",
    "2-2": "Creation date of the invoice. Equivalent to date in the deprecated Invoices export. Used for Created date range filter.",
    "3-0": "<span id=\"due_on\">due_on</span>",
    "3-1": "2012-02-19 12:01:33 PST",
    "3-2": "Date invoice is due. This is the date the net terms is reached.",
    "4-0": "<span id=\"closed_at\">closed_at</span>",
    "4-1": "2012-02-19 12:01:33 PST",
    "4-2": "Date invoice was closed (paid) or failed.",
    "5-0": "<span id=\"status\">status</span>",
    "5-1": "pending, processing, past_due, paid, failed, voided",
    "5-2": "Current status of the invoice. Equivalent to invoice_state in the Adjustments export. See filter notes above for details on what each status means.",
    "6-0": "<span id=\"net_terms\">net_terms</span>",
    "6-1": "on-receipt, net-10, net-30, net-60",
    "6-2": "Identifies the net_terms agreement associated with the invoice. All automatic collection invoices are due 'on-receipt'. Manual collection invoices can have terms of net-10, net-30, net-60, or a custom net day amount.",
    "7-0": "<span id=\"collection_method\">collection_method</span>",
    "7-1": "automatic or manual",
    "7-2": "Identifies whether the invoice fees are collected via manual or automatic invoicing. An automatic invoice means a corresponding transaction is run using the account's billing information at the same time the invoice is created. Manual invoices are created without a corresponding transaction.",
    "8-0": "<span id=\"account_code\">account_code</span>",
    "8-1": "123122E",
    "8-2": "Account code being charged for this invoice.",
    "9-0": "<span id=\"account_name\">account_name</span>",
    "9-1": "JJ Smith",
    "9-2": "First and last name from account associated with that invoice.",
    "10-0": "<span id=\"account_company\">account_company</span>",
    "10-1": "Company, Inc.",
    "10-2": "Company name from account. This field is from the Account Info and is displayed on the invoice if it exists.",
    "11-0": "<span id=\"account_line1\">account_line1</span>",
    "11-1": "1 Main Street",
    "11-2": "Address line 1 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "12-0": "<span id=\"account_line2\">account_line2</span>",
    "12-1": "Suite 100",
    "12-2": "Address line 2 of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "13-0": "<span id=\"account_city\">account_city</span>",
    "13-1": "San Francisco",
    "13-2": "City of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "14-0": "<span id=\"account_state\">account_state</span>",
    "14-1": "CA",
    "14-2": "State or province of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "15-0": "<span id=\"account_zip\">account_zip</span>",
    "15-1": "94107",
    "15-2": "ZIP/postal code of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "16-0": "<span id=\"account_country\">account_country</span>",
    "16-1": "US",
    "16-2": "The 2 letter country code for the country of the customer's address on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method.",
    "17-0": "<span id=\"vat_number\">vat_number</span>",
    "17-1": "IE124211145",
    "17-2": "VAT registration number for the customer on the invoice. This will come from the VAT Number field in the Billing Info or the Account Info depending on your tax settings and the invoice collection method.",
    "18-0": "<span id=\"po_number\">po_number</span>",
    "18-1": "AE12523",
    "18-2": "For manual invoicing, this identifies the Purchase Order number associated with the invoice. This value must be entered by the merchant at the time the invoice is created or it will not exist.",
    "19-0": "<span id=\"coupon_code\">coupon_code</span>",
    "19-1": "50off",
    "19-2": "The code for the coupon associated with any discounts on the invoice. This value will only exist if a coupon was applied to the invoice.",
    "20-0": "<span id=\"currency\">currency</span>",
    "20-1": "USD",
    "20-2": "The currency of the amounts on the invoice. We do not allow mixed currency invoices.",
    "21-0": "<span id=\"invoice_total\">invoice_total</span>",
    "21-1": "100",
    "21-2": "The final total on the invoice. The summation of invoice charges, discounts, credits, and tax. Equivalent to the total in the deprecated Invoices export",
    "22-0": "<span id=\"invoice_subtotal\">invoice_subtotal</span>",
    "22-1": "50",
    "22-2": "The Subtotal on the invoice. The summation of charges, discounts, and credits, before tax.",
    "23-0": "<span id=\"tax_amount\">tax_amount</span>",
    "23-1": "15.00",
    "23-2": "The total tax amount on the invoice.",
    "24-0": "<span id=\"tax_type\">tax_type</span>",
    "24-1": "usst, vat, ca, au, nz",
    "24-2": "Provides the tax type as \"vat\" for EU VAT, \"usst\" for U.S. Sales Tax, or the 2 letter country code for country level tax types like Canada, Australia, New Zealand, Israel, and all non-EU European countries.",
    "25-0": "<span id=\"tax_region\">tax_region</span>",
    "25-1": "NY, FR, GST, VAT",
    "25-2": "Provides the tax region applied on an invoice. For U.S. Sales Tax, this will be the 2 letter state code. For EU VAT this will be the 2 letter country code. For all country level tax types, this will display the regional tax, like VAT, GST, or PST.",
    "26-0": "<span id=\"tax_rate\">tax_rate</span>",
    "26-1": "0.1",
    "26-2": "Tax rate applied on the invoice.",
    "27-0": "<span id=\"credit_to_account\">credit_to_account</span>",
    "27-1": "0",
    "27-2": "Amount of credit applied back to the account. This amount is a charge with adjustment_origin of 'carryforward' on the invoice. This charge is what zeros out the invoice and should be filtered out of your reports. Credit to Account also maps to the uninvoiced credit that is created for the same amount and left on the account for payment of a future invoice. That credit will have an adjustment_origin that matches the original charge's origin.",
    "28-0": "<span id=\"recovery_reason\">recovery_reason</span>",
    "28-1": "exp_date, retry, account_updater, prior_recovery, customer_updates",
    "28-2": "If the initial transaction failed but a subsequent one succeeded, this field indicates why. See the details of what each reason means in our blog \"[Revenue Recovery: What Has Recurly Recovered for Me Lately?](https://blog.recurly.com/what-has-recurly-recovered-revenue)\".",
    "29-0": "<span id=\"invoice_country\">invoice_country</span>",
    "29-1": "FR",
    "29-2": "This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the EU or NZ country code of the customer's address on the invoice. The country refers to the evidence_matched.",
    "30-0": "<span id=\"evidence_matched\">evidence_matched</span>",
    "30-1": "Account Info Country, Billing Info Country, IP Address Country, Credit Card BIN Country",
    "30-2": "This column is only visible if your site has European Union VAT or New Zealand GST Location Validation enabled. Column shows the two pieces of evidence that matched when the invoice was created. The corresponding country is the invoice_country.",
    "31-0": "<span id=\"modified_at\">modified_at</span>",
    "31-1": "2014-12-26 08:23:34 PST",
    "31-2": "The date the invoice was last modified. An invoice is only modified if the status changes. Used for Modified date range filter.",
    "32-0": "<span id=\"invoice_type\">invoice_type</span>",
    "32-1": "purchase, refund, renewal, immediate_change, termination, credit, gift_card, write_off, external_refund, carryforward_credit, carryforward_gift_credit, usage_correction, import",
    "32-2": "This is the invoice origin. The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'.  \n<br>  \nAll other invoice types are unlocked only when the Credit Invoices feature is enabled. See the full table of <a href='/docs/invoices#section-origins'>invoice origins</a> for descriptions.",
    "33-0": "<span id=\"original_invoice_number\">original_invoice_number</span>",
    "33-1": "1002",
    "33-2": "If the row is a refund invoice, this value will exist and show the invoice number of the purchase invoice the refund was created from.",
    "34-0": "<span id=\"ship_address_name\">ship_address_name</span>",
    "34-1": "Julie Smith",
    "34-2": "The first and last name associated with the shipping address",
    "35-0": "<span id=\"ship_address_line1\">ship_address_line1</span>",
    "35-1": "ship_address_line1",
    "35-2": "ship_address_line1",
    "36-0": "<span id=\"ship_address_line2\">ship_address_line2</span>",
    "36-1": "Apt 1",
    "36-2": "The second line of the street address for the shipping address",
    "37-0": "<span id=\"ship_address_city\">ship_address_city</span>",
    "37-1": "West Bloomfield",
    "37-2": "The city for the shipping address",
    "38-0": "<span id=\"ship_address_state\">ship_address_state</span>",
    "38-1": "MI",
    "38-2": "The state for the shipping address",
    "39-0": "<span id=\"ship_address_zip\">ship_address_zip</span>",
    "39-1": "48322",
    "39-2": "The zip or postal code for the shipping address",
    "40-0": "<span id=\"ship_address_country\">ship_address_country</span>",
    "40-1": "US",
    "40-2": "The country for the shipping address",
    "41-0": "<span id=\"ship_address_phone\">ship_address_phone</span>",
    "41-1": "248-555-1212",
    "41-2": "The phone number associated with the shipping address",
    "42-0": "<span id=\"invoice_doc_type\">invoice_doc_type</span>",
    "42-1": "legacy, charge, credit",
    "42-2": "This is the invoice document type. All invoices created before the Credit Invoices feature is enabled will have a type of ‘legacy’. Once Credit Invoices is enabled, new invoices will be either ‘charge’ or ‘credit’.",
    "43-0": "<span id=\"invoice_balance\">invoice_balance</span>",
    "43-1": "50.25",
    "43-2": "The balance of the invoice.  \n**This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "44-0": "<span id=\"invoice_balance_modified_at\">invoice_balance_modified_at</span>",
    "44-1": "2016-01-01 10:17:02 UTC",
    "44-2": "The datetime the invoice_balance last changed due to a transaction or credit payment.  \n**This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "45-0": "<span id=\"invoice_balance_modified_at\">invoice_balance_modified_at</span>",
    "45-1": "10",
    "45-2": "The total of all discounts on the invoice. This is the sum of each adjustment’s discount.",
    "46-0": "<span id=\"invoice_discount\">invoice_discount</span>",
    "46-1": "50.25",
    "46-2": "The total of all adjustments on the invoice, before discounts and taxes.",
    "47-0": "<span id=\"invoice_subtotal_before_discounts\">invoice_subtotal_before_discounts</span>",
    "47-1": "50.25",
    "47-2": "The refundable amount of the invoice, which is the invoice total, including discounts and tax, minus all credit invoices issued against it.  \n**This column will be null until Recurly's Credit Invoices feature is enabled on your Recurly site.**",
    "48-0": "<span id=\"business_entity_code\">business_entity_code</span>",
    "48-1": "123456789",
    "48-2": "The Business Entity code is a unique string of letters and numbers you must create for each alternate business entity. This will be used to reference and assign/use business entity codes in the API, and is used to determine entities in exports. "
  },
  "cols": 3,
  "rows": 49,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


# Invoices - Unused Numbers

The unused invoice number export contains basic information for all invoice numbers that were **not** used on successfully-generated invoices. An unused invoice number could result from a failed sign-up, among other events.

This log of unused invoice numbers is especially useful for audit purposes. It complements the invoice numbers provided in the Invoices - Summary export to provide an explanation for each invoice number in your sequence.

All invoice numbers unsuccessfully attempted on or after July 1, 2019 will be shown in this export.

### Export Contents

[block:parameters]
{
  "data": {
    "h-0": "Column Name",
    "h-1": "Example",
    "h-2": "Description",
    "0-0": "invoice_number",
    "0-1": "1291",
    "0-2": "External invoice identifier.",
    "1-0": "invoice_type",
    "1-1": "purchase, refund, renewal, immediate_change, termination, credit, gift_card, write_off, external_refund, carryforward_credit, carryforward_gift_credit, usage_correction, import",
    "1-2": "This is the invoice origin. The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'.  \n<br>  \nAll other invoice types are unlocked only when the Credit Invoices feature is enabled. See the full table of <a href='/docs/invoices#section-origins'>invoice origins</a> for descriptions.",
    "2-0": "invoice_doc_type",
    "2-1": "legacy, charge, credit",
    "2-2": "This is the invoice document type. All invoices created before the Credit Invoices feature is enabled will have a type of ‘legacy’. Once Credit Invoices is enabled, new invoices will be either ‘charge’ or ‘credit’.",
    "3-0": "invoice_date",
    "3-1": "2019-07-19 12:01:33 PST",
    "3-2": "Attempted creation date of the invoice.  \nThe earliest invoice date possible is July 1, 2019, as this is the release date of this export."
  },
  "cols": 3,
  "rows": 4,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


# Invoices (DEPRECATED)

The invoice export contains individual invoice line items including summary totals for invoices, so multiple items may be associated with the same invoice ID. 

> 🚧 
> 
> The Invoices export has been replaced by the "Invoices - Summary" export and the "Adjustments" export. **This export will be removed when your site enables credit memo functionality**.

### Invoice Status Filter

#### All

Every invoice generated within your Recurly site, regardless of status.

#### Open

All invoices that have not received a payment attempt. Open is equivalent to 'pending' in the new invoice exports and does not include the 'past_due' status. This status only exists for manual invoices. If you see this status for an automatically collected invoice, it may mean that the payment attempt had a transaction communication error.

#### Processing

All invoices that have an ACH bank payment in process. This status will only exist for ACH bank payments. The status means the associated payment transaction has not settled. An ACH invoice with the Processing status that reaches the due date will not move to Past Due or Paid until the transaction has settled.

#### Closed

All successfully collected invoices. Closed is equivalent to 'paid' in the new invoice exports and does not include the 'failed' status. It is important to note that the associated credit card, PayPal, or Amazon transaction with a Closed invoice may not be settled with the gateway. Allow at least 1 to 3 business days for transaction settlement with the gateway.

#### Past Due

All automatic invoices that attempted collection, but payment failed, or manual invoices that have reached their due date. Payment for automatic invoices will be retried automatically through <a href='/docs/dunning-management'>the dunning process</a>.

#### Failed

All invoices that have either experienced 20 declines, or have been through the dunning process without successful payment. These invoices will not be retried. It is important to note that failed invoices will clear the owed balance from the account and will not attempt any future collections, but the charge line items will still exist in the account history.

### Date Range Filter

#### Created

Shows invoices created during the selected time range. Uses the 'billed_date' column in the export.

#### Modified

Shows invoices last modified during the selected time range. An invoice is only modified when its 'status' changes. Uses the 'modified_at' column in the export.

### Export Contents

| Column Name               | Example                                                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| :------------------------ | :------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                        | b964b5439c2548a489b3a136e75aee9f                                           | Unique internal identifier for the invoice. This is also called the 'invoice_id' or 'uuid' for the invoice in the API.                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| account_code              | 123122E                                                                    | Account code being charged for this invoice.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| account_name              | JJ Smith                                                                   | First and last name from account,                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| invoice_number            | 1291                                                                       | External invoice identifier.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| subscription_id           | 1fed8d153fcf4ea2a1d55ff2eebd51b7                                           | Subscription UUID associated with this line item on the invoice.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| plan_code                 | basic                                                                      | The plan code for the plan associated with the subscription. This value will exist for plan fee, setup fee, add-on fee and free trial line items. This value will not exist for custom charges, custom credits, or open amount refund credits.                                                                                                                                                                                                                                                                                                             |
| coupon_code               | 50off                                                                      | The code for the coupon associated with any discounts on the invoice. This value will only exist if a coupon was applied to the invoice and will show for all line items on an invoice, even if the specific line item was not discounted by the coupon.                                                                                                                                                                                                                                                                                                   |
| total                     | 100                                                                        | The final total on the invoice. The summation of invoice charges, discounts, credits, and tax. Equivalent to the invoice_total in the Invoices - Summary export                                                                                                                                                                                                                                                                                                                                                                                            |
| subtotal                  | 50                                                                         | Total charges on the invoice before discounts, credits, and tax.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| tax_amount                | 12.25                                                                      | The total tax amount on the invoice. This is not the tax amount for the specific line item.                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| currency                  | USD                                                                        | The currency of the amounts on the invoice. Every line item on an invoice will have the same currency. We do not allow mixed currency invoices.                                                                                                                                                                                                                                                                                                                                                                                                            |
| date                      | 2012-02-19 12:01:33 PST                                                    | Creation date of the invoice. Equivalent to billed_date in the Invoices - Summary export. **Used for Created date range filter.**                                                                                                                                                                                                                                                                                                                                                                                                                          |
| status                    | open, processing, past_due, closed, or failed                              | Current status of the invoice. Equivalent to invoice_state in the Adjustments export and status in the Invoices - Summary export. See filter notes above for details on what each status means.                                                                                                                                                                                                                                                                                                                                                            |
| closed_at                 | 2012-01-18 11:47:13 PST                                                    | Date invoice was closed (paid) or failed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| purchase_country          | IE                                                                         | The 2 letter country code for the country of the customer on the invoice. This will come from the Billing Address or the Account Address depending on your tax settings and the invoice collection method. Equivalent to account_country in the Invoices - Summary export.                                                                                                                                                                                                                                                                                 |
| vat_number                | IE124211145                                                                | VAT registration number for the customer on the invoice. This will come from the VAT Number field in the Billing Info or the Account Info depending on your tax settings and the invoice collection method.                                                                                                                                                                                                                                                                                                                                                |
| line_item_total           | 500                                                                        | The total amount of the line item after discounts and taxes [(quantity x price) + discount + tax]. Equivalent to adjustment_total in the Adjustments export.                                                                                                                                                                                                                                                                                                                                                                                               |
| line_item_description     | Basic Plan, one month                                                      | Description for a specific invoice line item. This is automatically generated for all plan line items. This is custom for one-time custom charges and credits. Equivalent to adjustment_description in the Adjustments export.                                                                                                                                                                                                                                                                                                                             |
| line_item_origin          | plan, plan_trial, setup_fee, add_on, debit, one_time, credit, carryforward | The original source for a line item. A credit created from an original charge will have the value of the charge's origin. Equivalent to adjustment_origin in the Adjustments export. (plan = subscription fee, plan_trial = trial period 0 amount charge, setup_fee = subscription setup fee, add_on = subscription add-on fee, debit = custom charge through the UI or Adjustments API, one_time = custom charge through the Transactions API, credit = custom credit, carryforward = the charge that zeros out a negative invoice and should be ignored) |
| line_item_product_code    | 0000yearly                                                                 | Plan code for a specific invoice line item. This will only populate if the line item is for a subscription. The value will always be the plan_code, unless the line item is an add-on, which would then show the add-on code. Equivalent to adjustment_product_code in the Adjustments export.                                                                                                                                                                                                                                                             |
| line_item_accounting_code | 0000yearly                                                                 | Internal accounting code for a specific invoice line item. This value will only populate if you define an accounting code for the line item. Accounting codes can be defined for all line items except free trials, which will inherit the plan's accounting code. Equivalent to adjustment_accounting_code in the Adjustments export.                                                                                                                                                                                                                     |
| line_item_start_date      | 2012-01-19 11:03:23 PST                                                    | Bill cycle start date for a specific invoice line item. Equivalent to adjustment_start_at in the Adjustments export.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| line_item_end_date        | 2012-02-19 11:03:23 PST                                                    | Bill cycle end date for a specific invoice line item. This date will not exist for custom charges (one-time). Equivalent to adjustment_end_at in the Adjustments export.                                                                                                                                                                                                                                                                                                                                                                                   |
| net_terms                 | on-receipt, net-10, net-30, net-60                                         | Identifies the net_terms agreement associated with the invoice. All automatic collection invoices are due 'on-receipt'. Manual collection invoices can have terms of net-10, net-30, net-60, or a custom net day amount.                                                                                                                                                                                                                                                                                                                                   |
| po_number                 | 213123                                                                     | For manual invoicing, this identifies the Purchase Order number associated with the invoice. This value must be entered by the merchant at the time the invoice is created or it will not exist.                                                                                                                                                                                                                                                                                                                                                           |
| collection_method         | automatic or manual                                                        | Identifies whether the invoice fees are collected via manual or automatic invoicing. An automatic invoice means a corresponding transaction is run using the account's billing information at the same time the invoice is created. Manual invoices are created without a corresponding transaction. The merchant must enter a manual payment transaction or have the customer pay the invoice with an automatic method, like credit card, PayPal, Amazon, or ACH bank payment.                                                                            |
| line_item_uuid            | 293f96f8c6fd1f8f622ec44306a3a92a                                           | Provides the unique internal identifier for each line item on an invoice. Equivalent to uuid in the Adjustments export.                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| tax_type                  | usst, vat, ca, au, nz                                                      | Provides the tax type as "vat" for EU VAT, "usst" for U.S. Sales Tax, or the 2 letter country code for country level tax types like Canada, Australia, New Zealand, Israel, and all non-EU European countries.                                                                                                                                                                                                                                                                                                                                             |
| tax_region                | NY, FR, GST, VAT                                                           | Provides the tax region applied on an invoice. For U.S. Sales Tax, this will be the 2 letter state code. For EU VAT this will be the 2 letter country code. For all country level tax types, this will display the regional tax, like VAT, GST, or PST.                                                                                                                                                                                                                                                                                                    |
| tax_rate                  | 0.1                                                                        | Tax rate applied on the invoice                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| discount                  | -5                                                                         | Total discount amount applied on an invoice. This is not the discount for the specific line item.                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| original_adjustment_uuid  | b964b5439c2548a489b3a136e75aee9f                                           | Value is the uuid of the previous related line item (adjustment). Will only have a value if the line item is a credit created from a previous credit, or if the credit was created from a charge refund.                                                                                                                                                                                                                                                                                                                                                   |
| modified_at               | 2014-12-26 08:23:34 PST                                                    | The date the invoice was last modified. An invoice is only modified if the status changes. **Used for Modified date range filter.**                                                                                                                                                                                                                                                                                                                                                                                                                        |
| invoice_type              | purchase, refund                                                           | The original invoice will have a type of 'purchase'. Any refunds or voids will create a negative invoice to cancel out the original. This negative invoice will have a type of 'refund'.                                                                                                                                                                                                                                                                                                                                                                   |
| original_invoice_number   | 1002                                                                       | If the row is a line item from a refund invoice, this value will exist and show the invoice number of the purchase invoice the refund was created from.                                                                                                                                                                                                                                                                                                                                                                                                    |