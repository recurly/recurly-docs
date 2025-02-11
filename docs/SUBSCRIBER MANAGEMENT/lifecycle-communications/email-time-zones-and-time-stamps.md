---
title: Email timezones and timestamps
excerpt: >-
  Harness the power of Recurly's dynamic email time zone feature. Tailor your
  customer emails according to their specific time zones for enhanced clarity
  and communication.
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

This feature or setting is available to all customers on any Recurly subscription plan.

# Definition

Recurly's email time zone feature is designed to help businesses cater to the diverse timezone preferences of their global clientele. With this, businesses can set a default timezone for their emails or assign specific time zones to individual customer accounts, ensuring each email's timestamp accurately reflects the recipient's local time.

# Key benefits

- **Personalization:** Tailor email delivery times to the local timezones of your global customer base.  
- **Clarity:** Eliminate timezone-related confusions by ensuring the timestamps in your emails accurately mirror the recipient's local time.  
- **Flexibility:** Choose a default email timezone or customize it for individual customer accounts.  
- **API integration:** Easily configure account-specific email timezones through the API for seamless system integrations.

# Key details

## Setting time zones for emails

The challenge of catering to a global clientele often comes down to managing time zones. With Recurly's email time zone feature, you can not only set a default email timezone for all your emails but also customize it for specific customer accounts, ensuring precision and clarity in every communication.

> **Note**: While this feature adjusts the time zone displayed in the email content, it does not change the actual send time of the email.

### Example

Consider Merchant 123 Inc., based in New York, with a client, Alex Smith, located in London. With the customized time zone feature, Alex's subscription-related emails will reflect London's local time, providing clarity and preventing any timestamp-related confusion.

By effectively leveraging the email timezone feature, you can ensure precise and timely communication with your clients across the globe, optimizing the customer experience.

# Configure time zones and timestamps for emails via Recurly

**Site-Level Email Timezone Configuration:**

1. Go to the “Site Settings” page.
2. Navigate to the “Email Settings” section.
3. At the bottom of this section, you'll find an option to set the timezone/timestamp for Emails. The default option is set to UTC.
4. Use the dropdown menu to select your preferred time zone. This will be applied to all emails sent to all customers site-wide.
5. If desired, you can also set a specific email time zone for individual customers at the “Account” level. If a unique email timezone is selected for a specific account, that will take precedence over the site-wide setting.

