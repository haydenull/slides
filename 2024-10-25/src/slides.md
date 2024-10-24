---
title: 微信小程序 CI/CD 实践
info: |
  ## 微信小程序 CI/CD 实践
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
colorSchema: dark
---

<img class="size-10 rounded-full absolute top-10 border" src="https://pocket.haydenhayden.com/blog/202403241700326.jpg" alt="avatar" />

# 微信小程序 CI/CD 实践 <DeviconGitlab />  <MingcuteWechatMiniprogramFill class="text-green-500 size-21 -mb-1.5" />

<h2 class="text-zinc">使用 GitLab CI/CD 实现微信小程序的自动化构建和部署</h2>

<a href="https://github.com/haydenull" target="_blank" alt="GitHub Haydenull" title="Open in GitHub" class="pt-12 text-base text-zinc-400 absolute bottom-14 !border-none !hover:text-white"><carbon-logo-github /> 启封 Hayden</a>

---
layout: center
title: 开始之前：传统开发与部署的痛点
---

# 传统开发与部署的痛点

<img src="/drawback.png" />

<!-- - **繁琐的流程**：一个 IDE 修改代码并打包，一个 IDE 上传
- **容易出错**： 一切依赖人工，容易出现上传版本错误，或者无法找到上传的版本对应的代码
- **操作成本高**：体验版小程序无法满足多测试环境需求，需要频繁手动修改代码再手动部署
- **协作不便**：多人开发时，只有一个人可以上传 -->

---
layout: center
title: GitLab CI 的引入：自动化打包与部署
---

# GitLab CI 的引入：自动化打包与部署

<img src="/advantage.png" />

<!-- - **自动化流程**：代码推送到 GitLab 后，CI 自动完成打包并上传
- **减少错误**：预设流程减少了人工干预，降低人为失误的几率，版本携带 commit 信息
- **节省时间**：开发人员可以专注于开发，减少繁杂的部署时间
- **团队协作更流畅**：多人协作时，每个人都可以部署 -->

---
layout: center
title: 使用 GitLab CI 模板的工作流程
---

# GitLab CI 模板的工作流程

<img width="700" src="/ci-flow.png" />

<!-- 1. **代码推送**：开发者将代码推送至 GitLab 仓库
2. **CI 启动**：GitLab CI 自动开始打包微信小程序代码
3. **打包过程**：安装依赖并打包代码
4. **自动部署**：下载 upload js 并上传产物到微信后台 -->

---
layout: center
title: 如何使用
---

# 如何使用

1. 在项目根目录增加 `.gitlab-ci.yml` 文件并引入 CI 模板
2. 在 `variables` 中配置 `APP_ID` 和 `APP_CODE_UPLOAD_SECRET`

```yaml
# 模板仓库：https://gitlab.corp.youdao.com/hikari/f2e/common-components/common-ci-cd
include:
  - project: "hikari/f2e/common-components/common-ci-cd"
    ref: master
    file: "/templates/weapp.yml"
```

https://docs.popo.netease.com/lingxi/271b51269cf044899829536336c5e989?xyz=1727254648147