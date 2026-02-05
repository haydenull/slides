---
layout: section
---

# 重新定位 — IDE vs Claude Code {#part1 .view-transition-title-1}

<div text-zinc text-sm mt-4>从召回机制理解本质差异</div>

---
title: 召回机制的本质差异
layout: center
---

# 召回机制的本质差异

<v-clicks>

| 维度 | Cursor/Copilot | Claude Code |
|------|----------------|-------------|
| **召回方式** | 向量化相似度 + 打开文件关联 | bash/grep 全局搜索 |
| **召回范围** | 编辑器内的"可见世界" | 整个代码库 + 文件系统 |
| **效率** | 高（向量检索快） | 低（暴力搜索慢） |
| **覆盖度** | 局部相关 | 不计代价召回更多 |
| **权衡** | 省 token，可能漏掉关键信息 | 以更高计算成本换正确率 |

> "CC 召回效率更低，但召回了更多上下文，效果反而更好"

</v-clicks>

---
title: 深入召回机制
layout: two-cols
---

# 核心矛盾：语义 vs. 结构

## <span class="text-red">RAG 向量检索</span>

<v-clicks>

<div text-sm text-zinc-400 mt-4>

**局限**

代码的灵魂是**逻辑依赖**

- 向量检索只能"断章取义"
- ❌ 难以感知架构位置

</div>

<div text-xs italic mt-4 text-zinc-500>
"搜"处理订单" → 找到语义相近片段，但漏掉调用的 5 个类"
</div>

</v-clicks>

::right::

## <span class="text-green">Agentic Search</span>

<v-clicks>

<div text-sm text-zinc-400 mt-4>

**优势**

工程师主动探索代码库

- ✓ 边找边思考

**三大能力**

<div text-xs mt-2>
- **符号索引**：Class A 在哪行
- **关键字搜索**：精准匹配变量名
- **Agent 循环**：顺着 import 追踪调用链
</div>

</div>

</v-clicks>

<div text-center mt-8 text-zinc-400 italic v-click>
"以更高计算成本召回更多上下文"
</div>

---
title: 从 Prompt 工程到 Context 管理
layout: center
---

# 时代转变

<div grid="~ cols-2 gap-8" class="mt-8">
  <div v-click>
    <h3 class="text-purple">Prompt 工程时代</h3>
    <div class="text-zinc-400 mt-4 text-base">
      <div><strong>核心问题</strong>：如何让 AI 理解我？</div>
      <div class="mt-2"><strong>解决方案</strong>：精心设计 prompt 的措辞、结构、示例</div>
    </div>
  </div>

  <div v-click>
    <h3 class="text-green">Context 管理时代</h3>
    <div class="text-zinc-400 mt-4 text-base">
      <div><strong>核心问题</strong>：如何让 AI 看到正确的东西？</div>
      <div class="mt-2"><strong>解决方案</strong>：Commands、Rules、Skills、SubAgents、MCP</div>
      <div class="mt-2"><strong>驱动力</strong>：大模型能力提升 → 不再需要"教" AI 怎么理解</div>
    </div>
  </div>
</div>

<div v-click class="mt-8 text-center">
  <blockquote class="text-zinc-300 italic">
    "从用好的提示词让 AI 理解我，变成给 AI 看到更多正确的上下文"
  </blockquote>
</div>

---
title: 专业开发者不是二选一
layout: two-cols
class: "flex flex-col justify-center"
---

<div class="flex flex-1 flex-col justify-center items-center">
  <h1 class="text-blue mb-6">IDE 更擅长</h1>

  <div class="text-zinc-400 text-base flex flex-col gap-3" v-click>
    <div class="flex items-start gap-2">
      <span class="text-blue mt-1">●</span>
      <span>极小的快速修改<br /><span class="text-sm text-zinc-500">（重命名、补全）</span></span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-blue mt-1">●</span>
      <span>阅读代码<br /><span class="text-sm text-zinc-500">（语法高亮、跳转、可视化）</span></span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-blue mt-1">●</span>
      <span>快速迭代<br /><span class="text-sm text-zinc-500">（自动补全速度更快更精准）</span></span>
    </div>
  </div>
</div>

::right::

<div class="flex flex-1 flex-col justify-center items-center">
  <h1 class="text-green mb-6">Claude Code 更擅长</h1>

  <div class="text-zinc-400 text-base flex flex-col gap-3" v-click>
    <div class="flex items-start gap-2">
      <span class="text-green mt-1">●</span>
      <span>跨文件重构<br /><span class="text-sm text-zinc-500">（理解整体架构）</span></span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-green mt-1">●</span>
      <span>复杂任务分解<br /><span class="text-sm text-zinc-500">（subagents）</span></span>
    </div>
    <div class="flex items-start gap-2">
      <span class="text-green mt-1">●</span>
      <span>非编码场景<br /><span class="text-sm text-zinc-500">（写作、系统操作）</span></span>
    </div>
  </div>
</div>

<div v-click class="absolute bottom-10 left-0 right-0 text-center">
  <div class="inline-block bg-zinc-800/50 px-6 py-3 rounded-lg border border-zinc-700">
    <span class="text-zinc-300 italic">IDE 在"看代码"上有天然优势，CC 在"理解系统"上更强</span>
  </div>
</div>
