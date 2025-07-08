---
title: Recurly Revenue Recognition Wizard
deprecated: false
hidden: true
metadata:
  robots: index
---
# Key details

After the Revenue Recognition feature is enabled for your site, you’ll notice several updates to your navigation panel prior to activating the feature.

1. A notification will appear, informing you that Revenue Recognition can now be enabled. This link will remain visible until you complete the enablement process.
2. A new "Revenue Recognition" section has been added to your main navigation menu. Advanced merchants will have access to advanced console options within this section, while standard merchants will be able to view Revenue Settings and General Ledger Accounts.

### **Revenue settings page:**

1. **Navigate** to Revenue Recognition > Revenue Settings.
2. **Adjust** the following required settings:
   1. **Auto Period Close Delay:** Specifies the number of days the system should wait after the end of a period before automatically closing it for standard merchants. The recommended minimum is 2 days, meaning the system will begin closing the completed period at the end of the second day. Merchants can choose to auto-close the period at any time after 2 days, depending on their business process.
   2. **Default Revenue Recognition Rules:** Set default rules for each type of plan, item, add-on, charge, credit, shipping method, and any other variant displayed on the screen for charges created prior to enabling the revenue recognition feature. The default value will be applied only if the system cannot find a rule at the charge line or plan/item level.
   3. **Global Reporting Currency:** Select a global currency for reporting purposes. Please note, this is separate from your site's global currency in Recurly. The global currency setup here is only for the purpose of revenue recognition.
   4. **Credit Transaction Handling:** For merchants using Advanced Revenue Recognition, you can specify how credit transactions—including Goodwill, On Account, and Prepaid Credits—are handled. If you choose the ‘ignore credit transactions’ option, revenue recognition will exclude these credit transactions from processing. To learn more about the various types of credits supported in Revenue Recognition, please refer to the **[Recurly Revenue Recognition Credits Documentation](recurly-revenue-recognition-credits)**.
   You can modify all these settings any time before activation. After activation, only the **Auto Period Close Delay** will remain editable.

### General ledger accounts