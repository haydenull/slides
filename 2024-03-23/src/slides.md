---
title: Github Copilot 101
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Github Copilot 101 <RiCopilotFill />

<h2 class="text-zinc">Github Copilot 入门指南</h2>

<a href="https://github.com/haydenull" target="_blank" alt="GitHub Haydenull" title="Open in GitHub" class="pt-12 text-base text-zinc-400 absolute bottom-14 !border-none !hover:text-white"><carbon-logo-github /> 启封 Hayden</a>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

# Github Copilot 是什么

<video v-click autoplay playsinline muted loop class="w-full" poster="https://github.githubassets.com/assets/hero-poster-18f705106687.webp">
  <source src="https://github.githubassets.com/assets/hero-lg-6a98e47708e8.mp4" type="video/mp4">
</video>

---
transition: slide-up
---
# 设置

<div class="flex justify-center">
  <img src="/github-copilot-language.png" alt="Copilot Settings" class="w-4/5" />
</div>

<p class="text-center !mt-10">设置语言为中文</p>

<!-- 默认使用 VSCode 的语言配置，但可以通过设置覆盖 -->

---
layout: section
---

# 使用原则

---
title: Don't let copilot fly your plane
layout: intro
level: 2
---

<h1 class="!text-5xl"><b class="text-rose">Don't</b> let copilot fly your plane</h1>

<v-clicks>

- <b class="text-green">引导</b> Copilot，<span class="text-zinc">如何做</span> <EpRight /> <span class="text-zinc">如何引导 Copilot 去做</span>
- <b class="text-green">有能力鉴别</b> Copilot 生成的代码，提取出有用的部分
- <b class="text-green">检查</b> Copilot 生成的代码，LLM 生成的代码可能不是最佳实践，甚至有错误

</v-clicks>

---
layout: intro
title: Copilot 是你的助手
level: 2
---

<h1 class="!text-5xl">把 Copilot 当做任劳任怨的<b class="text-green">免费助手</b></h1>

<v-clicks>

- 将自己放在更高的维度，把握大方向，让 Copilot 帮你做细节实现
- 有想法就写下来，让 Copilot 帮你实现，然后验证，快速试错
- 没有想法就让 Copilot 帮你想，然后验证
- 浪费 Copilot 的时间节约自己的时间

</v-clicks>

---
layout: intro
title: Copilot 可以减少精力消耗
level: 2
---

<h1 class="!text-5xl">Copilot 最大的用处是<b class="text-green">减少精力消耗</b></h1>

<b class="text-rose">不要期望</b> Copilot 大幅减少工作量和时间

<v-clicks>

- 写 Prompt 需要时间
- 检查生成的代码需要时间
- Copilot 的用处在于提高效率，减少精力消耗
- 减少工作量和时间是附带的

</v-clicks>

---
layout: two-cols
class: "flex flex-col justify-center"
title: 擅长与不擅长
---

<h1 class="text-green">擅长</h1>

- 单文件能够完成的功能（方法、Hook、组件）
- 常见的业务场景
- 编程相关概念（竞态、异步）

::right::

<div v-click>

<h1 class="text-rose">不擅长</h1>

- 多个文件组合完成的功能模块
- 业务特定的逻辑
- 使用新的框架、库、API

</div>

<!-- 对组件划分能力提出了更高的要求 -->

---
---

# 生成代码的几种方式

- 注释
- Inline Chat
- Chat Panel