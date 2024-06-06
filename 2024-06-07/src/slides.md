---
title: GitLab CI/CD 101
info: |
  ## GitLab CI/CD 入门指南
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
colorSchema: dark
---
<img class="size-10 rounded-full absolute top-10 border" src="https://pocket.haydenhayden.com/blog/202403241700326.jpg" alt="avatar" />

# GitLab CI/CD 101 <DeviconGitlab />

<h2 class="text-zinc">GitLab CI/CD 入门指南</h2>

(如无说明，本 Slide 提到的 GitLab 为 13.12.15 版本) {.text-zinc/40.text-sm}

<a href="https://github.com/haydenull" target="_blank" alt="GitHub Haydenull" title="Open in GitHub" class="pt-12 text-base text-zinc-400 absolute bottom-14 !border-none !hover:text-white"><carbon-logo-github /> 启封 Hayden</a>

---
layout: section
---

# GitLab CI/CD 概述 {.text-5xl!}

---
class: "flex flex-col justify-center"
---


## GitLab CI/CD 是什么 {.my-4}

<!-- <img src="/dev-workflow.excalidraw.png" /> -->

<v-clicks>

- CI: Continuous Integration 持续集成
- CD: Continuous Delivery 持续交付
- CD: Continuous Deployment 持续部署

</v-clicks>

<!--
持续集成是指频繁地将代码集成到主干分支中，并通过自动化的测试来验证每次集成。其目的是尽早发现集成问题，减少集成过程中的冲突和错误。

持续交付是指在持续集成的基础上，将代码自动化部署到类似于生产环境的预发布环境，并进行进一步的测试和验证。目的是确保代码可以随时安全地发布到生产环境。

持续部署是持续交付的进一步发展，是指代码通过所有测试和验证后，自动部署到生产环境，无需人工干预。
-->

---
layout: image
image: /ci-cd-workflow.png
class: p-0
title: CI/CD图示
---

<div class="size-full bg-black/20"></div>


---
layout: center
---
## 实现 CI/CD 的工具 {.text-center.my-10}

<div class="flex gap-10">

<span class="flex flex-col items-center text-sm p-4">
  <DeviconJenkins class="size-20" />
  Jenkins
</span>
<span class="flex flex-col items-center text-sm p-4">
  <LogosTravisCi class="size-20" />
  Travis
</span>
<span class="flex flex-col items-center text-sm p-4">
  <CodiconGithub class="size-20" />
  GitHub Actions
</span>
<span class="flex flex-col items-center text-sm p-4 bg-zinc-600/20 rounded">
  <DeviconGitlab class="size-20" />
  GitLab CI
</span>

</div>

---
layout: section
---

# GitLab CI/CD 基本概念 {.text-5xl!}

---
layout: center
title: 基础概念图示
---

<img src="/ci-concepts-excalidraw.png" />

<!--
一个完整的 Pipeline 由多个 Stages 组成，每个 Stage 中包含一个或多个 Jobs。

Stage 是 Pipeline 中的一个阶段，代表了一组相关的 Job。顺序执行。

Job 是 Pipeline 中的最小执行单元，代表了一项具体的任务，例如代码编译、测试、部署等。每个 Job 都有独立的运行环境。咱们公司内一般都是用 image 指定特定的 Docker 镜像。同一个 Stage 中的 Job 是并行执行的。

Runner 是执行 Jobs 的工作进程，Job 通过 tag 指定特定的 Runner。
-->

---
layout: center
---
## 配置文件 .gitlab-ci.yml {.my-5}

```yaml
stages:
  - test
  - build
  - deploy

job_name:
  stage: test # 所属 stage
  tags: # 用于选择合适的 Runner 执行 Job
    - k8s
  image: harbor-registry.inner.youdao.com/hikari/node-lite:18
  rules: # 规则，用于控制 Job 是否应该创建或执行
    - if: '$CI_COMMIT_TAG =~ /^v\d+\.\d+\.\d+$/' # 线上环境：master 分支打 tag 触发，tag 格式为 v1.0.0
      when: manual # 手动触发
  script: # Job 执行的命令
    - npm run test
```

---
layout: section
---
## 高级功能 {.text-5xl!}

---
---
## 变量 Variables {.text-center.my-5}

<div class="flex gap-10 justify-center">
<div v-click>

#### [预定义 CI/CD 变量](https://docs.gitlab.com/ee/ci/variables/predefined_variables.html)

- CI_COMMIT_REF_NAME
- CI_COMMIT_TAG
- CI_SERVER_HOST
- CI_PROJECT_PATH


</div>
<div v-click>

#### .gitlab-ci.yml 中定义变量

```yaml
variables: # 全局变量
  RANCHER_CLUSTER_PROD: k8s-prod-common1
  RANCHER_CLUSTER_PRE: k8s-dev-common1

job_name: # job 变量
  variables:
    RANCHER_NAMESPACE: default
    RANCHER_APP_NAME: app-name
```

