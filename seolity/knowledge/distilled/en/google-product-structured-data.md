---
title: Introduction to Product structured data
lang: en
topic: product
tags: product, schema, ecommerce, structured data, merchant listings, product snippets, google merchant center
sources: https://developers.google.com/search/docs/appearance/structured-data/product
updated: 2026-10-10
generated: knowledge-builder
---

# Introduction to Product structured data

Product structured data lets product information such as price, availability, ratings and shipping appear in richer ways in Google Search, Google Images and Google Lens. Choosing the right markup type and supplying as much accurate product data as possible maximizes eligibility for these experiences.

## Choosing the right markup type

- Use product snippets markup on product pages where people cannot directly purchase the product, such as editorial product review pages, because it offers more options for review information like pros and cons.
- Use merchant listings markup on pages where customers can purchase products from you, because it supports detailed product information such as apparel sizing, shipping details and return policy information.
- Review the requirements of both product snippets and merchant listings before deciding, because each has its own enhancements and the more properties you add, the more enhancements your page can be eligible for.
- Add the required merchant listing properties on purchasable product pages, because this generally also makes those pages eligible for product snippets.
- If you sell variants of a product, add product variant structured data so Google can understand which products are variations of the same parent product. Both product snippets and merchant listings support variants.

## Business-level policy markup

- Add merchant return policy structured data to describe your business's return policy or policies, nested under Organization markup.
- Add Loyalty Program structured data to describe any loyalty program you offer, nested under Organization markup.
- Keep policy markup in addition to, not instead of, structured data for the individual products you sell.

## Maximizing rich result enhancements

- Provide as much rich product information as you have, without worrying about which exact experience will use it, because enhancements are shown at the discretion of each experience and may change over time.
- Include customer reviews and ratings to enhance how your search result appears.
- On product review pages, identify pros and cons in the review description so they can be highlighted in search results.
- Share shipping costs, especially free shipping, so shoppers understand the total cost.
- Provide availability data so customers know when a product is in stock.
- Share return information such as the return policy, fees involved in returns, and the number of days customers have to return a product.
- Do not rely on price drop display: Google computes price drops by observing price changes over time and does not guarantee they are shown.

## Where product data can appear

- Expect product data to be eligible for several experiences: product snippets, popular products, shopping knowledge panels, and annotated product images in Google Images. Google Lens is also mentioned as a surface for product information.
- Treat the list of shopping experiences as non-exhaustive, because Google may change or add experiences over time.

## Combining structured data with Merchant Center

- Provide product data through Product structured data on your pages, through Google Merchant Center feeds (opting into free listings in the Merchant Center console), or both.
- Use both on-page structured data and a Merchant Center feed where possible, because this maximizes eligibility for experiences and helps Google correctly understand and verify your data.
- Keep feed data and page markup consistent, because some experiences combine both sources; for example, product snippets may use pricing from your merchant feed if it is missing from on-page structured data.
- Consult the Google Merchant Center feed documentation for additional feed attribute requirements and recommendations.
- Read the Merchant Center data and eligibility requirements if you want to be eligible for the Google Shopping tab.

Source: https://developers.google.com/search/docs/appearance/structured-data/product