![Site Settings Screenshot](https://files.readme.io/838b688-Screen_Shot_2022-06-21_at_12.58.48_PM.png)

**Account-level email timezone configuration:**

1. Navigate to the desired customer account page.
2. Choose the appropriate time zone from the dropdown menu.
3. If you wish to utilize the site-wide setting, simply select the "Site Settings (Default)" option and save the changes.

![Account Settings Screenshot](https://files.readme.io/b3705f0-Screen_Shot_2022-06-21_at_2.33.52_PM.png)

### Additional email parameters

Integrate the following parameters into your email templates via the Recurly App's Email Templates page:

- `transaction_date_and_time`: Reflects the transaction date and time adjusted for timezone.
- `transaction_declined?`: Indicates if the transaction was declined.
- `transaction_success?`: Indicates if the transaction was successful.
- `transaction_voided?`: Indicates if the transaction was voided.
- `subscription_expires_at_with_time`: Shows the adjusted date and time when a canceled subscription will expire.
- `subscription_trial_ends_at_with_time`: Denotes the adjusted end date and time for the current subscription trial.

# Setting account-specific email time zones via API

Ensure seamless integration with your existing systems by configuring account-specific email timezones through the Recurly API.

### Supported API IANA Time Zone Names

For `preferred_time_zone` in the Account API, refer to the following IANA time zone values:

[block:parameters]
{
  "data": {
    "h-0": "Admin UI Option",
    "h-1": "API IANA Value",
    "0-0": "(GMT-12:00) International Date Line West  \n(GMT-11:00) American Samoa  \n(GMT-11:00) Midway Island  \n(GMT-10:00) Hawaii  \n(GMT-09:00) Alaska  \n(GMT-08:00) Pacific Time (US & Canada)  \n(GMT-08:00) Tijuana  \n(GMT-07:00) Arizona  \n(GMT-07:00) Mazatlan  \n(GMT-07:00) Mountain Time (US & Canada)  \n(GMT-06:00) Central America  \n(GMT-06:00) Central Time (US & Canada)  \n(GMT-06:00) Chihuahua  \n(GMT-06:00) Guadalajara  \n(GMT-06:00) Mexico City  \n(GMT-06:00) Monterrey  \n(GMT-06:00) Saskatchewan  \n(GMT-05:00) Bogota  \n(GMT-05:00) Eastern Time (US & Canada)  \n(GMT-05:00) Indiana (East)  \n(GMT-05:00) Lima  \n(GMT-05:00) Quito  \n(GMT-04:00) Atlantic Time (Canada)  \n(GMT-04:00) Caracas  \n(GMT-04:00) Georgetown  \n(GMT-04:00) La Paz  \n(GMT-04:00) Puerto Rico  \n(GMT-04:00) Santiago  \n(GMT-03:30) Newfoundland  \n(GMT-03:00) Brasilia  \n(GMT-03:00) Buenos Aires  \n(GMT-03:00) Greenland  \n(GMT-03:00) Montevideo  \n(GMT-02:00) Mid-Atlantic  \n(GMT-01:00) Azores  \n(GMT-01:00) Cape Verde Is.  \n(GMT+00:00) Casablanca  \n(GMT+00:00) Dublin  \n(GMT+00:00) Edinburgh  \n(GMT+00:00) Lisbon  \n(GMT+00:00) London  \n(GMT+00:00) Monrovia  \n(GMT+00:00) UTC  \n(GMT+01:00) Amsterdam  \n(GMT+01:00) Belgrade  \n(GMT+01:00) Berlin  \n(GMT+01:00) Bern  \n(GMT+01:00) Bratislava  \n(GMT+01:00) Brussels  \n(GMT+01:00) Budapest  \n(GMT+01:00) Copenhagen  \n(GMT+01:00) Ljubljana  \n(GMT+01:00) Madrid  \n(GMT+01:00) Paris  \n(GMT+01:00) Prague  \n(GMT+01:00) Rome  \n(GMT+01:00) Sarajevo  \n(GMT+01:00) Skopje  \n(GMT+01:00) Stockholm  \n(GMT+01:00) Vienna  \n(GMT+01:00) Warsaw  \n(GMT+01:00) West Central Africa  \n(GMT+01:00) Zagreb  \n(GMT+01:00) Zurich  \n(GMT+02:00) Athens  \n(GMT+02:00) Bucharest  \n(GMT+02:00) Cairo  \n(GMT+02:00) Harare  \n(GMT+02:00) Helsinki  \n(GMT+02:00) Jerusalem  \n(GMT+02:00) Kaliningrad  \n(GMT+02:00) Kyiv  \n(GMT+02:00) Pretoria  \n(GMT+02:00) Riga  \n(GMT+02:00) Sofia  \n(GMT+02:00) Tallinn  \n(GMT+02:00) Vilnius  \n(GMT+03:00) Baghdad  \n(GMT+03:00) Istanbul  \n(GMT+03:00) Kuwait  \n(GMT+03:00) Minsk  \n(GMT+03:00) Moscow  \n(GMT+03:00) Nairobi  \n(GMT+03:00) Riyadh  \n(GMT+03:00) St. Petersburg  \n(GMT+03:00) Volgograd  \n(GMT+03:30) Tehran  \n(GMT+04:00) Abu Dhabi  \n(GMT+04:00) Baku  \n(GMT+04:00) Muscat  \n(GMT+04:00) Samara  \n(GMT+04:00) Tbilisi  \n(GMT+04:00) Yerevan  \n(GMT+04:30) Kabul  \n(GMT+05:00) Ekaterinburg  \n(GMT+05:00) Islamabad  \n(GMT+05:00) Karachi  \n(GMT+05:00) Tashkent  \n(GMT+05:30) Chennai  \n(GMT+05:30) Kolkata  \n(GMT+05:30) Mumbai  \n(GMT+05:30) New Delhi  \n(GMT+05:30) Sri Jayawardenepura  \n(GMT+05:45) Kathmandu  \n(GMT+06:00) Almaty  \n(GMT+06:00) Astana  \n(GMT+06:00) Dhaka  \n(GMT+06:00) Urumqi  \n(GMT+06:30) Rangoon  \n(GMT+07:00) Bangkok  \n(GMT+07:00) Hanoi  \n(GMT+07:00) Jakarta  \n(GMT+07:00) Krasnoyarsk  \n(GMT+07:00) Novosibirsk  \n(GMT+08:00) Beijing  \n(GMT+08:00) Chongqing  \n(GMT+08:00) Hong Kong  \n(GMT+08:00) Irkutsk  \n(GMT+08:00) Kuala Lumpur  \n(GMT+08:00) Perth  \n(GMT+08:00) Singapore  \n(GMT+08:00) Taipei  \n(GMT+08:00) Ulaanbaatar  \n(GMT+09:00) Osaka  \n(GMT+09:00) Sapporo  \n(GMT+09:00) Seoul  \n(GMT+09:00) Tokyo  \n(GMT+09:00) Yakutsk  \n(GMT+09:30) Adelaide  \n(GMT+09:30) Darwin  \n(GMT+10:00) Brisbane  \n(GMT+10:00) Canberra  \n(GMT+10:00) Guam  \n(GMT+10:00) Hobart  \n(GMT+10:00) Melbourne  \n(GMT+10:00) Port Moresby  \n(GMT+10:00) Sydney  \n(GMT+10:00) Vladivostok  \n(GMT+11:00) Magadan  \n(GMT+11:00) New Caledonia  \n(GMT+11:00) Solomon Is.  \n(GMT+11:00) Srednekolymsk  \n(GMT+12:00) Auckland  \n(GMT+12:00) Fiji  \n(GMT+12:00) Kamchatka  \n(GMT+12:00) Marshall Is.  \n(GMT+12:00) Wellington  \n(GMT+12:45) Chatham Is.  \n(GMT+13:00) Nuku'alofa  \n(GMT+13:00) Samoa  \n(GMT+13:00) Tokelau Is.",
    "0-1": "Etc/GMT+12  \nPacific/Pago_Pago  \nPacific/Midway  \nPacific/Honolulu  \nAmerica/Juneau  \nAmerica/Los_Angeles  \nAmerica/Tijuana  \nAmerica/Phoenix  \nAmerica/Mazatlan  \nAmerica/Denver  \nAmerica/Guatemala  \nAmerica/Chicago  \nAmerica/Chihuahua  \nAmerica/Mexico_City  \nAmerica/Mexico_City  \nAmerica/Monterrey  \nAmerica/Regina  \nAmerica/Bogota  \nAmerica/New_York  \nAmerica/Indiana/Indianapolis  \nAmerica/Lima  \nAmerica/Lima  \nAmerica/Halifax  \nAmerica/Caracas  \nAmerica/Guyana  \nAmerica/La_Paz  \nAmerica/Puerto_Rico  \nAmerica/Santiago  \nAmerica/St_Johns  \nAmerica/Sao_Paulo  \nAmerica/Argentina/Buenos_Aires  \nAmerica/Godthab  \nAmerica/Montevideo  \nAtlantic/South_Georgia  \nAtlantic/Azores  \nAtlantic/Cape_Verde  \nAfrica/Casablanca  \nEurope/Dublin  \nEurope/London  \nEurope/Lisbon  \nEurope/London  \nAfrica/Monrovia  \nEtc/UTC  \nEurope/Amsterdam  \nEurope/Belgrade  \nEurope/Berlin  \nEurope/Zurich  \nEurope/Bratislava  \nEurope/Brussels  \nEurope/Budapest  \nEurope/Copenhagen  \nEurope/Ljubljana  \nEurope/Madrid  \nEurope/Paris  \nEurope/Prague  \nEurope/Rome  \nEurope/Sarajevo  \nEurope/Skopje  \nEurope/Stockholm  \nEurope/Vienna  \nEurope/Warsaw  \nAfrica/Algiers  \nEurope/Zagreb  \nEurope/Zurich  \nEurope/Athens  \nEurope/Bucharest  \nAfrica/Cairo  \nAfrica/Harare  \nEurope/Helsinki  \nAsia/Jerusalem  \nEurope/Kaliningrad  \nEurope/Kiev  \nAfrica/Johannesburg  \nEurope/Riga  \nEurope/Sofia  \nEurope/Tallinn  \nEurope/Vilnius  \nAsia/Baghdad  \nEurope/Istanbul  \nAsia/Kuwait  \nEurope/Minsk  \nEurope/Moscow  \nAfrica/Nairobi  \nAsia/Riyadh  \nEurope/Moscow  \nEurope/Volgograd  \nAsia/Tehran  \nAsia/Muscat  \nAsia/Baku  \nAsia/Muscat  \nEurope/Samara  \nAsia/Tbilisi  \nAsia/Yerevan  \nAsia/Kabul  \nAsia/Yekaterinburg  \nAsia/Karachi  \nAsia/Karachi  \nAsia/Tashkent  \nAsia/Kolkata  \nAsia/Kolkata  \nAsia/Kolkata  \nAsia/Kolkata  \nAsia/Colombo  \nAsia/Kathmandu  \nAsia/Almaty  \nAsia/Dhaka  \nAsia/Dhaka  \nAsia/Urumqi  \nAsia/Rangoon  \nAsia/Bangkok  \nAsia/Bangkok  \nAsia/Jakarta  \nAsia/Krasnoyarsk  \nAsia/Novosibirsk  \nAsia/Shanghai  \nAsia/Chongqing  \nAsia/Hong_Kong  \nAsia/Irkutsk  \nAsia/Kuala_Lumpur  \nAustralia/Perth  \nAsia/Singapore  \nAsia/Taipei  \nAsia/Ulaanbaatar  \nAsia/Tokyo  \nAsia/Tokyo  \nAsia/Seoul  \nAsia/Tokyo  \nAsia/Yakutsk  \nAustralia/Adelaide  \nAustralia/Darwin  \nAustralia/Brisbane  \nAustralia/Melbourne  \nPacific/Guam  \nAustralia/Hobart  \nAustralia/Melbourne  \nPacific/Port_Moresby  \nAustralia/Sydney  \nAsia/Vladivostok  \nAsia/Magadan  \nPacific/Noumea  \nPacific/Guadalcanal  \nAsia/Srednekolymsk  \nPacific/Auckland  \nPacific/Fiji  \nAsia/Kamchatka  \nPacific/Majuro  \nPacific/Auckland  \nPacific/Chatham  \nPacific/Tongatapu  \nPacific/Apia  \nPacific/Fakaofo"
  },
  "cols": 2,
  "rows": 1,
  "align": [
    "left",
    "left"
  ]
}
[/block]