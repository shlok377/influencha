# Influencha 📸

A modular suite of AI agent skills for crafting high-impact Instagram posts using pure HTML/CSS, headless Chromium rendering, and iterative taste memory.

---

## ⚡ Download Skill

Prompt your LLM with one of the following commands:

### 1. Exclusive to a Project
> Prompt your LLM: Install https://github.com/shlok377/influencha skill exclusively for this project/directory

### 2. Global (For All Projects)
> Prompt your LLM: Install https://github.com/shlok377/influencha skill globally for all projects

---

## 🛠️ Slash Skills & Use Cases

| Command | Skill | Use Case |
|---|---|---|
| `/make-post` | [make-post](skills/make-post/skill.md) | Launches the interactive workflow guide mapping out the complete post creation lifecycle. |
| `/brand` | [brand](skills/brand/skill.md) | Conducts an onboarding interview to define typography, color palette, voice, and vibe in `brand.md`. |
| `/trend-scout` | [trend-scout](skills/trend-scout/skill.md) | Researches viral angles, trending topics, and content opportunities in your niche into `ideas.md`. |
| `/copy-hook` | [copy-hook](skills/copy-hook/skill.md) | Drafts scroll-stopping headline hooks, on-card micro-copy, captions, and hashtags in `caption.md`. |
| `/design-html` | [design-html](skills/design-html/skill.md) | Codes pure HTML/CSS graphics (1080px canvas, typography, gradients, SVGs) into `index.html`. |
| `/render-post` | [render-post](skills/render-post/skill.md) | Compiles `index.html` to high-resolution `post.png` via headless Chromium. |
| `/carousel-split` | [carousel-split](skills/carousel-split/skill.md) | Builds multi-slide carousel graphics (`slide-01.html`, etc.) and batch-renders PNGs. |
| `/critique` | [critique](skills/critique/skill.md) | Conducts visual review, refines code, and saves preferences and anti-patterns into `likes.md`. |
| `/grid-preview` | [grid-preview](skills/grid-preview/skill.md) | Simulates a 3x3 Instagram profile grid to verify feed harmony and visual rhythm. |
| `/publish-guide` | [publish-guide](skills/publish-guide/skill.md) | Prepares ready-to-copy caption bundles and guides manual publishing on Instagram Web. |
| `/research` | [research](skills/research/skill.md) | Deep-dives into research questions against primary sources and captures findings in markdown files. |
| `/grill-me` | [grill-me](skills/grill-me/skill.md) | Stress-tests plans, ideas, and decisions through structured interrogation. |
| `/handoff` | [handoff](skills/handoff/skill.md) | Compiles a session handoff document for another agent to seamlessly continue work. |

---

## 🔄 Recommended Workflow

```
[ /brand ]
[ /trend-scout ]
[ /copy-hook ]
[ /design-html ]
[ /critique ]
[ /render-post ] OR [ /carousel-split ]
[ /publish-guide ]
```

---

## ⚙️ Prerequisites

- **Chromium / Google Chrome**: Headless browser rendering (`chromium` or `google-chrome` binary in PATH).
- **Git**

---

## 📜 License

MIT
