---
name: publish-guide
description: Guide the user step-by-step through uploading post graphics and publishing captions on Instagram. Use when a post is approved and ready to go live.
---

1. Identify the target post folder (defaults to the latest folder in `posts/`). Confirm that `post.png` (or `slide-*.png`) and `caption.md` exist.

2. Prepare the **Publication Bundle** and present it clearly to the user:
   - **Image Assets**: List absolute file paths for easy drag-and-drop into Instagram Web or mobile transfer:
     ```markdown
     [post.png](file:///home/shlok377/Projects/influencha/posts/YYYY-MM-DD_<slug>/post.png)
     ```
   - **Caption to Copy**: Provide a clean code block containing the exact caption text, spacing, and hashtag cluster ready for one-click copying.
   - **Alt Text**: Provide a 1-sentence descriptive accessibility summary of the graphic for Instagram's alt-text field.

3. Launch Instagram in the user's default browser:
   ```bash
   xdg-open "https://www.instagram.com/" 2>/dev/null || google-chrome "https://www.instagram.com/" 2>/dev/null || chromium "https://www.instagram.com/" 2>/dev/null
   ```

4. Guide the user through the upload steps:
   - Click the **+ Create** button on Instagram.
   - Drag and drop `post.png` (or all `slide-*.png` files in numerical order for carousels).
   - In the crop tool, select **Original** (or **4:5** for portrait).
   - Skip filters (the code-designed graphic is already color-graded).
   - Paste the caption into the text box.
   - Expand **Accessibility** and paste the provided Alt Text.
   - Tap **Share**.

5. After publishing, update `ideas.md` to mark the topic as **Published** with the publication date.
