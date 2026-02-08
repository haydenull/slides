---
layout: cover
background: /cover-part2.jpg
class: text-center
---

# 核心能力解析

## 五个核心能力

<div class="text-zinc-400 mt-6 text-xl">
本质统一：都是 Context 管理的不同维度
</div>

---
title: 为什么是这五个?
layout: cards
cards:
  - title: Rules
    desc: 持久化约束 → 全局上下文
    tags: ["团队共识", "全局生效"]
  - title: Commands
    desc: 固化交互 → 结构化输入
    tags: ["高频重复", "快捷指令"]
  - title: Skills
    desc: 领域封装 → 专业上下文
    tags: ["领域专长", "打包复用"]
  - title: SubAgents
    desc: 任务分解 → 隔离上下文
    tags: ["复杂任务", "分治策略"]
  - title: MCP
    desc: 外部连接 → 扩展上下文边界
    tags: ["外部数据源", "无限扩展"]
---

# 为什么是这五个?

<div class="text-center mt-8 text-zinc-400 italic">
从"本地代码"到"整个世界"的上下文管理体系
</div>

---
title: Rules — 持久化的团队共识
layout: two-cols-header
---

# Rules

<div class="text-center text-purple text-xl mb-6">
持久化的团队共识
</div>

::left::

**本质**

<div class="text-zinc-400 text-base">
全局的上下文约束，无需每次重复
</div>

**价值**

<div class="text-zinc-400 text-base">
将"隐性知识"显性化，让 AI 理解团队共识
</div>

**何时使用**

<div class="text-zinc-400 text-sm mt-2 space-y-1">
  <div>✅ 需要在所有对话中生效的规则</div>
  <div>✅ 团队编码规范、命名约定</div>
  <div>❌ 不要写太多（只写 AI 不知道的）</div>
</div>

::right::

**实战场景 1：编码风格**

```markdown
# .claude/rules/code-style.md
- 优先可读性 > 正确性 > 性能
- 不加显而易见的注释
- 避免过度设计
```

**实战场景 2：团队规范**

```markdown
# .claude/rules/naming.md
- 组件文件使用 PascalCase
- 工具函数文件使用 kebab-case
- 测试文件后缀 .test.ts
```

---
title: Commands — 固化成功的交互模式
layout: topics
topics:
  - title: "/commit 命令"
    desc: "自动收集 git status/diff/log，分析变更风格和影响范围，生成 conventional commit"
    audience: "高频重复工作流"
    icon: terminal
  - title: "/gitlab-code-review 命令"
    desc: "自动召回 PR diff 和相关测试，分析代码质量和潜在问题，生成结构化 review 建议"
    audience: "高频重复工作流"
    icon: code
---

# Commands

<div class="text-center text-blue text-xl mb-4">
固化成功的交互模式
</div>

<div class="text-center text-zinc-400 italic mb-6">
将"成功的上下文配置"固化成可复用指令
</div>

<div class="mt-6 text-center text-zinc-400 text-sm">
  <span class="text-zinc-500">从"每次告诉 AI 做什么"</span>
  <span class="mx-2 text-green">→</span>
  <span class="text-green">"一个指令搞定"</span>
</div>

---
title: Skills — 领域专长的上下文封装
layout: cards
cards:
  - title: Obsidian Skill
    desc: "触发词：写日记、周总结。上下文：vault 结构、模板、OKR。输出：结构化 markdown"
    tags: ["个人知识管理"]
  - title: Slidev Skill
    desc: "触发词：写 PPT、生成 slides。上下文：Slidev 语法、组件库。输出：可预览的 slides.md"
    tags: ["技术演讲"]
---

# Skills

<div class="text-center text-green text-xl mb-4">
领域专长的上下文封装
</div>

<div class="text-center text-zinc-400 italic mb-6">
将"特定任务所需的所有上下文"打包成一个技能
</div>

<div class="text-center text-zinc-300 mt-8">
让 AI "学会"一个领域，而不是每次从零教
</div>

<div class="text-center text-sm text-zinc-500 mt-4">
✅ 特定领域的复杂任务 &nbsp;&nbsp; ❌ 通用任务用 Commands
</div>

---
title: SubAgents — 复杂任务的分治策略
layout: timeline
timeline:
  - year: Step 1
    event: SubAgent-1 (Explore)
    desc: 分析目录、关键文件 → 输出组件位置与关联关系
  - year: Step 2
    event: SubAgent-2 (Plan)
    desc: 基于发现 → 制定分步骤重构计划
  - year: Step 3
    event: 主 Agent (执行)
    desc: 基于 Plan 逐步实施重构
---

# SubAgents

<div class="text-center text-orange text-xl mb-4">
复杂任务的分治策略
</div>

<div class="text-center text-zinc-400 italic mb-4">
将复杂问题拆解，每个子任务带着"恰到好处"的上下文独立执行
</div>

<div class="text-center text-zinc-500 text-sm mb-6">
<span class="text-zinc-400">示例场景：</span>用户要求重构遗留组件
</div>

---
title: MCP — 突破本地文件系统的边界
layout: cards
cards:
  - title: Context7 MCP
    desc: "查询最新技术文档，获取实时 API 参考和代码示例"
    tags: ["文档查询"]
  - title: Playwriter MCP
    desc: "浏览器自动化测试，获取可访问性快照和页面状态"
    tags: ["自动化测试"]
  - title: Exa MCP
    desc: "语义搜索网络内容，获取最新研究、代码示例、公司信息"
    tags: ["网络搜索"]
---

# MCP

<div class="text-center text-cyan text-xl mb-2">
突破本地文件系统的边界
</div>

<div class="text-center text-zinc-400 text-sm italic">
本地代码库 → 整个世界
</div>

---
title: 如何选择？决策树
layout: list
---

# 如何选择？


-  **需要全局生效的规范?** → <span class="text-purple">Rules</span>

- **高频重复的固定流程?** → <span class="text-blue">Commands</span>

- **特定领域的复杂任务?** → <span class="text-green">Skills</span>

- **任务很复杂需要分解上下文隔离?** → <span class="text-orange">SubAgents</span>

- **需要外部数据源?** → <span class="text-cyan">MCP</span>
