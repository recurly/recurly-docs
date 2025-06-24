---
title: Testing a prompt before launching
excerpt: >-
  Guidance on how to safely test prompts before launching to production
  audiences in Recurly Engage.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# How can I test a prompt without affecting live users and ensure it can be re-displayed for repeated testing?

Activate the prompt on the internal **[Test Users](test-users)** segment so only designated user IDs can see and validate it in your production environment. You can also create a custom segment targeting individual test user IDs if you need more granular control. Once you’ve confirmed the prompt’s behavior and made any necessary adjustments, update the prompt’s segment to your intended audience and it will go live accordingly.

<Image align="center" className="border" border={true} src="https://files.readme.io/ba8c882-image.png" />

> 📘 If the test prompt only displays once:
>
> **Interaction Settings:** Ensure “Show prompt again after button 1 click or button 2 click” and/or “Show prompt again after button 3 click” under **User Interaction** is set to “On the next visit” or “After X minutes/hours/days.”
>
> **Prompt Limits:** Verify that impression limits, frequency caps, or delivery limits aren’t preventing repeated displays.
>
> **Reset Goals:** To simulate a fresh user state, reset goals via **Settings > Users > Test Users > Reset Goals** in the Live tool or run `RecurlyEngage.resetGoals();` in your browser console.