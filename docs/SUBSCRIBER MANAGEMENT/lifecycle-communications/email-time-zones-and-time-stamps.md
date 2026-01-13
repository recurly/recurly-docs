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

* **Personalization:** Tailor email delivery times to the local timezones of your global customer base.
* **Clarity:** Eliminate timezone-related confusions by ensuring the timestamps in your emails accurately mirror the recipient's local time.
* **Flexibility:** Choose a default email timezone or customize it for individual customer accounts.
* **API integration:** Easily configure account-specific email timezones through the API for seamless system integrations.

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

<Image alt="Site Settings Screenshot" border={false} src="https://files.readme.io/838b688-Screen_Shot_2022-06-21_at_12.58.48_PM.png" />

**Account-level email timezone configuration:**

1. Navigate to the desired customer account page.
2. Choose the appropriate time zone from the dropdown menu.
3. If you wish to utilize the site-wide setting, simply select the "Site Settings (Default)" option and save the changes.

<Image alt="Account Settings Screenshot" border={false} src="https://files.readme.io/b3705f0-Screen_Shot_2022-06-21_at_2.33.52_PM.png" />

### Additional email parameters

Integrate the following parameters into your email templates via the Recurly App's Email Templates page:

| Parameter                                       | What it does                                                                |
| ----------------------------------------------- | --------------------------------------------------------------------------- |
| `subscription_current_period_ends_at_with_time` | Shows the adjusted date and time when the current subscription period ends. |
| `transaction_date_and_time`                     | Reflects the transaction date and time adjusted for timezone.               |
| `transaction_declined?`                         | Indicates if the transaction was declined.                                  |
| `transaction_success?`                          | Indicates if the transaction was successful.                                |
| `transaction_voided?`                           | Indicates if the transaction was voided.                                    |
| `subscription_expires_at_with_time`             | Shows the adjusted date and time when a canceled subscription will expire.  |
| `subscription_trial_ends_at_with_time`          | Denotes the adjusted end date and time for the current subscription trial.  |

# Setting account-specific email time zones via API

Ensure seamless integration with your existing systems by configuring account-specific email timezones through the Recurly API.

### Supported API IANA Time Zone Names

