# Mistvale Tea Co. — Project Notes

## 1. What I changed

- Reworked the store into a calm, earthy tea-brand experience using cream, parchment, tea-green and saffron accents, Fraunces headings, and Inter body text.
- Added the hero, trust promises, product browsing controls, product quick view, persistent per-product wishlist, delivery checker, reviews, FAQ, inline newsletter validation and footer.
- Consolidated cart price calculations around `PRODUCTS`; added quantity/stock guards, coupon eligibility and cap, post-discount shipping logic, Indian currency formatting, stale-search protection and pincode loading/error handling.
- Added accessibility work including visible focus styles, keyboard support, live status messages, accessible labels and focus management for overlays/drawers.
- Added title/description metadata, canonical/social metadata and JSON-LD for the organization, products and FAQ.
- Added product and hero images inspired by the same warm, natural product-photography theme and converted them to WebP for delivery efficiency.

## 2. What the AI got wrong, and how I caught it

- An early hero-banner image included headline text, benefit labels and a button, even though the image was meant to be a background only. I asked for a new version with no text so the website can render its own accessible HTML text and controls.
- Earlier website drafts included unsupported promotional claims (including an award/press claim and customer rating/count language) and an expired-sale countdown. These were identified during review and removed from the later design.
- Early code iterations used outdated or duplicate browsing handlers and included external UI dependencies. The final direction is a single-file HTML/CSS/JS store without jQuery, icon fonts or UI frameworks. The final file still needs the browser tests below before it should be treated as fully verified.
- The first generated logo was a detailed photographic emblem rather than a simple vector mark. It was retained as a visual logo asset and converted to WebP; a cleaner SVG logo could be considered later if required.

## 3. Images and optimisation

- Product photos `p101.webp` through `p108.webp`: generated with ChatGPT image generation to keep the blank kraft packaging, warm cream/linen background, wood surface, soft side light and earthy product styling consistent. The sampler image uses an open wooden gift box with six blank pouches instead of a tea pouch and dish.
- `hero-banner.webp`: generated with ChatGPT image generation as a wide, text-free tea still life, then converted to WebP at 1600 × 640 (approximately 106 KB in the current project folder).
- `logo.webp`: generated with ChatGPT image generation and converted to WebP (approximately 92 KB in the current project folder).
- The eight product images are 800 × 800 WebP files (roughly 52–61 KB each in the current project folder). PNG source versions are also retained in the working files outside the compact website bundle; the store paths should resolve to the packaged WebP files.

## 4. How I tested it

- I reviewed the requirements and implementation iteratively in the AI-assisted workflow and prepared a Chrome test plan.
- **Browser verification has not been completed as part of this handoff.** I have not run a full manual Chrome pass, Lighthouse audit, screen-reader audit, or automated test suite here. Do not interpret the implementation review as proof that every interaction has passed.
- Before submission, run the complete manual test checklist: 360 px phone layout; keyboard focus and Escape handling; search/filter/sort combinations and out-of-order responses; quantity and sold-out handling; coupon minimum/cap/Gifts/no-stacking; shipping threshold after discount; invalid/serviceable/unserviceable pincodes; corrupt/legacy localStorage; empty-cart and payload checkout; newsletter validation; and image/SEO/schema checks.

## 5. Questions for the team

- Which newsletter provider or API endpoint should receive valid email addresses? The page currently validates input but must not claim a subscription was completed without a connected service.
- Are the three customer quotes in the supplied starter HTML approved for production publication?
- Is `https://mistvale.example` the intended assessment placeholder, or should the canonical URL, social metadata and JSON-LD be updated to a production domain before launch?
- Should both PNG source assets and WebP optimised assets be shipped, or is WebP-only acceptable for this assessment?

## 6. Time spent

Exact hands-on hours were not tracked across the multiple AI-assisted sessions. Add an honest estimate before submitting this file; no time figure has been invented here.

## 7. Extra features added

- Product wishlist saved in localStorage.
- Product quick-view dialog.
- Accessible FAQ accordion and FAQ structured data.
- Optimised WebP product images, logo and hero banner.
- Debounced search with stale-response protection.

## 8. With more time I would…

- Complete and document real Chrome tests at mobile and desktop widths, then run Lighthouse and accessibility checks.
- Connect the newsletter form to a real provider and verify success/error states against that service.
- Verify the generated image assets and metadata in the deployed environment, and replace `.example` URLs only after the real domain is confirmed.
- Review testimonial permissions and validate all structured data with the team's production SEO requirements.
