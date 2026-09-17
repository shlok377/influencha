---
name: design-html
description: Exclusively code the HTML/CSS layout for a static Instagram graphic artboard in index.html. Never renders images and never builds web dashboards.
---

1. **Hard Guardrail: Zero Dashboards, Zero Web Apps**
   - You are designing a **static graphic poster**, exactly like a Canva or Figma artboard built with code.
   - **STRICT PROHIBITION**: NEVER build an Instagram dashboard, web app, feed viewer, UI kit, admin panel, navbar, or interactive web page.
   - The output must be an isolated, static visual graphic enclosed in an exact 1080px artboard with zero runtime JavaScript.

2. **Hard Guardrail: Code Only, Never Render Images**
   - This skill is **strictly for HTML and CSS authoring**.
   - **STRICT PROHIBITION**: NEVER execute Chromium, headless browsers, screenshot commands, or generate PNG files in this skill.
   - Rendering is the exclusive domain of `/render-post` (or `/carousel-split`). Stop immediately once `index.html` is written.

3. Read `brand.md` for typography pairings, color palette tokens, and aesthetic archetype. Read `likes.md` to incorporate approved visual treatments and strictly avoid anything in `Avoid / Disliked`.

4. Locate or create the target post folder: `posts/YYYY-MM-DD_<topic-slug>/`. Read `caption.md` in that folder for the exact on-card copy (kicker, headline, body micro-copy, and brand handle).

5. Construct a completely self-contained `index.html` file using this technical specification:
   - **Fixed Artboard Canvas**:
     ```html
     <!DOCTYPE html>
     <html lang="en">
     <head>
       <meta charset="UTF-8">
       <link rel="preconnect" href="https://fonts.googleapis.com">
       <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
       <!-- Import Google Fonts specified in brand.md -->
       <style>
         * { margin: 0; padding: 0; box-sizing: border-box; -webkit-font-smoothing: antialiased; }
         html, body {
           width: 1080px;
           height: 1080px; /* or 1350px for portrait 4:5 */
           overflow: hidden;
           background: #000;
         }
         .artboard {
           width: 1080px;
           height: 1080px;
           position: relative;
           overflow: hidden;
           display: flex;
           flex-direction: column;
           justify-content: space-between;
           padding: 80px;
         }
       </style>
     </head>
     <body>
       <div class="artboard">
         <!-- Visual content, header, hero typography, body, footer handle -->
       </div>
     </body>
     </html>
     ```

6. Apply visual craftsmanship:
   - **Typography**: Dramatic scale contrast between headline and body. Set tight line-height (`0.95` to `1.15`) for display titles, generous line-height (`1.4` to `1.6`) for body. Use deliberate letter-spacing (`letter-spacing: -0.03em` for bold titles, `+0.08em` for small uppercase kickers).
   - **Color & Depth**: Use rich color tokens from `brand.md`. Layer subtle linear or radial gradients, subtle glow halos, frosted glass panels (`backdrop-filter: blur(20px)`), and crisp hairline borders (`1px solid rgba(255,255,255,0.12)`).
   - **Accents**: Use inline SVG for icons, geometric accents, badges, or quotes. Do not use external image URLs that can fail or load slowly.
   - **Branding**: Include a subtle brand watermark or handle in the top or bottom margin.

7. Save the file to `posts/YYYY-MM-DD_<topic-slug>/index.html`. Verify that the file contains all necessary styles inline or in `<style>` blocks.

8. **Completion Boundary**: Stop here. Do not execute any bash screenshot commands or image tools. Inform the user that `index.html` has been saved and direct them to run `/render-post` to compile it to PNG.
