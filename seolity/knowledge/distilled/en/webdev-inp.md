---
title: How to Optimize Interaction to Next Paint (INP)
lang: en
topic: site-architecture
tags: site-architecture, core-web-vitals, performance, technical, inp, javascript, rendering
sources: https://web.dev/articles/optimize-inp
updated: 2026-10-26
generated: knowledge-builder
---

# How to Optimize Interaction to Next Paint (INP)

Interaction to Next Paint (INP) is a Core Web Vital that measures a page's responsiveness to user interactions. This guidance explains how to find slow interactions in field and lab data, and how to reduce input delay, event callback time and presentation delay so interactions feel fast.

## Targets and measurement

- Aim for an INP of 200 milliseconds or less, because that is the threshold for a good user experience.
- Evaluate INP at the 75th percentile of page loads, segmented across mobile and desktop, so the target holds for most users.
- Remember that INP reflects the longest interaction observed (sometimes ignoring outliers) across a visit, so one slow interaction can set the page's INP.
- Treat INP optimization as iterative: after fixing one slow interaction, expect to find others, especially on highly interactive sites, and repeat the process as new features are added.

## Finding slow interactions

- Start with field data, ideally from a Real User Monitoring (RUM) provider, because it shows which interaction caused the INP value, whether it happened during or after load, and the interaction type (click, keypress, tap).
- If you have no RUM data, use PageSpeed Insights to view Chrome User Experience Report (CrUX) data, but supplement it with a RUM provider or your own RUM solution since CrUX lacks contextual detail.
- Once field data points to slow interactions, reproduce and diagnose them in the lab before attempting fixes.
- When field data is unavailable, test common user flows in the lab and interact with the page during load, when the main thread is often busiest.
- Check which frame an interaction happens in: each <iframe> has its own main thread, and INP is reported at page level including slow interactions in iframes.

## Understand the three interaction subparts

- Break each slow interaction into input delay, processing duration and presentation delay, because their sum is the total interaction latency and each can be optimized separately.
- Measure subparts across all event entries emitted within the same frame (for example pointerup, mouseup and click) to locate where the delay really is; the web-vitals JavaScript library calculates them this way.

## Reduce input delay

- Reduce input delay to a minimum so event callbacks can begin running as soon as possible.
- Look for main-thread activity such as script loading, parsing and compiling, fetch handling, timer functions, and overlapping interactions as sources of input delay.
- Reduce long tasks caused by script evaluation during page load, because users may interact before the page has finished loading even if it has rendered.
- Remember that fetched JavaScript still needs parsing, compiling to bytecode and execution, and that large scripts can create long tasks that delay responses to interactions.

## Optimize event callbacks

- Do as little work as possible inside event callbacks, because processing duration is a direct part of interaction latency.
- Break up callback work into separate tasks (for example with setTimeout) to prevent long tasks that block the main thread and delay other interactions.
- Yield to the main thread, ideally immediately after the callback logic that updates the UI, so rendering can happen sooner; yielding indiscriminately is still better than not yielding.
- Limit callback code to what is needed to apply the visual update for the next frame, and defer everything else (such as word counts, spell checks and saving) to a later task.
- To defer non-critical work in all browsers, queue a setTimeout inside a requestAnimationFrame() callback so it does not block the next frame.
- Avoid layout thrashing (forced synchronous layout): do not update styles in JavaScript and then read style or layout values in the same task, because it forces synchronous layout work that could have been done later.

## Minimize presentation delay

- Keep the DOM small where possible, because rendering work grows with DOM size and large DOMs make both initial render and post-interaction updates more expensive.
- Reduce DOM size by flattening the DOM or by adding elements during user interactions to keep the initial DOM small, while recognizing these techniques may only go so far.
- Consider the CSS content-visibility property to lazily render off-screen elements and lower rendering work during load and interactions; it takes practice but may improve INP.
- Avoid rendering large amounts of HTML on the client with JavaScript, because the browser does not yield until that HTML is parsed and rendered, which can delay the next frame.
- Prefer server-sent HTML where practical, because streamed HTML is parsed and rendered incrementally and the browser yields automatically during load.
- Be aware of the single-page application (SPA) model's drawback: client-side HTML rendering adds JavaScript processing cost on top of parsing and rendering cost.

Source: https://web.dev/articles/optimize-inp
