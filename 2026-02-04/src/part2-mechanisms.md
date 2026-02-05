---
layout: section
---

# 核心能力解析 — 五个核心能力 {#part2 .view-transition-title-2}

<div text-zinc text-sm mt-4>本质统一：都是 Context 管理的不同维度</div>

---
title: 为什么是这五个?
layout: center
---

# 为什么是这五个?

<div v-click>
<blockquote class="text-zinc-300 italic text-xl mb-8">
本质统一：都是 Context 管理的不同维度
</blockquote>
</div>

<div class="grid grid-cols-2 gap-6 mt-8 text-base">
  <div v-click class="text-zinc-400">
    <div class="text-purple mb-2">● Rules</div>
    <div class="text-sm">持久化约束 → 全局上下文</div>
  </div>

  <div v-click class="text-zinc-400">
    <div class="text-blue mb-2">● Commands</div>
    <div class="text-sm">固化交互 → 结构化输入</div>
  </div>

  <div v-click class="text-zinc-400">
    <div class="text-green mb-2">● Skills</div>
    <div class="text-sm">领域封装 → 专业上下文</div>
  </div>

  <div v-click class="text-zinc-400">
    <div class="text-orange mb-2">● SubAgents</div>
    <div class="text-sm">任务分解 → 隔离上下文</div>
  </div>
</div>

<div v-click class="text-center mt-8 text-zinc-400">
  <div class="text-cyan mb-2">● MCP</div>
  <div class="text-sm">外部连接 → 扩展上下文边界</div>
</div>

<div v-click class="mt-8 text-zinc-500 italic text-sm">
从"本地代码"到"整个世界"的上下文管理体系
</div>

---
title: Rules — 持久化的团队共识
layout: two-cols
---

# Rules

<div class="text-purple text-2xl mb-6">持久化的团队共识</div>

<div v-click>

**本质**

全局的上下文约束，无需每次重复

</div>

<div v-click class="mt-6">

**价值**

将"隐性知识"显性化，让 AI 理解团队共识

</div>

<div v-click class="mt-6 text-sm">

**何时使用**

<div class="text-zinc-400 mt-2 space-y-1">
  <div>✅ 需要在所有对话中生效的规则</div>
  <div>✅ 团队编码规范、命名约定</div>
  <div>❌ 不要写太多（AI 不一定看）</div>
</div>

</div>

::right::

<div v-click>

**实战场景 1：编码风格**

```markdown {all|2-4|all}
# .claude/rules/code-style.md
- 优先可读性 > 正确性 > 性能
- 不加显而易见的注释
- 避免过度设计
```

</div>

<div v-click class="mt-4">

**实战场景 2：团队规范**

```markdown {all|2-4|all}
# .claude/rules/naming.md
- 组件文件使用 PascalCase
- 工具函数文件使用 kebab-case
- 测试文件后缀 .test.ts
```

</div>

---
title: Commands — 固化成功的交互模式
layout: center
---

# Commands

<div class="text-blue text-2xl mb-6">固化成功的交互模式</div>

<div v-click>
<blockquote class="text-zinc-300 italic mb-6">
将"成功的上下文配置"固化成可复用指令
</blockquote>
</div>

<div class="grid grid-cols-2 gap-8 mt-8">

<div v-click>

**场景 1: /commit**

<div class="text-sm text-zinc-400 mt-2 space-y-1">
  <div>→ 自动收集：git status/diff/log</div>
  <div>→ 自动分析：变更风格、影响范围</div>
  <div>→ 自动生成：conventional commit</div>
</div>

</div>

<div v-click>

**场景 2: /review-pr**

<div class="text-sm text-zinc-400 mt-2 space-y-1">
  <div>→ 自动召回：PR diff、相关测试</div>
  <div>→ 自动分析：代码质量、潜在问题</div>
  <div>→ 自动生成：结构化 review</div>
</div>

</div>

</div>

