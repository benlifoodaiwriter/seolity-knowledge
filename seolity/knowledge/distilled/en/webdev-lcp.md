---
title: Optimize Largest Contentful Paint (LCP)
lang: en
topic: images
tags: images, core-web-vitals, performance, lcp, fetchpriority, ttfb
sources: https://web.dev/articles/optimize-lcp
updated: 2026-10-26
generated: knowledge-builder
---

# Optimize Largest Contentful Paint (LCP)

LCP measures how quickly the largest image or text block in the viewport renders, with a good value being 2.5 seconds or less for at least 75% of page visits. Improving it means optimizing the whole loading chain: TTFB, resource load delay, resource load duration and element render delay. This matters especially for hero images and other LCP images on WordPress and WooCommerce pages.

## Measure LCP with real-user data first

- Aim for an LCP of 2.5 seconds or less for at least 75% of page visits, because this is the threshold for a good user experience.
- Look at real-user (field) data from CrUX, PageSpeed Insights or a RUM tool before acting, because lab tools such as Lighthouse may not represent what actual users experience.
- If Lighthouse and CrUX disagree, trust CrUX as the more accurate picture of user experience, and check that the CrUX data is for the page rather than the whole origin before acting on it.
- Compare the four PageSpeed Insights CrUX views (mobile/desktop, URL/origin) to tell whether an LCP issue is page-specific, site-wide or device-specific.
- Use TTFB and FCP as diagnostic metrics: a large TTFB-to-FCP gap suggests render-blocking assets or heavy client-side rendering, and a large FCP-to-LCP gap suggests the LCP resource is not immediately discoverable or the browser is busy with other work.
- Supplement CrUX with your own RUM data when a page lacks enough traffic for page-level CrUX data.

## Break LCP into four subparts

- Identify the LCP element and its resource with PageSpeed Insights, Chrome DevTools or WebPageTest, then match it on the network waterfall alongside the initial HTML document.
- Split LCP into TTFB, resource load delay, resource load duration and element render delay, because these add up to the full LCP time with no gaps or overlap.
- Optimize all four subparts, not just one, because speeding up one part (for example compressing an image) can simply shift the saved time to another part such as element render delay.
- Use the guideline of roughly 40% TTFB, under 10% resource load delay, roughly 40% resource load duration and under 10% element render delay; treat any time spent in the two 'delay' parts as the main opportunity.
- Evaluate the subparts relative to each other rather than converting the percentages into absolute times.

## Eliminate resource load delay for the LCP image

- Make the LCP resource start loading at about the same time as the first resource on the page; if it starts later, there is room for improvement.
- Keep the LCP image discoverable in the initial HTML: use an <img> with src or srcset present in the markup rather than adding it with JavaScript.
- Avoid lazy-loading libraries that hide the LCP image's src or srcset in attributes like data-src or data-srcset, because the browser cannot discover the image until the script runs.
- If the LCP image is only referenced from external CSS or JavaScript (such as a CSS background image), preload it with <link rel="preload" fetchpriority="high" as="image" href="...">.
- Never set loading="lazy" on the LCP image, because it always adds unnecessary load delay and hurts LCP.
- Add fetchpriority="high" to the <img> likely to be the LCP element, but use it on only one or two images, since more makes the hint unhelpful.
- Use fetchpriority="low" on images that are early in the HTML but not visible at startup, such as non-visible carousel slides, and verify the effect in DevTools and with lab and field tests.
- Host critical LCP resources on the same origin as the HTML document when possible, because a different origin requires an extra connection before loading can start.

## Eliminate element render delay

- Ensure the LCP element can render as soon as its resource finishes loading; check for blocking stylesheets, synchronous scripts, elements hidden by A/B testing code, and long main-thread tasks.
- Reduce the size of render-blocking stylesheets so they are smaller than the LCP resource: remove unused CSS, defer non-critical CSS, and minify and compress critical CSS.
- Inline a stylesheet only if it is small, because inlined content cannot be cached on later page loads.
- Avoid synchronous scripts (without async or defer) in the <head>; if code must run early, inline it only when it is very small.
- Use server-side rendering or static site generation/prerendering where possible so images are discoverable in the HTML and content does not wait on extra JavaScript; prerendering is generally the better choice for performance if the architecture allows.
- Break up long JavaScript tasks and avoid loading large scripts that block the main thread, because browsers render images on the main thread and a blocked thread delays the LCP element.

## Reduce resource load duration

- Reduce the LCP resource size by serving the optimal image size, using modern image formats such as AVIF or WebP, compressing images, and reducing web font size.
- Use a CDN to bring resources geographically closer to users; image CDNs also automatically reduce image size.
- If using a third-party image CDN, prefer proxying it through your own origin, or preconnect to the CDN origin, to limit the extra connection cost.
- Avoid giving high fetchpriority to many resources or loading many resources at once, because network contention can slow the LCP resource.
- Serve resources with an efficient cache-control policy so repeat visits load them from cache.
- If the LCP element is text using a web font, set font-display to a value other than auto or block so text is visible during load.
- Inline a small LCP resource as a data URL only with care, because it cannot be cached and may add decode cost and render delay.
- Check real-user data before focusing on load duration, since it is often not the biggest LCP bottleneck.

## Reduce time to first byte

- Deliver the initial HTML as fast as possible, because nothing on the frontend can happen before the first byte arrives and TTFB affects every later metric.
- Minimize the number of redirects visitors must wait through, such as those from advertisements or shortened links.
- Avoid unique URL parameters (for example for analytics) that prevent CDN edge caching and force requests back to the origin server, even when the page content is identical.
- Monitor LCP subparts in JavaScript with the Largest Contentful Paint, Navigation Timing and Resource Timing APIs, or the attribution build of the web-vitals library, if your tools do not already report them.

Source: https://web.dev/articles/optimize-lcp
