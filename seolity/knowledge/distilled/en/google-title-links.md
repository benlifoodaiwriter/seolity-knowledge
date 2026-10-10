---
title: Influencing your title links in Google Search results
lang: en
topic: meta
tags: meta, ctr, serp, title, title-link, h1, og:title
sources: https://developers.google.com/search/docs/appearance/title-link
updated: 2026-10-10
generated: knowledge-builder
---

# Influencing your title links in Google Search results

Title links are often the primary piece of information users rely on when deciding which result to click. Google generates them automatically from several sources, but well-written <title> elements and a clear main heading help it show the title you intend. This guidance covers best practices, how Google builds title links and the common issues it corrects.

## Writing good <title> elements

- Do specify a <title> element on every page of the site, because it is the main source Google uses for the title link.
- Do write descriptive, concise titles. Avoid vague text such as "Home" for a home page or "Profile" for a person's profile page, because it tells users nothing about the content.
- Avoid unnecessarily long or verbose titles. There is no length limit on <title>, but the title link is truncated as needed, typically to fit the device width.
- Avoid keyword stuffing in titles (e.g. "Foobar, foo bar, foobars, foo bars"). A few descriptive terms can help, but repeating the same words makes results look spammy to Google and to users.
- Do write a distinct <title> for each page that describes that page's content. Avoid titling every page with the same text (e.g. "Cheap products for sale"), because users cannot tell the pages apart.
- Avoid long boilerplate titles that differ by only one piece of information. Instead, update titles dynamically to reflect the real content, e.g. mention "video" or "lyrics" only if that page actually has video or lyrics.
- Do not include flight price information in <title> elements, because Google will likely not show prices in title links for flight pages; prices change too quickly to match the landing page.

## Branding titles

- Do put extra descriptive branding text (such as a tagline) only in the home page <title>.
- On other pages, include just the site name at the beginning or end of the <title>, separated by a delimiter such as a hyphen, colon or pipe (e.g. "ExampleSocialSite: Sign up for a new account.").
- Avoid repeating the long brand tagline in every page title, because it looks repetitive when several pages from one site appear for the same query.
- Be aware that for domain-level site names Google may omit the site name from the title link if it duplicates the site name already shown in the search result.

## Making the main title clear

- Do make the main title of the page stand out as the most prominent text, for example with a larger font and by placing it in the first visible <h1> element.
- Avoid giving several headings the same visual weight or heading level, because Google may then use the first heading as the title link.
- Keep visible headings and the <title> consistent, since Google considers the main visual title, heading elements and other large, prominent text when building title links.

## Language and writing system

- Do write the <title> in the same language and writing system (script) as the page's primary content. For example, a Hindi page should have a Hindi title, not an English or Latin-transliterated one.
- Be aware that if the title's language or script does not match the primary content, Google may choose different text as the title link.
- For sites in non-Latin scripts, avoid writing titles in transliterated Latin characters when the page content is in the native script.

## Crawling and indexing considerations

- Be careful about blocking pages with robots.txt. It can stop crawling but may not prevent indexing, for example if Google discovers the URL through links from other sites.
- Be aware that if Google cannot access a page's content, it relies on off-page content such as anchor text from other sites to generate the title link.
- Use the noindex rule, not robots.txt, to prevent a URL from being indexed.

## How Google creates title links and why they get changed

- Know that title links are generated automatically from several sources: <title> elements, the main visual title, heading elements such as <h1>, og:title meta tags, other large and prominent text, other on-page text, anchor text on the page, text in links pointing to the page, and WebSite structured data.
- Fix half-empty titles (e.g. "| Site Name"), because Google will fall back to headings or prominent text to build the title link.
- Update titles for recurring content (e.g. yearly pages), because an obsolete <title> such as "2020 admissions criteria" on a page showing 2021 may be replaced with the date from the visible title.
- Make sure titles accurately reflect the page content, because Google may rewrite titles it judges inaccurate.
- Avoid identical titles across a subset of pages (e.g. TV show seasons without season numbers); include the distinguishing detail yourself rather than relying on Google to detect it.
- After changing titles, expect Google to need to recrawl and reprocess the page, which may take a few days to a few weeks; you can request a recrawl.
- Remember that Google cannot manually change title links for individual sites; if a title link is modified, first check whether the page has one of the listed issues, and consider whether the displayed title may fit the query better.

Source: https://developers.google.com/search/docs/appearance/title-link
