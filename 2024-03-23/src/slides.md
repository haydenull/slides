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
colorSchema: dark
---
<img class="size-10 rounded-full absolute top-10 border" src="https://pocket.haydenhayden.com/blog/202403241700326.jpg" alt="avatar" />

# Github Copilot 101 <RiCopilotFill />

<h2 class="text-zinc">Github Copilot 入门指南</h2>

<a href="https://github.com/haydenull" target="_blank" alt="GitHub Haydenull" title="Open in GitHub" class="pt-12 text-base text-zinc-400 absolute bottom-14 !border-none !hover:text-white"><carbon-logo-github /> 启封 Hayden</a>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
title: Github Copilot 是什么
transition: fade-out
---

<h1 transition-all absolute top-10 left-14 :class="$clicks <=0 ? 'scale-150 !left-1/2 !top-1/2 -translate-x-1/2' : ''">Github Copilot 是什么</h1>

<video v-click autoplay playsinline muted loop class="w-full mt-14 opacity-80 rounded-md" poster="https://github.githubassets.com/assets/hero-poster-18f705106687.webp">
  <source src="https://github.githubassets.com/assets/hero-lg-6a98e47708e8.mp4" type="video/mp4">
</video>

---
layout: section
---

# 使用原则

<!--
Copilot 的用法比较简单，但是使用者需要有正确的认识才能更高效地使用。
-->

---
title: Don't let copilot fly your plane
layout: intro
level: 2
---

<h1 class="!text-4xl"><b class="text-rose">Don't</b> let copilot fly your plane</h1>

Github Copilot is an assistant on your flight, not a replacement for you.

<v-clicks>

- <b class="text-green">引导</b> Copilot，<span class="text-zinc">如何做</span> <EpRight /> <span class="text-zinc">如何引导 Copilot 去做</span>
- <b class="text-green">有能力鉴别</b> Copilot 生成的代码，提取出有用的部分
- <b class="text-green">检查</b> Copilot 生成的代码，LLM 生成的代码可能不是最佳实践，甚至有错误

</v-clicks>

<!--
[click] 我们才是驾驶员，思想从如何做转变为引导 xxx

[click] 有能力鉴别生成的代码

[click] LLM 生成的代码有能有错误，可能违背最佳实践
-->

---
layout: intro
title: Copilot 是你的助手
level: 2
---

<h1 class="!text-4xl">把 Copilot 当做任劳任怨的<b class="text-green">免费助手</b></h1>

<v-clicks>

- 我们自己把握大方向，让 Copilot 做细节实现
- 有想法就写下来，让 Copilot 帮你实现，然后验证，快速试错
- 没有想法就让 Copilot 帮你想，然后验证
- 浪费 Copilot 的时间节约自己的时间

</v-clicks>

---
layout: intro
title: Copilot 可以减少精力消耗
level: 2
transition: slide-up
---

<h1 class="!text-4xl">Copilot 最大的用处是<b class="text-green">减少精力消耗</b></h1>

<b class="text-rose">不要期望</b> Copilot 大幅减少工作量和时间

<v-clicks>

- 写 Prompt 需要时间
- 检查生成的代码需要时间
- 也可能无法得到想要的答案
- Copilot 的用处在于提高效率，减少精力消耗
- 减少工作量和时间是附带的

</v-clicks>

---
layout: section
---

# 适用场景

---
layout: two-cols
class: "flex flex-col justify-center"
title: 擅长与不擅长
transition: fade
---

<h1 class="text-green"> 擅长</h1>

- 单文件能够完成的功能（方法、Hook、组件
- 常见的业务场景
- 编程相关概念（竞态、异步）

::right::

<div v-click>

<h1 class="text-rose">🤥 不擅长</h1>

- 多个文件组合完成的功能模块
- 业务特定的逻辑
- 使用新的框架、库、API

</div>

<!-- 对组件划分能力提出了更高的要求 -->


---
layout: section
transition: view-transition
---

# 生成代码的几种方式 {.view-transition-title-10}

---
layout: intro
transition: view-transition
---

