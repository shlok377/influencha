---
name: critique
description: Conduct a structured visual critique of a post, apply design refinements to HTML/copy, record learnings in likes.md, and hand off to render-post without generating PNGs.
---

1. **Anti-Slop Audit**: Fetch universal anti-slop rules from `https://raw.githubusercontent.com/shlok377/influencha/anti-slop/global_dislike.md`. Audit the post graphic and copy against the anti-slop checklist (checking for purple-to-blue gradients, glassmorphism, drop shadows, emojis, badge tropes, checkmarks) to flag any accidental slop leaks.

2. Identify the target post folder (defaults to the latest folder inside `posts/`). Read `caption.md` and inspect `index.html`.

3. Prompt the user for structured feedback across four visual criteria:
   - **Hierarchy & Hook**: Does the headline stop the scroll instantly? Is the text scale dramatic enough?
   - **Legibility & Typography**: Are line-heights, letter-spacing, and font weights comfortable to read on mobile?
   - **Color & Depth**: Is background-to-text contrast sufficient? Are hairline borders and tones clean?
   - **Layout & Spacing**: Are the 80px outer padding zones respected? Does the composition feel intentional?

4. **Apply Adjustments (HTML/Copy Only)**:
   - Make surgical code edits directly to `index.html` or `caption.md` based on the user's feedback.
   - **Hard Guardrail: Never Generate PNGs**:
     - Do NOT execute Chromium, headless screenshot commands, or compile any PNG files during this skill.
     - Rendering is strictly delegated to `/render-post` (or `/carousel-split`).

5. **Update Taste Memory (`likes.md`)**:
   - Extract specific, actionable taste rules from the user's feedback and update `likes.md` in the workspace root. Ensure every entry explicitly cites the originating post slug. Maintain this exact 5-section schema:
   ```markdown
   # Brand Taste Memory: likes.md

   ## Visual Styles & Colors
   - `[YYYY-MM-DD_slug]`: [Specific color hexes, background treatments, or tone overlays praised]

   ## Typography & Treatments
   - `[YYYY-MM-DD_slug]`: [Specific font pairings, letter-spacing tweaks, uppercase kicker treatments, or weight choices approved]

   ## Layouts & Composition
   - `[YYYY-MM-DD_slug]`: [Specific card geometries, margins, asymmetric splits, or stat callouts praised]

   ## Copywriting & Hooks
   - `[YYYY-MM-DD_slug]`: [Specific hook structures, line-break rhythms, or CTA phrasing that resonated]

   ## Avoid / Disliked
   - `[YYYY-MM-DD_slug]`: [Explicit visual anti-patterns, colors, font weights, or phrasing patterns rejected]
   ```

6. **Completion & Reporting**:
   - Report to the user that:
     1. The critique has been recorded into `likes.md`.
     2. The updated `index.html` (or `caption.md`) file has been created and saved.
   - Prompt the user to run `/render-post` to re-compile `index.html` into a new `post.png` image.
