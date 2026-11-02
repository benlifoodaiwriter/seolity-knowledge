---
title: How to optimize Interaction to Next Paint (INP)
lang: en
topic: site-architecture
tags: site-architecture, core-web-vitals, performance, technical, inp, javascript, rendering
sources: https://web.dev/articles/optimize-inp
updated: 2026-11-02
generated: knowledge-builder
---

# How to optimize Interaction to Next Paint (INP)

Interaction to Next Paint (INP) is a stable Core Web Vital that measures a page's responsiveness across all interactions in a visit. This guidance explains how to find slow interactions in field and lab data and how to reduce input delay, processing duration and presentation delay. Improving INP is iterative and directly affects user experience.

## Measure and set targets

- Aim for an INP of 200 milliseconds or less, because this is the threshold for a good user experience.
- Evaluate INP at the 75th percentile of page loads, segmented across mobile and desktop, because that is how to judge whether most users hit the target.
- Start with field data from a Real User Monitoring (RUM) provider where possible, because it shows which interaction caused the INP value, whether it happened during or after load, and the interaction type (click, keypress, tap).
- Use PageSpeed Insights to view Chrome User Experience Report (CrUX) data if you have no RUM provider, but supplement it with a RUM solution because CrUX lacks the context needed to analyze issues.
- Treat INP as relevant even on text-and-image pages with few interactive elements; a high INP at any site puts the user experience at risk.

## Diagnose slow interactions in the lab

- Move to lab testing once field data suggests slow interactions, so you can reproduce and diagnose them manually before optimizing.
- If you have no field data, test common user flows and interact with the page during load, because the main thread is often busiest then.
- Check which frame an interaction occurs in, because each <iframe> has its own main thread while INP is reported at the page level including iframes.
- Break each interaction into input delay, processing duration and presentation delay, because the sum is the total latency and each part can be optimized separately.
- Measure the subparts across all event entries emitted within the same frame (for example pointerup, mouseup and click), as the web-vitals JavaScript library does, to correctly locate where the delay occurs.

## Reduce input delay

- Reduce input delay to a minimum so event callbacks can start running as soon as possible.
- Look for main-thread activity as a cause of input delay, such as script loading, parsing and compiling, fetch handling, timer functions, and overlapping interactions.
- Reduce long tasks during page load, because a page that has rendered may not be finished loading and users may interact with it early.
- Be aware that script evaluation (parsing, compiling to bytecode, executing) can create long tasks that delay responses to interactions, especially for large scripts.

## Optimize event callbacks

- Do as little work as possible inside event callbacks, because processing duration is a direct part of interaction latency.
- Break up remaining callback work into separate tasks so it does not become a long task that blocks the main thread; setTimeout runs its callback in a new task and can be wrapped in a helper for yielding.
- Yield to the main thread often, because yielding indiscriminately is better than not yielding at all.
- Run only the logic needed for the next visual update in the callback and defer everything else to a later task, so rendering is not blocked by non-critical code (for example, in a text editor update the text box immediately and defer word count, spell check and saving).
- Defer non-critical work by calling setTimeout inside a requestAnimationFrame() callback, which works in all browsers to keep that code from blocking the next frame.
- Avoid layout thrashing (forced synchronous layout) by not updating styles in JavaScript and then reading style-dependent values in the same task, because it forces synchronous layout work the browser could otherwise do later.

## Minimize presentation delay

- Keep the DOM small, because rendering work grows with DOM size and large DOMs make both initial render and post-interaction updates more expensive.
- Flatten the DOM or add to it during user interactions to keep the initial DOM small, while recognizing that these techniques may only go so far for some pages.
- Consider the CSS content-visibility property to lazily render off-screen elements, which can lower rendering time during load and interactions and improve INP.
- Avoid rendering large amounts of HTML with JavaScript on the client, because the browser does not yield until it has finished parsing and rendering that HTML, delaying the next frame.
- Prefer server-sent HTML where practical, because the browser streams, incrementally parses and renders it and implicitly yields during page load.
- Understand that single-page application (SPA) patterns incur JavaScript processing cost plus uninterrupted parsing and rendering, while small amounts of client-side HTML rendering after interactions are generally fine.

## Maintain INP over time

- Treat INP optimization as an iterative process, because fixing one slow interaction often reveals others, especially on highly interactive sites.
- Repeat the measure, diagnose and optimize process when you add new features, since new interactions may introduce new responsiveness problems.

Source: https://web.dev/articles/optimize-inp
