---
name: product-visual-designer
description: Use when creating exact-size product launch operation visuals, TV projection screens, PC/mobile banners, popup cards, campaign modules, or platform-level marketing assets that require precise dimensions, coordinate safe zones, real text rendering or faithful reference slicing, direct brand asset usage, HTML/CSS layout, PNG export, and visual iteration.
---

# Product Visual Designer

Create polished, production-ready product operation visuals with deterministic layout and export.

## Core Rules

- Do not start final artwork until the brief and design/export contract are confirmed when exact dimensions, safe zones, or coordinate constraints exist.
- Respect the risk tier in the brief. L1 may be delivered as AI-final after verification. L2 outputs must be labeled and treated as draft/direction for designer review. L3 outputs must not be presented as final artwork; create strategy/reference/draft support only unless the user explicitly asks for internal exploration.
- Treat dimensions as non-negotiable.
- Treat safe zones and forbidden zones as hard boundaries. No text, logo, QR, card, icon, decoration, shadow, glow, cropped remnant, or HTML overflow may enter them unless the contract explicitly allows it.
- Use HTML/CSS or deterministic image composition for exact-size work.
- Render copy as real text when the contract requires editability. Use reference slicing when the contract prioritizes one-word-for-word visual fidelity from an existing poster.
- Directly reference supplied brand assets, QR codes, logos, and product symbols. Do not redraw, recolor, reshape, or reinterpret unless the contract allows it.
- Preserve all fixed copy exactly.
- Keep visual style restrained, clean, product-led, and suitable for the output channel.

## Workflow

1. Parse the confirmed contract:
   - final canvas size
   - coordinate system
   - reserved / forbidden zones
   - allowed content zones
   - required content and fixed text
   - asset policy
   - export format
   - risk tier and whether the output is final, draft, or strategy-only

2. Prepare assets:
   - copy source assets into the working folder
   - keep originals unchanged
   - verify dimensions
   - decide direct reference, slice reuse, or editable rebuild according to contract

3. Build the layout:
   - create a fixed-size canvas
   - place every element by explicit coordinates
   - keep right/bottom/top safety zones empty when required
   - for L-shaped regions, verify each element's bounding box is inside the allowed shape
   - account for shadows, glows, borders, and image alpha extents

4. Export:
   - save the final PNG with exact requested size
   - keep source HTML/assets reproducible
   - do not leave source HTML and PNG with different text or layout

5. Verify:
   - pixel dimensions match
   - forbidden zones contain background only
   - content zones contain all required elements
   - text is accurate
   - QR is unobstructed, unwarped, and has enough quiet zone
   - source file can reproduce the final image

## Coordinate Verification

For each forbidden zone, run an explicit check such as:

- inspect bounding boxes of all DOM / image elements
- sample or count high-contrast pixels in the forbidden zone
- manually inspect a screenshot at final size

If a zone must be "background only", remove even subtle labels, guide lines, decorations, and layout notes.

## Projection / TV Heuristics

- Prioritize large readable text and scannable QR over dense detail.
- Treat TV projection, 4K/8K, and print as at least L2: AI can draft, but designer review/refinement is required before real use.
- Keep reserved zones genuinely empty for TV UI, bezel, and viewing safety.
- Avoid thin text, low contrast, over-bright glow, and small explanatory copy.
- If a reference poster must be preserved, slice and reflow the poster elements rather than rewriting the copy from memory.

## Review Handoff

Hand the reviewer:

- confirmed brief / contract
- final PNG path
- source HTML path
- source asset paths
- expected dimensions
- forbidden-zone coordinates
- verification results
