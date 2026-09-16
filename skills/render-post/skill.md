---
name: render-post
description: Compile an HTML/CSS graphic artboard into a high-resolution PNG image using headless Chromium. Use when compiling post.png from index.html or re-rendering after styling edits.
---

1. Identify the target post folder. Default to the latest folder inside `posts/` if not explicitly specified by the user.

2. Inspect `index.html` in that folder to determine the canvas aspect ratio:
   - Square: `1080x1080` (window-size: `1080,1080`)
   - Portrait: `1080x1350` (window-size: `1080,1350`)

3. Run the headless screenshot command in the shell:
   ```bash
   TARGET_DIR="posts/YYYY-MM-DD_<slug>"
   TARGET_HTML="$(pwd)/${TARGET_DIR}/index.html"
   TARGET_PNG="$(pwd)/${TARGET_DIR}/post.png"

   # Run Chromium or Google Chrome with a virtual-time-budget so Google Fonts finish loading
   chromium --headless --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${TARGET_PNG}" "file://${TARGET_HTML}" 2>/dev/null \
   || google-chrome --headless=new --disable-gpu --hide-scrollbars --window-size=1080,1080 --virtual-time-budget=3000 --screenshot="${TARGET_PNG}" "file://${TARGET_HTML}"
   ```

4. Verify compilation output:
   - Check that `post.png` exists.
   - Check that `post.png` has a non-trivial file size (greater than 15 KB).
   - If the file is 0 bytes or missing, inspect stderr and retry.

5. Present the rendered image to the user with a clickable file link and image preview:
   ```markdown
   Rendered: [post.png](file:///home/shlok377/Projects/influencha/posts/YYYY-MM-DD_<slug>/post.png)
   ```

6. Direct the user to run `/critique` to inspect the visual balance, suggest tweaks, and record approved design elements into `likes.md`.
