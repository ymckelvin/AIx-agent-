---
name: product-design-orchestrator
description: Use when coordinating a full product design workflow across design-system intake, business design brief, coordinate/safe-zone contracts, visual execution, independent review, revision loops, and delivery for exact-size product launch visuals, operation banners, TV projection materials, popups, infographics, or multi-size marketing assets.
---

# Product Design Orchestrator

Coordinate the product design workflow. Keep strategy, execution, and review separate.

## Core Rules

- Freeze brand rules before production whenever assets are available.
- Classify every design request into L1 / L2 / L3 before deciding whether AI may produce a final artifact.
- L1 internal basic comms may be AI-final with checks. L2 large-screen/offline/print materials are AI drafts requiring designer review/refinement. L3 external/customer-facing/compliance-sensitive materials are designer-led; AI provides brief, strategy, inspiration, and references only.
- Automatically upgrade to L3 if customers/public will see it, customer data/cases are involved, or celebrity/达人/肖像/legal/compliance risk exists. Automatically upgrade to at least L2 for print, TV projection, large screen, 4K/8K, or irreversible launch.
- For exact-size materials with safe zones, forbidden zones, TV projection constraints, or coordinate-based layouts, do not proceed directly to visual execution.
- First produce a Business Design Brief and a Design / Export Contract, then wait for explicit user confirmation such as "OK", "按这个做", or "生图吧".
- Coordinates are contract-level constraints. Treat zones such as `x=1350-1920` or `420×250` as hard production boundaries, including shadows, glows, decorations, cropped remnants, and HTML overflow.
- Logo, QR codes, reference posters, supplied symbols, color, font, and forbidden items are contract-level constraints.
- Product Visual Designer must not be treated as the final reviewer.
- Product Visual Reviewer must be independent and must not edit the artwork.
- If the user changes the intended layout, update the brief/contract first, then revise artwork.

## Standard Flow

1. Design System Intake
2. Business Design Brief
3. Coordinate / Safe-Zone Contract, when dimensions or reserved regions are involved
4. User Confirmation
5. Asset and Export Contract Freeze
6. Visual Execution
7. Independent Review
8. Revision Loop
9. Delivery

## Exact-Size Material Gate

Use this gate for TV projection materials, banners, popups, large screens, or any request with exact pixel sizes, safe areas, forbidden areas, or templates.

Before production, confirm:

- risk tier and AI delivery boundary
- final canvas size and scale, e.g. `1920×1080` or `3840×2160`
- reserved / forbidden zones as coordinates, e.g. `area1 = x=0-420, y=0-250`
- content zones as coordinates or shapes, e.g. `area3 = remaining L-shaped area`
- whether zones are equal grid regions, template safe zones, or irregular layout regions
- what content must appear, what must be unchanged, and what can be omitted
- source-asset policy: direct reference, slice from reference, editable HTML text, or redraw
- text contract: exact copy that must not change
- export files and acceptance checks

## User Confirmation Prompt

Before execution, summarize:

- canvas size
- risk tier and who owns final approval
- forbidden zones
- allowed content zones
- required content
- asset policy
- text that cannot change
- export and verification plan

Then ask the user to confirm. Do not generate final artwork until confirmed.

## Default Design System

Use only when the user has not supplied a design system:

- font: PingFang SC with common Chinese sans-serif fallbacks
- background: light green-white diffused gradient
- tone: clean, restrained, young, platform-level
- output: structured HTML/CSS, SVG, PPT, or Figma-ready layout before bitmap export

## Review Handoff

Include only:

- confirmed brief and contract
- final PNG or HTML path
- source asset paths
- expected dimensions and coordinate constraints
- verification results

Do not include the designer's self-justification unless the reviewer asks for it.
