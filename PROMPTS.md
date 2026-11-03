# Mistvale Tea Co. — Website Project Prompt

## Project goal

Redesign the existing one-page Mistvale tea store into a calm, earthy, premium e-commerce website for urban Indian customers aged 25–45, with a mobile-first experience. The visual direction should feel like a quiet tea garden at dawn and match the product photography: warm cream linen, natural wood, soft window light, kraft-paper packaging, loose tea leaves, gentle shadows, and restrained botanical details. Do not make the store feel like a discount supermarket.

Deliver a polished, accessible, responsive store in a **single `index.html` file** with all CSS and JavaScript inline. Use plain HTML, CSS, and JavaScript only. Do not use frameworks, jQuery, Bootstrap, Tailwind, React, icon fonts, or other UI libraries. Google Fonts are allowed.

## Non-negotiable protected content

Do not change any of the following from the original supplied file:

1. The `PRODUCTS` array's IDs, names, and prices.
2. The complete API object, including every character between `API START` and `API END`.
3. The footer legal-text paragraph.
4. `<form id="checkout-form">`, including `action="https://mistvale.example/cart/checkout"`, `method="POST"`, and the field names `items` and `coupon`.

Do not invent product facts, company facts, customer reviews, ratings, award claims, press mentions, customer counts, discounts, or other numbers. Use the supplied facts only. Record unresolved assumptions in a visible-free HTML comment starting `<!-- QUESTION FOR TEAM: ... -->` and list those questions in `NOTES.md`.

## Company facts and voice

- Brand: **Mistvale Tea Co.**; short form: **Mistvale** (only the M is capitalised).
- Tagline: **“Hill-grown tea, honestly made.”**
- Founded: 2019.
- Address: 14 Hill Cart Road, Siliguri, West Bengal 734001, India.
- Phone: +91 90000 12345.
- Email: hello@mistvale.example.
- Website: https://mistvale.example.
- Instagram: https://instagram.com/mistvale.example.
- Prices include GST.
- Unopened packs can be returned within 7 days of delivery; opened tea cannot be returned for hygiene reasons.
- The supplied product data contains ratings for only two products. Show ratings only where they exist in `PRODUCTS`.

Use warm, specific, honest language, such as “Malty Assam leaves for your morning cup.” Avoid shouting, all-caps copy, exclamation marks in headings, unsupported superlatives, and false claims.

## Visual design system

Define these CSS custom properties on `:root` and use them consistently:

- `--tea-green: #1f3d2b` — primary colour, header/footer, primary buttons and headings.
- `--leaf: #4f7942` — secondary accents and success states.
- `--cream: #f6f1e7` — main page background.
- `--parchment: #ebe2cf` — cards and alternate section backgrounds.
- `--saffron: #d9962b` — sparingly, such as focus rings and a single accent per view.
- `--ink: #1b1b1b` — body text.
- `--error: #b3261e` — error states.

Do not use purple, pink, neon colours, unrelated gradients, or un-tokenised colours. Use text/background combinations that satisfy WCAG AA contrast (at least 4.5:1 for ordinary text).

Load exactly two font families from one Google Fonts `<link>` with `display=swap`: **Fraunces** for headings and **Inter** for body text. Do not use `@import`.

Typography and spacing:

- Body text: 16px minimum; do not go below 15px.
- Small text: 14px, never below 13px.
- `h3`: 20–24px; `h2`: 28–40px; `h1`: 40–64px using `clamp()`.
- Use sentence-case headings.
- Spacing scale: 8px multiples (4px allowed for tight gaps), using 8, 16, 24, 32, 48, and 64px design tokens.
- Content max-width: 1200px; 16px side padding on phones.
- Section vertical padding: 48px on phones and 64–96px on desktop.
- Product grid: two columns on phones, three to four on desktop; product cards must have equal height.
- Use one consistent corner radius throughout (12px); pills are reserved for filter chips and badges.
- Use specific-property transitions of 150–300ms. No `transition: all`, blinking, bouncing, rotating, marquee, or looping decorative animation. Respect `prefers-reduced-motion`.

Buttons and interaction styling:

- Exactly one primary style: tea-green filled.
- Exactly one secondary style: outline.
- Buttons have at least 44px touch height, with hover, focus-visible, active, and disabled states.
- Use at most one primary CTA per view.
- Links and cards should have visible, restrained hover feedback (underline, shadow, or a lift of no more than 4px).
- Use inline SVG icons with consistent `stroke-width="1.75"`; do not use icon fonts.

## Use the recently created imagery

Use the new brand assets supplied with the project, not generic placeholders:

- Logo: `images/logo.png` (and `images/logo.webp` may be used for an optimised version).
- Hero: `images/hero-banner.png` (and `images/hero-banner.webp` may be used for an optimised version).
- Product image IDs: `images/p101.webp` through `images/p108.webp`, corresponding to product IDs 101–108. PNG variants may be used as fallbacks if present.

