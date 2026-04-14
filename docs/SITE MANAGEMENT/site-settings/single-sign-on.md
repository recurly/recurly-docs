---
title: Single sign-on
excerpt: >-
  Single Sign-On (SSO) is a user authentication service that allows a user to
  use one set of login credentials to access multiple applications. This feature
  increases security and efficiency by reducing the need for multiple passwords
  and streamlining access management.
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

This feature **may not be included** in the Starter or Pro plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

### Limitations

While SSO offers a streamlined login process and enhanced security, it’s important to be aware of certain limitations associated with this feature:

* **User Provisioning**: Traditionally, Recurly required manual user setup for SSO, meaning new users had to be added manually in Recurly before they could authenticate via your SSO Identity Provider. This limitation remains for providers such as **Microsoft Entra** and **Google**. **However, if you use Okta, user provisioning can be automated.** For details on how Okta works with Recurly, please see our [Spring 2024 Product Launch Summary](https://recurly.com/blog/spring-2024-product-launch-summary/).
* **Supported Identity Providers:** Currently, Recurly’s SSO feature is available through Okta, Microsoft Entra, and Google. If you wish to use SSO with a different identity provider, please contact Recurly Support to discuss the possibilities.
* If you are interested about SCIM for Okta, please reach out to your Recurly account manager or [support@recurly.com](mailto:support@recurly.com) for more details.

# Definition

Single Sign-On (SSO) is a user authentication service that allows a user to use one set of login credentials to access multiple applications. This feature increases security and efficiency by reducing the need for multiple passwords and streamlining access management.

SSO simplifies the login process by enabling users to access multiple systems with a single set of credentials. It enhances security and efficiency, making it easier for teams to manage access to Recurly data.

# Key benefits

* **Enhanced security:** Minimize the risk of password-related security breaches by reducing the number of passwords used, bolstering overall system security.
* **Streamlined access management:** Simplify access management with a single set of credentials for multiple applications, facilitating a smoother user experience.
* **Diverse identity provider support:** Utilize Recurly's Single Sign-On (SSO) feature which supports prominent identity providers like Okta, Microsoft Entra, and Google, offering flexibility in aligning with your existing infrastructure.

# Key details

## Key principles and assumptions

* **One-to-one relationship:** For the SSO to work as intended, each Recurly user's account must have a corresponding identity provider account. For instance, if a user has an account [sample@recurly.com](mailto:sample@recurly.com) , they can't use both Okta and Microsoft Entra for their SSO. If employees need to use more than one SSO identity provider to access different Recurly sites, they must have separate Recurly accounts for each identity provider.
* **User ID matching:** The user ID in Recurly, which is typically an email address, must match the user ID in the identity provider. This means that the email address associated with a user in Okta, Entra, or Google must be identical to the email address registered for the Recurly user. If the two email addresses don't match, the Recurly user email must be updated to match the one in the identity provider before enabling SSO for the user.
* **Site-level configuration:** SSO is configured at the site level in Recurly. If a user is associated with multiple sites and each site requires the user to use SSO, the first site that requires SSO will dictate which SSO configurations are used. The identity provider/SSO chosen by this site will be the one the user must use.
* **SSO and access control:** While SSO handles authentication for the Recurly app, it does not govern which sites the user can access once they've logged in. For instance, if a user is associated with multiple sites in Recurly and is using SSO, they will have access to all of their associated sites upon logging in.
* **SSO and two-factor authentication:** When a user opts for SSO, they no longer have access to Recurly's two-factor authentication service. This is an important factor to consider when deciding on using the SSO feature.
* **Limited identity provider support:** Currently, Recurly's SSO feature supports only three identity providers: Okta, Microsoft Entra, and Google. If you use a different identity provider and are interested in the SSO feature, you should contact Recurly's support team.

## SSO and Recurly's access control

SSO controls authentication to Recurly App but does not govern which sites a user can access once they are logged in. Users associated with multiple sites in Recurly can navigate to all of their sites after logging in.

## Importance of a valid SSO certificate and consequences of neglect

### The role and significance of a valid SSO certificate

The SSO public certificate, generated by your Identity Provider (IdP), performs a critical function. It is used to sign and encrypt SAML responses and assertions sent between Recurly and your IdP. This process ensures that the login requests originate from the correct source and have not been tampered with. In short, this certificate is crucial for maintaining the security and integrity of your SSO setup.

### Consequences of an expired certificate

If your SSO public certificate expires and isn't updated, Recurly will not be able to verify the authenticity and integrity of the SAML responses and assertions from your IdP. Consequently, this will prevent your SSO users from being able to log in. Therefore, maintaining an up-to-date, valid certificate is critical for uninterrupted access to Recurly for your SSO users. It's strongly recommended to monitor and update your certificate before its expiration date to avoid any disruption in service.

# Step-by-step processes

## Configuration and setup for Okta

To utilize the Okta identity provider with Recurly's SSO feature, you'll need to perform the following steps:

#### Add Recurly Application to Okta

1. **Log in to Okta**: As an Okta Administrator, access your Okta instance and go to the "Admin" section.

2. **Access Applications**: Expand the "Applications" section in the left navigation pane and click on "Applications".

3. **Browse App Catalog**: Click on "Browse App Catalog" and search for "Recurly".

4. **Add Recurly Integration**: Select "Recurly" from the search results and click on "Add Integration".

5. **Configure Application Name**: Under the "General Settings" section, set the application name and then click "Next". 


![](https://files.readme.io/3296693-image.png)

6. **Configure Sign-On Options**: Set the "Default Relay State" to your site’s subdomain. Remember, you only need to input the subdomain, not the full URL. You can find the Recurly Subdomain under Site Settings from the Configuration navigation section of the site.  

![](https://files.readme.io/ddba16e161724317a80e179f69571752497841aec15ee32d6f9f4780193a7b83-image.png)

1. **Upload Recurly Certificate**: Get a copy of the certificate from Recurly Support and upload it in this step.

2. **Set Application Username Format**: Select "Email" for the "Application username format" and click "Done" to save your settings.

3. **Assign Recurly App**: The final step in Okta is to assign the Recurly App to the appropriate users.

<Image align="center" border={true} width="50% " src="https://files.readme.io/59de449-image.png" className="border" />

##### Configure SAML Credentials in Recurly

1. **Access Sign On**: In Okta, click on the “Sign On” tab and then click on “More Details”.

<Image align="center" border={true} width="50% " src="https://files.readme.io/9836171-image.png" className="border" />

2. **Set Status to Enabled**: In Recurly, navigate to the site you want to enforce SSO on. Expand the Admin section of the site and click on “SSO Settings”. Set “Status” to Enabled and “Provider” name to Okta.
3. **Transfer Metadata**: Copy the Okta Recurly application metadata to the Recurly SSO settings. You can do this by clicking the "Configure Single Sign-On" button on the Users page of your Recurly site and following the Okta instructions.

<Image align="center" border={true} width="50% " src="https://files.readme.io/497d725-image.png" className="border" />

Here's a quick guide to match Okta fields to Recurly fields:

| Okta Field          | Recurly Field  |
| ------------------- | -------------- |
| Sign-On URL         | Login URL      |
| Issuer              | SAML Issuer ID |
| Signing Certificate | Certificate    |

<Image align="center" border={true} width="50% " src="https://files.readme.io/8ed8616-image.png" className="border" />

4. **Save Changes**: Once you've filled all the necessary fields, click “Save Changes”.

##### Log in via SP-initiated SSO:

1. Open the following URL: `https://app.recurly.com/login/sso`
2. Enter your Email.
3. Click Log In.

**Note**: In the event that you face any difficulties or require further clarification, do not hesitate to contact Recurly's support team for assistance [support@recurly.com](mailto:support@recurly.com).

## Configuration and setup for Microsoft Entra (formerly Azure ID)

To configure Microsoft Entra as your identity provider with Recurly's SSO feature, you can follow a comprehensive tutorial on Microsoft's official documentation site.

Please refer to the <a href="https://learn.microsoft.com/en-us/azure/active-directory/saas-apps/recurly-tutorial" target="_blank">Entra Active Directory tutorial for Recurly</a> to guide you through the configuration process.  
Remember, don't hesitate to contact Recurly's support team if you face any issues or need further clarification during the setup process.

## Configuration and setup for Google SSO

To configure Google as your identity provider with Recurly's SSO feature, you will need to set up a "Custom SAML App" in Google Workspace. Note that Super Administrator permissions are necessary to carry out these configuration steps.

### Configure Custom SAML App in Google Admin Console

1. Navigate to "Apps→Web and mobile apps" in the Google Admin Console.

2. Click "Add App", then select "Add custom SAML app".

<Image align="center" border={true} width="80% " src="https://files.readme.io/7d2257f-image.png" className="border" />

3. Name the SAML app and add a description (optional).

<Image align="center" border={true} width="80% " src="https://files.readme.io/5e97bdf-image.png" className="border" />

4. On the Google Identity Provider details page, copy the "SSO URL" and download the "Certificate".

<Image align="center" border={true} width="80% " src="https://files.readme.io/b41aa90-image.png" className="border" />

5. In the Service Provider details page, configure the values as follows:

* ACS URL: `https://app.recurly.com/login/sso`
* Entity ID: `https://app.recurly.com`
* Uncheck the “Signed Response” box. Google will not sign the assertion if this is checked, but Recurly requires that the assertion is signed.
* Name ID format: select "EMAIL" from the dropdown menu.
* Name ID: select "Basic Information→Primary email" from the dropdown menu.

<Image align="center" border={true} width="80% " src="https://files.readme.io/d795b1d-image.png" className="border" />

6. On the "Attribute mapping" page, map the "Primary email" to an app attribute named "Email" (the name for this app attribute is case-sensitive).

<Image align="center" border={true} width="80% " src="https://files.readme.io/6be0aa4-image.png" className="border" />

> 🚧 **Important:**
>
> Ensure your configuration matches the provided reference.

### Configure access

Configure who can access the SAML app within your organization.

1. Navigate back to the Admin console, and go to "Apps→Web and mobile apps". Select the newly created SAML app.

   <Image align="center" border={true} src="https://files.readme.io/1e046ff-image.png" className="border" />

2. Click "User access".

   <Image align="center" border={true} src="https://files.readme.io/43fdede-image.png" className="border" />

3. Under "Groups", select the group to provide access to.  
   Remember: The email addresses users use to sign in to the SAML app must match the email addresses they use to sign in to the Google domain.

### Configure Recurly App

1. Log into Recurly App and navigate to "Admin→SSO Settings".

<Image align="center" border={true} src="https://files.readme.io/8226aa8b49c12d6707dad83a359d1954f986dcf4c52d41ba29a15bf463507828-image.png" className="border" />

2. ¿Configure SSO Settings using the values copied from the Google Admin Console:

* **Set** "Login URL" to the "SSO URL".
* **Set** "SAML Issuer ID" to [https://app.recurly.com](https://app.recurly.com) the same value entered in the "Entity ID" field during step 5 of configuring the custom SAML app.
* **Set** "Certificate" to the certificate that was downloaded.
* **Toggle** "Single Sign-On" to "Enabled".

3. **Save** your settings.

**Note:** If you encounter any issues with Recurly App initiated logins, ensure that the SAML Issuer ID configured in Recurly App matches the Entity ID value in the Google Service Provider details page.

### Finalizing your setup

After finishing the setup process for your chosen identity provider (Okta, Entra, or Google), you can finalize your SSO settings in Recurly.

1. **Go** to "Admin→SSO Settings" in the Recurly App.
2. **Click** on the "Enabled" radio button to enable SSO.

When you enable SSO, new user invitations for your site will automatically have SSO enabled by default.

> **Note:** Enabling SSO will not immediately affect existing users. To require existing users to use SSO, you'll need to manually update their settings. Follow the steps provided below for this process.

## Finding the certificate expiration date

To locate the expiration date of your SSO certificate, follow the steps below:

1. **Log** into your Recurly App.
2. **Navigate** to "Admin→SSO Settings".
3. **Locate** the uploaded certificate.

The expiration date of the certificate will be displayed alongside the certificate details. Make a note of this date and ensure you renew the certificate before its expiration to maintain seamless SSO login functionality for your users.

## How to update your certificate

Updating your SSO certificate is a crucial task to ensure the continued smooth operation of the single sign-on function. The process varies slightly based on your chosen identity provider. Below are the steps for each of the supported providers:

### Okta

1. **Navigate** to your Applications in Okta and click on the application you configured for Recurly.
2. **Proceed** to the "Sign On" tab and scroll down to "SAML Signing Certificates".
3. **Click** "Generate new certificate".
4. Under "Actions", **activate** the newly generated certificate. Note: The old certificate should now display an "Inactive" status after the new certificate has been activated.
5. Under "Actions" again, **download** the certificate and paste it into the "Certificate" field in your Recurly site's SSO settings.

Your site should no longer be displaying notifications regarding your SSO certificate, and the new certificate's expiration date should now be displayed.

### Entra

For Entra, please refer to <a href="https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/tutorial-manage-certificates-for-federated-single-sign-on" target="_blank">Microsoft's documentation available</a>.

### Google

For Google, please refer to <a href="https://support.google.com/a/answer/7394709?hl=en" target="_blank">Google's available support documentation</a>.

## Transitioning existing users to SSO

1. Navigate to the Users page on your Recurly site.

2. Select the user that you want to transition to SSO.

3. Click on the "Single Sign-On" radio button.

<Image align="center" border={true} width="80% " src="https://files.readme.io/fe4dc4167f4c80d54023882daf9bffc19b42a62039650f9c625f929b0b569392-image.png" className="border" />

If the user is currently using 2-factor authentication, you will be prompted to confirm that you want to disable 2FA and replace it with SSO.

### Saving Changes and User Login Process

Once the necessary changes for Single Sign-On (SSO) setup are made and saved, certain actions will automatically be initiated by Recurly:

1. Any current user session on Recurly will be logged out.
2. The user will receive an email notification informing them that SSO is now required for their Recurly login.
3. The user can then log back into Recurly by:
   * Clicking on the link provided in the email notification they received,
   * Navigating to [http://app.recurly.com/login/sso](http://app.recurly.com/login/sso) directly, or
   * Logging into their identity provider and clicking on the Recurly tile.  
     Subsequently, on the users' page of your site, a "Security" column will be visible in the table of users. This will help you determine whether a user is employing SSO or Two-Factor Authentication (2FA) for security. A user whose security method displays as "SSO" uses Single Sign-On, one with "2FA" uses Two-Factor Authentication, and if the column is empty, the user is simply using their email and password to login.

<Image align="center" border={true} width="75% " src="https://files.readme.io/7bf0361-image.png" className="border" />

Remember: Users will only be able to access Recurly with the email address that matches the one they use for their SSO identity provider. Make sure these emails match to prevent any login issues.

## Inviting a user to join a site and requiring them to use SSO

With Single Sign-On (SSO) enabled for your site, any new user invitations will default to requiring the use of SSO for Recurly login. This requirement can be disabled for individual invitations if desired.  
Assuming you send an invitation with the SSO option selected:

1. Ensure that the user also has access to Recurly through your identity provider.
2. The invited user will receive an email from Recurly, extending an invitation to join your site.
3. If they accept the invitation, they will be notified that they are required to use SSO for login.

* Please note, if the user already had a Recurly account and was using SSO to access it, they will continue to do so using the same SSO identity provider as before.
* You can check a user's SSO requirements by visiting their user profile on your site. If a different site is requiring them to use SSO, the details will be visible on their profile.

<Image align="center" border={true} src="https://files.readme.io/2748851-image.png" className="border" />

## Updating an existing user to no longer require them to use SSO

If you decide not to require a user to use SSO for login, you can update this by following these steps:

1. Navigate to the site that is requiring the user to use SSO.
2. Navigate to the users page for that site, and select "edit" for the user that you want to update.
3. Change the "Account Security" setting to "password only".  
   You will be prompted to confirm your action, since this change will downgrade the account's security from SSO to password only.
   After saving your changes, the following actions will occur:

* Recurly will log the user out of any current session.
* Recurly will send the user an email notifying them that SSO is no longer required for their Recurly login.
* The notification email will contain a link for the user to reset their password. Upon clicking this link, the user will enter their email address and receive another email from Recurly. This second email will contain a temporary URL that leads them to a page where they can create a new password for their Recurly account.

## Disabling SSO

If you need to disable SSO entirely for your site, follow these steps:

1. Navigate to the site for which you want to disable SSO, and proceed to the users page for that site.
2. Click on the "Configure Single Sign-On" button.
3. Select the "Disable" radio button, and then save your changes.  
   You will be prompted to confirm your action. If you confirm the action, the following will happen:

* Every user that is required to use SSO by this site will be logged out of any current session on Recurly.
* Recurly will send the users an email notifying them that SSO is no longer required for their Recurly login.
* The users will then follow the same flow as described above to create a new password for their Recurly account.

## SCIM for Okta

Currently, Recurly supports the following features with SCIM for Okta:

* Supported features:
  * Create users.
  * Deactivate users.
  * Group push.

### Configuration steps

* In your Recurly site, **navigate** to SSO Settings under the Admin section.
* **Select** Enable under SCIM Provisioning.
* **Select** an initial provisioning role for new users.
  * This role will be used for initial user provisioning. The role for the user can be updated later.
  * By default, new sites have only a `site admin` role. It is recommended to create a new user role under the Role section with the desired permissions.
* **Click** Save Changes to save the configuration and generate an API Token.

<Image align="center" border={true} width="75% " src="https://files.readme.io/35f385f-first_one.png" className="border" />

* **Click** on the icon at the end of the API Token field to display the API Token. Copy the API Token to your clipboard.
* In the Okta portal, **navigate** to the Recurly SAML App.
* **Click** on the Provisioning tab.

<Image align="center" border={true} width="75% " src="https://files.readme.io/a584551-image.png" className="border" />

* **Click** on Configure API Integration.

<Image align="center" border={true} width="75% " src="https://files.readme.io/7e9d6b4-the_onenow.png" className="border" />

* **Click** on Enable API Integration.
* **Paste** the Recurly API Token copied from the Recurly SSO Settings page to the API Token field.

<Image align="center" border={true} width="75% " src="https://files.readme.io/66eb572-image.png" className="border" />

* **Click** Test API Credentials.

<Image align="center" border={true} width="75% " src="https://files.readme.io/5c92519-image.png" className="border" />

* After a successful test of the API Integration, **click** "Save".
* Under To App, **click** "Edit".

<Image align="center" border={true} width="75% " src="https://files.readme.io/f4e4d9f-image.png" className="border" />

* **Enable** Create Users and Deactivate Users and Click Save.

<Image align="center" border={true} width="75% " src="https://files.readme.io/563ef76-image.png" className="border" />

* As users are Assigned the Recurly app in Okta, the users will receive an invite to the Recurly site that was configured for SCIM Provisioning.
* When users are unassigned the Recurly app in Okta, the user will be removed from the site configured for SCIM Provisioning.

## SCIM group support instructions

### SCIM group configuration in Okta

* **Open** the Okta Admin portal. Expand Directory and click on Groups.

* **Create** a Group in Okta.

<Image align="center" border={true} width="75% " src="https://files.readme.io/e5bd4dd-add_group_dark.png" className="border" />

* **Expand** Applications and click on Applications.

* **Select** Recurly app.

* **Click** on Push Groups then Find Groups by Name.

<Image align="center" border={true} width="75% " src="https://files.readme.io/25c8ae2-image.png" className="border" />

* For each group created in Okta for this Recurly site, type in the name of the group then select it.

<Image align="center" border={true} width="75% " src="https://files.readme.io/66d3f59-image.png" className="border" />

* **Click** save.

> **Note:** The group pushed under Push Groups should also not be assigned to the application per Okta Documentation on limitations of Group Push. [https://help.okta.com/oie/en-us/content/topics/users-groups-profiles/usgp-about-group-push.htm](https://help.okta.com/oie/en-us/content/topics/users-groups-profiles/usgp-about-group-push.htm)

* The group should appear in Recurly app prefixed with SCIM_

<Image align="center" border={true} width="75% " src="https://files.readme.io/a704759-Screenshot_2023-11-07_at_3.23.48_PM.png" className="border" />

> **Note:** When a group is first pushed to the Recurly app, the corresponding role in the Recurly app will be created with the default permissions of Customer Read Only. The permissions for the role will need to be updated in the Recurly app.

### Set group permissions in the Recurly app

* In the Recurly app, navigate to Roles under the Admin section.

* Select the role pushed to the Recurly app from Okta.

<Image align="center" border={true} width="75% " src="https://files.readme.io/a704759-Screenshot_2023-11-07_at_3.23.48_PM.png" className="border" />

* Click on Edit.

<Image align="center" border={true} width="75% " src="https://files.readme.io/b545e67-Screenshot_2023-11-07_at_4.51.39_PM.png" className="border" />

* Assign appropriate permissions to the role.

<Image align="center" border={true} width="75% " src="https://files.readme.io/16cd1b3-Screenshot_2023-11-07_at_3.24.11_PM.png" className="border" />

> **Notes:**
>
> * Groups created from Okta can only be renamed and deleted from Okta when SCIM provisioning is enabled for the site.
> * Users should only be assigned to one Group in Okta. Users assigned to multiple groups in Okta will only inherit the permissions of the last group assignment.

### Assigning users through Okta SCIM integration

* User(s) can be individually assigned to the Recurly Okta App.

<Image align="center" border={true} width="75% " src="https://files.readme.io/c7c5ed6-Screenshot_2023-12-12_at_4.57.56_PM.png" className="border" />

* User(s) can be assigned through a group to the Recurly Okta App.

<Image align="center" border={true} width="75% " src="https://files.readme.io/13d8b40-image.png" className="border" />

* User(s) will be assigned the default SCIM role configured in the Recurly app for the site.
  * If not using Group Push, the user can be assigned a different role in the Recurly app.

### Removing users through Okta SCIM integration

* If the user is individually assigned to the Recurly Okta App, unassign the user from the Recurly Okta App. This will result in the user being removed from the Recurly app.
* If the user is assigned through a group assigned to the Recurly Okta App, remove the user from the group. This will result in the user being removed from the Recurly app.
  * Unassigning the group from the Recurly Okta App will remove all users belonging to the group from the Recurly app.

### Using Okta groups to assign the Recurly app roles to users provisioned via SCIM

* After the user is assigned to the Recurly Okta Application and groups are pushed to the Recurly app via Group Push and permissions updated, assign the user to a group in Okta. The user in the Recurly app will be assigned the corresponding role.
  * It is recommended to only assign a user to a single pushed group in Okta. Assigning a user to multiple pushed groups will result in the user being assigned to the corresponding role of the last pushed group the user was assigned to.

### Changing a user’s role through Okta groups

* If the user is already assigned to an Okta group pushed to the Recurly app, remove the user from the pushed Okta group. The user’s role in the Recurly app will be updated to the default SCIM role configured in the Recurly app for the site.
* Assign the user to a pushed Okta group corresponding to the role the user should be assigned in the Recurly app. The user’s role in the Recurly app will be updated to the corresponding role.

### Migrating to using Okta group push for user role management in the Recurly app

* Ensure existing users are assigned the Recurly Okta Application individually or via a group that is not pushed to the Recurly app.
* Push Okta groups to Recurly apps via Group Push described above and configure permissions for the created role(s) in Recurly app.
* Assigning a user to a pushed group in Okta will assign the user to the corresponding role in the Recurly app.
* In order for user(s) to not lose their existing permissions, ensure the user is assigned to a group where the corresponding Recurly app role has the same permissions.

### Removing users through Okta SCIM integration

* If the user is individually assigned to the Recurly Okta App, unassign the user from the Recurly Okta App. This will result in the user being removed from the Recurly app.
* If the user is assigned through a group assigned to the Recurly Okta App, remove the user from the group. This will result in the user being removed from the Recurly app.

### Removing pushed Okta groups

* Unlinking and deleting the Okta group pushed to the Recurly app will delete the corresponding Recurly app role. Any users assigned this role will be updated with the default SCIM role assigned in the Recurly app for the site. This is the recommended way of unlinking a pushed Okta group.
* Unlinking and leaving the Okta group pushed to the Recurly app will leave the corresponding Recurly app role. Any users assigned this role will continue to access the Recurly app with the permissions assigned to this role.

# Migrating existing users to SCIM

Once SCIM has been enabled and configured on the Recurly Okta Integration app, existing users assigned to the Recurly Okta Integration app will need to be migrated as Okta only recognizes users assigned to the application as provisioned after SCIM has been enabled.

Currently, this requires unassigning and reassigning the users to the Recurly Okta Integration app. Since the existing users are not provisioned according to Okta, unassigning the users will not remove the user from Recurly App. During this time window of reassigning the user to the Recurly Okta Integration app, the user will not be able to log in to Recurly App.

Once the user is reassigned to the Recurly Okta Integration app, Okta will trigger a provisioning request to Recurly App. Since the user is already a member of your site, this will be a no-op.

While a default role is configured to assign to new users provisioned through SCIM, existing users will maintain their existing role. A user’s role will only change if a group has been pushed through Push Groups in the SCIM integration, and the user is a member of the group in Okta.

# FAQs and troubleshooting

**Q: I'm trying to login at[https://app.recurly.com/login](https://app.recurly.com/login) but keep getting an error that the email address or password is incorrect. What should I do?**

**A:** If you're an SSO user, you should be logging in at [https://app.recurly.com/login/sso](https://app.recurly.com/login/sso), or via your identity provider.

**Q: I'm trying to login at[https://app.recurly.com/login/sso](https://app.recurly.com/login/sso) but keep getting an error that my email address is invalid. How do I solve this?**

**A:** You might be entering the wrong email address, or your account may not be set up as an SSO account. Contact your site administrator or Recurly Support for assistance.

**Q: I'm trying to login to my new site, but I get an error that I "must first accept the invitation to join this site". What should I do?**

**A:** You need to accept the invitation to join a site before you can login. Check your email for an invitation from Recurly and click on the "Accept invitation" link. If you did not receive an email, check your spam folder or ask the site Administrator to resend the invitation.

**Q: I'm trying to login via my identity provider, but the login is failing - I get to Recurly and see an error message that the login is invalid. What can be the issue?**

**A:** First, verify that your Recurly account is required to use SSO and that Recurly is expecting you to sign in via the identity provider that you are using. If everything seems correct but you still can't login, ask your site Administrator to reset your account to use a password, and then set your account to use SSO again.
