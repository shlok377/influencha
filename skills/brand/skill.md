---
name: brand
description: Interrogate and define the Instagram page's high-character visual identity, aesthetic archetype, brand villain, and design system in brand.md using the grill-me interrogation protocol.
---

1. **Anti-Slop Pre-Flight**:
   - Fetch the universal anti-slop rules from `https://raw.githubusercontent.com/shlok377/influencha/anti-slop/global_dislike.md`.
   - **Strict Prohibition**: Never suggest, propose, or accept purple-to-blue gradients, glassmorphism, neon colors, raw pastels, soft 12px pill boxes, or badge-above-headline tropes.

2. **Check State**:
   - If `brand.md` exists: Display an executive summary of the current brand constitution and ask which pillar (Voice, Villain, Typography, Palette, Anti-Audience) the user wants to stress-test or refine.
   - If `brand.md` does not exist: Initiate the **Brand Interrogation Protocol**.

3. **The Brand Interrogation Protocol (`/grill-me` Engine)**:
   - Execute an adversarial, structured interrogation in rounds using the `/grill-me` format (`❓ Q - <title>: <body>` followed by `➡️ <recommended answer>`). Never be a passive "yes-man" that accepts generic descriptors like "clean", "minimalist", or "modern".
   
   - **Round 1: Splitting Vague Descriptors into Binary Aesthetic Lanes**
     - When the user mentions an aesthetic, refuse vague generalities and force a fork into two mutually exclusive visual philosophies:
       - *Lane A (e.g., German Swiss Industrial)*: Pure high-contrast monochrome, zero rounded corners (`border-radius: 0px`), hairline architectural grid lines, monospace kicker tags, and massive uppercase typography.
       - *Lane B (e.g., Silicon Valley Architectural Editorial)*: Deep obsidian canvas, warm off-white tones, subtle tone-on-tone panels, and high-character display fonts paired with clinical body sans.
     - Recommend the sharper lane and force an explicit choice.

   - **Round 2: The Brand Enemy & Core Villain**
     - Interrogate what industry practice, cliché, or bad habit the page actively opposes.
     - Ask: *"What widely accepted practice in your niche makes you physically cringe? What is the villain our content will attack?"* (e.g., over-engineering, tutorial hell, fake guru fluff, generic AI wrappers).

   - **Round 3: The Anti-Audience & Tone Boundaries**
     - Interrogate who this page is EXPLICITLY NOT FOR. Define exclusivity:
     - Ask: *"If a casual beginner finds our posts too dense or intimidating, is that a bug or a feature? What will our brand voice NEVER sound like?"* Establish 3 strict negative tone guardrails.

   - **Round 4: Visual Polarities & Concrete Tokens**
     - Lock down exact physical design tokens:
       - *Colors*: 1 primary background (ban raw `#ffffff`), 1 primary text, 1 muted text, 1 accent.
       - *Typography*: 1 display font and 1 body font from Google Fonts with specific weights (e.g., `Syne 800` + `Plus Jakarta Sans 400/600`).
       - *Geometric Polarities*: Strict rule on border-radius (`0px` vs custom geometry), margins (`80px`), and framing rules.

4. **Synthesize `brand.md`**:
   Write the resulting opinionated brand constitution to `brand.md` in the workspace root using this schema:
   ```markdown
   # Brand Constitution: [Account Name / Domain]

   ## 1. Positioning & Voice
   - **Niche**: [Exact domain]
   - **Target Audience**: [Who they are and what high-level problems they face]
   - **The Anti-Audience**: [Who this content explicitly excludes or filters out]
   - **Voice & Tone**: [3-4 punchy adjectives, e.g., Unapologetic, Surgical, Authoritative]
   - **Tone Guardrails**: [Phrases and attitudes this brand will NEVER use]

   ## 2. The Brand Villain & Core Philosophy
   - **The Core Villain**: [The industry practice, cliché, or scam we attack]
   - **The Core Belief**: [The counter-intuitive truth our content champions]

   ## 3. Visual Identity & Design System
   - **Aesthetic Archetype**: [Distinct lane chosen with visual description]
   - **Color Palette**:
     - Background: `#HEX` / `hsl(...)` (no raw white)
     - Foreground / Primary Text: `#HEX`
     - Secondary / Muted Text: `#HEX`
     - Accent: `#HEX`
   - **Typography (Google Fonts)**:
     - Display / Headline: `Font Name`, weights: `700, 800, 900`
     - Body / Subhead: `Font Name`, weights: `400, 500, 600`
   - **Geometric Polarities**:
     - Border Radius: `0px` (or exact architectural rule)
     - Outer Margin: `80px` fixed padding
     - Line Height & Kerning: Tight display (`0.95-1.05`), tracked kickers (`+0.08em`)

   ## 4. Post Archetypes
   - [Archetype 1: e.g., The Villain Roast - Layout focus & typography priority]
   - [Archetype 2: e.g., The Architecture Breakdown - Layout focus & structure]
   - [Archetype 3: e.g., The Contrarian Statement - Layout focus & quote hierarchy]
   ```

5. **Initialize Taste Memory**:
   - Check if `likes.md` exists. If missing, initialize `likes.md` with empty categorized sections ready to record post critiques.
