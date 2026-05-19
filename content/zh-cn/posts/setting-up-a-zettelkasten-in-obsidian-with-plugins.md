---
images: ["/og/setting-up-a-zettelkasten-in-obsidian-with-plugins.webp"]
title: "Obsidian Zettelkasten：必备插件与设置指南"
date: 2026-04-28
slug: setting-up-a-zettelkasten-in-obsidian-with-plugins
description: "提供一个主观的、'一键式' 的启动库模板，其中包含预配置的插件和设置，让用户能够立即开始使用。"
keywords: ["obsidian zettelkasten guide", "how to build a second brain in obsidian", "obsidian note-taking system", "best plugins for zettelkasten obsidian", "dataview plugin zettelkasten", "templater plugin obsidian setup", "atomic notes obsidian", "linking your thinking obsidian"]
draft: false
author: "Alex Chen"
type: "informational"
tags: ["build", "zettelkasten", "obsidian", "setting up a zettelkasten in obsidian with plugins"]
---

_作为 Amazon 联盟会员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# 在 Obsidian 中使用插件设置 Zettelkasten：分步工作流程指南

---

**TL;DR**

- 在 Obsidian 中搭建一个可用的 Zettelkasten 需要特定的文件夹结构、三个核心社区插件（Templater、QuickAdd、Dataview）以及清晰定义的工作流程——而不仅仅是安装好插件却闲置不用。
- 本指南将从零开始构建系统：库结构 → 模板 → 自动化笔记创建 → 链接 → 动态查询，确保每个部分都有其作用。
- 最终，你将拥有一个摩擦最小的设置，只需按下一个快捷键并输入两秒钟，即可创建新的永久笔记。

---

## 目录

