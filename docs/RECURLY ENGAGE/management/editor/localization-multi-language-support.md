---
title: Localization (Multi-language support)
excerpt: >-
  How to localize prompts based on your user’s browser or app locale without
  duplicating prompts for each language.
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

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.

# Definition

**Prompt localization** uses a CSV of translations to serve prompt copy in multiple languages, automatically matching your user’s locale without creating separate prompts.

# Key benefits

* **Single-prompt maintenance**: Manage all languages in one place—no need for multiple prompt copies.
* **Automatic matching**: Detects user locale and serves the correct translation.
* **Fallback support**: Default language ensures coverage when no match is found.

# Key details

## Setup

1. Prepare a CSV with one row per language, using [ISO 639-1](https://www.w3schools.com/tags/ref_language_codes.asp) codes. Columns correspond to prompt fields (headline, body, button labels).
2. Use the [sample CSV](https://assets.redfast.com/docs/translations_sample.csv) as a template.
3. Upload the CSV in Pulse under your prompt’s **Localization** section.

> 🚧 Important
>
> **Do not delete columns** in the CSV—all columns are required. Leave unused fields blank.
>
> Exactly **one** row must have `default=true`; this language serves as the fallback.

**Desktop preview**

![](https://files.readme.io/dc57b6a-image.png) 
<br/>

![](https://files.readme.io/18bf885-image.png)

**Mobile preview** ![](https://files.readme.io/1facf58-image.png) ![](https://files.readme.io/a2ca771-image.png)

After saving, a language selector appears in the preview area. Choose a language to verify translations, then use **Live Preview** to test on your site. ![](https://files.readme.io/ecfc764-image.png)

## Technical Information

Recurly Engage determines the end user’s language from three sources (in priority order):

1. Value passed by `Redfast.setLanguage()` in your web snippet
2. User’s `language` trait
3. Browser `Accept-Language` HTTP header

Matching logic:

* Exact match on 2-letter or 4-letter code (e.g., `en-US`).
* If no exact match, attempts generic 2-letter match (`en` for `en-GB`).
* If still no match, serves the row with `default=true` from your CSV.