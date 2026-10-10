---
title: Google Search spam policies: what to avoid and how to stay compliant
lang: en
topic: content
tags: content, spam, eeat, google-spam-policies, scaled-content, link-spam, affiliate, redirects, site-reputation
sources: https://developers.google.com/search/docs/essentials/spam-policies
updated: 2026-10-10
generated: knowledge-builder
---

# Google Search spam policies: what to avoid and how to stay compliant

Google's spam policies describe techniques that deceive users or manipulate Search, and violations can lower rankings or remove content from results, through automated systems or manual action. This guidance lists the practices to avoid and the legitimate alternatives (e.g. rel attributes for paid links, value-adding affiliate content, proper redirects) so WordPress and WooCommerce sites stay eligible to appear in results.

## Content quality and scale

- Avoid generating many pages primarily to manipulate rankings. This is scaled content abuse, whether created with generative AI tools, scraping, or other methods; every page must add real value for users.
- Do not scrape or republish content from other sites without adding original content or value. Avoid lightly modifying copied text (synonym swaps, automated rewriting or translation), because this is still treated as abusive scraping.
- Avoid stitching together content from different pages, or sites that merely embed or compile videos, images or other media, unless you add substantial value for users.
- Do not create multiple sites to hide the scaled nature of content.
- If low-value scaled content already exists on your site, exclude it from Search (for example with noindex) rather than leaving it indexable.
- Do not create pages whose text makes little sense to readers but contains search keywords.

## Keyword stuffing, hidden text and cloaking

- Avoid keyword stuffing: do not fill pages with keywords or numbers, lists of cities/regions you want to rank for, phone number lists without value, or unnaturally repeated phrases. Write naturally for readers.
- Do not hide text or links to manipulate search engines. Examples of violations: white text on a white background, text hidden behind an image, text positioned off-screen with CSS, font size or opacity set to 0, or a link on a single tiny character.
- Accordions, tabs, sliders, tooltips and screen-reader-only text that improve user experience are acceptable and do not violate the hidden text policy.
- Avoid cloaking: always show search engines the same content that users see. Never insert text or keywords only when the requesting user agent is a search engine.
- If JavaScript or images make content hard for search engines to access, use the recommended accessibility approaches instead of serving different content.
- Paywalled or gated content is not cloaking if Google can see the full content just as a person with access can and you follow the Flexible Sampling guidance.

## Doorway pages, redirects and misleading behavior

- Avoid doorway abuse: do not build multiple sites, domains or near-duplicate pages (e.g. per city or region) that funnel users to one destination. Prefer a clearly defined, browsable site hierarchy.
- Do not use sneaky redirects that show search engines different content from users, or send some users (e.g. mobile only) to unrelated or spam destinations.
- Use redirects for legitimate purposes: moving to a new address, consolidating several pages into one, or sending logged-in users to an internal page. Judge a redirect by whether it intends to deceive users or search engines.
- Do not build sites or tools that promise functionality or services (fake generators, PDF merge, timers, dictionaries) but deliver deceptive ads or nothing.
- Avoid malicious practices: do not host malware or unwanted software (check downloadable files you host unknowingly) and never hijack the back button by manipulating browser history.
- Do not impersonate businesses, fake official support pages or display false contact information.

## Links and sponsored content

- Do not buy or sell links for ranking purposes. This includes money, goods or services in exchange for links, or sending a product in exchange for an article with a link.
- Avoid excessive link exchanges, partner pages created only for cross-linking, and automated programs or services that create links to your site.
- Qualify paid, sponsored or advertising links with rel="sponsored" or rel="nofollow" on the <a> tag. Buying and selling links for advertising is acceptable when they are qualified this way.
- Avoid advertorials, guest posts or press releases that include links passing ranking credit or keyword-optimized anchor text.
- Do not use low-quality directory or bookmark links, keyword-rich or hidden links in distributed widgets, widely distributed footer or template links, or optimized links in forum comments and signatures.
- Do not require a link in terms of service or contracts without allowing the content owner to qualify the outbound link.

## Affiliate, WooCommerce and third-party content

- Avoid thin affiliation: do not publish affiliate pages whose product descriptions and reviews are copied from the merchant without original content or added value.
- Add value to affiliate and product pages with extra price information, original product reviews, rigorous testing and ratings, product or category navigation, and product comparisons. Participating in an affiliate program is not itself a problem.
- Avoid cookie-cutter affiliate sites or templates that replicate the same content across a site, multiple domains or languages.
- Do not host third-party content on your established site mainly to benefit from its ranking signals (site reputation abuse). Third-party content is fine when it is genuinely integrated and edited by the host.
- Integrate third-party or partner sections with the main site: consistent design and UX, comparable quality, clear authorship and editorial responsibility, disclosure of commercial nature, navigation from main sections, and a contact point for problems.
- Avoid publishing unauthored, undisclosed affiliate articles that are unlinked from site sections, differ in quality from the rest of the site, or duplicate content found on other sites.
- Syndicated news, press releases, user-generated content, editorial columns, and affiliate links or ad units that are treated appropriately are not inconsistent with the site reputation policy.

## Site security and user-generated spam

- Protect the site against hacking. Watch for injected code, injected spam or phishing pages, hidden links or text added via CSS/HTML, cloaking, and redirects that only trigger for visitors arriving from search results.
- Check for hacks by looking beyond existing pages: hackers may add new pages while old pages look normal, and redirects may depend on referrer, user agent or device.
- Prevent abuse of public areas such as comments, forums, user accounts and file uploads, since spammy user-generated content can harm the site even if the owner is unaware of it.
- Do not buy expired domains to repurpose them primarily for ranking manipulation with content that gives users little value, especially content unrelated to the domain's former purpose.
- Do not send automated queries to Google, such as scraping results for rank checking, without express permission; this violates the spam policies and the Terms of Service.

## Consequences and recovery

- Understand that violations are detected by automated systems and by human review, and can lower rankings or remove content from results entirely, including through a manual action.
- Do not try to circumvent policies by creating new subdomains, subdirectories or sites to continue violating them; this can lead to broader removals and loss of eligibility for features such as Top Stories and Discover.
- Monitor the Manual actions report and Search Console message center for notifications, and address issues and submit a reconsideration request if affected.
- Be aware that a significant volume of valid copyright removal requests, or similar complaints (defamation, counterfeit goods, court-ordered removals), can cause other content on the site to be demoted.

Source: https://developers.google.com/search/docs/essentials/spam-policies
