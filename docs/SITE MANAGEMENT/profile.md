---
title: Profile
excerpt: >-
  Streamline your security and contact settings effortlessly in a user-friendly
  interface.
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

This interface facilitates the management of your security and contact settings. It allows for the modification of your full name, email, job function, and time zone associated with the account. Additionally, you have the option to change your password, enable or disable 2FA (Two-factor authentication), and configure your preferred 2FA authentication method.

# Key benefits

* **Personalized Account Management**: Easily modify essential details like your full name, email, job function, and time zone to keep your account up-to-date.
* **Robust Security Features**: Enhance account security through intuitive password management features and Two-factor Authentication (2FA) options.
* **Reliable Support Access**: Swiftly regain account access with dedicated support, ensuring a seamless user experience and continuous security.

# Access

To manage your personal information and security settings, click on your name in the right-upper section of the Recurly app.

<Image align="center" border={true} src="https://files.readme.io/603dfb8111eb04f99eaae81f470d820208532d8cf8c9ae9c4c9fe0c3d4bcc840-Screenshot_2026-04-08_at_8.48.26_AM.png" className="border" />

# Personal information settings

This section displays your personal information. At any time, you may update your full name, email, job function, and time zone. Simply **click** on “Edit Personal Info”, and you will be prompted to enter the necessary changes.

<br />

# Account security settings

## Password management

Here, you can manage your login credentials and familiarize yourself with the security protocols designed to safeguard your account.

To modify your password, click the “Change Password” button and provide the required details.  Passwords must be at least 12 characters long and must include at least one numeric character.  The system will force a password change during login if the password is older than 90 days.

## Two-factor authentication

> **Deprecation notice**
>
> SMS 2FA is disabled for users on new sandbox sites. Current users using an Authenticator App for 2FA will need to upgrade to Recurly’s new TOTP service by March 5th, 2025.
>
> **Please** follow the instructions on how to upgrade to the new TOTP service [here](https://docs.recurly.com/docs/profile#upgrading-authenticator-app-to-new-totp-service).

Two-Factor Authentication (2FA) is a feature provided by Recurly that adds an extra layer of security to your account by requiring users to provide two pieces of information for authentication - the user password and a verification code.

#### Limitations

* While 2FA provides a strong additional layer of security to protect your Recurly account, it’s important to note:  
  2FA does not replace the need for strong, unique passwords and secure account practices.
* Users are responsible for maintaining access to their chosen method of receiving verification codes (Authenticator app, Text Message, Email).
* If a user loses access to their chosen method(s) of verification, they may be unable to access their account until they can receive verification codes again.
* As 2FA applies universally across all Recurly sites accessed with the same email, disabling 2FA will remove this layer of security from all connected sites.

### Enabling two-factor authentication

1. **Navigate** to your user profile in your Recurly account.
2. **Click** the Enable link that corresponds to the 2FA method to be enabled (Authenticator app, Text message, Email). Multiple 2FA methods can be configured for your account.

<Image align="center" border={true} src="https://files.readme.io/f61d06dd20926dce6b575d10ef55673f41dca07489497fa36921ea4c06dbf865-Screenshot_2026-04-08_at_9.00.33_AM.png" className="border" />

1. **Enter** your password for verification.
2. For the first 2FA configuration, ‘Set as default’ is selected automatically. For additional 2FA methods, selecting ‘Set as default’ will change the default 2FA method upon successful configuration. This selection just sets with 2FA method, when multiple are configured, is selected by default when a 2FA token is required to be entered during login.

#### Authenticator App verification

Recurly supports various authenticator apps such as Twilio Authy, Okta Verify, Google Authenticator, Microsoft Authenticator, LastPass Authenticator, and more.

<Image align="center" border={true} width="50% " src="https://files.readme.io/ef006ee81e9ad3112d8ba94826bbd9883a3ee369f6574f6169d2895926fd619e-image.png" className="border" />

You will be presented with a QR code to scan using your chosen authenticator app. Alternatively, you can enter a provided human-readable code manually into the app.

The app will generate a code that you will enter into Recurly to enable two-factor authentication.

#### SMS Verification

1. **Enter** a mobile phone number cable of receiving SMS text messages.
2. A Text message with a verification code will be sent to the entered phone number.
3. **Input** the received code into the verification field.

#### Email Verification

An Email message with a verification code will be sent to the email address for your Recurly account.  
Input the received code into the verification field.

### Changing Default Two-Factor Authentication method

1. **Click** the ellipses to the right of the 2FA method you want to set as default.
2. **Select** Set as Default.
3. **Enter** your password.
4. **Click** Set as Default.

### Disabling Two-Factor Authentication

#### Disable Individual Two-Factor Authentication for Your User Account

2FA methods can be individually disabled by the user. To disable a specific 2FA method:

1. **Click** on the ellipses to the right of the 2FA method and select **Disable**.
2. **Enter** your password.
3. **Click** on**Disable**.

#### Disable All Two-Factor Authentication for Your User Account

You can disable all enabled 2FA methods for your account at once:

1. **Click** on **Disable Two-Factor Auth**.
2. **Enter** your password.
3. **Click** on **Disable**.

All enabled 2FA methods on your account will now be disabled.

#### Disable Two-Factor Authentication for a User Account (by Site Admin Users)

A Site Admin can disable 2FA for individual user accounts:

1. **Go** to the **Users** section in Recurly.
2. **Click** to edit the profile of the user who needs Two-Factor Authentication disabled.
3. **Select** **Password** and **click** **Save Changes**.

### Setting up multiple Two-Factor Authentication configurations

We advocate the activation of 2FA to enhance the security of your account. Recurly supports configuring multiple 2FA configurations per account:

* Authenticator App
* SMS
* Email

Setting up multiple 2FA configurations provides a choice of 2FA method to use during login. Due to known weaknesses with SMS security, the Authenticator App and/or Email 2FA configurations are recommended.

**Click** Enable next to the 2FA configuration you want to set up and follow the instructions on the configuration modals to set up the requested 2FA method.

### Troubleshooting

#### Lost mobile device

If you can’t access the mobile device that receives your authentication codes, consider these steps:

1. **Consider** enabling multiple 2FA methods on your account when first setting up 2FA, such as both Authenticator app and Email. This will allow you to still login to your account by receiving a token via Email, and then you can disable the Authenticator app and reconfigure the 2FA Authenticator app method for a new device.
2. Many authenticator apps provide account restoration options or use alternative devices to receive codes. **Check** your app’s documentation for details.
3. **Reach out** to your Recurly site administrator. Admin users can disable Two-Factor Authentication on your profile, allowing you to log in using only your password.
4. **Contact** Recurly Support. They can disable Two-Factor Authentication on your profile allowing login with just your password.

#### General tips

* If authentication fails multiple times, try synchronizing your phone’s clock with your mobile provider.
* If you’re not receiving authentication codes via Text message, double-check that your phone number has been entered correctly.
* If your code isn’t working, make sure not to enter spaces between the numbers in the code.

### Upgrading Authenticator App to new TOTP service

Please follow the steps below to upgrade your Authenticator App to the new TOTP service.

1. **Log** into Recurly and navigate to your profile.
2. **Click** on the ellipses to the right side of the Authenticator App in the Two-Factor Authentication configuration section to access the drop down menu and select Disable.
3. **Follow** the prompts to disable the 2FA Authenticator App configuration.
4. **Open** your Authenticator App on your mobile phone and delete the configured Recurly account.
5. **Follow** the directions above to enable 2FA for your Authenticator app.

> 🚧 Session timeout
>
> The session inactivity timeout is preset to **20 minutes**, after which you would need to log in again to continue.
