---
title: VAT number/Tax ID number validation
excerpt: >-
  A comprehensive guide on Tax ID Validation in Recurly, detailing how customer
  tax IDs and VAT numbers are verified through government lookups and format
  validation to ensure compliance with local regulations.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

# Definition

**Tax ID Validation** is a feature that verifies customer-provided tax identification numbers—such as VAT numbers—using government lookup systems and format checks. This process is essential to ensure that tax information is accurate for invoice generation, VAT collection, and regulatory compliance.

# Key benefits

* **Enhanced accuracy**: Ensures that customer tax IDs are correctly validated, which leads to more accurate VAT and tax calculations on your invoices.
* **Streamlined Billing**: Automates the verification process to reduce manual errors and simplify tax application, making invoicing more efficient.
* **Risk Mitigation**: Helps maintain regulatory compliance and minimizes the risk of fines by ensuring that all tax identifiers meet local standards.

# Enable or disable Tax ID validation on your Recurly site

VAT/Tax ID validation can be enabled or disabled for any merchant on any site by contacting Recurly Support. Recurly supports tax ID number validation via government lookups for some countries, and format validation checks for others. This page outlines the type of validation provided for each country where VAT/Tax ID number validation is supported on Recurly.

The tax ID validation for this location is automatically turned on for all sites. If you would like to disable it, please contact <a href="https://support.recurly.com/">Recurly support</a>.

### When VAT numbers are validated

VAT numbers are validated whenever a VAT number is added or updated to an account, at each billing event, or if an invoice is created more than six months from the last time the VAT number was validated. Here are the validation points:

* Adding or editing Billing Information
* Adding or editing Account Information
* Creating or renewing Subscriptions
* Creating one-time charges

## EU VAT validation

Recurly provides validation for European Union VAT numbers to keep merchants collecting VAT compliant in their B2B customer interactions.

### How VAT numbers affect VAT collection

VAT numbers are business tax registration numbers in countries that collect VAT (value-added tax). All 27 member states of the EU fall under one coordinated VAT system. EU businesses with a VAT number only pay VAT on purchases within their country. If an EU business makes a purchase from a different EU country, the business does not pay VAT on the transaction and instead delays VAT payment to their own tax filing in their own country. Due to this exemption at time of purchase rule, it is important that merchants validate whether a VAT number is real before issuing an invoice without VAT.

### Validation through VIES

Recurly is integrated with the European Commission's VAT Information Exchange System (VIES) for validating EU VAT numbers. This is the only means of validating a VAT number for an EU member state. All other services and tools that do VAT number validation are using the VIES system. It is not possible to access the individual country VAT number databases directly. You can access the VIES website here: <a href="http://ec.europa.eu/taxation_customs/vies/">[http://ec.europa.eu/taxation\_customs/vies/](http://ec.europa.eu/taxation_customs/vies/)</a>.

VIES VAT number validation is a separate feature from Recurly's EU VAT collection and is on by default for sites in production mode. The VAT number validation response (valid/invalid) is stored in Recurly, along with the date/time of the validation response, but Recurly does not currently capture or store the VIES consultation number (also called request identifier) for these responses that would tie them back to the VIES system.

### Invalid VAT numbers

A VAT number is invalid if we get a response from VIES explicitly saying the number is invalid, which means the number is not in their database. If a VAT number is invalid, we will not save it on the customer's account and will block any sign-up attempts with that invalid VAT number. We will not revalidate an invalid VAT number for 1 hour, so a customer attempting a sign-up with an already invalid VAT number will need to wait an hour before making another attempt. This may happen if your customer was recently issued their VAT number and the VIES database is not yet up to date.

If a VAT number becomes invalid while it's already on an account, the VAT number will remain on the account, but subscription renewals will go through with VAT applied.

If you have a customer claiming their VAT number is correct and VIES is showing that it is invalid, please consult the European Commission's FAQ question #13 on how the customer can fix the official record of their VAT number. [http://ec.europa.eu/taxation\_customs/vies/faq.html](http://ec.europa.eu/taxation_customs/vies/faq.html)

### VIES downtime and country maintenance windows

