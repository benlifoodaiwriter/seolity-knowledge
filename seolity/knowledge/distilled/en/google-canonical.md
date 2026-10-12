---
title: Specifying canonical URLs for duplicate pages (rel="canonical" and other methods)
lang: en
topic: cannibalization
tags: cannibalization, site-architecture, canonical, duplicate-content, redirects, sitemap, hreflang, https
sources: https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls
updated: 2026-10-12
generated: knowledge-builder
---

# Specifying canonical URLs for duplicate pages (rel="canonical" and other methods)

Explains how to tell Google which URL is canonical among duplicate or very similar pages, using redirects, rel="canonical", and sitemaps. Consolidating duplicates concentrates signals such as links, simplifies metrics, and saves crawl time. Following the best practices avoids conflicting signals that cause the wrong URL to be chosen.

## Why and when to specify a canonical

- Specify a canonical URL when you want to control which URL appears in search results, because otherwise Google picks the version it considers best on its own (e.g. a clean product URL rather than one with a ?gclid= parameter).
- Consolidate duplicate or similar URLs into one preferred URL so signals such as links from other sites are combined on that single URL.
- Reduce duplicate URLs to simplify metric tracking, since many URLs for one piece of content make consolidated reporting harder.
- Reduce duplicates so Googlebot spends crawl time on new or updated pages instead of duplicate versions.
- Remember that specifying a canonical is not required; the site will likely do fine without it, but explicit signals give you control.

## Choosing and combining methods

- Use the methods in order of strength: redirects (strong), rel="canonical" annotations (strong), sitemap inclusion (weak).
- Combine methods where possible, because they stack and raise the chance that your preferred canonical URL is shown.
- Use rel="canonical" for large mappings of duplicates; it can map an unlimited number of duplicate pages, but it can be hard to maintain on large sites or where URLs change often.
- Use sitemaps as a simple way to declare canonicals on large sites, but treat them as a weaker signal than rel="canonical", since Google must still determine the duplicates.
- Use permanent redirects only when you are deprecating a duplicate page, to tell Google the redirected URL is the worse version.
- On a CMS such as WordPress, Wix or Blogger where you cannot edit the HTML directly, look for a search engine settings page or a mechanism for modifying the <head> to set the canonical.

## Implementing rel="canonical"

- Add <link rel="canonical" href="..."> inside the <head> of each duplicate page, pointing to the canonical page; it is only accepted in the <head>, so keep at least the <head> valid HTML.
- Add a self-referential rel="canonical" to the canonical page itself.
- Use absolute URLs (e.g. https://www.example.com/dresses/green/green-dress.html) rather than relative paths, because relative paths can cause problems later, such as when a test site is crawled unintentionally.
- For non-HTML files such as PDFs, send a Link HTTP header with rel="canonical" (using absolute URLs); this is supported for web search results only.
- Choose either the HTML element or the HTTP header and stay with it; using both is supported but more error prone because the two can point to different URLs.
- Avoid putting hreflang, lang, media or type attributes on rel="canonical" links, as those are not used for canonicalization; use rel="alternate" hreflang for language and country variants.
- If the canonical page has a separate mobile URL, add a rel="alternate" link with a media attribute pointing to the mobile version, alongside the canonical link.

## Sitemaps and redirects

- Pick one canonical URL per page and list only those in your sitemap; Google treats listed URLs as canonical suggestions and decides duplicates based on content similarity.
- Use redirects to remove existing duplicates, for example redirecting alternative hostnames or paths (/home, home.example.com, www) to a single chosen URL.
- Prefer HTTP (server-side) redirects for the quickest effect; all permanent redirect methods have the same effect on Google Search, but detection time can differ.

## Best practices and mistakes to avoid

- Do not use robots.txt for canonicalization, because disallowed URLs may still be indexed without their content.
- Do not use the URL removal tool for canonicalization, because it hides all versions of a URL from Search.
- Do not use noindex to choose between duplicates within a site, because it blocks the page completely; use rel="canonical" instead.
- Do not give conflicting canonical signals for the same page, such as one URL in the sitemap and a different one in rel="canonical".
- Do not specify a URL fragment as canonical, as Google generally does not support fragments.
- Link internally to the canonical URL rather than a duplicate, so your preference is consistent.
- With client-side JavaScript rendering, specify the canonical in the HTML source and ensure JavaScript does not change it; if you cannot set it in the HTML, omit it there and set it only with JavaScript.

## HTTPS and hreflang signals

- Serve canonical pages over HTTPS; Google prefers HTTPS over HTTP unless there are issues like an invalid SSL certificate, insecure dependencies (other than images), redirects to or through HTTP, or a rel="canonical" pointing to HTTP.
- Reinforce HTTPS preference by redirecting HTTP to HTTPS, adding a rel="canonical" from HTTP to HTTPS, or implementing HSTS.
- Avoid bad TLS/SSL certificates and HTTPS-to-HTTP redirects, because they make Google strongly prefer HTTP and HSTS cannot override this.
- Do not list HTTP versions of pages in your sitemap or hreflang annotations instead of the HTTPS versions.
- Make sure the SSL/TLS certificate matches the full site host (or is a suitable wildcard certificate), not a different host variant.
- Include all localized versions in reciprocal hreflang clusters, because Google prefers URLs in hreflang clusters as canonicals and may favor cluster members over a page left out.
- When using hreflang, specify a canonical in the same language, or the best possible substitute language if none exists.

Source: https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls
