---
title: React Web Framework
info: |
  ## React Web Framework
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
colorSchema: dark
---

<img class="size-10 rounded-full absolute top-10 border" src="https://pocket.haydenhayden.com/blog/202403241700326.jpg" alt="avatar" />

# React Web Framework <SkillIconsReactDark />

<h2 class="text-zinc">2024 究竟怎样开发一个网页</h2>

<a href="https://github.com/haydenull" target="_blank" alt="GitHub Haydenull" title="Open in GitHub" class="pt-12 text-base text-zinc-400 absolute bottom-14 !border-none !hover:text-white"><carbon-logo-github /> 启封 Hayden</a>


---
layout: center
title: 目录
---

<v-clicks>

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISR
- Next.js App Router 与 RSC
- Next.js 路由系统
- 全栈框架的后端能力
- Next.js 的 UX 优化
- SPA 模式下的 Framework

</v-clicks>

---
layout: center
title: <目录>Library and Framework
class: 'text-zinc-500'
---

- **Library and Framework** {.text-zinc-100}
- 渲染方式: CSR/SSR/SSG/ISR
- Next.js App Router 与 RSC
- Next.js 路由系统
- 全栈框架的后端能力
- Next.js 的 UX 优化
- SPA 模式下的 Framework

---
layout: two-cols
title: Library and Framework
class: "flex items-center"
transition: view-transition
---

<div class="flex flex-1 flex-col items-center">

# Library {.view-transition-title}

<div class="flex gap-10">
  <div class="flex flex-col items-center">
    <SkillIconsReactDark class="text-6xl view-transition-react" /> React
  </div>
  <div class="flex flex-col items-center">
    <SkillIconsVuejsDark class="text-6xl" /> Vue
  </div>
</div>
</div>

::right::

<div class="flex flex-1 flex-col items-center">

# Framework {.view-transition-framework-title}

<div class="flex gap-10">
  <div class="flex flex-col items-center">
    <SkillIconsNextjsDark class="text-6xl view-transition-next" /> Next.js
  </div>
  <div class="flex flex-col items-center">
    <SkillIconsRemixDark class="text-6xl" /> Remix
  </div>
  <div class="flex flex-col items-center">
    <SkillIconsNuxtjsDark class="text-6xl" /> Nuxt
  </div>
</div>
</div>

---
layout: two-cols
title: Library 与 Framework 的区别
class: 'h-50 my-auto'
---

# Library <SkillIconsReactDark class="text-2xl view-transition-react" /> {.view-transition-title}

<v-clicks>

- UI 渲染
- 状态管理

</v-clicks>

::right::

# Framework <SkillIconsNextjsDark class="text-2xl view-transition-next" /> {.view-transition-framework-title}

<v-clicks>

- 路由管理
- 全栈能力
- UX 优化
- 开箱即用

</v-clicks>

---
layout: center
title: <目录>常见渲染方式
class: 'text-zinc-500'
transition: view-transition
---

- Library and Framework
- **渲染方式: CSR/SSR/SSG/ISR** {.text-zinc-100.view-transition-title}
- Next.js App Router 与 RSC
- Next.js 路由系统
- 全栈框架的后端能力
- Next.js 的 UX 优化
- SPA 模式下的 Framework

---
layout: center
title: 常见渲染方式
---

# 常见渲染方式 {.view-transition-title}

| **CSR** | **SSR** | **SSG** | **ISR** |
| --- | --- | --- | --- |
| Client-Side Rendering | Server-Side Rendering | Static Site Generation | Incremental Static Regeneration |
| 客户端**渲染** | 服务端**渲染** | 服务端**生成** | 增量静态**生成** |

---
title: CSR
class: 'flex justify-center items-center gap-20'
---

# CSR

<Excalidraw drawFilePath="./csr.excalidraw.json" darkMode class="w-[500px]" />

---
layout: center
title: SSR
---

# SSR {.text-center}

<Excalidraw drawFilePath="./ssr.excalidraw.json" darkMode class="w-[650px]" />

---
title: SSG
class: 'flex justify-center items-center gap-20'
---

# SSG

<Excalidraw drawFilePath="./ssg.excalidraw.json" darkMode class="w-[520px]" />

---
title: ISR
class: 'flex justify-center items-center gap-20'
---

# ISR

<Excalidraw drawFilePath="./isr.excalidraw.json" darkMode class="w-[520px]" />


---
layout: center
title: <目录>RSC 与 Next.js App Router
class: 'text-zinc-500'
---

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISG
- **RSC 与 Next.js App Router** {.text-zinc-100}
- Next.js 路由系统
- 全栈框架的后端能力
- Next.js 的 UX 优化
- SPA 模式下的 Framework