VIES is a validation endpoint that aggregates the 28 different EU country databases. Some of the 28 countries have regular downtime for maintenance. Unfortunately, VAT numbers for those countries cannot be validated at those times. You can see their maintenance windows here: [http://ec.europa.eu/taxation\_customs/vies/help.html](http://ec.europa.eu/taxation_customs/vies/help.html)

If we are unable to determine the validity of a VAT number, we will not save it on the customer's account and will block any sign-up attempts. We will re-validate a VAT number at subscription renewal if the VAT number has not been validated for six months. If the re-validation comes back without a valid or invalid response, meaning VIES or the individual country is down, we will fallback to the last validation status of the VAT number and will let the subscription renewal go through without VAT applied if the last status was valid, or VAT applied if the last status was invalid.

You can view the status of each state's VIES validator at [http://ec.europa.eu/taxation\_customs/vies/technicalInformation.html](http://ec.europa.eu/taxation_customs/vies/technicalInformation.html). Recurly uses the VIES SOAP API, which is represented in the right column, titled "Ws Access Status".

### Disable VAT number validation

Please contact <a href="https://support.recurly.com/">Recurly support</a> if you'd like to disable VAT number validation on your Recurly site.

### Test validation

VAT numbers are not validated in sandbox mode in order to allow merchants to test what a real VAT number would do. If you would like to simulate an invalid VAT number, you can use the number 000000000 with any EU country.

#### Sample invalid VAT number error

If you are planning on transitioning from sandbox mode to production mode, then it may be useful to know ahead of time the response Recurly will generate with invalid VAT numbers. Below is a sample XML error response that would occur when creating an account with an invalid VAT number:

##### Request

<pre class="headers">
  Accept: application/xml
  Content-Type: application/xml; charset=utf-8
</pre>

```
<account>
  <account_code>1</account_code>
  <email>verena@example.com</email>
  <first_name>verena</first_name>
  <last_name>example</last_name>
  <vat_number>INVALID_VAT_1234</vat_number>
  <address>
    <zip>28070</zip>
    <country>ES</country>
  </address>
</account>
```

##### Response

```
<errors>
  <error field="account.vat_number" symbol="invalid">is invalid</error>
</errors>
```

## UK VAT validation

Similar to the European Union, there is a VAT ID validation government lookup system available for businesses registered in the United Kingdom. Support for customer VAT ID/tax ID numbers out of the UK being validated for UK-based customers is automatically enabled for all merchants on all sites. This integration provided is via the HMRC. Recurly integrates with [this site](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/vat-registered-companies-api/1.0) via API for UK VAT ID lookups.

To turn on tax ID validation for this location on your Recurly site, please contact <a href="https://support.recurly.com/">Recurly support</a>.

## Australia ABN validation

Recurly maintains an [integration](https://abr.business.gov.au/) with the Australian Business Register (ABR) for tax ID number lookups with their government's business register for Australian Business Numbers (ABNs).

To turn on tax ID validation for this location on your Recurly site, please contact <a href="https://support.recurly.com/">Recurly support</a>.

## Belarus UNP validation

Recurly maintains an [integration](http://grp.nalog.gov.by/grp/rest-api) with the Belarus government business register lookup.

To turn on tax ID validation for this location on your Recurly site, please contact <a href="https://support.recurly.com/">Recurly support</a>.

## Dominican republic RNC validation

Recurly maintains an [integration](https://www.dgii.gov.do/wsMovilDGII/WSMovilDGII.asmx) with the government business register lookup in the Dominican Republic.

To turn on tax ID validation for this location on your Recurly site, please contact <a href="https://support.recurly.com/">Recurly support</a>.

## Format validation

There is a set of countries that Recurly provides customer VAT/tax ID number format checks for that do not leverage integrations with local government business registers, but are supported by a ensuring the VAT/tax ID number entered on a customer's account follows the given country's specific format guidelines. Upon account creation, or updating a customer accounts' VAT/tax ID number, Recurly will use parameters to ensure the number entered is adequate based on the given country's specifications.

To turn on format validation for all of the locations below, please contact <a href="https://support.recurly.com/">Recurly support</a>.

**Please Note**: All locations below *except for the United States* are grouped together under 1 enablement option. If you would like to *enable format validation for the United States, please call that out specifically* in your Support ticket.

<br />

| Location             | Local Tax Id Type(s) | Accepted Format                                                                                                                                                                                                                                                                                                                                                                      |
| :------------------- | :------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Åland Islands        | YT; ALV              | 8 or 9 numeric digits with or without a dash; 8 numeric digits with the optional prefix of FI                                                                                                                                                                                                                                                                                        |
| Albania              | NIPT                 | 10 characters with the additional optional prefix of AL, the 10 characters should be in the format "A NNNNNNNN A", where A=alphanumeric character and N=numeric character                                                                                                                                                                                                            |
| Algeria              | NIF                  | 15 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Angola               | TIN; NIF             | 9-10 numeric digits                                                                                                                                                                                                                                                                                                                                                                  |
| Armenia              | INN                  | 8 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| Barbados             | TIN                  | 13 numeric digits where the first number is always "1"                                                                                                                                                                                                                                                                                                                               |
| Benin                | IFN                  | 13 numeric digits where the first number is 3, 4, 5, or 6.                                                                                                                                                                                                                                                                                                                           |
| Bosnia & Herzegovina | MBS; JIB; PIB        | 12 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Canada               | BN                   | 9 numeric digits; 9 numeric digits followed by 2 alphanumeric characters and 4 numeric digits                                                                                                                                                                                                                                                                                        |
| Canary Islands       | NIF                  | 9 characters in the format ANNNNNNNA where A is a letter and N is a number; Optional prefix of ES, then followed by 1 letter which can be A-H,J,N,P-S, or U-W, followed by 7 numeric digits, end in 1 alphanumeric character                                                                                                                                                         |
| Chile                | RUT                  | 9 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| China                | USSC                 | 15 numeric digits; 18 characters where sometimes alphanumeric characters appear in the last 10 characters                                                                                                                                                                                                                                                                            |
| Colombia             | NIT                  | 10 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Costa Rica           | CPJ; NITE            | 9-12 numeric digits                                                                                                                                                                                                                                                                                                                                                                  |
| Ecuador              | RUC                  | 13 characters where 3rd digit is aways "6" or "9", the 4th-9th digit are numeric, and the last three digits are "001"                                                                                                                                                                                                                                                                |
| Egypt                | TRN                  | 9 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| Georgia              | TIN                  | 9 or 11 numeric digits                                                                                                                                                                                                                                                                                                                                                               |
| Iceland              | KN;VSK               | 10 alphanumeric characters; 5 or 6 numeric digits with the optional prefix of IS                                                                                                                                                                                                                                                                                                     |
| India                | PAN; GSTN            | 10 characters in the format AAAAANNNNA where A is a letter and N is a number; 15 characters in the format "NNAAAAANNNNAXAX" where the the first 2 characters are numeric digits, the next ten characters are a combination of alphanumeric and numeric characters, 13th character is a numeric digit, and the 14th character is the letter Z, and the 15th character is alphanumeric |
| Indonesia            | NPWP                 | 15 or 16 numeric digits                                                                                                                                                                                                                                                                                                                                                              |
| Israel               | CN                   | 9 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| Japan                | CN                   | 1st digit is a number 1-9, followed by 12 numeric digits                                                                                                                                                                                                                                                                                                                             |
| Kazakhstan           | BIN                  | 12 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Kenya                | PIN                  | 8 character code in the format XXXXXXXY where X is a number and Y is alphanumeric                                                                                                                                                                                                                                                                                                    |
| Kosovo               | NIB; NUI; NIF        | 8-9 numeric digits                                                                                                                                                                                                                                                                                                                                                                   |
| Kyrgyzstan           | TIN                  | 14 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Lebanon              | TIN; TIN+VAT         | 1-15 numeric digits; 1-15 digits, optionally followed by either "601", "603", or "604"                                                                                                                                                                                                                                                                                               |
| Liechtenstein        | PEIN; PEID; TIN      | 5 numeric digits; 11-12 numeric digits                                                                                                                                                                                                                                                                                                                                               |
| Macedonia            | EDB                  | 13 numeric digits with the option prefix of MK                                                                                                                                                                                                                                                                                                                                       |
| Martinique           | SPI; VAT             | 9 or 13 numeric digits; FR followed by 11 numeric digits                                                                                                                                                                                                                                                                                                                             |
| Mexico               | RFC                  | Business RFC #: 12 characters, with a format as follows: XXX-YYYYYY-ZZZ (X = letters, Y = numbers, Z = alphanumeric) ; Personal/Individual RFC #: 13 characters, with a format as follows: XXXX-YYYYYY-ZZZ (X = letters, Y = numbers, Z = alphanumeric)                                                                                                                              |
| Moldova              | IDNO; VAT            | 13 numeric digits; 7 numeric digits with the optional prefix of MD                                                                                                                                                                                                                                                                                                                   |
| Norway               | ORGNR; MVA           | 9 numeric digits; 9 numeric digits followed by the letters MVA, may have an additional optional prefix of NO                                                                                                                                                                                                                                                                         |
| Serbia               | PIB                  | 9 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| South Africa         | TRN                  | 10 numeric digits where the first digit is 0,1,2,3, 4, or 9                                                                                                                                                                                                                                                                                                                          |
| South Korea          | BRN                  | 10 digit code where the first 3 digits are between 101-999, the second 2 digits are 01-89 excluding 80, followed by 4 numeric digits greater than "0000", ending in any numeric digit                                                                                                                                                                                                |
| Switzerland          | UID; VAT             | 12 characters in length where the format should follow the pattern: CHE-NNN.NNN.NNN, where there are 9 numeric digits following a prefix of "CHE"; 15-16 characters in length where the format should follow the pattern: CHE-NNN.NNN.NNN AAA, where there are 9 numeric digits, with a prefix of CHE, and a suffix of either MWST, TVA, IVA, or VAT                                 |
| Taiwan               | BAN                  | 8 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| Thailand             | TIN                  | 13 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Togo                 | NIF                  | 10 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Turkey               | VKN                  | 10 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| Untied Arab Emirates | TRN                  | 15 numeric digits                                                                                                                                                                                                                                                                                                                                                                    |
| United States        | EIN                  | 9 numeric digits in the format NN-NNNNNNN                                                                                                                                                                                                                                                                                                                                            |
| Ukraine              | EDRPOU               | 8 numeric digits                                                                                                                                                                                                                                                                                                                                                                     |
| Vietnam              | MST                  | 10-13 numeric digits where the 3rd through 10th digits cannot be "0000000" and the last 3 digits cannot be "000"                                                                                                                                                                                                                                                                     |