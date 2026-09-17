# Anti-Slop Guardrails (Universal Dislikes)

Mandatory negative filter for `/brand`, `/copy-hook`, `/design-html`, `/carousel-split`, and `/critique`.

## 1. Color & Gradients
- No purple-to-blue or harsh multi-stop gradients.
- No gradient text fills (`-webkit-background-clip`).
- No neon, raw pastel, or rainbow colors.
- No pure black/purple pairing or low-contrast text on dark backgrounds.
- No raw white (`#ffffff`) canvas backgrounds.

## 2. Visual Effects & Texture
- No glassmorphism (`backdrop-filter`), liquid glass, or glossy highlights.
- No soft blurry drop-shadows or floating radial glow orbs.
- No background dot grids or noise layered over gradients.
- No 1px colored card borders or left vertical accent stripes.
- No generic `border-radius: 12px` soft pill boxes (use sharp 0px or extreme geometry).

## 3. Layout & Composition
- No 3-icon box rows, 3-feature card grids, or 3-tier pricing cards.
- No badges hovering above headlines.
- No checkmark bullets or default untouched Shadcn/Tailwind UI.
- No unaligned padding or baseline spacing gaps.

## 4. Iconography & Copy
- No Lucide stroke icons everywhere or magic sparkle icons.
- No emojis in headlines, subheads, copy, or visual cards.
