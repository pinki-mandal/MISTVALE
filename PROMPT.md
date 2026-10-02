# Mistvale Tea Co. — AI Prompt Log

This file records the AI prompts I used during the assessment. I used AI for review, reasoning, implementation suggestions and image generation, and manually checked the results before using them.

## Prompt 1

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> I’m working on a vanilla HTML/CSS/JavaScript e-commerce assessment for Mistvale Tea Co. The existing page is functional but has bugs and poor UX. I want to improve it without replacing the architecture.
>
> First, review the assessment requirements and help me identify the highest-risk areas before making changes. Pay particular attention to the business rules R1–R8, because the product prices must come from PRODUCTS, quantity must respect both the 5-item limit and stock, WELCOME10 has eligibility and discount constraints, shipping depends on the post-discount amount, sold-out products must remain last, filters/search/sort must work together, and delivery checking must handle API delays/errors.
>
> The important constraints are: one index.html, no frameworks or libraries, do not modify PRODUCTS ids/names/prices, do not modify the API object, preserve the checkout form contract, and do not modify the approved footer legal text.
>
> I want recommendations based on the existing implementation rather than a completely new generic store.

* **Outcome:** Reviewed the requirements and identified the main areas that needed attention.

* **Why:** I wanted to understand the risky parts of the existing implementation before making changes.

## Prompt 2

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> Help me reason through the cart implementation for this Mistvale store. I need the cart calculations to always derive prices from PRODUCTS rather than DOM text. Quantities must never exceed min(5, stock), sold-out items cannot be added, and the final total should round only at the end.
>
> WELCOME10 should be case-insensitive, require a subtotal of at least ₹399, apply only to non-Gifts items, and give 10% off eligible items capped at ₹150. Shipping is ₹49 unless the amount after discount reaches the free-shipping threshold.
>
> Please focus on edge cases such as clicking Add to Cart repeatedly, changing quantity after applying a coupon, removing an item, adding a Gift item, and applying the coupon more than once. Explain what the implementation needs to guarantee rather than rewriting unrelated parts of the page.

* **Outcome:** Used the suggestions to check and update the cart logic. I then manually checked the different quantity, coupon and shipping cases.

* **Why:** The cart had several rules that could easily fail in edge cases, so I wanted to reason through them separately.

## Prompt 3

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> I need to improve the existing Mistvale UI while following BRAND.md closely instead of making it look like a generic AI-generated template.
>
> Use the existing content and facts only. The visual direction should be calm, earthy and premium: Tea Green #1f3d2b, Leaf #4f7942, Cream #f6f1e7, Parchment #ebe2cf, Saffron #d9962b, Ink #1b1b1b and Error #b3261e.
>
> Keep exactly two font families, use the required spacing/type scale, one consistent corner radius, clear primary and secondary button states, visible keyboard focus, subtle 150–300ms transitions, reduced-motion support, and a mobile-first layout with two product columns.
>
> The goal is refinement of the current page, not adding unnecessary sections or flashy effects.

* **Outcome:** Used the relevant styling suggestions and adjusted the existing UI. I checked the result against BRAND.md instead of accepting the visual changes automatically.

* **Why:** I wanted the design to follow the supplied brand guide and still feel like an improvement to the existing page.

## Prompt 4

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> Review the page structure against the Mistvale required section order: announcement, header, hero, trust strip, shop, delivery check, reviews, FAQ, newsletter and footer.
>
> Also check the semantic HTML, heading hierarchy, form labels, keyboard accessibility, focus states, image alt text and interactive controls. Identify anything that would create an accessibility or usability problem on a 360px mobile screen.
>
> Do not suggest frameworks or separate CSS/JS files because the assessment requires a single index.html.

* **Outcome:** Got a checklist of structural and accessibility issues to check and used the relevant suggestions in the existing page.

* **Why:** I wanted to make sure the page worked properly on small screens and that the required single-file structure was preserved.

## Prompt 5

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> Audit the SEO requirements for the Mistvale store. I need a unique 50–60 character title, 120–160 character meta description, canonical URL, Open Graph tags, Twitter card tags, one H1, logical H2/H3 structure and JSON-LD for Organization/OnlineStore, each product and the approved FAQ.
>
> Use only facts supplied in BRAND.md and PRODUCTS. Do not invent reviews, ratings, awards, business claims or product information. For product structured data, availability must reflect stock and ratings should only appear where the product actually has a rating.
>
> Tell me what is missing or risky in the current implementation.

* **Outcome:** Used the audit to identify and check the SEO and structured-data requirements in the page.

* **Why:** The assessment had specific SEO requirements, so I wanted a separate check instead of assuming the existing metadata was sufficient.

## Prompt 6

* **Tool:** AI Image Tool
* **Type:** image
* **Prompt:**

> Create a premium photorealistic hero image for Mistvale Tea Co., a Darjeeling tea brand. The visual language should feel calm, earthy and warm, like a quiet tea garden at dawn. Use natural soft morning light, cream, wood, linen or stone surfaces, subtle shadows and an editorial product-photography composition.
>
> Show a refined tea presentation suitable for an e-commerce homepage hero. Keep enough clean visual space for website copy to sit beside/over the composition without covering important product details. Do not include any text, logos, fake awards, badges, ratings or unsupported claims.
>
> The image should feel consistent with a premium Indian tea brand rather than a generic stock photograph.

* **Outcome:** Generated the hero image and then prepared it for use in the website by resizing/cropping and compressing it.

* **Why:** The assessment required a suitable hero image, so I used AI to create the visual and then handled the web optimization separately.

## Prompt 7

* **Tool:** AI Image Tool
* **Type:** image
* **Prompt:**

> Create a consistent 1:1 product photography style for Mistvale Tea Co. Use natural light, cream/wood/linen/stone backgrounds, soft shadows and the same camera framing and visual treatment across the product range.
>
> Each image should show the relevant tea pack or tin together with a subtle visual hint of the tea itself. Keep the product as the main subject and avoid excessive props. No baked-in text, fake ratings, awards, badges or promotional claims.
>
> The images need to look like one professionally photographed collection rather than eight unrelated AI images.

* **Outcome:** Generated the product imagery and reviewed the images for consistent framing and style before using them.

* **Why:** The product images needed to look like one collection rather than unrelated images.

## Prompt 8

* **Tool:** ChatGPT
* **Type:** code
* **Prompt:**

> Give me a final manual QA checklist for the completed Mistvale store. I want to test it as a real shopper rather than only checking whether the page looks correct.
>
> Include normal flows and edge cases for search, combined filters and sorting, sold-out products, cart quantity limits, stock limits, coupon eligibility, coupon repetition, discount cap, shipping threshold, delivery API success/error/invalid input, newsletter, FAQ interaction, checkout payload, mobile responsiveness, keyboard navigation, console errors, broken images and horizontal scrolling.
>
> Also include a quick constraint audit: PRODUCTS, API object, checkout contract, footer legal text, single-file architecture, image size and required submission files.

* **Outcome:** Used the checklist for the final manual QA and checked the important shopper flows and assessment constraints.

* **Why:** I wanted to test the finished store as a user and not rely only on the AI/code review.