</div>
</div>
<div class="w-2/3 m-auto mt-4" v-click>

#### Web 界面中定义变量

<img src="/ci-variables.png" class="rounded" />

</div>

<!--
还有一些不常用的可以看文档
-->

---
layout: center
---
## 缓存 Cache {.text-center.my-5}

在 Jobs 及 Pipeline 之间共享文件，常用于缓存依赖包，提高构建速度。

```yaml {all|5-10}
build-app:
  script:
    - pnpm install
    - pnpm build
  cache:
    key:
      files:
        - pnpm-lock.yaml
  paths:
    - .pnpm-store
```

---
layout: center
---
## 工件 Artifacts {.text-center.my-5}

Artifacts 是 Jobs 生成的文件，可以在 Pipeline 的后续 Jobs 中使用。常用于传递构建结果、测试报告等。

```yaml {all|5-8}
build-app:
  script:
    - pnpm install
    - pnpm build
  artifacts:
    name: $CI_COMMIT_REF_SLUG
    paths:
      - dist
```

---
layout: center
---
## 代码复用-include

将公共的 CI 配置放在单独的文件中，然后在 .gitlab-ci.yml 文件中使用 include 指令引入这些公共配置文件。

```yaml
include:
  - project: "hikari/f2e/common-components/common-ci-cd"
    ref: master
    file: "/templates/web-docker.yml"
```

---
layout: center
---
## 代码复用-extends

`extends` 指令允许一个 job 继承另一个 job 的配置。可以定义一个基础 job，然后让其他 job 继承它。
````md magic-move
```yaml
.tests:
  script: rake test
  stage: test

rspec:
  extends: .tests
  script: rake rspec
```

```yaml
rspec:
  script: rake rspec
  stage: test
```
````

---
layout: center
---
## 代码复用-anchor

锚点（anchors）是用来简化和复用配置的一种 YAML 语法特性。它们允许你定义一组配置片段，并在同一个文件中多次引用这些片段。

````md magic-move
```yaml
.job_template: &job_configuration
  image: ruby:2.6
  services:
    - postgres
    - redis

test1:
  <<: *job_configuration
  script:
    - test1 project
```

```yaml
test1:
  image: ruby:2.6
  services:
    - postgres
    - redis
  script:
    - test1 project
```
````

---
layout: center
---
## 代码复用-CI/CD Components

GitLab 16 引入 {.text-sm.text-zinc-500}

GitLab CI/CD Components 是可重用的 CI/CD 配置片段，可以在不同的项目中共享和重用。

```yaml
# 组件
spec:
  inputs:
    stage:
      default: test
---
unit-test:
  stage: $[[ inputs.stage ]]
  script: echo unit tests
```

```yaml
# 引用组件
include:
  - component: $CI_SERVER_FQDN/myorg/ruby/test@1.0.0
    inputs:
      stage: verify
```



---
layout: section
---
## 公共 CI 配置 {.text-5xl!}


---
layout: center
title: 公共 ci 流程图示
---
<img src="/common-ci-excalidraw.png" />


<Arrow v-click x1="214" y1="274" x2="304" y2="274" />
<div v-after.hide class="w-[200px] h-[300px] absolute blur-xl left-[280px] top-[120px] bg-zinc-900/90 rounded-xl"></div>
<Arrow v-click x1="458" y1="274" x2="546" y2="274" />
<div v-after.hide class="w-[200px] h-[300px] absolute blur-xl left-[530px] top-[120px] bg-zinc-900/90 rounded-xl"></div>
<Arrow v-click x1="698" y1="274" x2="764" y2="274" />
<div v-after.hide class="w-[200px] h-[300px] absolute blur-xl left-[740px] top-[120px] bg-zinc-900/90 rounded-xl"></div>



<!--
build-app: 自动判断包管理器，安装依赖，构建，cache 缓存依赖，生成 artifacts

prepare-deploy: 部署前准备，依据 app-type 判断是否需要 cdn

deploy: 部署 rancher

changelog: 生成 changelog，修改版本号
-->

---
layout: center
---
## 遇到的问题 {.my-5}

- DEBUG 变量导致 cache 失效
- cache 无法使用 job 变量
- before_script 覆盖

---
layout: center
---

## 如何使用 {.text-center}

https://docs.popo.netease.com/lingxi/a89c80332d954928bfd4a891ec8e5f92

---
layout: center
---

## 参考资料 {.my-5}
- [GitLab CI CD Tutorial for Beginners](https://www.youtube.com/watch?v=qP8kir2GUgo&t=2439s)
- [Get started with GitLab CI/CD](https://docs.gitlab.com/ee/ci/)
- [使用公共 CI 部署网页](https://docs.popo.netease.com/lingxi/a89c80332d954928bfd4a891ec8e5f92)

---
layout: center
class: 'text-center pb-5'
---

# 谢谢！

Slides on [slides.haydenhayden.com](https://slides.haydenhayden.com)