1. [为何在 Obsidian 中构建 Zettelkasten？](#why)
2. [核心插件栈：你的 Zettelkasten 工具包](#stack)
3. [步骤 1：设置你的库基础](#step1)
4. [步骤 2：使用 Templater 配置笔记模板](#step2)
5. [步骤 3：使用 QuickAdd 自动化笔记创建](#step3)
6. [步骤 4：Zettelkasten 工作流程实战](#step4)
7. [进阶：高级技巧和可选插件](#levelup)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 为何在 Obsidian 中构建 Zettelkasten？ {#why}

大多数笔记技巧都关乎*收集*信息。而 Zettelkasten 方法，由社会学家 Niklas Luhmann 开发，他用此方法出版了 70 多本书和 400 篇学术文章，其目的在于通过强制信息之间建立联系来*产生*想法。

使其发挥作用的三个机械规则：

1. **原子化笔记。** 每条笔记只包含一个想法，用你自己的话阐述。没有冗长的书籍摘要。没有堆积文件。
2. **明确的链接。** 每条新笔记至少引用一条现有笔记。链接才是重点，而不是标签或文件夹。
3. **无严格层级。** 网络通过链接而非预定义的文件夹分类法自然形成。

如果你想了解完整的哲学基础，[*How to Take Smart Notes* by Sönke Ahrens](URL_PLACEHOLDER_1) 是权威著作。读一遍，然后回来这里构建系统。

**为什么特别选择 Obsidian？**

- 笔记是本地存储的纯 `.md` 文件。没有厂商锁定。你 2035 年的库仍然可以打开，无需订阅。
- 双向链接和反向链接是第一类功能，而非事后添加。
- 插件生态系统足够庞大，可以自动化每一个重复步骤，而不会让应用程序变得臃肿。
- 图谱视图 (Graph View) 为你提供知识网络的可视化地图——有助于发现孤立笔记和意想不到的集群。

**本指南实际涵盖的内容：** 不是哲学（你可以阅读 Ahrens 的书）。不是表面化的插件列表。相反，你将获得一个具体、主观的工作流程，其中 Templater、QuickAdd 和 Dataview 作为一个相互连接的系统运作，而非三个不相关的功能。

---

## 核心插件栈：你的 Zettelkasten 工具包 {#stack}

在接触配置之前，请了解每个插件的作用以及它*为何*在插件栈中。安装你不了解的插件会导致设置被放弃。

| 插件 | 在系统中的作用 | 为何选择它 |
|---|---|---|
| **Templater** (社区) | 创建带有动态元数据的结构化笔记模板 | 确保每条永久笔记都具有一致的 YAML frontmatter 和自动填充的字段 |
| **QuickAdd** (社区) | 通过快捷键触发基于模板的笔记创建 | 消除了手动创建新笔记的多步操作 |
| **Dataview** (社区) | 像数据库一样查询你的笔记 | 为动态内容地图 (Maps of Content) 提供支持，并自动浮现孤立笔记 |
| **Linter** (社区) | 在保存时强制执行一致的格式 | 保持 YAML frontmatter 整洁，并添加/更新修改时间戳 |
| **Calendar** (社区) | 为每日笔记提供可点击的日历侧边栏 | 使零碎笔记捕获快速且按日期可导航 |
| **Unique Note Creator** (核心) | 生成带有 UID 前缀的文件名 | 为每条笔记提供一个稳定、无冲突的标识符 |

**为什么是这种特定组合？** Templater 处理*结构*，QuickAdd 处理*速度*，Dataview 处理*检索*，Linter 处理*一致性*。每个插件都填补了其他插件留下的空白。没有 Linter 和 Calendar 也可以操作，但对于此处描述的工作流程，Templater、QuickAdd 和 Dataview 是不可或缺的。

---

## 步骤 1：设置你的库基础 {#step1}

### 创建新库

打开 Obsidian → **创建新库**。给它一个永久名称（`ZK` 或 `Knowledge` 都可以）。将其放在你可控的位置——不要放在 Obsidian Sync 稍后也会尝试管理的云同步文件夹中。

### 推荐的文件夹结构

```
📁 ZK/
├── 📁 00 - Inbox/
├── 📁 10 - Fleeting/
├── 📁 20 - Literature/
├── 📁 30 - Permanent/
├── 📁 40 - Maps of Content/
├── 📁 50 - Resources/
└── 📁 _Templates/
```

**每个文件夹的作用：**

- **00 - Inbox:** 未处理的想法、链接、引文。任何内容都可以放在这里。你每天或每周清理它。
- **10 - Fleeting:** 尚未转化为永久笔记的快速笔记。每日笔记 (Daily Notes) 存放于此。
- **20 - Literature:** 每个来源（书籍、论文、文章）一条笔记。包含你处理过的摘录和摘要。
- **30 - Permanent:** 你的实际 Zettelkasten。这里的每条笔记都是原子化的、已链接的，并用你自己的话写成。
- **40 - Maps of Content:** 索引笔记，收集关于某个主题的永久笔记链接。它不是文件夹层级——只是一个精选的链接列表。
- **50 - Resources:** 参考资料（会议模板、项目文件等）。位于 ZK 核心之外。
- **_Templates:** Templater 使用的模板文件。将其放在根目录，便于插件访问。

### 配置核心 Obsidian 设置

前往 **设置 → 核心插件** 并启用：

- **每日笔记 (Daily notes)** — 将位置设置为 `10 - Fleeting`，日期格式为 `YYYY-MM-DD`
- **唯一笔记创建器 (Unique note creator)** — 将前缀格式设置为 `YYYYMMDDHHmm`，默认位置设置为 `00 - Inbox`
- **模板 (Templates)** (核心) — 指向 `_Templates`（你将使用 Templater 覆盖此设置，但仍需启用）
- **反向链接 (Backlinks)** 和 **出站链接 (Outgoing links)** — 启用两者，并设置为在侧边栏中打开

在 **设置 → 文件与链接 (Files & links)** 下：
- 将 **新笔记的默认位置 (Default location for new notes)** 设置为 `00 - Inbox`
- 启用 **重命名文件时自动更新内部链接 (Automatically update internal links)**
- 将 **新链接格式 (New link format)** 设置为 **文件相对路径 (Relative path to file)**

### 安装社区插件

前往 **设置 → 社区插件 → 浏览 (Browse)** 并安装：

1. Templater
2. QuickAdd
3. Dataview
4. Linter
5. Calendar

安装每个插件后，点击 **启用 (Enable)**。

---

## 步骤 2：使用 Templater 配置笔记模板 {#step2}

### 将 Templater 指向你的模板文件夹

**设置 → Templater：**
- 模板文件夹位置 (Template folder location): `_Templates`
- 启用 **在新文件创建时触发 Templater (Trigger Templater on new file creation)**: 开启
- 启用 **自动跳转到光标 (Automatic jump to cursor)**: 开启

### 创建永久笔记模板

在 `_Templates` 中，创建一个名为 `tpl-permanent-note.md` 的新文件。精确粘贴以下内容：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
title: <% tp.file.title %>
aliases: []
tags: []
created: <% tp.date.now("YYYY-MM-DD") %>
modified: <% tp.date.now("YYYY-MM-DD") %>
status: draft
source: ""
---

# <% tp.file.title %>

## The Idea

<!-- State the single idea this note is about. One paragraph. -->

## Why It Matters

<!-- Why does this idea matter to you? What does it connect to? -->

## Links

<!-- [[Related Note A]] | [[Related Note B]] -->

## References

<!-- [Source Title](URL) or Literature Note link -->
```

**每个 YAML 字段的作用：**

- `uid` — 基于时间戳的唯一 ID。允许你之后重命名文件而不会破坏引用。
- `title` — 创建时镜像文件名；对 Dataview 查询很有用。
- `aliases` — Obsidian 搜索时可以使用的别名。
- `status` — `draft` / `developing` / `mature`。跟踪笔记的成熟度。
- `source` — 想法的来源（URL、书名或 `[[Literature Note]]` 链接）。

### 创建文献笔记模板

创建 `_Templates/tpl-literature-note.md`：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
title: <% tp.file.title %>
author: ""
year: 
source-url: ""
tags: [literature]
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

## Bibliographic Info

- **Author:**
- **Year:**
- **URL / ISBN:**

## Key Arguments

1.

## Passages Worth Keeping

>

## My Permanent Notes from This Source

<!-- [[ZK - Note Title]] -->
```

### 创建零碎笔记模板

创建 `_Templates/tpl-fleeting-note.md`：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags: [fleeting]
---

# Fleeting: <% tp.date.now("YYYY-MM-DD HH:mm") %>

<!-- Dump the thought here. Don't edit. Process later. -->

**To process:** [ ]
```

零碎笔记中的复选框是故意的——你可以在之后通过 Dataview 查询所有未处理的零碎笔记。

---

## 步骤 3：使用 QuickAdd 自动化笔记创建 {#step3}

这就是设置的价值所在。你不再需要：新建文件 → 命名 → 应用模板 → 移动到文件夹 → 开始写作，而是只需按一个快捷键，笔记就会出现，已命名、已模板化并可供编辑。

### 为永久笔记配置 QuickAdd

前往 **设置 → QuickAdd**：

1. 在底部文本字段中，输入 `New Permanent Note` 并点击 **添加选项 (Add Choice)**
2. 选择 **模板 (Template)** 作为选项类型
3. 点击新选项旁边的 ⚙️ 齿轮图标

配置模板选项：

| 设置 | 值 |
|---|---|
| **模板路径 (Template Path)** | `_Templates/tpl-permanent-note.md` |
| **文件名格式 (File Name Format)** | `ZK - {{VALUE:Note title?}}` |
| **创建到文件夹 (Create in Folder)** | `30 - Permanent` |
| **打开 (Open)** | 启用 |
| **聚焦新笔记 (Focus new note)** | 启用 |

点击 ⚡ 闪电图标将此选项添加到 QuickAdd 菜单栏按钮。

**触发此操作时会发生什么：** QuickAdd 会提示你“笔记标题？(Note title?)”，你输入四个词，按 Enter 键，然后你就在 `30 - Permanent` 中打开了一个新永久笔记，所有 YAML 都已预填，光标等待输入。

### 为零碎笔记设置 QuickAdd

重复[此过程：

1. 添加一个新选项：`New Fleeting Note`
2. 类型：模板 (Template)
3. 配置：

| 设置 | 值 |
|---|---|
| **模板路径 (Template Path)** | `_Templates/tpl-fleeting-note.md` |
| **文件名格式 (File Name Format)** | `Fleeting - {{DATE:YYYYMMDDHHmm}}` |
| **创建到文件夹 (Create in Folder)** | `10 - Fleeting` |
| **打开 (Open)** | 启用 |

这个不需要你输入标题——它会自动为文件加上时间戳。先捕获，后思考。

### 分配快捷键

前往 **设置 → 快捷键 (Hotkeys)**，搜索 `QuickAdd`：

- `QuickAdd: New Permanent Note` → 分配 `Ctrl+Shift+P` (Windows/Linux) 或 `Cmd+Shift+P` (Mac)
- `QuickAdd: New Fleeting Note` → 分配 `Ctrl+Shift+F` 或 `Cmd+Shift+F`

测试两者。你应该在按下快捷键的两秒内进入一个新笔记。

---

## 步骤 4：Zettelkasten 工作流程实战 {#step4}

有了基础设施，以下是精确的日常工作流程。

### 阶段 1：捕获（收件箱 / 零碎笔记）

你正在阅读一篇文章并产生了一个想法。按下 `Cmd+Shift+F`。输入想法。关闭。完成。不要试图现在处理它——收件箱是一个压力阀，而不是最终目的地。

在你的每日回顾会话（15-20 分钟）中，打开 `10 - Fleeting` 并查看所有未勾选 `[ ]` 的内容。

### 阶段 2：处理为永久笔记

对于每条有价值的零碎笔记：

1. 按下 `Cmd+Shift+P`
2. 输入一个描述性、具体的标题（差的例子：“记忆”；好的例子：“间隔重复通过利用间隔效应发挥作用”）
3. 按 Enter 键
4. 在 **The Idea** 下用你自己的话写下想法
5. 在 **Why It Matters** 下添加你的个人解读
6. 完成后，将零碎笔记的复选框标记为 `[x]`

**原子笔记测试：** 你能用一句话总结这条笔记吗？如果答案是两句话由“和”连接，那么将其拆分为两条笔记。

### 阶段 3：链接新笔记

这就是 Zettelkasten 能否发挥作用的关键。在关闭新的永久笔记之前：

1. 问自己：这条笔记与哪些现有笔记相关联？
2. 在 **Links** 部分输入 `[[` 并搜索你的库
3. 添加至少一个出站链接——即使它很松散（“这与 [[Confirmation Bias]] 相关，因为……”）
4. 打开链接的笔记并在那里也添加一个反向链接引用

几周后，图谱视图 (Graph View)（`Ctrl+G`）将向你展示你是在真正链接还是只是归档。

### 阶段 4：使用 Dataview 展现知识

在 `40 - Maps of Content` 中创建一条名为 `MOC - Unlinked Notes.md` 的笔记：

````markdown
# 孤立的永久笔记

没有出站链接的笔记——它们需要连接。

```dataview
TABLE created, status
FROM "30 - Permanent"
WHERE length(file.outlinks) = 0
SORT created DESC
```
````

再创建一条：`MOC - Draft Notes.md`：

````markdown
# 仍处于草稿状态的笔记

```dataview
TABLE created, file.mtime as "Last Modified"
FROM "30 - Permanent"
WHERE status = "draft"
SORT file.mtime ASC
```
````

以及一个主题特定的 MOC。例如，`MOC - Learning Science.md`：

````markdown
# 学习科学

```dataview
LIST
FROM "30 - Permanent"
WHERE contains(tags, "learning") OR contains(tags, "memory") OR contains(tags, "cognition")
SORT created ASC
```
````

这些 Dataview 查询在你每次打开笔记时都会自动更新。无需手动维护。孤立笔记查询特别有用——一条孤立的永久笔记意味着它尚未完成其任务。

### 配置 Linter 进行自动清理

前往 **设置 → Linter：**

在 **YAML** 下，启用：
- **YAML 时间戳 (YAML Timestamp)** — 在每次保存时添加/更新 `modified` 字段
- **强制 YAML 特殊字符转义 (Force YAML escape on special characters)**

在 **通用 (General)** 下，启用 **保存时 lint (Lint on save)**。

现在，每次你按下 `Ctrl+S` 时，`modified` 日期都会自动更新——无需手动维护该字段。

---

## 进阶：高级技巧和可选插件 {#levelup}

### 战略性地使用图谱视图 (Graph View)

图谱视图不是一个生产力工具——它是一个诊断工具。每月使用一次，而不是每天。你要寻找的是：

- **孤立节点**（孤立笔记）→ 这些需要链接
- **具有许多连接的中心节点** → 这些是自然的 MOC 候选者
- **意想不到的集群** → 你未曾预料到的跨主题连接的想法。这些值得写新笔记。

通过添加路径过滤器将图谱过滤为只显示 `30 - Permanent`。包含模板和资源在内的完整库图谱是视觉噪音。

### Excalidraw 用于可视化思考

当你有大量永久笔记在空间上相关联时——例如流程、比较、层级结构，安装社区插件 **Excalidraw**。它直接嵌入到 Obsidian 中，并将绘图存储为 `.md` 文件（因此它们是面向未来的）。可用于：

- 跨相关笔记的论证图
- 链接文本不足时的可视化 MOC
- 永久笔记中引用的图表

### Obsidian Sync 实现跨设备访问

如果你在多台设备上工作——家里的台式机、工作中的笔记本电脑、阅读用的平板电脑——那么 [Obsidian Sync](URL_PLACEHOLDER_2) 值得付费。它会同步你的库，包括插件配置和设置，这很重要，因为你的 QuickAdd 选项和 Templater 模板都存储在库的 `.obsidian` 文件夹中。第三方同步（Dropbox、iCloud）可能会与基于 SQLite 的插件数据库发生同步冲突。Obsidian Sync 可以正确处理这个问题。它还提供版本历史——当你开始进行大量重组时，这是一个有用的安全网。

### 值得了解的可选插件

| 插件 | 用例 | 优先级 |
|---|---|---|
| **Smart Connections** | 基于语义相似度的 AI 驱动笔记建议 | 可有可无 (Nice to have) |
| **Strange New Worlds** | 在编辑器中显示反向链接计数 | 可有可无 (Nice to have) |
| **Kanban** | 将笔记转换为可视化看板——非常适合处理收件箱 | 可选 (Optional) |
| **Advanced Tables** | 使 Markdown 表格像电子表格一样可编辑 | 可选 (Optional) |
| **Better Word Count** | 比核心字数统计更准确的统计数据 | 次要的生活质量改善 (Minor QoL) |

不要一次性安装所有插件。添加一个，使用两周，然后决定它是否值得保留。

---

## 结论 {#conclusion}

这是你所构建的：

- 将想法阶段分开而没有造成官僚主义开销的文件夹结构
- 由 Templater 驱动的模板，在每条笔记上预填充一致的元数据
- QuickAdd 快捷键，让你在三秒内进入新的永久笔记
- Dataview 查询，自动浮现需要关注的内容——孤立笔记、草稿、主题集群
- Linter 无需手动操作即可保持 YAML 整洁

这个系统只有在你每天使用它（即使是短暂使用）才能发挥作用。处理零碎笔记并为新的永久笔记添加一个链接的十五分钟，其复合效应远超你的预期。90 天后，图谱将开始“回应”你。

**如果你想深入了解理论和高级工作流程设计**，[这门由经验丰富的知识管理实践者提供的 PKM 和 Obsidian 课程](URL_PLACEHOLDER_4)涵盖了完整的系统设计过程——从如何撰写真正产生洞见的原子笔记，到构建高级 Dataview 仪表板。一旦你掌握了基础知识，这笔投资将是值得的。

现在关闭这个标签页，开始设置你的库吧。阅读是容易的部分。

---

*披露：本文包含联盟链接。如果您通过它们购买，我们可能会获得佣金，而您无需支付额外费用。我们只推荐我们实际使用过的工具。*

---

## 常见问题

### 问：如果 Obsidian 已经通过文件名处理链接，我还需要在文件名中使用 UID 前缀吗？

技术上讲不需要——Obsidian 通过文件名解析链接，并在你重命名文件时自动更新它们。YAML frontmatter 中的 UID（而不是文件名）才是真正的稳定标识符。将其用于查询和未来导出到其他工具。文件名前缀（`ZK - `）纯粹是为了视觉排序，没有技术必要性。

### 问：我的系统需要多少永久笔记才能变得有用？

大多数人会在 50-100 条笔记之间开始感受到其价值。低于这个数量，图谱过于稀疏，无法浮现意想不到的连接。链接习惯比笔记数量更重要——一个包含 200 条已链接笔记的库，总是胜过 2,000 条未链接笔记的库。

### 问：文献笔记应该放在 Zettelkasten（永久文件夹）中还是单独存放？

将它们分开（`20 - Literature`）。文献笔记是经过处理的参考文献——它属于一个来源。永久笔记属于一个想法。它们之间的连接放在永久笔记的 `source` YAML 字段和文献笔记的 **My Permanent Notes** 部分。将它们混淆会模糊区别，并使 Dataview 查询更混乱。

### 问：我可以将现有的 Obsidian 库迁移到这个结构中而无需重新开始吗？

可以。创建文件夹结构，分批将现有笔记移动到适当的文件夹中，然后手动在每个文件夹上运行 Linter 以规范化 YAML。最重要的迁移任务是为现有笔记添加 `status: draft` 字段，以便 Dataview 查询能够捕获它们。使用 Obsidian 的 **查找和替换 (Find and Replace)** 功能在多个笔记中一次性添加缺失的 frontmatter 字段。

### 问：如果我不懂技术，Dataview 值得学习吗？

本指南中的查询足以应对 90% 的用例。复制粘贴它们，更改文件夹路径和标签名称以匹配你的设置，它们就会起作用。你不需要理解完整的 Dataview 查询语言就能从中受益。如果你想了解更多，[官方 Dataview 文档](URL_PLACEHOLDER_3)很直接，并有一个包含示例的查询构建器部分。

## 相关阅读

- [Excalidraw 是什么，为何在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [2024 年为何要在 Obsidian 中追踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
- [Obsidian 社区插件是什么？](/zh-cn/posts/obsidian-community-plugins-list/)
- [为何在 Obsidian 移动版上使用社区插件？](/zh-cn/posts/how-to-install-community-plugins-in-obsidian-mobile/)
---
images: ["/og/setting-up-a-zettelkasten-in-obsidian-with-plugins.webp"]
title: "Obsidian Zettelkasten：必备插件与设置指南"
date: 2026-04-28
slug: setting-up-a-zettelkasten-in-obsidian-with-plugins
description: "提供一个主观的、'一键式' 的启动库模板，其中包含预配置的插件和设置，让用户能够立即开始使用。"
keywords: ["obsidian zettelkasten guide", "how to build a second brain in obsidian", "obsidian note-taking system", "best plugins for zettelkasten obsidian", "dataview plugin zettelkasten", "templater plugin obsidian setup", "atomic notes obsidian", "linking your thinking obsidian"]
draft: false
author: "Alex Chen"
type: "informational"
tags: ["build", "zettelkasten", "obsidian", "setting up a zettelkasten in obsidian with plugins"]
---

_作为 Amazon 联盟会员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# 在 Obsidian 中使用插件设置 Zettelkasten：分步工作流程指南

---

**TL;DR**

- 在 Obsidian 中搭建一个可用的 Zettelkasten 需要特定的文件夹结构、三个核心社区插件（Templater、QuickAdd、Dataview）以及清晰定义的工作流程——而不仅仅是安装好插件却闲置不用。
- 本指南将从零开始构建系统：库结构 → 模板 → 自动化笔记创建 → 链接 → 动态查询，确保每个部分都有其作用。
- 最终，你将拥有一个摩擦最小的设置，只需按下一个快捷键并输入两秒钟，即可创建新的永久笔记。

---

## 目录

1. [为何在 Obsidian 中构建 Zettelkasten？](#why)
2. [核心插件栈：你的 Zettelkasten 工具包](#stack)
3. [步骤 1：设置你的库基础](#step1)
4. [步骤 2：使用 Templater 配置笔记模板](#step2)
5. [步骤 3：使用 QuickAdd 自动化笔记创建](#step3)
6. [步骤 4：Zettelkasten 工作流程实战](#step4)
7. [进阶：高级技巧和可选插件](#levelup)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 为何在 Obsidian 中构建 Zettelkasten？ {#why}

大多数笔记技巧都关乎*收集*信息。而 Zettelkasten 方法，由社会学家 Niklas Luhmann 开发，他用此方法出版了 70 多本书和 400 篇学术文章，其目的在于通过强制信息之间建立联系来*产生*想法。

使其发挥作用的三个机械规则：

1. **原子化笔记。** 每条笔记只包含一个想法，用你自己的话阐述。没有冗长的书籍摘要。没有堆积文件。
2. **明确的链接。** 每条新笔记至少引用一条现有笔记。链接才是重点，而不是标签或文件夹。
3. **无严格层级。** 网络通过链接而非预定义的文件夹分类法自然形成。

如果你想了解完整的哲学基础，[*How to Take Smart Notes* by Sönke Ahrens](URL_PLACEHOLDER_1) 是权威著作。读一遍，然后回来这里构建系统。

**为什么特别选择 Obsidian？**

- 笔记是本地存储的纯 `.md` 文件。没有厂商锁定。你 2035 年的库仍然可以打开，无需订阅。
- 双向链接和反向链接是第一类功能，而非事后添加。
- 插件生态系统足够庞大，可以自动化每一个重复步骤，而不会让应用程序变得臃肿。
- 图谱视图 (Graph View) 为你提供知识网络的可视化地图——有助于发现孤立笔记和意想不到的集群。

**本指南实际涵盖的内容：** 不是哲学（你可以阅读 Ahrens 的书）。不是表面化的插件列表。相反，你将获得一个具体、主观的工作流程，其中 Templater、QuickAdd 和 Dataview 作为一个相互连接的系统运作，而非三个不相关的功能。

---

## 核心插件栈：你的 Zettelkasten 工具包 {#stack}

在接触配置之前，请了解每个插件的作用以及它*为何*在插件栈中。安装你不了解的插件会导致设置被放弃。

| 插件 | 在系统中的作用 | 为何选择它 |
|---|---|---|
| **Templater** (社区) | 创建带有动态元数据的结构化笔记模板 | 确保每条永久笔记都具有一致的 YAML frontmatter 和自动填充的字段 |
| **QuickAdd** (社区) | 通过快捷键触发基于模板的笔记创建 | 消除了手动创建新笔记的多步操作 |
| **Dataview** (社区) | 像数据库一样查询你的笔记 | 为动态内容地图 (Maps of Content) 提供支持，并自动浮现孤立笔记 |
| **Linter** (社区) | 在保存时强制执行一致的格式 | 保持 YAML frontmatter 整洁，并添加/更新修改时间戳 |
| **Calendar** (社区) | 为每日笔记提供可点击的日历侧边栏 | 使零碎笔记捕获快速且按日期可导航 |
| **Unique Note Creator** (核心) | 生成带有 UID 前缀的文件名 | 为每条笔记提供一个稳定、无冲突的标识符 |

**为什么是这种特定组合？** Templater 处理*结构*，QuickAdd 处理*速度*，Dataview 处理*检索*，Linter 处理*一致性*。每个插件都填补了其他插件留下的空白。没有 Linter 和 Calendar 也可以操作，但对于此处描述的工作流程，Templater、QuickAdd 和 Dataview 是不可或缺的。

---

## 步骤 1：设置你的库基础 {#step1}

### 创建新库

打开 Obsidian → **创建新库**。给它一个永久名称（`ZK` 或 `Knowledge` 都可以）。将其放在你可控的位置——不要放在 Obsidian Sync 稍后也会尝试管理的云同步文件夹中。

### 推荐的文件夹结构

```
📁 ZK/
├── 📁 00 - Inbox/
├── 📁 10 - Fleeting/
├── 📁 20 - Literature/
├── 📁 30 - Permanent/
├── 📁 40 - Maps of Content/
├── 📁 50 - Resources/
└── 📁 _Templates/
```

**每个文件夹的作用：**

- **00 - Inbox:** 未处理的想法、链接、引文。任何内容都可以放在这里。你每天或每周清理它。
- **10 - Fleeting:** 尚未转化为永久笔记的快速笔记。每日笔记 (Daily Notes) 存放于此。
- **20 - Literature:** 每个来源（书籍、论文、文章）一条笔记。包含你处理过的摘录和摘要。
- **30 - Permanent:** 你的实际 Zettelkasten。这里的每条笔记都是原子化的、已链接的，并用你自己的话写成。
- **40 - Maps of Content:** 索引笔记，收集关于某个主题的永久笔记链接。它不是文件夹层级——只是一个精选的链接列表。
- **50 - Resources:** 参考资料（会议模板、项目文件等）。位于 ZK 核心之外。
- **_Templates:** Templater 使用的模板文件。将其放在根目录，便于插件访问。

### 配置核心 Obsidian 设置

前往 **设置 → 核心插件** 并启用：

- **每日笔记 (Daily notes)** — 将位置设置为 `10 - Fleeting`，日期格式为 `YYYY-MM-DD`
- **唯一笔记创建器 (Unique note creator)** — 将前缀格式设置为 `YYYYMMDDHHmm`，默认位置设置为 `00 - Inbox`
- **模板 (Templates)** (核心) — 指向 `_Templates`（你将使用 Templater 覆盖此设置，但仍需启用）
- **反向链接 (Backlinks)** 和 **出站链接 (Outgoing links)** — 启用两者，并设置为在侧边栏中打开

在 **设置 → 文件与链接 (Files & links)** 下：
- 将 **新笔记的默认位置 (Default location for new notes)** 设置为 `00 - Inbox`
- 启用 **重命名文件时自动更新内部链接 (Automatically update internal links)**
- 将 **新链接格式 (New link format)** 设置为 **文件相对路径 (Relative path to file)**

### 安装社区插件

前往 **设置 → 社区插件 → 浏览 (Browse)** 并安装：

1. Templater
2. QuickAdd
3. Dataview
4. Linter
5. Calendar

安装每个插件后，点击 **启用 (Enable)**。

---

## 步骤 2：使用 Templater 配置笔记模板 {#step2}

### 将 Templater 指向你的模板文件夹

**设置 → Templater：**
- 模板文件夹位置 (Template folder location): `_Templates`
- 启用 **在新文件创建时触发 Templater (Trigger Templater on new file creation)**: 开启
- 启用 **自动跳转到光标 (Automatic jump to cursor)**: 开启

### 创建永久笔记模板

在 `_Templates` 中，创建一个名为 `tpl-permanent-note.md` 的新文件。精确粘贴以下内容：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
title: <% tp.file.title %>
aliases: []
tags: []
created: <% tp.date.now("YYYY-MM-DD") %>
modified: <% tp.date.now("YYYY-MM-DD") %>
status: draft
source: ""
---

# <% tp.file.title %>

## The Idea

<!-- State the single idea this note is about. One paragraph. -->

## Why It Matters

<!-- Why does this idea matter to you? What does it connect to? -->

## Links

<!-- [[Related Note A]] | [[Related Note B]] -->

## References

<!-- [Source Title](URL) or Literature Note link -->
```

**每个 YAML 字段的作用：**

- `uid` — 基于时间戳的唯一 ID。允许你之后重命名文件而不会破坏引用。
- `title` — 创建时镜像文件名；对 Dataview 查询很有用。
- `aliases` — Obsidian 搜索时可以使用的别名。
- `status` — `draft` / `developing` / `mature`。跟踪笔记的成熟度。
- `source` — 想法的来源（URL、书名或 `[[Literature Note]]` 链接）。

### 创建文献笔记模板

创建 `_Templates/tpl-literature-note.md`：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
title: <% tp.file.title %>
author: ""
year: 
source-url: ""
tags: [literature]
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

## Bibliographic Info

- **Author:**
- **Year:**
- **URL / ISBN:**

## Key Arguments

1.

## Passages Worth Keeping

>

## My Permanent Notes from This Source

<!-- [[ZK - Note Title]] -->
```

### 创建零碎笔记模板

创建 `_Templates/tpl-fleeting-note.md`：

```markdown
---
uid: <% tp.date.now("YYYYMMDDHHmm") %>
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags: [fleeting]
---

# Fleeting: <% tp.date.now("YYYY-MM-DD HH:mm") %>

<!-- Dump the thought here. Don't edit. Process later. -->

**To process:** [ ]
```

零碎笔记中的复选框是故意的——你可以在之后通过 Dataview 查询所有未处理的零碎笔记。

---

## 步骤 3：使用 QuickAdd 自动化笔记创建 {#step3}

这就是设置的价值所在。你不再需要：新建文件 → 命名 → 应用模板 → 移动到文件夹 → 开始写作，而是只需按一个快捷键，笔记就会出现，已命名、已模板化并可供编辑。

### 为永久笔记配置 QuickAdd

前往 **设置 → QuickAdd**：

1. 在底部文本字段中，输入 `New Permanent Note` 并点击 **添加选项 (Add Choice)**
2. 选择 **模板 (Template)** 作为选项类型
3. 点击新选项旁边的 ⚙️ 齿轮图标

配置模板选项：

| 设置 | 值 |
|---|---|
| **模板路径 (Template Path)** | `_Templates/tpl-permanent-note.md` |
| **文件名格式 (File Name Format)** | `ZK - {{VALUE:Note title?}}` |
| **创建到文件夹 (Create in Folder)** | `30 - Permanent` |
| **打开 (Open)** | 启用 |
| **聚焦新笔记 (Focus new note)** | 启用 |

点击 ⚡ 闪电图标将此选项添加到 QuickAdd 菜单栏按钮。

**触发此操作时会发生什么：** QuickAdd 会提示你“笔记标题？(Note title?)”，你输入四个词，按 Enter 键，然后你就在 `30 - Permanent` 中打开了一个新永久笔记，所有 YAML 都已预填，光标等待输入。

### 为零碎笔记设置 QuickAdd

重复[此过程：

1. 添加一个新选项：`New Fleeting Note`
2. 类型：模板 (Template)
3. 配置：

| 设置 | 值 |
|---|---|
| **模板路径 (Template Path)** | `_Templates/tpl-fleeting-note.md` |
| **文件名格式 (File Name Format)** | `Fleeting - {{DATE:YYYYMMDDHHmm}}` |
| **创建到文件夹 (Create in Folder)** | `10 - Fleeting` |
| **打开 (Open)** | 启用 |

这个不需要你输入标题——它会自动为文件加上时间戳。先捕获，后思考。

### 分配快捷键

前往 **设置 → 快捷键 (Hotkeys)**，搜索 `QuickAdd`：

- `QuickAdd: New Permanent Note` → 分配 `Ctrl+Shift+P` (Windows/Linux) 或 `Cmd+Shift+P` (Mac)
- `QuickAdd: New Fleeting Note` → 分配 `Ctrl+Shift+F` 或 `Cmd+Shift+F`

测试两者。你应该在按下快捷键的两秒内进入一个新笔记。

---

## 步骤 4：Zettelkasten 工作流程实战 {#step4}

有了基础设施，以下是精确的日常工作流程。

### 阶段 1：捕获（收件箱 / 零碎笔记）

你正在阅读一篇文章并产生了一个想法。按下 `Cmd+Shift+F`。输入想法。关闭。完成。不要试图现在处理它——收件箱是一个压力阀，而不是最终目的地。

在你的每日回顾会话（15-20 分钟）中，打开 `10 - Fleeting` 并查看所有未勾选 `[ ]` 的内容。

### 阶段 2：处理为永久笔记

对于每条有价值的零碎笔记：

1. 按下 `Cmd+Shift+P`
2. 输入一个描述性、具体的标题（差的例子：“记忆”；好的例子：“间隔重复通过利用间隔效应发挥作用”）
3. 按 Enter 键
4. 在 **The Idea** 下用你自己的话写下想法
5. 在 **Why It Matters** 下添加你的个人解读
6. 完成后，将零碎笔记的复选框标记为 `[x]`

**原子笔记测试：** 你能用一句话总结这条笔记吗？如果答案是两句话由“和”连接，那么将其拆分为两条笔记。

### 阶段 3：链接新笔记

这就是 Zettelkasten 能否发挥作用的关键。在关闭新的永久笔记之前：

1. 问自己：这条笔记与哪些现有笔记相关联？
2. 在 **Links** 部分输入 `[[` 并搜索你的库
3. 添加至少一个出站链接——即使它很松散（“这与 [[Confirmation Bias]] 相关，因为……”）
4. 打开链接的笔记并在那里也添加一个反向链接引用

几周后，图谱视图 (Graph View)（`Ctrl+G`）将向你展示你是在真正链接还是只是归档。

### 阶段 4：使用 Dataview 展现知识

在 `40 - Maps of Content` 中创建一条名为 `MOC - Unlinked Notes.md` 的笔记：

````markdown
# 孤立的永久笔记

没有出站链接的笔记——它们需要连接。

```dataview
TABLE created, status
FROM "30 - Permanent"
WHERE length(file.outlinks) = 0
SORT created DESC
```
````

再创建一条：`MOC - Draft Notes.md`：

````markdown
# 仍处于草稿状态的笔记

```dataview
TABLE created, file.mtime as "Last Modified"
FROM "30 - Permanent"
WHERE status = "draft"
SORT file.mtime ASC
```
````

以及一个主题特定的 MOC。例如，`MOC - Learning Science.md`：

````markdown
# 学习科学

```dataview
LIST
FROM "30 - Permanent"
WHERE contains(tags, "learning") OR contains(tags, "memory") OR contains(tags, "cognition")
SORT created ASC
```
````

这些 Dataview 查询在你每次打开笔记时都会自动更新。无需手动维护。孤立笔记查询特别有用——一条孤立的永久笔记意味着它尚未完成其任务。

### 配置 Linter 进行自动清理

前往 **设置 → Linter：**

在 **YAML** 下，启用：
- **YAML 时间戳 (YAML Timestamp)** — 在每次保存时添加/更新 `modified` 字段
- **强制 YAML 特殊字符转义 (Force YAML escape on special characters)**

在 **通用 (General)** 下，启用 **保存时 lint (Lint on save)**。

现在，每次你按下 `Ctrl+S` 时，`modified` 日期都会自动更新——无需手动维护该字段。

---

## 进阶：高级技巧和可选插件 {#levelup}

### 战略性地使用图谱视图 (Graph View)

图谱视图不是一个生产力工具——它是一个诊断工具。每月使用一次，而不是每天。你要寻找的是：

- **孤立节点**（孤立笔记）→ 这些需要链接
- **具有许多连接的中心节点** → 这些是自然的 MOC 候选者
- **意想不到的集群** → 你未曾预料到的跨主题连接的想法。这些值得写新笔记。

通过添加路径过滤器将图谱过滤为只显示 `30 - Permanent`。包含模板和资源在内的完整库图谱是视觉噪音。

### Excalidraw 用于可视化思考

当你有大量永久笔记在空间上相关联时——例如流程、比较、层级结构，安装社区插件 **Excalidraw**。它直接嵌入到 Obsidian 中，并将绘图存储为 `.md` 文件（因此它们是面向未来的）。可用于：

- 跨相关笔记的论证图
- 链接文本不足时的可视化 MOC
- 永久笔记中引用的图表

### Obsidian Sync 实现跨设备访问

如果你在多台设备上工作——家里的台式机、工作中的笔记本电脑、阅读用的平板电脑——那么 [Obsidian Sync](URL_PLACEHOLDER_2) 值得付费。它会同步你的库，包括插件配置和设置，这很重要，因为你的 QuickAdd 选项和 Templater 模板都存储在库的 `.obsidian` 文件夹中。第三方同步（Dropbox、iCloud）可能会与基于 SQLite 的插件数据库发生同步冲突。Obsidian Sync 可以正确处理这个问题。它还提供版本历史——当你开始进行大量重组时，这是一个有用的安全网。

### 值得了解的可选插件

| 插件 | 用例 | 优先级 |
|---|---|---|
| **Smart Connections** | 基于语义相似度的 AI 驱动笔记建议 | 可有可无 (Nice to have) |
| **Strange New Worlds** | 在编辑器中显示反向链接计数 | 可有可无 (Nice to have) |
| **Kanban** | 将笔记转换为可视化看板——非常适合处理收件箱 | 可选 (Optional) |
| **Advanced Tables** | 使 Markdown 表格像电子表格一样可编辑 | 可选 (Optional) |
| **Better Word Count** | 比核心字数统计更准确的统计数据 | 次要的生活质量改善 (Minor QoL) |

不要一次性安装所有插件。添加一个，使用两周，然后决定它是否值得保留。

---

## 结论 {#conclusion}

这是你所构建的：

- 将想法阶段分开而没有造成官僚主义开销的文件夹结构
- 由 Templater 驱动的模板，在每条笔记上预填充一致的元数据
- QuickAdd 快捷键，让你在三秒内进入新的永久笔记
- Dataview 查询，自动浮现需要关注的内容——孤立笔记、草稿、主题集群
- Linter 无需手动操作即可保持 YAML 整洁

这个系统只有在你每天使用它（即使是短暂使用）才能发挥作用。处理零碎笔记并为新的永久笔记添加一个链接的十五分钟，其复合效应远超你的预期。90 天后，图谱将开始“回应”你。

**如果你想深入了解理论和高级工作流程设计**，[这门由经验丰富的知识管理实践者提供的 PKM 和 Obsidian 课程](URL_PLACEHOLDER_4)涵盖了完整的系统设计过程——从如何撰写真正产生洞见的原子笔记，到构建高级 Dataview 仪表板。一旦你掌握了基础知识，这笔投资将是值得的。

现在关闭这个标签页，开始设置你的库吧。阅读是容易的部分。

---

*披露：本文包含联盟链接。如果您通过它们购买，我们可能会获得佣金，而您无需支付额外费用。我们只推荐我们实际使用过的工具。*

---

## 常见问题

### 问：如果 Obsidian 已经通过文件名处理链接，我还需要在文件名中使用 UID 前缀吗？

技术上讲不需要——Obsidian 通过文件名解析链接，并在你重命名文件时自动更新它们。YAML frontmatter 中的 UID（而不是文件名）才是真正的稳定标识符。将其用于查询和未来导出到其他工具。文件名前缀（`ZK - `）纯粹是为了视觉排序，没有技术必要性。

### 问：我的系统需要多少永久笔记才能变得有用？

大多数人会在 50-100 条笔记之间开始感受到其价值。低于这个数量，图谱过于稀疏，无法浮现意想不到的连接。链接习惯比笔记数量更重要——一个包含 200 条已链接笔记的库，总是胜过 2,000 条未链接笔记的库。

### 问：文献笔记应该放在 Zettelkasten（永久文件夹）中还是单独存放？

将它们分开（`20 - Literature`）。文献笔记是经过处理的参考文献——它属于一个来源。永久笔记属于一个想法。它们之间的连接放在永久笔记的 `source` YAML 字段和文献笔记的 **My Permanent Notes** 部分。将它们混淆会模糊区别，并使 Dataview 查询更混乱。

### 问：我可以将现有的 Obsidian 库迁移到这个结构中而无需重新开始吗？

可以。创建文件夹结构，分批将现有笔记移动到适当的文件夹中，然后手动在每个文件夹上运行 Linter 以规范化 YAML。最重要的迁移任务是为现有笔记添加 `status: draft` 字段，以便 Dataview 查询能够捕获它们。使用 Obsidian 的 **查找和替换 (Find and Replace)** 功能在多个笔记中一次性添加缺失的 frontmatter 字段。

### 问：如果我不懂技术，Dataview 值得学习吗？

本指南中的查询足以应对 90% 的用例。复制粘贴它们，更改文件夹路径和标签名称以匹配你的设置，它们就会起作用。你不需要理解完整的 Dataview 查询语言就能从中受益。如果你想了解更多，[官方 Dataview 文档](URL_PLACEHOLDER_3)很直接，并有一个包含示例的查询构建器部分。

## 相关阅读

- [Excalidraw 是什么，为何在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [2024 年为何要在 Obsidian 中追踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
- [Obsidian 社区插件是什么？](/zh-cn/posts/obsidian-community-plugins-list/)
- [为何在 Obsidian 移动版上使用社区插件？](/zh-cn/posts/how-to-install-community-plugins-in-obsidian-mobile/)