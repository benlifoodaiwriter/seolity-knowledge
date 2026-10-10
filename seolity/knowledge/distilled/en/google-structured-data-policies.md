---
title: General structured data guidelines for rich results
lang: en
topic: schema
tags: schema, rich-results, structured-data, json-ld, google-search
sources: https://developers.google.com/search/docs/appearance/structured-data/sd-policies
updated: 2026-10-10
generated: knowledge-builder
---

# General structured data guidelines for rich results

These are Google's general guidelines that all structured data must follow to be eligible for rich results. They cover technical format and access, content quality, relevance, completeness, placement, and how to mark up multiple items on one page. Following them improves eligibility, but Google never guarantees that rich results will appear.

## Eligibility and expectations

- Make sure structured data does not violate Google's Content policies for Google Search (including the spam policies), because violations make a page ineligible for rich results.
- Do not promise that markup will produce a rich result. Structured data enables a feature but does not guarantee it, because Google tailors results to search history, location, device type and other variables.
- Check the Manual Actions report in Search Console for structured data issues. A structured data manual action removes rich result eligibility but does not affect how the page ranks in Google web search.
- Do not rely only on the Rich Results Test passing. It cannot catch every error, such as markup that is incorrect in ways it cannot detect or that is misleading.
- Follow the general guidelines, the guidelines of the specific feature, Search Essentials and the Content policies together, because missing any of them can stop rich results from showing.

## Technical requirements

- Use one of the three supported formats: JSON-LD (recommended), Microdata or RDFa.
- Prefer JSON-LD for new markup, such as in a WordPress or WooCommerce template, because Google recommends it.
- Do not block pages with structured data from Googlebot via robots.txt, noindex or any other access control, because Google must be able to access them.
- Test technical compliance with the Rich Results Test and the URL Inspection tool, which catch most technical errors.

## Content quality and honesty

- Mark up only content that is visible to readers of the page. For example, if the JSON-LD describes a performer, the HTML body must describe that same performer.
- Keep time-sensitive information up to date, because Google won't show a rich result for time-sensitive content that is no longer relevant.
- Provide original content that you or your users have generated.
- Avoid marking up irrelevant or misleading content, such as fake reviews or content unrelated to the focus of the page.
- Do not use structured data to deceive users, impersonate a person or organization, or misrepresent ownership, affiliation or primary purpose.
- Follow any extra content policies in the specific feature guide, such as the job posting content policies for JobPosting.
- Make the markup a true representation of the page content. For example, do not label broadcasts as local events or woodworking instructions as recipes.

## Completeness, specificity and placement

- Include all required properties listed for your specific rich result type, because items missing required properties are not eligible for rich results.
- Add as many recommended properties as you can, because they raise the quality of the result for users (for example, explicit salaries in job postings, or genuine user reviews and star ratings in recipes).
- Do not use reviews or ratings that are not from actual users, because this may lead to a manual action.
- Put structured data on the page it describes, unless the documentation says otherwise.
- If duplicate pages exist for the same content, place the same structured data on all duplicates, not only on the canonical page.
- Use the most specific applicable schema.org type and property names.

## Images in structured data

- Use images in structured data properties only when they are relevant to the page. For example, the image of a NewsArticle must be relevant to that article.
- Make sure every image URL in structured data is crawlable and indexable, otherwise Google cannot find and display it.
- Use the URL Inspection tool to check whether Google can access your image URLs.

## Multiple items on a page

- Mark up every distinct, user-visible item on a page (for example a recipe, its video and its breadcrumbs), because this gives Google a fuller picture and makes the page eligible for more search features.
- Use nesting when one main item has related items grouped under it, such as a Recipe with nested aggregateRating and video.
- Use individual items when each item is a separate block, for example Recipe and BreadcrumbList in a JSON-LD array.
- When separate items belong together (for example a recipe and its video), use @id in both items to link them, otherwise Google may not know it can show the video as a Recipe rich result.
- Always include the main structured data type that reflects the page's main focus. A recipe page needs Recipe markup in addition to Video and Review, because Video alone would not let Google show a recipe rich result.
- Make marked-up items complete. If you mark up reviews, include all reviews visible on the page, because omitting some would mislead people who expect to see them all.

Source: https://developers.google.com/search/docs/appearance/structured-data/sd-policies
