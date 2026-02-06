---
paths:
  - "**/slides.md"
  - "**/*.slidev.md"
  - "**/src/part*.md"
description: Slidev Gemini Theme 布局和组件使用指南
---

# Slidev Gemini Theme 使用指南

## 主题概述

**slidev-theme-gemini** 是一个现代化的 Slidev 主题，提供 9 种精心设计的布局和丰富的动画效果。

- **版本**：0.1.0
- **设计理念**：科技感、渐变效果、流畅动画
- **技术栈**：Vue 3 + UnoCSS + Tailwind

### 安装配置

```json
// package.json
{
  "devDependencies": {
    "slidev-theme-gemini": "^0.1.0"
  }
}
```

```markdown
---
# slides.md
theme: gemini
---
```

---

## 布局清单

| 布局 | 使用场景 | 插槽 |
|------|---------|------|
| **cover** | 封面页、章节首页 | 默认 |
| **table** | 数据对比、多维度展示 | 默认 |
| **two-cols-header** | 左右对比、优劣分析 | 默认、left、right |
| **topics** | 功能/场景展示 | 默认 + Props |
| **cards** | 卡片式内容 | 默认 + Props |
| **timeline** | 时间线、流程 | 组件/Props |
| **list** | 编号列表 | 默认 |
| **default** | 通用内容 | 默认 |

---

## 布局详解

### 1. cover - 封面页

**使用场景**：演讲封面、章节分隔页

**特性**：
- 支持背景图自动缩放动画
- 文字居中显示
- 适合大标题展示

**示例代码**：

```markdown
---
layout: cover
background: /cover-part1.jpg
class: text-center
---

# 章节标题

## 副标题说明
```

**注意事项**：
- `background` 图片路径相对于 `public/` 目录
- 建议使用高分辨率图片（1920x1080 或更高）

---

### 2. table - 对比表格

**使用场景**：多维度对比、功能差异展示

**特性**：
- 渐变表头（深色背景）
- 悬停高亮行
- **第2、3列自动着色**：
  - 第2列：蓝色主题
  - 第3列：黄色主题
- 自动为第2、3列的 `code` 或 `span` 添加徽章样式

**示例代码**：

```markdown
---
layout: table
---

# 对比标题

| 维度 | Cursor | Claude Code |
|:-----|:-------|:-----------|
| 召回方式 | 向量化相似度 | bash/grep 搜索 |
| 召回范围 | 编辑器内 | 整个代码库 |
| 效率 | 高（向量检索快） | 低（暴力搜索慢） |
```

**自动样式说明**：
- 表头自动大写、加粗、间距优化
- 第2、3列内容自动居中
- 第2、3列的 code/span 自动添加彩色徽章（无需手动添加类名）

---

### 3. two-cols-header - 双列对比布局

**使用场景**：左右对比、优劣分析、概念对比

**布局结构**：
```
┌─────────────────────────────────────┐
│      默认插槽（标题/副标题）           │  ← 顶部，居中显示
├──────────────┬──────────────────────┤
│  ::left::    │      ::right::      │  ← 双列内容区
│  (左列)      │      (右列)         │
└──────────────┴──────────────────────┘
```

**插槽说明**：
- **默认插槽**：页面标题和副标题，位于双列**上方**，居中显示
- **`::left::`**：左列内容（延迟 500ms 显示）
- **`::right::`**：右列内容（延迟 650ms 显示）
- ⚠️ **不支持** `::bottom::` 插槽

**底部内容处理**：
如需放置到底部，需使用 CSS 定位（如 `absolute bottom-0`），放在默认插槽中。

**示例代码**：

```markdown
---
layout: two-cols-header
---

# 核心对比

<div class="text-center text-sm text-zinc-400 mb-6">
  <em>副标题或引用</em>
</div>

::left::

## 方案 A

<div class="text-zinc-400 mt-4 text-base">

**优点**：简单易用

**缺点**：功能受限

</div>

::right::

## 方案 B

<div class="text-zinc-400 mt-4 text-base">

**优点**：功能强大

**缺点**：学习曲线陡峭

</div>
```

**已知问题**：
- 如果需要底部内容，放在**默认插槽中**（标题下方）
- 不要使用 `::bottom::`，该插槽不存在

---

### 4. topics - 主题卡片

**使用场景**：多个功能/特性/场景展示

**Props 定义**：

