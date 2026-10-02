# Mistvale Tea Co. — Notes

## 1. What I changed

I started by reviewing the existing store and the assessment requirements before making changes.

### Store and business logic

* Fixed cart calculations so product prices are taken from the `PRODUCTS` data instead of relying on displayed text.
* Added the maximum quantity rule of 5 items per product while also respecting the product's available stock.
* Prevented sold-out products from being added to the cart.
* Fixed `WELCOME10` so the coupon is case-insensitive, requires a minimum subtotal of ₹399, applies only to eligible tea products, excludes the `Gifts` category, and has a maximum discount of ₹150.
* Prevented the coupon from stacking when it is applied more than once.
* Fixed shipping calculation so the ₹49 charge is removed only when the required amount after discount qualifies for free shipping.
* Updated sorting so sold-out products remain at the end.
* Fixed the interaction between search, category filtering and sorting so changing one does not reset the others.
* Improved the delivery check so the UI handles successful responses, unavailable pincodes and invalid/error cases instead of remaining stuck on the loading state.
* Preserved the existing `PRODUCTS` data, API object and checkout form contract.

### Design and UX

* Reworked the visual styling to follow the Mistvale brand guide instead of using a generic e-commerce style.
* Used the specified Mistvale colour tokens and typography.
* Improved spacing, product cards, buttons, hover states and keyboard focus states.
* Improved the mobile layout with the product grid and navigation designed for smaller screens.
* Added/refined the required store sections and FAQ presentation.
* Improved the shopping flow so cart actions and product interactions provide clearer feedback.

### SEO and accessibility

* Improved page metadata and semantic heading structure.
* Added/updated structured data for the store, products and FAQ using only the supplied information.
* Added descriptive image `alt` text.
* Improved labels and keyboard focus for interactive elements.

### Images

* Replaced the placeholder imagery with AI-generated tea imagery.
* Kept the product images visually consistent in framing and style.
* Optimized the hero image for web use.
* The final hero file is `images/hero-banner.png` and is approximately 240.91 KB.

---

## 2. What the AI got wrong

I did not treat the AI output as final. I checked the implementation against the assessment requirements and tested the important flows manually.

One specific issue I caught was related to the hero image optimization. The generated optimization report described a 1280 × 715px image as 16:9. I checked the dimensions myself and found that exact 16:9 at 1280px width would be 1280 × 720px. I therefore recorded the actual dimensions instead of repeating the incorrect claim.

I also checked the generated implementation against the assessment constraints because an AI-generated change can unintentionally affect existing data, API behaviour or the checkout contract.

---

## 3. Images

The imagery was created using AI tools and then reviewed before being used in the store.

The hero image was resized and compressed for web delivery. The final file is:

`images/hero-banner.png`

Final size:

`240.91 KB`

The existing required filename and path were preserved.

The product images were also reviewed for consistent framing and visual treatment rather than using unrelated images for each product.

---

## 4. How I tested it

I tested the store manually in Chrome rather than relying only on the code review.

I checked:

* Product search
* Category filtering
* Sorting
* Search + filter + sort together
* Product quick view
* Adding products to the cart
* Repeated Add to Cart actions
* Cart quantity changes
* Quantity and stock limits
* Removing products
* Sold-out products
* `WELCOME10`
* Coupon minimum subtotal
* Gift-product coupon eligibility
* Coupon discount cap
* Applying the coupon more than once
* Shipping calculation after discount
* Delivery pincode checking
* Invalid delivery input/error handling
* Newsletter interaction
* Countdown behaviour
* Checkout form fields and payload requirements

I also checked the page at mobile and desktop widths and looked for horizontal scrolling.

For keyboard accessibility, I used keyboard navigation to move through the interactive elements and checked that focus was visible.

I checked the browser console and image loading for obvious errors.

---

## 5. Questions for the team

The assessment requires the hero image to be under 250 KB and recommends a 1:1 ratio for product images, but it does not explicitly require the hero to be exactly 16:9.

The final hero image is 1280 × 715px and 240.91 KB. I kept the optimized composition because changing the crop again would alter the existing visual composition.

No company facts, reviews, awards or product claims were added beyond the information supplied in the assessment and `BRAND.md`.

---

## 6. Time spent

Approximately 4–5 hours.

---

## 7. Extra features I added

I focused primarily on the required assessment items rather than adding large bonus features before completing the core requirements.

Any additional UI refinements were kept within the existing store functionality and did not change the required backend/API or checkout contract.

---

## 8. With more time I would…

* Run a full Lighthouse audit and address any remaining performance, accessibility and SEO findings.
* Test the store on more physical devices and browsers.
* Perform a dedicated screen-reader pass.
* Do additional edge-case testing around asynchronous delivery checking and rapid user interactions.
* Further refine small visual details after testing the store with real users.
