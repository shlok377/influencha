---
name: grid-preview
description: Simulate a 3x3 Instagram profile grid using recent post graphics to verify aesthetic harmony and color rhythm. Use before publishing to ensure your feed looks cohesive.
---

1. Scan the `posts/` directory and collect up to 9 recent posts ordered by date descending (newest first).
   - For single posts, use `post.png`.
   - For carousel posts, use `slide-01.png` (the cover image).
   - If fewer than 9 posts exist in `posts/`, generate neutral branded placeholders to fill the 3x3 grid.

2. Generate a standalone local HTML file at `posts/grid_preview.html`.
   - Layout: Exact 3-column CSS Grid mimicking the native Instagram profile grid (`grid-template-columns: repeat(3, 1fr); gap: 4px; max-width: 935px; margin: 0 auto;`).
   - Every tile must be a perfect 1:1 square with `aspect-ratio: 1 / 1; overflow: hidden;`.
   - Include post folder names and dates on subtle hover overlays.
   - Include a header showing the page handle and brand vibe from `brand.md`.

3. Open `posts/grid_preview.html` in the default browser:
   ```bash
   xdg-open file://$(pwd)/posts/grid_preview.html 2>/dev/null || google-chrome file://$(pwd)/posts/grid_preview.html 2>/dev/null || chromium file://$(pwd)/posts/grid_preview.html 2>/dev/null
   ```

4. Provide a feed critique checklist in the terminal:
   - **Color Balance**: Are contrasting dark/light or accent colors evenly distributed, or clustered awkwardly?
   - **Typographic Cadence**: Does the feed alternate between heavy display headlines and cleaner layouts?
   - **Grid Continuity**: Do adjacent posts feel like parts of the same curated publication?

5. If the new post clashes with its immediate neighbors, suggest a palette or background tweak via `/critique` before final publishing.