# 生成代码的几种方式 {.view-transition-title-10.!text-4xl}

<div pl-1>
  <div v-click>

  <CarbonIbmWatsonxCodeAssistantForZRefactor text-purple /> Code Completion {.view-transition-title-11}

  </div>

  <div mt-3 />

  <div v-click><CarbonChatBot text-purple /> Chat</div>
  <v-clicks text-sm pl-4 text-zinc>

  - Inline Chat
  - Chat Panel

  </v-clicks>
</div>


---
title: Code Completion
layout: intro
---

# <CarbonIbmWatsonxCodeAssistantForZRefactor text-4xl text-purple mb-1 /> Code Completion {.view-transition-title-11.!text-4xl}

根据已有代码自动推断，生成代码。

<v-clicks>

1. Copilot 会将 VSCode 当前打开的 Tab 作为上下文
   - <span class="text-zinc-400 text-base">适时打开相关的文件</span>
   - <span class="text-zinc-400 text-base">及时关闭不相关的文件</span>
2. 增加详细的注释
   - <span class="text-zinc-400 text-base">文件顶部总览型注释</span>
   - <span class="text-zinc-400 text-base">函数、方法、变量的注释</span>
   - <span class="text-zinc-400 text-base">代码执行 step by step 的注释</span>
3. 完善而准确的类型定义
4. 具有描述性且易于理解的变量名
5. 提供示例：Input <PhArrowRightBold text-sm text-zinc /> Output
6. 手动控制 import 库

</v-clicks>

<!-- 代码可读性越高，提示效果越好 -->

---
title: Inline Chat
layout: intro
---

# <CarbonChatBot text-purple text-4xl /> Inline Chat {.!text-4xl}

快捷键：<kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>i</kbd>

唤起临时对话框，输入Prompt，生成代码。适用于临时需求。但也可以多次对话。

---
title: Chat Panel
layout: intro
---

# <CarbonChatBot text-purple text-4xl /> Chat Panel {.!text-4xl}

Copilot Chat：侧边栏，输入 Prompt，生成代码。适用多轮对话。

---
title: Tip1:合理使用预置 Prompt
layout: intro
---

# <span class="text-green font-semibold text-4xl">Tip1:</span> 合理使用预置 Prompt {.!text-4xl}

<v-clicks>

- `/fix`: 修复问题
- `/explain`: 解释代码
- `/docs`: 生成文档
- `/tests`: 生成测试代码

</v-clicks>

<IcOutlineTipsAndUpdates class="text-zinc text-4xl absolute right-1/5 top-1/2 opacity-10 scale-600 -translate-y-1/2" />

---
title: Tip2:提供更相关的上下文
layout: intro
---

# <span class="text-green font-semibold text-4xl">Tip2:</span> 提供更相关的上下文 {.!text-4xl}

- Highlight Code
- Current File
- @workspace
- @terminal
- #file
- #selection

<IcOutlineTipsAndUpdates class="text-zinc text-4xl absolute right-1/5 top-1/2 opacity-10 scale-600 -translate-y-1/2" />

---
title: Tip3:按主题组织对话
layout: intro
---

# <span class="text-green font-semibold text-4xl">Tip3:</span> 按主题组织对话 {.!text-4xl}

- 一个对话只处理一个问题
- 适当移除与问题不相关的对话

<IcOutlineTipsAndUpdates class="text-zinc text-4xl absolute right-1/5 top-1/2 opacity-10 scale-600 -translate-y-1/2" />

---
title: 编写更好的 Prompt
layout: section
---
# 编写更好的<FluentSquareHintSparkles48Regular text-purple duration-300 transition-all text-6xl :class="$clicks >=1 ? 'w-20 ml-2' : 'w-0'" /> <span v-if="$clicks <= 0">Prompt</span> <span v-if="$clicks >= 1" text-purple v-mark.underline.purple.at="1">Prompt</span>

---
title: 3S 原则
transition: view-transition
class: grid grid-cols-3 gap-4
---

