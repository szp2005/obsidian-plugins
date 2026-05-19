---
images: ["/og/how-to-publish-obsidian-notes-to-a-blog.webp"]
title: "Obsidian Vault 发布：将笔记转化为博客"
author: "Alex Chen"
date: 2026-04-29
slug: how-to-publish-obsidian-notes-to-a-blog
description: "提供一个决策框架，包含对比表格（成本 vs. 技术技能 vs. 自定义程度），帮助用户选择合适的发布方法。"
keywords: ["Obsidian Publish", "digital garden", "static site generator", "Obsidian to Hugo", "Obsidian Quartz", "publish notes online", "Obsidian GitHub Pages", "Markdown blog"]
draft: false
type: "informational"
tags: ["turn", "obsidian", "vault", "into"]
---

_作为一名亚马逊联盟成员，我们从符合条件的购买中赚取佣金。本文可能包含联盟链接。_

# 如何将 Obsidian 笔记发布到博客：所有方法比较（2024）

---

## TL;DR

- **Obsidian Publish** 每月费用 $8–$16，设置只需 10 分钟——如果你想零摩擦且不介意付费，那它就物有所值。
- **Quartz + GitHub Pages** 是最佳免费选项：专为 Obsidian Vault 设计，原生支持 wikilinks，自动部署。
- **Hugo 和 Astro** 提供了完全的设计控制权，但需要真正的技术投入——只有当自定义程度比发布速度更重要时才选择它们。

---

## 目录