The eight product photos use a consistent warm product-photography style. Product images should be square, 1:1, with `object-fit: cover`, explicit width and height attributes, and `loading="lazy"`. Do not lazy-load the hero image. Add descriptive alt text to all meaningful images. Keep all images optimised for the web; product WebP images should remain below 150 KB each and the hero below 250 KB.

## Required page sections, in this exact order

1. **Announcement strip:** one short, honest line; for example, free shipping on orders of ₹499 or more after discount and an instruction to use WELCOME10 at checkout. Do not add a countdown.
2. **Header:** `images/logo.png` with alt text “Mistvale Tea Co.”; navigation links for Shop, Delivery, Reviews, FAQ and Contact; search access; and a cart button with a live quantity badge. The header is sticky. On phones, collapse search to an icon that opens the search field.
3. **Hero:** exactly one `<h1>` containing “Hill-grown tea, honestly made.” Add a short supporting line using only approved facts, one primary CTA labelled “Shop the teas”, at most one outline secondary CTA labelled “Check delivery”, and `images/hero-banner.png` as the hero image with a dark-green overlay where needed for text contrast.
4. **Trust strip:** three or four concise promises supported by known facts only: prices include GST; unopened packs can be returned within 7 days; delivery takes 2–5 working days across India; founded in 2019 in the hills. Add inline SVG icons.
5. **Shop:** an `<h2>`, category chips (All, Black, Green, Herbal, Gifts), search, sort control, and product grid. Each product card includes an image, product name, category pill, short description, price with ₹ and Indian digit grouping, rating only for products that have a rating, a visible Add to cart button, a wishlist heart, and a Sold out badge with a disabled add button when stock is zero. Include a styled quick-view dialog with a visible close button.
6. **Delivery check:** visible label, pincode input, button, result and error messages with inline SVG icons.
7. **Reviews:** heading “What customers say” and only the three original quotes and names. Do not add ratings, counts, or invented testimonials.
8. **FAQ:** accessible `<details>/<summary>` accordion using these answers exactly:
   - **How long does delivery take?** 2 to 5 working days depending on your pincode. Use the delivery check to see yours.
   - **Can I return tea?** Unopened packs can be returned within 7 days of delivery. Opened tea cannot be returned for hygiene reasons.
   - **How should I store my tea?** In an airtight container, away from light, heat and strong smells. It tastes best within 6 months of opening.
   - **Is Chamomile & Tulsi caffeine-free?** Yes, it is a caffeine-free herbal blend.
   - **Do you ship outside India?** Not yet. We currently deliver within India only.
   - **Can I send tea as a gift?** Yes. The Tea Lover's Sampler comes in a wooden gift box with a brewing guide.
9. **Newsletter:** inline section, not a popup. Include a visible email label, client-side validation, inline errors, and a clear success/validation state. Do not promise a discount. Do not claim a subscription succeeded unless an actual newsletter service is connected.
10. **Footer:** logo, brand name, contact facts, Instagram icon linking to `https://instagram.com/mistvale.example`, unchanged legal text paragraph, and unchanged copyright line.

## Required inline SVG icons

Use a consistent stroke width of 1.75. Include icons for: shopping bag/basket, search, wishlist heart, close, plus, minus, delivery truck, returns/arrow, leaf/quality, check, and Instagram. Decorative SVGs should be hidden from assistive technology; functional controls must have accessible labels.

## Cart drawer requirements

- Slide in from the right over 200–300ms with a dark click-to-close overlay.
- Escape closes the drawer; focus remains trapped while open and returns to the opening control on close.
- Use clear line items with product image thumbnails, product name, price from `PRODUCTS`, quantity stepper with 44px touch targets, and remove button.
- Show a free-shipping progress bar and useful message.
- Provide a labelled coupon field with an inline status/message, itemised totals, and a single primary Checkout button.
- Show a toast “Added to cart: [item name]” on successful addition and a clear message when a limit prevents addition.

## Business rules — must all work

