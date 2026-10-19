---
title: Sitemaps overview: what they do and when you need one
lang: en
topic: site-architecture
tags: site-architecture, sitemap, technical
sources: https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview
updated: 2026-10-19
generated: knowledge-builder
---

# Sitemaps overview: what they do and when you need one

A sitemap is a file listing the pages, videos and other files on a site and their relationships, which helps search engines crawl the site more efficiently. It aids URL discovery but does not guarantee crawling or indexing. Most sites benefit from one, especially large, new or media-heavy sites.

## What a sitemap does

- Use a sitemap to tell search engines which pages and files you consider important, because it helps them crawl your site more efficiently.
- Include useful metadata in the sitemap, such as when a page was last updated and any alternate language versions of the page, because search engines can use this information.
- Do not expect a sitemap to guarantee crawling or indexing of every listed URL, because it only helps search engines discover URLs.
- Use specialized sitemap entries for rich content: video entries can specify running time, rating and age-appropriateness rating; image entries can give the location of images on a page; news entries can give the article title and publication date.

## Check whether your CMS already provides one

- On a CMS such as WordPress, Wix or Blogger, first check whether a sitemap is already available to search engines, because it is likely the CMS has already made one and no extra action is needed.
- Avoid creating a duplicate sitemap before confirming what your CMS already generates.

## When you likely need a sitemap

- Add a sitemap if your site is large, because it is harder to ensure every page is linked from at least one other page and Googlebot may miss new pages.
- Add a sitemap if your site is new and has few external links, because Googlebot finds pages by following URLs from previously crawled pages and may not discover pages nobody links to.
- Add a sitemap if your site has a lot of rich media (video, images) or appears in Google News, because Google can take additional information from sitemaps into account for Search.
- In most cases, provide a sitemap anyway, because most sites benefit from having one.

## When you may not need a sitemap

- You may skip a sitemap if your site is small (about 500 pages or fewer), counting only pages you want to appear in search results.
- You may skip a sitemap if your site is comprehensively linked internally, meaning Googlebot can reach all important pages by following links from the home page.
- You may skip a sitemap if you have few video, image or news files that you want to show in search results, because sitemaps mainly help Google find and understand those file types.

## Keep internal linking sound regardless

- Make sure every important page is reachable through some form of navigation, such as the site menu or links placed on pages, because proper linking lets Google discover most of your site.
- Treat a sitemap as a supplement to internal linking, not a replacement, because it can improve crawling of larger or more complex sites but does not replace good navigation.

Source: https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview
