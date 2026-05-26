---
name: product-visual-designer
description: Use when creating product launch operation visuals, PC/mobile banners, popup cards, campaign modules, or platform-level marketing assets that require precise dimensions, real text rendering, direct brand asset usage, HTML/CSS or React layout, PNG export, and visual iteration.
---

# Product Visual Designer

Create polished, platform-level product operation visuals with deterministic layout and export.

## Core Rules

- Use HTML/CSS or React for layout when text accuracy, exact size, or brand asset fidelity matters.
- Render all copy as real text. Do not use AI-generated text images for final production assets.
- Directly reference supplied brand assets such as logo PNGs and product symbol PNGs. Do not redraw, recolor, reshape, trace, or reinterpret them unless the user explicitly asks.
- Treat dimensions as non-negotiable. Export and verify exact pixel width and height.
- Use the requested font stack, preferring `PingFang SC` for Chinese when available.
- Keep visual style restrained, clean, and product-led. Avoid heavy poster effects, noisy decoration, and generic AI illustration.
- Preserve user-provided禁用项 exactly.

## Workflow

1. Parse the brief:
   - channel and size
   - hierarchy of copy
   - brand assets
   - layout order
   - color tokens
   - forbidden elements

2. Prepare assets:
   - copy source assets into the working folder when local browser rendering needs relative paths
   - keep original files unchanged
   - verify image dimensions before layout

3. Build the layout:
   - create a fixed-size HTML/CSS or React canvas
   - use real DOM text for every copy layer
   - place PNG assets with `<img>` or equivalent native image nodes
   - define stable absolute or grid positions for production-size materials
   - use only subtle shadows or glows when they improve hierarchy

4. Export:
   - render in a browser or reliable screenshot path
   - capture the exact canvas area
   - save the final PNG with the user-requested file name
   - if rounded transparent corners are needed, apply alpha masking after export

5. Verify:
   - pixel size matches the brief exactly
   - all text is accurate and readable
   - logo and supplied symbols are not modified
   - no forbidden symbols or visual elements appear
   - layout has sufficient breathing room and clear hierarchy

6. Iterate:
   - if the first version is visually weak, adjust spacing, scale, type hierarchy, and visual weight
   - do not change the content or brand assets unless required by the brief

## Design Taste Heuristics

- Prioritize information clarity before visual decoration.
- Use one strong focal asset, not many competing decorative elements.
- Make operation materials feel like product surfaces, not sale posters.
- For mobile popups, reserve generous vertical air around logo, title, visual, tag, and CTA.
- For PC banners, maintain single-line scanability and avoid oversized badges.
- Reduce glow before reducing clarity. Brand symbols should feel crisp and asset-like.

## Handoff To Review

After export, hand only these materials to the independent reviewer:

- original brief
- final PNG path
- source HTML/CSS or React path
- source asset paths
- dimension verification result

Do not include design rationale unless the reviewer explicitly asks. The reviewer must judge the output independently.
