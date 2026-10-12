---
title: Google image SEO best practices
lang: en
topic: images
tags: images, accessibility, alt text, image sitemap, responsive images, structured data, og:image, page speed
sources: https://developers.google.com/search/docs/appearance/google-images
updated: 2026-10-12
generated: knowledge-builder
---

# Google image SEO best practices

This guidance explains how to help Google discover, index and display images in Google Images, Discover and text result images. It covers HTML embedding, sitemaps, formats, speed, metadata, alt text and landing page optimization, which together determine whether and how images appear in search.

## Help Google discover images

- Embed images with standard HTML <img> elements (src attribute, including when nested in <picture>) because Google finds images this way and does not index CSS background images.
- Avoid using CSS background-image for images you want indexed; use <img src="..." alt="..."> instead.
- Submit an image sitemap to expose images Google might not otherwise discover.
- In image sitemaps, <image:loc> may point to other domains, so you can host images on a CDN. If you use a CDN, verify ownership of the CDN domain in Search Console so Google can report crawl errors.

## Responsive images and formats

- When using srcset or <picture>, always include a fallback <img> with a src attribute because some browsers and crawlers do not understand those features.
- Use srcset to offer different versions of the same image for different screen sizes, and the <picture> element with <source> items to serve newer formats with graceful degradation.
- Use a supported format for images in img src: BMP, GIF, JPEG, PNG, WebP, SVG or AVIF, and make the file extension match the file type.
- Use Data URI inlined images (Base64 in src) sparingly because they can considerably increase page size.

## Speed and quality

- Serve sharp, high-quality images because they are more appealing in result thumbnails and can increase traffic; avoid blurry or unclear images.
- Apply current image optimization and responsive image techniques because images are often the largest part of page size and slow pages down.
- Analyze site speed with PageSpeed Insights and test with a slow network connection emulator.
- Reference a shared image with the same URL across pages so Google can cache and reuse it, which helps crawl budget on larger sites.

## Specify a preferred image

- Indicate your preferred image with schema.org primaryImageOfPage (URL or ImageObject), or with an image property attached to the main entity via mainEntity or mainEntityOfPage, or with the og:image meta tag, since Google's preview image selection is automated.
- Choose a preferred image that is relevant to and representative of the page.
- Avoid generic images (such as a site logo) or images containing text as the preferred image in schema.org markup or og:image.
- Avoid images with extreme aspect ratios (too narrow or too wide) and use a high resolution when possible.

## Filenames, alt text and context

- Place images near relevant text on pages relevant to the image subject, because Google derives subject information from page content, captions and image titles.
- Use short, descriptive filenames (my-new-black-kitten.jpg) and avoid generic ones like image1.jpg, pic.gif or IMG00023.JPG; consider automating naming for sites with thousands of images.
- When localizing images, translate the filenames too, and follow URL encoding guidelines if using non-Latin or special characters.
- Always write alt text, as it is the most important image metadata, helps Google understand the image and improves accessibility for screen reader and low-bandwidth users.
- Write useful, information-rich alt text in context of the page, using keywords appropriately; avoid stuffing keywords into alt because it harms user experience and may be seen as spam. Prefer 'Dalmatian puppy playing fetch' over 'puppy' or a keyword list.
- Alt text also serves as anchor text when an image is used as a link.
- For inline <svg>, provide an accessible name with a <title> element referenced via aria-labelledby.

## Titles, snippets and structured data

- Write good page titles and meta descriptions following Google's title link and snippet guidelines, since they influence how the result is displayed.
- Add structured data so images can appear in rich results with a badge in Google Images, and follow the general and type-specific structured data guidelines to stay eligible.
- Include the image property in structured data, as it is required for the badge and rich result in Google Images.

## Controlling image display

- To opt out of inline linking of full-size images in Google Images, check the HTTP referrer header and, for requests from a Google domain, reply with a 200 or 204 status code with no content; Google will show a thumbnail generated at crawl time. This is not considered cloaking.
- Alternatively, prevent the image from appearing in search results entirely if you do not want it shown.
- Make sure Google understands the nature of your site and label pages for SafeSearch when appropriate so filters can be applied correctly.

Source: https://developers.google.com/search/docs/appearance/google-images