<div v-click class="mt-8 bg-zinc-800/50 px-6 py-4 rounded-lg border border-zinc-700 inline-block">
  <div class="text-zinc-300">从"每次都要告诉 AI 该做什么"</div>
  <div class="text-center my-2 text-zinc-500">↓</div>
  <div class="text-green">到"一个指令搞定"</div>
</div>

<div v-click class="mt-6 text-sm text-zinc-500">
✅ 高频重复的工作流 &nbsp;&nbsp; ❌ 一次性任务不值得
</div>

---
title: Skills — 领域专长的上下文封装
layout: center
---

# Skills

<div class="text-green text-2xl mb-6">领域专长的上下文封装</div>

<div v-click>
<blockquote class="text-zinc-300 italic mb-6">
将"特定任务所需的所有上下文"打包成一个技能
</blockquote>
</div>

<div class="grid grid-cols-2 gap-6 text-sm mt-8">

<div v-click class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">

**Obsidian Skill**

<div class="text-zinc-400 mt-3 space-y-2">
  <div><span class="text-purple">触发词</span>：写日记、周总结</div>
  <div><span class="text-purple">上下文</span>：vault 结构、模板、OKR</div>
  <div><span class="text-purple">输出</span>：结构化 markdown</div>
</div>

</div>

<div v-click class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">

**Slidev Skill**

<div class="text-zinc-400 mt-3 space-y-2">
  <div><span class="text-blue">触发词</span>：写 PPT、生成 slides</div>
  <div><span class="text-blue">上下文</span>：Slidev 语法、组件库</div>
  <div><span class="text-blue">输出</span>：可预览的 slides.md</div>
</div>

</div>

</div>

<div v-click class="mt-8 text-zinc-300">
让 AI "学会"一个领域，而不是每次从零教
</div>

<div v-click class="mt-4 text-sm text-zinc-500">
✅ 特定领域的复杂任务 &nbsp;&nbsp; ❌ 通用编程用 Commands
</div>

---
title: SubAgents — 复杂任务的分治策略
layout: center
---

# SubAgents

<div class="text-orange text-2xl mb-6">复杂任务的分治策略</div>

<div v-click>
<blockquote class="text-zinc-300 italic mb-6">
将复杂问题拆解，每个子任务带着"恰到好处"的上下文独立执行
</blockquote>
</div>

<div class="text-left max-w-2xl mx-auto">

<div v-click class="bg-zinc-800/30 px-6 py-3 rounded-lg mb-2">
  <div class="text-zinc-300">用户：重构这个遗留组件</div>
</div>

<div v-click class="text-center text-zinc-500 text-2xl my-2">↓</div>

<div v-click class="bg-blue-900/20 border border-blue-700/50 px-6 py-3 rounded-lg mb-2">
  <div class="text-blue-300 font-bold">SubAgent-1 (Explore)</div>
  <div class="text-sm text-zinc-400 mt-2">→ 只看目录、关键文件、依赖图</div>
  <div class="text-sm text-zinc-400">→ 输出：组件的位置、关联关系</div>
</div>

<div v-click class="text-center text-zinc-500 text-2xl my-2">↓</div>

<div v-click class="bg-green-900/20 border border-green-700/50 px-6 py-3 rounded-lg mb-2">
  <div class="text-green-300 font-bold">SubAgent-2 (Plan)</div>
  <div class="text-sm text-zinc-400 mt-2">→ 输入：SubAgent-1 的发现</div>
  <div class="text-sm text-zinc-400">→ 输出：分步骤的重构计划</div>
</div>

<div v-click class="text-center text-zinc-500 text-2xl my-2">↓</div>

<div v-click class="bg-purple-900/20 border border-purple-700/50 px-6 py-3 rounded-lg">
  <div class="text-purple-300 font-bold">主 Agent：执行重构</div>
  <div class="text-sm text-zinc-400 mt-2">→ 基于 Plan 逐步实施</div>
</div>

</div>

<div v-click class="mt-8 text-zinc-300 text-sm">
避免单一上下文过大，提高召回精度
</div>

<div v-click class="mt-4 text-sm text-zinc-500">
✅ 复杂任务（跨文件重构） &nbsp;&nbsp; ❌ 简单任务直接做
</div>