1. [为什么要将 Obsidian Vault 变成公共博客？](#why)
2. [方法一：Obsidian Publish（官方途径）](#obsidian-publish)
3. [方法二：免费静态网站生成器](#ssg-overview)
4. [深入探讨——对比适用于 Obsidian 的最佳 SSG](#ssg-comparison)
5. [分步指南：使用 Quartz 和 GitHub Pages 发布](#quartz-tutorial)
6. [已发布笔记的 SEO](#seo)
7. [使用 GitHub Actions 自动化部署](#automation)
8. [哪种方法适合你？最终比较](#final-comparison)
9. [常见问题](#faq)
10. [结论](#conclusion)

---

## 1. 为什么要将 Obsidian Vault 变成公共博客？ {#why}

你的 Obsidian Vault 已经是一个结构化、相互关联的知识体系。发布它并不意味着将文件复制到 WordPress——它意味着向需要它的人展示你已经构建的内容。

**数字花园模型**与传统博客不同。你不需要等到文章“完成”。笔记处于永久草稿模式，随着你的学习而成长。读者可以看到你的思维实时演变。它诚实，并且——实际上——这意味着你可以更频繁地发布，减少焦虑。

除了理念之外，实际的理由也很充分：

- **个人品牌。** 公共知识库在搜索引擎中排名靠前，获得链接，并比简历更能展示能力。
- **公开学习。** 读者纠正你的错误，提供反例，并指出你错过的论文。反馈循环使你的笔记更好。
- **单一事实来源。** 当你的 Obsidian Vault 就是你的博客时，你只需编写一次。无需在应用程序之间复制粘贴，没有格式偏差。

唯一的问题是哪种发布路径适合你的情况。这正是本指南要回答的。

---

## 2. 方法一：使用 Obsidian Publish 的官方途径 {#obsidian-publish}

[Obsidian Publish](URL_PLACEHOLDER_1) 是内置的第一方发布服务。你支付订阅费，选择哪些笔记上线，其余由 Obsidian 处理。

### 工作原理

在 Obsidian 内部，打开任何笔记并点击发布图标（左侧边栏的纸飞机图标）。你会看到一个差异视图，显示哪些笔记未发布、已修改或已上线。点击你想要的笔记，点击发布，它们会在几秒钟内出现在 `your-site.obsidian.site`。

### 分步设置

1. 前往 **设置 → 核心插件 → Obsidian Publish** 并启用它。
2. 打开发布面板（Ctrl/Cmd + P → “发布更改”）。
3. 创建新网站并选择子域名。
4. 选择你希望公开的笔记，然后点击**发布**。
5. 可选：在发布设置面板中配置自定义域名。

### 定价

- 个人网站**每月 $8**（按年计费）。
- 按月计费则**每月 $16**。

### 优点

- 零技术开销——在 Obsidian 内部一键操作。
- Wikilinks、反向链接和图谱视图自动工作。
- 选择性发布：你的私人笔记默认保持私密。
- Obsidian 处理 SSL、CDN 和移动响应式布局。

### 缺点

- 持续的永久成本。一年花费 $96–$192。
- 自定义受限：你可以添加自定义 CSS，但无法更改网站的核心结构。
- 没有插件，没有自定义 JavaScript 逻辑。
- 基本的 SEO 控制——没有服务器端渲染，元标签控制有限。

**总结：** 如果你重视时间胜过金钱，并且对接触代码不感兴趣，那么 Obsidian Publish 是正确的选择。如果你发布的笔记少于 50 条，并且只想完成任务，这就是你的答案。

---

## 3. 方法二：免费静态网站生成器 {#ssg-overview}

静态网站生成器（SSG）将你的 Markdown 文件转换为纯 HTML、CSS 和 JavaScript。因为 Obsidian 笔记已经是 Markdown，SSG 是一个自然的匹配。

一般工作流程如下：

```
Obsidian Vault → Git Repository → SSG Build Step → Static HTML → Hosted on CDN
```

你在 Obsidian 中写作。推送到 GitHub 会触发自动构建。SSG 解析你的 Markdown，解析链接，应用主题，并输出一个包含 HTML 文件的文件夹。像 [Netlify](URL_PLACEHOLDER_2) 或 [Vercel](URL_PLACEHOLDER_3) 这样的托管平台会在几秒钟内将该文件夹全局部署——两者都提供真正免费的套餐，可以处理大量流量。

**相较于 Obsidian Publish 的主要优势：**

- 在 Netlify、Vercel 或 GitHub Pages 上**免费托管**。
- **完全设计控制**——更改每个像素。
- **更好的 SEO**——服务器渲染的 HTML，完全控制元标签、站点地图和规范 URL。
- **无供应商锁定**——你的笔记仍以 Markdown 文件形式存在。

折衷方案是设置时间。如果你是新手，Quartz 预算 1-3 小时，Hugo 或 Astro 预算 4-8 小时。

---

## 4. 深入探讨：对比适用于 Obsidian 的最佳 SSG {#ssg-comparison}

### Quartz

[Quartz](URL_PLACEHOLDER_4) 专为 Obsidian Vault 设计。它原生支持 `[[wikilinks]]`，渲染反向链接，并生成交互式图谱视图——所有这些都无需配置。如果你知道如何使用 Git，你可以在一小时内拥有一个实时网站。

### Hugo

Hugo 是目前最快的 SSG。一个拥有 1,000 页的网站的构建时间不到 1 秒。它拥有成熟的插件生态系统、出色的 SEO 支持和数百个主题。学习曲线是真实存在的——Hugo 的模板语言（Go templates）一开始并不直观。[Obsidian-to-Hugo](URL_PLACEHOLDER_5) 插件和 PaperMod 等社区主题使集成更加顺畅。

### Astro

Astro 是一个现代框架，默认不提供 JavaScript，这意味着你的页面加载速度快。它支持在 Markdown 文件中使用 React、Vue 和 Svelte 组件，因此你以后可以添加交互式功能。FreeCodeCamp 上有一个专门的 Obsidian-Astro 集成。如果你是一名开发人员，想要一个可以发展成为完整 Web 应用程序的博客，那么它是最佳选择。

### Jekyll

Jekyll 是最老的玩家。GitHub Pages 原生运行 Jekyll——只需推送一个包含 `_config.yml` 的仓库，你的网站就可以上线，无需构建管道。缺点是：`[[wikilinks]]` 无法原生转换。你需要 `jekyll-wikilinks` 插件，而且其生态系统没有跟上新工具的步伐。

---

## 5. 分步指南：使用 Quartz 和 GitHub Pages 发布你的 Vault {#quartz-tutorial}

这是从零到实时数字花园的最快路径。先决条件：一个 GitHub 帐户和本地安装的 Git。

### 步骤 1：Fork 并克隆 Quartz

前往 [Quartz GitHub 仓库](URL_PLACEHOLDER_6)并点击 **Fork**。然后将你的 fork 克隆到本地：

```bash
git clone https://github.com/YOUR_USERNAME/quartz.git
cd quartz
npm install
```

### 步骤 2：添加你的笔记

将你的 Obsidian 笔记复制到 `/content` 目录。保持你的文件夹结构——Quartz 会将其保留为 URL 路径。你的 Vault 的 `index.md` 将成为主页。

```bash
cp -r ~/path/to/your/vault/* ./content/
```

### 步骤 3：配置 Quartz

编辑根目录中的 `quartz.config.ts`：

```typescript
const config: QuartzConfig = {
  configuration: {
    pageTitle: "Your Site Name",
    baseUrl: "your-username.github.io/quartz",
    // Change to your GitHub Pages URL or custom domain
  },
}
```

设置 `ignorePatterns` 以排除你希望私有的任何文件夹：

```typescript
ignorePatterns: ["private", "templates", ".obsidian"],
```

### 步骤 4：本地构建和预览

```bash
npx quartz build --serve
```

打开 `http://localhost:8080`。验证 wikilinks 是否正确解析，图谱视图是否正常工作。

### 步骤 5：通过 GitHub Pages 推送和部署

Quartz 包含预构建的 GitHub Actions 工作流程。推送你的更改：

```bash
git add .
git commit -m "Initial vault publish"
git push origin main
```

在你的 GitHub 仓库设置中：
- 前往 **设置 → Pages**。
- 将**来源**设置为 **GitHub Actions**。
- `.github/workflows/deploy.yml` 中的工作流程将处理其余部分。

在 2-3 分钟内，你的网站将在 `https://your-username.github.io/quartz` 上线。

### 步骤 6：设置自定义域名（可选）

从 [Namecheap](URL_PLACEHOLDER_7) 购买域名。在你的域名的 DNS 设置中，添加：

```
Type: CNAME
Name: www
Value: your-username.github.io
```

在你的 `/content` 目录中添加一个只包含你的域名（`www.yourdomain.com`）的 `CNAME` 文件。更新 `quartz.config.ts` 中的 `baseUrl` 以匹配。

---

## 6. 不要忘记 SEO：优化你已发布的笔记 {#seo}

发布笔记而不注意 SEO 会浪费流量潜力。以下是一个具体的清单。

### YAML Frontmatter 是你的元数据层

你发布的每条笔记都应该有一个 Frontmatter [块：

```yaml
---
title: "间隔重复如何重塑我的学习习惯"
author: "Alex Chen"
description: "我如何结合使用 Anki 和 Obsidian 来记住 90% 的阅读内容。"
date: 2024-03-15
tags: [learning, memory, obsidian]
slug: spaced-repetition-obsidian-study
draft: false
---
```

- `title` 成为 `<title>` 标签和 H1。首先为人类撰写，自然地包含你的关键词。
- `description` 成为元描述。保持在 155 个字符以内。
- `slug` 设置你的 URL。使用小写、连字符，不含特殊字符。Quartz、Hugo 和 Astro 都遵循此字段。
- 如果你希望构建但未索引任何笔记，请将 `draft: true` 添加到该笔记上——在你的 SSG 配置中添加 `noindex` 规则。

### Wikilinks 和 URL 结构

发布 Obsidian 笔记时最大的技术 SEO 风险是内部链接断裂。`[[Note Title]]` wikilinks 需要在 HTML 中变为 `<a href="/note-title">`。

- **Quartz** 自动处理。
- **Hugo**：在构建之前使用 `hugo-obsidian` 预处理器工具转换 wikilinks。
- **Astro**：`remark-wiki-link` 插件在 `astro.config.mjs` 中处理转换。
- **Jekyll**：安装 `jekyll-wikilinks` gem 并将其添加到 `_config.yml`。

每次进行重大结构调整后，审核你的内部链接。断裂的内部链接不仅损害用户体验——它还会流失 PageRank。

### 站点地图和 Robots

Quartz 自动生成 `sitemap.xml`。对于 Hugo，在 `hugo.toml` 中设置 `enableRobotsTXT = true` 和 `sitemap.changefreq = "weekly"`。在网站上线的第一周内将站点地图 URL 提交到 Google Search Console。

### 清洁的 URL Slug

避免发布标题为“202401 会议笔记间隔重复 v3 FINAL”的笔记。在笔记公开之前，请正确重命名它。笔记文件名是大多数 SSG 中的默认 slug。像 `spaced-repetition-study-method` 这样的 slug 在各项指标上都优于 `202401-meeting-notes-spaced-rep-v3-FINAL`。

---

## 7. 使用 GitHub Actions 自动化部署 {#automation}

如果你使用 Quartz，部署工作流程已包含在内。但如果你使用 Hugo 或自定义设置，这里有一个完整、可复制粘贴的 GitHub Actions 工作流程：

```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout @v4
        with:
          submodules: true
          fetch-depth: 0

      - name: Setup Hugo
        uses: peaceiris/actions-hugo @docs/archive/xhs_post_02_v3.zip
        with:
          hugo-version: "latest"
          extended: true

      - name: Build site
        run: hugo --minify

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages @v4
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

**工作原理：** 每次你将提交推送到 `main` 分支——无论是新笔记、编辑还是配置更改——GitHub 都会启动一个新的 Ubuntu 容器，安装 Hugo，构建你的网站，并将输出部署到 `gh-pages` 分支。你的网站会在推送后 60-90 秒内更新。

要从你的日常 Obsidian 工作流程中触发此操作而无需接触终端：使用 [Obsidian Git 插件](URL_PLACEHOLDER_8)。将其配置为按计划（每 15 分钟或 Obsidian 关闭时）自动提交和推送。你在 Frontmatter 中标记为 `draft: false` 的笔记将自动上线。

对于需要更多计算或自定义服务器逻辑的高级设置，请考虑 [DigitalOcean App Platform](URL_PLACEHOLDER_9)——它们的基本层支持静态网站，并比 GitHub Pages 让你对构建环境有更多控制。

---

## 8. 哪种方法适合你？最终比较 {#final-comparison}

| 因素 | Obsidian Publish | Quartz + GitHub Pages | Hugo + GitHub Pages | Astro + Netlify |
|---|---|---|---|---|
| **每月成本** | $8–$16 | 免费 | 免费 | 免费 |
| **设置时间** | 10 分钟 | 45–60 分钟 | 3–6 小时 | 4–8 小时 |
| **技术技能** | 无 | 基本 Git | 中级 | 中级–高级 |
| **Wikilink 支持** | 原生 | 原生 | 需要插件 | 需要插件 |
| **图谱视图** | 是 | 是 | 否（主题不同） | 否 |
| **自定义程度** | 低（仅 CSS） | 中等 | 高 | 非常高 |
| **SEO 控制** | 基本 | 良好 | 优秀 | 优秀 |
| **构建速度** | 即时 | 快速 | 最快 | 快速 |
| **供应商锁定** | 是 | 否 | 否 | 否 |

### 基于角色的决策框架

**初学者**——你使用 Obsidian 已经 3 个月，想开始分享笔记但从未使用过 Git。**使用 Obsidian Publish。** 每月支付 $8，花时间学习你想发布什么以及如何发布，然后当你不再满足于它时，迁移到 Quartz。

**修补匠**——你知道 Git 是什么，你以前编辑过配置文件，并且免费对你很重要。**使用 Quartz。** 它专为你的工作流程而设计，文档可靠，社区活跃。你今天就可以上线。

**专业人士**——你想要一个可以发展成为完整产品的网站：时事通讯集成、自定义页面类型、快速搜索、独特设计。**在 [Netlify](URL_PLACE_PLACHOLDER_10) 上使用 Astro 或在 [Vercel](URL_PLACEHOLDER_11) 上使用 Hugo。** 前期工作量更大，但你不会遇到瓶颈。

---

## 结论 {#conclusion}

发布你的 Obsidian 笔记不是一个复杂的问题——它是一个决策问题。所有工具都有效。问题是你在优化什么。

如果你想**今天**就上线，没有任何麻烦，那就掏钱使用 [Obsidian Publish](URL_PLACEHOLDER_12)。如果你想要**免费、自动且以所有权为先**，那就 Fork Quartz，花一个小时设置，然后推送你的第一次提交。如果你想要一个可以发展成为真正自定义的网站，那就从 [Netlify 上的 Astro](URL_PLACEHOLDER_13) 开始，并投入时间学习工具。

最糟糕的决定是等到你的笔记“足够好”。按照这个标准，它们永远不会足够好。选择一种方法，本周上线，并在公共场合迭代。

准备好购买你的域名并正式上线了吗？[在 Namecheap 上以不到 $10 的价格购买一个 .com 域名](URL_PLACEHOLDER_14)，并立即将其指向你的新网站。

---

*披露：本文包含联盟链接。如果您通过它们购买，我们可能会赚取佣金，而您无需支付额外费用。*

---

## 常见问题

### 发布时可以保留某些笔记私有吗？

是的，所有方法都可以。Obsidian Publish 只发布你明确选择的笔记。对于 SSG，在 Frontmatter 中使用 `draft: true`，将私人笔记放在一个忽略的文件夹中（在你的 SSG 配置或 `.gitignore` 中定义），或者在你的 Vault 中维护一个单独的“public”子文件夹。

### 我的 Wikilinks 在发布时会断裂吗？

除非你处理转换，否则会。Quartz 自动转换它们。对于 Hugo，使用 `hugo-obsidian` CLI 工具作为预处理步骤。对于 Astro，安装 `remark-wiki-link`。对于 Jekyll，使用 `jekyll-wikilinks` gem。在上线之前运行本地构建并审核所有链接。

### 如何处理我的 Vault 中的图片和附件？

将你的附件文件夹复制到你的 SSG 的内容或静态目录中。在 Quartz 中，将图片放在 `/content` 中，与你的笔记一起。如果你的文件夹结构发生变化，请更新 Frontmatter 或笔记正文中的任何图片路径。Obsidian Publish 自动处理附件。

### 如果我只有 20 条笔记，Obsidian Publish 值得付费吗？

可能值得，在前六个月。在你弄清楚发布工作流程时，节省的摩擦成本值得每月 $8。一旦你有了持续的习惯和更多内容，再评估 SSG 迁移。

### 以后如何从 Obsidian Publish 迁移到 Quartz？

你的笔记已经采用 Markdown 格式——最难的部分已经完成。将你的 Vault 的 Markdown 文件导出或复制到 Quartz 的 `/content` 目录中，运行构建，并检查是否有断裂的链接。主要调整是更新你的 Frontmatter 中任何 Obsidian Publish 特定的设置，并配置你的新自定义域名 DNS。

## 相关阅读

- [什么是 Obsidian Canvas？你的 Vault 中的无限白板](/zh-cn/posts/what-is-the-obsidian-canvas-plugin/)
- [什么是 Excalidraw 以及为什么要在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [为什么要在 2024 年在 Obsidian 中跟踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
---