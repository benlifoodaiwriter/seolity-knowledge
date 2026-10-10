---
title: Google SEO Starter Guide: On-Page Fundamentals and Site Organization
lang: en
topic: on-page
tags: on-page, content, site-architecture, title-links, snippets, images, internal-linking, canonical
sources: https://developers.google.com/search/docs/fundamentals/seo-starter-guide
updated: 2026-10-10
generated: knowledge-builder
---

# Google SEO Starter Guide: On-Page Fundamentals and Site Organization

Summarizes Google's starter guidance for helping search engines find, crawl and understand a site, and for making pages useful to users. It covers crawl visibility, URL structure, duplicate content, content quality, links, titles, snippets, images and video, and lists common SEO myths not worth prioritizing.

## Crawlability and indexing checks

- Check whether Google already has your site indexed with the site: search operator before doing discovery work, because you may not need to do anything.
- Make sure Google can access the same resources as a user's browser, including CSS and JavaScript. Hiding them can prevent Google from understanding pages and ranking them for target terms.
- Use the URL Inspection Tool in Search Console to check how Google sees a page.
- If page content varies by user location, confirm you are satisfied with what Google sees from its crawler location, which is generally the US.
- Help Google discover pages through links from other pages, and consider submitting a sitemap listing the URLs you care about. A sitemap is optional, and many CMSes generate one automatically.
- Use Google's supported methods to block files, directories or whole sites from search if you do not want them to appear in results.
- Allow time to assess changes: some take hours, others months. Generally wait a few weeks before judging results, then iterate if needed.

## URL structure and site organization

- Use descriptive URLs with words useful to users (for example /pets/cats.html) rather than random identifiers, because URL words can appear as breadcrumbs in results.
- Group topically similar pages in directories, especially on sites with more than a few thousand URLs, because it helps Google learn how often each directory's content changes and crawl accordingly.
- Treat a logical structure as a long-term benefit, not an urgent task: search engines will likely understand your pages as they are now, so do not drop everything to reorganize.
- For ecommerce and other large sites, a good URL structure matters more because they tend to be larger.

## Duplicate content and canonicalization

- Aim for each piece of content to be reachable through a single URL, because several pages with the same information confuse users and waste crawling resources.
- Redirect non-preferred URLs to the URL that best represents the content when you have multiple pages with the same information.
- Use the rel="canonical" link element when you cannot redirect.
- Do not fear a duplicate content penalty: duplicate content on multiple URLs is inefficient but does not cause a manual action. Copying others' content is a different matter.
- If you do not canonicalize, Google will try to choose a canonical URL automatically, so treat this as a refinement rather than a crisis.

## Content quality and links

- Prioritize compelling, useful content, as it likely influences search presence more than any other suggestion in the guide.
- Write text that is easy to read and well organized: write naturally, avoid spelling and grammar mistakes, and break long content into paragraphs and sections with headings.
- Create unique content from your own knowledge instead of copying or rehashing what others have published.
- Keep content up to date by revisiting published pages, updating them, or deleting them if no longer relevant.
- Write helpful, reliable, people-first content, and provide expert or experienced sources to show expertise.
- Anticipate the different terms that experts and beginners use (for example "charcuterie" vs "cheese board"), but do not worry about covering every variation because Google's language matching can relate pages to queries without exact terms.
- Avoid ads or interstitials that distract users or make the content difficult to read or use.
- Write link text (anchor text) that tells users and search engines what the linked page contains.
- Link to relevant resources, internal and external, for context. Only link to external sites you trust, or add nofollow or a similar annotation to links you cannot vouch for.
- Make your CMS automatically add nofollow or a similar annotation to every link in user-generated content such as comments and forum posts.

## Title links and snippets

- Write titles that are unique to the page, clear and concise, and accurate about the page's contents, because the <title> element is a key source for the title link in search results.
- Consider including the site or business name, location, and what the page offers in the title, where relevant.
- Check that your CMS turns the titles you write into a <title> element, as most do.
- Remember that snippets are sourced from the page's actual content, so the page text controls the snippet, though the meta description is occasionally used.
- Write meta descriptions that are short, unique to each page, and include the page's most relevant points.

## Images and video

- Use sharp, clear, high-quality images so users can tell whether an image matches what they want.
- Place images near text relevant to them, such as the yarn shop photo in the section describing that shop, so Google can understand the image in context.
- Add short, descriptive alt text through the alt attribute of the img element, or through the CMS image description field, explaining how the image relates to your content.
- For pages primarily about a video, embed the video on a standalone page near relevant text.
- Write descriptive text in video titles and description fields, applying the same best practices as for page titles.

## Promotion and myths to deprioritize

- Promote new content through social media, community engagement, advertising, newsletters (with permission) and word of mouth, and list your URL on offline materials such as business cards.
- Avoid over-promoting, because audiences get fatigued and search engines may see some practices as manipulation of search results.
- Do not use the keywords meta tag for Google, because Google Search does not use it.
- Avoid keyword stuffing, since repeating the same words excessively tires users and violates Google's spam policies.
- Choose domain names and URL paths for business reasons: keywords in them have hardly any ranking effect beyond appearing in breadcrumbs, and the TLD matters only when targeting a specific country.
- Do not target a word count: content length alone does not matter for ranking. Varying your wording naturally gives more chances to match queries.
- Choose subdomains or subdirectories based on what suits your business, not on a supposed SEO advantage.
- Do not obsess over heading order or count: semantic order helps screen readers but does not matter to Google Search, and there is no ideal number of headings. If a page seems to have too many, it probably does.
- Do not treat E-E-A-T as a ranking factor, and do not treat PageRank as the only signal, since Google uses many ranking signals.

Source: https://developers.google.com/search/docs/fundamentals/seo-starter-guide