---
title: MCP — 突破本地文件系统的边界
layout: center
---

# MCP

<div class="text-cyan text-2xl mb-6">突破本地文件系统的边界</div>

<div v-click>
<blockquote class="text-zinc-300 italic mb-6">
连接任何数据源作为上下文
</blockquote>
</div>

<div class="grid grid-cols-3 gap-4 text-xs mt-8">

<div v-click class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">

**Context7 MCP**

<div class="text-zinc-400 mt-3">
  <div class="mb-2">用户：React 19 的 use API?</div>
  <div class="text-cyan text-xs">→ MCP 查询最新文档</div>
  <div class="text-cyan text-xs">→ AI 基于实时文档回答</div>
</div>

</div>

<div v-click class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">

**Playwright MCP**

<div class="text-zinc-400 mt-3">
  <div class="mb-2">用户：测试页面可访问性</div>
  <div class="text-cyan text-xs">→ MCP 注入 playwriter</div>
  <div class="text-cyan text-xs">→ 返回 a11y snapshot</div>
</div>

</div>

<div v-click class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">

**Obsidian MCP**

<div class="text-zinc-400 mt-3">
  <div class="mb-2">用户：总结上周 AI 思考</div>
  <div class="text-cyan text-xs">→ MCP 搜索 #ai 笔记</div>
  <div class="text-cyan text-xs">→ 返回摘录 + 关联图谱</div>
</div>

</div>

</div>

<div v-click class="mt-8 bg-gradient-to-r from-cyan-900/20 to-blue-900/20 border border-cyan-700/50 px-6 py-4 rounded-lg inline-block">
  <div class="text-zinc-300">从"只能看本地代码"</div>
  <div class="text-center my-2 text-cyan-400">→</div>
  <div class="text-cyan-300">到"连接整个世界"</div>
</div>

<div v-click class="mt-6 text-sm text-zinc-500">
✅ 需要外部数据源 &nbsp;&nbsp; ❌ 本地文件系统够用就别引入复杂度
</div>

---
title: 如何选择？决策树
layout: center
---

# 如何选择？

<div class="text-2xl mb-8 text-zinc-400">决策树</div>

<div class="max-w-3xl mx-auto text-left">

<div v-click class="flex items-center mb-4">
  <div class="w-64 text-zinc-300">需要全局生效的规范?</div>
  <div class="text-zinc-500 mx-4">→</div>
  <div class="bg-purple-900/30 border border-purple-700 px-4 py-2 rounded text-purple-300">Rules</div>
</div>

<div v-click class="flex items-center mb-4">
  <div class="w-64 text-zinc-300">高频重复的固定流程?</div>
  <div class="text-zinc-500 mx-4">→</div>
  <div class="bg-blue-900/30 border border-blue-700 px-4 py-2 rounded text-blue-300">Commands</div>
</div>

<div v-click class="flex items-center mb-4">
  <div class="w-64 text-zinc-300">特定领域的复杂任务?</div>
  <div class="text-zinc-500 mx-4">→</div>
  <div class="bg-green-900/30 border border-green-700 px-4 py-2 rounded text-green-300">Skills</div>
</div>

<div v-click class="flex items-center mb-4">
  <div class="w-64 text-zinc-300">任务很复杂需要分解?</div>
  <div class="text-zinc-500 mx-4">→</div>
  <div class="bg-orange-900/30 border border-orange-700 px-4 py-2 rounded text-orange-300">SubAgents</div>
</div>

<div v-click class="flex items-center mb-4">
  <div class="w-64 text-zinc-300">需要外部数据源?</div>
  <div class="text-zinc-500 mx-4">→</div>
  <div class="bg-cyan-900/30 border border-cyan-700 px-4 py-2 rounded text-cyan-300">MCP</div>
</div>

</div>

<div v-click class="mt-12 text-center">
  <div class="inline-block bg-zinc-800/50 px-8 py-4 rounded-lg border border-zinc-700">
    <div class="text-zinc-300 text-lg">原则：从简单到复杂，按需组合</div>
  </div>
</div>
