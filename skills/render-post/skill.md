---
name: render-post
description: Mechanically compile an existing HTML/CSS graphic into a high-resolution PNG image using headless Chromium. Never modifies or regenerates the HTML.
---

1. **Hard Guardrail: Read-Only HTML (Zero Modifications)**:
   - **STRICT PROHIBITION**: NEVER edit, rewrite, modify, re-generate, or touch `index.html` or `caption.md`.
   - You are an **uncompromising, mechanical headless compiler**. Your sole purpose is to convert the exact code already on disk into a PNG. Any modification to the HTML is a critical failure.

2. Identify the target post folder (defaults to the latest folder inside `posts/`). Confirm that `index.html` exists on disk.

3. Inspect `index.html` in that folder only to determine the canvas dimensions:
   - Square: `1080x1080` (window-size: `1080,1080`)
   - Portrait: `1080x1350` (window-size: `1080,1350`)

4. Run the headless screenshot command immediately against the untouched file:
   ```bash
   TARGET_DIR="posts/YYYY-MM-DD_<slug>"
   TARGET_HTML="$(pwd)/${TARGET_DIR}/index.html"
   TARGET_PNG="$(pwd)/${TARGET_DIR}/post.png"

   # Execute Chromium or Chrome with virtual-time-budget for font stabilization
   chromium --headless --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${TARGET_PNG}" "file://${TARGET_HTML}" 2>/dev/null \
   || google-chrome --headless=new --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${TARGET_PNG}" "file://${TARGET_HTML}"
   ```

5. Verify compilation output:
   - Check that `post.png` exists and is non-empty (> 15 KB).
   - If missing or 0 bytes, check stderr and retry without touching the HTML.

6. Present the rendered image to the user:
   ```markdown
   Rendered: [post.png](file:///home/shlok377/Projects/influencha/posts/YYYY-MM-DD_<slug>/post.png)
   ```

7. Direct the user to run `/critique` if they want to review or suggest visual tweaks to the HTML.
