---
name: make-post
description: Open the visual workflow guide in the browser mapping the complete Instagram post creation lifecycle. Use when starting a new post, deciding which skill to reach for, or orienting yourself in the workflow.
---

1. Check if the project already contains `brand.md`. If missing, remind the user to run `/brand` first to establish their page identity before producing content.

2. Open the visual workflow guide directly in the default browser using the raw GitHub repository link:
   ```bash
   xdg-open "https://raw.githubusercontent.com/shlok377/influencha/main/process.html" 2>/dev/null || google-chrome "https://raw.githubusercontent.com/shlok377/influencha/main/process.html" 2>/dev/null || chromium "https://raw.githubusercontent.com/shlok377/influencha/main/process.html" 2>/dev/null
   ```

3. Present a concise terminal summary pointing the user to the workflow guide and prompt them with the logical next action based on whether `brand.md` or a target post topic already exists.
