---
title: Prompts
excerpt: >-
  An introduction to in-app messaging prompts in Recurly Engage and quick access
  to their management console.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Prompts are versatile in-app messages designed to engage users with timely calls to action. Whether you want to announce a feature, offer a discount, or gather feedback, prompts help drive the actions that matter most.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

# Definition

A **prompt** is an in-app message that appears when a user visits your application or website. It consists of a headline, body copy, background, and up to three call-to-action buttons. Recurly Engage supports multiple prompt types—overlay and inline—across desktop, mobile, tablet, and TV devices.

# Key benefits

* **Contextual engagement**: Reach users at the right moment with targeted in-app messages.
* **Flexible customization**: Choose from various prompt types, designs, triggers, and schedules to match your brand and objectives.
* **Data-driven optimization**: Leverage segments, limits, and A/B experiments to refine and improve performance.

# Prompt types

Recurly Engage supports a variety of in-app message formats, all designed in accordance with the [IAB Guidelines](https://www.iab.com/guidelines/iab-new-ad-portfolio/):

* [Inlines](inlines) (horizontal, vertical, tile, text-only): Prompts embedded directly within your page layout.

* [Overlays](overlays) (notification, interstitial, pop up, video, bottom banner): Floating prompts that appear above your content.

* [Invisible](invisible-1): Silent prompts delivered via tracking pixels or JavaScript callbacks for analytics.

* [Other](other) (Email, Push notification\*): Messages sent outside the page—email campaigns or push notifications.

<Image align="center" className="border" border={true} src="https://files.readme.io/b91dfe4-image.png" />

A prompt can be targeted to one or more [Segments](segments) and set to [Trigger](triggers) on events like button clicks, page visits, or time spent on a page. You can [Schedule](schedule-1) prompts for specific dates and times and [Limit](limits) their delivery by user count or budget. For use-case inspiration, explore our [Popular Use Cases](popular-uses).

It’s also possible to run A/B tests with our built-in [Experiments](experiments-1), helping you choose the most effective variation before a full rollout.

Creating prompts is core to what your customers experience. In this section, you’ll find detailed how-to guides for building and managing every prompt type. If you need hands-on support or want us to manage campaigns on your behalf, chat with us to learn about our Managed Campaign options.

The **Prompts** page provides a quick view of all prompts in your account, displaying their status, design preview, target segments, schedule, and high-level performance metrics (impressions, clicks, CTR). Use the **Search** bar or filters (Status, Device/type, Segment) to find what you need.

![](https://files.readme.io/b2e10b0-Screenshot_2024-04-18_173049.png)

## Inline

This video shows how to create a horizontal inline banner for all visitors on your homepage. The steps for vertical, tile, and text-only prompts are identical.

<Embed url="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" href="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

These four prompt types occupy defined zones on your site or application alongside your content—hence the name **inline**.

<Image align="center" className="border" border={true} src="https://files.readme.io/3306b54-Screenshot_2024-04-18_193019.png" />

Inline prompts live in [zones](zones). Any prompt assigned to a zone appears in that location—for example, a horizontal banner in the **Web Featured** zone.

<Image align="center" className="border" border={true} src="https://files.readme.io/e0c5481-Screenshot_2024-04-18_191758.png" />

A single zone can render multiple items of the same type in one of three modes:

* **Stack**: items overlap; each new item appears after the prior one is dismissed.
* **List**: items display side by side, ideal for showing a row of personalized recommendations.
* **Slider**: a carousel showing one item at a time, with optional bullet indicators or auto-rotation.

### Horizontal

A wide banner with a landscape orientation that spans the width of your content area or screen edge-to-edge. Commonly placed at the top or bottom of pages, it can include a call-to-action button and hide itself on click or remain visible.

* **Recommended ratios**: 2×1, 4×1, **6×1**, 8×1, 10×1

![](https://files.readme.io/994d3cd-image.png)

### Vertical

A tall panel with a portrait orientation, typically along the left or right edge of your layout. Like horizontals, it may include buttons and can be timed or click-to-dismiss.

* **Recommended ratios**: 1×2, **1×3**, 1×4

![](https://files.readme.io/a1fb469-image.png)

### Tile

A square or rectangle zone—perfect for grid layouts. Tiles display media and text, and can be closed or persist after interaction.

* **Recommended ratios**: 1×1, 4×3, 16×9.

![](https://files.readme.io/5729a7f-image.png)

### Text-only

A clickable text bar without images, useful for simple announcements or links. It can be configured to hide on click or remain in view.

* **Recommended ratios**: 6×1, 8×1, 10×1.

![](https://files.readme.io/392d0bc-image.png)

### Implementation Guide

1. **Create a zone**

   * **Navigate** to **Settings > Zones > New Zone**.
   * **Name** the zone (no spaces) and **select** its placement (e.g., “Home Page Top Banner”).

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/0e07cb5-image.png" />

   <Image align="center" className="border" border={true} src="https://files.readme.io/60a9382-inline2.png" />

2. **Build an inline prompt**

   * Go to **Prompts > New Prompt**.
   * Choose **Desktop and Mobile**, then select **Horizontal** (or your desired inline type).

     <Image align="center" className="border" border={true} src="https://files.readme.io/564d84a-image.png" />

   <Image align="center" className="border" border={true} src="https://files.readme.io/664a781-image.png" />

   * Enter a name, description, and assign it to your new zone, then click **Submit**.

     <Image align="center" className="border" border={true} src="https://files.readme.io/c8c3561-image.png" />

   * Configure **Segments**, **Limits** (optional), **Schedule** (optional), and **Actions**.

   * Click **Edit prompt design** to customize visuals and copy.

     <Image align="center" className="border" border={true} src="https://files.readme.io/6a6227a-Screenshot_2024-04-22_173653.png" />

   * Tweak settings in the designer and preview live changes. Download sample backgrounds [here](/images/samples.zip).

     <Image align="center" className="border" border={true} src="https://files.readme.io/0d80810-Screenshot_2024-04-22_174308.png" />

   * Click **Publish** to make the prompt live.

     <Image align="center" className="border" border={true} src="https://files.readme.io/a55eac9-Screenshot_2024-04-22_174752.png" />

3. **Manage your zone**

   * View all prompts assigned to a zone under **Settings > Zones**.
   * If multiple items exist, switch between **Stack**, **List**, or **Slider** display modes.

     <Image align="center" className="border" border={true} src="https://files.readme.io/dcbb8c2-Screenshot_2024-04-22_175035.png" />

***

## Integration

Recurly Engage offers two methods for inserting inline zones into your site:

### Live Tool

1. Click the **Live Tool** button and select your domain. ![](https://files.readme.io/7cb2ded-Screenshot_2024-04-22_175333.png) ![](https://files.readme.io/03543e0-Screenshot_2024-04-22_175548.png)
2. Expand the panel, switch to the **Add** tab, and choose your zone. ![](https://files.readme.io/a1fe85f-image.png)
3. Hover over the target area until the outline appears, then click to insert the zone. ![](https://files.readme.io/7878719-image.png)

### Developer Guide

1. Copy the zone identifier (e.g., `data-rf-zone="example-tag"`).
2. In your HTML, insert:

   ```html
   <div data-rf-zone="example-tag"></div>
   ```
3. Optionally wrap it in a container with explicit height for absolute positioning:

   ```html
   <div style="height:200px">
     <div data-rf-zone="example-tag"></div>
   </div>
   ```

***

## Tips & Tricks

> **Absolute positioning—new content**
>
> 1. Insert the zone tag where needed.
> 2. Wrap in a container with a set height.
> 3. Initialize your scroll or animation logic.
>
> **Absolute positioning—replacing content**\
> Use the Live Tool sparingly—ensure your prompt dimensions match the replaced element.

**Content delay solutions**

* **Header load lag**: add CSS animations or skeleton loaders.
* **Above-the-fold delay**: set explicit height with a brief no-collapse timer.
* **Slow SDK load**: move the Recurly Engage tag earlier in your tag order.

**Responsive resizing**

* **Width issues**: use CSS media queries or `transform: scale()`.
* **Background images**: apply `background-size: cover` or bake text into the image.

For further assistance, reach out to our support team or explore our developer resources.