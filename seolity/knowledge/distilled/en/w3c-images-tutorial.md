---
title: Choosing the Right alt Text for Images: W3C Decision Tree
lang: en
topic: accessibility
tags: accessibility, images, alt-text, img, decorative-images, functional-images
sources: https://www.w3.org/WAI/tutorials/images/decision-tree/
updated: 2026-10-26
generated: knowledge-builder
---

# Choosing the Right alt Text for Images: W3C Decision Tree

This guidance describes how to decide what to put in the alt attribute of an <img> element depending on the image's role. Choosing correctly ensures that images that carry meaning or function are understandable to all users, while decorative or redundant images do not add noise.

## Images that contain text

- Use an empty alt attribute (alt="") when the text in the image is also present as real text nearby, because the information is already available and repeating it is redundant.
- Use an empty alt attribute when the text in the image is shown only for visual effect, because it adds no information for the user.
- Use the alt attribute to communicate the function of the image when its text has a specific function, for example an icon, rather than reading out the visual content.
- Use the alt attribute to include the full text of the image when that text is not present anywhere else on the page, so the information is not lost.
- Where possible, consider web fonts instead of images of text, since real text is an alternative approach to using images for text.

## Images in links and buttons (functional images)

- Use the alt attribute to communicate the destination of the link or the action of the button when it would be hard or impossible to understand what the link or button does without the image.
- Describe the function (where the link goes or what action happens), not the appearance of the image.

## Images that contribute meaning

- Use a brief description in the alt attribute that conveys the meaning of the image in its context when it is a simple graphic or photograph.
- For graphs or other complex information, include the information contained in the image elsewhere on the page instead of trying to fit it all in the alt attribute.
- Use an empty alt attribute when the image shows content that is redundant to real text nearby, because the text already conveys the information.

## Decorative images and unclear cases

- Use an empty alt attribute for images that are purely decorative or not intended for users, so they are skipped by assistive technology.
- Consider CSS background images for decorative images as an alternative to <img> elements.
- When an image's use is not covered by the common cases or it is unclear what alt text to provide, consult the W3C Images Tutorial for detailed guidance, since the decision tree does not cover all cases.

## Decision order to follow for each image

- Evaluate each image in order: first whether it contains text, then whether it is used in a link or button, then whether it contributes meaning to the page, then whether it is purely decorative.
- Apply the first matching case to determine the alt value rather than defaulting to a generic description.

Source: https://www.w3.org/WAI/tutorials/images/decision-tree/
