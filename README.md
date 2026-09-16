# influencha

A modular suite of AI agent skills for crafting high-impact Instagram posts using pure code (HTML & CSS), headless Chromium rendering, and iterative taste memory.

## Philosophy

- **Code-Crafted Visuals**: Posts are not AI-generated images or generic Canva templates. They are precision-engineered graphic artboards built with standard HTML, CSS typography, gradients, glassmorphism, and inline SVGs.
- **Strictly No Dashboards**: No web apps, no admin panels, and no UI kits. Every output is an isolated static graphic (1080x1080 square or 1080x1350 portrait) rendered directly to high-resolution PNG.
- **Evolving Taste Memory**: Your feedback is continuously recorded in `likes.md`, training the agent on what visual treatments, typography pairings, and layout structures you love and which anti-patterns to avoid.

---

## The Skill Suite

The repository contains 10 standalone, modular skills under `skills/`:

| Command | Skill | Description |
|---|---|---|
| `/make-post` | [make-post](skills/make-post/skill.md) | Launches a local visual workflow guide in the default browser mapping out all available skills. |
| `/brand` | [brand](skills/brand/skill.md) | Conducts a 4-part onboarding interview to define typography, color palette, voice, and vibe in `brand.md`. |
| `/trend-scout` | [trend-scout](skills/trend-scout/skill.md) | Researches trending angles, viral hooks, and high-resonance topics in your niche into `ideas.md`. |
| `/copy-hook` | [copy-hook](skills/copy-hook/skill.md) | Crafts scroll-stopping visual headline hooks, on-card micro-copy, captions, and hashtag groups in `caption.md`. |
| `/design-html` | [design-html](skills/design-html/skill.md) | Generates pure HTML/CSS code for static graphic artboards (1080px canvas, Google Fonts, gradients, SVGs). |
| `/render-post` | [render-post](skills/render-post/skill.md) | Compiles `index.html` to high-resolution `post.png` via headless Chromium with font preloading. |
| `/carousel-split` | [carousel-split](skills/carousel-split/skill.md) | Builds sequential multi-slide carousel graphics (`slide-01.html`, etc.) and batch-renders them into PNGs. |
| `/critique` | [critique](skills/critique/skill.md) | Interactive visual review: applies design refinements and curates approved patterns and anti-patterns into `likes.md`. |
| `/grid-preview` | [grid-preview](skills/grid-preview/skill.md) | Simulates an Instagram 3x3 profile grid locally to inspect color rhythm, variety, and typographic cadence. |
| `/publish-guide` | [publish-guide](skills/publish-guide/skill.md) | Prepares ready-to-copy caption bundles, alt-text, and provides step-by-step guidance for publishing on Instagram Web. |

---

## Workflow Overview

```
   [ /brand ] (Establish brand.md & initial identity)
       │
       ▼
 [ /trend-scout ] (Brainstorm high-resonance hooks into ideas.md)
       │
       ▼
  [ /copy-hook ] (Draft headline, on-card micro-copy, and caption.md)
       │
       ▼
 [ /design-html ] (Code standalone 1080px HTML/CSS artboard)
       │
       ▼
 [ /render-post ] (Compile index.html -> post.png via headless Chromium)
       │
       ▼
   [ /critique ] (Review aesthetics, refine code, update likes.md)
       │
       ▼
 [ /grid-preview ] (Verify feed harmony in 3x3 grid simulation)
       │
       ▼
[ /publish-guide ] (Copy assets & caption to Instagram Web)
```

---

## Prerequisites

- **Chromium / Google Chrome**: Required for headless rendering (`chromium` or `google-chrome` command available in PATH).
- **Git**

## License

MIT