---
title: React Server Component
class: 'flex justify-center items-center gap-20'
---

# RSC

<Excalidraw drawFilePath="./rsc.excalidraw.json" darkMode class="w-[520px]" />

---
title: Next.js 服务端渲染策略
class: 'flex flex-col'
---

# Next.js 服务端渲染策略 {.text-zinc-400.font-bold.!text-sm}

<div class="grid grid-cols-3 my-auto gap-10">
  <div>
    <h2>静态渲染</h2>
    <p class="text-zinc-400">Static Rendering (Default)</p>

```jsx
async function Article({ id }) {
  const content = await getArticle(id)
  return <p>{content}</p>
}
```

  </div>
  <div>
    <h2>动态渲染</h2>
    <p class="text-zinc-400">Dynamic Rendering</p>

```jsx
async function UserInfo({ id }) {
  const id = new URLSearchParams(window.location.search).get('id')
  const user = await getUserInfo(id)
  return <p>{user}</p>
}
```

  </div>
  <div>
    <h2>流式渲染</h2>
    <p class="text-zinc-400">Streaming Rendering</p>
    <img src="/streaming-rendering.png" alt="Streaming Rendering" />
  </div>
</div>


---
layout: center
title: <目录>Next.js 路由系统
class: 'text-zinc-500'
---

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISR
- RSC 与 Next.js App Router
- **Next.js 路由系统** {.text-zinc-100}
- 全栈框架的后端能力
- Next.js 的 UX 优化
- SPA 模式下的 Framework

---
layout: center
title: 定义路由
---

# 定义路由

<img src="/defining-routes.png" alt="Defining Routes" />

```jsx
// app/page.js
export default function Page() {
  return <h1>Hello, Next.js!</h1>
}
```


---
title: 动态路由
---

# 动态路由 {.!mb-[60px]}

```tsx
// app/blog/[slug]/page.tsx
export default function Page({ params }: { params: { slug: string } }) {
  return <div>My Post: {params.slug}</div>
}
```

<div class="h-[40px]"></div>

| Route | Example Url | `params` |
| --- | --- | --- |
| `app/blog/[slug]/page.js` | `/blog/a` | `{ slug: 'a' }` |
| `app/blog/[slug]/page.js` | `/blog/b` | `{ slug: 'b' }` |
| `app/blog/[slug]/page.js` | `/blog/c` | `{ slug: 'c' }` |

---
title: 布局
---

# 布局

<div class="grid grid-cols-2 gap-6 mt-[50px]">
  <div class="grid gap-4">

```jsx {1-3,8}
// app/dashboard/layout.js
export default function DashboardLayout({
  children,
}) {
  return (
    <section>
      <nav>nav</nav>
      {children}
    </section>
  )
}
```

```jsx
// app/dashboard/page.js
export default function Page() {
  return <h1>Hello, Dashboard!</h1>
}
```

  </div>

  <div class="grid gap-4">
    <img src="/layout.png" alt="Layout" />
    <img src="/layout-preview.png" alt="Layout Preview" />
  </div>
</div>

---
title: 平行路由
---
# 平行路由 <span class="text-zinc-500 text-base">(插槽)</span>

<img src="/parallel-routes.png" alt="Parallel Routes" class="rounded h-[400px] m-auto" />

---
title: 拦截路由
---

# 拦截路由 <a href="https://dribbble.com/" class="text-zinc-500 text-base">Dribbble</a>

<div class="grid gap-4 ml-[170px]" v-click.hide>
  <img src="/intercepting-routes-feed.png" alt="Intercepting Routes Feed" class="rounded h-[200px]" />
  <img src="/intercepting-routes-photo.png" alt="Intercepting Routes Photo" class="rounded h-[200px]" />
</div>

<img v-after src="/intercepting-routes-code.png" alt="Intercepting Routes Code" class="rounded absolute h-[400px] left-[140px] top-[110px]" />

---
layout: center
title: <目录>Next.js 的后端能力
class: 'text-zinc-500'
---

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISR
- RSC 与 Next.js App Router
- Next.js 路由系统
- **全栈框架的后端能力** {.text-zinc-100}
- Next.js 的 UX 优化
- SPA 模式下的 Framework

---
layout: center
title: Next.js 的后端能力
---

# Next.js 的后端能力

- 路由处理程序
- 服务端组件
- Server Actions
- Remix 的处理方式

---
title: 路由处理程序
---

# 路由处理程序

<img src="/route-handlers.png" alt="Route Handlers" class="rounded w-[720px] m-auto mt-[30px]" />

<div class="w-[720px] m-auto mt-[10px]">

