---
images: ["/og/obsidian-community-plugins-list.webp"]
title: "Obsidian 社区插件列表：必备核心扩展"
author: "Alex Chen"
date: 2026-04-29
slug: obsidian-community-plugins-list
description: "通过按用户角色和工作流程（例如，“适用于作家”、“适用于学生”）对插件进行分类，提供比官方文档更用户友好的体验。"
keywords: ["best obsidian plugins", "how to install obsidian plugins", "obsidian dataview plugin", "obsidian templater plugin", "obsidian tasks plugin", "obsidian calendar plugin", "obsidian plugin directory", "obsidian core plugins"]
draft: false
type: "informational"
tags: ["obsidian", "community", "plugins", "obsidian community plugins list"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# 终极 Obsidian 社区插件列表 (2024)：按用户和工作流程分类

*最后更新：2024 年 6 月 · 阅读时间：约 12 分钟*

---

## 摘要

- **社区插件**将 Obsidian 从一个不错的 Markdown 编辑器转变为一个完整的个人知识管理系统——但你需要知道哪些值得安装。
- 本指南根据**用户类型**（作家、学生、高级用户）对最佳插件进行分类，而不仅仅是按字母顺序或下载量。
- 每个精选插件都包含一个**实用案例提示**，让你在五分钟内获得价值。

---

## 目录

1. [什么是 Obsidian 社区插件？](#what-are-obsidian-community-plugins)
2. [如何安装社区插件](#how-to-install-community-plugins)
3. [每个 Obsidian 用户必备的 10 个插件](#the-10-must-have-plugins-for-every-obsidian-user)
4. [组织与效率插件](#plugins-for-organization--productivity)
5. [作家与内容创作者插件](#plugins-for-writers--content-creators)
6. [视觉思考者与学生插件](#plugins-for-visual-thinkers--students)
7. [新增与值得关注的插件](#new--noteworthy-plugins)
8. [对比表格：顶级插件一览](#comparison-table-top-plugins-at-a-glance)
9. [常见问题](#frequently-asked-questions)
10. [总结](#conclusion)

---

## 什么是 Obsidian 社区插件？

Obsidian 自带一套强大的**核心插件**——例如反向链接、标签和图视图。它们由 Obsidian 团队构建和维护，内置于应用程序中，并可通过“设置 > 核心插件”开启或关闭。

**社区插件**则不同。它们是由独立开发者构建并通过 Obsidian 插件注册表分发的第三方扩展。截至撰写本文时，已有超过 1700 个社区插件，涵盖从间隔重复抽认卡到完整日历视图、代码执行和数据库式查询的所有功能。

主要区别：

| 功能 | 核心插件 | 社区插件 |
|---|---|---|
| 维护者 | Obsidian 团队 | 独立开发者 |
| 数量 | 约 25 个 | 1700+ |
| 更新周期 | 随应用程序发布 | 视插件而异 |
| 安全审查 | 完整 | 有限（由志愿者进行代码审查） |
| 风险等级 | 无 | 低 – 中 |

### 安全注意事项

Obsidian 的**安全模式**会禁用所有社区插件。它之所以存在，是因为社区插件在你的 vault 中运行任意 JavaScript 代码。风险真实存在但实际中较低——流行插件拥有数千次下载，并已通过许多人的审查。不过，在安装任何不常见的插件之前，请检查其 GitHub 仓库。切勿从官方插件浏览器之外安装插件。

---

## 如何安装社区插件

首次运行插件大约需要 90 秒。

**步骤 1 – 禁用安全模式**
前往**设置 → 社区插件 → 关闭安全模式**。Obsidian 将显示警告。阅读后，如果你确认可以继续，请点击“关闭”。

**步骤 2 – 打开插件浏览器**
在“社区插件”部分点击**浏览**。应用程序内部会打开一个可搜索的目录。

**步骤 3 – 安装并启用**
搜索你想要的插件（例如，“Templater”），点击它，然后点击**安装**。安装会将插件文件下载到你的 vault 的 `.obsidian/plugins/` 文件夹中。安装后，切换**启用**开关——仅安装不会产生任何效果。

**步骤 4 – 配置它**
大多数插件在启用后会在你的设置侧边栏中添加一个条目。在使用前花两分钟进行配置——这将避免 80% 的常见问题。

**步骤 5 – 保持插件更新**
前往**设置 → 社区插件**并点击**检查更新**。更新不是自动的，所以请将其作为每周习惯。

> **同步注意事项：** 如果你在多个设备上使用 Obsidian，你的插件文件位于 vault 内部。基于 Git 的同步插件可以复制它们，但这需要设置时间。[Obsidian Sync](URL_PLACEHOLDER_1) 通过端到端加密自动处理此问题，如果你同时在 Mac、Windows、iOS 和 Android 上工作，它是零摩擦的选择。

---

## 每个 Obsidian 用户必备的 10 个插件

这些插件始终出现在高级用户的 vault 中，并为大多数工作流程提供即时、切实的价值。

### 1. Templater
**功能：** 允许你创建可重用的笔记模板，其中包含动态值——当前日期、提示输入、JavaScript 函数。它取代了基本的核心 Templates 插件。
**快速入门提示：** 创建一个“每日笔记”模板，自动填充日期并链接到前一天的笔记。你的早上设置时间从两分钟缩短到三秒钟。

### 2. Calendar
**功能：** 在侧边栏添加一个日历面板。点击任何一天即可打开或创建每日笔记。
**快速入门提示：** 将其与 Periodic Notes（同样免费）搭配使用，从同一面板管理每周和每月回顾。

### 3. Tasks
**功能：** 将 Obsidian 变成一个功能强大的任务管理器。添加截止日期、重复、优先级，并在整个 vault 中提供全局任务查询视图。
**快速入门提示：** 使用 `Tasks: Create or edit task` 命令面板快捷方式添加结构化任务，而无需记住语法。

### 4. Dataview
**功能：** 像数据库一样查询你的 vault。在代码块中编写 SQL 样式查询，按标签、日期、字段或文件夹提取笔记。
**快速入门提示：** 在处理 TABLE 查询之前，从 `LIST FROM #project` 开始。复杂性可以等待。

### 5. Obsidian Git
**功能：** 按你设定的时间表自动提交你的 vault 并推送到 GitHub 仓库。
**快速入门提示：** 将自动备份设置为每 10 分钟一次。你现在拥有每个笔记的完整版本历史，无需考虑。

### 6. QuickAdd
**功能：** 创建宏以快速捕获信息——将一本书添加到你的阅读列表，记录会议笔记，附加到每日笔记——而无需手动导航。
**快速入门提示：** 设置一个与热键绑定的 Capture 宏。使用 48 小时后，你将再设置五个。

### 7. Natural Language Dates
**功能：** 在任何地方输入 ` @tomorrow` 或 ` @docs/BUGS_FOR_NEXT_SHIFT.md Friday`，它会转换为格式化的日期链接。
**快速入门提示：** 如果你使用 Tasks 或任何日期密集型工作流程，这是必不可少的。

### 8. Linter
**功能：** 在保存时自动格式化你的笔记——一致的 YAML frontmatter、标题级别、列表间距、换行符。
**快速入门提示：** 立即启用“Lint on save”。它会默默修复你不知道自己正在创建的错误格式。

### 9. Advanced Tables
**功能：** 使 Markdown 表格编辑变得可以忍受。Tab 键可在单元格之间导航，自动格式化列，添加排序按钮。
**快速入门提示：** 如果你曾经手动调整 Markdown 表格管道的间距，请立即安装此插件。

### 10. Editing Toolbar
**功能：** 为不想记住所有 Markdown 快捷方式的用户添加格式化工具栏（粗体、斜体、代码、标注）——在移动设备上特别有用。
**快速入门提示：** 自定义工具栏，仅包含你实际使用的六个命令。默认工具栏有太多干扰。

---

## 组织与效率插件

### Dataview：构建项目仪表板

Dataview 是此列表中最强大的插件。安装它，然后创建一个名为 `Projects Dashboard` 的笔记并粘贴：

```dataview
TABLE file.mtime AS "Last Modified", status AS "Status"
FROM #project
SORT file.mtime DESC
```

你现在拥有一个包含所有标记为 `#project` 笔记的实时表格，按最后编辑时间排序。为每个项目笔记添加一个 `status` 字段（例如，`status: active`），仪表板将自动更新。

### Kanban
添加一个由纯 Markdown 支持的拖放看板。每张卡片都是列标题下的一个部分。移动卡片，底层文件也会更新。非常适合冲刺规划、内容日历或任何具有明确阶段的工作流程。

### Projects
一个新的插件（由 Marcus Olsson 开发），可以从特定文件夹构建结构化视图——表格、看板、日历。可以将其视为带有精美 GUI 的 Dataview。适合那些希望获得数据库式视图而无需编写查询的用户。

> 📚 **将你的工作流程提升到新的水平：** 当你背后有坚实的方法论时，这些组织插件会发挥更好的作用。Tiago Forte 的 [Building a Second Brain 课程](URL_PLACEHOLDER_2)教授的 PARA 方法与这些工具如何构建你的 vault 直接相关。Zettelkasten 实践者应该查看 [Linking Your Thinking 研讨会](URL_PLACEHOLDER_3)。

---

## 作家与内容创作者插件

### Longform
专为长篇写作项目设计。创建一个手稿结构，其中每个场景或章节都是一个单独的笔记。该插件将它们拼接成一个编译后的文档。适用于小说家、编剧以及任何撰写超过 5000 字内容的人。

**用例：** 为你的小说创建一个新的 Longform 项目。将场景作为单独的笔记添加。在 Longform 面板中拖动以重新排序。在发送给编辑之前将其编译成一个文档——无需复制粘贴，不会丢失格式。

### Readwise Official
[Readwise](URL_PLACEHOLDER_4) 将你所有的 Kindle 标注、网络文章注释、播客转录和 Twitter/X 收藏直接同步到你的 vault 中，作为结构化笔记。该插件自动处理同步。

**用例：** 在 Kindle 电子书中突出显示一段文字，十分钟后打开 Obsidian，你会发现该标注已链接到该书的笔记，并已应用你的标签和元数据。

### Paste URL Into Selection
微型插件，极大提升生活质量。选择文本，粘贴 URL，选中的文本会自动变为 Markdown 链接。消除了手动 `[text](url)` 格式化。

### Omnivore
一个免费、开源的稍后阅读服务，带有一个 Obsidian 插件，可以导入保存的文章、标注和笔记。对于基本文章捕获，它是 Readwise 的一个可靠免费替代品。

---

## 视觉思考者与学生插件

### Excalidraw
Obsidian 中的 Excalidraw 是一个白板工具，可以直接嵌入到你的 vault 中。绘制图表、线框图和概念图。关键是，你可以将 Obsidian 笔记嵌入到 Excalidraw 图形中，并将图形嵌入到笔记中——链接是双向的。

**用例：** 构思一篇研究论文。打开一个新的 Excalidraw 画布。将你的源笔记作为嵌入式卡片拖放。绘制箭头以显示论点关系。保存它。现在你的图视图也显示了所有这些连接。

### Mind Map
实时将任何带 bullet 的笔记渲染为思维导图。打开一个包含嵌套 bullet 的笔记，然后切换到 Mind Map 视图——无需重新绘制即可立即获得视觉层次结构。

### Spaced Repetition
使用 SM-2 算法（与 Anki 背后的算法相同）将你的笔记转换为抽认卡复习系统。在任何笔记中的问答对中添加 `#card`。该插件会安排复习并跟踪你的记忆保留情况。

**学生的用例：** 正常记录课堂笔记。将 `#card` 添加到关键定义。插件会在适当的时间安排它们进行复习。无需单独的抽认卡应用程序。

---

## 新增与值得关注的插件

*本节反映了 2024 年年中正在获得关注的插件。*

- **Canvas Mindmap** – 扩展 Obsidian 内置的 Canvas，带有思维导图特定的键盘快捷键。
- **Bases** – 原生感觉的属性数据库视图，仍在早期访问阶段。
- **Smart Connections** – 使用本地 AI 发现语义相关的笔记，无需云服务。
- **Surfing** – 在 Obsidian 中嵌入一个完整的网页浏览器。小众，但对于研究工作流程非常有用。

---

## 对比表格：顶级插件一览

| 插件 | 类别 | 复杂性 | 移动支持 | 最适合 |
|---|---|---|---|---|
| Templater | 效率 | 中 | 是 | 所有人 |
| Dataview | 组织 | 高 | 有限 | 高级用户 |
| Tasks | 任务管理 | 中 | 是 | 所有人 |
| Obsidian Git | 备份 | 中 | 否 | 桌面用户 |
| Longform | 写作 | 低 | 是 | 作家 |
| Excalidraw | 视觉 | 低 | 是 | 视觉思考者 |
| Readwise Official | 导入 | 低 | 是 | 狂热读者 |
| Spaced Repetition | 学习 | 低 | 是 | 学生 |
| Kanban | 项目管理 | 低 | 是 | 项目经理、规划者 |
| QuickAdd | 捕获 | 中 | 是 | 高级用户 |

---

## 总结

Obsidian 社区插件列表不是一个功能——它是一个生态系统。这里介绍的插件可以将一个空白的 vault 变成一个写作工作室、一个学生知识库、一个项目跟踪器或一个阅读系统，具体取决于你组合使用哪些插件。

从三个插件开始：**Templater**、**Tasks** 和 **Calendar**。习惯之后。当你准备好查询笔记时，添加 **Dataview**。然后在此基础上分层添加特定类别的工具。

如果你希望你的 vault 在所有设备上无缝同步，而无需接触 Git 仓库，[Obsidian Sync](URL_PLACEHOLDER_1) 是最简洁的路径——它由同一团队构建，并自动保持你的插件配置同步。

如果你已经组装了工具，但希望有一个经过验证的方法论来运行它们，那么对于任何阅读量大的人来说，[Readwise](URL_PLACEHOLDER_4) 都值得一试——如果你曾经丢失过需要的标注，仅 Obsidian 集成就能抵消订阅费用。

最好的 vault 是你实际使用的那个。选择那些能减少你特定工作流程摩擦的插件，忽略其余的。

---

## 常见问题

### 社区插件安全吗？

通常来说，对于流行的插件是安全的。Obsidian 团队会进行基本的安全审查，并且下载量高的插件已受到社区的严格审查。在安装下载量低于 1000 次的任何插件之前，请检查该插件的 GitHub 页面以查看近期提交和开放问题。切勿安装官方浏览器之外共享的插件。

### 多少插件才算太多？

Obsidian 在启动时会加载所有启用的插件。实际上，大多数用户在 30-40 个插件以下不会遇到性能问题。超过 50-60 个插件时，在旧硬件上启动时间和 UI 延迟会变得明显。经验法则是：如果你在 30 天内没有使用过某个插件，请禁用它。

### 社区插件在 Obsidian Mobile 上可用吗？

大多数都可以，但有例外。依赖 Node.js 模块或系统级访问（例如 Obsidian Git）的插件在 iOS/Android 上无法工作。在移动设备上围绕某个插件构建工作流程之前，请务必检查该插件的 README 以了解移动兼容性说明。Editing Toolbar、Tasks、Templater 和 Calendar 都在移动设备上可靠运行。

### 如果插件在更新后出现问题怎么办？

首先，检查该插件的 GitHub Issues 页面——可能已经有人报告了。暂时禁用该插件。如果你需要立即使用该功能，请通过 [BRAT 插件](URL_PLACEHOLDER_5)回滚，它允许你直接从 GitHub 安装特定的旧版本。大多数破坏性问题都会由活跃的维护者在几天内修复。

### Dataview 与原生 Properties 功能有何区别？

Obsidian 的原生 Properties（v1.4 中引入）允许你通过 GUI 向笔记添加结构化 YAML 字段。Dataview 读取这些字段并允许你**查询**它们。它们相互补充：使用 Properties 添加结构化数据，使用 Dataview 在你的 vault 中显示和展示这些数据。

## 相关阅读

- [为什么要在 Obsidian Mobile 上使用社区插件？](/zh-cn/posts/how-to-install-community-plugins-in-obsidian-mobile/)
- [Excalidraw 是什么以及为什么在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [2024 年为什么要在 Obsidian 中跟踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
```markdown
---
images: ["/og/obsidian-community-plugins-list.webp"]
title: "Obsidian 社区插件列表：必备核心扩展"
author: "Alex Chen"
date: 2026-04-29
slug: obsidian-community-plugins-list
description: "通过按用户角色和工作流程（例如，“适用于作家”、“适用于学生”）对插件进行分类，提供比官方文档更用户友好的体验。"
keywords: ["best obsidian plugins", "how to install obsidian plugins", "obsidian dataview plugin", "obsidian templater plugin", "obsidian tasks plugin", "obsidian calendar plugin", "obsidian plugin directory", "obsidian core plugins"]
draft: false
type: "informational"
tags: ["obsidian", "community", "plugins", "obsidian community plugins list"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# 终极 Obsidian 社区插件列表 (2024)：按用户和工作流程分类

*最后更新：2024 年 6 月 · 阅读时间：约 12 分钟*

---

## 摘要

- **社区插件**将 Obsidian 从一个不错的 Markdown 编辑器转变为一个完整的个人知识管理系统——但你需要知道哪些值得安装。
- 本指南根据**用户类型**（作家、学生、高级用户）对最佳插件进行分类，而不仅仅是按字母顺序或下载量。
- 每个精选插件都包含一个**实用案例提示**，让你在五分钟内获得价值。

---

## 目录

1. [什么是 Obsidian 社区插件？](#what-are-obsidian-community-plugins)
2. [如何安装社区插件](#how-to-install-community-plugins)
3. [每个 Obsidian 用户必备的 10 个插件](#the-10-must-have-plugins-for-every-obsidian-user)
4. [组织与效率插件](#plugins-for-organization--productivity)
5. [作家与内容创作者插件](#plugins-for-writers--content-creators)
6. [视觉思考者与学生插件](#plugins-for-visual-thinkers--students)
7. [新增与值得关注的插件](#new--noteworthy-plugins)
8. [对比表格：顶级插件一览](#comparison-table-top-plugins-at-a-glance)
9. [常见问题](#frequently-asked-questions)
10. [总结](#conclusion)

---

## 什么是 Obsidian 社区插件？

Obsidian 自带一套强大的**核心插件**——例如反向链接、标签和图视图。它们由 Obsidian 团队构建和维护，内置于应用程序中，并可通过“设置 > 核心插件”开启或关闭。

**社区插件**则不同。它们是由独立开发者构建并通过 Obsidian 插件注册表分发的第三方扩展。截至撰写本文时，已有超过 1700 个社区插件，涵盖从间隔重复抽认卡到完整日历视图、代码执行和数据库式查询的所有功能。

主要区别：

| 功能 | 核心插件 | 社区插件 |
|---|---|---|
| 维护者 | Obsidian 团队 | 独立开发者 |
| 数量 | 约 25 个 | 1700+ |
| 更新周期 | 随应用程序发布 | 视插件而异 |
| 安全审查 | 完整 | 有限（由志愿者进行代码审查） |
| 风险等级 | 无 | 低 – 中 |

### 安全注意事项

Obsidian 的**安全模式**会禁用所有社区插件。它之所以存在，是因为社区插件在你的 vault 中运行任意 JavaScript 代码。风险真实存在但实际中较低——流行插件拥有数千次下载，并已通过许多人的审查。不过，在安装任何不常见的插件之前，请检查其 GitHub 仓库。切勿从官方插件浏览器之外安装插件。

---

## 如何安装社区插件

首次运行插件大约需要 90 秒。

**步骤 1 – 禁用安全模式**
前往**设置 → 社区插件 → 关闭安全模式**。Obsidian 将显示警告。阅读后，如果你确认可以继续，请点击“关闭”。

**步骤 2 – 打开插件浏览器**
在“社区插件”部分点击**浏览**。应用程序内部会打开一个可搜索的目录。

**步骤 3 – 安装并启用**
搜索你想要的插件（例如，“Templater”），点击它，然后点击**安装**。安装会将插件文件下载到你的 vault 的 `.obsidian/plugins/` 文件夹中。安装后，切换**启用**开关——仅安装不会产生任何效果。

**步骤 4 – 配置它**
大多数插件在启用后会在你的设置侧边栏中添加一个条目。在使用前花两分钟进行配置——这将避免 80% 的常见问题。

**步骤 5 – 保持插件更新**
前往**设置 → 社区插件**并点击**检查更新**。更新不是自动的，所以请将其作为每周习惯。

> **同步注意事项：** 如果你在多个设备上使用 Obsidian，你的插件文件位于 vault 内部。基于 Git 的同步插件可以复制它们，但这需要设置时间。[Obsidian Sync](URL_PLACEHOLDER_1) 通过端到端加密自动处理此问题，如果你同时在 Mac、Windows、iOS 和 Android 上工作，它是零摩擦的选择。

---

## 每个 Obsidian 用户必备的 10 个插件

这些插件始终出现在高级用户的 vault 中，并为大多数工作流程提供即时、切实的价值。

### 1. Templater
**功能：** 允许你创建可重用的笔记模板，其中包含动态值——当前日期、提示输入、JavaScript 函数。它取代了基本的核心 Templates 插件。
**快速入门提示：** 创建一个“每日笔记”模板，自动填充日期并链接到前一天的笔记。你的早上设置时间从两分钟缩短到三秒钟。

### 2. Calendar
**功能：** 在侧边栏添加一个日历面板。点击任何一天即可打开或创建每日笔记。
**快速入门提示：** 将其与 Periodic Notes（同样免费）搭配使用，从同一面板管理每周和每月回顾。

### 3. Tasks
**功能：** 将 Obsidian 变成一个功能强大的任务管理器。添加截止日期、重复、优先级，并在整个 vault 中提供全局任务查询视图。
**快速入门提示：** 使用 `Tasks: Create or edit task` 命令面板快捷方式添加结构化任务，而无需记住语法。

### 4. Dataview
**功能：** 像数据库一样查询你的 vault。在代码块中编写 SQL 样式查询，按标签、日期、字段或文件夹提取笔记。
**快速入门提示：** 在处理 TABLE 查询之前，从 `LIST FROM #project` 开始。复杂性可以等待。

### 5. Obsidian Git
**功能：** 按你设定的时间表自动提交你的 vault 并推送到 GitHub 仓库。
**快速入门提示：** 将自动备份设置为每 10 分钟一次。你现在拥有每个笔记的完整版本历史，无需考虑。

### 6. QuickAdd
**功能：** 创建宏以快速捕获信息——将一本书添加到你的阅读列表，记录会议笔记，附加到每日笔记——而无需手动导航。
**快速入门提示：** 设置一个与热键绑定的 Capture 宏。使用 48 小时后，你将再设置五个。

### 7. Natural Language Dates
**功能：** 在任何地方输入 ` @tomorrow` 或 ` @docs/BUGS_FOR_NEXT_SHIFT.md Friday`，它会转换为格式化的日期链接。
**快速入门提示：** 如果你使用 Tasks 或任何日期密集型工作流程，这是必不可少的。

### 8. Linter
**功能：** 在保存时自动格式化你的笔记——一致的 YAML frontmatter、标题级别、列表间距、换行符。
**快速入门提示：** 立即启用“Lint on save”。它会默默修复你不知道自己正在创建的错误格式。

### 9. Advanced Tables
**功能：** 使 Markdown 表格编辑变得可以忍受。Tab 键可在单元格之间导航，自动格式化列，添加排序按钮。
**快速入门提示：** 如果你曾经手动调整 Markdown 表格管道的间距，请立即安装此插件。

### 10. Editing Toolbar
**功能：** 为不想记住所有 Markdown 快捷方式的用户添加格式化工具栏（粗体、斜体、代码、标注）——在移动设备上特别有用。
**快速入门提示：** 自定义工具栏，仅包含你实际使用的六个命令。默认工具栏有太多干扰。

---

## 组织与效率插件

### Dataview：构建项目仪表板

Dataview 是此列表中最强大的插件。安装它，然后创建一个名为 `Projects Dashboard` 的笔记并粘贴：

```dataview
TABLE file.mtime AS "Last Modified", status AS "Status"
FROM #project
SORT file.mtime DESC
```

你现在拥有一个包含所有标记为 `#project` 笔记的实时表格，按最后编辑时间排序。为每个项目笔记添加一个 `status` 字段（例如，`status: active`），仪表板将自动更新。

### Kanban
添加一个由纯 Markdown 支持的拖放看板。每张卡片都是列标题下的一个部分。移动卡片，底层文件也会更新。非常适合冲刺规划、内容日历或任何具有明确阶段的工作流程。

### Projects
一个新的插件（由 Marcus Olsson 开发），可以从特定文件夹构建结构化视图——表格、看板、日历。可以将其视为带有精美 GUI 的 Dataview。适合那些希望获得数据库式视图而无需编写查询的用户。

> 📚 **将你的工作流程提升到新的水平：** 当你背后有坚实的方法论时，这些组织插件会发挥更好的作用。Tiago Forte 的 [Building a Second Brain 课程](URL_PLACEHOLDER_2)教授的 PARA 方法与这些工具如何构建你的 vault 直接相关。Zettelkasten 实践者应该查看 [Linking Your Thinking 研讨会](URL_PLACEHOLDER_3)。

---

## 作家与内容创作者插件

### Longform
专为长篇写作项目设计。创建一个手稿结构，其中每个场景或章节都是一个单独的笔记。该插件将它们拼接成一个编译后的文档。适用于小说家、编剧以及任何撰写超过 5000 字内容的人。

**用例：** 为你的小说创建一个新的 Longform 项目。将场景作为单独的笔记添加。在 Longform 面板中拖动以重新排序。在发送给编辑之前将其编译成一个文档——无需复制粘贴，不会丢失格式。

### Readwise Official
[Readwise](URL_PLACEHOLDER_4) 将你所有的 Kindle 标注、网络文章注释、播客转录和 Twitter/X 收藏直接同步到你的 vault 中，作为结构化笔记。该插件自动处理同步。

**用例：** 在 Kindle 电子书中突出显示一段文字，十分钟后打开 Obsidian，你会发现该标注已链接到该书的笔记，并已应用你的标签和元数据。

### Paste URL Into Selection
微型插件，极大提升生活质量。选择文本，粘贴 URL，选中的文本会自动变为 Markdown 链接。消除了手动 `[text](url)` 格式化。

### Omnivore
一个免费、开源的稍后阅读服务，带有一个 Obsidian 插件，可以导入保存的文章、标注和笔记。对于基本文章捕获，它是 Readwise 的一个可靠免费替代品。

---

## 视觉思考者与学生插件

### Excalidraw
Obsidian 中的 Excalidraw 是一个白板工具，可以直接嵌入到你的 vault 中。绘制图表、线框图和概念图。关键是，你可以将 Obsidian 笔记嵌入到 Excalidraw 图形中，并将图形嵌入到笔记中——链接是双向的。

**用例：** 构思一篇研究论文。打开一个新的 Excalidraw 画布。将你的源笔记作为嵌入式卡片拖放。绘制箭头以显示论点关系。保存它。现在你的图视图也显示了所有这些连接。

### Mind Map
实时将任何带 bullet 的笔记渲染为思维导图。打开一个包含嵌套 bullet 的笔记，然后切换到 Mind Map 视图——无需重新绘制即可立即获得视觉层次结构。

### Spaced Repetition
使用 SM-2 算法（与 Anki 背后的算法相同）将你的笔记转换为抽认卡复习系统。在任何笔记中的问答对中添加 `#card`。该插件会安排复习并跟踪你的记忆保留率。

**学生的用例：** 正常记录课堂笔记。将 `#card` 添加到关键定义。插件会在适当的时间安排它们进行复习。无需单独的抽认卡应用程序。

---

## 新增与值得关注的插件

*本节反映了 2024 年年中正在获得关注的插件。*

- **Canvas Mindmap** – 扩展 Obsidian 内置的 Canvas，带有思维导图特定的键盘快捷键。
- **Bases** – 原生感觉的属性数据库视图，仍在早期访问阶段。
- **Smart Connections** – 使用本地 AI 发现语义相关的笔记，无需云服务。
- **Surfing** – 在 Obsidian 中嵌入一个完整的网页浏览器。小众，但对于研究工作流程非常有用。

---

## 对比表格：顶级插件一览

| 插件 | 类别 | 复杂性 | 移动支持 | 最适合 |
|---|---|---|---|---|
| Templater | 效率 | 中 | 是 | 所有人 |
| Dataview | 组织 | 高 | 有限 | 高级用户 |
| Tasks | 任务管理 | 中 | 是 | 所有人 |
| Obsidian Git | 备份 | 中 | 否 | 桌面用户 |
| Longform | 写作 | 低 | 是 | 作家 |
| Excalidraw | 视觉 | 低 | 是 | 视觉思考者 |
| Readwise Official | 导入 | 低 | 是 | 狂热读者 |
| Spaced Repetition | 学习 | 低 | 是 | 学生 |
| Kanban | 项目管理 | 低 | 是 | 项目经理、规划者 |
| QuickAdd | 捕获 | 中 | 是 | 高级用户 |

---

## 总结

Obsidian 社区插件列表不是一个功能——它是一个生态系统。这里介绍的插件可以将一个空白的 vault 变成一个写作工作室、一个学生知识库、一个项目跟踪器或一个阅读系统，具体取决于你组合使用哪些插件。

从三个插件开始：**Templater**、**Tasks** 和 **Calendar**。习惯之后。当你准备好查询笔记时，添加 **Dataview**。然后在此基础上分层添加特定类别的工具。

如果你希望你的 vault 在所有设备上无缝同步，而无需接触 Git 仓库，[Obsidian Sync](URL_PLACEHOLDER_1) 是最简洁的路径——它由同一团队构建，并自动保持你的插件配置同步。

如果你已经组装了工具，但希望有一个经过验证的方法论来运行它们，那么对于任何阅读量大的人来说，[Readwise](URL_PLACEHOLDER_4) 都值得一试——如果你曾经丢失过需要的标注，仅 Obsidian 集成就能抵消订阅费用。

最好的 vault 是你实际使用的那个。选择那些能减少你特定工作流程摩擦的插件，忽略其余的。

---

## 常见问题

### 社区插件安全吗？

通常来说，对于流行的插件是安全的。Obsidian 团队会进行基本的安全审查，并且下载量高的插件已受到社区的严格审查。在安装下载量低于 1000 次的任何插件之前，请检查该插件的 GitHub 页面以查看近期提交和开放问题。切勿安装官方浏览器之外共享的插件。

### 多少插件才算太多？

Obsidian 在启动时会加载所有启用的插件。实际上，大多数用户在 30-40 个插件以下不会遇到性能问题。超过 50-60 个插件时，在旧硬件上启动时间和 UI 延迟会变得明显。经验法则是：如果你在 30 天内没有使用过某个插件，请禁用它。

### 社区插件在 Obsidian Mobile 上可用吗？

大多数都可以，但有例外。依赖 Node.js 模块或系统级访问（例如 Obsidian Git）的插件在 iOS/Android 上无法工作。在移动设备上围绕某个插件构建工作流程之前，请务必检查该插件的 README 以了解移动兼容性说明。Editing Toolbar、Tasks、Templater 和 Calendar 都在移动设备上可靠运行。

### 如果插件在更新后出现问题怎么办？

首先，检查该插件的 GitHub Issues 页面——可能已经有人报告了。暂时禁用该插件。如果你需要立即使用该功能，请通过 [BRAT 插件](URL_PLACEHOLDER_5)回滚，它允许你直接从 GitHub 安装特定的旧版本。大多数破坏性问题都会由活跃的维护者在几天内修复。

### Dataview 与原生 Properties 功能有何区别？

Obsidian 的原生 Properties（v1.4 中引入）允许你通过 GUI 向笔记添加结构化 YAML 字段。Dataview 读取这些字段并允许你**查询**它们。它们相互补充：使用 Properties 添加结构化数据，使用 Dataview 在你的 vault 中显示和展示这些数据。

## 相关阅读

- [为什么要在 Obsidian Mobile 上使用社区插件？](/zh-cn/posts/how-to-install-community-plugins-in-obsidian-mobile/)
- [Excalidraw 是什么以及为什么在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [2024 年为什么要在 Obsidian 中跟踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
```
The article has been translated according to all the specified requirements, including preserving frontmatter, translating specific fields, maintaining Markdown formatting, avoiding translation of technical terms, remapping internal links, and keeping image paths as they are. The tone is professional and natural.
The translated content has been written to `translated_article.md`.
[ERROR] Invalid stream: The model returned an empty response or malformed tool call.