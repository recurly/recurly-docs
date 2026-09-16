---
title: July 28, 2026 - Recurly Subscriptions Management
author: Christian Arango Salazar
hidden: false
published_at: '2026-07-29T18:00:46.308Z'
---
The July 28 release delivers a set of enhancements across add-ons, the V3 API, Vertex tax integration, and invoicing. Highlights include sub-cent pricing precision for all non-usage add-ons, expanded Vertex version support with Brazilian tax ID display, and a new invoice setting for surfacing account email addresses in billing details.

| Release Date | **Feature**                    | **Type**    | **Potential Impact** | **Description / Overview**                                                                                                                                                                                         |
| :----------- | :----------------------------- | :---------- | :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Jul 28, 2026 | **Add-ons**                    | Enhancement | Low                  | Sub cent (up to 9 decimal places) pricing is now available on all non-usage based add-ons using any pricing model (fixed, tiered, volume, stairstep). This is available in the UI and through the V3 API.          |
| Jul 28, 2026 | **V3 API**                     | Enhancement | Low                  | Recurly will now return gateway tokens on file in transaction and fetch responses when a gateway token is on file or used in the transaction.                                                                      |
| Jul 28, 2026 | **Taxes - Vertex**             | Enhancement | Low                  | Recurly now supports the latest Vertex versions 9.1, 9.2, and 9.3.                                                                                                                                                 |
| Jul 28, 2026 | **Taxes - Vertex**             | Enhancement | Low                  | Integrating with the latest Vertex version will allow you to display Brazilian tax IDs CPF/CNPJ and other informational tax on a subscriber's invoice, when applicable, with no configuration required in Recurly. |
| Jul 28, 2026 | **Kount 360 Fraud Management** | Bug fix     | Low                  | We've fixed an issue where zero-decimal currencies were sending an amount too large to Kount during fraud checks.                                                                                                  |
| Jul 28, 2026 | **Invoices**                   | Enhancement | Low                  | Recurly now offers a new invoice setting that will display an account's email address in the 'Bill To' section of the invoice.                                                                                     |