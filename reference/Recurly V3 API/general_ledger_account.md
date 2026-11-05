---
title: general_ledger_account
excerpt: |-
  A general ledger account is an account of record used to sort, store
  and summarize a company's transactions. Recurly supports the balance
  sheet (Liability) account and income (Revenue) account to be attached
  to business entities, plans, or at the item level.

  When invoices are created, system can default to the accounts based
  on the GL Accounts attached at the plan/item level. The accounts can
  be defaulted from the business entity level as well.

  These accounts will be used in the Revenue Recognition module to create
  the revenue journals that can be posted into Merchant GL system.

  Revenue and Liability accounts can defined in the system using this
  API or via the General Ledger Accounting page in the Admin UI and then
  used at the plan/item level.

  Recurly allows merchants to default the accounts at the following levels:
  - Business Entities (default)
  - Plans
      - Base Price
      - Setup Fee
      - Add-ons
  - Items
  - Charges
  - Gift Cards
  - Shipping Methods
  - Credits

  If you are interested in Recurly Revenue Recognition features, please
  contact a Recurly customer service representative.
hidden: false
---