---
name: business-design-brief
description: Use when turning raw business, marketing, product launch, advertising, sales, or operation-material requests into an executable design brief with target audience, business goal, P0-P4 information hierarchy, visual strategy, multi-size adaptation plan, prompt guidance, and acceptance criteria.
---

# Business Design Brief

Translate business requirements into an executable design brief. Do not directly generate final artwork.

## Goal

Read the user's raw request like a senior commercial product designer. Identify the use scenario, target user, business goal, expected user action, information hierarchy, visual motif, delivery constraints, and acceptance criteria.

## Principles

- Business users do not need to speak in design language.
- Infer design strategy from goal, context, audience, and information priority.
- Ask only for missing information that materially blocks the brief.
- Do not default to AI image generation for final assets with Chinese text or exact dimensions.
- Prefer structured outputs such as HTML/CSS, SVG, PPT, or Figma-ready layouts for production.

## Workflow

1. Identify basic material information:
   - project name
   - business goal
   - material type
   - usage channel
   - scene
   - target user
   - desired user action
   - hard constraints
   - delivery count and sizes

2. Extract information assets:
   - product name
   - launch event
   - core benefit
   - numeric hook
   - capability explanation
   - trust proof
   - CTA
   - constraints

3. Assign information hierarchy:
   - P0: first-glance message
   - P1: core user benefit
   - P2: click or memory hook
   - P3: supporting explanation
   - P4: action button

4. Adapt by material type:
   - PC large popup: P0 + P1 + P2 + P3 + CTA
   - PC long banner: P0 + P1 + CTA
   - PC small banner: P0 + P2 + CTA
   - mobile popup: P0 + P2 + CTA
   - mobile banner: P1 + P2, minimal expression
   - sales poster: P0 + P1 + proof + CTA
   - report page: conclusion + structure + data + judgment

5. Translate business language into visual strategy:
   - visual keywords
   - visual motif
   - color direction
   - component language
   - background suggestion
   - anti-directions

## Output Format

```markdown
# 设计 Brief

## 1. 项目判断
- 项目名称：
- 物料类型：
- 使用场景：
- 目标用户：
- 业务目标：
- 用户动作：

## 2. 核心传播主张
一句话说明这张图要让用户记住什么。

## 3. 信息层级
| 层级 | 内容 | 设计处理 |
|---|---|---|
| P0 | | |
| P1 | | |
| P2 | | |
| P3 | | |
| P4 | | |

## 4. 多端适配策略
| 端 / 点位 | 尺寸 | 保留信息 | 删除 / 弱化信息 | 设计重点 |
|---|---|---|---|---|

## 5. 视觉策略
- 视觉关键词：
- 视觉母题：
- 色彩方向：
- 字体建议：
- 组件建议：
- 背景建议：
- 不建议方向：

## 6. 作图 Prompt
生成可直接用于视觉执行 Agent 的 prompt。

## 7. 验收标准
| 维度 | 标准 |
|---|---|
| 信息清晰 | |
| 场景适配 | |
| 品牌一致 | |
| CTA 明确 | |
| 多端可读 | |
| 上线安全 | |
```

## Quality Bar

- Must contain design judgment, not just restating the user's request.
- Must define P0-P4 hierarchy.
- Must include multi-size adaptation when multiple sizes are requested.
- Must include negative directions.
- Must preserve constraints around dimensions, fonts, buttons, logo, and supplied assets.
