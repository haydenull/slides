---
layout: cover
background: /cover-part1.jpg
class: text-center
---

# 重新定位 — IDE vs Claude Code

## 从召回机制理解本质差异

---
title: 召回机制的本质差异
layout: table
---

# 召回机制的本质差异

| 维度 | Cursor | Claude Code |
|:------|:------|:----|
| 召回方式 | 向量化相似度 + 打开文件关联 | bash/grep 全局搜索 |
| 召回范围 | 编辑器内的"可见世界" | 整个代码库 + 文件系统 |
| 效率 | 高（向量检索快） | 低（暴力搜索慢） |
| 覆盖度 | 局部相关 | 不计代价召回更多 |
| 权衡 | 省 token，可能漏掉关键信息 | 以更高计算成本换正确率 |

> "CC 召回效率更低，但召回了更多上下文，效果反而更好"

---
title: 深入召回机制
layout: two-cols-header
---

# 核心矛盾：语义 vs. 结构

::left::

## RAG 向量检索

<div text-sm text-zinc-400 mt-4>

**局限**

代码的灵魂是**逻辑依赖**

- 向量检索只能"断章取义"
- 难以感知架构位置

</div>

<div text-xs italic mt-4 text-zinc-500>
"搜"处理订单" → 找到语义相近片段，但漏掉调用的 5 个类"
</div>

::right::

## Agentic Search

<div text-sm text-zinc-400 mt-4>

**优势**

工程师主动探索代码库

- 边找边思考

**三大能力**

<div text-xs mt-2>

- **符号索引**：Class A 在哪行
- **关键字搜索**：精准匹配变量名
- **Agent 循环**：顺着 import 追踪调用链

</div>

</div>

<!-- <div text-center mt-8 text-zinc-400 italic>
"以更高计算成本召回更多上下文"
</div> -->

---
title: 从 Prompt 工程到 Context 管理
layout: two-cols-header
---

# 时代转变

<div class="text-center text-zinc-400 text-sm mb-6">
  <blockquote class="italic">
    "从用好的提示词让 AI 理解我，变成给 AI 看到更多正确的上下文"
  </blockquote>
</div>

::left::

## Prompt 工程时代

<div class="text-zinc-400 mt-4 text-base">

**核心问题**：如何让 AI 理解我？

**解决方案**：精心设计 prompt 的措辞、结构、示例

</div>

::right::

## Context 管理时代

<div class="text-zinc-400 mt-4 text-base">

**核心问题**：如何让 AI 看到正确的东西？

**解决方案**：Commands、Rules、Skills、SubAgents、MCP

**驱动力**：大模型能力提升 → 不再需要"教" AI 怎么理解

</div>

---
title: 专业开发者不是二选一
layout: topics
topics:
  - title: IDE 更擅长
    desc: 极小快速修改、阅读代码、快速迭代（补全更精准）
    audience: 开发者
    icon: code
  - title: Claude Code 更擅长
    desc: 跨文件重构、复杂任务分解、非编码场景
    audience: 开发者
    icon: sparkles
---

# 专业开发者不是二选一

<div text-center mt-8 text-zinc-400 italic>
IDE 在"看代码"上有天然优势，CC 在"理解系统"上更强
</div>
