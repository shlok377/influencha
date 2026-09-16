---
name: carousel-split
description: Design and batch-render multi-slide Instagram carousel posts using pure HTML/CSS. Use when creating 3-10 slide educational decks, breakdowns, or step-by-step tutorials. Strictly creates static slide artboards, never a dashboard.
---

1. **Hard Guardrail: Zero Dashboards, Zero Web Apps**
   - Each carousel slide is an isolated, static graphic artboard (1080x1080 or 1080x1350).
   - NEVER build a web slider component, interactive app, dashboard, or UI carousel widget. You are producing separate graphic images for Instagram.

2. Read `brand.md` for typography, color palette, and visual vibe. Read `likes.md` for approved layout patterns. Read `caption.md` for the slide outline and body copy.

3. Structure the carousel deck into 3 distinct slide types across a target folder `posts/YYYY-MM-DD_<topic-slug>/`:
   - **Slide 01 (Cover)**: Huge attention-grabbing headline, category pill tag, author handle, and a subtle "Swipe ➔" indicator.
   - **Slides 02 through N-1 (Content)**: Structured cards with a large step counter (`01`, `02`, etc.), bold sub-headline, clean body micro-copy, bottom pagination tracker (`2/6`), and consistent header watermark.
   - **Slide N (Outro & CTA)**: Summary card, high-contrast call-to-action ("Save this for reference", "Follow @handle for more"), and profile mark.

4. Write individual HTML files (`slide-01.html`, `slide-02.html`, ... `slide-N.html`) in the post folder. Ensure each slide is completely self-contained with embedded CSS and Google Fonts.

5. Batch-render every slide to high-res PNG using headless Chromium:
   ```bash
   TARGET_DIR="posts/YYYY-MM-DD_<slug>"
   for html_file in $(ls "${TARGET_DIR}"/slide-*.html | sort); do
     base=$(basename "$html_file" .html)
     output_png="${TARGET_DIR}/${base}.png"
     chromium --headless --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${output_png}" "file://$(pwd)/${html_file}" 2>/dev/null \
     || google-chrome --headless=new --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${output_png}" "file://$(pwd)/${html_file}"
   done
   ```

6. Verify that all PNG files (`slide-01.png`, `slide-02.png`, etc.) exist and are non-empty.

7. Display the rendered carousel sequence to the user and prompt them to run `/critique` to review the flow.
