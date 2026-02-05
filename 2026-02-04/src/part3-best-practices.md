---
layout: section
---

# Claude Code 最佳实践 {#part3 .view-transition-title-3}

<div text-zinc text-sm mt-4>高效协作的技巧与原则</div>

---
title: 上下文管理技巧
layout: center
---

# 上下文管理技巧

<div class="text-zinc-400 text-base max-w-4xl mx-auto space-y-4 mt-8">

<div v-click class="flex items-start">
  <div class="text-purple mr-3 mt-1 text-xl">①</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>复杂任务使用 Plan Mode</strong></div>
    <div class="text-sm text-zinc-500">Explore → Plan → Implement，避免 AI 在不理解全貌时贸然修改</div>
  </div>
</div>

<div v-click class="flex items-start">
  <div class="text-blue mr-3 mt-1 text-xl">②</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>持续更新 CLAUDE.md</strong></div>
    <div class="text-sm text-zinc-500">积累项目特定的约定、架构决策、常见问题 → AI 自动获取上下文</div>
  </div>
</div>

<div v-click class="flex items-start">
  <div class="text-green mr-3 mt-1 text-xl">③</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>积累 Commands/Skills 优化重复工作</strong></div>
    <div class="text-sm text-zinc-500">三次重复就值得自动化（如 /commit、/review-pr）</div>
  </div>
</div>

<div v-click class="flex items-start">
  <div class="text-orange mr-3 mt-1 text-xl">④</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>提供精准上下文</strong></div>
    <div class="text-sm text-zinc-500">@ 引用文件、MCP 连接、粘贴完整报错 > 模糊描述"那个组件有问题"</div>
  </div>
</div>

<div v-click class="flex items-start">
  <div class="text-cyan mr-3 mt-1 text-xl">⑤</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>善用语音输入</strong></div>
    <div class="text-sm text-zinc-500">语音比打字能提供更多信息、输入更快速</div>
  </div>
</div>

<div v-click class="flex items-start">
  <div class="text-pink mr-3 mt-1 text-xl">⑥</div>
  <div class="flex-1">
    <div class="text-zinc-200 mb-1"><strong>会话生命周期管理</strong></div>
    <div class="text-sm text-zinc-500">/clear 清理上下文 · /resume 接力对话 · /compact 压缩历史 · /rewind 回到变差前</div>
  </div>
</div>

</div>

---
title: 高效工作流
layout: center
---

# 高效工作流

<div class="grid grid-cols-2 max-w-4xl mx-auto mt-8" style="gap: 1.5rem;">

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-purple text-lg font-bold mb-3">主动澄清</div>
  <div class="text-sm text-zinc-400">让 AI 使用 AskUserQuestion 主动询问，不要让 AI 猜测需求</div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-blue text-lg font-bold mb-3">命令别名</div>
  <div class="text-sm text-zinc-400"><code class="text-xs bg-zinc-900 px-2 py-1 rounded">alias cc="claude"</code><br />高频工具值得最短命令</div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-green text-lg font-bold mb-3">立即暂存</div>
  <div class="text-sm text-zinc-400">AI 每次小步修改后立即 git add<br />永远不要盲目信任 AI 产出</div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-orange text-lg font-bold mb-3">控制规模</div>
  <div class="text-sm text-zinc-400">理想：2-3 个文件、几十行代码、3 分钟 review 完<br />避免：一次性重构整个模块</div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700 col-span-2">
  <div class="text-cyan text-lg font-bold mb-3">明确验收标准</div>
  <div class="text-sm text-zinc-400 grid grid-cols-2" style="gap: 1rem;">
    <div><span class="text-red">❌</span> "帮我加个搜索功能"</div>
    <div><span class="text-green">✅</span> "加搜索功能：支持模糊匹配，结果高亮关键词，空输入显示全部"</div>
  </div>
</div>

</div>

---
title: SDD 驱动开发范式
layout: center
---

# SDD 驱动开发范式

<div class="max-w-4xl mx-auto">

<div class="grid grid-cols-2 mt-8" style="gap: 2rem;">

<div v-click class="text-center">
  <h3 class="text-zinc-400 mb-4">传统开发</h3>
  <div class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700 text-sm">
    <div class="text-zinc-300">需求 → 设计 → 编码 → 测试</div>
  </div>
</div>

<div v-click class="text-center">
  <h3 class="text-green mb-4">SDD 开发</h3>
  <div class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700 text-sm space-y-2">
    <div class="text-zinc-300">需求 → <span class="text-purple">Spec</span>（需求上下文）</div>
    <div class="text-zinc-500">↓</div>
    <div class="text-zinc-300"><span class="text-blue">Design</span>（技术设计上下文）</div>
    <div class="text-zinc-500">↓</div>
    <div class="text-zinc-300"><span class="text-green">Implement</span>（实施方案上下文）</div>
  </div>
</div>

</div>

<div v-click class="mt-8">
<blockquote class="text-zinc-300 italic text-center text-lg">
"从不确定到确定，每个阶段都在积累确定性"
</blockquote>
</div>

<div v-click class="mt-8 bg-zinc-800/30 p-6 rounded-lg border border-zinc-700">
  <div class="text-zinc-200 font-bold mb-4">SDD 的价值 — 上下文管理</div>
  <div class="text-sm text-zinc-400 space-y-2">
    <div><span class="text-purple">● Spec 文档</span>：将"用户需求"转化为 AI 可理解的上下文</div>
    <div><span class="text-blue">● Design 文档</span>：将"技术决策"固化成可追溯的上下文</div>
    <div><span class="text-green">● Implement 文档</span>：将"实施方案"转化为 AI 分步执行的任务</div>
  </div>
</div>

</div>
