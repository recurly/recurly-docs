---
title: Personalized onboarding
excerpt: Use Redfast to onboard new and existing users in a personalized manner
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: See more popular uses
  pages:
    - type: basic
      slug: popular-uses
      title: Popular Uses
---
#### Metadata description

Configuration guide for the Personalized Onboarding use case, leveraging Journey guides to educate new users contextually.

# Overview

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

Traditional onboarding tours interrupt the user flow with step-by-step callouts. The **Personalized Onboarding** Journey guide delivers prompts only for actions or sections the user hasn’t yet seen—and can span multiple visits—for a frictionless, contextual experience.

# Key benefits

* **Contextual guidance**: Show prompts only for features the user hasn’t accessed.
* **Multi-visit flexibility**: Space your onboarding steps across sessions to avoid overload.
* **Higher engagement**: Streamlined education that respects the user’s flow.

# Key details

Traditional approaches to onboarding new users include a step-by-step homepage tour with highlighted callouts to various features. This method may work for B2B, but B2C users often find it disruptive.

Recurly Engage’s Journey guide lets you predefine a sequence of prompts linked to key site elements. Each prompt fires only if the user hasn’t completed the associated action, and you can schedule them over multiple visits—resulting in a more user-friendly onboarding flow.

<Image align="center" className="border" border={true} src="https://files.readme.io/8e77a00-Screenshot_2024-04-19_at_1.33.00_PM.png" />

> 📘 Important
>
> Create usage trackers for your key features and content, then reference those trackers in your onboarding guide to target only first-time interactions.

## Guide

1. **Create** a new Guide (Settings > Guides) and **set** the type to **Journey**.
2. **Configure** the first prompt as a **Popup** targeting first-time visitors.
3. **Set** the CTA on that prompt to either trigger the feature directly (1-Click) or **redirect** to the relevant page.
4. **Add** a second prompt in the guide and schedule it for the user’s next visit.
5. **Add** a third prompt scheduled for a subsequent visit as needed.
6. **Target** the guide to the **Test Users** segment.
7. **Specify** the trigger conditions (e.g., specific page URLs or tracker events).
8. **Start** the Guide.
9. **Add** your User ID to **Test Users** (Settings > Users > Test Users).
10. **Verify** that each prompt appears in the correct order across visits.

> 📘 Important
>
> To experiment with different onboarding sequences, run an A/B test on your guide prompts.