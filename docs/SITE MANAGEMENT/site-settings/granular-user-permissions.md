---
title: Granular User Permissions
excerpt: >-
  Create and assign roles in Recurly to control what each team member can access
  and do — from read-only customer views to full site admin privileges.
deprecated: false
hidden: true
icon: fad fa-alicorn
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">User roles and permissions let you control exactly what each team member can see and do in Recurly. Create custom roles, assign them to users, and update them as your organization evolves — keeping access aligned with responsibilities and sensitive data appropriately restricted.</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#create-a-role"><span class="rp-toc-num">4</span>Create a role</a>
    <a class="rp-toc-pill" href="#delete-a-role"><span class="rp-toc-num">5</span>Delete a role</a>
    <a class="rp-toc-pill" href="#invite-a-user"><span class="rp-toc-num">6</span>Invite a user</a>
  </div>
</div>

# Definition

<div class="rp-definition">User roles in Recurly are defined sets of permissions that determine what actions and features a user can access within the platform. You can tailor roles to match your organization's structure — granting each team member access to exactly the sections and functions they need, and nothing more.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Tailored access</strong>
    <span>Customize roles to grant permissions so users only access to functionality and data relevant to their work.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Enhanced security</strong>
    <span>Set read, write, and delete access levels for most permissions for precise control over what each user can view, change, or remove.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users" aria-hidden="true"></i></div>
    <strong>Optimized collaboration</strong>
    <span>Ensure team members have the tools they need by matching roles to their actual responsibilities.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-table-list" aria-hidden="true"></i></div>
    <strong>Streamlined management</strong>
    <span>Manage and modify all roles from a centralized page, with a clear view of who has access to what.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-spin" aria-hidden="true"></i></div>
    <strong>Flexibility</strong>
    <span>Adapt roles as your organization grows or changes, keeping access aligned with evolving business needs.</span>
  </div>
</div>

# Key details

## Permission Categories

<div class="rp-callout rp-callout-note">
  <div>Permissions in Recurly build on each other. If you give a role delete access, it also includes edit and read access. Likewise, a role with edit access also includes read access</div>
</div>

### Customers

**Customers** — Selecting this single view only permission will grant read access to accounts, subscriptions, gift cards, invoices, and transactions; allowing your user to have a complete view of a customer's account activity.  Users at this level can't access Hosted Account Management links or update billing information.

**Accounts, Subscriptions, Invoices, Transactions** — Selecting one or more of these permissions will inherit the **Customers** view access listed above, plus grant either edit or a destructive action (cancelling a subscription, closing an account) as its highest level of access.

<Image src="https://files.readme.io/3cefff296c30a1efa6395fc7273882640f737f00189e03dd03ec44a274ee0cd8-Screenshot_2026-10-06_at_3.44.55_PM.png" border={true} />


### Analytics

Users with Analytics access can view and export all data in the Analytics section, with full visibility into analytics reporting.

### Configuration

A vast number of role combinations can be created within the Configuration category, allowing you to create and edit roles as your business needs shift and change.  No two permissions depend on one another to grant access to a single page.  However, a few select permissions will grant access to multiple pages.

### App Management

These permissions are enabled through a feature flag.

### Integrations

Users with Integrations access can view and edit Webhooks, API keys, and Recurly integrations with QuickBooks Online, Xero, Mailchimp, Salesforce, and Zendesk.

### Revenue Recognition

Users can be assigned Read-Only or Admin access to Recurly's Revenue Recognition platform. The **Allow Access** checkbox enables or disables general access to Revenue Recognition for the role. &#x20;

These permissions are enabled through a feature flag.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The Read-Only vs. Admin distinction within Revenue Recognition can only be set during initial role configuration. After a role is saved, granular access control within Revenue Recognition itself is the only way to change this. The Revenue Recognition section only appears on sites with the Revenue Recognition feature flag enabled.</div>
</div>

### Admin

Users with Admin access have full control over company billing information, account settings, Users, Roles, Admin Exports, and SSO Settings — the highest level of access in Recurly.

<br />