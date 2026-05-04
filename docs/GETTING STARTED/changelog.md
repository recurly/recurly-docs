---
title: Recurly release notes/Changelog
excerpt: >-
  Stay updated with the latest minor tweaks and enhancements in Recurly’s
  functionality through the Release Notes section. Explore a curated digest of
  UI upgrades, API extensions, and more that continually refine your user
  experience.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Introduction

A concise digest of Recurly's ongoing changes and minor updates that continually shape and refine your user experience. Get a glimpse of the small but mighty changes in our app's look, feel, and functionality, along with additions to the API and Recurly.js.

## Learn about recent refinements

The Release Notes section is your go-to place to catch up on the minor yet meaningful changes we have rolled out. From UI tweaks to API and Recurly.js extensions, stay in the loop with the incremental improvements making your Recurly experience smoother. For major updates, our [blog](https://blog.recurly.com) and newsletter are still your best companions. Questions? [Contact support](mailto:support@recurly.com).

# 2026

## May

| Release Date | **Feature**                  | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                    |
| :----------- | :--------------------------- | :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| May 5        | **Custom fields & invoices** | Low                  | Custom fields are now available to be applied on invoices.  A new configuration option controls whether or not a custom field is available in invoice templates.  Once the custom field is saved to a template, the field and its value will be displayed on an invoices moving forward.                                                                                                                      |
| May 5        | **Admin Exports**            | Low                  | Admin exports (Account Activities, Site Activities and Users exports) can now be scheduled to run automatically on a recurring basis, eliminating the need to trigger them manually each cycle. To enable scheduling, a user must have both the Admin and Integrations roles assigned. For setup instructions, see [Automated Exports](https://docs.recurly.com/recurly-subscriptions/docs/automated-exports) |
| May 5        | **V3 API**                   | Medium               | The `payment_gateway_references`array will be available in the `payment_method` object in transaction responses for both processing and fetch endpoints. This will enable visibility into the gateway token used in a given purchase for both synchronous transaction responses and historical data queries.                                                                                                  |
| May 5        | **WorldPay Gateway**         | Medium               | We'll be making a small adjustment to void handling to ensure that capture delay differences at the gateway do not interfere with purchase cancellations. After release, we will request that WorldPay void **or** refund, depending on what action is possible on a given transaction.                                                                                                                       |

## April

| Release Date | **Feature**                                      | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| :----------- | :----------------------------------------------- | :------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Apr 22       | **Kount 360 Fraud Management**                   | Med                  | Final migrations from Kount Command to Kount 360 will occur on April 22nd. Again, no integration changes are necessary for merchants. Please see our updated <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount">Kount documentation</a> for information on new features.                                                                                                                                                                                                     |
| Apr 21       | **Payments Hub Analytics**                       | Low                  | Payments Hub Dashboards — General Availability. Payments Hub is now available to all customers with the analytics user role permission. The new analytics experience includes five (5) dashboards that give you comprehensive visibility into your payment operations including Overview, Payment Processing, Account Updater, Payment Retry Recovery and Fraud Prevention. Reference documentation: [Payments Hub](https://docs.recurly.com/recurly-subscriptions/docs/payments-hub)         |
| Apr 21       | **Kount Fraud Management**                       | Low                  | After release, we'll be sending the transaction UUID to Kount for better Kount Dashboard search-ability. This modification is for Kount 360 onlly.                                                                                                                                                                                                                                                                                                                                            |
| Apr 21       | **Cybersource Gateway**                          | Med                  | Post-release, GooglePay signup transactions that aren't authenticated through the phone will use 3DS authentication instead. This will require the use of 3DS flows in Recurly.js as usual.                                                                                                                                                                                                                                                                                                   |
| Apr 21       | **Stripe Gateway**                               | Med                  | We will be returning additional fraud-data from Stripe gateway including Radar scores.                                                                                                                                                                                                                                                                                                                                                                                                        |
| Apr 21       | **Cybersource Gateway**                          | Low                  | The P12 certificate in gateway configuration will now be a required field. If you have not yet added a P12 certificate to your gateway configuration, the next time you edit the configuration, you will need to provide one. Please see our <a href="https://docs.recurly.com/recurly-subscriptions/docs/cybersource#step-3-generate-your-p12-certificate-file-and-password">Cybersource documentation</a> for steps to create and add your file and password to your Recurly configuration. |
| Apr 14       | **V3 API**                                       | Low                  | Introducing a new synchronous bulk coupon endpoint.  POST `/coupons/{coupon_id}/generate_sync`                                                                                                                                                                                                                                                                                                                                                                                                |
| Apr 14       | **Vindicia Integration**                         | Low                  | Sending additional metadata to Vindicia.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Apr 9        | **Automated Exports**                            | Low                  | Scheduled export listings now include expanded filter details — version, variation, time range/zone, and creation date — giving you a clearer at-a-glance view of each configured export.                                                                                                                                                                                                                                                                                                     |
| Apr 9        | **Dark Mode**                                    | Low                  | Users can select their preferred appearance from 3 options - Auto (system setting), Light, Dark.  This setting can be found in the user's profile within Recurly.                                                                                                                                                                                                                                                                                                                             |
| April 8      | **Kount 360 Fraud Management**                   | Medium               | Initial migrations to Kount 360 will be taking place on April 8th. No integration changes are necessary at this time. Please see our updated <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount">Kount documentation</a> for information on new behaviors.                                                                                                                                                                                                                    |
| Apr 7        | **Commerce Hub Gateway**                         | Low                  | Minor improvements to Discover card handling, and improvements to expired card forwarding logic.                                                                                                                                                                                                                                                                                                                                                                                              |
| Apr 7        | **FreedomPay, Checkout.com, and Nuvei Gateways** | Low                  | Minor improvements to expired card forwarding logic.                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Apr 7        | **Kount 360 Fraud Management**                   | Medium               | For migrated merchants, Kount 360 will now send risk checks on all payment methods by default including Check / ACH transactions, Direct Debit, and applicable APMs.                                                                                                                                                                                                                                                                                                                          |
| Apr 7        | **Braintree Gateway**                            | Low                  | Minor improvements to descriptor handling to avoid Venmo errors.                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Apr 7        | **OAuth Onboarding Gateways**                    | High                 | We've made security improvements to gateways that onboard via OAuth including Amazon Pay V2, GoCardless, Stripe, and PayPal Complete. No issues are expected.                                                                                                                                                                                                                                                                                                                                 |
| Apr 1        | **PayPal Complete**                              | Medium               | No joking around, we've added the ability to use PayPal Credit when using the PayPal Complete gateway with the PayPal wallet. No code changes are required to make use of this feature, and customers may see PayPal Credit offered to them when signing up for subscriptions using PayPal.                                                                                                                                                                                                   |
| Apr 1        | **Recurly Engage**                               | Low                  | Integration with Hightouch to allow for data syncing.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Apr 1        | **Recurly Engage**                               | Low                  | Chargebee integration allowing merchants to sync their subscription data and execute billing actions directly from prompts in Recurly Engage, leveraging their existing Chargebee account.                                                                                                                                                                                                                                                                                                    |

## March

| Release Date | **Feature**                                  | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| :----------- | :------------------------------------------- | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mar 31       | **Stripe Gateway**                           | Medium               | We'll be adding support for Level III fields, and upgrading Stripe's underlying version to `2025-08-27.basil`                                                                                                                                                                                                                                                                                                                                                                                                    |
| Mar 31       | **PayPal Complete Gateway**                  | Low                  | We'll be enabling the usage of PayPal Complete's "Recurring Module", which will allow merchants to show PayPal users more detail about the subscriptions they're signing up for in the modal when using Recurly.js. Backwards compatibility is retained, and only a small adjustment to Recurly.js is necessary if you wish to use it. Please read our documentation for further details and examples in <a href="https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete">PayPal Complete</a> docs. |
| Mar 25       | **Kount 360 Fraud Management**               | High                 | We will be migrating a small percentage of traffic to Kount 360, away from Kount Command. No integration changes are necessary at this time.                                                                                                                                                                                                                                                                                                                                                                     |
| Mar 24       | **Netsuite Integration**                     | Low                  | New functionality in the Netsuite integration where data synchronization errors between Recurly and Netsuite can be viewed, drilled into for further investigation, and resolved by re-syncing selected records.                                                                                                                                                                                                                                                                                                 |
| Mar 24       | **Stripe Gateway**                           | High                 | We will be re-releasing updated Card on File handling for Stripe, as the original implementation was reverted to revise one specific use case.                                                                                                                                                                                                                                                                                                                                                                   |
| Mar 24       | **Kount 360 Fraud Management**               | Low                  | We will be rolling out the latest and greatest Kount integration for sandbox usage only. Information on migration strategy will be available on the Kount documentation page after release. No integration changes are expected at this time though recommendations may be made in the future. After release, please review updated <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount">Kount documentation</a> and recommendations for integration.                                             |
| Mar 24       | **Adyen Gateway**                            | Low                  | We've recently added 3DS Authentication UI updates allowing merchants to see the status of a 3DS interaction in their transaction UI. To see these values, you must enable 3DS response details in your Adyen gateway. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#activation-of-3ds-results-data">3DS results data notes in our Adyen setup guide</a> for more details.                                                                                                              |
| Mar 24       | **PayPal Complete Gateway**                  | Low                  | We are making a small tweak to PayPal respond handling, when invalid shipping information is provided by merchants that is rejected by PayPal. The error will now return as `invalid_data` -- please ensure you are providing valid shipping address information, or omit it entirely.                                                                                                                                                                                                                           |
| Mar 17       | **Apple Pay Payments**                       | Low                  | We have updated documentation on how integrators can make updates to their checkout flows when using Recurly.js to support Apple Pay in. non-safari browsers. Please see <a href="https://docs.recurly.com/recurly-subscriptions/docs/apple-payhttps://docs.recurly.com/recurly-subscriptions/docs/apple-pay">Apple Pay Recurly.js documentation</a> for details.                                                                                                                                                |
| Mar 17       | **iDeal Logos**                              | Low                  | We are making a logo/branding update for iDeal to represent the shift to iDeal \| Wero. In UIs, you will now see a new logo that represents the branding change for this payment method. Please note, depending on the integration method you are using, that integration UI is controlled by the gateway itself (Adyen and Stripe) and may update at a different time.                                                                                                                                          |
| Mar 17       | **Stripe Gateway**                           | High                 | We're making behind-the-scenes updates to the Stripe integration related to card-on-file handling in order to improve auth rates. No integration changes are necessary from merchant-side, and all signups/renewals should continue to run smoothly.                                                                                                                                                                                                                                                             |
| Mar 17       | **Wallet**                                   | Low                  | Introducing a new configuration item in Payment Settings that will prevent duplicate billing infos from being saved.  This will function with PANs and RJS tokens.  This validation will also occur in the billing_infos API.                                                                                                                                                                                                                                                                                    |
| Mar 17       | **Compass Assistant**                        | Low                  | Ask AI is an AI-powered assistant built into Recurly. It helps you understand and get more value by answering questions about the current feature — all without leaving your current workflow.                                                                                                                                                                                                                                                                                                                   |
| Mar 10       | **Nuvei and Checkout.com Gateways**          | Low                  | We've updated handling of Level 2 data to the gateways. If you have already onboarded one of these gateways, please ensure you have saved your MCC code on file, and your Business entity and Site Settings are up to date.                                                                                                                                                                                                                                                                                      |
| Mar 10       | **Recurly Engage**                           | Low                  | Improvements and enhancements to Drill Down Metrics. You can now utilize Drill Down Metrics on the live view, as well as export the data on the all prompts page.                                                                                                                                                                                                                                                                                                                                                |
| Mar 6        | **Ebanx Gateway**                            | Medium               | We're making a change to how we query the gateway for mandate and status updates to avoid transactions and mandates in a pending or poor state.                                                                                                                                                                                                                                                                                                                                                                  |
| Mar 3        | **Adyen Gateway**                            | Low                  | Updated handling of CashApp response codes to avoid, or make more clear, errors related to this payment method.                                                                                                                                                                                                                                                                                                                                                                                                  |
| Mar 3        | **AmazonPay V2 Gateway**                     | Low                  | Updated handling of certain gateway responses to ensure Charge IDs that can't be used **yet** are classified as try_again.                                                                                                                                                                                                                                                                                                                                                                                       |
| Mar 3        | **Recurly Reporting \| Transaction Details** | Low                  | We are exposing 3DS Authentication information in our UI when a transaction goes through SCA. You will see some new fields around the final state of the authentication (results), and if available on that gateway, the final ECI and Code related to the 3DS authentication.                                                                                                                                                                                                                                   |
| Mar 3        | **Braintree Gateway**                        | Low                  | We've updated the handling of the UAH currency to avoid errors when using gateway tokens instead of Recurly.js.                                                                                                                                                                                                                                                                                                                                                                                                  |

## February

| Release Date | **Feature**                         | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| :----------- | :---------------------------------- | :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Feb 24       | **Checkout.com and Nuvei Gateways** | Low                  | These two payment gateways will be visible when onboarding gateways to your site. If you are interested in joining the EA program, please reach out to our Support team. For more information on Checkout and Nuvei, please visit their respective documentation pages: <a href="https://docs.recurly.com/recurly-subscriptions/docs/checkoutcom">Checkout.com documentation</a> and <a href="https://docs.recurly.com/recurly-subscriptions/docs/nuvei">Nuvei documentation</a>.                                                                                                                      |
| Feb 24       | **Vindicia Integration**            | Low                  | Introducing a new integration page in Recurly specifically for managing the connection to Vindicia.  This is a gated feature.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Feb 24       | **Dunning Campaigns**               | Low                  | Adding the ability to have unique Vindicia collection windows within each dunning campaign.  This feature is only available to those who have a Vindicia integration.                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Feb 20       | **Adyen Gateway**                   | Low                  | A small update to iDeal handling has been released, where if the consumer abandons their cart after initial payment submission and does not authorize the iDeal payment, the billing info ID on file will be invalidated, avoid an error if the consumer retries against their existing account.                                                                                                                                                                                                                                                                                                       |
| Feb 19       | **Ebanx Gateway**                   | Medium               | Pursuant to RBI's formatting modifications for UPI Subscriptions, any subscription plan names that contain special characters will be scrubbed and special characters removed prior to sending to the gateway in order to avoid subscription errors.                                                                                                                                                                                                                                                                                                                                                   |
| Feb 17       | **Braintree Gateway**               | High                 | Where necessary, we will be querying on externally provided gateway tokens, ingested via API or through a data migration, to ensure our billing information on file is as complete as possible. We do not expect any processing latency or a difference in processing to occur, however certain features will be available post-release, such as payment-method-dependent emails or retry behavior.                                                                                                                                                                                                    |
| Feb 17       | **Transaction Detail \| RA**        | Low                  | On a subset of gateways, we will be exposing the 3DS Results for a given transaction, if 3DS was used on the customer initiated purchase, verification, or signup request. You will be able to see whether or not the 3DS Authentication was successful, failed, unavailable, attempted, or experienced a downstream error in addition to the final authorization approval or decline. This will be exposed in APIs and analytics in the future. Support is limited to Adyen, Stripe, and Braintree initially. No integration changes are required.                                                    |
| Feb 17       | **Recurly Engage**                  | Low                  | We’ve added a dedicated Domain field to our standard trigger builder, making it easier to manage engagement across multiple brands. Merchants with domain aliases can now specify exactly which site a prompt should appear on without relying on complex segments or advanced logic.                                                                                                                                                                                                                                                                                                                  |
| Feb 17       | **Cybersource Gateway**             | Low                  | We will have made a small response mapping update for Merchants on the Barclays platform to avoid returning retry '83' responses as fraudulent decline messages.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Feb 17       | **Chase Orbital Gateway**           | Medium               | We will be making a change to how _refund_ invoice numbers are sent to the platform to avoid reconciliation issues. This will not have an effect on how invoice numbers are sent on authorizations or purchases.                                                                                                                                                                                                                                                                                                                                                                                       |
| Feb 17       | **Recurly Engage**                  | Low                  | We have significantly optimized the Experiment View to reduce latency and improve page load speeds.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Feb 10       | **Adyen Gateway**                   | Low                  | Added support for using ISK currency when passing in gateway tokens via API..                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Feb 10       | **Kount**                           | Medium               | Updated handling of rare cases of Kount usage that were causing BIN mishandling.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Feb 10       | **Adyen Gateway**                   | Medium               | Updated to support Level 3/III data parameters when you are using proper line items, taxes, shipping data, and HS/commodity codes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Feb 10       | **Recurly Engage**                  | Low                  | We have updated the evaluation logic for triggers that rely exclusively on exclusion rules to ensure more consistent behavior when firing.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Feb 10       | **Recurly Checkout**                | Low                  | V3 (hidden) reCAPTCHA will now always be enabled in Checkout.  If a failure occurs, V2 (I'm not a robot checkbox) reCAPTCHA will be displayed.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Feb 3        | **Braintree Gateway**               | Low                  | You can now enable Zero Dollar Authentication (ZDA / verifications) on Braintree when using Discover and American Express. This allows you to run trials and billing info updates without a 1.00 Authorization. Per Braintree's guidance, American Express will process 1 penny. You will be able to read more about this and any additional configuration requirements in our <a href="https://docs.recurly.com/recurly-subscriptions/docs/braintree-rd">Braintree</a> documentation post-release.                                                                                                    |
| Feb 3        | **Adyen Gateway**                   | Low                  | We will be offering Adyen's direct Realtime Account Updater feature for Adyen merchants. You will need to be using Adyen with raw credit card data (no tokens or APMs) to utilize the service. Since Adyen's service does not offer full card brand coverage, it is recommended to keep Recurly's Account Updater enabled in tandem. You will be able to read more about the service in our <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater">Account Updater</a> and <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen">Adyen</a> gateway documentation. |
| Jan 27       | **Recurly Engage**                  | Low                  | You can now filter your prompts using the new Engagement Category filter on the All Prompts page. This allows you to quickly sort content by categories such as Acquisition, Retention, or Upsell, including a "None" option for uncategorized prompts.                                                                                                                                                                                                                                                                                                                                                |
| Jan 27       | **Recurly Engage**                  | Low                  | We have introduced the ability to update Engagement Categories for multiple prompts simultaneously. By selecting a group of prompts, you can now assign a single category to all of them in one action, significantly reducing manual configuration time.                                                                                                                                                                                                                                                                                                                                              |
| Jan 27       | **Recurly Engage**                  | Low                  | Survey prompts now support "If selected option is" logic for Connector Actions. This enables you to trigger specific events, such as 1-click offers, directly based on a user’s unique survey response without needing complex workarounds.                                                                                                                                                                                                                                                                                                                                                            |

## January

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Jan 27
      </td>

      <td>
        **Stripe Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of line items on Stripe to avoid a rare collision when using Stripe Elements.
      </td>
    </tr>

    <tr>
      <td>
        Jan 27
      </td>

      <td>
        **Checkout.com Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        A brand new integration will be launched including support for Cards, Apple Pay and Google Pay. **Checkout.com** is a high performance gateway known for enterprise level support, and works as a modular and robust option for merchants looking for high volume and global reach.  Read more about our solution in our <a href="https://docs.recurly.com/recurly-subscriptions/docs/checkoutcom">Checkout.com documentation</a>.

        This gateway is part of Recurly's new Early Access Program. If you'd like to be part of this EA program, please reach out to our Support team.
      </td>
    </tr>

    <tr>
      <td>
        Jan 27
      </td>

      <td>
        **Nuvei Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        A brand new integration will be launched including support for Cards, Apple Pay and Google Pay. Nuvei is a flexible, global platform offering comprehensive payment options at scale for physical and digital goods.  Nuvei is particularly good for businesses wanting to scale rapidly or handle complex, cross-border payments through a single vendor. Read more about our solution in our <a href="https://docs.recurly.com/recurly-subscriptions/docs/nuvei">Nuvei documentation</a>.

        This gateway is part of Recurly's new Early Access Program. If you'd like to be part of this EA program, please reach out to our Support team.
      </td>
    </tr>

    <tr>
      <td>
        Jan 27
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Adjustments will be made to transaction handling to avoid errors caused by a lack of merchant permissions at the gateway level. Merchants who wish to use MOTO should speak with WorldPay specifically to enable `Allow Dynamic Interaction` permissions for their gateway account to avoid errors.
      </td>
    </tr>

    <tr>
      <td>
        Jan 21
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Sandbox accounts only will be updated to take advantage of behind-the-scenes improvements. if any issues arise, they will corrected prior to production updates.
      </td>
    </tr>

    <tr>
      <td>
        Jan 20
      </td>

      <td>
        **Subscriptions**
      </td>

      <td>
        Low
      </td>

      <td>
        Introducing new functionality that will apply proration when changing a subscription's bill date.  This is available in the UI and V3 API.
      </td>
    </tr>

    <tr>
      <td>
        Jan 20
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of refunds when using separate Auth and Capture to avoid settlement issues.
      </td>
    </tr>

    <tr>
      <td>
        Jan 20
      </td>

      <td>
        **Data Exports**
      </td>

      <td>
        Low
      </td>

      <td>
        The Revenue recognition schedules export will be deprecated as this export is related to the legacy Revenue Recognition feature which has also been sunsetted.
      </td>
    </tr>

    <tr>
      <td>
        Jan 20
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Medium
      </td>

      <td>
        You can now assign specific categories (such as Acquisition, Retention, Upgrade, Winback & Engagement) to your prompts and guides during configuration. This classification provides clearer insights into your "Prompt Success Rate" by use case, helping you better measure the impact of your engagement strategies on revenue
      </td>
    </tr>

    <tr>
      <td>
        Jan 20
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        For users with multiple subscriptions, you can now target specific attributes and create more granular segments based on subscription type. This allows for more personalized outreach, such as applying targeted coupons to one specific product while defaulting to a user's latest subscription.
      </td>
    </tr>

    <tr>
      <td>
        Jan 13
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates behind-the-scenes are being released to improve the gateway performance overall. No impact is expected with these upgrades.
      </td>
    </tr>

    <tr>
      <td>
        Jan 13
      </td>

      <td>
        **Business Entity Updates**
      </td>

      <td>
        Low
      </td>

      <td>
        The Business Entity UI in Recurly App will now support adding your MCC (Merchant Category Code) to your entities. Please ensure you have this data set accurately as it will be used for nuanced payment processing in the future.
      </td>
    </tr>

    <tr>
      <td>
        Jan 13
      </td>

      <td>
        **Card Brand Updates**
      </td>

      <td>
        Medium
      </td>

      <td>
        We will be updating handling of certain ELO Bins to avoid Discover classification to certain gateways.
      </td>
    </tr>

    <tr>
      <td>
        Jan 13
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We will be enabling the ability to set Account Credits on an account when a UPI, Pix, or Mercado Pago billing mandate is present on the account. Keep in mind, it is not supported to sign up for a mandate-reliant subscription with Account Credits or coupons that cover the entire initial amount, but partial credits and coupons are supported.
      </td>
    </tr>

    <tr>
      <td>
        Jan 13
      </td>

      <td>
        **Check Commerce Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        We'll be exposing a field in gateway configuration for this gateway so that Merchants can set their highest transaction amount per their gateway contract. This should be set, else the maximum is 5000.00 per invoice. See <a href="https://docs.recurly.com/recurly-subscriptions/docs/check-commerce">Check Commerce</a>  documentation for more information.
      </td>
    </tr>

    <tr>
      <td>
        Jan 12
      </td>

      <td>
        **Analytics**
      </td>

      <td>
        Low
      </td>

      <td>
        In the Analytics Billings dashboards, if the transaction billing country is not available, then the issuer country will be used in the underlying data.
      </td>
    </tr>

    <tr>
      <td>
        Jan 6
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Added user traits to the "User Look Up" profile view, allowing administrators to easily verify imported user data and confirm values for dynamic variables directly within the UI.
      </td>
    </tr>

    <tr>
      <td>
        Jan 6
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Introduced a bulk editing feature that enables users to apply or modify tags across multiple prompts simultaneously, streamlining the management of large-scale campaigns.
      </td>
    </tr>

    <tr>
      <td>
        Jan 6
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Upgraded prompt reporting to support detailed performance breakdowns by segment, locale, and device category, providing deeper visibility into how localized content performs across different markets.
      </td>
    </tr>
  </tbody>
</Table>

# 2025

## December

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Dec 16
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Optimization of real-time webhooks, ensuring that custom goals are recorded without timing discrepancies.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Data Exports**
      </td>

      <td>
        Low
      </td>

      <td>
        Two new data exports will be available for both adhoc and automated reporting.

        **Products Catalog export** - provides a detailed list of all product offerings, add-ons and items, whether active or inactive. **Subscriptions - Pending changes export** - reports on all active subscriptions with a pending change that will be applied at the next renewal or future date. This includes changes to the plan, price, or quantity.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Additional improvements to retries including a small UI tweak and error code handling.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Stripe gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Fixes to stored payment method handling when the consumer is in India, as well as avoiding a rare return url for stored cards.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Medium
      </td>

      <td>
        Enhanced Security & Access. Recurly Engage now supports HIPAA compliance and Okta sign-in, providing superior data protection and simplified access.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Recurly webhook optimizations have been implemented for increased reliability and speed.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Recurly Engage now offers One-Click actions with Recurly Commerce.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Recurly Engage & Recurly Compass**
      </td>

      <td>
        Low
      </td>

      <td>
        30-day Sandbox provisioning for Recurly Engage is now available through the Recurly Compass assistant or the Recurly Engage Integrations page.
      </td>
    </tr>

    <tr>
      <td>
        Dec 9
      </td>

      <td>
        **Subscriptions**
      </td>

      <td>
        Low
      </td>

      <td>
        Proration can now be enabled when changing a subscription's bill date.  An immediate credit and charge will be created.  This can be accomplished in both the UI and v3 API.
      </td>
    </tr>

    <tr>
      <td>
        Dec 2
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Added **UPI Retries** for <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/">UPI AutoPay</a> renewals/subscriptions. UPI AutoPay retries will run the same day as the initial decline. Read more about the payment method and <a href="https://docs.recurly.com/recurly-subscriptions/docs/ebanx-gateway#/">Ebanx gateway</a> in our dedicated documentation.
      </td>
    </tr>

    <tr>
      <td>
        Dec 2
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Enhanced Security & Access. Recurly Engage now supports HIPAA compliance and Okta sign-in, providing superior data protection and simplified access.
      </td>
    </tr>

    <tr>
      <td>
        Dec
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Recurly webhook optimizations have been implemented for increased reliability and speed.
      </td>
    </tr>

    <tr>
      <td>
        Dec 2
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated UPI AutoPay transaction requests (for renewals only) to occur within regulation time frames per RBI requirements. UPI AutoPay renewals will run between 12 AM and 7 AM IST. This does not apply to signup transactions.
      </td>
    </tr>

    <tr>
      <td>
        Dec 2
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Optimized handling of PIX Automatico and Mercado Pago retry scheduling and next charge dates.
      </td>
    </tr>

    <tr>
      <td>
        Dec 2
      </td>

      <td>
        **Stripe gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated return customer requests (CIT, customer initiated) to the gateway in order to optimize 3DS requests from Stripe.
      </td>
    </tr>
  </tbody>
</Table>

## November

| Release Date | **Feature**                    | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                           |
| :----------- | :----------------------------- | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nov 25       | **Analytics**                  | Low                  | Added two new drill-downs to the Billings Global dashboard: Product Details and Transaction and Invoice Details, providing deeper visibility into billing activity.                                                                                                                                                                                  |
| Nov 20       | **V3 API**                     | Low                  | Added the ability to choose to apply credits on a purchase or subscription.                                                                                                                                                                                                                                                                          |
| Nov 18       | **Stripe gateway**             | Low                  | Updated handling of coupons, account credits, and prorations when using Stripe Payment Elements through Third Party Checkout to avoid miscalculations.                                                                                                                                                                                               |
| Nov 18       | **Recurly Engage**             | Medium               | We've updated the look and feel of Pulse, the Recurly Engage management console. It now incorporates Recurly UI design elements to ensure a more cohesive and consistent experience alongside the rest of your Recurly platform.                                                                                                                     |
| Nov 18       | **Recurly Engage**             | Low                  | New focus state color input option for Pulse for Apple TV, Roku, Android TV devices.                                                                                                                                                                                                                                                                 |
| Nov 18       | **Recurly Engage**             | Low                  | UI enhancements to Preview tool widget to improve accessibility and functionality.                                                                                                                                                                                                                                                                   |
| Nov 18       | **Recurly Checkout**           | Low                  | Adding cookie management to Checkout.                                                                                                                                                                                                                                                                                                                |
| Nov 18       | **Recurly Admin**              | Low                  | Adding cookie management to Checkout and Recurly, including a _Cookie Settings_ option in upper right of Recurly.                                                                                                                                                                                                                                    |
| Nov 12       | **Data Exports**               | Low                  | A more modern, streamlined and easier to use UI will be available for all async data exports. These are the exports that can be requested on an ad hoc basis and downloaded once processed. The updated Exports Page UI will include easier to use filters and a more dynamic “time range” filter so users can customize their exports for download. |
| Nov 12       | **Compass Assistant**          | Low                  | Compass Assistant Chat History is now available. Clicking on a previous conversation will load that conversation and you can ask follow-up questions.   <a href="https://docs.recurly.com/recurly-subscriptions/docs/compass-assistant" target="_blank" rel="noopener noreferrer">Learn more</a>                                                     |
| Nov 4        | **Account Updater**            | Low                  | Updated handling of MCC ingestion to avoid an error upon selection and saving your merchant category code.                                                                                                                                                                                                                                           |
| Nov 4        | **Client Libraries**           | Low                  | The .NET library was updated to support the Klarna payment method.                                                                                                                                                                                                                                                                                   |
| Nov 1        | **Legacy Revenue Recognition** | Low                  | The legacy Revenue Recognition feature will sunset as of 11/1/2025. Merchants are encouraged to explore the enhanced Recurly Revenue Recognition Advanced or Standalone editions.                                                                                                                                                                    |

<br />

## October

| Release Date | **Feature**                        | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| :----------- | :--------------------------------- | :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Oct 31       | **Ebanx gateway**                  | Medium               | We will be supporting MercadoPago and Pix Automatico. These will be in a temporary EA review with Ebanx prior to availability. More information will be available once generally available.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Oct 28       | **Invoices**                       | Low                  | Introduced a new invoice setting to breakdown taxes on invoices if the merchant is integrated with Vertex.  This setting defaults to off.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Oct 28       | **Recurly Engage**                 | Low                  | New feature allowing users to search for prompts directly within the connector actions modal. This makes it much easier and quicker to find and apply the exact prompt you need.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Oct 28       | **Recurly Engage**                 | Low                  | The display of recommended prompt sizes within the Prompt Editor has been standardized.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Oct 28       | **Recurly Engage**                 | Low                  | Added automatic custom goal integration from RSM to allow Engage customers who use Recurly for subscription management to automatically track and update customer subscription statuses, such as plan changes, payment failures, and cancellations. <a href="https://docs.recurly.com/recurly-engage/docs/recurly-webhooks#/">Learn more.</a>                                                                                                                                                                                                                                                                              |
| Oct 28       | **Recurly Engage**                 | Low                  | Added a new Recurly connector action to Engage for the Update Subscription API passing a new`next_bill` parameter that allows trial start/end dates to be adjusted.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Oct 21       | **Recurly Engage**                 | Low                  | Our enhanced integration with Recurly now provides near real-time subscription status information, enabling quicker, more effective targeting and custom event tracking within Recurly Engage. <a href="https://docs.recurly.com/recurly-engage/docs/recurly-webhooks#/">Learn more.</a>                                                                                                                                                                                                                                                                                                                                   |
| Oct 21       | **Gateway Tokens**                 | High                 | When using a gateway token on a gateway, you will now be able to use that gateway token (gateway_token) on a different `gateway_code` value when routing transactions for payments via API. Keep in mind, the gateway credentials tied to the gateway_code in use must have access to the token in order for the payment to function, else invalid token responses are expected.                                                                                                                                                                                                                                           |
| Oct 21       | **Stripe gateway**                 | Medium               | Soon, Stripe gateway users will be able to take advantage of India e-mandate creation when signing up Indian users for subscriptions when using a credit card. If you are accepting payments from Indian subscribers, please read through India-specific support on our <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe#/india-mandates-with-credit-cards">Stripe gateway</a>  documentation and related RBI mandate information.                                                                                                                                                                      |
| Oct 21       | **Recurly**                        | Low                  | Replacing all Redfast verbiage with Engage.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Oct 21       | **Recurly Account**                | Low                  | Changing the email address in the "past due" banner from [support@recurly.com](mailto:support@recurly.com) to [billing@recurly.com](mailto:billing@recurly.com).                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Oct 21       | **Recurly Checkout**               | Low                  | Adding an account management link in checkout if the URL is provided in the corresponding checkout configuration.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Oct 17       | **Recurly Commerce**               | Low                  | Commerce plans support contract terms and cancellation fees.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Oct 14       | **Exports**                        | Low                  | Transactions Export - new fields will be added including payment_method_identifier, cc_last_4, expire_month, expire_year, processor_response_code, processor_response_text, issuer_response_code and billing_info_id.                                                                                                                                                                                                                                                                                                                                                                                                      |
| Oct 14       | **Gateway Configuration**          | Low                  | Minor updates to improve configuring card brands available on a given gateway. When editing, you were unable to uncheck an individual (singular) APM or card brand. Now, with the exception of Discover (which will require JCB, UnionPay, and Diners to be checked), unchecking one APM is possible again!                                                                                                                                                                                                                                                                                                                |
| Oct 14       | **Exports**                        | Low                  | Adjustments Export - new fields will be added for `price_segment_id` and `price_segment_code`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Oct 14       | **Exports**                        | Low                  | Subscriptions Export - new fields will be added for `price_segment_id` and `price_segment_code`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Oct 14       | **Compass Assistant**              | Low                  | Enhancements to Compass Assistant are now available across all active subdomains! Our conversational chatbot directs you to pages as well as use our documentation and knowledge base to help you find the solutions you need.  Compass Assistant can take action to help you create, view or update plans, add-ons and measured units. Click the sparkles at the button right to start a chat with Compass Assistant! Should a merchant wish to opt-out, please contact Support. <a href="https://docs.recurly.com/recurly-subscriptions/docs/compass-assistant" target="_blank" rel="noopener noreferrer">Learn more</a> |
| Oct 14       | **Edit Subscription**              | Low                  | A new look and feel to the plan picker on the Edit Subscription page.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Oct 7        | **Recurly Commerce**               | Low                  | Updated Recurly Commerce Special Discount, _By Quantity_, to support multiple discount tiers, which incentivizes the customer to buy more and save more.                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Oct 7        | **Analytics Explore**              | Low                  | Plan _custom fields_ and _price segment code_ will now be available in both the Transactions and Invoices analytics explores. Existing _Charges_ dimension/field name will be renamed to _Invoice Line Items_.                                                                                                                                                                                                                                                                                                                                                                                                             |
| Oct 7        | **Invoice Tax Compliance Updates** | Low                  | Updates to support tax compliance on invoices were made to display tax rate and net information and currency conversion information. In addition, products now include an optional field to add HS Code/Commodity code.                                                                                                                                                                                                                                                                                                                                                                                                    |
| Oct 2        | **Recurly.js**                     | Low                  | Updated handling of Elo BINs in Recurly.js.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Oct 1        | **Price Segmentation**             | Low                  | Plans can now have different price points for a single currency; allowing merchants to target different subscriber segments and to conduct A/B testing.  This new feature is available on create/edit plan pages, add/edit subscription pages, v3 API's, and Recurly.js.                                                                                                                                                                                                                                                                                                                                                   |

## September

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **Adyen gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Cash App Pay is now generally available to any Adyen merchant. You can learn about accepting Cash App in our dedicated documentation for <a href="https://docs.recurly.com/recurly-subscriptions/docs/cash-app-pay#/" target="_blank" rel="noopener noreferrer">Cash App</a> and <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-cash-app-pay" target="_blank" rel="noopener noreferrer">Adyen</a>, respectively. Reach out to your Adyen contact to enable the method in your gateway prior to enabling at Recurly.
      </td>
    </tr>

    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **WorldPay gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We're enabling ACH Direct Debit processing through our WorldPay connection. Learn more about <a href="https://docs.recurly.com/recurly-subscriptions/docs/ach-bank-payments#/" target="_blank" rel="noopener noreferrer">ACH</a> on <a href="https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/" target="_blank" rel="noopener noreferrer">WorldPay</a> in our dedicated documentation for the gateway.
      </td>
    </tr>

    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **Kount Fraud Management**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to avoid duplicate requests to Kount in rare cases involving 3DS rejections on Adyen.
      </td>
    </tr>

    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **Recurly Revenue Recognition Advanced (RR managed) and Standalone**
      </td>

      <td>
        Medium
      </td>

      <td>
        Addition of ‘delete functionality” in the Data Rule menu so that certain transactions (i.e.: free trials) are not included in reporting. This data will be soft deleted - meaning it will be recorded in Cost / Doc stage history tables as archived data but the transactions will not appear in the reporting. In addition there were configuration audit report fixes - enhanced endpoint to filter by entity names. Also Period ID column, Target ID column, and All periods filter were added to audit reports.
      </td>
    </tr>

    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **Recurly Revenue Recognition Standard and Advanced (RA managed)**
      </td>

      <td>

      </td>

      <td>
        Improvements to the date picker in the self onboarding dialog so that it opens to the correct period. Additionally, fixed the inverted mapping for credit event transactions (selecting Track saved as Yes, but loaded as Ignore). For users that do not have a RevRec role, the ‘Get Started’ button is no longer visible.
      </td>
    </tr>

    <tr>
      <td>
        Sept 30
      </td>

      <td>
        **Email Templates**
      </td>

      <td>
        Low
      </td>

      <td>
        Introducing 4 new email templates centered around Recurly's Pause functionality.
      </td>
    </tr>

    <tr>
      <td>
        Sept 23
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        New feature to allow export and download of experiment data.
      </td>
    </tr>

    <tr>
      <td>
        Sept 23
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor update to scheduling logic and general UI enhancement for scheduling modal.
      </td>
    </tr>

    <tr>
      <td>
        Sept 16
      </td>

      <td>
        **PayPal Complete**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor behind-the-scenes optimizations for PayPal Complete's Recurly.js implementation. No merchant or consumer-facing changes are expected.
      </td>
    </tr>

    <tr>
      <td>
        Sept 16
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor visual update to traffic allocation for experimental prompts.
      </td>
    </tr>

    <tr>
      <td>
        Sept 16
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Medium
      </td>

      <td>
        *Reports now display descriptive names instead of technical codes for field values, consistent with the UI.

        *Resolved issue where the order of segments changed after refresh; added order sequence to maintain original order.

        *Dynamic UI totals will now be shown based on filters only when the entire dataset is fetched; previous behavior is retained otherwise.

        *Fixed issue where creating an SSP configuration for the first time did not save properly; workaround via Copy is no longer required.

        *Fixed issue where Range displayed “Range is not valid” even before selection in SSP configuration.

        *Fixed Revenue Workbench issues:

        *Audit tab now displays data when Primary book is selected. *Switching from Primary book to All no longer reverts back to Primary. *Applying VC through Workbench functions no longer results in an error after switching books.
      </td>
    </tr>

    <tr>
      <td>
        Sept 9
      </td>

      <td>
        **Admin Users Export**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated from export to an explore style report with enhanced capabilities which allow for ad-hoc analysis, visualization of the data and downloadable into multiple file format types such as csv, txt, excel, etc.
      </td>
    </tr>

    <tr>
      <td>
        Sept 9
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        You can now extend the reset period days within your Prompt Guide Limits, giving you more flexibility in how you manage your campaigns.
      </td>
    </tr>

    <tr>
      <td>
        Sept 9
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        A new feature is available that enables live editing of Recurly Engage experiments. You can now directly edit various elements including variants, triggers and actions.
      </td>
    </tr>

    <tr>
      <td>
        Sept 9
      </td>

      <td>
        **Stripe gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We are updating our API version to support Klarna Recurring Line Items for subscriptions. Klarna and Elements will run through the preview endpoint `2025-04-30.preview` , while the rest of the ecosystem will run through the non-preview endpoint `2025-04-30.basil`.
      </td>
    </tr>

    <tr>
      <td>
        Sept 9
      </td>

      <td>
        **WorldPay gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to mandates and one time transactions for SEPA support.
      </td>
    </tr>

    <tr>
      <td>
        Sept 2
      </td>

      <td>
        **FreedomPay gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to enable AVS and CVV checks on customer initiated transactions within Payment Settings.
      </td>
    </tr>

    <tr>
      <td>
        Sept 2
      </td>

      <td>
        **Ebanx gateway + UPI AutoPay**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated subscription PUT validations via the V3 API to allow updates to subscriptions when using the UPI AutoPay payment method on Ebanx. This update will allow behaviors such as editing custom fields, among other things.
      </td>
    </tr>

    <tr>
      <td>
        Sept 2
      </td>

      <td>
        **Stripe gateway**
      </td>

      <td>
        High
      </td>

      <td>
        Updated the supported Stripe Client library underpinning calls to the gateway in preparation for version upgrades. No impact is expected.
      </td>
    </tr>

    <tr>
      <td>
        Sept 2
      </td>

      <td>
        **WorldPay gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        WorldPay is now an allowable gateway within the Direct Debit retries UI within Payment Settings. If you are using WorldPay with SEPA Direct Debit, you can make use of automatic retries for payments rejected due to Insufficient Funds.
      </td>
    </tr>
  </tbody>
</Table>

## August

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Aug 29
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Low
      </td>

      <td>
        * Added deleted order lines to Order Stage History as archived data.
        * Introduced Bundle Rule ID field in order lines for mapping.
        * Extended Account Type table with 10 additional segment columns to support new segments.Added a data sync API check to update client indicators only when a job is set; revalidates before saving to prevent duplicate job updates.Implemented validation for VC date.
        * Built the Workbench object and added a helper for tab switching.Added "Select All" button for Stage Area.
        * Enabled book retention from the search page.
        * Enhanced account type functionality by adding 10 new segments to `account_type_c`.
        * Enhanced Standalone Selling Price (SSP) with multiple fixes, including criteria handling for "Approved" status, Compliance Pct corrections, SSP group item download and contract link, support for BundleRuleID/BundleParentID in criteria, editable Parent Identifier in new lines, and a fix for the Format ID unit test.
      </td>
    </tr>

    <tr>
      <td>
        Aug 26
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to segment data CSV exports to better handle special characters in titles.
      </td>
    </tr>

    <tr>
      <td>
        Aug 26
      </td>

      <td>
        **Recurly Engage**
      </td>

      <td>
        Low
      </td>

      <td>
        Enhance experiment window user experience by preventing auto-close on save.
      </td>
    </tr>

    <tr>
      <td>
        Aug 26
      </td>

      <td>
        **PayPal Complete gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We are updating our currency support to include BRL, CNY, HDK, ILS, MXN, and THB to enable more processing opportunities for merchants. We will also be making minor tweaks to onboarding in Recurly Admin to allow merchants in several other countries to view PayPal Complete and onboarding without regional warnings. To learn more about <a href="https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete#/" target="_blank" rel="noopener noreferrer">PayPal Complete</a>, visit our dedicated documentation.
      </td>
    </tr>

    <tr>
      <td>
        Aug 26
      </td>

      <td>
        **v3 API**
      </td>

      <td>
        Low
      </td>

      <td>
        Adding a new optional proration setting to several v3 endpoints.
      </td>
    </tr>

    <tr>
      <td>
        Aug 26
      </td>

      <td>
        **Stripe gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We will be adding support for Indian e-mandates to support recurring processing for credit cards. This will enable Merchants who wish to expand into India with subscriptions the ability to stay compliant with RBI mandates. For more information on <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe" target="_blank" rel="noopener noreferrer">Stripe</a>, please see our dedicated documentation. Our  <a href="https://docs.recurly.com/recurly-subscriptions/docs/rbi-regulations-update#/" target="_blank" rel="noopener noreferrer">RBI mandate documentation</a> will be updated after release with new support details.
      </td>
    </tr>

    <tr>
      <td>
        Aug 20
      </td>

      <td>
        **Kount Fraud Management**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated to account code handling to avoid errors in rare cases. To learn more about <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount#/" target="_blank" rel="noopener noreferrer">Kount Fraud Management</a>, visit our dedicated documentation.
      </td>
    </tr>

    <tr>
      <td>
        Aug 20
      </td>

      <td>
        **PayPal Complete gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        If PayPal (the digital wallet) is the primary payment method for a subscription and the PayPal subscription agreement is cancelled by the subscriber within their PayPal app or otherwise outside of Recurly, Recurly will now cancel that related subscription.
      </td>
    </tr>

    <tr>
      <td>
        Aug 19
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Medium
      </td>

      <td>
        *Added display of the Initial Financial Open Period to the Revenue Settings page. *Synced RevRec activation email timing with site activation to prevent premature sends. Introduced `enabled_email_sent_at `to track email dispatch after data sync, updated cron to handle unsent emails, and modified the Snappy Activate Site endpoint to respect sync status. *Fixed overlap issue where the Recurly Resources button on the Home page covered the wizard when opened. *Auto Period Close and Period Close Checklist job refactoring *Fix auto period lag days to count complete N days *Api to purge client and client data *Hide RevRec settings for Setup Fees when no setup fee exists
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Adyen gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Minor updates to <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ideal" target="_blank" rel="noopener noreferrer">iDeal payments</a> to avoid an error for return customer signups.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to Pause events on UPI AutoPay mandates. Consumer-driven mandate pauses will be automatically paused for 1 year. Subscription pause lengths can be updated by a merchant after confirming length of pause with the consumer.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to trial handling to avoid a 1 INR charge.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Adyen gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ach" target="_blank" rel="noopener noreferrer">ACH</a> Reporting queries to avoid improper invoice status updates.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **V3 Client Libraries**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated to support returning enhanced Google Pay indicators when a DPAN is in use.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Added scroll-to-top behavior when opening the Configuration of Default Rules section.
      </td>
    </tr>

    <tr>
      <td>
        Aug 12
      </td>

      <td>
        **Anomaly Insights**
      </td>

      <td>
        Low
      </td>

      <td>
        Introducing Anomaly Insights available on all subdomains. Anomaly insights to help merchants act instantly when transactional issues arise.

        [Anomaly Insights](https://docs.recurly.com/recurly-subscriptions/docs/recurly-compass#/anomaly-insights) documentation.
      </td>
    </tr>

    <tr>
      <td>
        Aug 11
      </td>

      <td>
        **Ebanx gateway**
      </td>

      <td>
        High
      </td>

      <td>
        Updates to mandate handling related to plan amount. Mandates will be sent with a dynamic plan + 18% tolerance for amount updates. This will support add-ons and trials where taxation is necessary. Read more about mandates in our <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/" target="_blank" rel="noopener noreferrer">UPI AutoPay payment method</a> documentation.
      </td>
    </tr>

    <tr>
      <td>
        Aug 5
      </td>

      <td>
        **Compass Assistant**
      </td>

      <td>
        Low
      </td>

      <td>
        We're excited to announce the launch of Compass Assistant, now available across all active subdomains! This new conversational chatbot provides instant access to information from our product documentation and knowledge base, and can even furnish helpful code snippets for our APIs. You'll also notice that AI Answers will now direct you to Compass Assistant for a more comprehensive experience; should a merchant wish to opt-out, please contact Support.
      </td>
    </tr>

    <tr>
      <td>
        Aug 5
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Medium
      </td>

      <td>
        Revrec Enhancements in Recurly and RevRec- Removed Auto Period Close Delay for Advanced Merchants in Revenue Settings.

        Removed Auto Period Close Delay option from the Self-Service Onboarding Wizard for RA-enabled merchants.

        Fixed datepicker in the RevRec enablement dialog to display correctly in front of the dialog (CSS update only).

        Updated RevRec Enablement Alert to display the correct text and buttons based on user permissions and site configurations.

        Updated Data Sync Finished alert logic to only display after `enabled_at` is set in the group memberships table, ensuring it appears only when the site is activated.

        Added validation for VC Rules to ensure "From Date" is less than or equal to "To Date."
      </td>
    </tr>

    <tr>
      <td>
        Aug 1
      </td>

      <td>
        **MasterCard Account Updater**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updates to flow involving querying the network for updates. This modification will be in addition to the current behavior where Recurly receives push notifications on registered cards. Please see our dedicated <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater#/" target="_blank" rel="noopener noreferrer">Account Updater documentation</a> for more information.
      </td>
    </tr>

    <tr>
      <td>
        Aug 1
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Updates - removed open period logic from `infra/revrecStart` to prevent the period from reverting to the initial period. Fixed bundle rule addition issue when only one bundle rule exists under a parent item by grouping the count by bundle ID.
      </td>
    </tr>

    <tr>
      <td>
        Aug 1
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updates to mandate handling related to plan amount. Mandates will be sent with a dynamic plan + 10% tolerance for amount updates.
      </td>
    </tr>
  </tbody>
</Table>

## July

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Jul 31
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        WorldPay gateway will be enabled with SEPA processing capabilities. For more information, please see our

        [SEPA](https://docs.recurly.com/recurly-subscriptions/docs/sepa-direct-debit#/)

        and

        [WorldPay gateway](https://docs.recurly.com/recurly-subscriptions/docs/worldpaydlocal-latam-support#/overview)

        documentation after release.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of gateway-level events so that we will cancel a subscriptions when a mandate is revoked after a successful transaction. Additionally, paused subscriptions events will also pause the subscription on the Recurly platform until a consumer-driven change (cancellation or resume) is received.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Adyen Gateway | Third Party Checkout**
      </td>

      <td>
        Medium
      </td>

      <td>
        We are adding support for Direct Debit payment methods into our Adyen Web Components solution for Third Party Checkout. New payment method availability includes: ACH, SEPA, iDeal, Bancontact (renewals require SEPA), and BACS. For more information, please read our

        [Third Party Checkout](https://docs.recurly.com/recurly-subscriptions/update/docs/adyen-web-components#/)

        and

        [Adyen](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/)

        documentation.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        We are enabling support for Giact for NACHA Verification on the Adyen platform. For more information about

        [NACHA compliance](https://docs.recurly.com/recurly-subscriptions/docs/nacha-verification#/)

        , you can read our dedicated documentation. If you are using Giact on

        [Adyen](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/)

        , read through our documentation on how to enable the feature.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Recurly.js | Recurly Engage**
      </td>

      <td>
        Medium
      </td>

      <td>
        Introducing an automated integration between Recurly Subscription Management (RSM) and Recurly Engage! Current customers can take advantage of the Recurly Engage SDK within Recurly.js in all environments where Recurly.js is used including Checkout, and Hosted Account Management pages. See our dedicated documentation for more information about

        [Recurly Engage](https://docs.recurly.com/recurly-subscriptions/docs/recurly-engage-integration#/)

        .
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Commerce Hub Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Added support for Level 2 data processing. This includes purchase order number and tax details.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Added support for sending Line Items to Adyen. Review best practices when sending line items in our dedicated documentation. For more information, please see our

        [Adyen gateway](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/)

        and

        [Line Item](https://docs.recurly.com/recurly-subscriptions/docs/line-items#/)

        documentation.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to decline handling when 3DS authentication is not completed by the consumer.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Minor updates to decline handling when the Merchant ID on file is invalid at the gateway level.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Cybersource Gateway**
      </td>

      <td>
        High
      </td>

      <td>
        Updates to decline handling when the processor selected is 'Barclays' or 'Barclays2' in gateway configuration.
      </td>
    </tr>

    <tr>
      <td>
        Jul 29
      </td>

      <td>
        **Sagepay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updates to query encryption logic to enhance security.
      </td>
    </tr>

    <tr>
      <td>
        Jul 21
      </td>

      <td>
        **Salesforce Integration**
      </td>

      <td>
        Low
      </td>

      <td>
        Added new functionality Send Payment Capture Link which sends an email to the Recurly Account email. In the Recurly Admin page, a new template is available  Payment Invoice Link Email Template. [learn more](https://docs.recurly.com/recurly-subscriptions/docs/salesforce-recurly#utilizing-automatic-payment-link-in-salesforce-opportunities).

        Updates to more easily link to Recurly account information from Salesforce. For more information, please see our [Salesforce integration](tps://docs.recurly.com/recurly-subscriptions/docs/adyen#/https://docs.recurly.com/recurly-subscriptions/docs/salesforce-recurly) documentation.
      </td>
    </tr>

    <tr>
      <td>
        Jul 18
      </td>

      <td>
        **Invoice Number Prefix**
      </td>

      <td>
        High
      </td>

      <td>
        Updated Invoicing with the ability to modify invoice number sequencing to include a prefix. Invoice numbers are used for invoices as well as transactions and are sent to gateways which can have varying formatting requirements.  As such, changes to invoice numbers could impact reconciliation.
      </td>
    </tr>

    <tr>
      <td>
        Jul 18
      </td>

      <td>
        **Amazon V2 Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of Amazon pre-renewal queries related to rate limiting responses. We will retry transactions that return as rate limited moving forward.
      </td>
    </tr>

    <tr>
      <td>
        Jul 15
      </td>

      <td>
        **Stripe Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for Payment Method Configuration IDs to Third Party Checkout.
      </td>
    </tr>

    <tr>
      <td>
        Jul 15
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Enabling support for Shipping Amount. This will send the line item shipping cost to transactions sent to Adyen.
      </td>
    </tr>

    <tr>
      <td>
        Jul 15
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of Mandate Expiry dates for UPI AutoPay to extend 2 years past the initial renewal term.
      </td>
    </tr>

    <tr>
      <td>
        Jul 15
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for IDR currency on the Adyen platform.
      </td>
    </tr>

    <tr>
      <td>
        Jul 16
      </td>

      <td>
        **General Compliance Enhancements**
      </td>

      <td>
        Medium
      </td>

      <td>
        Recurly is committed to compliance and general upkeep of our systems. In doing so, several features are receiving behind-the-scenes maintenance including subscription NTID management and storage. No merchant or customer-facing facing features are impacted.
      </td>
    </tr>

    <tr>
      <td>
        Jul 8
      </td>

      <td>
        **Commerce Hub Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        The gateway will be visible in Payment Gateway onboarding.
      </td>
    </tr>

    <tr>
      <td>
        Jul 8
      </td>

      <td>
        **Emails**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated to avoid sending a 'refund' email when a chargeback occurs.
      </td>
    </tr>

    <tr>
      <td>
        Jul 8
      </td>

      <td>
        **Stripe Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of asynchronous refund status updates. If pending refunds on Stripe move to a failed state, they can be reattempted manually.
      </td>
    </tr>

    <tr>
      <td>
        Jul 8
      </td>

      <td>
        **FreedomPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated to support a 'Test Configuration' button to test credentials during testing and go-live procedures.
      </td>
    </tr>

    <tr>
      <td>
        July 8
      </td>

      <td>
        **Revenue Recognition Standard**
      </td>

      <td>
        High
      </td>

      <td>
        Revenue Recognition Self-Service Onboarding - Introduced a streamlined process for setting up and activating the RevRec self-service experience. This allows merchants using RevRec Standard and Recurly Managed RevRec Advanced to independently configure and launch their sites. This process requires the following steps to be completed before activation: -Assign Business Entity Defaults -Review All Product Settings -Configure Default Recognition Rules -Set Global Currency -Set Auto Period Close Delay -Configure Credit Handling (Advanced RevRec only) -Set Revenue Recognition Start Date
      </td>
    </tr>

    <tr>
      <td>
        July 8
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Low
      </td>

      <td>
        BigQuery Refactoring & Bug Fixes - Improved BigQuery performance through query optimization and folder restructuring. Enhanced code reusability and resolved existing query issues by rewriting problematic logic.
      </td>
    </tr>

    <tr>
      <td>
        July 8
      </td>

      <td>
        **Revenue Recognition Advanced**
      </td>

      <td>
        High
      </td>

      <td>
        New Revenue Recognition Menu - Introduced a dedicated "Revenue Recognition" section in the main navigation. Advanced merchants can access the Advanced Console, Revenue Settings, and General Ledger Accounts, while Standard merchants will see Revenue Settings and General Ledger Accounts.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for sending the expected arrival date of a physically shipped item to Adyen in API transactions. This is also in relation to Revenue Protect availability on

        [Adyen Gateway](https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium)

        . See documentation in our Adyen Gateway page for details after release.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for customer acquisition dates (account age) to Adyen in API transactions. This is also in relation to Revenue Protect availability on

        [Adyen Gateway](https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium)

        . See documentation in our Adyen Gateway page for details after release.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Chase Orbital Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Added support for an undocumented response code (9797) to the platform. This response code will be handled as a declined transaction.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Currency Support**
      </td>

      <td>
        Medium
      </td>

      <td>
        Behind-the-scenes improvements to allow more currencies to be enabled on a single gateway configuration for gateways that allow many ISO-standard currencies.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Commerce Hub Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Added support for Fiserv's newest gateway offering, Commerce Hub. See

        [documentation on Commerce Hub](https://docs.recurly.com/docs/commerce-hub#/)

        for more information on the new platform.
      </td>
    </tr>

    <tr>
      <td>
        Jul 1
      </td>

      <td>
        **Direct Debit Retry Enablement**
      </td>

      <td>
        Low
      </td>

      <td>
        Added broader support for Direct Debit retries for Adyen, Stripe, and GoCardless gateways for the following payment methods: BACS, BECS, SEPA, and ACH. See our

        [Direct Debit retries](https://docs.recurly.com/docs/sepa-retries#/)

        documentation for more information.
      </td>
    </tr>
  </tbody>
</Table>

## June

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        **Bug Fixes**

        Resolved issue causing duplicate POB rule entries.

        Fixed Issue with Saving Multi-Element POB Rules.

        Fixed UI total display when all data fits on the screen.

        Addressed unauthorized error appearing on UI after login.

        Corrected redirection link to Recurly App on authentication click.

        Updated default user role to "No Access".

        Resolved a race condition issue that occurred when users updated multiple contract modifications simultaneously.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Low
      </td>

      <td>
        Config Audit for Scheduled Jobs -  Config audit reports now include changes made to scheduled jobs.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Align Credit Journal Accounting with Invoice Accounting -  The journal entries for credits are now aligned with the invoice accounting. The ledger accounts used in invoice accounting would be considered for CM/CMR accounting entries, when the CM/CMR does not have accounts present then the system reads from the associated invoices or Subscriptions
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Low
      </td>

      <td>
        Activate Multi-Element Revenue Rule for RA-Enabled Merchants -  The multi element POB rule support is extended to Recurly Managed merchants too.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Import only Subs/Orders and auto create the billing records for Non Recurly data -  This feature allows businesses to import just their subscription or order data into Recurly Revenue Recognition. The system will automatically create the related billing records, saving time for companies that use external systems to manage subscriptions.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Auto-fetch exchange rates for non-Recurly data -  This feature automatically retrieves and applies the correct exchange rates for contracts/subscriptions and invoices associated with subscriptions that are created outside the Recurly platform.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        High
      </td>

      <td>
        Referenced Credit Standalone Treatment Credit Memos for which the invoice is not present in Revenue Recognition will now be collected and processed as a standalone invoice with a negative amount.
      </td>
    </tr>

    <tr>
      <td>
        Jun 30
      </td>

      <td>
        **Revenue Recognition**
      </td>

      <td>
        Low
      </td>

      <td>
        Invoice Sync Check in Auto Period Close Job -  Added a check in the auto period close job to ensure invoice counts are synced before closing the period for standard merchants.
      </td>
    </tr>

    <tr>
      <td>
        Jun 24
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for sending the Shipping Method "name" to Adyen in API transactions. This is also in relation to

        [Adyen Gateway](https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium)

        . See documentation in our Adyen Gateway page for details after release.
      </td>
    </tr>

    <tr>
      <td>
        Jun 24
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support via V3 API to pass in Adyen's Revenue Protect Risk Profile IDs on API driven transactions. Documentation will be added to the V3 API upon release. Read more about

        [Recurly's Revenue Protect support ](https://docs.recurly.com/docs/adyen#/revenue-protect--protect-premium)

        in our Adyen documentation.
      </td>
    </tr>

    <tr>
      <td>
        Jun 24
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Enabled support for Adyen's token update lifecycle webhooks for credit cards. If you are using Adyen tokens for card processing and updates occur at the Gateway level, Recurly will receive those updates to ensure the card number and/or expiration date shown in billing information is up to date. This will require enabling this event in your Adyen settings to take advantage of the new behavior.
      </td>
    </tr>

    <tr>
      <td>
        Jun 24
      </td>

      <td>
        **Checkout**
      </td>

      <td>
        Low
      </td>

      <td>
        Fixed an issue where country is required when the Address Requirement is set to 'No Address'.
      </td>
    </tr>

    <tr>
      <td>
        Jun 18
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of failed UPI AutoPay signups to avoid errors when re-subscribing.
      </td>
    </tr>

    <tr>
      <td>
        Jun 17
      </td>

      <td>
        **Cybersource Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated to support Google Pay transactions.
      </td>
    </tr>

    <tr>
      <td>
        Jun 17
      </td>

      <td>
        **Cybersource Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of phone numbers to avoid errors in rare cases where a partial phone number is present.
      </td>
    </tr>

    <tr>
      <td>
        Jun 17
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Enabled Late failure / Chargeback Invoice behavior for Adyen ACH transactions and invoices. In the event an ACH transaction returns after initial processing and the status is _not_ "Insufficient Funds", a chargeback Invoice will be created and recorded. You can read more about this feature and how to enable it in our

        [Chargebacks / late failures for Direct Debit](https://docs.recurly.com/docs/chargebacks-for-direct-debit#/)

        documentation.
      </td>
    </tr>

    <tr>
      <td>
        Jun 16
      </td>

      <td>
        **App Management MRR Dashboard**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated the App Management net MRR chart from a bar to a line chart to be in parity with the Recurly App MRR Dashboard.
      </td>
    </tr>

    <tr>
      <td>
        Jun 16
      </td>

      <td>
        **Business Entities Dashboard**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated descriptions for New & Renewing Billings.
      </td>
    </tr>

    <tr>
      <td>
        Jun 16
      </td>

      <td>
        **Transactions Explore**
      </td>

      <td>
        Low
      </td>

      <td>
        Added "cc_payment_id" field which is the unique identifier for a credit card.
      </td>
    </tr>

    <tr>
      <td>
        Jun 16
      </td>

      <td>
        **Invoice Explore**
      </td>

      <td>
        Low
      </td>

      <td>
        Added "cc_payment_id" field which is the unique identifier for a credit card.
      </td>
    </tr>

    <tr>
      <td>
        Jun 10
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabled support for the `CAPTURE_FAILED` event. Capture failures will mark Purchase transactions as declined. If you are using separate Auth and Capture, and the Capture fails, you can re-try the capture. This will require enabling this event in your Adyen settings to take advantage of the new behavior.
      </td>
    </tr>

    <tr>
      <td>
        Jun 10
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Enabled support for sending shipping addresses to Adyen. If you are providing a shipping / delivery address in your transactions, or a consumer has one on file, the information will be sent to Adyen.
      </td>
    </tr>

    <tr>
      <td>
        Jun 10
      </td>

      <td>
        **PayPal Complete Gateway**
      </td>

      <td>
        High
      </td>

      <td>
        Updated our integration to support WebView browsers when using PayPal Complete with Recurly.js. This will enable Recurly.js functionality for PayPal when viewing web pages within the container of a social media application such as Facebook or Instagram. See our

        [Recurly.js PayPal documentation](https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete)

        for more information about our PayPal Complete integration, and the

        [Recurly.js browser support documentation](https://docs.recurly.com/recurly-subscriptions/v1.2/docs/support#/)

        for more information about the environments we support with Recurly.js.
      </td>
    </tr>

    <tr>
      <td>
        Jun 10
      </td>

      <td>
        **V3 API | Verify Routes**
      </td>

      <td>
        High
      </td>

      <td>
        Updated the V3

        [Verify Billing Info](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info)

        and

        [Verify CVV](https://recurly.com/developers/api/v2021-02-25/index.html#operation/verify_billing_info_cvv)

        endpoints to support 3DS and Recurly.js tokens. For SCA-regulated Merchants, you can use these new endpoints to verify consumer SCA prior to unpausing or reactivating subscriptions. These paths are also useful for other 3DS, or verification related activities such as account takeover mitigation, and other KYC / security reasons. Read more in our dedicated guide on

        [using Stored Billing Information in Recurly.js.](https://docs.recurly.com/recurly-subscriptions/v1.1/docs/using-3d-secure-with-stored-billing-information#/)

        . This update also includes a Recurly.js client update. More information will be available in Recurly.js docs after release.
      </td>
    </tr>

    <tr>
      <td>
        Jun 9
      </td>

      <td>
        **General Security Enhancement**
      </td>

      <td>
        High
      </td>

      <td>
        We will be making scheduled maintenance updates for security purposes that will include a Recurly.js client update. No functional changes are expected. Recurly.js can be used natively but is also used in HPP and Recurly Checkout products, which are included in this update.
      </td>
    </tr>

    <tr>
      <td>
        Jun 3
      </td>

      <td>
        **PayPal Complete Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of status updates for PayPal transactions using a bank account as a funding source to avoid transactions suck in pending state.
      </td>
    </tr>

    <tr>
      <td>
        Jun 3
      </td>

      <td>
        **Webhooks**
      </td>

      <td>
        Medium
      </td>

      <td>
        Added webhook support for `payment.succeeded` event to enable events firing when UPI AutoPay transactions are updated asynchronously.
      </td>
    </tr>

    <tr>
      <td>
        Jun 3
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of Late Failure (Chargeback) invoices for ACH Bank payments to ensure transactions that fail asynchronously are invoiced or marked failed appropriately. Transactions that experience a return due to insufficient funds (R01) will be marked as declined and have the associated invoice marked Past due so the invoice collection can be reattempted.
      </td>
    </tr>

    <tr>
      <td>
        Jun 3
      </td>

      <td>
        **Vantiv Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Remapped a response code (218) to a soft decline due to remapping by WorldPay.
      </td>
    </tr>
  </tbody>
</Table>

## May

<Table align={["left","center","left","left"]}>
  <thead>
    <tr>
      <th>
        Release Date
      </th>

      <th>
        **Feature**
      </th>

      <th>
        **Potential Impact**
      </th>

      <th>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        May 27
      </td>

      <td>
        **PayPal Complete Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated support for webhooks to disable deleted tokens when a consumer cancels their agreement via PayPal directly. When Recurly wallet is in use, if the token is the primary billing info, deactivation is not possible.
      </td>
    </tr>

    <tr>
      <td>
        May 27
      </td>

      <td>
        **Amazon Pay V2 Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of Charge Permission IDs to query status prior to transaction processing. This will gather the chargeable 'status' of a buyer's Amazon payment methods and reduce declines. We will also be updating transaction params to include the Charge Permission ID status in the event of a decline, and closing Charge Permission IDs when subscriptions expire.
      </td>
    </tr>

    <tr>
      <td>
        May 27
      </td>

      <td>
        **V3 API Subscription Change**
      </td>

      <td>
        Medium
      </td>

      <td>
        Considered a _breaking change_ -- updated the validation messaging so that it matches the public API documentation.
      </td>
    </tr>

    <tr>
      <td>
        May 27
      </td>

      <td>
        **Plan Configuration UI Updates**
      </td>

      <td>
        Low
      </td>

      <td>
        Replacing the toggles for Free Trial and Setup Fee with checkboxes.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Ebanx Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Several invalid actions will be blocked based on the UPI payment method usage and presence on a given account. Please see list of invalid actions on the UPI AutoPay and Ebanx gateway pages respectively. Examples include multiple subscriptions on a single customer account, and one-time transactions.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Adyen Gateway | 3DS**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of 'origin' field to avoid errors. Origin is sent when a referring URL for **3DS** (such as with R.js and Checkout) is present.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **V3 Client Libraries**
      </td>

      <td>
        Medium
      </td>

      <td>
        Several origin enums will be added to the V3 client libraries.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Stripe Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of mandate reference data for applicable payment methods (Direct Debit). Mandate references will appear in UIs and API response payloads where applicable, and if available from the gateway.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Adyen Gateway | iDeal in Recurly.js**
      </td>

      <td>
        Low
      </td>

      <td>
        When using iDeal via Recurly.js, if the consumer cancels out of their consumer authorization flow modal, the subscription associated with the customer will be expired automatically.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        When enabled in your Adyen Gateway Webhook configuration, the Expired Authorization webhook will now mark uncaptured, expired authorization transactions as voided. You can enable this webhook in your Adyen Gateway settings (at the gateway), with no configuration on the Recurly site. See Adyen gateway setup instructions for additional details on webhook configuration.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **V3 API Invoice Preview**
      </td>

      <td>
        Low
      </td>

      <td>
        Update v3 api invoice response to include subtotal after discount.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Compass Insights**
      </td>

      <td>
        Low
      </td>

      <td>
        Adding feedback options (thumbs up or down) to each insight which will be visible with mouse hover-over.
      </td>
    </tr>

    <tr>
      <td>
        May 20
      </td>

      <td>
        **Checkout**
      </td>

      <td>
        Low
      </td>

      <td>
        Introducing a new Checkout configuration option that, if enabled, will display a recurring charge consent message and checkbox in Checkout _if_ there are recurring billable items in the cart.
      </td>
    </tr>

    <tr>
      <td>
        May 19
      </td>

      <td>
        **Recurly.js, HPP, Checkout**
      </td>

      <td>
        High
      </td>

      <td>
        We will be making scheduled maintenance updates for security purposes that will include a Recurly.js client update. No functional changes are expected.
      </td>
    </tr>

    <tr>
      <td>
        May 14
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Adyen (Third Party) Network Token usage on a per transaction basis will be reported in UIs and gateway params via API when applicable. If you have Network Tokens enabled at the Adyen level, you will be able to see when they are used on a transaction moving forward.
      </td>
    </tr>

    <tr>
      <td>
        May 14
      </td>

      <td>
        **Braintree Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        We will be updating the Braintree SDK version to 3.118.2 in Recurly.js. This will enable MPAN creation for Apple Pay transactions.
      </td>
    </tr>

    <tr>
      <td>
        May 13
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated Adyen Drop-in Components to ensure proper iDeal bank redirect handling in Recurly.js
      </td>
    </tr>

    <tr>
      <td>
        May 13
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Recurly transaction detail UIs will now show the Chargeback reason code associated with a chargeback invoice.
      </td>
    </tr>

    <tr>
      <td>
        May 13
      </td>

      <td>
        **Plan Configuration**
      </td>

      <td>
        Low
      </td>

      <td>
        Redesigned the Create Billable Add-on UI component when choosing a Tiered, Volume, or Stairstep pricing model; impacting both the Create and Edit plan pages.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Stripe Gateway** | **Third Party Checkout**
      </td>

      <td>
        Low
      </td>

      <td>
        Enabling Third Party Checkout: Stripe Elements with Klarna BNPL, Pay Now, and Pay Later, as well as iDeal payment methods. See the <a href="https://recurly.com/developers/guides/third-party-checkout-stripe-elements.html">Third Party Checkout developer guide</a> for more details.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Stripe Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        We are adding support for Chargebacks to the gateway. Chargebacks are delivered via webhooks, but no additional configuration is necessary. Reach out to Recurly Support to enable them via a special feature flag.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Hosted Page settings**
      </td>

      <td>
        Low
      </td>

      <td>
        Introduced a warning banner to warn users of FTC regulations when disabling the 'Cancel subscription' setting. For more information on FTC rulings around subscription cancellation, see <a href="https://www.ftc.gov/news-events/news/press-releases/2024/10/federal-trade-commission-announces-final-click-cancel-rule-making-it-easier-consumers-end-recurring">the press release on the FTC website</a>.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Compass Insights**
      </td>

      <td>
        Low
      </td>

      <td>
        Added 3 new insights to the Welcome page:

        1. Daily Subscriber Churn Trends
        2. Daily Billings Trends
        3. Monthly Recovered Revenue Trends (Recurly Value)
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Email Templates**
      </td>

      <td>
        Low
      </td>

      <td>
        Introduced a fourth option for Audience Criteria when creating alternative email templates
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **Gateway Token Handling**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated handling of gateway tokens to that gateway tokens referenced in billing information updates that cause a _decline_ do not override existing data.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **WorldPay Gateway**
      </td>

      <td>
        Low
      </td>

      <td>
        Updated handling of refund failures on the gateway.
      </td>
    </tr>

    <tr>
      <td>
        May 6
      </td>

      <td>
        **PayPal Complete Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Updated Recurly.js to support passing the gateway_code value for PayPal Complete.
      </td>
    </tr>

    <tr>
      <td>
        May 5
      </td>

      <td>
        **Adyen Gateway**
      </td>

      <td>
        Medium
      </td>

      <td>
        Minor updates to improve authorization rates for card billing information updates.
      </td>
    </tr>
  </tbody>
</Table>

## April

| Release Date | **Feature**                                | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                |
| :----------- | :----------------------------------------- | :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| April 29     | **Braze**                                  | Low                  | Adding two new Braze data centers, US-10 and IN-01.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                |
| April 29     | **Plan Configuration**                     | Low                  | Introducing a new currency picker to the Create and Edit Plan pages.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                |
| April 29     | **Stripe Gateway**                         | Low                  | Adding support for Late Failures/Chargebacks to Direct Debit payment methods. Additionally, mandate status display will accompany this release.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                |
| April 29     | **Stripe Gateway**                         | **Gateway Routing**  | Medium                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Updated behavior in gateway routing to ensure bank details that are not Stripe Payment Tokens are routed to the Stripe Gateway.                                                                |
| April 29     | **Ebanx Gateway**                          | Low                  | Updated available regions when onboarding the gateway.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 29     | **WorldPay Gateway**                       | Low                  | Updated available regions when onboarding the gateway.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 29     | **General + Security Enhancements**        | High                 | Recurly is committed to compliance and general upkeep of our systems. In doing so, several features are receiving behind-the-scenes updates that may affect front-end features including [Recurly.js](https://recurly.com/developers/reference/recurly-js/), [Checkout](https://docs.recurly.com/docs/checkout#/) and [HPP](https://docs.recurly.com/docs/hosted-payment-pages#/) (Hosted Pages), Data Collectors for 3DS and Kount, and Redirect Payment Methods. Specific payment methods or redirect features include, but are not limited to: PayPal, PayPal Complete, 3DS Challenge windows, iDeal and Klarna Debit Risk (Sofort), and Amazon Pay (v1 and v2). Learn more about our [security](https://docs.recurly.com/docs/security#/) and [compliance](https://docs.recurly.com/docs/compliance#/) practices in our documentation. |                                                                                                                                                                                                |
| April 22     | **Order Number Prefix**                    | Low                  | Updated title and text to be more clear and consistent and updated the hint for valid characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                |
| April 22     | **Braintree Gateway**                      | Medium               | Updated behind-the-scenes query behavior to ensure "in-flight" transactions' status are not inaccurately updated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                |
| April 18     | **WorldPay Gateway**                       | Medium               | Updated handling of MOTO transactions to correct intermittent payment failures.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                |
| April 18     | **Recurly.js                               | Checkout/HPP**       | HIgh                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Updated handling of Recurly.js tokens to address an error in processing related to 3DS handling. This updated addresses direct Recurly.js integrations and usage of Checkout and Hosted Pages. |
| April 17     | **Ebanx Gateway**                          | Low                  | Updated to send additional customer data to the platform including address, phone and email information.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                |
| April 15     | **Explore Assistant**                      | Low                  | A new natural language chat interface that returns site data in the form of charts and graphs.  It can be found within Analytics.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                |
| April 15     | **Revenue Recognition**                    | High                 | Period Close Automation to ensure accurate and consistent monthly closures. The process starts with four system-defined tasks, and users can add custom, site-specific tasks to meet their unique requirements. This feature ensures a consistent and error-free period close by preventing missed steps, reducing manual and reconciliation errors, and detecting unresolved issues before closure. It also standardizes the process across all monthly cycles for greater reliability.                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                |
| April 15     | **Revenue Recognition**                    | Low                  | POB Rule: Users can upload and download POB rules.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                |
| April 15     | **Ebanx Gateway**                          | Low                  | Added support for full refunds to Ebanx. Additionally, UPI mandates will not be created if a chosen plan does not have INR currency enabled.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                |
| April 15     | **Activity Logs**                          | Low                  | The subscription activity log will be updated if a chargeback triggered the subscription to expire for fraud or service-based chargeback reasons.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                |
| April 15     | **Adyen Gateway**                          | Low                  | Updated iDeal support in Recurly.js to support new streamlined redirects related to bank selection.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                |
| April 15     | **Stripe Gateway**                         | Medium               | Stripe gateway now supports basic chargeback management, including lost chargeback display in Recurly.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 11     | **Stripe Gateway**                         | Medium               | Updated Connected Accounts to enable merchant-configuration of payment methods within the Stripe Dashboard. Additionally, updated supported payment methods to block methods Recurly does not support.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 8      | **WorldPay Gateway**                       | Medium               | Added support for Online Refunds to the platform. WorldPay will enable Online Refund behavior to all merchants this year. No effort from merchants is expected with this change.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                |
| April 8      | **FreedomPay Gateway**                     | Low                  | Introducing FreedomPay to the Recurly Platform! This gateway supports tokenized card payments for merchants with Omnichannel use cases where the subscription begins its life in a card-present environment. Learn more about [FreedomPay](https://docs.recurly.com/docs/freedompay#/) in our dedicated documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 8      | **Ebanx Gateway** with UPI AutoPay         | Low                  | Introducing Ebanx, with UPI AutoPay for recurring subscriptions. This brand new gateway and payment method supports customers in India who want to use the UPI App to sign up for subscriptions. Learn more about [UPI AutoPay](https://docs.recurly.com/docs/upi-autopay#/) and [Ebanx](https://docs.recurly.com/docs/ebanx-gateway#/) in our dedicated documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                |
| April 8      | **V3 Client Libraries**                    | Medium               | Updated enums to support `upi_vpa` for UPI AutoPay on Ebanx.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                |
| April 4      | **iOS SDK**                                | Low                  | Updated SDK to resolve Swift build errors.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                |
| Apr 1        | **Create subscriptions with date in past** | Low                  | Ability to add a date in the past when creating a subscription.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                |
| April 1      | **Stripe Gateway**                         | Medium               | Adding support for ACH, SEPA, BACS, and BECS through Stripe Elements. Read through our [Third Party Checkout guide](https://recurly.com/developers/guides/3rd-party-checkout.html) for more information.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                |
| April 1      | **Adyen Gateway**                          | Low                  | Adding support for ACH, SEPA, and BACS through Adyen Components x Recurly.js.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                |
| April 1      | **Kount Fraud Management**                 | Medium               | Adding support for Apple Pay fraud scrubbing through Kount. Read more about Kount on our dedicated [fraud management](https://docs.recurly.com/docs/fraud-management#/) documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                |
| April 1      | **WorldPay Gateway**                       | Low                  | Removed the `tax_identifier_type` parameter requirement when processing in LATAM regions. No integration changes are necessary, but this will allow processing in additional LATAM regions that do not support documented tax types. Read more about [Worldpay LATAM support ](https://docs.recurly.com/docs/worldpaydlocal-latam-support#/) in our documentation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                |
| April 1      | **Stripe Gateway**                         | Low                  | Added support for CoBadge behavior on the Stripe gateway in Recurly.js. Please look at our [Cobadged Guide](https://recurly.com/developers/guides/co-badge.html) for more details on implementation. **Pulled from Release**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                |

## March

| Release Date |              **Feature**              | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| :----------- | :-----------------------------------: | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mar 25       |           **Brand Refresh**           | Low                  | New styling, font, and colors across all pages in Recurly.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Mar 25       |          **Recurly Compass**          | Low                  | The Compass suite of features include AI search capabilities called AI Answers in the left navigation, Compass Playbooks also in the left navigation, and performance Insights on the homepage.  [Learn more about Recurly Compass](https://docs.recurly.com/docs/recurly-compass#/)                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Mar 20       |             **Apple Pay**             | Medium               | Updated handling of supported countries to allow returning the correct country availability via API.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Mar 18       |          **Invoice Explore**          | Low                  | Added shipping address and custom fields for accounts, subscriptions, and charges.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Mar 18       |        **Transaction Explore**        | Low                  | Added shipping address and reorganized the layout by moving charge, subscription and account related custom fields to their appropriate sections.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Mar 18       |           **Vantiv Gateway**          | Low                  | Updated handling of UnionPay cards on the platform for streamlined authorizations.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Mar 18       |          **WorldPay Gateway**         | Low                  | Updated handling of UnionPay cards on the platform for streamlined authorizations.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Mar 18       |           **Stripe Gateway**          | Low                  | Adding support for Payment Method and Customer (gateway token) Lifecycle events and Transaction Lifecycle events. See [Stripe documentation](https://docs.recurly.com/docs/stripe#/) for details.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Mar 12       | **Two Factor         Authentication** | Medium               | For users of the two factor (2FA) authentication Authenticator App, a new TOTP (time-based one-time password) migration wizard will guide users through the migration process. The existing TOTP service will be deprecated on 3/5/2025. Users must either upgrade or disable 2FA.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Mar 11       |       **CheckCommerce Gateway**       | Low                  | During onboarding, the sidebar application will display an email instead of an application button.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Mar 11       |      **VAT Currency Conversion**      | Low                  | EU VAT rules require the VAT amount on an invoice to be displayed in the local currency of the customer. This applies to countries who fall within the EURO currency (eu member states) and GBP currency (uk). [VAT Currency Conversion Documentation](https://docs.recurly.com/docs/eu-vat-2015#vat-currency-conversion)                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Mar 10       |        **Gateway Enhancements**       | Medium               | Rolled out previously-implemented improvements to card on file handling for gateways including: Stripe, Adyen, Braintree, Cybersource, Chase Orbital, WorldPay, Authorize.net, Payeezy, First Data, TSYS, and AmazonV2. No integration changes are expected in most cases. Please see notes on respective payment method pages, depending on your integration, specific to return customers. [3DS](https://docs.recurly.com/docs/-3d-secure#/best-practices), and Device-Wallet Methods such as [Apple Pay](https://docs.recurly.com/docs/apple-pay-on-the-web#/prerequisites--supported-gateways) and [Google Pay](https://docs.recurly.com/docs/google-pay#/recurlyjs-integration) may need modification if you allow return customer flows. |
| Mar 3        |         **Braintree Gateway**         | Low                  | Improved response code handling to retry additional soft-declined card transactions moving forward.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Mar 3        |        **Cybersource Gateway**        | Medium               | Added support for enforcing 3DS via `challengeCode`on certain Cybersource processors. Read more in our [Cybersource documentation](https://docs.recurly.com/docs/cybersource#/step-5-configure-your-3ds2-support-optional) .                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Mar 3        |           **Vantiv Gateway**          | Low                  | Added new response codes to our system to ensure proper handling of new decline codes.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## February

* 2/26/2025: **WorldPay Gateway** - Added support for passing Sales Tax to the gateway.
* 2/26/2025: **Vantiv Gateway** - Added support for two new response codes: 142 and 141. These are associated with Prepaid cards.
* 2/18/2025: **V3 Libraries** - updated to support new `payment_gateway_references` parameters.
* 2/18/2025: **Vantiv Gateway** - added support for response code 378 on the gateway.
* 2/4/2025: **Check Commerce gateway** - updated endpoint for sandbox Check Commerce to support new gateway development endpoint.
* 2/4/2025: **Vantiv Gateway** - Updated handling of response codes 229 and 992 on the gateway.

## January

* 1/28/2025: **Cybersource gateway** - Enable adding the P12 certificate to gateway configuration. This will be required for all Cybersource merchants before Feb 13th, 2025. Check app notifications for details, or visit our instructions on the [Cybersource documentation](https://docs.recurly.com/docs/cybersource#configuring-cybersource-gateway-in-recurly).
* 1/21/2025:**Adyen gateway**-- Enabled SEPA retry capabilities when using Adyen gateway tokens. Read more about [SEPA retries](https://docs.recurly.com/docs/sepa-retries) on our dedicated documentation page.
* 1/21/2025: **ApplePay** -- Support tracking MPAN and reporting for merchant-derived tokens.
* 1/21/2025:  **Webhooks**- Expanded the webhooks auto-pause functionality to production merchant sites for webhook endpoints that have not responded with a 2xx status code for multiple consecutive days.
* 1/21/2025: **Webhooks**- Added the notification ID to the webhook headers of JSON formatted webhooks.
* 1/21/2025:  **Password criteria**- Upon the next user password expiration, there will be a new password length requirement where length must be at minimum 12 characters long with at least one numeric character.
* 1/14/2025: **Adyen gateway**- We've added support for ISK and CLP zero-decimal currencies. Please see [Adyen documentation for special considerations](https://docs.recurly.com/docs/adyen#special-currency-considerations) when using these currencies.

# 2024

## December

* 12/17/2024: **Recurly.js** -  Added support for displaying the card issuing country, PCI-compliant masked card data (first-six/last four), expiry info, and funding source.
* 12/17/2024: **AmazonPay V2**-  Added support for EU/UK 3DS and Multi-currency support.
* 12/11/2024:**Cybersource gateway** - Added support for Auth and Capture transactions to the platform. Read more about [Auth and Capture](https://docs.recurly.com/docs/auth-and-capture) in our helpful guide.
* 12/12/2024: **Access Invoice through RevRec** -  Users can now access invoice through RevRec by clicking on the hyperlink. 12/12/2024: **View Profile Page from RevRec** -  Users can now navigate to the user profile page by clicking on View Profile on top-right dropdown in Revrec.
* 12/11/2024: **Vantiv gateway**: Added some helpful text at the top of the gateway configuration page to assist with proper Merchant ID configuration.
* 12/10/2024: **Alternate Email Templates**: Merchants on Recurly's Elite plans can now create up to 20 total email variations for each email template, including custom headers and footers to reflect accurate brand logos and information within emails. This allows organizations to tailor customer communications towards the appropriate subscriber segments, such as by the entity(ies) they subscribe to, or their geographic location. [Learn more](https://docs.recurly.com/docs/alternate-email-templates).
* 12/10/2024: **Subscription Entity Assignment**: Consolidate all of your brands and subsidiaries on a single Recurly Site, allowing for a customer account to subscribe to many of your business entities/brands at a single point in time. Requires a Recurly Elite plan. [Learn more](https://docs.recurly.com/docs/multiple-business-entities#apply-an-entity-to-a-customers-subscription).

## November

* 11/26/2024: **Vertex Transaction Type**: The Vertex Transaction Type field is a field only available for merchants with Vertex integrations, and requires a Recurly Support ticket to enable. Please see our [product documentation](https://docs.recurly.com/docs/vertex#vertex-transaction-type-field) for more information.
* 11/20/2024: **Amazon V2 gateway**: Added support for sending the merchant site name and customer note (populated via the invoice or plan description) to Amazon.
* 11/13/2024: **Braintree gateway**: Added support for PHP, MYR, TWD currencies when using PayPal tokens.
* 11/6/2024: **Amazon V2 gateway**: Updated handling of response data to have more verbose details in transaction records.

## October

* 10/29/2024: **Stripe gateway**: Upgraded to the latest API and SDK versions. No integration changes are necessary.
* 10/22/2024: **Revenue Recognition Standalone**:  Revenue Recognition Standalone allows non-Recurly merchants to automate their revenue recognition (ASC 606/IFRS 15) and expense accounting (ASC 340-40). Non-Recurly merchants can import their external data, including subscriptions, invoices, credits, and expenses, via the RevRec APIs or through manual file uploads. Additionally, this module includes the essential admin features needed within the Recurly app.
* 10/22/2024: **Stripe gateway**: Added support for authorization code display in UIs and APIs.
* 10/22/2024: **Cybersource gateway**: Minor updates to 3DS payload details, to support Visa required fields including browser info and phone number details. No changes to 3DS behavior are expected.
* 10/22/2024: **Checkout** Announcing new levels of customization and versatility for merchants using Recurly’s Checkout experience. Recurly Checkout is the new standard for fast and frictionless checkout, allowing you to easily create and launch a highly customizable and secure subscription payment experience. [Learn more about the new Recurly Checkout](https://docs.recurly.com/docs/checkout).
* 10/22/2024: **Multiple Business Entity Analytics** Recurly has added a new dashboard, the Business Entities Overview dashboard, to help provide key insights into metrics like MRR, churn, expansion, and growth within each of their business entities supported on a single site. Please see our [product documentation](https://docs.recurly.com/docs/business-entities-overview) for more information.
* 10/22/2024: **Invoice Explore** Launched Invoice Explore which will allow building reports and visualizations related to invoices including those without associated transactions ie. account credits and trials.
* 10/15/2024: **Braze Enhancements** Recurly has added in additional fields to custom events and custom attributes, as well as the ability to omit account attributes to be set in the Braze profile.
* 10/15/2024: **Debt Collection Email** Recurly has added support for merchant to opt into sending payment-related emails between the hours of 2-4PM ET daily to adhere to the federal law about not communicating with customers about money owed. Please see our [product documentation](https://docs.recurly.com/docs/email-templates#debt-collection-email-notifications) for more information.
* 10/8/2024: **Vantiv (Litle Online) gateway**: Added support for sending the original Invoice number to the gateway on refunds. This will help merchants associate refunds with their original purchase request.
* 10/1/2024: **Braintree gateway:** Added support for Proactive 3D-Secure Authentication through Recurly.js. Please see our [Recurly.js documentation](https://recurly.com/developers/reference/recurly-js/#3d-secure) for more information.
* 10/1/2024: **Adyen gateway:** Minor updates to 3DS payload details, to support new required fields in Adyen's documentation. No changes to 3DS behavior are expected.
* 10/1/2024: **Adyen gateway**: Updated Sofort Logos to display as Klarna Debit Risk. This is only a branding change and does not imply BNPL support. Please see our [product documentation for Sofort/Klarna Debit Risk](https://docs.recurly.com/docs/adyen#adyen-sofort--klarna-debit-risk) for more information.

## September

* 9/26/2024: **Cybersource gateway**- Updated handling of cryptograms for Network tokens to ensure processing excellence.
* 09/24/2024: **Fixed amount in product bundle** - Revenue Recognition Advanced users can now define a product bundle in RevRec by enabling one line as a fixed amount.
* 09/24/2024: **Contract ID field in SSP** - Revenue Recognition Advanced users can select contract ID  as part of their grouping criteria for defining SSPs.
* 09/24/2024: **Rules section of datasets** - In the new UI design for Revenue Recognition Advanced users, the rules part of the dataset is seen on a different tab. By clicking on the rules, the user can add or upload the dataset rules.
* 9/24/2024: **Braintree gateway**- Added support for Google Pay. Please see [Google Pay documentation](https://dash.readme.com/project/reference-docs/v1.0/docs/google-pay) for more information.
* 9/11/2024: **Cybersource gateway**- Added support for returning request ID and capture reconciliation ID in API responses.
* 09/11/2024: **SingleSignOn** - Revenue Recognition Advanced login/logout is now in sync with the Recurly login/logout. While in Revenue Recognitions Advanced, users can navigate to the Recurly app by clicking on the Recurly logo on RevRec. Users can toggle between different sites from RevRec.
* 09/11/2024: **Gateway Enhancements** - Made improvements to card on file handling for gateways including: Stripe, Adyen, Braintree, Cybersource, Chase Orbital, WorldPay, Authorize.net, Payeezy, First Data, TSYS, and AmazonV2. No integration changes are expected in most cases. Please see notes on respective payment method pages depending on your integration specific to return customers.
* 9/4/2024: **Worldpay gateway**- Added support for additional response codes related to virtual card numbers.

## August

* 8/20/2024: **Exposing Geocode field for Vertex customers** - In every tax response call from Vertex, there is a "geocode" identifier passed that serves as a specific way to pinpoint the location/address that was used for tax calculation on the invoice. This field provides accurate reporting for tax to state and local tax authorities. This field is queryable in both API versions, and will also show the corresponding values populated in the "geo_code" field within the Adjustments-Taxes export when a merchant has Vertex enabled on their site. [Learn more](https://docs.recurly.com/docs/adjustments-taxes-export#version-7---may-15-2023)
* 8/20/2024: **Line-Item Refunds** - Merchants can now apply specific dollar and cent refund amounts, or percentage amounts, to individual line items on an invoice. This allows merchants to make specific amount refunds to one or many items on an invoice and _not_ others, ensuring they are only applying refund amounts to the desired individual invoice items. This is also supported in both API V2 and V3, and is only available for merchants with Only Bill What Changed and Credit Memos feature flags enabled on their sites. Learn more about Recurly's flexible refund options [here](https://docs.recurly.com/docs/invoice-management#refunds).
* 8/14/2024: **NetSuite Integration** - Enhancements to Error Reports have been made! [Learn more](https://docs.recurly.com/docs/recurly-for-oracle-netsuite) about our NetSuite integration.
  * Updated the data included in error reports for more efficient review.
  * Error reports will now be provided through Google Drive.
* 8/13/2024: **Kount** now supports Authorize only transactions. If you are passing Auth and Capture transactions, you can now take advantage of the fraud-reduction benefits of Kount. Learn more about [separate Auth and Capture](https://docs.recurly.com/docs/auth-and-capture) as well as [Kount](https://docs.recurly.com/docs/kount) in Recurly docs.
* 8/6/2024: **Worldpay gateway** now supports Apple Pay and Google Pay! You can find information on integrating Apple Pay and Google Pay in the Recurly.js [developer hub](https://recurly.com/developers/reference/recurly-js/#apple-pay), and read more about Apple Pay and Google Pay [here](https://docs.recurly.com/docs/apple-pay-on-the-web) and [here](https://docs.recurly.com/docs/google-pay).

## July

* 7/31/2024: **Adyen Cash App updates**: Added support for passing in billing address details when using Cash App via Recurly.js. Please see our [developer hub](https://recurly.com/developers/reference/recurly-js/#cashapp) for more information.
* 7/31/2024: **Opayo/Sagepay gateway updates**: Added a merchant-facing 3DS enablement option within payment gateway settings to allow 3D Secure enablement or disablement via the Recurly Admin UI. Please see our [product documentation](https://docs.recurly.com/docs/opayo#step-7-enable-3d-secure) for more information.
* 7/23/2024: **Invoice PDF attachments for emails**: Moved the ability to apply invoice PDF attachments to invoice-related emails _from_ the "Invoice Settings" page to [each individual email template](https://docs.recurly.com/docs/invoice-settings#email-settings) that supports an invoice PDF. Merchants can now pick and choose which impacted emails to send an invoice PDF with, versus only having this setting apply site-wide.
* 7/10/2024: **Analytics updates:** Added a new view on the Signup Declines and the Renewal Declines dashboards with more granular filtering. On the Dunning Invoice Details dashboard, the graph for the dunning buckets was removed and replaced with a table.
* 7/9/2024: **Specific tax codes for in-the-box taxes:** Merchants using Recurly's in-the-box tax solution can now add a specific tax code to their plans, add-ons, and items. This enhancement provides merchants with the ability to apply more precise tax amounts to products based on merchant's location and type of goods sold. Please see our [product documentation](https://docs.recurly.com/docs/tax#tax-product-type) for more information.
* 7/2/2024: **Taxable address overrides for charges:** Support for merchants on Recurly's Elite plan to set distinct taxable address configurations for one-time-charges via UI and API. These settings would override the taxable address settings from the Business Entity that would otherwise be applied to the invoice. Please see our [product documentation](https://docs.recurly.com/docs/tax#taxable-addresses-for-one-time-charges) for more information.

## June

* 6/17/2024: **Analytics Dashboards updates:** Recurly continues to enhance our suite of in app dashboards, including the following updates.
  * Added the time series for percent and count with a KPI tile on the Signup Declines, Renewal Invoices and Renewal Declines dashboards.
  * Added time series for failure type on the Renewal Declines and Signup Declines dashbaords.
  * Added time series for invoices with other outcomes by % of Total Count and Total Amount on the Renewal Invoices dashboard.
* 6/10/2024: **Taxable address control:** Control which taxable addresses form each invoice to send your tax service based on your business entity's configurations. This empowers you to determine whether to charge customers tax based off of your merchant entity tax address, or your customer's location. Please see our [product documentation](https://docs.recurly.com/docs/tax#determining-taxable-addresses) for more information.
* 6/10/2024: **BACS on Adyen:** Enable BACS Direct Debit payments on Adyen for your UK merchants. Read more about BACS in our [product documentation](https://docs.recurly.com/docs/adyen#bacs).
* 6/5/2024: **Redfast partnership announcement:** Drive action across your in-app subscriber lifecycle usingRecurly Engage.Recurly Engage is a platform that delivers real-time, personalized messages across web, mobile, and TV based on users’ behavior, allowing B2C companies to guide their customers to take actions that will drive acquisition, retention, and upselling. Your best chance to get your subscribers' attention is when they’re actively using your product. Please see our [product documentation](https://docs.recurly.com/docs/redfast) for more information.
* 6/4/2024: **Support for Multiple Business Entity Invoice Mapping to Vertex:** Merchants on Elite plans can create mappings between their Recurly Business Entities and Vertex Company and Divisions to enable entity-specific invoice filing within their Vertex instance. Please see our [product documentation](https://docs.recurly.com/docs/vertex#business-entity-division-mapping) for more information.
* 6/4/2024: **Support entity-specific "Company" values for email parameters**: Merchants on Elite plans with Multiple Business Entities configured will now have [emails support the appropriate Business Entity](https://docs.recurly.com/docs/email-templates#company-information) information that should be reflected based on the entity applied to the invoice associated with an email, or the overriding Business Entity assigned to a given customer's account.
* 6/4/2024: **Refund invoice reflects customer's address from the original charge invoice**: Refund invoices will now reflect the customer's "bill to" that was applied to the charge invoice the refund was generated from. [This ensures ](https://docs.recurly.com/docs/multiple-business-entities#refund-invoices)that location codes for customer refunds match the location codes for the given customer's original charge invoice.
* 6/4/2024: **Support for the "Entity Use Code" field with Recurly's Avalara integration via API V3**

## May

* 5/31/2024: **Cash App Pay on Adyen**: Updated our Adyen gateway integration to support Cash App Pay. Enabling will require USD support enabled. Please see our [product documentation](https://docs.recurly.com/docs/adyen#adyen-cash-app-pay) and [developer hub documentation](https://recurly.com/developers/reference/recurly-js/#alternative-payment-methods) for more information on Cash App support.
* 5/21/2024: **Expanded Customer Tax ID and VAT validation**: Expanded the list of countries and regions Recurly supports customer VAT/Tax ID number validation or format checks for to better support our B2B merchants. This functionality helps prevent customers from committing fraud and reduces risks of merchants being incorrectly liable for paying taxes on invoices when customers enter invalid tax ID number information. See our [product documentation](https://docs.recurly.com/docs/vat-number-validation#uk-vat-validation) for more information on taking advantage of customer tax ID number validation on your site.
* 5/14/2024: **Dankort on Adyen**: Enabled Dankort card brand for the Adyen gateway. Enabling Dankort for recurring will also require the DKK currency enabled. See our [product documentation](https://docs.recurly.com/docs/adyen#dual-badge-card-support) for more information on this dual-badge card brand.
* 5/14/2024: **Bancontact on Adyen**: Enabled Bancontact card brand for the Adyen gateway. Enabling Bancontact for recurring will also require SEPA enablement. See our [product documentation](https://docs.recurly.com/docs/adyen#dual-badge-card-support) for more information on this dual-badge card brand.
* 5/7/2024: **Proration Flexibility**- Choose from a new variety of ways to handle charges and credits resulting from immediate subscription changes that are most effective for your business needs. Ex: When upgrading a customer’s subscription to a new plan mid-billing cycle, choose to issue them no credit for their original plan and only charge them a prorated amount for their new plan based on how much time is left in their current billing period. You can set site-level proration behavior settings in the Recurly Admin UI, or override the site-level settings during an immediate subscription change via UI or either [API](https://recurly.com/developers/api/v2021-02-25/index.html#operation/create_subscription_change) version.  [Learn more](https://docs.recurly.com/docs/change-subscription#handling-immediate-subscription-changes)
* 5/7/2024: Made additional updates to GoCardless name handling.

## April

* 4/30/2024: Updated the V3 API to support Authorize and Capture endpoints.
* 4/23/2024: Updated handling of Company information on GoCardless to ensure seamless processing. Merchants who wish to accept a business's company name will need to enable the field in HPP settings or collect it via API.
* 4/16/2024: **More built-in subscription benchmarks**. We’ve added more built-in benchmarks to help you compare your acquisition and churn rates to industry peers. You’ll find it in [Recurly Reporting & Analytics](https://recurly.com/product/reporting-analytics/). Read all about it [here in the blog](https://recurly.com/blog/built-in-subscription-benchmarks/) and learn more in [product docs](https://docs.recurly.com/docs/built-in-benchmarks).
* 4/16/2024: Updated the Braintree SDK to the latest and greatest. No Recurly.js changes are required with this update.
* 4/16/2024: Updated Adyen response code handling to account for an undocumented response code of '47'. This will enable Recurly to disallow retries on transactions declined due to customers blocking merchants at the Issuer level.
* 4/09/2024: **NetSuite** Enhancements have arrived! This month’s enhancements include:
  * Overall stability and performance enhancements.
  * Support for Multiple Business Entities: Allows you to map a single Recurly site to multiple subsidiaries in their NetSuite instance. Please reach out to Professional Services to have this flag enabled.
  * Support for Voided Credits: Allows you to create a record in NetSuite to offset ‘open’ credit memos that have been voided in Recurly. Please reach out to Professional Services to have this flag enabled.
  * Added new mappings for the plan sync: Recurly Accounting Code now maps to Income Account on the item record in NetSuite. This gives you the ability to use different GL accounts per plan, item, add-on, & setup fee.
  * New Account Sync Filters:
    * **Do Not Sync Filter**  allows you to enable a custom field on the account record that will prevent the customer account and associated transactions from syncing into NetSuite.
    * **Free Plan Filter**  allows you to configure a certain plan within your configuration file that prevents the customer account and associated transactions from syncing into NetSuite if they are subscribed to a “Free Plan”.
    * **Domain Filter**  allows you to configure a domain name associated with a customer’s account that prevents the account and associated transactions from syncing into NetSuite. You have the ability to add multiple domain names to the configuration.
* 4/09/2024: Updated handling of First and Last Name information on GoCardless to ensure seamless processing.
* 4/02/2024: Updated handling of Vantiv MAC codes related to Virtual Card Numbers.
* 4/02/2024: Introducing Recurly Automated SEPA Retries! Read more about this new feature in our dedicated feature documentation: [SEPA Automated Retries](https://docs.recurly.com/docs/sepa-retries).

## March

* 3/26/2024: Updated Sagepay endpoints ahead of March 31st URL deprecation deadline. No impact to transactions will occur.
* 3/19/2024: Added support for Adyen Co-Badged cards to Client Libraries. Learn more by viewing our [Developer Guides](https://recurly.com/developers/api/#api-versions).
* 3/19/2024: Added support to include the **\{\{invoice_subtotal}}** [email parameter](https://docs.recurly.com/docs/email-templates#invoice-details) to the following email templates: Bill Date Reminder, Term Renewal Reminder, Annual Reminder, SEPA Renewal Reminder, Credit Card Expired, Ramp Price change, and Subscription Trial Expiring. This allows merchants to include an estimation within these emails sent to customers that reflects what their next invoice will amount to, taking into consideration any coupons and discounts that would apply to that next invoice, at the point in time that the email is sent.
* 3/19/2024: Merchants can now apply a credit to any open invoice. Previously we had a limitation where a credit could not be applied to the past-due open invoice that the credit was originally generated from, but with that limitation removed, they can use credits to put towards or close out any invoice of their choosing.
* 3/13/2024: Merchants on Recurly's Elite plan can now set entity-specific billing contact email addresses for each of their alternate business entities, ensuring the desired merchant email address is displayed on invoices sent to customers, and is being used as the "from" address on emails sent to customers. [Learn more](https://docs.recurly.com/docs/multiple-business-entities#entity-specific-merchant-email-addresses).

## February

* 2/28/2024: Adyen now supports Cartes Bancaires cards with customer choice through Recurly.js. [Learn more](https://docs.recurly.com/docs/adyen#adyen-codual-badged-cards) about Adyen and Co-Badge cards and view [Developer guides](https://recurly.com/developers/guides/co-badge.html).
* 2/27/2024: Braze integration now supports Custom Attributes being set from Recurly for subscription and account level data. The subscription and account data can now be used in segmentation within Braze and apply to Canvases to communicate with your subscribers across their subscription journey. [Learn more](https://docs.recurly.com/docs/braze-integration) about the Recurly integration with Braze.
* 2/21/2024: Added additional fields to Transactions Explore.
  * voided_at in utc time, voided_at in the merchants local time, collected_at in utc time, collected_at in local time, is_test, avs_result, avs_result_postal, avs_result_street, approval_code, description, po_number, collection_method, backup_payment_used, vat_number, fraud_decision, fraud_score, fraud_message
* 2/13/2024: **Automatic Invoices Terms** is now available for additional invoice flexibility. Collect your automatic invoices on a date after the invoice creation. This allows the invoice to be shared, including the final billable amount and any usage based billing charges, prior to payment collection. This invoice would collect after the predetermined time using the payment method on file. Automatic Invoice Terms are available for both invoices generated from subscriptions and standalone invoices. [Learn more](https://docs.recurly.com/docs/automatic-invoicing-terms).

## January

* 1/23/2024: Recurly is proud to introduce a powerful new feature to our Reporting & Analytics suite: **Built-in Benchmarks.** It’s an innovative tool designed to give you a competitive edge in understanding and improving your subscription metrics.
  * What does it mean for you?
    * Benchmark against the best: Compare your performance metrics against industry standards in real-time.
    * Strategic insights: Use these benchmarks to refine your strategies and enhance your subscription business.
  * This feature is a part of our ongoing commitment to provide you with the most comprehensive tools for managing your subscription business. To learn more about how you can leverage this new functionality, check out our latest [blog post](https://recurly.com/blog/built-in-subscription-benchmarks/).
  * These new benchmarks can be found in the Renewal Invoices and Renewal Declines dashboards, under Churn Management in Recurly Analytics.

# 2023

## December

* 12/06/2023: **NetSuite** Enhancements: Added new functionality to sync orphaned payments and refunds to NetSuite in the event the payment or refund does not have a corresponding invoice.
* 12/06/2023: Added functionality to consume late failure and chargeback events for GoCardless SEPA and ACH transactions. Merchants can request access to a new feature and enable automatic chargeback invoices to be created to keep transaction reporting in sync.

## November

* 11/29/2023: **Braze** announced as new integration partner. Braze provides a leading customer engagement platform that enables and automates personalized cross-channel communications to enhance subscriber engagement, drive retention, and improve the user experience. Recurly’s new integration with Braze allows merchants to leverage subscriber and subscription data within Braze to craft real-time, hyper-personalized messages across communication channels, including email, web, and mobile. Through targeted and personalized messages, you can drive engagement and retention. [Learn more](https://docs.recurly.com/docs/braze-integration).
* 11/14/2023: Merchants using the **Hosted Payment Page** can now choose whether to hide the [currency dropdown](https://docs.recurly.com/docs/hosted-pages#hosted-page-settings) menu on the checkout page, or continue to display it. This will help deter "currency hopping" and consequentially price manipulation.
* 11/14/2023: Added [Dunning Campaign](https://docs.recurly.com/docs/dunning-management#key-benefits) codes and Dunning email template names as metadata on account activity logs. This will show merchants which dunning campaigns customers belong to and which dunning emails they have been sent from their account pages or within the Account Activities export.
* 11/14/2023: Added additional tax regions for Recurly's in-the-box tax calculation solution. See the [taxes documentation](https://docs.recurly.com/docs/tax#supported-regions) page for all tax regions Recurly supports tax calculation for.
* 11/14/2023: Enabled customer billing and shipping consumption via enriched data for Venmo transactions and Web Desktop Authentication via R.js when using Braintree payment gateway.

## October

* 10/24/2023: Released entity-specific invoices treatments, an enhancement to our Business Entity offering, where merchants on Elite plans can apply entity-specific invoice header and footer images/logos, notes to the customer, and terms and conditions. Merchants on Professional and Starter plans can apply header and footer images/logos to their Site Default Entity. Setting specific invoice treatments for each of your entities helps in ensuring each business entity's contact information, logo presentation, desired notes for respective subscriber pools, and entity-specific legal communications and mandate information are sent to the right customers at the right time.

## September

* 9/19/2023: Increase the limit of integers allowed within the VAT field on customer accounts when the country= New Zealand, from 9 to 13.
* 9/12/2023:
  * **Updated UI navigation menu**
    * Within the Recurly UI, we’ve made a subtle change to the navigation menu by grouping similar dashboards together, making it easier to find specific dashboards and discover new ones.
  * **Two new dashboards**: To make it simpler to discover which plans are performing and which trial offers are converting, we enabled two dashboards to all merchants (Previously, these two dashboards were available only to Pro and Elite and Elite plans respectively.)
    * **Trial performance**: Track the performance of subscription trials and monitor the conversion rates from trial to active subscriptions.
    * **Plan performance**: Compare the performance of distinct plans across eight different performance metrics, including trial conversion rates, churn rates, subscription totals, and subscription growth.
* 9/11/2023: NetSuite integration enhancements:
  * Connector upgraded for overall better stability and performance
  * Enhancement related to credits converted to cash refund
  * Additional Retry Logic added to account for concurrency limits
  * Credit Reconciliation (Feature Flag) must be enabled by Professional Services
    * Added new functionality to move an applied credit(s) from one invoice to another in the event the original invoice fails. Example: End Customer received a $100 credit refund to be applied to their next charge invoice. The charge invoice is created in Recurly and the credit refund is applied to the invoice. The end customer does not pay the remaining balance on the charge invoice and the invoice is failed. The credit refund is voided and a write-off credit memo is applied to the invoice. In NetSuite, the credit refund is created as a credit memo and then the charge invoice is created. The credit memo is applied to the charge invoice. Once the invoice is failed in Recurly, the integration will send a request to NetSuite and the original credit will be unapplied from the invoice. The write off credit will be created as a credit memo in NetSuite and applied to the invoice. The original credit will now be open to be applied to the next charge invoice.
    * Modification to the Credit Flow. The credit flow will only create the credit memo in NetSuite. The applyList will now be triggered from the invoice record once the credit is applied.
    * Modification to the Invoice Flow. When a credit payment is applied to an invoice in Recurly, this will trigger the NetSuite integration to send the applyList for the credit(s) to apply to the invoice. Invoices will now use the updated_at date field to sync to NetSuite

## August

* 8/23/2023: Updated account naming on customer invoices that are in an Account Hierarchy. Display now reads Primary Account and Linked Account.
* 8/22/2023: Increased number of child accounts that can be added to each parent account in Recurly App from 500 to 10,000
* 8/22/2023: Released API V3 support for obtaining Brazilian CPF/CNPJ number via the "tax_identifier" field, more information available in [developer documentation ](https://recurly.com/developers/api/v2021-02-25/index.html#operation/update_billing_info)
* 8/16/2023: Updated Braintree integration to expose PayPal PayerID in the account_reference field nested in the gateway_attributes section.
* 8/16/2023: NetSuite integration enhancement: Added additional retry logic to properly sync failed payment transactions.
* 8/9/2023: Updated [iDeal](https://docs.recurly.com/docs/adyen#adyen-ideal) and [Sofort](https://docs.recurly.com/docs/adyen#adyen-sofort) payment methods on the Adyen gateway. With a new integration Recurly uses Adyen Components API for iDeal and Sofort payment methods.
* 8/4/2023: Updated Recurly.js for the Venmo payment method on Braintree integration to start including device data in payment requests.
* 8/1/2023: Update to the Transaction export, newest version is Version 6. This update includes an added column for "vat_number" to allow merchants who require obtaining a customer's VAT or Tax ID Number via export to easily access that information.

## July

* 7/25/23: Added two Ramp Pricing enhancements. Plan changes on a subscription now support the ability to set a unique ramp pricing schedule on the new plan ([learn more](https://docs.recurly.com/docs/ramp-pricing#changing-plans-on-a-subscription)). Subscription API responses now include date data around each ramp interval dates ([example](https://docs.recurly.com/docs/ramp-pricing-implementation-guide#step-2-1)).
* 7/25/2023: Added End of Month term options for manual invoicing. This feature requires enablement from Recurly Support and is available for Professional and Elite plans. These term types will benefit merchants who have business customers whose accounting teams require fulfilling payment for invoices at a later point in time, typically in increments of weeks or months following the original month an invoice was issued. The EOM term calculation include EOM 0, 15, 30, 45, 60 and 90. Currently available via UI and API V3 for early access. This also resulted in new export versions for the following reports: Adjustments, Subscriptions, Invoices- Accounts Receivable, Invoices- Summary, and Invoices (deprecated report available only on some sites)
* 7/11/2023: There is a new German mandate that requires merchants include the time/date that a subscription was canceled within the email body of subscription cancelation emails sent to their German customers. We have added a new email parameter to solve for this; merchants must add it to their subscription cancelation email template if they wish to have it included in those emails. `{{subscription_canceled_at_with_time}} `
* 7/1/2023: Early Access program began for the newly added Site Audit Log report in Recurly's Admin section of the application. Requires Admin access on merchant site. Currently available to select merchants on Recurly's Elite plan. This new dashboard captures a wide array of change activity that users on your Recurly site conduct via the Admin UI and/or API to objects such as plans, items, coupons, site settings, business entities, and even captures user logins.

## June

* 6/28/2023: Updated Salesforce integration to improve account sync.
* 6/28/2023: Chase Orbital now supports Apple Pay and Google Pay! You can find information on integrating Apple Pay and Google Pay in the Recurly.js [developer hub](https://recurly.com/developers/reference/recurly-js/#apple-pay), and read more about Apple Pay and Google Pay [here](https://docs.recurly.com/docs/apple-pay-on-the-web) and [here](https://docs.recurly.com/docs/google-pay).
* 6/21/2023: Launched a new integration with PayPal Complete payment gateway. PayPal Complete is the newest payment gateway from PayPal. PayPal Complete is a convenient way to support multiple payment methods offered by PayPal within one integration. Learn more [here](https://docs.recurly.com/docs/paypal-complete).
* 6/21/2023: Launched a new payment method Boleto. This payment method is a popular payment method in Brazil. Boleto is available in the early access on the Adyen gateway. Learn more [here](https://docs.recurly.com/docs/boleto).
* 6/5/2023: Various NetSuite integration enhancements:
  * Increased application resiliency with additional connection level tuning ensuring connections are established and destroyed consistently across all activities
  * Increased horizontal scaling allowing for more nodes to handle substantially more activities in parallel without impacting the stability of the overall environment
  * Multiple dedicated load balancers have been established to guarantee a balanced allocation throughout the newly expanded nodes. This process also ensures that as nodes restart, they are automatically reinstated into the distribution pool following a successful health check.
  * Shifted guaranteed message delivery mechanism from local Java Queue based technology to Enterprise grade MQ backed by AWS services to allow for guaranteed cross application messaging in a consistent and infinitely scalable way.
  * Introduced enhanced back-pressure capabilities to better equip applications with insights into the load conditions of downstream systems. This allows them to adjust effectively and hold messages during periods of heavy load until horizontal scaling policies automatically scale up the environment to handle the additional demand. This improvement has led to a reduction in overall CPU usage across all nodes by a factor of 4 to 5 times. Coupled with the scaling improvements mentioned previously, the throughput of the environment has increased as much as 5x, with the potential for significant further increase thanks to additional scaling capabilities.
  * Implemented fully configurable retry logic allowing individual merchants to set maximum retry at the object level (account, invoice, payments, etc) and a max retry threshold to stop and hold for nightly error report delivery. Further this retry capability will ensure transactions aren’t attempted if a prior dependent object has failed to create.  A good example of this is attempting to apply payments where a prior invoice failed to create, which ensures API calls are more strategically called vs just handling an error response in prior versions.
  * Updated our data transmission strategy to NetSuite for enhanced efficiency. Now, instead of batch processing, we transmit one record at a time, leveraging multiple threads to expedite the process. By default, we use four threads, meaning that four records are concurrently dispatched to NetSuite, ensuring a quicker response time and increasing the throughput approximately 2x across all api calls. The sync now cadence runs every 5 minutes but does vary depending on the number of records syncing during a cycle.
  * Implemented messaging queues to store records until a successful response is received from NetSuite. This is helpful, should NetSuite go down due to an outage or scheduled maintenance. Once a successful connection is restored with NS, the messages stored in the queue will sync to NetSuite following a standard FIFO approach.
  * Introduced a new credit flow. Credit flow takes into consideration credit invoices created in the past that will be applied to future invoices. Example: Invoice is refunded as a credit April 1, 2023 however the credit is not redeemed until May 15, 2023 on a new charge invoice. The new credit flow will apply the credit to the newly created charge invoice by only updating the applyList of the credit record in NetSuite.

## May

* 5/31/2023 Launched Multiple Business Entities, a feature that allows merchants on a Recurly Elite plan to set up as many business entities on a single Recurly site as they wish. Each business entity consists of its own Tax ID numbers, and can consist of a unique business address used for invoice display, and a unique business address for origin tax address calculation. Learn more [here](https://docs.recurly.com/docs/multiple-business-entities).

## April

* 4/25/23 Launched Recurly's new app management solution designed to make Recurly your single source of truth for subscriptions across web, Apple, and Google platforms.  Learn more [here](https://docs.recurly.com/docs/app-management).
* 4/25/23 Added a new field to the API, a column in exports, and a note in the UI if tax service was used or not. The field in the API and Exports is a boolean field called used_tax_service. In the UI, the invoice will display a note if tax service was used or not.
* 4/19/23 Added [Apple Pay ](https://docs.recurly.com/docs/apple-pay-on-the-web#payment-gateways)and [Google Pay](https://docs.recurly.com/docs/google-pay) support to Recurly's Adyen integration.
* 4/19/23 Added new parameters to the [Apple Pay](https://recurly.com/developers/reference/recurly-js/#apple-pay) and [Google Pay](https://recurly.com/developers/reference/recurly-js/#google-pay-) integrations to streamline Recurly.js purchase flows.
* 4/17/23 Added new "Subscriber Reports" to Recurly Analytics. These new dashboards include an additional filter to “Combine Subscriptions” which combine back-to-back subscriptions to provide a more accurate count for activations and churn. [Learn more](https://docs.recurly.com/docs/subscribers#new-reports-for-monitoring-subscriber-counts-in-beta).
* 4/4/23 Added additional billing models for Usage Based Billing Add-ons. When charging a percentage of an amount, these add-ons now support pricing tiers and volume in addition to a fixed percentage take rate. Additionally, usage can now be tallied cumulatively over the entire subscription term, in addition to tallying usage over each billing cycle. [Learn more](https://docs.recurly.com/docs/usage-based-billing).

## March

* 3/15/23 Added the ability to define your business's identity in a single location, allowing you to more easily manage the company information used for invoices and transactions with your customers. You are now able to set a company address to display on invoices sent to customers, and create an entirely separate/unique address to use as the origin tax calculation address that is passed through Vertex and Avalara for all transactions. "Company Information" and "VAT ID" fields no longer live on the "Site Settings" page are now managed directly from the newly added "Business Entities" page. [Learn more](https://docs.recurly.com/docs/business-entities)

## February

* 2/21/23 Added the ability to set a Charge custom field value via the Recurly Admin UI. [Learn more](https://docs.recurly.com/docs/custom-fields) in the Custom Fields on Charges section.
* 2/10/23 [Recurly Entitlements](https://docs.recurly.com/docs/entitlements) have been released. Merchants can now create and manage a catalog of features and functionality that can be granted to their end customers based on purchases of subscription Plans and Item Add-ons.
* 2/7/23 Released API V3 support for Gift Cards. [Learn more](https://recurly.com/developers/api/v2021-02-25/index.html#tag/gift_cards).
* 2/7/23 Released API v2 Client Libraries to support Custom Fields on Charges and Plans. [Learn more](https://docs.recurly.com/docs/custom-fields) or view the [developer docs](https://recurly.com/developers/api-v2/v2.29).

## January

* 1/31/23 Released support for Google as a [Single Sign-On (SSO)](https://docs.recurly.com/docs/single-sign-on#for-google-sso) identity provider (IdP). Recurly now supports three IdP's: Google, Okta and Azure.
* 1/24/23 Create and assign custom roles based on your unique security requirements to ensure the right people have access to the right features and data. For existing merchants, previously configured permission sets have been recreated as roles, so you don’t need to change anything for existing users. [Learn more.](https://docs.recurly.com/docs/user-roles-and-permissions)
* 1/17/23 Added the ability to set Custom Fields on Charges (via Line Items and Purchases) when using the v3API. [Learn more](https://docs.recurly.com/docs/custom-fields).
* 1/10/23 Email parameters for custom fields are now available to support merchants in merging a custom field value into their email templates. [Learn more.](https://docs.recurly.com/docs/email-templates)
* 1/10/23 Recurly's email timezone functionality is now available through both API versions to support account-level email timezone assignment. [Learn more](https://docs.recurly.com/docs/email-time-zones-and-time-stamps).

# 2022

## December

* 12/08/22 In Salesforce fixed bugs where on initial subscription creation the plan could not be changed, unable to edit fields, and syncing was erroring out; have all been fixed. The timing card on the VF page of an order has also been moved to where it should be. A separate shipping address field was added so it only displays when needed.
* 12/7/22 Added additional webhook functionality to better support renewal notifications. [Learn more](https://docs.recurly.com/docs/renewal-reminder#prerenewal-webhook-notifications) about prenewal webhook notifications, or view the [developer docs](https://recurly.com/developers/reference/webhooks/#prerenewal-notifications).
* 12/6/22 Added the ability to duplicate a plan. This was a Recurly Engineering [Innovation Days](https://www.linkedin.com/posts/recurly_innovationdays-recurlylife-keepagoodthinggrowing-activity-6980201028310769664-Rkne) project that is delivered into the hands of our merchants. Read the documentation on how to duplicate a plan. [Learn more](https://docs.recurly.com/docs/plans#duplicating-plans).

## November

* 11/29/22 Added API V3 and API V2 support to be able to apply account balances to past due invoices. [Learn More](https://docs.recurly.com/docs/invoices#past-due).
* 11/21/22 in Salesforce it was incorrectly displayed showing the plan length as the length of the trial due to incorrect naming. This was updated to reflect the actual plan length and trial length(if applicable)
* 11/15/22 Added API V2 support for Custom Fields on Plans, where you can create, view and edit plan custom fields via the API. Added resource for Custom Field Definition, where you can see all custom fields defined in the site or retrieve a specific field. [Learn more](https://docs.recurly.com/docs/custom-fields).
* 11/9/22 Added additional flexibility for Renewal Reminder email templates, which are now have the option to send at Term Renewal AND/OR Bill Date. [Learn more](https://docs.recurly.com/docs/renewal-reminder).
* 11/9/22 The usage-based add-on calculation methods feature enables merchants to determine whether to charge their customers for usage by the sum of all recorded usage amounts throughout a billing period, or by the most recent amount of usage recorded before the end of a billing period.
* 11/8/22 Recurly's [Two Factor Authentication (2FA) feature](https://docs.recurly.com/docs/two-factor-authentication) now supports additional authenticator apps including Twilio Authy, Okta Verify, Google Authenticator, Microsoft Authenticator, LastPass Authenticator
* 11/3/22 Recurly JSON webhooks now support [signature verification](https://recurly.com/developers/reference/webhooks/#signature-verification) for increased security. Verification can be performed manually or with the help of the v3 Ruby and Golang client libraries
* 11/2/22 Ability to add custom, formulaic fields within Report Builder for dashboard specific needs
* 11/2/22 Added API V3 support for Custom Fields on Plans, where you can create, view and edit plan custom fields via the API. [Learn more](https://docs.recurly.com/docs/custom-fields#custom-fields-on-a-plan).
* 11/2/22 Added additional conditional logic flexibility to the Renewal Reminder email templates when there is a pending subscription change. [Learn more](https://docs.recurly.com/docs/email-templates#subscription-change-fields).

## October

* 10/25/22 With Custom Fields on Plans, merchants can now add custom attributes to a plan in the UI, allowing them to more easily find the plan that is right for their customers. [Learn more](https://docs.recurly.com/docs/custom-fields#custom-fields-on-a-plan).
* 10/21/22 Added the ability to log and display usage-based add-ons on plans in decimal quantities. Merchants will need to contact Recurly Support to enable this feature flag on their Recurly site. Once the feature flag is turned on, all usage-based add-ons will be measured and displayed in decimal quantities on invoices. Supports both V2 and V3 APIs.
* 10/20/22 In Analytics for Subscriber Retention, increased the capacity to download additional columns up to 100
* 10/17/22 In Salesforce the UX for updating a payment method would cause a new page to display, instead of updating the values on the VF page. This has been updated to allow the payment method to be updated on the VF page without the extra page
* 10/14/22 With the Recurly Builder feature, merchants are now able to build powerful, flexible, and configurable custom reports and dashboards. Merchants can download these reports for further analysis and share as dashboards throughout their company.
* 10/5/22 In Salesforce fixed a bug where fields were updated and being overwritten by the sync causing an error

## September

* 9/27/22 With Ramp Pricing, merchants can attract new subscribers through a discounted point of entry that ramps up over time to the full subscription cost. Conversely, merchants can reward subscriber loyalty by scheduling pricing discounts to valuable, long-term customers. Learn more about [Ramp Pricing.](https://docs.recurly.com/docs/ramp-pricing)
* 09/27/22 Released [revenue recognition for Enterprise](https://docs.recurly.com/docs/revenue-recognition#enterprise--solution) in beta access
* Added the ability to apply account balances to past due invoices via the UI.
* 09/13/22 Added a new Annual Reminder email template. This template will be sent to customers on an annual basis from the start date of their subscription. There are state specific mandates which require this notification to be sent annually. [Learn more](https://docs.recurly.com/docs/email-templates#annual-reminder).
* 09/13/22 On the Mastercard Renewal Reminder email template, the "days prior" configuration option is updated from a preset dropdown to a text field.

## August

* 08/24/22 Released a new NetSuite Integration that allows merchants to connect sites to NetSuite to push catalog data and transactions data on a hourly cadence with a configurable approach
* 08/23/22 Restricted the ability to change the email address on an existing account via Recurly HPP (Hosted Payment Page).
* 08/16/22 Released Mastercard mandate addition to the Payment Confirmation Template. Allows you to send payment confirmation emails to only customers using a Mastercard.
* 08/10/22 Released updates to Analytics experience with the following: Persistent (i.e. saved) dashboard filters, Dashboard sharing, Refunds on the Subscriber Retention Dashboard, Expanded Monthly Recurring Revenue dashboard
* 08/09/22 Released Account Activities Explore & Download feature. Gain critical insight into _who_ within your Recurly site does _what_, _when_. Available for Professional and Elite plans, only accessible for users with Admin access.
* 08/09/22 Relocated Users Export from the dropdown on the Users page to the new Admin Exports tab under the "Admin" section on the left-side navigation panel.

## July

* 07/28/2022 [JSON webhooks](https://developers.recurly.com/reference/webhooks/index.html#webhooks) now available! Webhook endpoints can be configured to a.) receive XML or JSON payloads b.) receive specific notifications related to subscription lifecycle events
* 07/19/2022 China UnionPay payment method is now available on Adyen, Cybersource, and Stripe gateways in addition to Chase Orbital and Braintree.
* 07/19/2022 New ability to set a unique time zone specifically for sending emails to each of your customer accounts. This will help ensure your varying customer geographical locations receive emails sent via the Recurly App in their corresponding time zones, alleviating confusion of time/date stamp discrepancies between the email itself and dates reflected within the email content.
* 07/18/2022 Released updated version of our Recurly for Salesforce integration which enables merchants to be able to automatically capture customer payments by empowering the customer to input their own billing information from the Recurly's billing info update page. Also, enabled the ability to automatically create a subscription once an opportunity is set to "closed won" without the need to click the "Create Subscription in Recurly" button. See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes)
* 07/12/2022 Google Pay payment method is now available! Today we support Google Pay with Stripe gateway. We will add more gateways support in the future.
* 07/05/2022 Added support for ZDA for Vantiv and FirstData gateways
* 07/05/2022 Updated the max length of custom fields to 255 characters. [Learn about Custom Fields](https://docs.recurly.com/docs/custom-fields).

## June

* 06/14/2022 A User Export report is now live in production for all merchant sites. This is accessible in the admin section of Recurly App, and provides a CSV output of a given site's users, their permissions, and the date each user was added to the site.
* 06/14/2022 Admins can now search for specific users by name or email via a search box on the main User Access page
* 06/14/2022 On the main Users page, Admins can now leverage the Permissions filter to narrow the User list down by access levels
* 06/01/2022: Polish and Swedish added to list of supported languages for email templates, hosted pages, and invoices
* 06/01/2022 Tax inclusive pricing now supported using the Recurly In the Box tax service and Avalara Direct.

## May

* 05/17/2022: Kount custom fields support. Now it is possible to send data for Kount custom fields from [Recurly JS](https://developers.recurly.com/reference/recurly-js/index.html#recurly-fraud-management--kount-integration).
* 05/03/2022: Tax inclusive pricing using API V3, V2, and the UI available when using Vertex. Adds "Includes tax" or "does not include tax" in the UI when creating subscription or purchase and a tax_inclusive field in the subscriptions and purchases endpoints of the API. To learn more, visit the [Tax Inclusive Pricing](doc:tax-inclusive-pricing) page.
* 05/03/2022: Updated UI under Admin Section on Recurly App. On "User Access" page under "Admin" section, admin user must click on individual site user within main table to navigate to their unique user page in order to remove a specific user.
* 05/03/2022: "SSO Settings" is no longer a button present on the "User Access" page. Merchants can now access SSO Settings on its own page accessible under the "Admin Section".

## April

* 04/04/2022: Updated Invoice Settings page to provide new images that accurately reflect the existing UI design, as well as provide context for where to find Invoice Customization information.
* 04/05/2022: Newly added documentation page for Invoice Customization, an RA feature that went GA on 04/05/2022 for all Pro and Elite merchants. With Invoice Customization, merchants can tailor multiple invoice templates to reflect different customer segments, geographical locations, entities within a merchant's organization, and unique logos.
* 04/28/2022: Apple Pay payment method on [Braintree gateway](https://developer.paypal.com/braintree/docs/guides/apple-pay/configuration/javascript/v3#production-environment). Now it is possible to accept Apple Pay on Braintree in addition to Vantiv, Stripe, Cybersource. Please see [developer documentation](https://developers.recurly.com/reference/recurly-js/index.html#apple-pay) for more information.

## March

* 03/23/2022: Released support for Microsoft Azure as a [Single Sign-On (SSO)](https://docs.recurly.com/docs/single-sign-on) identity provider. Recurly now supports Okta and Azure.
* 03/22/2022: Released updated version of Recurly for Salesforce integration that enabled multiple subscriptions via opportunity as well as allow our EU merchants to set their data center for their salesforce organizations. Also included is a a couple bug fixes related to issues with invoice calculations and delayed syncs. See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes)
* 03/17/2022: Mastercard Reminder email template added to help merchants stay compliant with the upcoming Mastercard mandate. When enabled on a plan, the email reminder is sent to Mastercard subscribers 3-7 days prior to their bill date.
* 03/08/2022: Updates to the subscription edit page within the Recurly App Admin UI were released, which provide the ability to change some subscription details when there are existing pending changes, without losing the existing pending change.

## February

* 02/25/2022: iDEAL payment method is now live and available to all merchants though RecurlyJS via Adyen. See more details [here](https://docs.recurly.com/docs/adyen#adyen-ideal).
* 02/08/2022: The Dunning Campaigns feature has now been enabled on all sites. The Dunning Effectiveness report is updated to allow viewing data for an individual campaign or all dunning campaigns collectively. See more feature details [here](https://docs.recurly.com/docs/dunning-management) and details on the Dunning Effectiveness reporting [here](https://docs.recurly.com/docs/dunning-effectiveness-report)

## January

* 01/28/2022: Released updated version of the Recurly for Salesforce integration that enabled editing subscriptions from opportunities and easier correlation to subscriptions. Added a sidebar highlighting subscription details and updated to invoice rollup data sync.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes)

# 2021

## December

* 12/17/2021: Released updated version of the Recurly for Salesforce integration that fixed a bug related to SOQL limits.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).
* 12/10/2021: Released updated version of the Recurly for Salesforce integration that fixed a bug related to future dated subscriptions.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).
* 12/07/2021: Added support for the Wallet & Account Hierarchy features to be compatible. Learn more about [Wallet](https://docs.recurly.com/docs/wallet#wallet--account-hierarchy-feature-support).

## November

* 11/23/2021: Added 3DS support to our SagePay integration so merchants can properly adhere to the PSD2 mandate.  Documentation [here](https://docs.recurly.com/docs/gateway-specific-updates#sagepay).
* 11/19/2021: Released updated version of the Recurly for Salesforce integration that fixed bugs related to the admin page and permissions for loading the subscription page.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).
* 11/08/2021: Released updated version of the Recurly for Salesforce integration that enabled broader multi-currency syncs for Products and Subscriptions, full readability to all Subscription Term fields, and Updated VF architecture to LWC.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes)

## October

* 10/29/2021: Recurly releases Account Hierarchy: Invoice Rollup, providing new capabilities for billing and invoicing customers with complex hierarchical business structures. You can now rollup charges from multiple child accounts that bill to a common parent account into a single invoice. This provides you with the the ability to greatly simply the billing process for your customers, while reducing your transaction costs. Learn more [here](https://docs.recurly.com/docs/ah-invoice-rollup)
* 10/21/2021: Support added for Worldpay/dlocal accounts in Argentina, which include a new payment method, Tarjeta Naranja. Learn more about this account configuration [here](https://docs.recurly.com/docs/worldpaydlocal-latam-support).
* 10/14/2021: Added new capabilities to Recurly's Dunning Management functionality. You can now create multiple dunning campaigns and assign specific plans and accounts to different campaigns (available for Pro and Enterprise only), create trial specific dunning cycles, and stop dunning emails for a past due invoice without having to fail the invoice.  Details [here](https://docs.recurly.com/docs/dunning-management).  To enable these features, please reach out to Recurly Support and request to have the Dunning Campaigns feature enabled on your site.

## September

* 9/30/2021: Added a processor configuration selection option for Cybersource merchant, which fixes processor-specific Card-on-File handling. See more details [here](https://docs.recurly.com/docs/additional#section-cybersource).
* 9/29/2021: Released updated version of the Recurly for Salesforce integration that fixed a bug related to subscription creation via the subscription object.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).
* 9/02/2021: Released updated version of the Recurly for Salesforce integration that fixed bugs related to editing subscriptions.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).

## August

* 8/31/21: Released updated version of the Recurly for Salesforce integration that allows for one-time charges, syncing custom fields from Recurly, and extending start dates for future dated subscriptions.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes)
* 8/25/21: Added IP Address collection for Cybersource payments where Recurly.js is present.
* 8/10/21: Updated email template descriptions related to dunning.
* 8/05/21: Released updated version of the Recurly for Salesforce integration that fixed a bug related to pricing sync and enabled additional logging during resync.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).

## July

* 7/27/21: An update to our Recurly Admin UI modifies the appearance of the buttons used to create new items, charges, credits, subscriptions, etc.
* 7/13/21: Added dunning campaign name, code, and ID to the [Dunning Event webhook](https://developers.recurly.com/reference/webhooks/index.html#dunning-event-notifications).
* 7/9/21: Released updated version of the Recurly for Salesforce integration that fixed a bug related to manual invoicing.  See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).

## June

* 6/24/21: Re-organized the elements on the Plan page in a chronological order to enhance our merchant’s experience when building, viewing, or editing Plans.
* 6/17/21: Updated Vertex integration to break out Canadian taxes for country and state rates on customers final invoices. Invoice responses via API also support a breakout of Canadian tax rates.
* 6/3/21: Released updated version of the Recurly for Salesforce integration. This version allows users to sync Recurly plans, add-ons, and items with Salesforce products and standard price book entries, as well as creating subscriptions and accounts in Recurly from closed opportunities in Salesforce. See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).

## May

* 5/17/21: Released updated version of the Recurly for Salesforce integration, fixing a few bugs. See more details [here](https://docs.recurly.com/docs/salesforcereleasenotes).

## April

* 4/29/21: Released enhancements to out out of the box Avalara tax integrations to always send AccountID and no longer send AccountCode.
* 4/22/21: Recurly releases Wallet to let you offer more convenience and improve customer satisfaction by giving your customers the ability to have [multiple payment methods](https://docs.recurly.com/docs/wallet) on one account. Wallet also allows you to simplify renewals and reduce payment failures by enabling [backup payment method](https://docs.recurly.com/docs/backup-payment-method). Read the [press release](https://www.recurly.com/press/recurly-launches-wallet-in-a-strategic-expansion-of-its-subscription-platform?utm_source=twitter\&utm_medium=social\&utm_campaign=2021-02-high-impact-subscription-tips\&utm_content=infographic/) to learn more.
* 4/22/21: Updated Avalara integration to break out Canadian taxes for country and state rates on customers final invoices.
* 4/15/21: Released enhancements to Recurly's in-the-box tax solution to support taxation in Indonesia.  [Learn more.](https://docs.recurly.com/docs/tax#section-supported-countries)
* 4/8/21: Released enhancements to tax integrations for AvaTax and AFC to select which account identifier is sent to Avalara. To prevent sending PII to Avalara, you can now send Account ID instead of Account Code.
* 4/8/21: Released enhancements to AvaTax integration to make it optional to send $0 invoices. Invoices created at the start of a trial are $0 and will have not have any taxes applied. To avoid Avalara charging for these invoices, don't send $0 invoices.

## March

* 3/25/21: Released enhancements to Recurly's in-the-box tax solution to support taxation in Chile.  [Learn more.](https://docs.recurly.com/docs/tax#section-supported-countries)

## February

* 2/25/21: Release Pay with Venmo as a new payment method available via our partnership with Braintree.
* 2/25/21: Released a [prerenewal webhook](https://developers.recurly.com/reference/webhooks/index.html#subscription-prerenewal) which is sent 1 day before each subscriptions renewal. This can be used as a notification to log additional usage, one time charges, or make updates to the subscription that can be included for the renewal invoice.
* 2/25/21: Released additional support for usage add-ons with a tiered pricing model to allow for [usage corrections](https://docs.recurly.com/docs/usage-based-billing#section-usage-corrections). Usage logged for a previous billing period will be charged on top of the usage already billed in that billing period
* 2/18/21: Released decimal pricing for usage add-ons. Recurly can now support up to 9 decimal places for usage-based billing.  [Learn more.](https://docs.recurly.com/docs/decimal-pricing)

# 2020

### December

* 12/29/20: Released enhancements to Recurly's in-the-box tax solution to support Brexit related tax changes.  [Learn more.](https://docs.recurly.com/docs/eu-vat-2015#section-brexit-implications)
* 12/3/20: Released the ability to Preview an Invoice when creating a new subscription within the Recurly App Admin UI. ([learn more](https://docs.recurly.com/docs/create-subscription#section-invoice-preview))

### November

* 11/19/20: Released support for Quantity Based Usage Add-Ons for Xero and Quickbooks Online.
* 11/19/20: Updated the [Hosted Account Management](https://docs.recurly.com/docs/hosted-account-management) page and added new [email parameters ](https://docs.recurly.com/docs/subscription-terms-new#section-emails) to better support Subscription Billing Terms.
* 11/12/20: Released Prepaid Account Balance for the Admin Console enabling customers to prepay for their future subscriptions and one time purchases so merchants can collect cash immediately. ([learn more](doc:prepaid-account-balance))
* 11/5/20: Released Items on Subscriptions.  This improvement provides merchants the flexibility to create plans that sell any item(s) in their catalog without defining a plan for every specific item combination. ([learn more](https://docs.recurly.com/docs/catalog#section-selling-items-directly-on-subscriptions)).
* 11/5/20: Released the ability to Preview an Invoice when editing a subscription within the Recurly App Admin UI. ([learn more](https://docs.recurly.com/docs/change-subscription#section-invoice-preview)).

### October

* 10/29/20: Released support for Item Coupons ([learn more](https://docs.recurly.com/docs/coupons#section-item-coupons)).
* 10/12/20: Released Recurly for Salesforce v2.39.3. [Release notes](https://docs.recurly.com/docs/salesforcereleasenotes#section-version-2-39-3-october-12-2020).

### September

* 9/24/20: Released Recurly for Salesforce v2.39 ([release notes](https://docs.recurly.com/docs/salesforcereleasenotes#section-version-2-39-september-2020))
* 9/17/20: Released [Prepaid Account Balance](doc:prepaid-account-balance) functionality enabling customers to prepay for their future subscriptions and one time purchases so merchants can collect cash immediately
* 9/10/20: Released updates to the Avalara for Communications integration
* 9/10/20: Released [Multiple Tax Numbers](https://docs.recurly.com/docs/site-settings#section-tax-information) functionality to allow merchants to issue invoices with Tax Identification Numbers specific to the customer's country. This allows for better international invoice compliance.
* 9/10/20: Updated payment gateway configuration flow to support education around payment gateways and invitation of other users who are best positioned to configure the gateway in Recurly.
* 9/10/20: Launched [Secure Data Sharing](https://docs.snowflake.com/en/user-guide/data-sharing-intro.html) integration with [Snowflake](https://www.snowflake.com/). Recurly data exports can be requested through the [Snowflake Data Marketplace](https://www.snowflake.com/data-marketplace)

### August

* 8/31/20: Recurly for Salesforce v2.38 released
* 8/27/20: 100+ currencies added to Recurly. [Learn more](https://docs.recurly.com/docs/currencies#section-supported-currencies). American Express Card Refresher: Merchants can now input their own SE number to register for American Express Card Refresher.
* 8/21/20: Clarified documentation for Russian VAT rate and the fact that reverse charge is no longer applicable. Functionality already reflected this.
* 8/14/20: [FlexibleField mapping support for Vertex Integration](https://docs.recurly.com/docs/vertex#section-flexible-fields)
* 8/7/20: Early Access for [Avalara for Communications Integration](https://docs.recurly.com/docs/afc)
* 8/7/20: Support for Vertex Version 9.0 (version 7.0 is being deprecated 12/31/20)

### July

* 7/30/20: All country/region codes in the Recurly application have been updated to match the latest ISO listings.
* 7/30/20: For businesses with their own Avalara AvaTax accounts that are leveraging [accrual-basis sales tax accounting](https://docs.recurly.com/docs/avalara#section-connect-your-avalara-ava-tax-account) in Recurly, invoices will now be committed in Avalara upon creation rather than upon payment.
* 7/30/20: Released [Quantity-Based Pricing](https://docs.recurly.com/docs/billing-models#section--quantity-based-) for Usage Add-Ons. Usage Add-Ons that charge a price per unit now support tiered, volume, and stairstep pricing models. The V3 API now includes support for Usage-based billing.
* 7/16/20: Based on new tax guidance, the logic supporting coupons applied to tax-inclusive transactions has been updated. Coupons applied to tax-inclusive transactions are now treated as tax-inclusive themselves. Contact Recurly Support for further details if necessary.
* 7/16/20: Added ability to Preview Subscription Changes in the [V3 API ](https://developers.recurly.com/api/v2019-10-10/index.html#operation/preview_subscription_change)
* 7/9/20: Fixed bug that allowed revenue recognition schedule to be set for subscription add-ons via the V3 API when the revenue recognition feature was not enabled.
* 7/7/20: Released new option to [define recurring item add-on charges at the subscription level](https://docs.recurly.com/docs/catalog#section-configuring-item-add-ons-directly-on-subscriptions) rather than the plan level. This functionality is in Early Access testing at this time. For early access to this feature, please contact Recurly Support.

### June

* 6/25/20: Added API and Recurly.js support for BACS via GoCardless.
* 6/18/20: Fixed bug that prevented invoices with older add-ons from syncing between Recurly and Quickbooks Online & Xero.
* 6/11/20: Adyen level II card data support released.
* 6/11/20: Updated invoice info when viewing invoices in the Recurly Admin Console for sites with the Credit Invoices feature enabled. The Invoice Info card will now clearly indicate if an invoice was created prior to the Credit Invoices feature being enabled, so that it's easy to understand how future actions on that invoice will work.

### May

* 5/28/20: Released [Quantity-Based Pricing](https://docs.recurly.com/docs/billing-models#section--quantity-based-) for Item Add-Ons. Items added to plans can now support tiered, volume, and stairstep pricing models.
* 5/28/20: Updated Zendesk Integration introducing Recurly for Zendesk Sell. Chat and Support now offer permissions for Professional Zendesk customers with Groups.
* 5/28/20: Added support for charging Mexican VAT when using Recurly Taxes.
* 5/7/20: China UnionPay Support added to the Chase Orbital gateway.

### April

* 4/30/20: Updated the Item Details URL format to only include pagination when uninvoiced charges exist for that item (triggering the display of those charges in a paginated table at the bottom of the page). The base item URL will continue to redirect automatically to the paginated URL when uninvoiced charges exist.
* 4/23/20: Released [Quantity Based Pricing Models](https://docs.recurly.com/docs/billing-models#section--quantity-based-) for Add-ons. These pricing models are now supported for Add-ons charged at the beginning of the billing period. The same pricing models will be available for Items and Usage Add-Ons later in Q2. If you are interested in the Items and Usage functionality, please email [quantitybasedpricing@recurly.com.](mailto:quantitybasedpricing@recurly.com.)
* 4/23/20: Released GoCardless ACH support. This is supported on API V2 and V3 as well as RJS and Recurly HPP.
* 4/16/20: Released new [Item Add-Ons](doc:catalog) functionality enabling catalog items to be sold as add-ons on plans and subscriptions. This release also includes two new item-related exports.
* 4/9/20: Released functionality to choose between accrual-basis and cash-basis sales tax reporting for users connecting Recurly to their own Avalara AvaTax account.
* 4/2/20: Added external_sku field for saved item add-ons to the v2 Subscription Add-Ons and Subscriptions Add-Ons History exports.
* 4/2/20: Added Add-On Tier Type and Add-On Total Amount to the v2 Subscription Add-Ons and Subscriptions Add-Ons History exports to support the Quantity-Based Pricing Models.

### March

* 3/26/20: Released support for Croatian Kuna (HRK) across the following gateways: Adyen, Bambora, Braintree, CardConnect, Chase Orbital, Cybersource, First Data, Payeezy, Stripe, Vantiv, Wirecard, and Worldpay.
* 3/26/20: Released updates to Merchant e-Solutions integration to support new COF indicators.
* 3/12/20: Released new Item Add-Ons feature for Early Access testing! This allows catalog items to be sold as recurring add-ons on plans and subscriptions. This release also included two new item-related exports, the display of external_sku for saved item add-ons in the Subscription Add-Ons array in the Subscriptions webhooks, and an optional external_sku e-mail parameter for item add-ons and one-time item charges in customized e-mail templates. For early access to this feature, please contact Recurly Support.
* 3/5/20: Added revenue_schedule_type field to all v3 API requests and responses for the Plans, Plan Add-Ons, Subscriptions, and Purchases endpoints. This change spans all versions of the v3 API. The field will display in API responses for all sites, but will only be populated or accept values for sites using our Revenue Recognition feature.

### February

* 2/27/20: Recurly's integrations with [QuickBooks Online](doc:quickbooks) and [Xero](doc:xero) were updated to support the Item Catalog feature. Now, items created in Recurly are synced to the QuickBooks Online or Xero item catalogs, and both one-time and recurring item sales in Recurly are tagged to the appropriate QuickBooks Online or Xero items when passed to one of these accounting systems.
* 2/20/20: Released new [Item Catalog](doc:catalog) functionality enabling a catalog of offerings to be built in Recurly and sold via one-time charges. This release also included updated wording around add-on type and billing model on the Create/Edit Plan pages, and an update to the Billable Add-Ons table on the Plan Details pages to show Add-On Code instead of Accounting Code.
* 2/3/20: Released Convert Trial feature enabling a subscription to immediately move from a trial to a paid subscription when a customer requests to end their trial early. Current available in the Admin UI and V2 API.
* 2/13/20: Recurly launches a new integration with GoCardless! [Learn more](https://docs.recurly.com/docs/gocardless). The initial launch supports SEPA payments via Recurly's Hosted Pages, with API support coming soon, as well as additional payment methods.
* 2/13/20: Added new external_sku field for one-time item charges to the [Adjustments](doc:adjustments-exports) (v4), [Adjustments - Taxes](doc:adjustments-taxes-export) (v4), and [Adjustments - Coupons](doc:adjustments-exports) (v3) exports.
* 2/6/20: Added support for Discover Stored Credentials for the Payeezy Gateway.
* 2/6/20: Added new external_sku field for one-time item charges to all Adjustments (v2.24) and Line Items (v2019-10-10) API endpoints.
* 2/3/20: For one-time item charges, the attribute populated in the product_code field in our Adjustments and Line Items API endpoints was switched from the item's external_sku to the item's item_code, to better align with upcoming item add-ons. All historic one-time item charges were updated so the data is consistent over time. Upcoming releases will pass this change on to our Adjustments exports, and add an additional field for displaying external_sku.

### January

* 1/30/20: Released update to Adyen to support Visa Free Trial Mandate.
* 1/2/20: Released updated export for Subscriptions - History (V2)

# 2019

### December

* 12/17/19: Phased rollout starts for the new [Item Catalog](doc:catalog) functionality. This feature will be enabled for all sites with the Credit Invoices feature over the upcoming weeks. To get immediate access to this feature, please contact [Recurly Support](support.recurly.com).

### November

* 11/27/19: Recurly introduces the newest version of our integration with Zendesk. The first release enabled support agents to find details on a customer’s account and subscription information directly within their Zendesk interface. The second release adds the ability to Pause, Cancel, and Refund subscriptions; also within the Zendesk interface. Check out the full details  [here](https://docs.recurly.com/docs/recurly-for-zendesk).
* 11/22/19: Added Stored Credential support for Bambora.
* 11/22/19: Recurly introduces our new [Item Catalog](doc:catalog) functionality for early access testing. To get access to this feature on your site, please contact [Recurly Support](support.recurly.com).
* 11/14/19: Pause and Postpone requests will now update the current_period_ends_at to be reflective of when the current period will end. Historically these dates were not updated and were not accurate when a subscription was paused or postponed.
* 11/1/19: Recurly introduces Gateway Failover. To safeguard your payments against gateway downtime, [learn more](https://docs.recurly.com/docs/gateway-failover) about this feature.

### October

* 10/10/19: Recurly API v3 is now GA. Features JSON and foundation built upon OpenAPI. Get started with the [Quickstart Guide](https://developers.recurly.com/guides/quickstart.html) or take a look at the [Upgrade Guide](https://developers.recurly.com/guides/v3-upgrade-guide.html) if you're upgrading from v2.
* 10/10/19: ZDA support across all supported gateway integrations completed.
* 10/2/19: Released [Recurly for Zendesk Support](https://www.zendesk.com/apps/support/recurly-for-support/?source=app_directory) and [Recurly for Zendesk Chat](https://www.zendesk.com/apps/chat/recurly-for-chat/?source=app_directory). Integrate subscriber details into your support and chat ticket interface, saving time, optimizing your revenue, and providing great service to your customers.

### September

* 9/26/19: Fixed bug on edit subscription page which will now display the Plan Name and not the Plan Code in the dropdown.
* 9/12/19: Added [Declined Refund](https://docs.recurly.com/docs/credit-invoices-release#section-block-all-declined-refunds) invoice setting for merchants using the Credit Invoices feature. Enabling this setting sets the default behavior for declined refunds to block the transaction rather than issuing a refund credit invoice.
* 9/5/19: Change and cancellation subscription requests now support three timeframes for the UI and API: immediately, at next bill date, and at term renewal. Renewal requests are currently supported but will be deprecated in a future API version. For any API Requests before 2.21: For merchants with more than one billing period on any subscription, renewal requests will be converted to next bill date. For merchants with only one billing period on any subscription, renewal requests will be converted to term renewal. This enables all API integrations on subscriptions terms to be backwards compatible.

### August

* 8/20/19: We have enabled the majority of sites on [Subscription Terms](https://docs.recurly.com/docs/subscription-terms-new). Your existing Subscriptions and API integrations will notice no changes to their behavior but there are some minor UI changes to the Subscription Details card. In order to change the bill date for a Subscription, you will now need to use the dropdown and select Change Next Bill Date.
* 8/15/19: Fixed bug in DocDate assignment for tax documents in Avalara. DocDate will once again be updated to reflect the transaction paid date when a transaction is committed.

### July

* 7/18/19: Added new [Invoices - Unused Numbers](https://docs.recurly.com/docs/invoices-exports#section-invoices-unused-numbers) export

### June

* 6/27/19: Added an update to ensure at renewal changes will result in the subscription term renewing for the full term length
* 6/20/19: Added ability to schedule changes to subscriptions [At Next Bill Date](https://docs.recurly.com/docs/change-subscription#section-at-next-bill-date-changes) for Update Subscriptions (V2), Update Subscriptions (V3), and UI
* 6/14/19: Automated Exports will only maintain the last 60 days of files available to be downloaded.
* 6/6/19: Added support for ACH transactions via Adyen gateway using API. Learn more [here](https://docs.recurly.com/docs/check-gateway-ach#section-adyen-ach-gateway-integration).

### May

* 5/23/19: [Shipping Fees](https://docs.recurly.com/docs/shipping) are now generally available in Recurly! This feature allows merchants to easily and accurately bill for shipping fees for physical goods.
* 5/23/19: Added 'cc_first_6' column to the end of both the <a href="https://docs.recurly.com/docs/billing-info-export">Billing Info</a> and <a href="https://docs.recurly.com/docs/transaction-export">Transaction</a> exports as a new version 4.
* 5/23/19: Exports will use the site timezone (under Site Settings) rather than the users timezone when determining what data will be exported. Additionally, the days that are requested will be exported in their entirety rather than potentially having missing data for current day.
* 5/2/19: Added compression (zip) to all Data Exports accessible thru Recurly App. For more information see [Exports](doc:export-overview).
* 5/2/19: Released the ability to configure [Shipping Methods and Shipping Fees](https://docs.recurly.com/docs/shipping). Contact us to enable this feature.
* 5/2/19: Released updated exports for Subscriptions (V3), Subscriptions - Churned (V2), and Adjustments (V2).
* 5/2/19: Added support for Thai VAT collection

### April

* 4/25/19: Added 'cc_first_6' column to the <a href="https://docs.recurly.com/docs/billing-info-export">Billing Info</a> and <a href="https://docs.recurly.com/docs/transaction-export">Transaction</a> exports
* 4/23/19: Released [new version](https://docs.recurly.com/docs/salesforcereleasenotes) of the Salesforce integration.

### March

* 3/28/19: Released an integration with the CardConnect payment gateway. [Learn More](https://docs.recurly.com/docs/cardconnect).

### February

* 2/21/19: Released [shipping fees beta](https://docs.recurly.com/docs/shipping).
* 2/21/19: Added support for Korean in email languages.
* 2/19/19: Added support for Amazon Pay in Europe and the United Kingdom. [Learn more](https://docs.recurly.com/docs/amazon-payments#section-amazon-pay-support-in-europe-and-the-united-kingdom-).

### January

* 1/31/19: Added option to change the sidebar color of your Recurly site. (The sidebar is the section on the left with site navigation links.) Currently, your Recurly sidebar is purple. Now, Recurly provides three new color options: teal, blue, and steel grey. More information [here](https://docs.recurly.com/v1.0/docs/site-settings)
* 1/31/19: Increased the number of [custom fields](https://docs.recurly.com/v1.0/docs/custom-fields) available by plan.

# 2018

### December

* 12/13/18: Recurly announces support for our Custom Gateway Routing feature, which allows allow merchants to route transactions to a specific payment gateway. [Learn more](https://docs.recurly.com/docs/custom-gateway-routing-configuration).

### November

* 11/29/18: Added support for the Icelandic Krona (ISK) on the Wirecard gateway.
* 11/09/18: [Recurly for Salesforce](https://docs.recurly.com/docs/salesforce) V2.24 has been released

### October

* 10/11/18: Support for SOFORT (Klarna Instant bank transfer) via the Adyen HPP integration.
* 10/11/18: Recurly now supports the exporting of billing info from Adyen into Recurly for recurring subscription renewals for the SEPA payment method (includes SEPA, iDEAL, and SOFORT).
* 10/11/18: Visa Stored Credentials Mandate: Added Ecommerce Indicators to Vantiv (Litle) Gateway.

### September

* 9/27/18: All sites are now able to export [custom fields](https://docs.recurly.com/docs/custom-fields) in their Accounts and Subscriptions export.
* 9/27/18: Added support for Thai Baht (THB) currency within Recurly, and to the Adyen gateway.
* 9/20/18: Recurly Taxes powered by Avalara now supports <a href="https://docs.recurly.com/docs/tax#section-europe-non-eu-">Liechtenstein</a>.
* 9/20/18: adjustment_tax_code column added to the <a href="https://docs.recurly.com/docs/adjustments-taxes-export">Adjustments - Taxes export</a> for Vertex in Version 2.
* 9/20/18: Only Bill What Changed now <a href="https://docs.recurly.com/docs/change-subscription#section-credit-discounts">smooths discounts on credits</a> instead of favoring the customer and only reversing a discount once necessary.
* 9/20/18: Transaction Export: added 'gateway_code', which notes which gateway was used for each transaction.

### August

* 8/16/18: If you have access to Manual Invoicing, you can now set a PO Number on automatic invoices from your Admin Console.
* 8/9/18: If the Credit Invoices feature is enabled, manual invoices can no longer be reopened from the Invoice Details page. You must void the manual transaction directly in order to reopen the invoice.
* 8/7/18: New email parameter subscription_customer_notes to show the subscription's customer notes.

### July

* 7/19/18: Requiring successful transaction on subscription upgrade now also requires successful collection on all automatic collection past due invoices on the account. <a href="https://docs.recurly.com/docs/invoice-settings#section-require-paid-invoice-and-successful-transaction-on-upgrades">Learn more</a>
* 7/12/18: Recurly is now integrated with Vertex for global tax collection on the Elite plan. <a href="https://docs.recurly.com/docs/vertex">Learn more</a>
* 7/12/18: Fixed a typo in the credit_payment webhooks in the original_invoice_number attribute.
* 7/12/18: Removed the symbol data type from the invoice "origin" attribute in the charge_invoice, credit_invoice, and new_dunning_event webhooks due to a vulnerability.
* 7/12/18: Automated Exports can now be configured via the admin console. This process was previously a custom set up. For sites on professional, Elite, and Enterprise plans, this allows you to add new exports to your configurations and bump versions of existing exports on your own.  More [HERE](https://docs.recurly.com/v1.0/docs/export-overview#section-automated-exports)

### June

* 6/25/18: Updates for Visa Stored Credential mandate for MIT and CIT transactions were applied to the First Data gateway.
* 6/14/18: Add ILS Currency to WorldPay and Braintree

### May

* 5/14/18: NEW [Subscription history export ](https://docs.recurly.com/docs/subscription-history-export) available to all sites.  Track upgrades, downgrades, add_on changes, etc.
* 5/11/18: Added additional payment methods to Adyen HPP, including: ACH, Qiwi, and iDEAL.
* 5/7/18: The new <a href="https://docs.recurly.com/docs/invoices">Credit Invoices</a> feature is now automatically on new Recurly sites.
* 5/4/18: New <a href="https://docs.recurly.com/docs/invoices">Credit Invoices</a> feature available to enable on existing Recurly sites.

### April

* 4/12/18: Updates for Visa Stored Credential mandate for MIT and CIT transactions were applied to Braintree, Adyen and TSYS gateways.
* 4/12/18: Invalid Avalara credentials will no longer disable Recurly's connection with our Avalara account. <a href="https://docs.recurly.com/docs/avalara#section-invalid-avalara-credentials">Learn more</a>
* 4/5/18: MRR on multi-currency sites now shows total across all currencies, converted into site's primary currency

### March

* 3/22/18: One new column added to the [Gift Cards](https://docs.recurly.com/docs/gift-cards-export) export (redemption_invoice_number)
* 3/14/18: Added shipping address to Kount fraud check request.
* 3/8/18: Canada is now supported on the Vantiv / Litle gateway. Recurly.JS mobile tabbing enhancement to tab into and out of RJS hosted fields.
* 3/1/18: Added support for Czech Koruna (CZK) in Stripe. Updated Danish translations.

### February

* 2/22/18: Added the functionality to specify a shipping address per invoice line item when creating purchases via the /purchases API. I.e. you can specify different shipping addresses for every subscription and each one time product even if those items are all purchased at the same time. [Learn more](https://docs.recurly.com/v1.0/docs/shipping-address-per-line-item#section-shipping-addresses-per-line-item).
* 2/22/18: Enhanced Xero integration to add the ability to sync different income accounts by plan (applies to new invoices only)
* 2/22/18: An activity is now created when an uninvoiced charge or credit is deleted
* 2/22/18: A new activity is now created when a transaction is retried manually, outside of the automated retry schedule
* 2/22/18: Updated existing pre-renewal email template to have a configurable send timeframe. Added a pre-renewal email template for SEPA Payment Method subscription renewals. Added a pre-renewal email template to be sent before a subscription renewal when a users credit card is expired.
* 2/15/18: Added additional currency support for the Adyen gateway integration - Argentine Peso (ARS), Chilean Peso (CLP), Venezuelan Bolívar (VEF), South Korea Won (KRW),Hong Kong Dollar (HKD), Colombian Peso (COP).
* 2/8/18: New refreshed email template designs
* 2/8/18: Payment Processing, Refund Processing, and Payment Voided email templates have been deprecated and removed
* 2/8/18: The Subscription Change email template now includes the invoice in the body of the email and as a PDF attachment
* 2/8/18: New refreshed invoice design with Payments section
* 2/8/18: New Dunning templates that allow you to create different emails for each step in your dunning cycle

### January

* 1/18/18: Added a webhooks link to the Account page (just above the activity log) to make it easy to see webhooks sent for that specific account. Note: this link is visible only if you have access to view webhooks.
* 1/11/18: [Invoices - Line Items - Coupons](https://docs.recurly.com/v1.0/docs/adjustments-exports#section-adjustments-coupons) export renamed to "Adjustments - Coupons" and four new columns added (invoice_due_on, adjustment_subtotal, adjustment_credit_reason_code, adjustment_refundable_amount)
* 1/11/18: [Invoices - Line Items](https://docs.recurly.com/v1.0/docs/adjustments-exports#section-adjustments) export renamed to "Adjustments" and four new columns added (invoice_due_on, adjustment_subtotal, adjustment_credit_reason_code, adjustment_refundable_amount)
* 1/11/18: Six new columns added to the [Invoices - Summary](https://docs.recurly.com/v1.0/docs/invoices-exports#section-invoices-summary) export (invoice_doc_type, invoice_balance, invoice_balance_modified_at, invoice_discount, invoice_subtotal_before_discounts, invoice_refundable_amount)
* 1/11/18: One new column added to the [Revenue Recognition Schedules](https://docs.recurly.com/docs/revenue-recognition-export) export (invoice_origin)
* 1/11/18: Two new columns added to the [Accounts Receivable](https://docs.recurly.com/docs/accounts-receivable-export) export (invoice_balance and invoice_balance_modified_at)
* 1/11/18: Recurly.js has launched Card Hosted Fields support for a single iFrame to collect all required credit card information. [Learn more.](https://developers.recurly.com/pages/recurly-js.html)
* 1/8/18: Recurly now supports additional currencies via the Adyen Gateway for Russian Ruble (RUB) and Chinese Yuan (CNY).

# 2017

### December

* 12/14/17: Recurly now supports single sign-on through Okta. [Learn more](https://docs.recurly.com/v1.0/docs/single-sign-on). Added support to the Pricing API via Recurly.JS for multiple subscriptions purchased in the same transaction.

### November

* 11/30/17: Security enhancements to the process of changing your email address
* 11/16/17: New password security coming soon: starting 12/4 your Recurly password will need to be updated at least once every 90 days and your new password cannot match one of your 4 previous passwords.
* 11/9/17: Recurly launches an [integration with the Adyen Hosted Payment Pages](https://docs.recurly.com/docs/adyen#section-adyen-hosted-payment-pages).
* 11/2/17:  Recurly supports Amazon's CloseBillingAgreement API. This API will notify Recurly when a user closes the billing agreement within Amazon, Recurly can be notified and clear out the billing agreement, since it is no longer valid. This is a recommended best practice from Amazon. This feature is behind a feature flag. Contact support to enable this feature.
* 11/9/17: Analytics Subscriber Retention calculation for paying subscriber cohorts has been modified.
* 11/16/17: NEW Analytics Report released.  Understand how effective your dunning settings are at recovering revenue and subscriptions with the new Dunning Effectiveness Report. [Learn More](https://docs.recurly.com/docs/dunning-effectiveness-report)

### October

* 10/12/17:  Added support to Apple Pay on the Web for automatically pulling in Billing Info when a user pays with Apple Pay. Updated user permissions for configurations and integrations.
* 10/12/17: Added support for Amazon IPNs regarding refund status updates, and billing info updates. With these additional notifications, merchants are able to see the status of refunds within Recurly App in order to take the desired action to the account, and be notified of billing info updates regarding a billing agreement to then retry transactions. IPNs will need to be enabled and configured within Amazon in order to receive the updated stats for these events. [Learn more](https://docs.recurly.com/docs/amazon-payments#section-amazon-instant-payment-notification-messages-ipn-) about Amazon IPNs.

### September

* 9/21/17: The Trial Performance report calculation for "converted" has been modified so that subscriptions in trial that pay set up fees are no longer considered converted. The subscription must have paid its actual unit amount to be considered converted. For Recurly.js, on mobile browsers the card expiration fields will now be native dropdowns instead of input fields.
* 9/14/17: Updates to Recurly.js to add a. the ability to scan / take photo of a credit card with Safari on an Apple device and b. allow external form fills to populate credit card fields (LastPass, Google Wallet, iCloud Keychain).

### August

* 8/31/17: An activity is now created when a manual invoice is reopened
* 8/17/17: Added new column to the end of the Transactions Export for failure_type. New [email parameters](https://docs.recurly.com/docs/email-templates#section-parameters) for billing info: payment method as well as transaction specific payment method, credit card type, and credit card last 4 digits.
* 8/10/17: Added new column and date range option to the [Subscriptions Export](https://docs.recurly.com/docs/subscriptions-exports). This enables sites to export subscriptions that have been created but not yet activated.

### July

* 7/27/17: Introduced a new Analytics report: [Trial Performance](https://docs.recurly.com/docs/trial-performance-report). It is available to sites on our Enterprise and Professional plans. Enhancements made to Analytics Billings report to separate out new vs. renewing customer billings and provide better multi-currency support.
* 7/13/17: API v1 has been deprecated. We added a date picker to the Customer index pages (Accounts, Subscriptions, Invoices, and Transactions) so that you can now narrow your search to a date or range of dates. We also added a "currencies" filter to the transactions index page. You can now [save an end-customer's PayPal shipping address to Recurly](https://docs.recurly.com/docs/paypal-payments#section-collect-paypal-shipping-address).)

### June

* 6/29/17: Added new [MasterCard 2-series test card number](https://docs.recurly.com/docs/test) for sandbox sites. Added support for a 'company' property to RJS. [Only bill what changed in an immediate subscription change](https://docs.recurly.com/docs/change-subscription). **The Reports section of the navigation (and all reports under that section) have now been removed from the application. These reports have been replaced by the improved[Analytics section](https://docs.recurly.com/docs/recurly-analytics)**
* 6/15/17: In-the-box taxes now support South Africa. Added support for Australia's new GST rules on cross-border sales of digital services. Fix bug with PayPal Express Checkout on IE 11. Improved ability to preview emails.
* 6/1/17: Added support for PayPal Express Checkout to the Hosted Payment Page

### May

* 5/25/17: In the Admin Console you can now retry payment on a past due invoice after dunning is complete. Update handling of "soft decline" for Amazon Payments.
* 5/18/17: New updated_account_notification webhook when account information is changed
* 5/12/17: Changed "Active Subscriptions" and "% Churned" calculations to better align with Subscriber Churn rate (on Dashboard)  calculation. See [Churn Analysis](https://docs.recurly.com/docs/recurly-analytics#section-churn-analysis)
* 5/11/17: Extended the site default options for net-terms to include a custom length.
* 5/4/17: Recurly is now in beta with an integration with Adyen for credit / debit card processing. [Learn more.](https://docs.recurly.com/v1.0/docs/adyen). Redesigned Email Index Page: we have completely re-imagined the look and feel of our email template page UI to make it easier to navigate and understand. Past due invoices will now automatically attempt collection after a new subscription is added to the account. Recurly now supports PayPal Express Checkout and One Touch when using Recurly.js v4. [Learn more](https://docs.recurly.com/docs/paypal-payments).

### April

* 4/19/17: Recurly now offers DKIM signing for emails. [Learn more](https://docs.recurly.com/docs/email-templates#section-spf-and-dkim-records).
* 4/13/17: Recurly now supports free trials without billing info! [Learn more](https://docs.recurly.com/docs/plans#section-free-trials-without-billing-information).
* 4/6/17: Merchants creating custom charges and credits on an account in the Admin Console can now include a product code

### March

* 3/30/17: Updated Account Updater service to improve efficiency. End of life for our old Salesforce integration. Quickbooks Online integration update to map one-time charges to the default account in Quickbooks Online sync.
* 3/22/17: Added support for [Apple Pay on the Web](https://docs.recurly.com/docs/apple-pay-on-the-web) through Stripe! New API Rate Limit Email that will be sent to site administrators and technical contacts when a site hits its API rate limit within a 12-hour window. Added device fingerprint collection for Braintree v.zero in Recurly.js. Added ability to choose a liability account as the default account for QuickBooks Online. New purchase endpoint for invoicing multiple adjustments and requiring successful payment.

### February

* 2/23/17: Added support for Russia's 2017 tax rules on cross-border sales of digital services
* 2/17/17: Recurly Exports download process has changed to improve reliability.  All sites will start to see a slight change to the download process over the next several weeks. See more information [here](https://docs.recurly.com/docs/export-overview#section-exports-update-2-17-17-)
* 2/17/17: One-time charges can now have their own product code via API v2.5
* 2/17/17: You can now process PayPal transactions through Braintree.

### January

* 1/25/17: Analytics Subscriber Growth Report now separates new subscribers from reactivated subscribers. See the definition of a reactivated subscriber [here](https://docs.recurly.com/docs/recurly-analytics#section-subscriber-growth)
* 1/25/17: Updated visual design of the [Hosted Payment Page](https://docs.recurly.com/docs/hosted-payment-pages)
* 1/25/17: Added [Gift Card Hosted Payment Page](https://docs.recurly.com/docs/gift-cards#section-hosted-pages)
* 1/25/17: Updated [Hosted Account Management Page](https://docs.recurly.com/docs/hosted-account-management) to 1. allow Gift Card redemption and 2. display "credits on account"
* 1/20/17: Dunning now includes the option to leave invoices past due at the end of the dunning cycle. [Learn more](https://docs.recurly.com/docs/dunning-management).
* 1/12/17: Zero amount adjustments made through the API are now charges instead of credits.
* 1/5/17: Recurly Analytics now offers [Analytics Settings](https://docs.recurly.com/docs/recurly-analytics#section-analytics-settings). The first setting option available allows Analytics users to choose whether or not coupons discounts and failed invoices are included in their MRR calculation. See more in the Analytics [documentation](https://docs.recurly.com/docs/recurly-analytics#section-analytics-settings).
* 1/5/17: We added [a new webhook](https://developers.recurly.com/pages/webhooks.html#account-notifications) that is sent whenever a customer attempt to update their billing information is unsuccessful.
* 1/5/17: Added [a new API endpoint](https://developers.recurly.com/api/latest.html#operation/collect_invoice) that allows you to force a collection on a pending or past-due Invoice.

# 2016

### December

* 12/15/16: We are proud to launch a new **integration with Quickbooks Online**. [Read more about our integration,](https://docs.recurly.com/docs/quickbooks) and how it helps you accelerate your month-end close process, automate your revenue accounting flow, and eliminate manual processes.
* 12/15/16: In today's release we also updated invoices with tax so that they now show the Tax column to the right of Subtotal and include a Total column at the end.
* 12/8/16: Enhanced handling of Braintree token. Added a new attribute to inform customers whether the dunning webhook is the last one or not
* 12/1/16: Gift card redemption codes can be a custom length between 15 and 20 characters

### November

* 11/17/16: Optimized Account Updater lookups. [Learn more about Account Updater](https://docs.recurly.com/docs/account-updater).
* 11/10/16: Added CVV checks for initial transactions in Payeezy. Added Stripe support in more countries. Recurly now sends a webhook for each invoice in dunning, whenever it is time for a dunning communication: use these to power in-app messages. [Learn more about Recurly's webhooks](https://docs.recurly.com/docs/webhooks), or see our [webhooks documentation for developers](https://developers.recurly.com/pages/webhooks.html).

### October

* 10/20/16:
  * New and improved support for **gift subscriptions and gift cards** is now available to customers on the Professional and Elite plan! [Learn more](https://recurly.com/gift-subscriptions/) and then [read the detailed documentation](https://docs.recurly.com/docs/gift-subscriptions). The feature includes updates to the Subscriptions and Subscriptions - Churned exports ... which now include two new columns for the Gift Cards feature: started_with_gift and converted_at. Plus we have added a new Gift Cards export with gift card purchase and redemption information.
  * Updated Recurly.js to add automatic spacing into credit card numbers entered on checkout forms to make them easier for end-customers to read and validate that they are entering the number correctly.
  * Added shipping address support to Recurly.js pricing module.

* 10/13/16: Recurly now supports shipping addresses! [Learn more](https://docs.recurly.com/docs/shipping-addresses).

* 10/6/16:

* Support added for the October 1, 2016 changes to NZ GST on digital services.

* The Subscriptions - Churned export now shows "Tax Location Invalid" instead of "VAT Invalid Location" as an expiration_reason for EU VAT Location Validation.

* The Accounts export column "vat_location_invalid" is now called "tax_location_invalid" and is supported by a new column called "location_validation_tax_type".

* Send dunning email immediately when Recurly won't schedule retry attempts (hard declines and billing info not found).

### September

* 9/22/16: Invoices will now follow dunning schedule that was active at the time the invoice entered dunning. We will retry a failed transaction before sending first delayed dunning email.

* 9/14/16: Added support for Hong Kong Dollar currency.

* 9/9/16: Added support for Beanstream in UK. Added ability to correlate previous failed signup transaction attempts. Added support for new MasterCard BIN ranges.

* 9/9/16: Recurly now supports the ability to choose whether or not to send an email at the plan level. You can toggle each email on or off on the plan create / edit page. [Read more about this in our documentation](https://docs.recurly.com/docs/email-templates#section-enabling-and-disabling-email-templates).

### August

* 8/25/16: [Two Factor Authentication](https://docs.recurly.com/docs/two-factor-authentication) is now generally available. Added Account Acquisition Data to the [Account export](https://docs.recurly.com/docs/export-overview#section-accounts).

* 8/17/16: Country drop-downs list user's country at the top of the list. Update to ACH emails to send only one email to confirm ACH payment on a new subscription at the time of signup.

* 8/15/16: New [Recurly Analytics](https://docs.recurly.com/docs/recurly-analytics) includes refreshed versions of the old reports with enriched calculations and better usability as well as 5 new advanced reports.

* 8/10/16: Add-ons now support both fixed-price and [usage-based billing](https://docs.recurly.com/docs/usage-based-billing). Recurly now supports Account Acquisition Data so Merchants now have the ability to record account acquisition data on each account in their Recurly site.

* 8/3/16:

* [Revenue Recognition](https://docs.recurly.com/docs/revenue-recognition) is now available.

* Added [Free Trial Coupons](https://docs.recurly.com/v1.0/docs/coupons#section-free-trial-coupons).

### July

* 7/13/16: Added Mexican Peso to WorldPay.

* 7/7/16: Updated the Hosted Account Management page to ensure that tall logos render correctly. New email parameter to show line item discounts in email body invoice displays.

* 7/6/16: Two Factor Authentication for increased security (beta).

* 7/1/16: Updated Recurly.js v4 to improve handling of coupon errors and pricing.

### June

* 6/29/16: We've made 2 big updates to the Recurly V2 API. First, we've added date filtering & pagination which allows merchants to query records from the V2 API based on a date range based on when the records were created or updated. Second, we've added Account Balance which allows merchants to query the balance on an account record. We also updated the Hosted Account Management page to ensure that merchant logos display correctly.

* 6/16/16: Added ability to configure color of placeholder text in Recurly.js v4. Added gateway, gateway_error_code and failure_type to failed payment webhook notification.

* 6/8/16: Improvements to the Worldpay integration. Added payment_method, billing_phone, billing_postal, billing_country to payment related webhooks.

* 6/7/16: Under certain circumstances, we will display reCAPTCHA on the [Hosted Payment Pages](https://docs.recurly.com/docs/hosted-payment-pages) to help ensure the validity of attempted purchases.

### May

* 5/23/16: Added support to Recurly.js v4 for collecting data relevant for fraud checks.

* 5/18/16: Fixed issues with Webhooks "created" date. With this fix, the page now correctly sorts on this date.

* 5/4/16: CVV Checks for Paypal CC gateways.

### April

* 4/28/16:

* Usage-based billing is now available in beta! [See how it works!](https://docs.recurly.com/docs/usage-based-billing). [Contact Support](mailto:support@recurly.com) if you're interested in participating in the beta.

* New [email parameters for add-ons](https://docs.recurly.com/docs/email-templates#section-subscription-and-add-on-fields). Invoice email templates now include a Qty column in the invoice table and Discounts is now above Subtotal.

* 4/14/16: Recurly now allows merchants to add multiple webhook endpoints. When combined with multiple API keys, merchants can now easily integrate with multiple business systems to further automate key business processes.

* 4/13/16: Add-on invoice line items no longer include quantity and the append of "Add-On"

### March

* 3/30/16: Lots of bug fixes. Added "Company Name" to billing info in the Recurly Admin.

* 3/2/16: End date added to account-level credits. Site drop down is now ordered alphabetically.

### February

* 2/24/16: New risk (fraud) check details columns added to the transactions export. Webhooks Delivery Retry Logic modified.

* 2/18/16: Fixed CVV validation bug in Recurly.js v4. Added ability to set target currency when adding billing info for an account.

* 2/5/16: New columns in the Coupons and Coupon Redemptions exports. See more info in our <a href="https://docs.recurly.com/export-overview">exports documentation</a>.

### January

* 1/26/16: New column in Transactions export called "collected_at". New column in Coupon Redemptions export called "Coupon ID". Ability to configure AVS Checks on First Data.

* 1/13/16: New version of <a href="https://recurly.com/recurlyjs/">Recurly.js</a> to help you reduce your PCI scope. Check out the <a href="https://docs.recurly.com/js/">updated documentation</a>!

* 1/6/16: UI improvements to the account details page to make it easier to use. Added support to retain scroll position between page changes. Multiple other UI bug fixes.

# 2015

### December

* 12/9/15: Read Only User Permission. Multiple API Keys. Read-Only API Keys. Additional currencies in Stripe (New Zealand Dollar, South African Rand, Singapore Dollar, Polish Złoty).

* 12/2/2015: Update failed invoices if ACH payment was successful. New currencies and countries: Braintree Blue in New Zealand, Swiss Franc (CHF) currency in Stripe, Cybersource in South Africa.

### November

* 11/5/2015: New subscriptions through the API that include a coupon redemption and fail due to a declined transaction will no longer remove an existing active redemption on the account. The invoice redemptions API endpoint now correctly shows all coupon redemptions that discounted the invoice, regardless of their status. Subscription-level coupons can now be redeemed in immediate subscription changes.

### October

* 10/30/2015: Added ability to configure when first dunning email is sent. You can now control when to enforce Cybersource's AVS checks on the gateway configuration page.

* 10/23/2015: Handling new error messages returned from Chase Paymentech. Launched Stripe support for Austria. Subscription-level coupon redemptions will be removed if subscription is changed to ineligible plan.

* 10/16/2015: Allow refund attempt on transaction over 60 (or 120) days old. Quick link to the Bulk Unique Coupons export now available on the Coupon Overview page. Fixed formatting issue with %s on report tooltips. Handling new error messages returned from PayPal, Stripe, Sagepay, and Braintree.

* 10/08/2015:
  * We're very exited to announce that many new coupon features are now available, like bulk unique coupons, multiple coupons per account, <a href="https://docs.recurly.com/coupons">and more</a>!
  * Also new this week: Improved error message displayed when the transaction amount is too small for the gateway. EU VAT numbers are now validated only at sign-up and every 6 months to reduce VIES validation downtime issues. Merchants can now test invalid EU VAT numbers in sandbox mode with 000000000. Fixed issue where subscription terminate and refund was blocked for zero amount invoices.

* 10/01/2015: Added payment_method to the <a href="https://docs.recurly.com/export-overview#transactions">transactions export</a>, and launched First Data support for new countries (Please see <a href="https://recurly.com/gateways/">Recurly Gateways</a>) for gateways supported in your country).

### September

* 09/24/2015: Calls to our API v2 Account end point now returns 'cc_emails'.

* 09/17/2015: First Data gateway integration maintenance.

* 09/10/2015: Added a bunch of new columns to the Invoice - Line Items export, and added original_invoice_number to all 3 Invoices exports to help associate refund invoices to original purchase invoices.

### August

* 08/27/2015: Ability to set "setup fee accounting code" for one-time setup fee in the App UI. Ability to set Date Range for one-time charges.

* 08/20/2015: Ability to set setup_fee_accounting_code for one-time setup fee via the API. Coupon Redemptions export now includes 'uuid' and 'currency'.

* 08/13/2015: First Data Payeezy gateway integration. Integration with Check Commerce online application portal. Fixed email formatting issue with credit card type parameter.

* 08/06/2015: Single Use coupons are now calculated in subscription change credits. Single Use coupons will no longer be used up on free trial invoices if the subscription does not have a setup fee, or if the coupon has a percentage discount. Subscription Preview API no longer requires billing information. Send "Payment Confirmation" email (if enabled) when manual invoice is paid online and converted to automatic collection. Local businesses in Singapore can now process their transactions in Singapore Dollars (SGD) using Braintree or Cybersource.

### July

* 07/31/2015: Tax previews now exist in the Preview Subscription API call for AvaTax Pro customers.

* 07/30/2015: Coupons can now be made with a duration of days, weeks, months or years. The Invoices - Line Items export now includes coupon codes. Invoices in the Admin UI now links to related invoices. Added character restrictions to account_code. Future subscriptions with invalid addresses will now activate when taxes are turned on.

* 07/24/2015: Account Information Phone Number field no longer blocks fallback to Billing Information address on invoice. Handle retry attempts from Check Commerce.

* 07/16/2015: Invoices on sandbox sites now have "TEST INVOICE" as a watermark. Stripe now supported in Nordic countries.

* 07/09/2015: ACH payment gateway provider Check Gateway is now called Check Commerce. Add "account_closed_at" to the "Get Accounts" API.

* 07/01/2015: Account coupon management improvements in the new UI. Create Transaction API endpoint now supports tax_exempt and tax_code parameters. ACH now supports voiding transactions.

### June

* 06/29/2015: Tax Settings now includes the option to disable Avalara address validation.

* 06/25/2015: Gateway error code added to lookup transactions API. Invoices without an address will not be considered taxable. Taxes now supported for refunds after a jurisdiction is disabled. Automatic payments on manual invoices now available on the Enterprise plan. Subscription refunds now default to no proration. Transaction Refunds have been deprecated. All refunds will now use line item or open amount refunds. ACH Bank Payments are now available on the Enterprise plan.

* 06/19/2015: Improved translation of Invoices to German.

* 06/19/2015: Avalara address validation now supported for taxed purchases.

* 06/11/2015: "Reopen" button for Customer Service users on failed manual invoices. A Site Settings country is now required to add or edit a Payment Gateway. Added new email parameters. Invoice Line Items export now includes invoice number and state.

* 06/05/2015: Added support for "full refunds" in the invoice Open Amount Refunds API. Recurly now supports taxes in all European countries. Refund Invoices due to voids now say VOIDED on the invoice. Refunds can now specify "transaction first" via the API.

### May

* 05/28/2015: Added "account closed at" date to Accounts Export. Fixed issue where Hosted Page logo uploads would fail when editing settings for the first time.

* 05/21/2015: Added gateway error_code to Transactions Export. Hosted edit billing info page now defaults to most recent gateway added.

* 05/14/2015: Manual transactions can now be voided. Added IP address to Lookup Transaction API.

### April

* 04/23/2015: Payment Declined email template subject has been updated to "Your Payment Has Been Declined".

* 04/16/2015: Email previews now use consistent data for Merchant Name and Customer Name & Address.

* 04/14/2015: Clearing your site data will now delete any uncommitted tax docs in AvaTax.

* 04/09/2015: Invoices and Invoice Summary exports now include an invoice_type column that has either 'purchase' or 'refund'.

* 04/07/2015: AvaTax Pro tax documents cannot be committed when Recurly site is in sandbox mode in order to allow document deletion when moving to production mode. Recurly's estimated tax previews now round down for digits under five, and up for five and higher.

* 04/02/2015: Fixed "count of accounts" on Reporting Dashboard.

### March

* 03/19/2015: Bugfix for stripe refunds that were, in some cases, showing as Voided in Recurly but were actually Refunded in Stripe. The Invoices and Invoices Summary exports now include a "modified_at" column at the end that shows the date the record was last edited. Sandbox and Production webhooks may now send on different schedules to prioritize production delivery. Recurly Merchants whose subscriptions are cancelled for non-payment will now have their sites closed after 30 days of nonuse.

* 03/05/2015: Wirecard Error Code 34 is now classified as a generic fraud response.

* 03/03/2015: Refund adjustments in the API now have quantity_remaining to show the remaining amount of the original charge that has yet to be refunded. For non credit card billing info, you are no longer required to store first and last name.

### February

* 02/26/2015: New PayPal Error codes for: paypal_cannot_pay_self, reference_transactions_not_enabled, billing_agreement_not_accepted, and billing_agreement_already_accepted. Drop down links on Hosted Account Management pages are now fully clickable.

* 02/19/2015: Recurly will send notifications if your Public API key or Payment Gateway are modified.

* 02/18/2015: Recurly will now notify you by email if your password has changed.

* 02/11/2015: Added a new column to the Invoices export called "original_adjustment_uuid" to link credits to the previous credit they were created from.

* 02/10/2015: Added a new column to the Invoices export called "original_adjustment_uuid" to link credits to the previous credit they were created from.

* 02/05/2015: A bug has been fixed that will prevent certain duplicate push notifications from being sent. Legacy VAT feature for the European Union has been deprecated.

* 02/03/2015: Adjustments API now includes original_adjustment_uuid for connecting a credit to the previous credit it was created from. Improved support for Amazon errors and messages. For customers using Vantiv, a new option in Payment Gateway Settings allows you to retry all hard declines to better use Vantiv's AAU.

### January

* 01/29/2015: We've improved our integration with Wirecard to better support the Recurly Account Updater. The Adjustment API now includes tax_type, tax_region, and tax_rate.

* 01/27/2015: Added support for tracking of deleted accounts in our Salesforce integration. Contact support to learn more!

* 01/20/2015: Tax invoices now include line item tax amounts and in the case of more than one rate, tax rate information is displayed in the line item description. Invoices API now includes the customer's address for the specific invoice.

* 01/19/2015: Webhooks that mention an invoice number now have a new field called invoice_number_prefix that is only populated with a value for EU VAT country specific invoice sequencing. This fixed a previous bug where the country code prefix was not displaying correctly in the webhooks.

* 01/06/2015: API responses for a subscription will now include the Update Subscription Notes endpoints. Recurly now supports amazon payments. Please contact our support team to learn more.

# 2014

### December

* 12/18/2014: VAT Location Validation account status has been added to the Accounts export as vat_location_valid. Recurly.js v3 tax previews now support digital rates with the tax_code parameter. Update Subscription API now supports invoice notes editing when "/notes" is added to the call. Trailing and leading whitespaces will now be removed from all hosted page submissions in all form fields.

* 12/16/2014: Fixed short-term bug where site invoice prefix numbers were showing in the invoice number for 3D secure transactions with SagePay and Wirecard.

* 12/15/2014: Our new EU VAT features for 2015 are now available.

### November

* 11/18/2014: For "Current period" - Future subscriptions no longer show a "current period" until they are activated.

### October

* 10/29/2014: Hosted Account Management pages have been updated to a new style and include new invoice management features. Sites that switch to Invoice Refunds will now be blocked from making Transaction Refunds via the API. A customer's hosted pages login token can now be reset by merchants through the Admin. New Invoice Settings option to use account address for the Bill To address and for tax calculations on all invoices. Refund invoices for European Union VAT transactions now use the original invoice's customer VAT number for tax calculations.

* 10/07/2014: We removed three deprecated pages: coupons_v1, accounts_v1, transactions_v1.

* 10/02/2014: API v2 now supports invoice previews for taxes on adjustments. Merchants can now configure Canada tax collection to GST only.

### September

* 09/30/2014: If tax services are down, new signups are now blocked and renewals are queued up until tax services are back online. Made updates to our Reporting service to improve scalability.

* 09/25/2014: Deprecated old content at /signup and moved the new content from /join to /signup.

* 09/17/2014: Improvements to Recurly.js integration with PayPal for IE users.

* 09/09/2014: Modified the blog feed source.

### August

* 08/27/2014: Improved results returned on /subscriptions_v2 page. Added filtering of trial or paid on /subscriptions_v2 page. Added more search parameters to /subscriptions_v2 page.

* 08/26/2014: Charges with tax codes are now denoted on invoices. Avalara integration is now available on Sandbox sites. "Use Invoice Date" is now an option on Adjustments export. Added VAT number to the billing info in the Admin Panel (already support in the API). Polish Zloty is now an option for Braintree gateway.

* 08/21/2014: Fix a UI bug in the terminate subscription flow in the Admin Panel. General availability for Canada, Australia, New Zealand and Israel taxes. General availability for Canada, Australia, New Zealand and Israel taxes.

* 08/20/2014: Enabled search on /invoices page and sped up page load. Improvements were made for PayPal error message handling. A bug in refund charges dates was fixed. A bug in Gateway test configuration result page was fixed. Net term billing issue with manual invoice is fixed. Coupon redemption total recalculation amount is fixed. When processing a transaction for a tax region where multiple special jurisdictions are applied, the rate is appended into the field.

* 08/07/2014: Push notification configuration workflow was fixed.

### July

* 07/29/2014: Address requirement for tax estimation is clarified.

* 07/22/2014: Updates were made to the way we handle error messages from Stripe and Litle.

* 07/17/2014: V2 of the coupons page was deprecated for no longer being necessary.

* 07/15/2014: A change was made to a transaction error message for clarification.

* 07/09/2014: PayPal transactions limitations have been updated to reflect changes by PayPal. The Show VAT button in the Hosted Payment Page Settings will now always show the VAT number, regardless of country.

* 07/08/2014: An issue was fixed where the MailChimp sync time was not being correctly displayed. An issue was fixed where verification_value would sometimes lose its value before being stored.

* 07/02/2014: An issue was fixed where canceled subscription URLs would sometimes result in a 404.

### June

* 06/26/2014: A bug was fixed related to enabling and disabling Canadian sales tax.

* 06/23/2014: New invoice and subscription pages were announced.

* 06/19/2014: Export timezone changes were made. Search facets were tweaked.

* 06/18/2014: Announcement made regarding export changes.

* 06/17/2014: Rolling API keys were added. Improvements were made to the Redeem Coupons dropdown menu. A visual bug was corrected on some of the gateway pages.

* 06/12/2014: The MailChimp integration was improved.

* 06/10/2014: The PayPal checkout flow for Recurly.js V3 was improved.

* 06/09/2014: A new parameter was added to the email templates: current_period_end. This shows the time a subscription will end.

* 06/05/2014: Authorization transactions have been renamed verifications.

* 06/04/2014: A new parameter was added to the email templates: current_period_end. This shows the time a subscription will end. The settings for Hosted Payment Pages were reorganized. New subtotal logic for the invoice email was added.

* 06/02/2014: Cancel button can now be removed from the Hosted Payment Pages. New Zealand Tax added.

### May

* 05/29/2014: Invoice web hooks were added. The grammar in an error code was corrected.

* 05/27/2014: Push notifications are now called Web Hooks. The formatting was improved for Taxes on the Hosted Account Management pages.

* 05/20/2014: The payment gateway settings UI was updated to show the Account Updater. An issue with Hosted Payment Pages in IE8 was corrected.

* 05/19/2014: Miscellaneous bug fixes around taxes. Tax labels no longer show "Sales Tax" if the region ends in ST (such as GST, PST, etc). Taxes by country are now show on the Edit and New Subscription pages.

* 05/15/2014: Coupon searching was improved.

* 05/13/2014: A bug was fixed related to US Sale Tax configuration. Error messaging around VAT and Sales Tax was improved.

* 05/12/2014: New Zealand is now a supported country for Cybersource.

* 05/07/2014: Subscriptions can no longer be activated on a closed account. Various improvements were made to the Coupons page, such as sorting, formatting, and expiration behavior. An issue was fixed where a deleted coupon could occasionally be redeemed.

* 05/05/2014: The /js/v1/token endpoint now uses the :postal_code param in addition to :zip. An issue was corrected that would cause the fix six numbers of a credit cad to not appear correctly.

### April

* 04/30/2014: The Non-Renewing subscriptions facet now includes both canceled and no remaining renewals. Coupons V2 announced. An issue was corrected where duplicate emails would be sent when a future subscription was activated. An issue was corrected where the currency selector would sometimes incorrectly appear on Hosted Payment Pages.

* 04/29/2014: Partial transaction UUIDs can now be searched. Transactions V1 deprecation announced.

* 04/28/2014: The Closed Invoices facet now only shows successful invoices. Tooltips were added to the Invoices and Transactions facets.

* 04/24/2014: Tooltips were added to Subscription facets.

* 04/23/2014: A CSS issue related to disabled buttons was corrected. Line item exports have been added.

* 04/21/2014: State is now only a required field if the country is set to US. The accounts page has been updated with an announcement about its deprecation. Tooltips were added to the new accounts page.

* 04/14/2014: The Resend Email button no longer appears in the email is disabled. The Invoices Refund by Line Item now responds with a 201.

* 04/10/2014: A bug was corrected that caused future subscriptions to fail when a site had no enabled gateways. Upcoming transactions page changes announced through banner on transactions page. IE8 is no longer a supported browser.

* 04/09/2014: Public keys can now be regenerated in the UI. Terms of service were updated.

* 04/08/2014: Transaction UUIDs can now be searched. Transaction notes are now shown on the details page. Public key for Recurly.js V3 was added to the API access page. Hungarian Forints (HUF) is now a supported currency in emails. Offline manual payments can now be entered using the API. Tax calculations are no longer shown on exempt subscriptions. The address used for taxation calculations was corrected. Plan name is now shown on the accounts page, instead of plan code.

### March

* 03/31/2014: Emails entered on the Hosted Payment Pages can now be longer than 50 characters.

* 03/28/2014: The subscriptions API now includes a Subscription Change Preview. Max logo height on Hosted Payment Pages is now unrestricted. Max width is 555px. Validation is now performed on IP addresses on the Allowlist.

* 03/26/2014: A bug related to correctly setting approval_code has been fixed. Text that displays when changing billing cycle of a plan has been updated to specify that the change will happen at renewal.

* 03/25/2014: Invoice - Line Items export added. Subscription churn export added.

* 03/24/2014: The new accounts page has gone live.

* 03/21/2014: Database improvements related to add-on ordering were made. Logo size on Hosted Payment Pages is now constrained to 250x100.

* 03/12/2014: Fixed an issue that affected browsers that don't support the placeholder attribute (for instance, IE8)

* 03/11/2014: Search results are now more specific. An issue was corrected with the Hosted Payment Pages pricing display. Send Trial Email checkbox is now displayed on the Subscription Plan edit page. Phone number was been added to billing account info form. Tax exempt related fields are now shown when US Sales Tax is enabled.

* 03/03/2014: Added UI information for when Address Requirement is set to None (sales tax won't be calculated). Amputated Exports with new Invoices Summary. Ability to enable US Sales Tax support. Ability to toggle tax exemption for accounts, plans or charges.  Updated hosted payment pages UI, added US Sales Tax support. Added API objects with tax amounts and details. Added subscription preview API with client libraries. Admin Panel updates for improved UX to support taxes and calculations. Added a new invoice summary export. Added country drop-down for account billing info. Enabled Recurly.js V3 Beta support.  Fixed calculations for refund and terminate for discounts and taxes.

### February

* 02/28/2014: Updated links to gateway error code explanation pages. Authorized_currencies is no longer reset during billing info update.

* 02/24/2014: Update to transparent post error messaging for null responses.

* 02/21/2014: Changed export functionality to stream directly to the API.

* 02/11/2014: No longer show expired coupons in emails. Subscription list page now links directly to the subscription.

* 02/10/2014: Added "VAT #" field for all merchants regardless of VAT collections. Added line item refunds to the API. Fixed bug with renewal reminders being sent for plans with 0 renewals left. Update link to intuit error codes. Fixed bugs with renewal terms when changing collection type.

* 02/07/2014: Fixed sort on push notifications.

### January

* 01/28/2014: Update r.js download to always point to the latest.
* 01/24/2014: Fix bug with add-ons migrating with plan changes. New subscription preview API endpoint.
* 01/15/2014: New info on ISO country standards.
* 01/15/2014: Add subscribe to status site for real time alerts.
* 01/13/2014: Add PLN to wirecard currencies.
* 01/13/2014: New logout message.
* 01/10/2014: Add collection method to push notifications.
* 01/02/2014: Added "discount" column to invoice export.
* 01/02/2014: Added links between invoices and subscriptions in v2 API responses.

# 2013

### December

* 12/30/2013: Changed subscription "edit" button to "more".
* 12/10/2013: Added support for 3-digit American Express CVVs.
* 12/09/2013: Updated pricing for Enterprise Plan.
* 12/09/2013: Bug fixes around VAT and Phone Number displays on invoices.
* 12/05/2013: Fix for updating billing information on manually invoiced accounts.
* 12/05/2013: Added support for NZD to Braintree
* 12/05/2013: Updated activity log to link account_code rather than UUID.
* 12/04/2013: Updated error messaging around passed expiration years.
* 12/04/2013: Added boolean logic to display VAT on email templates
* 12/04/2013: Auto update and backwards compatibility for VAT on email templates.

### November

* 11/26/2013: Added line_accounting_code parameter to email templates
* 11/15/2013: Added link to coupon from admin view
* 11/12/2013: Updated invoice style
* 11/05/2013: Updated user invite/welcome emails
* 11/05/2013: Better error messaging when a payment gateway times out
* 11/04/2013: Fix for 500 error when throttling API requests
* 11/04/2013: Activity log now links refund event to original transaction
* 11/04/2013: Recurly.js fix: setting add-on quantity to zero will remove the add-on
* 11/04/2013: Added postponement to the subscription change push notification

### October

* 10/28/2013: Clear net_terms when switching from manual to automatic invoicing
* 10/28/2013: Fix for SagePay and 3D Secure invoice numbers
* 10/28/2013: Added breadcrumbs to the transaction details page
* 10/24/2013: Removed extra fields from CSV exports to optimize export speed
* 10/24/2013: API fix to disallow setting both single use and applies to months to coupons
* 10/17/2013: Remove API access for useragent NING/1.0
* 10/16/2013: Fix to show proper coupon redemption currency on account view
* 10/15/2013: Fix to stop throwing 400 errors on merchants using an unsupported API parameter
* 10/14/2013: Added support for PayPal payments from Cambodia
* 10/14/2013: Support links now open in a new tab
* 10/14/2013: Corrected credits to be applied to the invoice total when VAT is applied
* 10/14/2013: Fixed multiple quantity credits not applying to user accounts via the API
* 10/14/2013: Fixed display of credits in the account balance where VAT was applied
* 10/09/2013: Added breadcrumbs to plan creation/details pages
* 10/09/2013: Update to email templates UI
* 10/09/2013: Depreciated v1 Hosted Payment Pages

### September

* 09/27/2013: Added a Void/Refund email
* 09/26/2013: Updated icons on admin console
* 09/26/2013: Moved renewal reminder and trial ending emails out of beta
* 09/19/2013: Added line_item_uuid to the invoice export.
* 09/16/2013: Fixed bug with subscription renewal reminder emails and limited lifespan subscriptions
* 09/03/2013: Update to VAT validation process on Hosted Payment Page billing information updates

### August

* 08/29/2013: Allow Recurly merchants to upgrade their pricing plans
* 08/21/2013: Improved app UI loading times
* 08/20/2013: Subscription Renewal and Trial Ending emails to beta
* 08/20/2013: Timezone fix for API requests with "+00:00"
* 08/20/2013: Export buttons now link to new /exports page
* 08/15/2013: Modified Braintree multi-currency support setup
* 08/15/2013: Released fix for coupon pagination
* 08/14/2013: Included Croatia in EU country list for VAT calculations
* 08/14/2013: Added better UI support for long invoices
* 08/14/2013: Added gateway column to transaction export
* 08/14/2013: Fixed bug referencing all subscription changes as upgrades
* 08/13/2013: Added support for Person Accounts on the Salesforce Connector
* 08/05/2013: Added support for Diner's Club to Braintree Blue

### July

* 07/30/2013: API v2 pagination fixes
* 07/26/2013: Simplified user subscription to Recurly newsletters
* 07/17/2013: Allow Salesforce integration to connect to different environments
* 07/08/2013: Add transactions for header, footer email templates
* 07/08/2013: Updated menu icons
* 07/01/2013: Improved VAT support in email templates

### June

* 06/24/2013: Transaction status displayed on new Invoice view
* 06/24/2013: Released Manual Invoicing
* 06/24/2013: Partial Payment emails for Manual Invoicing
* 06/24/2013: New Dashboard for Production Customers
* 06/24/2013: VAT support for Manual Invoicing
* 06/10/2013: Added new invoice view
* 06/10/2013: Added new subscription view
* 06/10/2013: Added subscription reactivations to activity logs
* 06/10/2013: Updates to Danish transactions
* 06/10/2013: Added product_code to adjustments XML response
* 06/03/2013: Added support for more card types to Beanstream
* 06/03/2013: Added support for subscription add-on details in push notifications
* 06/03/2013: Updated Recurly.js v2.2.2 Merchants on V2.2.x should update for PayPal bug fix
* 06/03/2013: Salesforce no longer overwrites company name if Recurly  company name is blank

### May

* 05/27/2013: Added "Days past due" on invoice overview
* 05/27/2013: Split out invoice view into automated/manually collected invoices
* 05/27/2013: Updates to Recurly.js and VAT
* 05/20/2013: Added a "Deselect All" function for the Plans report
* 05/06/2013: Added coupon details view
* 05/06/2013: Added account level addresses to admin UI, emails, and exports
* 05/06/2013: UI changes and more details added to activity log
* 05/06/2013: Better validation around future start dates

### April

* 04/29/2013: Account notes (read only) added to API v2
* 04/29/2013: Fixed a coupon bug on new subscription emails
* 04/22/2013: Added support for CAD, GBP, and EUR for Authorize.net
* 04/15/2013: Added support for Swiss francs on Litle
* 04/15/2013: Updated error messaging for TSYS/Recurly Gateway error code 5
* 04/08/2013: Improved UX for multi-currency invoicing
* 04/01/2013: Improved messaging on Dunning Management UI

### March

* 03/18/2013: Recurly.js PayPal beta
* 03/18/2013: Fix to currency changes on Hosted Payment Pages
* 03/18/2013: Improvements to VAT validation
* 03/18/2013: Improved messaging around credits and refunds
* 03/11/2013: Better Hosted Payment Page support for subscriptions with limited renewals
* 03/11/2013: Better CVV validation - AmEx CVVs must be 4 characters, all other card types 3 characters
* 03/04/2013: Fixes for PayPal billing agreements with redirects
* 03/04/2013: Ability to modify stored billing address information, regardless of site address requirements

### February

* 02/25/2013: Improvements to speed in API queries
* 02/05/2013: Added enforcement for APIv2 to validate address requirements based on site settings
* 02/05/2013: Site admins can no longer update users in their site

### January

* 01/21/2013: Stopped creating credits for $0
* 01/21/2013: Set UTC on every API request when timezone isn't specified
* 01/21/2013: Apply coupon redemptions to trial invoice when there's a setup fee
* 01/21/2013: Adjust error messaging for CVV mismatch to note that error could be expiration date related
* 01/13/2013: Added additional encryption and storage layers for secure data
* 01/13/2013: Added custom color settings to Hosted Account Management page
* 01/07/2013: Adjusted coupons to expire at 11:59PM in the timezone they were created in
* 01/07/2013: Added a tooltip to explain coupon expiration time
* 01/07/2013: Enhanced API V2 to accept coupon expiration time

# 2012

### December

* 12/23/2012: Relabeled months to billing cycles on plans overview page
* 12/17/2012: Enabled Litle Automatic Account Updater
* 12/09/2012: Update mobile Hosted Payment Pages to support PayPal payments on iPhone
* 12/09/2012: Added support for IE10

### November

* 11/25/2012: Added coupon redemptions export
* 11/12/2012: Added validation for unique add-on codes at creation
* 11/12/2012: first_renewal_date will now update when a future subscription is postponed before it's first renewal
* 11/12/2012: Added validation for postpone dates when being set through the API

### October

* 10/21/2012: Removed Afghanistan as default country on Hosted Payment Pages dropdown
* 10/21/2012: Added details "hover" to display lengthy charge/credit description
* 10/14/2012: Removed European Union from countries list
* 10/14/2012: Added ability to postpone canceled subscriptions
* 10/14/2012: Removed future subscriptions from Subscriber Retention Report
* 10/14/2012: Updated current_period_ends_at_ date to return "nil" for canceled subscriptions
* 10/07/2012: Updated list of countries supported for PayPal purchases

### September

* 09/30/2012: Fail any open invoices when an account is closed
* 09/23/2012: Added per-plan subscription churn exports
* 09/23/2012: CSV exports now provide local timezone data
* 09/09/2012: Updated styling of Hosted Account Management Pages
* 09/09/2012: Added yellow billing information icon to indicate tokenized billing information
* 09/09/2012: Removed semicolons from use in account codes

### August

* 08/27/2012: Added support for Braintree in Canada and Europe
* 08/20/2012: Added conversions for known provides and countries to 2-char codes
* 08/20/2012: Added email activity to Activity Log
* 08/13/2012: Modifications to account details page to show invoice number in charges, invoice due date, and invoices above transactions
* 08/06/2012: Proper proration of subscriptions with custom first renewal date
* 08/06/2012: Added CC email to customer accounts

### July

* 07/30/2012: Credit Cards are no longer authorized unless Credit Card Number or Expiration Date are updated
* 07/23/2012: Allow "collect now" functionality in all site currencies
* 07/23/2012: Force selection of refund option when terminating a plan inside the Recurly application
* 07/16/2012: Modifications to subscriptions maintain original UUID
* 07/16/2012: Deleted Add-on codes can now be reused
* 07/09/2012: Made coupon parameters available in email templates
* 07/09/2012: Expanded currencies for Wirecard customers

### June

* 06/25/2012: Search on Coupon Name and Description
* 06/25/2012: Display "VAT" in front of VAT charges on a subscription
* 06/25/2012: Clarify Future Start Date inside of the Recurly App
* 06/25/2012: Remove JYP as a listed currency, as it's not supported
* 06/18/2012: Allow customers with PayPal info to pay via credit card on Hosted Payment Pages
* 06/18/2012: Added "verify" transactions for supported gateways to avoid authorizing and voiding $1 charges
* 06/18/2012: Relabeled "Refund" to "Refund Options..." on transactions
* 06/18/2012: Void transactions if there is an error saving account information for new accounts
* 06/11/2012: Added Ogone and Merchant eSolution gateways
* 06/04/2012: Set new users timezones when new users are created
* 06/04/2012: Added 3d secure support for SagePay
* 06/04/2012: Allow white labeling of IP addresses

### May

* 05/28/2012: Added subscription postpone to the API
* 05/28/2012: Added "Site Live" email for merchants
* 05/28/2012: Updated transaction error code when no gateway is present on the account
* 05/28/2012: Removed customer payment declined emails when no gateway is present on the account
* 05/28/2012: Marking invoice as successful/failed added to the API
* 05/28/2012: Expire active subscriptions when a Recurly site is closed
* 05/21/2012: Creating accounts via the API now shows up in the activity log
* 05/21/2012: VAT country and percent added to recurly.js
* 05/14/2012: New “edit subscription” button on accounts page
* 05/14/2012: Hosted Payment Pages: T and C’s and Privacy policy now open in new window
* 05/14/2012: Hosted Payment Pages: Set default payment type (CC vs. Paypal)
* 05/14/2012: Default all views to “all” for Accounts, subscriptions, invoices, and transactions
* 05/14/2012: Updated CSV exporter that streams files to browser
* 05/07/2012: Expire inactive sessions after 20 minutes
* 05/07/2012: Related transactions to subscription plans
* 05/07/2012: Set coupons description for Hosted Payment Pages via API

### April

* 04/30/2012: Added total billing cycles to the API
* 04/30/2012: Updated logic for calculating credits for VAT customers
* 04/23/2012: Push notifications for changing (postponing) a renewal date
