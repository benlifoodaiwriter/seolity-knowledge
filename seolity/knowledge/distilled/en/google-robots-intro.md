---
title: Introduction to robots.txt
lang: en
topic: site-architecture
tags: site-architecture, robots, technical, crawling, indexing, noindex
sources: https://developers.google.com/search/docs/crawling-indexing/robots/intro
updated: 2026-10-19
generated: knowledge-builder
---

# Introduction to robots.txt

A robots.txt file tells crawlers which URLs they may access, mainly to manage crawl traffic and avoid overloading a site. It is not a way to keep pages out of Google Search, so choosing the right mechanism (robots.txt, noindex or password protection) matters for both crawl efficiency and visibility.

## What robots.txt is for

- Use robots.txt mainly to manage crawler traffic and avoid overloading your server with requests, not as a way to keep a page out of Google.
- Use robots.txt for web pages (HTML, PDF and other readable non-media formats) when you think your server could be overwhelmed by Google's crawler, or to avoid crawling unimportant or similar pages.
- If you use a CMS such as Wix or Blogger, check for a search settings page or similar visibility option, because you may not need to (or be able to) edit robots.txt directly.
- To hide or unhide a page on a CMS, look up your CMS's instructions for changing page visibility in search engines.

## Keeping pages out of Google Search

- Do not rely on robots.txt to hide web pages (including PDFs and other text-based formats) from Google Search results, because Google can still index the URL without visiting the page if other pages link to it with descriptive text.
- To keep a page out of search results, use noindex (meta tag or response header) or password-protect the page, or remove the page entirely.
- Understand that a page blocked by robots.txt can still appear in results as a URL without a description, and anchor text from links pointing to it may also show.
- If a blocked page shows up in search results without a description and you want that fixed, remove the robots.txt entry blocking it; if you want it hidden completely, use another method such as noindex.
- Be careful when combining multiple crawling and indexing rules, because some rules can counteract others (for example, a robots.txt block can stop crawlers from seeing a noindex).

## Media and resource files

- Use robots.txt to prevent image, video and audio files from appearing in Google Search results, knowing it will not stop other pages or users from linking to those files.
- Block resource files (images, scripts, styles) in robots.txt only if pages loaded without them are not significantly affected.
- Do not block resources that Google needs to understand a page, because Google will not analyze pages well if they depend on those blocked resources.
- Remember that images, videos, PDFs and other non-HTML files embedded in a blocked page are also excluded from crawling unless other crawlable pages reference them.

## Limitations of robots.txt

- Do not treat robots.txt as an enforcement mechanism: compliance is up to each crawler, and some crawlers may ignore it.
- To keep sensitive information secure from crawlers, password-protect private files on your server instead of relying on robots.txt.
- Check the proper syntax for each crawler you address, because different crawlers may interpret rules differently and some may not understand certain instructions.
- Remember that Google will not crawl or index content blocked by robots.txt, but it may still index a disallowed URL that is linked from other sites.

Source: https://developers.google.com/search/docs/crawling-indexing/robots/intro
