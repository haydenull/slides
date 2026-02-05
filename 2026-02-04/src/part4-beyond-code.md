---
layout: section
---

# 代码之外 — Claude Code 作为通用 AI 助手 {#part4 .view-transition-title-4}

<div text-zinc text-sm mt-4>Claude Code 不是"更好的 Cursor"，它是"通用 AI 操作系统"</div>

---
title: 从开发工具到通用助手
layout: center
---

# 从开发工具到通用助手

<div v-click>
<blockquote class="text-zinc-300 italic text-xl mb-8">
Claude Code 的本质是"能操作文件系统的 AI"，而非"会写代码的编辑器"
</blockquote>
</div>

<div class="grid grid-cols-2 gap-8 mt-8">
  <div v-click class="bg-zinc-800/30 p-6 rounded-lg border border-zinc-700">
    <div class="text-red-400 text-lg mb-4">❌ 错误理解</div>
    <div class="text-sm text-zinc-400 space-y-2">
      <div>• Cursor 的替代品</div>
      <div>• 只能写代码的工具</div>
      <div>• 编辑器插件</div>
    </div>
  </div>

  <div v-click class="bg-zinc-800/30 p-6 rounded-lg border border-zinc-700">
    <div class="text-green-400 text-lg mb-4">✅ 正确理解</div>
    <div class="text-sm text-zinc-400 space-y-2">
      <div>• 通用 AI 操作系统</div>
      <div>• 能操作文件系统的智能体</div>
      <div>• 任何涉及文本处理的场景</div>
    </div>
  </div>
</div>

<div v-click class="mt-8 text-center text-zinc-500 text-sm italic">
"编程只是众多应用场景之一"
</div>

---
title: 实战场景 A - 写日记
layout: center
---

# 实战场景 A：用 Claude Code 写日记

<div class="text-zinc-400 mb-6" v-click>从口语化描述到结构化输出</div>

<div class="max-w-4xl mx-auto">

<div v-click class="bg-zinc-800/30 p-6 rounded-lg border border-zinc-700 mb-6">
  <div class="text-zinc-300 mb-3">口语化输入</div>
  <div class="bg-zinc-900/50 p-4 rounded text-sm text-zinc-400 font-mono leading-relaxed">
"今天完成了用户管理模块的重构，把 class 组件改成了 hooks。<br />
修复了 issue #234 的登录超时问题，token 过期时间设置错了。<br />
开会讨论了 Q1 技术规划，决定引入 React 19。<br />
状态不太好，下午有点困。"
  </div>
</div>

<div v-click class="flex items-center justify-center mb-6 text-sm">
  <div class="bg-zinc-900/50 px-4 py-2 rounded text-zinc-300">/journal</div>
  <div class="text-zinc-500 mx-3 text-xl">→</div>
  <div class="bg-green-900/30 border border-green-700 px-4 py-2 rounded text-green-300">Obsidian Skill</div>
  <div class="text-zinc-500 mx-3 text-xl">→</div>
  <div class="bg-blue-900/30 border border-blue-700 px-4 py-2 rounded text-blue-300">结构化日记</div>
  <div class="text-zinc-500 mx-3 text-xl">→</div>
  <div class="bg-purple-900/30 border border-purple-700 px-4 py-2 rounded text-purple-300">关联 OKR</div>
</div>

<div v-click class="grid grid-cols-2 gap-4 mt-4">
  <div class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">
    <div class="text-green-300 text-sm mb-2">Obsidian Skill</div>
    <div class="text-xs text-zinc-400 space-y-1.5">
      <div>• 理解 vault 目录结构</div>
      <div>• 识别 Markdown 扩展语法</div>
    </div>
  </div>

  <div class="bg-zinc-800/30 p-4 rounded-lg border border-zinc-700">
    <div class="text-blue-300 text-sm mb-2">LLM 能力</div>
    <div class="text-xs text-zinc-400 space-y-1.5">
      <div>• 信息提取与结构化</div>
      <div>• 情感分析（"状态不好" → mood: 疲惫）</div>
    </div>
  </div>
</div>

</div>

---
title: 实战场景 B - 写本次 PPT
layout: center
---

# 实战场景 B：用 Claude Code 写本次 PPT

<div v-click class="text-zinc-400 text-xl mb-8 italic">
Meta 演示："你现在看到的这个 PPT，就是用 Claude Code + Slidev Skill 生成的"
</div>

<div class="max-w-4xl mx-auto">

