---
name: make-post
description: Launch a visual workflow guide in the browser mapping the complete Instagram post creation lifecycle. Use when starting a new post, deciding which skill to reach for, or orienting yourself in the workflow.
---

1. Check if the project already contains `brand.md`. If missing, tell the user to run `/brand` first to establish their page identity before producing content.

2. Generate a clean, modern, standalone HTML workflow guide at `guide.html` in the workspace root. The guide must visually map out the complete standalone skill suite:
   - **Phase 1: Foundation & Discovery**
     - `/brand`: Onboarding interview and style identity specification (`brand.md`).
     - `/trend-scout`: Viral angles, trending topics, and market research (`ideas.md`).
   - **Phase 2: Content & Copy**
     - `/copy-hook`: Scroll-stopping headline hooks, slide micro-copy, captions, and hashtag groups.
   - **Phase 3: Visual Design & Craft**
     - `/design-html`: Pure HTML/CSS static graphic artboard (1080x1080 or 1080x1350).
     - `/carousel-split`: Multi-slide carousel HTML structures with swipe cues and pagination.
   - **Phase 4: Headless Compilation**
     - `/render-post`: Chromium headless screenshot rendering to high-res PNG (`post.png`).
   - **Phase 5: Taste & Coherence**
     - `/critique`: Visual review, revision loop, and updating preference memory (`likes.md`).
     - `/grid-preview`: 3x3 feed layout simulation to check aesthetic flow and color balance.
   - **Phase 6: Distribution**
     - `/publish-guide`: Step-by-step browser publishing copilot for Instagram web.

3. **Hard Guardrail**: The guide is a static local reference document explaining the skills. Do NOT build an Instagram dashboard web app, admin UI, or backend service.

4. Open `guide.html` in the user's default browser:
   ```bash
   xdg-open file://$(pwd)/guide.html 2>/dev/null || google-chrome file://$(pwd)/guide.html 2>/dev/null || chromium file://$(pwd)/guide.html 2>/dev/null
   ```

5. Present a concise terminal summary pointing the user to `guide.html` and prompt them with the logical next action based on whether `brand.md` or a target post topic already exists.
