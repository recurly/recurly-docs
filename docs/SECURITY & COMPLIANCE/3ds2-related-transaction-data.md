---
title: 3DS2 Related Transaction Data
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
###Using Recurly Exports to Track 3DS2 Authentication Failures and Successes


####Failures
When a transaction is challenged for 3DS2 authentication, it will be declined with a 3DS2 decline failure <INSERT ERROR CODE / MESSAGE>. Since the transaction is being declined, you can track these failures using our transactions export. They can be identified by the failure type, <DECLINE CODE>, under column <COLUMN>. 

####Successes
To track customers who ultimately succeed 3DS2 authentication, you'll want to use our transactions export in conjunction with our <INVOICE> export. The steps to do this with Microsoft Excel are listed below:

1. Use our transactions export to identify any transactions declined due to <3DS2 DECLINE CODE>. These are transaction attempts challenged for 3DS2 authentication. 
2. Use our <INVOICE> export to join the data from the transactions export using Excel’s VLOOKUP command. 
3. Use the most recent transaction status to identify if 3DS2 authentication was completed
 * Success: Customer successfully completed authentication and processed a payment. 
 * 3DS2 decline: Customer did not complete authentication. 
 * Other decline: Customer successfully completed authentication, but did not process a payment due to a legitimate decline.