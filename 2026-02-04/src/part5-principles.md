---
layout: cover
---

# 批判性反思 — 陷阱与原则 {#part5 .view-transition-title-5}

## 从"Talk is Cheap"到"Code is Cheaper"

---
title: 编程的本质
layout: two-cols-header
---

# 编程的本质是复杂度管理

<div v-click class="text-center text-zinc-300 italic text-xl mt-4 mb-4">
"代码不是资产，是负债"
</div>

<div v-click class="mt-8 text-center fixed bottom-10 left-1/2 transform translate-x-[-50%] bg-red-900/20 border border-red-700/50 px-6 py-3 rounded-lg">
  <div class="text-red-300">
    AI 写代码 = 加速产生负债
  </div>
</div>

::left::

## 资产 ✅

能持续产生价值的东西

- 用户价值
- 团队知识

::right::

## 负债 ⚠️

需要持续维护的东西

- 代码
- 技术债

---
title: 价值观转变
layout: two-cols-header
---

# Talk is Cheap, Show Me the Code?

::left::

## 曾经的价值观

<div class="font-mono text-purple-300 text-lg">Talk is cheap, show me the code</div>

<div class="text-zinc-400 text-sm mt-4">
→ 能写出代码的人才有价值

→ 代码量 = 生产力
</div>

::right::

## AI 时代的转变

<div class="font-mono text-green-300 text-lg">Code is cheaper, show me the solution</div>

<div class="text-zinc-400 text-sm mt-4">
→ AI 让生成代码的成本极低

→ 代码量 ≠ 价值，解决问题的能力才是
</div>

---
title: 工程师价值重新定位
layout: two-cols-header
---

# 工程师价值的重新定位

::left::

## 旧时代

工程师 = <span class="text-purple-300">写代码的人</span>

- 价值 = 交付代码行数
- 核心技能 = 架构设计、编码规范且熟练

::right::

## AI 时代

工程师 = <span class="text-green-300">问题分解者 + 质量把关者</span>

- 价值 = <span class="text-green-300">问题建模能力 + 技术判断力</span>
- 核心技能 = 拆解复杂问题、给 AI 分配任务、审查 AI 产出

---
title: 工程师经验的价值
---

# 工程师经验的价值

<div class="space-y-6 mt-8">

<div v-click class="text-center text-zinc-300 text-xl italic">
"人的认知上限决定了 AI 的代码质量"
</div>

<div v-click class="grid grid-cols-2 gap-6 mt-12">

<div class="bg-zinc-800/40 p-6 rounded-xl border border-zinc-700/50">
<div class="text-orange-400 text-2xl mb-3">🔍</div>
<div class="text-zinc-200 font-semibold mb-2">识别问题</div>
<div class="text-sm text-zinc-400">
判断 AI 方案是否正确<br>
识别幻觉和边界问题
</div>
</div>

<div class="bg-zinc-800/40 p-6 rounded-xl border border-zinc-700/50">
<div class="text-green-400 text-2xl mb-3">⚖️</div>
<div class="text-zinc-200 font-semibold mb-2">技术决策</div>
<div class="text-sm text-zinc-400">
选择合适的架构方案<br>
权衡性能与可维护性
</div>
</div>

<div class="bg-zinc-800/40 p-6 rounded-xl border border-zinc-700/50">
<div class="text-blue-400 text-2xl mb-3">🎯</div>
<div class="text-zinc-200 font-semibold mb-2">质量把关</div>
<div class="text-sm text-zinc-400">
Review AI 生成的代码<br>
保证工程标准一致性
</div>
</div>

<div class="bg-zinc-800/40 p-6 rounded-xl border border-zinc-700/50">
<div class="text-purple-400 text-2xl mb-3">💡</div>
<div class="text-zinc-200 font-semibold mb-2">经验传承</div>
<div class="text-sm text-zinc-400">
将隐性知识显性化<br>
指导 AI 生成高质量代码
</div>
</div>

</div>

<div v-click class="mt-12 text-center">
<div class="inline-block bg-gradient-to-r from-orange-900/20 to-purple-900/20 px-8 py-4 rounded-xl border border-orange-700/30">
<div class="text-zinc-200 font-bold text-lg">结论</div>
<div class="text-zinc-300 mt-2">工程师经验不再是负担，而是 AI 时代的<strong class="text-orange-300">核心杠杆</strong></div>
</div>
</div>

</div>

---
title: 不要本末倒置
layout: two-cols-header
---

