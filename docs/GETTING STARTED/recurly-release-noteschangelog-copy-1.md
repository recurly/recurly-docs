---
title: RELEASE NOTES (with JSX tables)
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
        We are updating our currency support to include BRL, CNY, HDK, ILS, MXN, and THB to enable more processing opportunities for merchants. We will also be making minor tweaks to onboarding in Recurly Admin to allow merchants in several other countries to view PayPal Complete and onboarding without regional warnings. To learn more about
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/paypal-complete#/" target="_blank" rel="noopener noreferrer">PayPal Complete</a>, visit our dedicated documentation.
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
        We will be adding support for Indian e-mandates to support recurring processing for credit cards. This will enable Merchants who wish to expand into India with subscriptions the ability to stay compliant with RBI mandates. For more information on
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/stripe#/" target="_blank" rel="noopener noreferrer">Stripe</a>, please see our dedicated documentation. Our
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/rbi-regulations-update#/" target="_blank" rel="noopener noreferrer">RBI mandate documentation</a> will be updated after release with new support details.
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
        Updated to account code handling to avoid errors in rare cases. To learn more about
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/kount#/" target="_blank" rel="noopener noreferrer">Kount Fraud management</a>, visit our dedicated documentation.
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
        *Added display of the Initial Financial Open Period to the Revenue Settings page.
        *Synced RevRec activation email timing with site activation to prevent premature sends. Introduced `enabled_email_sent_at `to track email dispatch after data sync, updated cron to handle unsent emails, and modified the Snappy Activate Site endpoint to respect sync status.
        *Fixed overlap issue where the Recurly Resources button on the Home page covered the wizard when opened.
        *Auto Period Close and Period Close Checklist job refactoring
        *Fix auto period lag days to count complete N days
        *Api to purge client and client data
        *Hide RevRec settings for Setup Fees when no setup fee exists
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
        Minor updates to
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ideal" target="_blank" rel="noopener noreferrer">iDeal</a> to avoid an error for return customer signups.
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
        Updated handling of
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/adyen#/adyen-ach" target="_blank" rel="noopener noreferrer">ACH</a> Reporting queries to avoid improper invoice status updates.
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
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-compass#/anomaly-insights" target="_blank" rel="noopener noreferrer">Anomaly Insights</a> documentation.
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
        Updates to mandate handling related to plan amount. Mandates will be sent with a dynamic plan + 18% tolerance for amount updates. This will support add-ons and trials where taxation is necessary. Read more about mandates in our
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/upi-autopay#/" target="_blank" rel="noopener noreferrer">UPI AutoPay payment method</a> documentation.
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
        We're excited to announce the launch of Compass Assistant, now available across all active subdomains! This new conversational chatbot provides instant access to information from our product documentation and knowledge base, and can even furnish helpful code snippets for our APIs. You'll also notice that AI Answers will now direct you to Compass Assistant for a more comprehensive experience; should a merchant wish to opt-out, please contact Support.
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
        Revrec Enhancements in Recurly and RevRec-
        Removed Auto Period Close Delay for Advanced Merchants in Revenue Settings.
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
        Updates to flow involving querying the network for updates. This modification will be in addition to the current behavior where Recurly receives push notifications on registered cards. Please see our dedicated
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/account-updater#/" target="_blank" rel="noopener noreferrer">Account Updater documentation</a> for more information.
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
        Updates - removed open period logic from infra/revrecStart to prevent the period from reverting to the initial period.
        Fixed bundle rule addition issue when only one bundle rule exists under a parent item by grouping the count by bundle ID.
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