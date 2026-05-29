---
name: business-design-brief
description: Use when turning raw business, marketing, product launch, advertising, sales, projection, or operation-material requests into an executable design brief with target audience, business goal, P0-P4 hierarchy, visual strategy, exact pixel dimensions, coordinate safe zones, asset policies, prompt guidance, and acceptance criteria.
---

# Business Design Brief

Translate raw business requirements into an executable design brief. Do not generate final artwork.

## First Step: Risk Tier Classification

Before writing the brief, classify the request into one of three production-risk tiers. This decides what AI may deliver and where human designers must take responsibility.

| Tier | Scenario | AI Role | Designer Role | Risk |
|---|---|---|---|---|
| L1 Internal Basic Comms | internal activity posters, group notices, training covers, low-risk internal images | AI may produce final draft / final output | no involvement or sampling review | low |
| L2 Internal Large-Screen / Offline | TV projection, 4K/8K, large screens, roll-up banners, print materials | AI produces draft / direction only | 100% review and refinement before use | medium |
| L3 External / Customer-Facing | customer proposals, sales/招商 materials, brand ads, case studies, PR images | AI only supports brief, strategy, inspiration, references | designer must lead full production | high |

Automatic upgrade triggers:

- external customers or the public will see it: L3
- print, TV projection, large-screen, 4K, or 8K output: at least L2
- customer cases, customer data,达人/代言人/肖像, legal/compliance-sensitive content: L3
- cannot be changed after launch: at least L2
- typo or visual error could be screenshotted and spread: at least L2, L3 if external
- internal small group with low consequence: may remain L1

If the tier is unclear, ask the user to confirm before production. Do not silently downgrade risk.

Tier-specific output boundaries:

- L1: Brief + prompt + AI generation may proceed after ordinary checks.
- L2: full Brief + prompt + draft generation is allowed, but mark output as "待设计师审核/精修" and do not call it final production artwork.
- L3: output Brief, visual strategy, reference direction, and production checklist only. Do not generate or promise final artwork unless the user explicitly reframes the task as internal draft exploration.

## Core Principle

For exact-size materials, the brief must describe geometry, not just style. If the user gives a reference image, decide whether it is a style reference, content source, slicing source, layout template, or hard coordinate contract.

## Required Fields

1. Basic material info:
   - project name
   - material type
   - usage scene
   - target user
   - business goal
   - desired user action
- final canvas size
   - risk tier: L1 / L2 / L3

2. Coordinate contract:
   - canvas coordinate system
   - reserved / forbidden zones
   - allowed content zones
   - whether each zone may contain background only, decoration, or core content
   - any scale relationship, e.g. `1920×1080 template doubled to 3840×2160`

3. Information assets:
   - product name
   - launch event
   - core benefit
   - numeric hook
   - capability explanation
   - QR / CTA
   - bottom quote or fixed slogan
   - logo and brand marks

4. Asset policy:
   - direct reference supplied file
   - slice from reference poster
   - rebuild as editable HTML text
   - redraw allowed / forbidden
   - what text must remain one-word-for-word unchanged

5. Visual strategy:
   - style keywords
   - color direction
   - typography direction
   - component language
   - anti-directions

## Exact-Size Brief Output

For projection, TV, banner, popup, or any coordinate-specific request, output:

```markdown
# 设计 Brief

## 1. 项目判断
- 项目名称：
- 物料类型：
- 使用场景：
- 目标用户：
- 业务目标：
- 用户动作：
- 最终尺寸：
- 风险档位：L1 / L2 / L3
- AI 交付边界：

## 2. 坐标与安全区合同
| 区域 | 坐标 | 允许内容 | 禁止内容 |
|---|---|---|---|
| 区域1 | | | |
| 区域2 | | | |
| 区域3 | | | |

## 3. 内容资产合同
| 内容 | 文案 / 素材 | 处理方式 | 是否可改 |
|---|---|---|---|

## 4. 信息层级
| 层级 | 内容 | 设计处理 |
|---|---|---|

## 5. 视觉策略
- 视觉关键词：
- 色彩方向：
- 字体建议：
- 背景建议：
- 不建议方向：

## 6. 执行 Prompt

## 7. 验收标准
| 维度 | 标准 |
|---|---|
```

## Clarify Before Execution

Ask or explicitly state assumptions when any of these are missing:

- final output size
- exact forbidden-zone coordinates
- whether reference art must be sliced/reused or rebuilt
- whether text must be editable HTML or may be image slices
- QR source and whether it must remain scannable
- whether logo/symbol assets may be redrawn