For `preferred_time_zone` in the Account API, refer to the following IANA time zone values:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Admin UI Option
      </th>

      <th>
        API IANA Value
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        (GMT-12:00) International Date Line West
        (GMT-11:00) American Samoa
        (GMT-11:00) Midway Island
        (GMT-10:00) Hawaii
        (GMT-09:00) Alaska
        (GMT-08:00) Pacific Time (US & Canada)
        (GMT-08:00) Tijuana
        (GMT-07:00) Arizona
        (GMT-07:00) Mazatlan
        (GMT-07:00) Mountain Time (US & Canada)
        (GMT-06:00) Central America
        (GMT-06:00) Central Time (US & Canada)
        (GMT-06:00) Chihuahua
        (GMT-06:00) Guadalajara
        (GMT-06:00) Mexico City
        (GMT-06:00) Monterrey
        (GMT-06:00) Saskatchewan
        (GMT-05:00) Bogota
        (GMT-05:00) Eastern Time (US & Canada)
        (GMT-05:00) Indiana (East)
        (GMT-05:00) Lima
        (GMT-05:00) Quito
        (GMT-04:00) Atlantic Time (Canada)
        (GMT-04:00) Caracas
        (GMT-04:00) Georgetown
        (GMT-04:00) La Paz
        (GMT-04:00) Puerto Rico
        (GMT-04:00) Santiago
        (GMT-03:30) Newfoundland
        (GMT-03:00) Brasilia
        (GMT-03:00) Buenos Aires
        (GMT-03:00) Greenland
        (GMT-03:00) Montevideo
        (GMT-02:00) Mid-Atlantic
        (GMT-01:00) Azores
        (GMT-01:00) Cape Verde Is.
        (GMT+00:00) Casablanca
        (GMT+00:00) Dublin
        (GMT+00:00) Edinburgh
        (GMT+00:00) Lisbon
        (GMT+00:00) London
        (GMT+00:00) Monrovia
        (GMT+00:00) UTC
        (GMT+01:00) Amsterdam
        (GMT+01:00) Belgrade
        (GMT+01:00) Berlin
        (GMT+01:00) Bern
        (GMT+01:00) Bratislava
        (GMT+01:00) Brussels
        (GMT+01:00) Budapest
        (GMT+01:00) Copenhagen
        (GMT+01:00) Ljubljana
        (GMT+01:00) Madrid
        (GMT+01:00) Paris
        (GMT+01:00) Prague
        (GMT+01:00) Rome
        (GMT+01:00) Sarajevo
        (GMT+01:00) Skopje
        (GMT+01:00) Stockholm
        (GMT+01:00) Vienna
        (GMT+01:00) Warsaw
        (GMT+01:00) West Central Africa
        (GMT+01:00) Zagreb
        (GMT+01:00) Zurich
        (GMT+02:00) Athens
        (GMT+02:00) Bucharest
        (GMT+02:00) Cairo
        (GMT+02:00) Harare
        (GMT+02:00) Helsinki
        (GMT+02:00) Jerusalem
        (GMT+02:00) Kaliningrad
        (GMT+02:00) Kyiv
        (GMT+02:00) Pretoria
        (GMT+02:00) Riga
        (GMT+02:00) Sofia
        (GMT+02:00) Tallinn
        (GMT+02:00) Vilnius
        (GMT+03:00) Baghdad
        (GMT+03:00) Istanbul
        (GMT+03:00) Kuwait
        (GMT+03:00) Minsk
        (GMT+03:00) Moscow
        (GMT+03:00) Nairobi
        (GMT+03:00) Riyadh
        (GMT+03:00) St. Petersburg
        (GMT+03:00) Volgograd
        (GMT+03:30) Tehran
        (GMT+04:00) Abu Dhabi
        (GMT+04:00) Baku
        (GMT+04:00) Muscat
        (GMT+04:00) Samara
        (GMT+04:00) Tbilisi
        (GMT+04:00) Yerevan
        (GMT+04:30) Kabul
        (GMT+05:00) Ekaterinburg
        (GMT+05:00) Islamabad
        (GMT+05:00) Karachi
        (GMT+05:00) Tashkent
        (GMT+05:30) Chennai
        (GMT+05:30) Kolkata
        (GMT+05:30) Mumbai
        (GMT+05:30) New Delhi
        (GMT+05:30) Sri Jayawardenepura
        (GMT+05:45) Kathmandu
        (GMT+06:00) Almaty
        (GMT+06:00) Astana
        (GMT+06:00) Dhaka
        (GMT+06:00) Urumqi
        (GMT+06:30) Rangoon
        (GMT+07:00) Bangkok
        (GMT+07:00) Hanoi
        (GMT+07:00) Jakarta
        (GMT+07:00) Krasnoyarsk
        (GMT+07:00) Novosibirsk
        (GMT+08:00) Beijing
        (GMT+08:00) Chongqing
        (GMT+08:00) Hong Kong
        (GMT+08:00) Irkutsk
        (GMT+08:00) Kuala Lumpur
        (GMT+08:00) Perth
        (GMT+08:00) Singapore
        (GMT+08:00) Taipei
        (GMT+08:00) Ulaanbaatar
        (GMT+09:00) Osaka
        (GMT+09:00) Sapporo
        (GMT+09:00) Seoul
        (GMT+09:00) Tokyo
        (GMT+09:00) Yakutsk
        (GMT+09:30) Adelaide
        (GMT+09:30) Darwin
        (GMT+10:00) Brisbane
        (GMT+10:00) Canberra
        (GMT+10:00) Guam
        (GMT+10:00) Hobart
        (GMT+10:00) Melbourne
        (GMT+10:00) Port Moresby
        (GMT+10:00) Sydney
        (GMT+10:00) Vladivostok
        (GMT+11:00) Magadan
        (GMT+11:00) New Caledonia
        (GMT+11:00) Solomon Is.
        (GMT+11:00) Srednekolymsk
        (GMT+12:00) Auckland
        (GMT+12:00) Fiji
        (GMT+12:00) Kamchatka
        (GMT+12:00) Marshall Is.
        (GMT+12:00) Wellington
        (GMT+12:45) Chatham Is.
        (GMT+13:00) Nuku'alofa
        (GMT+13:00) Samoa
        (GMT+13:00) Tokelau Is.
      </td>

      <td>
        Etc/GMT+12  
        Pacific/Pago_Pago  
        Pacific/Midway  
        Pacific/Honolulu  
        America/Juneau  
        America/Los_Angeles  
        America/Tijuana  
        America/Phoenix  
        America/Mazatlan  
        America/Denver  
        America/Guatemala  
        America/Chicago  
        America/Chihuahua  
        America/Mexico_City  
        America/Mexico_City  
        America/Monterrey  
        America/Regina  
        America/Bogota  
        America/New_York  
        America/Indiana/Indianapolis  
        America/Lima  
        America/Lima  
        America/Halifax  
        America/Caracas  
        America/Guyana  
        America/La_Paz  
        America/Puerto_Rico  
        America/Santiago  
        America/St_Johns  
        America/Sao_Paulo  
        America/Argentina/Buenos_Aires  
        America/Godthab  
        America/Montevideo  
        Atlantic/South_Georgia  
        Atlantic/Azores  
        Atlantic/Cape_Verde  
        Africa/Casablanca  
        Europe/Dublin  
        Europe/London  
        Europe/Lisbon  
        Europe/London  
        Africa/Monrovia  
        Etc/UTC  
        Europe/Amsterdam  
        Europe/Belgrade  
        Europe/Berlin  
        Europe/Zurich  
        Europe/Bratislava  
        Europe/Brussels  
        Europe/Budapest  
        Europe/Copenhagen  
        Europe/Ljubljana  
        Europe/Madrid  
        Europe/Paris  
        Europe/Prague  
        Europe/Rome  
        Europe/Sarajevo  
        Europe/Skopje  
        Europe/Stockholm  
        Europe/Vienna  
        Europe/Warsaw  
        Africa/Algiers  
        Europe/Zagreb  
        Europe/Zurich  
        Europe/Athens  
        Europe/Bucharest  
        Africa/Cairo  
        Africa/Harare  
        Europe/Helsinki  
        Asia/Jerusalem  
        Europe/Kaliningrad  
        Europe/Kiev  
        Africa/Johannesburg  
        Europe/Riga  
        Europe/Sofia  
        Europe/Tallinn  
        Europe/Vilnius  
        Asia/Baghdad  
        Europe/Istanbul  
        Asia/Kuwait  
        Europe/Minsk  
        Europe/Moscow  
        Africa/Nairobi  
        Asia/Riyadh  
        Europe/Moscow  
        Europe/Volgograd  
        Asia/Tehran  
        Asia/Muscat  
        Asia/Baku  
        Asia/Muscat  
        Europe/Samara  
        Asia/Tbilisi  
        Asia/Yerevan  
        Asia/Kabul  
        Asia/Yekaterinburg  
        Asia/Karachi  
        Asia/Karachi  
        Asia/Tashkent  
        Asia/Kolkata  
        Asia/Kolkata  
        Asia/Kolkata  
        Asia/Kolkata  
        Asia/Colombo  
        Asia/Kathmandu  
        Asia/Almaty  
        Asia/Dhaka  
        Asia/Dhaka  
        Asia/Urumqi  
        Asia/Rangoon  
        Asia/Bangkok  
        Asia/Bangkok  
        Asia/Jakarta  
        Asia/Krasnoyarsk  
        Asia/Novosibirsk  
        Asia/Shanghai  
        Asia/Chongqing  
        Asia/Hong_Kong  
        Asia/Irkutsk  
        Asia/Kuala_Lumpur  
        Australia/Perth  
        Asia/Singapore  
        Asia/Taipei  
        Asia/Ulaanbaatar  
        Asia/Tokyo  
        Asia/Tokyo  
        Asia/Seoul  
        Asia/Tokyo  
        Asia/Yakutsk  
        Australia/Adelaide  
        Australia/Darwin  
        Australia/Brisbane  
        Australia/Melbourne  
        Pacific/Guam  
        Australia/Hobart  
        Australia/Melbourne  
        Pacific/Port_Moresby  
        Australia/Sydney  
        Asia/Vladivostok  
        Asia/Magadan  
        Pacific/Noumea  
        Pacific/Guadalcanal  
        Asia/Srednekolymsk  
        Pacific/Auckland  
        Pacific/Fiji  
        Asia/Kamchatka  
        Pacific/Majuro  
        Pacific/Auckland  
        Pacific/Chatham  
        Pacific/Tongatapu  
        Pacific/Apia  
        Pacific/Fakaofo
      </td>
    </tr>
  </tbody>
</Table>
