---
title: Link best practices for Google: crawlable links, anchor text, internal and external links
lang: en
topic: internal-linking
tags: internal-linking, site-architecture, anchor-text, crawlability, nofollow, external-links
sources: https://developers.google.com/search/docs/crawling-indexing/links-crawlable
updated: 2026-10-12
generated: knowledge-builder
---

# Link best practices for Google: crawlable links, anchor text, internal and external links

Google uses links as a signal of page relevancy and to discover new pages to crawl. This guidance explains how to build crawlable links, write descriptive anchor text, cross-reference internal content, and handle external links with the right rel attributes.

## Make links crawlable

- Use <a> elements with an href attribute for links, because Google can generally only crawl links in that format and most other formats are not parsed or extracted.
- Avoid links that depend on script events, such as <a onclick="goto('https://example.com')"> without an href, <span href="..."> or <a routerLink="...">, because Google cannot reliably extract URLs from them.
- Make sure the href resolves to a real web address that crawlers can request, such as /products or /products.php?id=123. Avoid javascript: URLs like href="javascript:goTo('products')", because Google may not resolve them.
- Links inserted dynamically with JavaScript are crawlable as long as they use the standard <a href> markup.
- Extra attributes such as class or onclick on an <a> element with a valid href do not stop the link from being parsed.

## Place anchor text correctly

- Put the anchor text between the opening and closing <a> tags of a crawlable link so it tells people and Google what the target page is about.
- Avoid empty links such as <a href="https://example.com"></a>, because they provide no anchor text.
- Treat the title attribute only as a fallback, since Google can use it as anchor text when the <a> element is empty.
- For image links, add descriptive alt text on the img element, because Google uses it as the anchor text. Avoid an empty alt on an image that is the only content of a link.
- If JavaScript inserts anchor text, use the URL Inspection Tool to confirm it is present in the rendered HTML.

## Write good anchor text

- Write anchor text that is descriptive, reasonably concise, and relevant to both the page it sits on and the page it links to, so it sets reader expectations.
- Avoid generic anchor text such as "click here", "read more", "website" or "article", because it says nothing about the destination.
- Test anchor text by reading it out of context. If you cannot tell what the target page is about, make it more descriptive.
- Avoid overly long anchor text that wraps whole sentences. Link only the words that describe the target.
- Write naturally and do not cram related keywords into anchor text, because keyword stuffing violates Google's spam policies. If it feels forced, it is probably too much.
- Give links context, since the words before and after a link matter. Avoid chaining links right next to each other, because readers cannot tell them apart and each link loses surrounding text.

## Internal linking

- Make sure every page you care about is linked from at least one other page on your site so people and Google can find it.
- Use descriptive anchor text on internal links to help people and Google understand your site and discover other pages.
- Link in context to other resources on your site that help readers understand the current page.
- There is no ideal number of links per page, but if a page seems to have too many, it probably does.

## External links

- Link to other sites when it makes sense, for example to cite sources, because external links can help establish trustworthiness.
- Give readers context about what to expect from an external link through the surrounding text and anchor text.
- Use nofollow only for sources you do not trust, and not on every external link on the site.
- Qualify paid links with rel="sponsored" or nofollow.
- Add rel="ugc" or nofollow to links that users can insert, such as in forums or Q&A sections.

Source: https://developers.google.com/search/docs/crawling-indexing/links-crawlable
