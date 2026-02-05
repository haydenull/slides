# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个基于 **Slidev** 的技术演讲幻灯片仓库，使用 PNPM workspace 管理多个独立的演示文稿。每个演讲都是一个独立的子项目，部署在 Vercel 上，访问地址为 `slides.haydenhayden.com`。

## 目录结构

```
slides/
├── 2023-08-31/          # 按日期组织的独立演讲项目
│   └── src/
│       ├── slides.md    # 幻灯片主要内容（Markdown）
│       ├── components/  # Vue 组件
│       ├── layouts/     # 自定义布局
│       └── public/      # 静态资源
├── 2024-03-23/
├── 2024-06-07/
├── 2024-07-12/
├── 2024-10-25/
├── dist/                # 构建产物（部署到 Vercel）
├── package.json         # 根 package.json
├── pnpm-workspace.yaml  # PNPM workspace 配置
└── vercel.json          # Vercel 部署配置（路由重写规则）
```

## 常用命令

### 根级别命令

```bash
# 构建所有演讲
pnpm build

# 代码检查
pnpm lint
```

### 单个演讲开发

进入具体演讲目录（如 `2024-06-07/`）后：

```bash
# 启动开发服务器（自动打开浏览器）
pnpm dev

# 构建静态站点
pnpm build

# 导出为 PDF（每页一幻灯片）
pnpm export
```

## 技术栈

- **Slidev** - 基于 Web 的演示框架
- **Vue 3** - UI 框架
- **TypeScript** - 类型安全
- **Vite** - 构建工具
- **UnoCSS** - 原子化 CSS 引擎
- **PNPM** - 包管理器（workspace 模式）

## 创建新演讲

1. 创建新目录（建议格式：`YYYY-MM-DD/`）
2. 复制 `package.json` 并调整版本号
3. 创建 `src/slides.md` 作为主内容文件
4. 按需添加 `src/components/`、`src/layouts/` 等目录
5. 在根目录 `pnpm install` 安装依赖

## 部署说明

- 构建产物输出到 `dist/` 目录
- Vercel 根据 `vercel.json` 中的 `rewrites` 配置处理路由
- 每个演讲的 PDF 导出文件存放在各自目录的根目录
- 根路径重定向到 `https://haydenhayden.com/talk`

## 注意事项

- 每个 `slides.md` 文件独立管理其演讲内容
- 使用 UnoCSS 进行样式定制
- `vercel.json` 的路由重写规则修改后需同步更新 `scripts/redirects.ts`（如果存在）
- 导出 PDF 功能依赖 playwright-chromium