<div v-click class="flex items-center justify-center mb-8 text-sm">
  <div class="bg-zinc-900/50 px-3 py-2 rounded text-zinc-300 whitespace-nowrap">零散想法</div>
  <div class="text-zinc-500 mx-2 text-xl">→</div>
  <div class="bg-orange-900/30 border border-orange-700 px-3 py-2 rounded">
    <div class="text-orange-300 whitespace-nowrap">AskUserQuestion</div>
    <div class="text-xs text-zinc-400 mt-1 whitespace-nowrap">主动询问</div>
  </div>
  <div class="text-zinc-500 mx-2 text-xl">→</div>
  <div class="bg-blue-900/30 border border-blue-700 px-3 py-2 rounded text-blue-300 whitespace-nowrap">结构化大纲</div>
  <div class="text-zinc-500 mx-2 text-xl">→</div>
  <div class="bg-green-900/30 border border-green-700 px-3 py-2 rounded">
    <div class="text-green-300 whitespace-nowrap">Slidev Skill</div>
    <div class="text-xs text-zinc-400 mt-1 whitespace-nowrap">理解语法</div>
  </div>
  <div class="text-zinc-500 mx-2 text-xl">→</div>
  <div class="bg-blue-900/30 border border-blue-700 px-3 py-2 rounded text-blue-300 whitespace-nowrap">slides.md</div>
  <div class="text-zinc-500 mx-2 text-xl">→</div>
  <div class="bg-purple-900/30 border border-purple-700 px-3 py-2 rounded text-purple-300 whitespace-nowrap">预览迭代</div>
</div>

<div v-click class="grid grid-cols-2 gap-6">
  <div class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
    <div class="text-blue-300 mb-3">我专注于</div>
    <div class="text-sm text-zinc-400 space-y-1">
      <div>• 核心观点</div>
      <div>• 论证逻辑</div>
      <div>• 案例选择</div>
    </div>
  </div>

  <div class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
    <div class="text-green-300 mb-3">AI 负责</div>
    <div class="text-sm text-zinc-400 space-y-1">
      <div>• 格式规范（Slidev 语法）</div>
      <div>• 排版布局（UnoCSS）</div>
      <div>• 动画效果（v-click）</div>
    </div>
  </div>
</div>

<div v-click class="mt-6 text-center">
  <div class="inline-block bg-zinc-800/50 px-6 py-3 rounded-lg border border-zinc-700">
    <span class="text-zinc-300 italic">Claude Code + Skill = 本地上下文 + 领域知识</span>
  </div>
</div>

</div>

---
title: 更多可能性
layout: center
---

# 更多可能性

<div class="text-zinc-400 text-base mb-8" v-click>
只要涉及"文本处理 + 本地文件"，都可以是 Claude Code 的应用场景
</div>

<div class="grid grid-cols-3 gap-4 max-w-5xl mx-auto text-sm">

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-purple text-lg mb-3">📝 写作</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• 博客文章生成</div>
    <div>• Markdown 格式化</div>
    <div>• 多语言翻译</div>
  </div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-blue text-lg mb-3">📊 数据处理</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• CSV/JSON 转换</div>
    <div>• 日志分析</div>
    <div>• 批量重命名文件</div>
  </div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-green text-lg mb-3">🎨 设计</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• SVG 生成与修改</div>
    <div>• 配置文件生成</div>
    <div>• 主题切换脚本</div>
  </div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-orange text-lg mb-3">🔧 系统管理</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• Shell 脚本生成</div>
    <div>• 环境配置</div>
    <div>• 批量操作自动化</div>
  </div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-cyan text-lg mb-3">📚 学习</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• 笔记整理</div>
    <div>• 知识图谱生成</div>
    <div>• 闪卡制作</div>
  </div>
</div>

<div v-click class="bg-zinc-800/30 p-5 rounded-lg border border-zinc-700">
  <div class="text-pink text-lg mb-3">🎯 生产力</div>
  <div class="text-zinc-400 space-y-1 text-xs">
    <div>• Todo 管理</div>
    <div>• 会议记录整理</div>
    <div>• 时间追踪分析</div>
  </div>
</div>

</div>

<div v-click class="mt-12 bg-gradient-to-r from-purple-900/20 to-cyan-900/20 border border-purple-700/50 px-8 py-5 rounded-lg inline-block">
  <div class="text-zinc-200 text-lg">
    从"编程助手"到"文件系统上的智能操作系统"
  </div>
</div>
