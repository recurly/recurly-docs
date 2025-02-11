---
title: Tax/VAT Rate Override
excerpt: >-
  The "Tax Rate Override" feature allows merchants to set a single fixed tax/VAT
  rate amount on their site to apply to all transactions.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# How to apply an overriding tax rate

You will need to have the feature flag for VAT Rate Override turned on for your site. This can only be enabled via Recurly Support. Once the feature flag is enabled, you will see the "Tax Rate Override" box appear on the right-side of your screen, with an "Enable" button. 

![](https://files.readme.io/ee75793-Screenshot_2023-06-01_at_4.14.46_PM.png)

Once you accept the enablement terms, you will see the edit view to input an overriding tax rate. Once you input the desired tax rate and press "Enable", your fixed tax rate will be applied to your site and the original "Taxes" Page will change to only show the the Tax Rate Override option. You can enter in whole percentages or decimal percentages up to the fourth decimal place. 

**Before pressing enable**

![](https://files.readme.io/23659cb-Screenshot_2023-06-01_at_8.42.36_PM.png)

**After pressing enable**

![](https://files.readme.io/1ebc800-Screenshot_2023-06-01_at_8.43.50_PM.png)

# Edit the Tax/VAT rate you have configured

You can edit the tax rate override amount at any point in time. All forward-moving transactions will leverage the new tax rate amount; pre-existing invoices will not change the tax rate amount applied at the time the pre-existing transaction took place. 

![](https://files.readme.io/f4d1bc5-Screenshot_2023-06-01_at_8.45.51_PM.png)

# Disable the Tax/VAT Rate Override

![](https://files.readme.io/567a899-Screenshot_2023-06-01_at_8.47.08_PM.png)

Once you have successfully disabled the tax rate override feature from your site, your Tax page will return to its original state with all in-the-box options to enable the desired regions you need configured on your site for tax calculation. 

![](https://files.readme.io/d1018e2-Screenshot_2023-06-01_at_8.47.56_PM.png)

# What changes when enabling the Tax Rate Override functionality?

- You will not need to enable or configure particular regions for tax support as you previously did on Recurly. The tax rate you input as your tax rate override amount will be applied to each and every transaction executed on your site, regardless of your merchant origin tax address and regardless of the customer's tax address. This tax rate will simply be used on every single invoice created across your site.
- You will, however, need to make sure that the "Collect Tax" checkbox is selected on each plan for the tax rate override feature to successfully be applied to any invoice leveraging a plan. Without selecting to collect tax on a plan, the invoices generated from that corresponding plan will not show any tax of any kind on the invoice. This is consistent with how the behavior of tax application on invoices works today using in-the-box taxes or a direct integration with a tax service. 

  ![](https://files.readme.io/d428d1f-Screenshot_2023-06-01_at_9.00.50_PM.png)

Furthermore, accounts with the "Tax Exempt" option applied to their account will also not have any taxes applied to their invoices to obey industry best practice. Tax exempt organizations typically include non-profits, charities, religious organizations, or educational organizations. You as the merchant can choose to make an account tax exempt or not. If you prefer to have these common types of "Tax Exempt" organizations still receive tax applied to their invoices, you must not select the "Tax Exempt" option on their account. 

![](https://files.readme.io/faa9be8-Screenshot_2023-06-01_at_9.29.12_PM.png)

Tax will appear on the invoice as "VAT X%: $ Amount" with the corresponding tax rate override applied as X, and the resulting tax rate amount value showing after the currency symbol. 

- This establishes a change from how in-the-box taxes or direct-integration taxes work because there is no specific country to associate a unique tax rate with, but rather, the site-wide tax rate you have applied is a general tax rate applied to all transactions regardless of the location of your business or your customers' location. Thus, a country prefix before the VAT rate amount on the invoice is not included.
- Applying an overriding tax rate will also ignore all reverse-tax rules. Once the overriding tax rate is set, all future transactions will have that tax rate applied, and, customers will need to manually request a reverse-VAT charge be issued from your company directly if their business does not qualify for VAT rate charges. 
- This is because there is no interaction/integration with a tax service in place. By selecting to override a site tax rate, you are acknowledging that you understand the tax rate you decide to apply to all transactions is up to your discretion, and you must maintain and update that tax rate as needed for your business.