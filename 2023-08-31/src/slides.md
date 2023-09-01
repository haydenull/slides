---
layout: cover
highlighter: shiki
css: unocss
transition: fade-out
lineNumbers: true
---

<h1 class="font-mono">fetch-bot</h1>

## 接口请求助手

<div uppercase text-sm tracking-widest mt-1>
启封 Hayden
</div>

<a href="https://github.com/haydenull" class="absolute top-0 left-0 mx-10 my-12 border-none! cursor-pointer"><img class="w-10 h-10 rounded-full shadow" target="_blank" src="/avatar.png" /></a>
<div absolute right-0 bottom-0 mx-10 my-12 flex="~ col" text-sm text-right>
  <div>Hikari FE</div>
  <div text-sm text-gray-400>2023-08-31</div>
</div>

---
transition: slide-left
growX: 10
growY: 90
---

# Why fetch-bot

<v-click>

## 前端数据可靠性

</v-click>

<LightOrDark>
  <template #dark>
    <v-click><img src="/front-data.excalidraw.dark.png" class="mt-8 rounded shadow-sm" /></v-click>
  </template>
  <template #light>
    <v-click><img src="/front-data.excalidraw.light.png" class="mt-8 rounded shadow-sm" /></v-click>
  </template>
</LightOrDark>


<v-click><Arrow x1="400" y1="500" x2="170" y2="350" /></v-click>

---
layout: intro
growX: 70
growY: 50
---

# Features

<v-clicks>

- 类型友好
- 运行时数据校验 <a href="https://valibot.dev/" class="text-gray-400 text-sm ml-2" target="_blank" >valibot</a>
- 自动 Mock
- 无侵入<span class="text-gray-400 text-sm ml-2">适配任意请求方法</span>
- 小尺寸<span class="text-gray-400 text-sm ml-2">按需加载</span>
- 高度自定义<span class="text-gray-400 text-sm ml-2">接口延时，自定义 handler</span>

</v-clicks>

---
layout: intro
growX: 0
growY: 50
---

# 安装

<pre text-3xl flex font-mono class="select-none!">
  <span text-gray:50>yarn </span>
  <span text-green>add </span>
  <span text-transparent bg-clip-text bg-gradient-to-r from-blue-300 to-blue-500>@velo/fetch-bot valibot</span>
</pre>
<pre text-3xl flex font-mono class="select-none!">
  <span text-gray:50>yarn </span>
  <span text-green>add </span>
  <span text-transparent bg-clip-text bg-gradient-to-r from-blue-300 to-blue-500>@velo/@velo/mock msw</span>
  <span text-gray:50> -D</span>
</pre>

---
layout: intro
growX: 80
growY: 60
---

# 引入

```ts {2-4|6-8|11-15|all}
// src/util/fetchBot.ts
import { initFetchBot } from '@velo/fetch-bot'
import * as random from '@velo/mock'
import { setupWorker, rest } from 'msw'

const mswWorker = import.meta.env.PROD ? null : setupWorker()
const mswRest = import.meta.env.PROD ? null : rest
const mockjsRandom = import.meta.env.PROD ? null : random

if (mswWorker) mswWorker.start()
const fetchBot = initFetchBot({
  worker: mswWorker,
  rest: mswRest,
  random: mockjsRandom,
})

export default fetchBot
```

---
layout: intro
growX: 50
growY: 70
---

# 使用

```ts {5|7,19|8-11|12-18|all}
// src/services/demo.ts
import axios from 'axios'
import { number, object, string } from 'valibot'

import fetchBot from '@/util/fetchBot'

export const getStudentInfo = fetchBot(
  async (id: number) => {
    const res = await axios.get(`/api/student/${id}`)
    return res.data
  },
  {
    pathSchema: '/api/student/:id', // 代理接口的路径
    responseSchema: object({        // 接口返回的数据结构
      name: string(),
      age: number(),
    }),
  },
)
```

---
layout: intro
growX: 50
growY: 10
---

# 效果

<img src="/demo.png" class="mt-8 rounded shadow-sm" />

---
layout: intro
growX: 80
growY: 20
---

# 自定义

- `overrides`<span class="text-gray-400 text-sm ml-2">覆盖指定部分的返回值</span>
- `delay`<span class="text-gray-400 text-sm ml-2">指定延迟时间</span>
- `action`<span class="text-gray-400 text-sm ml-2">完全自定义接口的动作</span>
- `ignoreValidation`<span class="text-gray-400 text-sm ml-2">是否忽略接口的返回值校验结果</span>

---
layout: intro
growX: 50
growY: -20
---

# 可能性

<v-clicks depth="2">

- <span class="text-green-600">提升项目可读性</span>
  - 全接口 Mock，随时随地能跑起来项目
  - 随意修改想要的数据，方便调试
