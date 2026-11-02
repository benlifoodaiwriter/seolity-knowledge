---
title: Schema.org Product type: marking up products and offers
lang: en
topic: schema
tags: schema, product, structured-data, json-ld, ecommerce, offers, reviews, gtin
sources: https://schema.org/Product
updated: 2026-11-02
generated: knowledge-builder
---

# Schema.org Product type: marking up products and offers

This guidance covers how to describe products with the Schema.org Product type, including identifiers, offers, ratings, reviews, variants, and shipping and return details. Accurate, specific markup helps machines interpret product pages correctly, especially in e-commerce.

## Core Product markup

- Use the Product type for any offered product or service (e.g. shoes, a ticket, a car rental, a haircut), and include at least name, image, description and offers for a typical product page.
- Mark up the same information that is visible on the page (name, price, availability, ratings, description). The examples mirror the on-page content in the structured data.
- Prefer JSON-LD in a <script type="application/ld+json"> tag with "@context": "https://schema.org" and "@type": "Product". Microdata and RDFa are also valid ways to express the same data.
- Use url, sameAs, mainEntityOfPage and alternateName where helpful to identify the item. sameAs should point to a reference page that unambiguously indicates the item's identity, such as a Wikipedia or Wikidata page or an official website.
- Use brand (Brand or Organization) and manufacturer (Organization) to state who makes or markets the product.
- When a page lists several products (e.g. a category listing), wrap them in an ItemList with itemListElement entries of type Product, and give each a name, url, image and offers.

## Product identifiers

- Provide strong identifiers such as gtin, mpn and sku where they exist. For the model property, the source recommends additionally giving gtin8/gtin13/gtin14 and mpn.
- Use a valid GTIN in the gtin property: an all-numeric string of 8, 12, 13 or 14 digits with a valid GS1 check digit. Do not left-pad values, because padding is neither required nor encouraged.
- Put GS1 Digital Link URLs in hasGS1DigitalLink, not in gtin. Include only the Application Identifiers relevant to the entity and the correct granularity (serial number AI 21 only on IndividualProduct; lot number AI 10 on SomeProducts or IndividualProduct; global model number AI 8013 on Product or ProductModel).
- Use sku for a merchant-specific identifier, and use asin only for Amazon Standard Identification Numbers.
- Use identifier with a PropertyValue (propertyID plus value) for identifier schemes that have no dedicated property, such as a DID.
- Avoid expressing data in generic additionalProperty when a dedicated property exists (e.g. width, color, gtin13). Consumers built for specific properties typically expect the dedicated one.

## Offers, price and availability

- Attach an Offer through the offers property with price, priceCurrency and availability (e.g. https://schema.org/InStock).
- Give price as a plain machine-readable number (e.g. "55.00") without thousands separators or currency symbols, and give the currency separately in priceCurrency as a code such as USD, EUR or RUB.
- When several sellers offer the same product, use an AggregateOffer with lowPrice, highPrice, priceCurrency and offerCount, and list individual Offer entries (e.g. with url) inside it.
- Use itemCondition with an OfferItemCondition value (e.g. https://schema.org/NewCondition) to state the condition of the product.
- Use priceSpecification with UnitPriceSpecification and priceType https://schema.org/MaximumRetailPrice to express a list price alongside the actual selling price.
- Use priceValidUntil on an Offer when the price is only valid until a given date.

## Ratings and reviews

- Use aggregateRating (AggregateRating) with ratingValue and either reviewCount or ratingCount to summarise the overall rating, and include bestRating/worstRating when the scale is not the default (e.g. 87 out of 100).
- Mark up individual reviews with review (Review), including author, datePublished, name, reviewBody and a reviewRating (Rating with ratingValue, bestRating, worstRating).
- Only mark up ratings and reviews that actually appear on the page, and keep the numbers in the markup consistent with the visible content, as the source examples do.
- Use positiveNotes and negativeNotes for pro/con lists. In a list, the most positive (or most negative) item comes first.

## Variants, models and related products

- Use ProductGroup with hasVariant for sets of products that differ only on explicitly defined dimensions, and link each variant back with isVariantOf or inProductGroupWithID.
- Use ProductModel for a base model. A variant can be assumed to inherit the base model's features unless they are defined locally, and this inheritance is not transitive.
- Use isAccessoryOrSparePartFor, isConsumableFor, isOftenBoughtWith, isRelatedTo and isSimilarTo to link to other Product entries that have a real relationship to the current product.
- Use the more specific subtypes when they fit: DietarySupplement, Drug, IndividualProduct, ProductCollection, ProductGroup, ProductModel, SomeProducts, Vehicle.

## Product details, specifications and policies

- Use dedicated properties for physical attributes: color, size, material, pattern, weight, width, height, depth and hasMeasurement. Keep colorSwatch consistent with the textual color value.
- Use specification (PropertyValue) for strict retail specifications, optionally grouped with valueGroup, and use additionalProperty only for characteristics with no matching schema.org property.
- Describe returns with hasMerchantReturnPolicy (MerchantReturnPolicy) and shipping with shippingDetails (OfferShippingDetails), including destination, rate and handling and transit times.
- Use consumerNotice for safety warnings or mandatory consumer information, and hasCertification, hasEnergyConsumptionDetails, countryOfOrigin and hasDigitalProductPassport for compliance and sustainability data where it applies.
- Use image with a URL or a full ImageObject, and give images meaningful alt text in the page HTML that matches the product, as the examples do.
- Where several languages are offered, give description values with @language tags in JSON-LD (e.g. en and fr).

Source: https://schema.org/Product
