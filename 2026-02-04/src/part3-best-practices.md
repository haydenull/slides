---
layout: cover
background: /cover-part3.jpg
class: text-center
---

# Claude Code 最佳实践 {#part3 .view-transition-title-3}

## 高效协作的技巧与原则

---
title: 上下文管理技巧
layout: default
---

# 上下文管理技巧

<div class="max-w-4xl mx-auto space-y-4 mt-8">

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-blue-400">1</div>
  <div>
    <div class="text-lg font-semibold">复杂任务使用 Plan Mode</div>
    <div class="text-zinc-400 text-sm">Explore → Plan → Implement，避免 AI 在不理解全貌时贸然修改</div>
  </div>
</div>

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-purple-400">2</div>
  <div>
    <div class="text-lg font-semibold">持续更新 CLAUDE.md</div>
    <div class="text-zinc-400 text-sm">积累项目特定的约定、架构决策、常见问题 → AI 自动获取上下文</div>
  </div>
</div>

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-green-400">3</div>
  <div>
    <div class="text-lg font-semibold">积累 Commands/Skills 优化重复工作</div>
    <div class="text-zinc-400 text-sm">三次重复就值得自动化（如 /commit、/gitlab-code-review）</div>
  </div>
</div>

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-orange-400">4</div>
  <div>
    <div class="text-lg font-semibold">提供精准上下文</div>
    <div class="text-zinc-400 text-sm">@ 引用文件、MCP 连接浏览器、粘贴完整报错 > 模糊描述"那个组件有问题"</div>
  </div>
</div>

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-cyan-400">5</div>
  <div>
    <div class="text-lg font-semibold">善用语音输入</div>
    <div class="text-zinc-400 text-sm">语音比打字能提供更多信息、输入更快速</div>
  </div>
</div>

<div v-click class="flex items-start gap-4">
  <div class="text-2xl font-bold text-pink-400">6</div>
  <div>
    <div class="text-lg font-semibold">会话生命周期管理</div>
    <div class="text-zinc-400 text-sm">/clear 清理上下文 · /resume 接力对话 · /compact 压缩历史 · /rewind 回到变差前</div>
  </div>
</div>

</div>

---
title: 高效工作流
layout: cards
cards:
  - title: 主动澄清
    desc: 让 AI 使用 AskUserQuestion 主动询问，不要让 AI 猜测需求
    tags: ["沟通"]
  - title: 命令别名
    desc: 高频工具值得最短命令，如 alias cc="claude"
    tags: ["效率"]
  - title: 立即暂存
    desc: AI 每次小步修改后立即 git add，永远不要盲目信任 AI 产出
    tags: ["安全"]
  - title: 控制规模
    desc: 理想：2-3 个文件、几十行代码、3 分钟 review 完
    tags: ["节奏"]
  - title: 明确验收标准
    desc: 对比示例展示清晰 vs 模糊的需求描述
    tags: ["质量"]
---

# 高效工作流

---
title: SDD 驱动开发范式
layout: two-cols-header
---

# SDD 驱动开发范式

<div class="text-center text-zinc-400 text-sm mb-6">
  <em>"从不确定到确定，每个阶段都在积累确定性"</em>
</div>

::left::

## 传统开发

<div class="text-zinc-400 mt-4">

需求 → 设计 → 编码 → 测试

- 一次性传递大量上下文
- 容易偏离原始需求
- 技术决策难以追溯

</div>

::right::

## SDD 开发

<div class="text-zinc-400 mt-4">

需求 → **Spec** → **Design** → **Implement**

- 分阶段固化上下文
- 每步都有明确产出
- 全过程可追溯

</div>

---
title: SDD 的价值 — 上下文管理
layout: timeline
timeline:
  - year: Spec
    event: 需求转化
    desc: 将"用户需求"转化为 AI 可理解的上下文
  - year: Design
    event: 技术决策
    desc: 将"技术决策"固化成可追溯的上下文
  - year: Implement
    event: 任务分解
    desc: 将"实施方案"转化为 AI 分步执行的任务
---

# SDD 的价值 — 上下文管理

<div class="text-center text-zinc-400 italic">
  每个阶段都在积累确定性
</div>

---
title: ai-config-kit - 同步功能
layout: cards
cards:
  - title: 统一管理
    desc: 集中管理 skills、commands、rules，一处配置全局生效
    tags: ["管理"]
  - title: 一键同步
    desc: 同步到 Claude Code、Cursor、Windsurf、OpenCode
    tags: ["效率"]
---

# ai-config-kit

<div class="text-center text-zinc-500 mt-8">
  团队共建 AI 配置同步工具
</div>

---
title: ai-config-kit - 已积累配置
layout: cards
cards:
  - title: Skills
    desc: gitlab-code-review · sdd (spec/design/impl) · react-useeffect · planning-with-files · yapi-service-generator
    tags: ["6"]
  - title: Commands
    desc: commit · create-gitlab-mr · new-git-branch
    tags: ["3"]
  - title: Rules
    desc: code-guideline · comments · typescript · browser-compatibility
    tags: ["4"]
---

# ai-config-kit 已积累配置