- <span class="text-green-600">提升 Mock 系统维护体验</span>
  - 物理位置上将 Mock 与接口请求代码放在一起
  - 降低 Mock 系统维护成本
- <span class="text-green-600">线上问题排查</span>
  - 自动校验数据，打印错误日志

</v-clicks>

---
layout: section
growX: 50
growY: 120
---

# 如何实现

---
layout: center
---

<LightOrDark>
  <template #dark>
    <img src="/theory.excalidraw.dark.png" class="mt-8 rounded shadow-sm" />
  </template>
  <template #light>
    <img src="/theory.excalidraw.light.png" class="mt-8 rounded shadow-sm" />
  </template>
</LightOrDark>

---
layout: intro
growX: 50
growY: -10
---

# 问题

## 部分代码<span class="text-green-500">需要</span>打包 部分代码<span class="text-red-500">不需要</span>打包

<v-clicks>

- <span class="text-green-500">valibot</span>
- <span class="text-red-500">msw</span>
- <span class="text-red-500">mockjs</span>

</v-clicks>

---
layout: intro
growX: 100
growY: 70
---

# Tree shaking 友好

<v-clicks>

- 支持 ES Module
- 独立导出<span class="text-gray-400 text-sm ml-2">对比 zod 与 valibot</span>
- sideEffect 管理

</v-clicks>

---
layout: iframe
url: https://rollupjs.org/repl/?version=3.28.0&shareable=JTdCJTIyZXhhbXBsZSUyMiUzQW51bGwlMkMlMjJtb2R1bGVzJTIyJTNBJTVCJTdCJTIyY29kZSUyMiUzQSUyMiUyRiUyRiUyMFRSRUUtU0hBS0lORyU1Q25pbXBvcnQlMjAlN0IlMjBmYWtlciUyMCU3RCUyMGZyb20lMjAnLiUyRnRlc3QuanMnJTNCJTVDbiU1Q25pZiUyMChmYWxzZSklMjAlN0IlNUNuJTIwJTIwY29uc3QlMjBteUZha2VyJTIwJTNEJTIwZmFrZXIlNUNuY29uc29sZS5sb2cobXlGYWtlciklNUNuJTdEJTIyJTJDJTIyaXNFbnRyeSUyMiUzQXRydWUlMkMlMjJuYW1lJTIyJTNBJTIybWFpbi5qcyUyMiU3RCUyQyU3QiUyMmNvZGUlMjIlM0ElMjJpbXBvcnQlMjAlN0IlN0QlMjBmcm9tJTIwJy4lMkZ0ZXN0LmpzJyUyMiUyQyUyMmlzRW50cnklMjIlM0FmYWxzZSUyQyUyMm5hbWUlMjIlM0ElMjJtYXRocy5qcyUyMiU3RCUyQyU3QiUyMmNvZGUlMjIlM0ElMjJjbGFzcyUyMEZha2VyJTIwJTdCJTVDbiUyMCUyMGNvbnN0cnVjdG9yKCklMjAlN0IlN0QlNUNuJTIwJTIwbWV0aG9kKCklMjAlN0IlNUNuJTIwJTIwJTIwJTIwd2luZG93LmElMjAlM0QlMjAxJTVDbiUyMCUyMCU3RCU1Q24lN0QlNUNuJTVDbmV4cG9ydCUyMGNvbnN0JTIwZmFrZXIlMjAlM0QlMjBuZXclMjBGYWtlcigpJTIyJTJDJTIyaXNFbnRyeSUyMiUzQWZhbHNlJTJDJTIybmFtZSUyMiUzQSUyMnRlc3QuanMlMjIlN0QlNUQlMkMlMjJvcHRpb25zJTIyJTNBJTdCJTIyb3V0cHV0JTIyJTNBJTdCJTIyZm9ybWF0JTIyJTNBJTIyZXMlMjIlN0QlMkMlMjJ0cmVlc2hha2UlMjIlM0F0cnVlJTdEJTdE
scale: 0.6
---

---
layout: intro
---

# Solution

<v-clicks>

- 迁移改造 `@velo/mock`
- 将依赖从 fetch-bot 内置改为使用者传入

</v-clicks>

---
layout: intro
growX: 70
growY: 30
growSize: 0.6
---

# Roadmap

<v-clicks>

- yapi-bee 一键生成 fetch-bot 需要的参数 <span class="text-gray-400 text-sm ml-2">valibot schema, pathSchema</span>
- 在网页中注入调试面板，随时修改接口数据
- 线上接口数据异常时告警？

</v-clicks>

---
layout: center
class: 'text-center pb-5'
growX: 50
growY: 120
---

# 谢谢！

Slides on [slides.haydenhayden.com](https://slides.haydenhayden.com)