```ts
import { NextRequest, NextResponse } from "next/server"

export async function POST(req: NextRequest) {
  const { startTime, duration, type } = await req.json()
  return NextResponse.json({
    success: true,
    message: "create pomodoro success",
  })
}
```

</div>

---
title: 服务端组件
---

# 服务端组件

<div class="h-[100px]"></div>

```tsx
export default async function Page() {
  const md = fs.readFileSync(`${process.cwd()}/README.md`, "utf8")
  const html = marked(md)

  return <div dangerouslySetInnerHTML={{ __html: html }} />
}
```

---
title: Server Actions
---

# Server Actions

```tsx {all|5-15}
'use client'

export default function Page() {
  async function createInvoice(formData: FormData) {
    'use server'

    const rawFormData = {
      customerId: formData.get('customerId'),
      amount: formData.get('amount'),
      status: formData.get('status'),
    }

    supabase.from('invoices').insert(rawFormData)
  }

  return <form action={createInvoice}>...</form>
}
```

---
title: Remix 的处理方式
---

# Remix 的处理方式

```tsx
export async function action({
  request,
}: ActionFunctionArgs) {
  const body = await request.formData();
  const todo = await fakeCreateTodo({
    title: body.get("title"),
  });
  return redirect(`/todos/${todo.id}`);
}

export async function loader() {
  return json(await fakeGetTodos());
}

export default function Todos() {
  const data = useLoaderData<typeof loader>();
  return (
    <div>
      <TodoList todos={data} />
      <Form method="post">
        <input type="text" name="title" />
        <button type="submit">Create Todo</button>
      </Form>
    </div>
  );
}
```

---
layout: center
title: <目录>Next.js 的 UX 优化
class: 'text-zinc-500'
---

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISR
- RSC 与 Next.js App Router
- Next.js 路由系统
- 全栈框架的后端能力
- **Next.js 的 UX 优化** {.text-zinc-100}
- SPA 模式下的 Framework

---
layout: center
title: Next.js 的 UX 优化
---

# Next.js 的 UX 优化

- Cache
- 定制组件 Link Img

---
title: Cache
---

# Cache

| **机制** | **缓存内容** | **存储地方** | **目的** | **期间** |
|---|---|---|---|---|
| 请求记忆（Request Memoization）| 函数返回值 | 服务端 | 在 React 组件树中复用数据|每个请求的生命周期 |
|数据缓存（Data Cache ）|	数据|服务端	|跨用户请求和部署复用数据	|持久（可重新验证）|
|完整路由缓存（Full Route Cache）|	HTML 和 RSC payload|	服务端|	降低渲染成本、提高性能|	持久（可重新验证）|
|路由缓存（Router Cache）|	RSC payload |	客户端	|减少导航时的服务端请求	|用户会话或基于时间|


---
title: Cache
layout: center
---

<img src="/cache.png" alt="Cache" class="rounded h-[500px]" />

---
title: RSC
layout: center
---

# RSC

1. 性能优化
   - 减小客户端包体积 {.text-zinc-400.text-sm}
   - 更快的首屏渲染 {.text-zinc-400.text-sm}
2. SEO 友好
3. 数据获取更快更安全
   - 服务端获取数据更安全 {.text-zinc-400.text-sm}
   - 更快看到数据 {.text-zinc-400.text-sm}
4. 代码更易维护
   - 客户端与服务端代码复用 {.text-zinc-400.text-sm}
   - 逻辑集中 {.text-zinc-400.text-sm}

---
title: 定制组件
layout: center
---

# 定制组件

- Link
- Image
- Metadata
- ...

---
layout: center
title: <目录>Next.js 的 UX 优化
class: 'text-zinc-500'
---

- Library and Framework
- 渲染方式: CSR/SSR/SSG/ISR
- RSC 与 Next.js App Router
- Next.js 路由系统
- 全栈框架的后端能力
- Next.js 的 UX 优化
- **SPA 模式下的 Framework** {.text-zinc-100}

---
layout: center
title: Next.js 的静态导出
---

# Next.js 静态导出

1. 服务端组件

next build 时生成静态 HTML {.text-zinc-400.text-sm.!mt-0}

2. 客户端组件

使用 API 获取数据 {.text-zinc-400.text-sm.!mt-0}

3. 路由处理程序

只支持 GET，执行并生成静态的 HTML json 等文件 {.text-zinc-400.text-sm.!mt-0}

4. 不支持的功能

Cookies、Headers、Redirects、Middleware、ISR 等 {.text-zinc-400.text-sm.!mt-0}

5. 部署

任何静态资源服务器，例如 Nginx {.text-zinc-400.text-sm.!mt-0}

---
layout: center
class: 'text-center pb-5'
---

# 谢谢！

Slides on [slides.haydenhayden.com](https://slides.haydenhayden.com)
