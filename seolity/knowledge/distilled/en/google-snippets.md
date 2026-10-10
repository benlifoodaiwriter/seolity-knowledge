---
title: Control your snippets in search results
lang: en
topic: meta
tags: meta, ctr, serp, snippet, meta description, nosnippet, max-snippet, data-nosnippet
sources: https://developers.google.com/search/docs/appearance/snippet
updated: 2026-10-10
generated: knowledge-builder
---

# Control your snippets in search results

Google builds snippets mainly from on-page content, but sometimes uses the meta description when it describes the page better. Writing unique, descriptive meta descriptions and using snippet control directives helps improve the quality of search results and the traffic they bring.

## How Google creates snippets

- Do make the on-page content clear and relevant, because Google primarily builds snippets from the page content itself.
- Do expect different snippets for different queries, because Google shows the part of the page that best relates to a user's specific search.
- Do write a good meta description, because Google sometimes uses it when it describes the page more accurately than the on-page content.
- Avoid assuming you can set or manually change a snippet for a page, because Google cannot change snippets for individual sites manually; you can only influence them through content and meta descriptions.

## Controlling snippet display and length

- Use the nosnippet meta tag only when you want to prevent Google from showing a snippet for a page in search results.
- Use the max-snippet: [number] meta tag to tell Google the maximum snippet length you want.
- Use the data-nosnippet attribute to keep specific parts of a page out of the snippet.
- Do not worry about a meta description length limit, because there is none, but know that the snippet is truncated as needed, typically to fit the device width.

## Writing quality meta descriptions

- Do write the meta description as a short, relevant summary that works like a pitch convincing the user the page is what they are looking for.
- Do make descriptions truly descriptive, because meta descriptions are not visible on the page and are easy to neglect, yet high-quality ones can improve the quality and quantity of search traffic.
- Avoid descriptions that are just lists of keywords, because they do not tell users what the page contains and are less likely to be shown as a snippet.
- Avoid descriptions that are too short (for example just a product name); be specific and detailed about the product or page.
- Avoid vague or off-topic intros that do not summarize the page; summarize the whole page, including what the user will learn or get.
- Do include useful facts in the description, such as author, publication date or byline for articles, and price, age or manufacturer for products, so key information scattered across the page is brought together.

## Unique descriptions and prioritization

- Do create a unique description for each page that accurately describes that specific page, because identical or similar descriptions across pages are not helpful in search results.
- Use site-level descriptions on the home page and other aggregation pages, and page-level descriptions everywhere else.
- If time is limited, prioritize writing descriptions for critical URLs such as the home page and popular pages.
- Avoid reusing one generic description across all articles (for example the same tagline for every news story); use a summary taken from the specific article instead.

## Programmatic descriptions and CMS setups

- Do generate descriptions programmatically on large database-driven sites (for example product catalogs) where hand-writing is impractical, because Google encourages this when done well.
- Make programmatically generated descriptions human-readable and diverse, and base them on page-specific data.
- Avoid building generated descriptions from long strings of keywords, because they do not give users a clear idea of the page.
- If you use a CMS such as WordPress, Wix or Blogger and cannot or prefer not to edit HTML directly, use the CMS's search engine settings page or similar mechanism to set meta tags in the page <head>.

## Supporting "Read more" deep links

- Make sure the main content is immediately visible to a human, not hidden behind expandable sections or tabbed interfaces, to increase the chance of "Read more" deep links.
- Avoid using JavaScript to control the user's scroll position on page load, such as forcing the scroll position to the top, because it can reduce the likelihood of deep links.
- If you use history API calls or modify window.location.hash on page load, do not remove the hash fragment from the URL, because that breaks deep linking behavior.

Source: https://developers.google.com/search/docs/appearance/snippet
