---
title: RELEASE NOTE (with Markdown Tables)
excerpt: >-
  Stay updated with the latest minor tweaks and enhancements in Recurly’s
  functionality through the Release Notes section. Explore a curated digest of
  UI upgrades, API extensions, and more that continually refine your user
  experience.
deprecated: false
hidden: true
metadata:
  robots: index
---
## August

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Release Date
      </th>

      <th style={{ textAlign: "left" }}>
        **Feature**
      </th>

      <th style={{ textAlign: "left" }}>
        **Potential Impact**
      </th>

      <th style={{ textAlign: "left" }}>
        **Description / Overview**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 29
      </td>

      <td style={{ textAlign: "left" }}>
        **Revenue Recognition**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        * Added deleted order lines to Order Stage History as archived data.<br />
        * Introduced Bundle Rule ID field in order lines for mapping.<br />
        * Extended Account Type table with 10 additional segment columns to support new segments.Added a data sync API check to update client indicators only when a job is set; revalidates before saving to prevent duplicate job updates.Implemented validation for VC date.<br />
        * Built the Workbench object and added a helper for tab switching.Added "Select All" button for Stage Area.<br />
        * Enabled book retention from the search page.<br />
        * Enhanced account type functionality by adding 10 new segments to `account_type_c`.<br />
        * Enhanced Standalone Selling Price (SSP) with multiple fixes, including criteria handling for "Approved" status, Compliance Pct corrections, SSP group item download and contract link, support for BundleRuleID/BundleParentID in criteria, editable Parent Identifier in new lines, and a fix for the Format ID unit test.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 26
      </td>

      <td style={{ textAlign: "left" }}>
        **Recurly Engage**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Minor updates to segment data CSV exports to better handle special characters in titles.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 26
      </td>

      <td style={{ textAlign: "left" }}>
        **Recurly Engage**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Enhance experiment window user experience by preventing auto-close on save.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 26
      </td>

      <td style={{ textAlign: "left" }}>
        **PayPal Complete gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        We are updating our currency support to include BRL, CNY, HDK, ILS, MXN, and THB to enable more processing opportunities for merchants. We will also be making minor tweaks to onboarding in Recurly Admin to allow merchants in several other countries to view PayPal Complete and onboarding without regional warnings. To learn more about

        [PayPal Complete](https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete#/)

        , visit our dedicated documentation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 26
      </td>

      <td style={{ textAlign: "left" }}>
        **v3 API**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Adding a new optional proration setting to several v3 endpoints.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 26
      </td>

      <td style={{ textAlign: "left" }}>
        **Stripe gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        We will be adding support for Indian e-mandates to support recurring processing for credit cards. This will enable Merchants who wish to expand into India with subscriptions the ability to stay compliant with RBI mandates. For more information on

        [Stripe](https://docs.recurly.com/recurly-subscriptions/docs/stripe#/)

        , please see our dedicated documentation. Our

        [RBI mandate documentation](https://docs.recurly.com/recurly-subscriptions/docs/rbi-regulations-update#/)

        will be updated after release with new support details.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 20
      </td>

      <td style={{ textAlign: "left" }}>
        **Kount Fraud Management**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Updated to account code handling to avoid errors in rare cases. To learn more about

        [Kount Fraud management](https://docs.recurly.com/recurly-subscriptions/docs/kount#/)

        , visit our dedicated documentation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 20
      </td>

      <td style={{ textAlign: "left" }}>
        **PayPal Complete gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        If PayPal (the digital wallet) is the primary payment method for a subscription and the PayPal subscription agreement is cancelled by the subscriber within their PayPal app or otherwise outside of Recurly, Recurly will now cancel that related subscription.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 19
      </td>

      <td style={{ textAlign: "left" }}>
        **Revenue Recognition**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        *Added display of the Initial Financial Open Period to the Revenue Settings page.<br />*Synced RevRec activation email timing with site activation to prevent premature sends. Introduced `enabled_email_sent_at `to track email dispatch after data sync, updated cron to handle unsent emails, and modified the Snappy Activate Site endpoint to respect sync status.<br />*Fixed overlap issue where the Recurly Resources button on the Home page covered the wizard when opened.<br />*Auto Period Close and Period Close Checklist job refactoring<br />*Fix auto period lag days to count complete N days<br />*Api to purge client and client data<br />*Hide RevRec settings for Setup Fees when no setup fee exists
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Adyen gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Minor updates to

        [iDeal](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ideal)

        to avoid an error for return customer signups.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Ebanx gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Minor updates to Pause events on UPI AutoPay mandates. Consumer-driven mandate pauses will be automatically paused for 1 year. Subscription pause lengths can be updated by a merchant after confirming length of pause with the consumer.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Ebanx gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Minor updates to trial handling to avoid a 1 INR charge.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Adyen gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Updated handling of

        [ACH](https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ach)

        Reporting queries to avoid improper invoice status updates.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **V3 Client Libraries**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Updated to support returning enhanced Google Pay indicators when a DPAN is in use.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Revenue Recognition**
      </td>

      <td style={{ textAlign: "left" }}>
        High
      </td>

      <td style={{ textAlign: "left" }}>
        Added scroll-to-top behavior when opening the Configuration of Default Rules section.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 12
      </td>

      <td style={{ textAlign: "left" }}>
        **Anomaly Insights**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        Introducing Anomaly Insights available on all subdomains. Anomaly insights to help merchants act instantly when transactional issues arise.

        [Anomaly Insights](https://docs.recurly.com/recurly-subscriptions/docs/recurly-compass#/anomaly-insights)

        documentation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 11
      </td>

      <td style={{ textAlign: "left" }}>
        **Ebanx gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        High
      </td>

      <td style={{ textAlign: "left" }}>
        Updates to mandate handling related to plan amount. Mandates will be sent with a dynamic plan + 18% tolerance for amount updates. This will support add-ons and trials where taxation is necessary. Read more about mandates in our

        [UPI AutoPay payment method](https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/)

        documentation.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 5
      </td>

      <td style={{ textAlign: "left" }}>
        **Compass Assistant**
      </td>

      <td style={{ textAlign: "left" }}>
        Low
      </td>

      <td style={{ textAlign: "left" }}>
        We're excited to announce the launch of Compass Assistant, now available across all active subdomains! This new conversational chatbot provides instant access to information from our product documentation and knowledge base, and can even furnish helpful code snippets for our APIs. You'll also notice that AI Answers will now direct you to Compass Assistant for a more comprehensive experience; should a merchant wish to opt-out, please contact Support.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 5
      </td>

      <td style={{ textAlign: "left" }}>
        **Revenue Recognition**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Revrec Enhancements in Recurly and RevRec-<br />Removed Auto Period Close Delay for Advanced Merchants in Revenue Settings.<br /><br />Removed Auto Period Close Delay option from the Self-Service Onboarding Wizard for RA-enabled merchants.<br /><br />Fixed datepicker in the RevRec enablement dialog to display correctly in front of the dialog (CSS update only).<br /><br />Updated RevRec Enablement Alert to display the correct text and buttons based on user permissions and site configurations.<br /><br />Updated Data Sync Finished alert logic to only display after `enabled_at` is set in the group memberships table, ensuring it appears only when the site is activated.<br /><br />Added validation for VC Rules to ensure "From Date" is less than or equal to "To Date."
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 1
      </td>

      <td style={{ textAlign: "left" }}>
        **MasterCard Account Updater**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Updates to flow involving querying the network for updates. This modification will be in addition to the current behavior where Recurly receives push notifications on registered cards. Please see our dedicated

        [Account Updater documentation](https://docs.recurly.com/recurly-subscriptions/docs/account-updater#/)

        for more information.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 1
      </td>

      <td style={{ textAlign: "left" }}>
        **Revenue Recognition**
      </td>

      <td style={{ textAlign: "left" }}>
        High
      </td>

      <td style={{ textAlign: "left" }}>
        Updates - removed open period logic from infra/revrecStart to prevent the period from reverting to the initial period.<br />Fixed bundle rule addition issue when only one bundle rule exists under a parent item by grouping the count by bundle ID.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Aug 1
      </td>

      <td style={{ textAlign: "left" }}>
        **Ebanx Gateway**
      </td>

      <td style={{ textAlign: "left" }}>
        Medium
      </td>

      <td style={{ textAlign: "left" }}>
        Updates to mandate handling related to plan amount. Mandates will be sent with a dynamic plan + 10% tolerance for amount updates.
      </td>
    </tr>
  </tbody>
</Table>

<br />