```typescript
topics: Array<{
  title: string       // 卡片标题
  desc: string        // 描述文字
  audience: string    // 受众标签（显示在底部）
  hot?: boolean       // 是否高亮（橙色主题）
  hotLabel?: string   // 热门标签文字
  icon?: string       // 图标名称
}>
```

**可用图标**：
- `brain` → 🧠
- `sparkles` → ✨
- `terminal` → ⌨️
- `code` → 💻
- 其他 → ⚡（默认）

**示例代码**：

```markdown
---
layout: topics
topics:
  - title: IDE 更擅长
    desc: 极小快速修改、阅读代码、快速迭代
    audience: 开发者
    icon: code
  - title: Claude Code 更擅长
    desc: 跨文件重构、复杂任务分解
    audience: 开发者
    icon: sparkles
    hot: true
    hotLabel: 推荐
---

# 使用场景对比
```

**特性**：
- 响应式布局（移动端1列，桌面2列）
- 点击页面可切换高亮状态
- 热门卡片自动橙色主题

---

### 5. cards - 卡片网格

**使用场景**：功能列表、工具介绍、特性展示

**Props 定义**：

```typescript
cards: Array<{
  title: string       // 卡片标题
  desc: string        // 描述文字
  tags?: string[]     // 标签列表（可选）
}>
```

**示例代码**：

```markdown
---
layout: cards
cards:
  - title: 功能 A
    desc: 这是功能 A 的详细描述
    tags: ["稳定", "高性能"]
  - title: 功能 B
    desc: 这是功能 B 的详细描述
    tags: ["实验性"]
  - title: 功能 C
    desc: 这是功能 C 的详细描述
---

# 核心功能
```

**特性**：
- 自适应网格布局（最小卡片宽度 220px）
- 3种颜色主题循环（蓝、紫、绿）
- 悬停上浮动画（`-translate-y-2`）
- 标签徽章自动配色

---

### 6. default - 默认布局

**使用场景**：通用内容展示

**特性**：基础样式，无特殊布局结构

---

### 7. list - 列表布局

**使用场景**：步骤说明、编号要点、流程清单

**语法要求**：
- 必须使用 `- xxx` 无序列表语法
- 不要使用 `1. xxx` 有序列表语法（会导致样式异常）

**示例代码**：

```markdown
---
layout: list
---

# 步骤说明

- 第一步：安装依赖
- 第二步：配置环境
- 第三步：启动服务
```

**特性**：
- 自动生成编号徽章
- 渐进动画效果
- 适合有序列表

---

### 8. timeline - 时间轴

**使用场景**：时间线展示、发展历程、流程演进、步骤流程

**Props 定义**：

```typescript
timeline: Array<{
  year: string       // 阶段标识（显示为标题）
  event: string      // 事件/步骤名称
  desc: string       // 描述文字
}>
```

**示例代码**：

```markdown
---
layout: timeline
timeline:
  - year: Step 1
    event: SubAgent-1 (Explore)
    desc: 分析目录、关键文件 → 输出组件位置
  - year: Step 2
    event: SubAgent-2 (Plan)
    desc: 基于发现 → 制定重构计划
  - year: Step 3
    event: 主 Agent (执行)
    desc: 基于 Plan 逐步实施重构
---

# SubAgents

<div class="text-center text-orange text-xl mb-4">
复杂任务的分治策略
</div>

<div class="text-center text-zinc-400 italic">
将复杂问题拆解，每个子任务独立执行
</div>
```

**特性**：
- 横向时间轴布局，节省纵向空间
- 底部有时间轴线连接各阶段
- 最后一个节点自动高亮（橙色主题）
- 支持 3-4 个步骤，过多会导致拥挤
- 默认插槽（slot）可放标题和副标题

**注意事项**：
- 步骤数量建议控制在 3-4 个以内
- 描述文字保持简洁（单行或双行）
- `year` 字段不限于年份，可以是任何阶段标识（如 "Step 1"、"Phase A"）

---

## 常用样式类速查

### 文本样式

```css
/* 颜色 */
text-zinc-400      /* 次要文本（灰色） */
text-slate-300     /* 普通文本（浅灰） */
text-white         /* 高亮文本（白色） */

/* 字号 */
text-base          /* 基础字号（16px） */
text-sm            /* 小字号（14px） */
text-xs            /* 超小字号（12px） */
text-lg            /* 大字号（18px） */

/* 样式 */
italic             /* 斜体 */
font-bold          /* 加粗 */
font-semibold      /* 半粗 */
```

