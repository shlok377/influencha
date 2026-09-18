---
name: carousel-split
description: Mechanically decompose an existing index.html into a multi-slide carousel deck (cover, body slides, ending) using the exact same CSS styles, and batch-render to PNGs.
---

1. **Hard Guardrail: Zero Dashboards, Zero Web Apps**
   - Each slide is an isolated, static 1080px graphic artboard. Never build an interactive slider or web app.

2. **Hard Guardrail: `index.html` is the Master Style Blueprint**
   - **STRICT PROHIBITION**: Do NOT invent new colors, fonts, backgrounds, or layouts.
   - You must copy the exact `<style>` block, font imports, background colors, and typography styles directly from `index.html`. All slides must share 100% visual consistency with the master design.

3. Identify the target post folder (defaults to the latest in `posts/`). Read `index.html` and `caption.md`.

4. **Deconstruct `index.html` into Exactly 3 Slide Types**:
   - **Slide 01 (`slide-01.html` - Cover)**:
     - Contains **ONLY the main headline**, brand handle/kicker, and a subtle "Swipe ➔" indicator.
     - **ZERO body copy or bullet points**. The cover must be ultra-bold, spacious, and uncluttered.
   - **Slides 02 through N-1 (`slide-02.html` ... `slide-N-1.html` - Middle Content)**:
     - Distribute the core insights, steps, or bullet points from `index.html` cleanly across slides (1 point/step per slide).
     - Include a large step counter (`01`, `02`), the bold subhead, tight micro-copy, pagination tracker (e.g., `2/5`), and consistent brand watermark.
   - **Slide N (`slide-N.html` - Ending)**:
     - Final summary takeaway, high-contrast call-to-action ("Save this post", "Follow @handle for more"), and brand mark.

5. Save each slide file (`slide-01.html`, `slide-02.html`, ... `slide-N.html`) in the post folder. Ensure each is completely self-contained with the cloned CSS from `index.html`.

6. Batch-render every slide to high-resolution PNG using headless Chromium:
   ```bash
   TARGET_DIR="posts/YYYY-MM-DD_<slug>"
   for html_file in $(ls "${TARGET_DIR}"/slide-*.html | sort); do
     base=$(basename "$html_file" .html)
     output_png="${TARGET_DIR}/${base}.png"
     chromium --headless --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${output_png}" "file://$(pwd)/${html_file}" 2>/dev/null \
     || google-chrome --headless=new --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${output_png}" "file://$(pwd)/${html_file}"
   done
   ```

7. Verify that all PNG files (`slide-01.png`, `slide-02.png`, etc.) exist and are non-empty (> 15 KB).

8. Present the rendered carousel sequence to the user and prompt them to run `/critique` if they want to adjust the copy or flow.