- **R1 — Prices:** Prices come from `PRODUCTS` only, never page text.
- **R2 — Quantity:** At most 5 of any product and never more than its stock. Enforce this for product cards, quick view, plus/minus controls, typed quantity, and checkout. Sold-out products cannot be added.
- **R3 — Coupon:** `WELCOME10` is case-insensitive. It gives 10% off eligible line items only, excludes category `Gifts`, is capped at ₹150, and requires the full cart subtotal to be at least ₹399. Only one coupon per order; applying twice must not stack. Recalculate eligibility whenever the cart changes. If the subtotal falls below ₹399, remove the coupon and explain why. If the coupon is applied to a gift-only cart and discount is zero, show “WELCOME10 does not apply to gift boxes”.
- **R4 — Shipping:** Shipping is ₹49 and becomes free when subtotal minus discount reaches the configured free-shipping threshold. Do not calculate the threshold from the pre-discount subtotal.
- **R5 — Currency:** Round only the final payable total to the nearest rupee. Format all amounts with ₹ and Indian grouping (for example, ₹1,23,456).
- **R6 — Sold out:** Sold-out products must never be addable, including through quick view, and must appear last in every sort order.
- **R7 — Browsing:** Keep category, sort and query in one state object. Category matching is case-insensitive; “all” applies no category filter. Search, category filter and sort must compose. Sort a copy, never mutate shared `PRODUCTS`. Use explicit membership checks, not truthy `indexOf()` results. Debounce API search; ignore stale responses; always show results for the text currently in the search field. Show “No teas found” when appropriate. Changing filter or sort must preserve the current query.
- **R8 — Delivery check:** Use the untouched `API.checkPincode()`. Validate the six-digit format client-side before calling the API. Handle `INVALID_PINCODE` with “Enter a valid 6-digit pincode”; show “Delivery in N days” or “Sorry, not serviceable”; handle other errors; disable the button while loading; ignore stale results; and always clear loading state so it never remains on “Checking…”. Put status in an `aria-live` region.

## Storage and security

- Store only `{id, qty}` per cart line in localStorage. Look up product names and prices from `PRODUCTS`.
- Recover safely from empty, corrupted, outdated, or invalid localStorage entries. Normalise string/numeric IDs, merge duplicate lines, enforce current stock and quantity limits, and drop invalid/sold-out entries.
- Save the wishlist as an array of product IDs. Toggling one heart affects only that product, updates `aria-pressed`, and preserves keyboard focus on that same heart.
- Escape dynamic product content used in HTML attributes/markup. Prefer `textContent` for user-entered text and status messages. Never insert a raw email or pincode into `innerHTML`.
- Do not use `alert()` for feedback.
- Newsletter is an inline section; no timed popup.
- The old countdown date (2025-11-01) is in the past. Remove the countdown strip rather than inventing a new sale date.
- Checkout blocks an empty cart, fills `items` with JSON shaped like `[ {"id": 101, "qty": 2} ]` containing only IDs and quantities, sets `coupon` to `WELCOME10` or an empty string, and submits the existing form with `form.submit()`.

## SEO and structured data

- Use `<html lang="en">`.
- Create a unique 50–60 character title and a 120–160 character meta description.
- Add a canonical link for `https://mistvale.example`, Open Graph tags and Twitter card tags.
- Use exactly one `<h1>` and logical h2/h3 order.
- Add JSON-LD for `Organization` (or `OnlineStore`) using only the known company facts, a `Product` entry for each product (INR price, availability derived from stock and aggregate rating only where a rating exists), and `FAQPage` containing the six approved FAQs.
- Include a skip-to-content link and semantic landmarks (`header`, `nav`, `main`, `footer`).
- The header cart button must keep `id="cart-open"`, keep the badge `id="cart-count"`, and have a live accessible label such as “Open cart, N items”.

## Technical and responsive acceptance

- Everything except supplied image assets must be in `index.html`.
- Use no UI frameworks or icon libraries.
- Layout must work from 360px phone width through desktop with no sideways scrolling.
- Respect reduced-motion settings.
- All form labels must be visible; errors and success states must be inline.
- Buttons, filter chips, cards, links, quantity controls and dialogs must be keyboard accessible.
- Keep `PRODUCTS`, API, legal paragraph, and checkout form protected exactly as supplied.

## Required submission contents

Create one ZIP under 20 MB containing:

```text
Tarun_kaushik-mistvale.zip
├── index.html
├── images/
│   ├── logo.png and/or logo.webp
│   ├── hero-banner.png and/or hero-banner.webp
│   └── p101.webp through p108.webp (PNG fallbacks if supplied)
├── LINK_AI_TOOLS.md
├── NOTES.md
├── PROMPTS.md
└── Tarun_Kumar_Kaushik_Resume.pdf
```

`NOTES.md` must document unresolved questions, temporary choices and bonus additions. `PROMPTS.md` must log every actual AI prompt used for code and images in chronological order and exactly as typed, including the tool, prompt type, prompt text, outcome and why. This `prompt.md` is the project brief; it does **not** replace the required chronological `PROMPTS.md` prompt log.

## Final verification before submission

Test in Chrome with empty and corrupted localStorage, legacy cart entries, repeated additions, quantity edits, out-of-stock products, coupon + cart changes, shipping threshold transitions, all combinations of search/filter/sort, out-of-order search responses, invalid/serviceable/unserviceable pincodes, keyboard-only use, screen-reader status messages, newsletter validation, empty-cart checkout blocking, and the checkout form payload. Confirm that every protected data block remains unchanged and that image paths resolve inside the submitted ZIP.