### 间距

```css
/* 外边距 */
mt-4 / mb-6        /* 上/下外边距（1rem / 1.5rem） */
mx-auto            /* 左右自动居中 */

/* 内边距 */
px-6 / py-4        /* 左右/上下内边距（1.5rem / 1rem） */

/* Gap（Grid/Flex 间距）*/
gap-8              /* 间距 2rem */
```

### 布局

```css
text-center        /* 文本居中对齐 */
grid="~ cols-2 gap-8"  /* UnoCSS 语法：双列网格 */
```

### 动画

```markdown
<!-- Slidev 内置点击渐显 -->
<div v-click>点击后显示的内容</div>
<div v-click>再次点击显示的内容</div>
```

---

## 最佳实践

### 1. 布局选择原则

| 需求场景 | 推荐布局 | 理由 |
|---------|---------|------|
| 数据对比、功能差异 | `table` 或 `two-cols-header` | 清晰的结构化展示 |
| 多个功能/特性展示 | `cards` 或 `topics` | 卡片式布局更直观 |
| 时间线、流程演进 | `timeline` | 视觉化时间概念 |
| 章节分隔、封面 | `cover` + `background` | 视觉冲击力强 |

### 2. 视觉一致性

- **颜色统一**：同一演讲中保持主题配色（zinc/slate/blue/purple/green）
- **布局风格**：避免在一个演讲中混用过多不同布局
- **动画节奏**：优先使用主题提供的渐进动画，避免手动 `v-click`（除非需要精确控制）

### 3. 响应式设计

- ✅ gemini theme 自动处理移动端适配
- ✅ 避免手动写死宽度（使用 `max-w-*` 而非固定 `w-[600px]`）
- ✅ 优先使用主题布局而非自定义 `grid`

### 4. 性能考虑

- 大型表格使用 `table` 布局（内置了性能优化）
- 避免在一页放置过多卡片（建议 ≤ 6 个）
- 图片使用合适分辨率，避免过大文件

---

## 已知问题和解决方案

### ❌ `two-cols-header` 不支持 `::bottom::` 插槽

**问题**：尝试使用 `::bottom::` 会导致内容不显示

**解决方案**：将底部内容放在**默认插槽中**（标题下方）

```markdown
---
layout: two-cols-header
---

# 标题

<div class="text-center text-zinc-400 mb-6">
  底部引用或副标题
</div>

::left::
左列内容
```

### ⚠️ 自定义样式覆盖

如需覆盖主题样式，在项目中创建 CSS 文件：

```markdown
---
# slides.md
css: unocss
---
```

或在 `src/styles/` 中创建自定义样式文件。

### ⚠️ frontmatter Props 传递

`topics`、`cards` 等布局的 Props 需要在 frontmatter 中定义：

```markdown
---
layout: topics
topics:
  - title: 标题
    desc: 描述
    audience: 受众
---
```

**不能**在 Markdown 正文中传递 Props（Vue 组件限制）。

### ⚠️ 表格第2、3列自动着色

`table` 布局会自动为第2、3列添加蓝色/黄色主题：

- 如果不希望着色，考虑使用普通 Markdown 表格（不用 `table` 布局）
- 第2、3列的 `code` 或 `span` 会自动添加徽章样式

---

## 参考资源

- **NPM 包**：`slidev-theme-gemini`
- **Slidev 官方文档**：https://sli.dev
- **UnoCSS 文档**：https://unocss.dev
- **Tailwind CSS 文档**：https://tailwindcss.com

---

## 示例项目结构

```
slides/
├── 2026-02-04/
│   └── src/
│       ├── slides.md              # 主幻灯片文件
│       ├── part1-repositioning.md # 使用 cover、table、two-cols-header、topics
│       ├── part2-mechanisms.md    # 使用 table、center
│       └── public/
│           └── cover-part1.jpg    # 背景图片
└── package.json                   # 包含 slidev-theme-gemini
```

---

## 快速决策树

**我需要展示...**

- 📊 数据对比表格 → `table`
- 🔀 左右对比（有标题）→ `two-cols-header`
- 🎴 多个功能卡片 → `cards` 或 `topics`
- ⏱️ 时间线/流程 → `timeline`
- 📋 编号列表 → `list`
- 🖼️ 封面/章节首页 → `cover`
- 📄 通用内容 → `default`

---

**版本**：基于 slidev-theme-gemini@0.1.0
**最后更新**：2026-02-05
