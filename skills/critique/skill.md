---
name: critique
description: Conduct a structured visual critique of a rendered Instagram post, apply design refinements, and update preferences and anti-patterns in likes.md. Use when evaluating a post draft or training the brand taste memory.
---

1. Identify the target post folder (defaults to the latest folder inside `posts/`). Read `caption.md` and check the rendered `post.png` (or `slide-*.png`).

2. Present the rendered image and prompt the user for structured feedback across four visual criteria:
   - **Hierarchy & Hook**: Does the headline stop the scroll instantly? Is the text scale dramatic enough?
   - **Legibility & Typography**: Are line-heights, letter-spacing, and font weights comfortable to read on mobile?
   - **Color & Depth**: Is background-to-text contrast sufficient? Do gradients, glows, or borders look sleek or noisy?
   - **Layout & Spacing**: Are the 80px outer padding zones respected? Does the composition feel intentional?

3. If the user requests design adjustments:
   - Make surgical edits to `index.html` or `caption.md`.
   - Re-run the Chromium screenshot command to regenerate `post.png`.
   - Present the updated image and verify user satisfaction.

4. Extract specific, actionable taste rules from the interaction and update `likes.md` in the workspace root. Ensure every entry explicitly cites the originating post slug. Maintain this exact 5-section schema:
   ```markdown
   # Brand Taste Memory: likes.md

   ## Visual Styles & Colors
   - `[YYYY-MM-DD_slug]`: [Specific color hexes, gradient angles, glassmorphism values, or background treatments praised]

   ## Typography & Treatments
   - `[YYYY-MM-DD_slug]`: [Specific font pairings, letter-spacing tweaks, uppercase kicker treatments, or weight choices approved]

   ## Layouts & Composition
   - `[YYYY-MM-DD_slug]`: [Specific card geometries, margins, asymmetric splits, or stat callouts praised]

   ## Copywriting & Hooks
   - `[YYYY-MM-DD_slug]`: [Specific hook structures, line-break rhythms, or CTA phrasing that resonated]

   ## Avoid / Disliked
   - `[YYYY-MM-DD_slug]`: [Explicit visual anti-patterns, colors, font weights, or phrasing patterns rejected]
   ```

5. Confirm to the user that their preferences have been committed to `likes.md`. Suggest running `/grid-preview` to see how the post fits into the profile feed, or `/publish-guide` to publish.