<div mt-30 flex flex-col gap-3 items-center >
  <h2 text-center><span text-6xl text-purple font-semibold class="view-transition-title-20-1">S</span>imple</h2>
  <div text-zinc-400 text-base flex flex-col gap-2 v-click>
    <div>将复杂问题拆分成多步简单问题</div>
    <div>一个 Prompt 只处理一个问题</div>
    <div>生成的代码越多，越容易出错</div>
    <div>生成的代码越少，越容易 review</div>
  </div>

</div>

<div mt-30 flex flex-col gap-3 items-center>
  <h2 text-center><span text-6xl text-green font-semibold class="view-transition-title-20-2">S</span>pecific</h2>
  <div text-zinc-400 text-base flex flex-col gap-2 v-click>
    <div>提供更多更具体的上下文</div>
    <div>利用相关文件</div>
    <div>利用高亮代码</div>
    <div>利用 agent 和指令</div>
  </div>
</div>

<div mt-30 flex flex-col gap-3 items-center>
  <h2 text-center><span text-6xl text-teal font-semibold class="view-transition-title-20-3">S</span>hort</h2>
  <div text-zinc-400 text-base flex flex-col gap-2 v-click>
    <div>不用在意错别字</div>
    <div>不需要写完整的句子</div>
  </div>
</div>

---
title: 3S 原则
layout: section
class: "flex justify-center"
---

<div flex gap-10>
  <h2 flex justify-end items-end text-zinc-400 >
    <span inline-flex flex-col text-center text-7xl text-purple font-semibold>
      <PhCrownSimpleBold text-4xl mb--2 />
      <span class="view-transition-title-20-1">S</span>
    </span>
    <span mb-2>imple</span>
  </h2>
  <h2 flex justify-end items-end text-zinc-400 >
    <span inline-flex flex-col text-center text-7xl text-green font-semibold>
      <PhCrownSimpleBold text-4xl mb--2 />
      <span class="view-transition-title-20-2">S</span>
    </span>
    <span mb-2>pecific</span>
  </h2>
  <h2 flex justify-end items-end text-zinc-400 >
    <span inline-flex flex-col text-center text-7xl text-teal font-semibold>
      <PhCrownSimpleBold text-4xl mb--2 />
      <span class="view-transition-title-20-3">S</span>
    </span>
    <span mb-2>hort</span>
  </h2>
</div>


---
layout: section
---

# 不只是代码生成

---
title: 不只是代码生成
layout: intro
---

<v-clicks>

- Github Copilot Cli
  - Code Whisperer (Fig)
  - Warp
- Commit Message
- 处理 PR，Code Review

</v-clicks>

---
layout: intro
---

# 其他工具

- [Perplexity](https://www.perplexity.ai/)
- [Devv](https://devv.ai)

---
transition: slide-up
---

# 设置

<div class="flex justify-center">
  <img src="/github-copilot-language.png" alt="Copilot Settings" class="w-4/5 opacity-80 rounded-md" />
</div>

<p class="text-center !mt-10 text-zinc">设置语言为中文</p>

<!--
默认使用 VSCode 的语言配置，但可以通过设置覆盖

但是对于生成 commit message 无效
-->

---
layout: intro
---

# 参考资料
- [开贴写一下我如何让 github copilot 完成我日常 50% 左右的工作](https://twitter.com/real_kai42/status/1728280569640018107)
- [Release party v1.84 🎉 | Copilot Updates](https://www.youtube.com/watch?v=i63DjsjdR3s)
- [Using GitHub Copilot in your IDE: Tips, tricks and best practices](https://github.blog/2024-03-25-how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/)
- [Copilot Best Practices (What Not To Do)](https://www.youtube.com/watch?v=2q0BoioYSxQ&list=PLKOP-QacfsTVPTEkkoMhDvu2c80VJUw05&index=4)
- [Master the core principles of prompt engineering with GitHub Copilot](https://www.youtube.com/watch?v=hh1nOX14TyY&list=PLKOP-QacfsTVPTEkkoMhDvu2c80VJUw05&index=5)

---
layout: center
class: 'text-center pb-5'
---

# 谢谢！

Slides on [slides.haydenhayden.com](https://slides.haydenhayden.com)
