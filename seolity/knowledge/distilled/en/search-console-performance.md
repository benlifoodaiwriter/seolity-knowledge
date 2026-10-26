---
title: Google Search Console Performance Report: Overview and Basic Setup
lang: en
topic: reporting
tags: reporting, ctr, experiments, search-console, performance-report, metrics
sources: https://support.google.com/webmasters/answer/7576553?hl=en
updated: 2026-10-26
generated: knowledge-builder
---

# Google Search Console Performance Report: Overview and Basic Setup

This guidance explains how to configure and read the Search Console Performance report for Google Search results, including metrics, dimensions, date ranges, search types and time granularity. Understanding how data is aggregated and presented helps you avoid misreading numbers and draw correct conclusions about traffic, queries and click-through rate.

## Purpose of the Performance report

- Use the Performance report to see how search traffic changes over time, where it comes from, and which queries are most likely to show your site.
- Use the Queries data to learn which searches bring traffic and feed that into your SEO improvements.
- Use the report to find pages with the highest and lowest click-through rate from Google results, so you can prioritize pages that underperform.
- Remember the default view covers clicks and impressions for the past three months; change metrics, dimensions and date range when you need a different view.

## Metrics and how to interpret them

- Toggle the metrics above the chart to show only the ones you need: Clicks, Impressions, CTR and Average position.
- Read CTR as clicks divided by impressions, so compare it alongside impressions rather than in isolation.
- Interpret Average position as the position of the topmost result from your site. In the chart it covers the whole site; in the table it applies to the specific URL or grouping shown in that row.
- Do not assume you will see your site when you repeat a listed query yourself, because results depend on the time, place, device and recent history of the searcher.

## Dimensions and search types

- Pick a dimension tab (Queries, Pages, Countries, Devices, Search appearance, Dates) to choose how the table is grouped.
- Use the search type filter to separate Web (text-based), Web (multimodal), Image, Video and News traffic so that you analyze each source individually.
- Treat Web multimodal as traffic from image-based searches such as Google Lens, Circle to Search on Android, uploaded images and Chrome image search.
- Use the date filter to change the period; in the 24-hour view, data points represent hours and include preliminary data.

## Choosing time granularity

- Use Hourly granularity only for the most recent data, since it is available only in the 24-hour view.
- Use Daily granularity to detect issues or traffic spikes (not available in the 24-hour view).
- Use Weekly or Monthly granularity to analyze longer-term trends, because they smooth out fluctuations such as weekends or holidays and help you judge overall growth or decline.

## Reading chart and table data correctly

- Treat the newest data as preliminary, shown as a dotted line on the graph, because it may change within the next few hours.
- Remember the chart aggregates by property, so two results from the same site for one query count as a single impression.
- Know that table aggregation depends on the dimension: Queries, Countries, Devices and Dates are aggregated by property, while Pages and Search appearance are aggregated by page.
- Do not be alarmed if chart totals differ from table totals; this is usually caused by property versus page aggregation.
- Expect the table to be omitted occasionally when it would add no information beyond the chart.

## Sharing and exporting

- Use the Share button to give others access to the current view only; the link does not grant access to other pages of your property or let the user take actions on your property or account.
- Use the export button to download chart and table data for further analysis or reporting.
- Remember that values shown as ~ or - in the report (not available or not a number) appear as zeros in exported data, so account for this when analyzing downloads.

Source: https://support.google.com/webmasters/answer/7576553?hl=en