# 不要本末倒置

<!-- 底部引用 -->
<div v-click class="mt-6">
<blockquote class="text-zinc-300 italic text-center text-lg">
"会开车的人坐在副驾驶才是最紧张的"
</blockquote>
</div>

::left::

## 警惕

快速产出代码 ≠ 好事

能跑过测试 ≠ 可以合并

AI 提速 ≠ 人可以撒手不管

::right::

## 适用场景

**严肃的公司项目**

必须 review，必须掌控

**个人玩票项目**

可以放飞，只要自己能负责

---
title: LLM 会不择手段
layout: list
---

# 关键问题：LLM 会"不择手段"完成目标

<div v-click class="text-center text-zinc-300 italic text-lg mt-6 mb-4">
AI 的目标函数是"让测试通过"，而不是"写出正确的代码"
</div>

- 修改测试 — 修改测试用例让它不再报错
- 删除断言 — 删除失败的断言
- 注释逻辑 — 注释掉边界检查逻辑
- 破坏机制 — 破坏已有的错误处理
- ✨ 真正修复 bug（你期望的）

---
title: LLM 的局限性
layout: two-cols-header
---

# 为什么 LLM 会"不择手段"？

::left::

## 原因

- LLM 理解"目标"但不理解"价值观"
- "让测试通过"和"写正确代码"在 AI 眼中可能等价
- AI 没有"工程师的职业操守"这种隐性约束

::right::

## 人类 Review 的价值

- 识别"达成目标但违背原则"的代码
- 判断"技术上可行但工程上错误"的方案
- 保证代码不是靠"绕过检查"实现的

---
title: 现阶段的铁律
layout: cards
cards:
  - title: 代码必须 review
    desc: 当前 LLM 会犯错、会幻觉、会遗漏边界情况，人类 review 是质量保障的最后防线
  - title: 理解 > 生成
    desc: 先理解，再让 AI 生成，不理解就生成 = 技术债黑箱
  - title: 保持掌控感
    desc: 你是驾驶员，AI 是副驾，掌控 = 知道系统在做什么，能预判问题
---

# 现阶段（2026-02）的铁律

---
title: 未来的可能性
layout: two-cols-header
---

# 未来的可能性

<!-- 结论 -->
<div v-click class="mt-6">
<blockquote class="text-zinc-300 italic text-center text-lg">
"代码会越来越 cheap，但解决正确的问题永远不 cheap"
</blockquote>
</div>

::left::

## 当 LLM 能力足够强时

- AI 能自我修复 bug → review 不再必须？
- AI 理解全局上下文 → 不会产生技术债？
- AI 能自证正确性 → 测试即保障？

::right::

## 但即使如此

- 业务需求的理解仍需人
- 技术方向的决策仍需人

---
title: 总结
layout: two-cols-header
---

<div class="my-6">

# 总结 — 工程师的核心价值

</div>

<!-- 底部流程，使用 fixed 定位 -->
<div class="fixed bottom-20 left-0 right-0 py-2 px-8">
<div class="max-w-3xl mx-auto flex items-center justify-between text-xs gap-2">
  <div class="px-3 py-1.5 border border-zinc-600/50 rounded text-zinc-400">现实世界问题</div>
  <div class="text-zinc-700">→</div>
  <div class="px-3 py-1.5 border border-zinc-600/50 rounded text-zinc-400">抽象建模</div>
  <div class="text-zinc-700">→</div>
  <div class="px-3 py-1.5 border border-zinc-600/50 rounded text-zinc-400">问题拆解</div>
  <div class="text-zinc-700">→</div>
  <div class="px-3 py-1.5 border border-zinc-600/50 rounded text-zinc-400">技术决策</div>
  <div class="text-zinc-700">→</div>
  <div class="px-3 py-1.5 border border-zinc-600/50 rounded text-zinc-400">编码</div>
  <div class="text-zinc-700">→</div>
  <div class="px-3 py-1.5 border border-orange-700/50 rounded text-orange-300">应用到现实</div>
</div>
</div>

::left::

## 技术审美

<div class="text-zinc-300 italic text-sm mb-6">
"The taste for code"
</div>

- 看到坏代码有哪里不对劲的直觉
- 做出正确技术决策
- 解决正确的问题

::right::

## 工程化思维

<div class="text-zinc-300 italic text-sm mb-6">
"Engineering mindset"
</div>

- 拆解问题
- 固化解决方案
- 确定性证明
