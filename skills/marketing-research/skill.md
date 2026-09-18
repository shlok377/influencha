---
name: marketing-research
description: Dissect a product, project, or repo to extract star bragging points, scout live niche complaints, and formulate high-voltage Instagram post angles in ideas.md.
---

1. **Anti-Slop Pre-Flight**:
   - Fetch the universal anti-slop rules from `https://raw.githubusercontent.com/shlok377/influencha/anti-slop/global_dislike.md`.
   - **Strict Prohibition**: Ban all generic SaaS brochure jargon ("game-changer", "streamline your workflow", "unlock your potential", "all-in-one solution", "introducing XYZ"). Angles must read like unskippable organic content, never paid ads. Zero emojis in hooks.

2. **Product Intake (XYZ)**:
   - Identify the product or project from the user's input: a URL (landing page/docs), a local repo or file path (e.g., `README.md`, source code), or prompt text.
   - Extract three technical facts:
     - The **Superpower**: What does XYZ do faster, cheaper, or cleaner than existing tools?
     - The **Mechanism**: How does it physically achieve this (under the hood)?
     - The **Receipt**: What is a concrete stat, benchmark, before/after metric, or line-count delta?

3. **Live Problem Scouting (Market Friction)**:
   - Run targeted web searches against developer/user discussions (Reddit, X, forums) in the niche:
     - Search for common grievances, rants, and recurring bottlenecks related to the problem XYZ solves.
     - Identify what people hate about current market incumbents or manual workflows.
     - Pinpoint the exact vocabulary and frustration phrases practitioners use.

4. **Formulate the 4-Angle Framework**:
   Synthesize XYZ's superpowers with the live market friction into four distinct, high-resonance post angles:
   - **Angle 1: The Villain (The Roast)**
     - *Focus*: Attack the tedious, expensive, or broken status quo that everyone tolerates.
     - *Hook Style*: "Why 90% of [Audience] are wasting 10 hours a week on [Task]."
     - *Payoff*: Reveal XYZ as the common-sense alternative that kills the pain.
   - **Angle 2: The Unfair Advantage (The Flex)**
     - *Focus*: Lead with a hard, jaw-dropping benchmark, speed comparison, or cost flex.
     - *Hook Style*: "We replaced a [Legacy Tool / $X Expense] with [X Lines of Code / XYZ]."
     - *Payoff*: Show the benchmark graph or execution receipt.
   - **Angle 3: The Contrarian Truth (The Reality Check)**
     - *Focus*: Shatter a widely accepted industry dogma or bad advice.
     - *Hook Style*: "Stop doing [Popular Practice]. Here is what actually happens when you [Alternative]."
     - *Payoff*: Explain the underlying principle that XYZ was built upon.
   - **Angle 4: The Visual Receipt (Show, Don't Tell)**
     - *Focus*: A graphic designed around raw technical proof rather than narrative.
     - *Hook Style*: "[Task] in [Incumbent Tool] vs [Task] in XYZ."
     - *Payoff*: Side-by-side terminal output, architecture delta, or code diff.

5. **Commit to `ideas.md`**:
   - Locate or initialize `ideas.md` in the workspace root.
   - Append the four angles under a dedicated section:
     ```markdown
     # Marketing Angles: [Product Name]
     - Target Audience: [Domain & User Profile]
     - Core Villain: [The specific friction attacked]

     ### 1. The Villain: [Hook Headline]
     - Core Insight: [1-2 sentences on the broken old way]
     - Recommended Format: [Single Post / Carousel]

     ### 2. The Unfair Advantage: [Hook Headline]
     - Core Insight: [The hard flex or benchmark stat]
     - Recommended Format: [Single Post / Carousel]

     ### 3. The Contrarian Truth: [Hook Headline]
     - Core Insight: [The myth debunked]
     - Recommended Format: [Single Post / Carousel]

     ### 4. The Visual Receipt: [Hook Headline]
     - Core Insight: [The side-by-side visual proof structure]
     - Recommended Format: [Single Post / Carousel]
     ```

6. Present the four angles to the user with a recommended starting angle, and prompt them to run `/copy-hook` to begin drafting on-card copy and captions.
