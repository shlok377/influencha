---
name: copy-hook
description: Draft scroll-stopping headline hooks, on-card micro-copy, Instagram captions, and hashtag groups. Use when writing copy for a new post or refining caption text in caption.md.
---

1. **Anti-Slop Pre-Flight**: Fetch the universal anti-slop rules from `https://raw.githubusercontent.com/shlok377/influencha/anti-slop/global_dislike.md`. Strictly enforce:
   - **Zero Emojis**: NEVER use emojis in headlines, subheads, body copy, visual cards, or captions. Rely on typography and visual structure.
   - **No Checkmark Bullets**: Never use `✓` or `✔` symbols for list items.
   - **No AI Buzzwords**: Ban corporate/AI cliché terms ("delve", "game-changer", "unlock your potential", "tapestry", "mastering X").

2. Read `brand.md` (for brand voice, tone, and audience) and `likes.md` (specifically the `Copywriting & Hooks` and `Avoid / Disliked` sections).

3. Identify the target post topic from the user's prompt or the active item in `ideas.md`.

4. Craft the **On-Card Visual Copy** (text that will physically render inside the HTML/CSS graphic):
   - **Headline Hook**: 3 to 8 words maximum. Must provoke curiosity, challenge an assumption, or declare a bold premise. Never use passive corporate jargon.
   - **Support Micro-copy**: 1-2 tight sentences or 3 concise bullet points. Words must be chosen for graphic economy—every syllable must earn its visual footprint on a 1080px canvas.

5. Craft the **Instagram Post Caption**:
   - **First Line**: An irresistible hook that demands the viewer tap "...more".
   - **Body**: 2 to 4 short, single-sentence paragraphs expanding on the graphic's premise with zero fluff. Use clean line breaks.
   - **Call-to-Action (CTA)**: A single low-friction prompt (e.g., "Save this before starting your next sprint", "Comment your biggest bottleneck").
   - **Hashtag Cluster**: 5 to 8 niche-specific, relevant hashtags. Avoid saturated generic tags (#love, #viral, #instagram).

6. Determine the post directory: `posts/YYYY-MM-DD_<topic-slug>/`. Create the directory if it does not exist, and write the caption to `caption.md`:
   ```markdown
   # Caption: [Topic Title]

   ## On-Card Text
   - **Kicker / Category**: [Small uppercase tag]
   - **Headline**: [Main bold hook]
   - **Body / Bullets**: [On-graphic micro-copy]

   ## Instagram Caption
   [Hook line]

   [Body paragraph 1]

   [Body paragraph 2]

   [CTA line]

   .
   .
   [Hashtags separated by spaces]
   ```

7. Output the copy for the user to review. Proceed to `/design-html` once confirmed.
