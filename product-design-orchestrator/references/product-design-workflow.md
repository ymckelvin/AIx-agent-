# Product Design Workflow

## 流程图

```text
用户原始需求 / 素材 / 参考图
  ↓
[0] Design System Intake
  - 收集 Logo / 主视觉 / 色彩 / 字体 / 组件 / 禁用项
  - 生成 Design System Contract
  ↓
[1] Business Design Agent
  - 业务目标
  - 用户动作
  - 信息层级 P0-P4
  - 尺寸策略
  - 视觉方向
  ↓
[2] Product Visual Designer
  - 使用真实素材
  - 使用真实字体
  - HTML/CSS/React/Figma-ready 实现
  - 导出 PNG
  ↓
[3] Product Visual Reviewer
  - 尺寸 / 文案 / Logo / 字体 / 资产 / 审美 / 可交付性
  - 输出 P0/P1/P2 Review Report
  ↓
[4] Orchestrator
  - P0 必改回流
  - P1 优先修改
  - P2 记录优化
  ↓
最终交付
```

## 设计师与 AI 边界

AI 负责生成、穷举、执行、校验；设计师负责判断、取舍、定义标准、对结果负责。

```text
AI 是设计生产力
设计师是设计责任人
Agent workflow 是把设计师判断标准变成可重复执行的系统
```
