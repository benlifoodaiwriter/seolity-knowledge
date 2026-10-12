---
title: Redirects and Google Search
lang: en
topic: redirects
tags: redirects, site-architecture, 301, 302, canonicalization, site-migration
sources: https://developers.google.com/search/docs/crawling-indexing/301-redirects
updated: 2026-10-12
generated: knowledge-builder
---

# Redirects and Google Search

Redirects tell users and Google that a page has moved. The redirect type you choose (permanent or temporary) signals which URL Google should treat as canonical and show in search results, so choosing the right type and method matters for migrations, URL consolidation and removed pages.

## When to use redirects

- Do use redirects when you move to a new domain, to make the transition as seamless as possible for users and Google.
- Do pick one preferred (canonical) URL when a page is reachable at several URLs (for example https://example.com/home, http://home.example.com or https://www.example.com), and redirect the other URLs to it.
- Do redirect outdated URLs to the correct corresponding pages when merging two websites.
- Do redirect users to a relevant new page when you remove a page.
- Check whether your platform (for example Blogger or Shopify) already provides built-in redirect tools before implementing redirects manually.

## Choosing between permanent and temporary redirects

- Do use permanent redirects when you're sure the redirect won't be reverted, because Google uses them as a signal that the redirect target should be canonical and shows the new target in search results.
- Do use temporary redirects when the move is short-lived, because Google doesn't treat them as a canonicalization signal and generally keeps showing the source page in search results.
- Understand that with a temporary redirect the target page might still be indexed if other canonicalization signals are present.
- Use a temporary redirect when a service is temporarily unavailable to send users to an explanatory page without compromising the original URL in search results.

## Prefer server-side redirects

- Do use server-side redirects whenever possible, because they have the highest chance of being interpreted correctly by Google.
- Use HTTP 301 or 308 for permanent moves and HTTP 302, 303 or 307 for temporary ones.
- Set up server-side redirects through server configuration files (for example .htaccess on Apache) or through server-side scripts such as PHP.
- In PHP, set the redirect headers with header() before anything is sent to the screen, include the Location header and call exit().
- On Apache, use mod_alias (Redirect permanent / Redirect temp) for simple redirects and mod_rewrite (RewriteRule with [R=301]) for more complex ones.
- On NGINX, use return 301 or return 302 inside a location block for simple redirects, and the rewrite rule with permanent or redirect for more complex ones.
- For other web servers, consult your server manager, hoster or the server's documentation.

## Meta refresh redirects

- Use meta refresh redirects only if server-side redirects aren't possible on your platform.
- Use an instant meta refresh (content="0; url=...") when the move is permanent, because Google interprets it as a permanent redirect.
- Avoid a delayed meta refresh (more than 0 seconds) for permanent moves, because Google interprets it as a temporary redirect.
- Place the meta refresh in the <head> element of the HTML, or send it as a Refresh HTTP header from server-side code.

## JavaScript and crypto redirects (last resorts)

- Avoid JavaScript redirects unless server-side or meta refresh redirects are impossible, because Google runs JavaScript in the Web Rendering Service after crawling and rendering may fail, so the redirect might never be seen.
- If you must use a JavaScript redirect, set window.location.href to the target URL in a script block in the HTML head.
- Avoid relying on crypto redirects (a plain link to the new page with a short explanation) to tell search engines content has moved, since not all search engines recognize them as redirects.
- If no other method works, still add a visible link and short explanation pointing users to the new page, and ask your hosting provider about other redirect options first.

## Expectations after redirecting

- Expect Google to track both the redirect source and target; one becomes canonical (depending on signals such as permanent vs. temporary) and the other becomes an alternate name.
- Don't worry if old URLs occasionally still appear in search results after a domain move, since alternate names can show when a query suggests users trust the old URL more.
- Allow time for alternate names to fade away on their own as users get used to the new domain; no action is needed.

Source: https://developers.google.com/search/docs/crawling-indexing/301-redirects
