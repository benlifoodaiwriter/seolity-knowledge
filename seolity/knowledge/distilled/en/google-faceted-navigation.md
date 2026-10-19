---
title: Managing crawling of faceted navigation URLs
lang: en
topic: ecommerce
tags: ecommerce, faceted-navigation, site-architecture, crawl-budget, robots.txt, canonical, url parameters
sources: https://developers.google.com/search/docs/crawling-indexing/crawling-managing-faceted-navigation
updated: 2026-10-19
generated: knowledge-builder
---

# Managing crawling of faceted navigation URLs

Faceted navigation built on URL parameters can create near-infinite URL spaces that cause overcrawling and slow the discovery of new, useful pages. This guidance explains how to block crawling of unneeded facet URLs, and how to structure facet URLs that you do want crawled and indexed.

## Understand the risk of faceted URLs

- Treat parameter-based faceted navigation as a crawl risk: every combination of filters (for example products, color, size) produces a different URL, so the number of possible URLs becomes very large.
- Avoid letting crawlers spend time on useless facet URLs, because crawlers cannot tell whether such URLs are useful without crawling them first, which leads to overcrawling.
- Remember that overcrawling of facet URLs slows discovery of new, useful URLs, since crawl time is wasted on low-value pages.
- Decide for each facet type whether it needs to be indexable: if not, prevent crawling; if yes, follow the URL best practices below. Keep in mind that crawling faceted URLs costs significant server resources because of the number of URLs and the rendering work required.

## Prevent crawling of facet URLs you don't need indexed

- Use robots.txt to disallow crawling of filter parameters (for example disallow: /*?*color=) when filtered pages add no or negligible benefit, because this saves server resources.
- Allow crawling of individual item pages and a dedicated listing page that shows all products without filters applied, while disallowing the filtered variants. An allow rule such as allow: /*?products=all$ can keep that unfiltered listing crawlable.
- Consider using URL fragments (after #) to specify filters instead of URL parameters, because Google Search generally doesn't support URL fragments in crawling and indexing, so the filtering has no crawl impact positive or negative.
- Prefer robots.txt or URL fragments over rel="canonical" and rel="nofollow" for controlling crawl, as the latter are generally less effective in the long term.

## Use canonical and nofollow as secondary signals

- Point rel="canonical" on filtered URLs to a less-filtered or unfiltered version (for example, a URL with products=fish, color and size filters can canonicalize to ?products=fish), because this may decrease crawling of the non-canonical versions over time.
- Add rel="nofollow" to anchors that link to filtered results pages when appropriate, but make sure every anchor pointing to that specific URL carries rel="nofollow", otherwise it will not be effective.

## Build crawl-friendly URLs for facets you want indexed

- Use the standard & character to separate URL parameters. Avoid commas, semicolons and brackets ([ and ]) as separators because crawlers have difficulty recognizing them as parameter separators.
- If filters are encoded in the URL path (for example /products/fish/green/tiny), keep the logical order of filters always the same and make sure duplicate filters cannot occur.
- Accept that allowing facet URLs to be crawled increases server resource usage and may slow discovery of new URLs on the site.

## Return proper status codes for empty or invalid filter combinations

- Return an HTTP 404 status code when a filter combination returns no results, so both users and crawlers get a proper "not found" response.
- Return 404 as well for URLs with duplicate filters, nonsensical filter combinations, and nonexistent pagination URLs.
- Do not redirect empty filter combinations to a common "not found" page. Serve the 404 error under the URL where it was encountered.
- If the site is a single-page app and returning a real 404 isn't possible, follow the best practices for single-page apps.

Source: https://developers.google.com/search/docs/crawling-indexing/crawling-managing-faceted-navigation
