# Product Design Agent System

一个多 Agent 协作的产品设计工作流系统，将业务需求转化为可上线的运营视觉物料。

## 系统架构

```
用户原始需求 / 素材 / 参考图
  ↓
[0] Design System Intake（设计系统收集）
  - 收集 Logo / 主视觉 / 色彩 / 字体 / 组件 / 禁用项
  - 生成 Design System Contract
  ↓
[1] Business Design Brief（业务设计 Brief）
  - 业务目标
  - 用户动作
  - 信息层级 P0-P4
  - 尺寸策略
  - 视觉方向
  ↓
[2] Product Visual Designer（产品视觉设计师）
  - 使用真实素材
  - 使用真实字体
  - HTML/CSS/React/Figma-ready 实现
  - 导出 PNG
  ↓
[3] Product Visual Reviewer（独立视觉审核官）
  - 尺寸 / 文案 / Logo / 字体 / 资产 / 审美 / 可交付性
  - 输出 P0/P1/P2 Review Report
  ↓
[4] Orchestrator（产品设计总控）
  - P0 必改回流
  - P1 优先修改
  - P2 记录优化
  ↓
最终交付
```

## 四个 Agent 分工

### 1. Business Design Brief（业务设计 Brief）

**职责**：将原始业务需求翻译成可执行的设计 Brief。

**输入**：业务方的项目背景、目标用户、核心文案、物料类型、尺寸要求。

**输出**：
- 项目判断（业务目标、用户动作）
- 核心传播主张（一句话）
- P0-P4 信息层级表
- 多端适配策略
- 视觉策略（关键词、母题、色彩、字体、反方向）
- 作图 Prompt
- 验收标准

**触发时机**：业务方提出设计需求，需要先理清信息层级和视觉方向时。

---

### 2. Product Visual Designer（高级产品视觉设计师）

**职责**：按 Brief 生成可上线的运营视觉物料。

**核心规则**：
- 使用 HTML/CSS 或 React 布局，确保文字精确
- 所有文案用真实字体渲染，不用 AI 假字
- 直接使用品牌资产（Logo、符号），不重绘
- 尺寸精确到像素
- 风格克制、干净、平台级

**输出**：
- 最终 PNG（精确尺寸）
- 源文件（HTML/CSS/React/Figma）
- 资产引用清单
- 尺寸校验结果

**触发时机**：Brief 已确定，需要执行作图时。

---

### 3. Product Visual Reviewer（独立视觉审核官）

**职责**：独立审核已生成的视觉物料，不生成、不修改。

**审核维度**：
1. **生产正确性**：尺寸、透明角、文件名
2. **文字完整性**：中文准确、无乱码、真实字体
3. **品牌资产保真**：Logo 未重绘、未改色、比例正确
4. **布局与层级**：主信息可读、间距合理、CTA 清晰
5. **视觉审美**：平台感、克制、无 AI 装饰噪音
6. **禁用项合规**：用户明确禁止的元素

**输出**：P0/P1/P2/P3 分级 Review Report，含修改建议。

**触发时机**：视觉稿完成后，上线前必须过审。

---

### 4. Product Design Orchestrator（产品设计总控）

**职责**：协调整个工作流，是流程 Owner。

**核心规则**：
- 先冻结设计系统，再启动生产
- 设计师 ≠ 审核员，角色必须分离
- P0 必改、P1 优先修、P2 记录、P3 备注
- 根据任务范围灵活裁剪流程阶段

**工作流**：
1. Design System Intake
2. Business Design Brief
3. Asset and Export Contract Freeze
4. Visual Execution
5. Independent Review
6. Revision Loop
7. Delivery

**触发时机**：需要端到端协调完整设计流程时。

---

## 设计师与 AI 边界

```
AI 是设计生产力
设计师是设计责任人
Agent workflow 是把设计师判断标准变成可重复执行的系统
```

## 设计系统默认配置

当用户未提供设计系统时，使用以下默认值：

- **字体**：PingFang SC，fallback Noto Sans CJK SC / Microsoft YaHei
- **背景**：浅绿白弥散渐变
- **色调**：干净、克制、年轻、平台级
- **输出**：结构化 HTML/CSS、SVG、PPT 或 Figma-ready 布局

## 问题等级定义

| 等级 | 含义 | 处理 |
|---|---|---|
| P0 | 上线事故 / 必须打回 | 必改，不允许交付 |
| P1 | 影响效果 / 品牌一致性风险 | 原则上修改 |
| P2 | 审美 polish / 可优化 | 记录建议，视情况修改 |
| P3 | 备注 | 不阻塞 |

## 上线评分卡

| 模块 | 权重 |
|---|---:|
| 业务传达 | 25 |
| 信息层级 | 20 |
| 品牌一致性 | 20 |
| 视觉质量 | 20 |
| 可交付性 | 15 |

- 90+：可上线
- 80-89：需修 P1
- 70-79：方向可用但需重做
- <70：不建议上线

## 目录结构

```
product-design-agent-system/
├── business-design-brief/
│   ├── SKILL.md
│   └── agents/
│       └── openai.yaml
├── product-design-orchestrator/
│   ├── SKILL.md
│   ├── agents/
│   │   └── openai.yaml
│   └── references/
│       ├── design-system-contract.md
│       ├── export-contract.md
│       ├── product-design-workflow.md
│       └── review-contract.md
├── product-visual-designer/
│   ├── SKILL.md
│   └── agents/
│       └── openai.yaml
└── product-visual-reviewer/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

## 使用方式

### 在 MyFlicker 中使用

四个 Agent 作为独立 Skill 安装在 `user-skills/` 目录下，根据用户话语独立触发：

- "帮我写个设计 Brief" → `business-design-brief`
- "帮我做一张 Banner" → `product-visual-designer`
- "审核一下这张图" → `product-visual-reviewer`
- "帮我协调整个设计流程" → `product-design-orchestrator`

### 作为项目模板

直接复制本仓库目录结构，修改 SKILL.md 中的业务规则和视觉标准，即可适配自己的品牌。

## License

MIT