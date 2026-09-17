---
name: brand
description: Establish or refine the Instagram page's visual identity, aesthetic vibe, and brand guidelines in brand.md. Use when onboarding a new account, defining typography and color palettes, or auditing brand consistency.
---

1. **Anti-Slop Pre-Flight**: Fetch the universal anti-slop rules from `https://raw.githubusercontent.com/shlok377/influencha/anti-slop/global_dislike.md`. Use these rules as an absolute negative filter during the onboarding interview: NEVER suggest purple-to-blue gradients, glassmorphism, neon colors, raw pastels, soft 12px pill boxes, or badge-above-headline tropes.

2. Check if `brand.md` exists in the workspace root.
   - If `brand.md` exists: Read it, present a compact summary of the current identity, and ask the user what specific section (voice, typography, palette, archetypes) they want to refine.
   - If `brand.md` does not exist: Proceed directly with the 4-part onboarding interview.

3. Conduct the 4-part onboarding interview. Ask questions sequentially or in focused batches, giving concrete examples filtered against anti-slop rules:
   - **Part 1: Niche & Target Audience**: What is the core domain (tech, fitness, design, business, finance, culture)? Who is the ideal follower, and what emotion should the page evoke?
   - **Part 2: Aesthetic Vibe**: Choose a distinct design archetype (e.g., Swiss Typography, Brutalist Cyberpunk, Minimalist Editorial, Luxury Darkroom, Modern Monochromatic).
   - **Part 3: Visual Assets & Palette**:
     - *Colors*: 1 primary background, 1-2 foreground/text colors, 1 accent. Record exact hex/hsl codes.
     - *Typography*: 1 headline font (expressive, high-character) and 1 body font (ultra-legible) available on Google Fonts (e.g., `Syne` + `Inter`, `Cabinet Grotesk` + `General Sans`, `Playfair Display` + `Plus Jakarta Sans`).
     - *Visual Treatments*: Grain textures, sharp hairline borders, architectural grid geometry, or flat minimalism.
   - **Part 4: Content Archetypes**: The primary graphic types the page will publish (e.g., bold statement quotes, 3-point checklists, data/stat highlights, framework diagrams, curated resource lists).

4. When the user's answers are vague, contradictory, or generic, invoke the `/grill-me` skill pattern to stress-test decisions before writing the file.

5. Write the approved brand specification to `brand.md` in the workspace root using this structure:
   ```markdown
   # Brand Guide: [Account Name / Niche]

   ## 1. Positioning & Voice
   - **Niche**: [Domain]
   - **Target Audience**: [Who they are and what they care about]
   - **Voice & Tone**: [3-4 adjectives, e.g., Authoritative, Unapologetic, Direct]

   ## 2. Visual Identity & Tokens
   - **Aesthetic Vibe**: [Archetype name and visual description]
   - **Color Palette**:
     - Background: `#HEX` / `hsl(...)`
     - Foreground / Primary Text: `#HEX`
     - Secondary / Muted Text: `#HEX`
     - Accent: `#HEX`
   - **Typography (Google Fonts)**:
     - Display / Headline: `Font Name`, weights: `700, 900`
     - Body / Subhead: `Font Name`, weights: `400, 500, 600`
   - **Design Accents**: [Borders, border-radius, shadows, gradients, grain, glassmorphism rules]

   ## 3. Post Archetypes
   - [Archetype 1: description and layout focus]
   - [Archetype 2: description and layout focus]
   ```

6. Check if `likes.md` exists. If not, initialize `likes.md` with empty categorized sections ready to record future post feedback.
