---
title: Tell Google about localized versions of your page (hreflang)
lang: en
topic: site-architecture
tags: site-architecture, hreflang, international, x-default, sitemap, localization
sources: https://developers.google.com/search/docs/specialty/international/localized-versions
updated: 2026-10-19
generated: knowledge-builder
---

# Tell Google about localized versions of your page (hreflang)

Explains how to signal language and regional page variants to Google using hreflang via HTML, HTTP headers, or XML sitemaps. Correct, reciprocal annotations help Google show users the most appropriate version of a page by language or region.

## When and why to declare alternates

- Do explicitly indicate language- or region-specific versions of a page, because Google may find alternates on its own but explicit annotation is usually better.
- Do add hreflang annotations when only the template (navigation, footer) is translated and the main content stays in one language, as on forums with user-generated content.
- Do add hreflang annotations when you have small regional variations of similar content in one language (e.g. English for US, GB and Ireland), or when content is fully translated into multiple languages.
- Remember that localized versions are only treated as duplicates if the main content stays untranslated.
- Do not rely on hreflang or the HTML lang attribute for Google to detect a page's language, because Google uses its own algorithms for that.

## Choosing an implementation method

- Choose one of three equivalent methods: HTML <link> tags, HTTP Link headers, or an XML sitemap, based on what is most convenient for your site.
- Avoid implementing all three at once, because it gives no benefit in Search and makes maintenance harder.
- Use HTML <link> elements in <head> if you have no sitemap or cannot set HTTP response headers.
- Use HTTP Link headers for non-HTML files such as PDFs.
- Use sitemap <xhtml:link> entries when you prefer to manage annotations centrally in an XML sitemap.

## Core hreflang rules for all methods

- Make every language version list itself and all other language versions; the set of annotations should be identical on every version.
- Use fully qualified alternate URLs including the protocol (https://example.com/foo), not //example.com/foo or /foo.
- Alternate URLs may be on different domains; subdomain or path names such as en-gb are not used by Google to determine the target audience, so map the audience explicitly with hreflang.
- Make annotations bidirectional: if page X points to page Y, Y must point back to X, otherwise the tags are ignored or misinterpreted.
- If maintaining full bidirectional sets is hard, you may omit some languages on some pages, but always link newly added language pages bidirectionally to your originating/dominant language versions.
- When you have several same-language pages for different locales (en-IE, en-CA, en-AU), also provide a generic catchall page for that language (e.g. en), which can be one of the specific pages.

## HTML implementation details

- Place <link rel="alternate" hreflang="lang_code" href="url_of_page" /> elements inside a well-formed <head>, one per variant including the page itself.
- Validate the rendered page with an HTML validator to confirm the link tags are actually within <head>.
- Do not combine hreflang with other attributes such as media in a single <link> tag.

## HTTP header and sitemap implementation details

- In a Link: header, give each URL in < > with rel="alternate" and hreflang, comma-separated, for every version including the requested one; return the same header for every version.
- In a sitemap, declare xmlns:xhtml="http://www.w3.org/1999/xhtml" and create a <url> with a <loc> for each page.
- Give each <url> child <xhtml:link rel="alternate" hreflang="..." href="..."/> entries listing every variant including itself; ordering does not matter but keeping it consistent helps checking.
- Host the sitemap in a directory that covers its URLs, because a sitemap can only contain descendant URLs of its directory, and follow general sitemap guidelines.

## Language and region codes

- Use hreflang values of an ISO 639-1 language code optionally followed by an ISO 3166-1 Alpha 2 region code (e.g. en-GB); uppercase region codes follow convention though values are case-insensitive.
- Never specify a region code alone, because the first code is the language (e.g. use nl-BE, not be, which is Belarusian).
- Use a language code alone (e.g. de) when content is independent of region.
- Use ISO 15924 script codes when needed (zh-Hant, zh-Hans, optionally with region like zh-Hans-US); for zh-TW the script is derived automatically.
- Avoid codes outside ISO 639-1 and ISO 3166-1 Alpha 2 such as es-419, and avoid reserved region codes like EU, UN or UK, which Google ignores.

## x-default fallback

- Add hreflang="x-default" as a fallback for users whose language settings match none of your versions.
- Point x-default at a language/country selector or auto-redirecting home page, since it was designed for those and works best there.
- Do not specify a language code for x-default; add it as an extra link alongside the existing hreflang annotations.

## Troubleshooting

- Check for missing return links first, the most common hreflang mistake.
- Verify all language and region codes are valid and in the correct ISO formats.
- Use third-party tools such as Aleyda Solis's hreflang tags generator or Merkle's hreflang testing tool to generate or validate tags (not maintained by Google).

Source: https://developers.google.com/search/docs/specialty/international/localized-versions
