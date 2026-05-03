---
images: ["/og/how-to-use-obsidian-dataview-for-beginners.webp"]
title: "什么是 Dataview，为什么它是改变你笔记方式的利器？"
date: 2026-04-28
slug: how-to-use-obsidian-dataview-for-beginners
description: "提供适用于常见场景（如会议记录、项目跟踪和内容日历）的复制粘贴即用查询“配方”，让初学者能立即获得价值。"
keywords: ["obsidian dataview examples", "dataview query language", "DQL tutorial", "obsidian dataview table", "obsidian dataview list", "obsidian dataview task query", "how to install dataview obsidian", "obsidian metadata tutorial"]
draft: false
author: "Alex Chen"
type: "informational"
---

# 如何为初学者使用 Obsidian Dataview：带有可复制查询的详细指南

---

**总结 (TL;DR)**

- Dataview 可以使用简单的、类似自然语言的命令将你的 Obsidian 笔记变成一个可查询的数据库——无需任何编程经验。
- 你可以使用 YAML frontmatter 或内联字段 (inline fields) 为笔记添加“标签”（元数据），然后编写简短的查询，将这些笔记自动汇总成列表和表格。
- 本指南为你提供了会议记录、图书追踪器和项目中心的复制粘贴配方——你可以在 10 分钟内构建出可用的仪表板 (dashboards)。

---

## 目录

1. [什么是 Dataview，为什么它是改变你笔记方式的利器？](#what-is-dataview)
2. [第 1 步：在 60 秒内安装和设置 Dataview](#installing-dataview)
3. [秘诀：如何为 Dataview 标记笔记](#tagging-notes)
4. [你的第一个查询：从零到自动列表](#first-queries)
5. [实用配方：今天就能构建的 3 个 Dataview 仪表板](#practical-recipes)
6. [过滤和排序：准确找到你需要的内容](#filtering-sorting)
7. [救命！我的查询不起作用：常见错误及修复方法](#troubleshooting)
8. [常见问题解答 (FAQ)](#faq)
9. [结论](#conclusion)

---

## 什么是 Dataview，为什么它是改变你笔记方式的利器？ {#what-is-dataview}

可以将 Dataview 想象为你 vault（库）中的自动图书管理员。你像往常一样编写笔记，但你为它们附加了小标签——状态、日期、类别。Dataview 读取这些标签并为你构建动态索引。每次你添加新笔记时，索引都会自动更新。你再也不用手动维护项目或会议记录的列表了。

**使用 Dataview 之前：** 你有 200 篇笔记放在文件夹里。要找到每一个标记了 `#project/alpha` 的笔记，意味着你要么得记住你把它们放在了哪里，要么得运行一次搜索，并祈祷你那天的命名是一致的。

**使用 Dataview 之后：** 只需要一篇笔记——你的“项目 Alpha 中心”——就能显示一个实时更新的表格，包含所有相关笔记、它们的状态以及最后修改的时间。无论你何时创建或更改了任何内容，它都会瞬间更新。

Dataview 带来的三个具体优势：

1. **自动索引。** 一篇名为“阅读列表”的笔记能够始终显示你 vault 中的每一本图书笔记，并按评分排序——设置完成后你完全不需要再去管它。
2. **动态仪表板。** 一个每周回顾页面可以提取跨所有笔记中标记为未完成的每一项任务，无需手动收集。
3. **跨文件任务追踪。** 你可以通过单一视图查看整个 vault 中的每一个 `- [ ]` 复选框，并可以按项目或截止日期进行过滤。

如果你认真考虑建立一个真正的个人知识系统，[《Building a Second Brain》by Tiago Forte](URL_PLACEHOLDER_1) 和 [《How to Take Smart Notes》by Sönke Ahrens](URL_PLACEHOLDER_2) 中清晰地阐述了这种结构化笔记背后的理念——这两本书都值得与本指南一起阅读。

---

## 第 1 步：在 60 秒内安装和设置 Dataview {#installing-dataview}

Dataview 是一个社区插件 (community plugin)，因此你需要先启用社区插件。

**安装步骤：**

1. 打开 Obsidian。转到 **Settings**（左下角的齿轮图标）。
2. 在左侧边栏中点击 **Community plugins**。
3. 如果你看到“安全模式”警告，请点击 **Turn on community plugins**。
4. 点击 **Browse**。
5. 在搜索栏中，输入 **Dataview**。
6. 点击作者为 **blacksmithgu** 的结果，然后点击 **Install**。
7. 安装完成后，点击 **Enable**。

就是这样——Dataview 已经开始运行了。

**有两个值得立即启用的设置：**

- **Enable JavaScript Queries** — 这会解锁 `dataviewjs` 代码块，当基础查询不够用时，它能提供更强大的功能。转到 Settings → Dataview，然后将其打开。你今天不需要它，但以后你会用到的。
- **Enable Inline Queries** — 这允许你在单行文本内运行微小查询，比如在句子中嵌入实时的笔记计数。同样在 Settings → Dataview 中设置。

将其他所有内容保留为默认设置即可。你以后可以探索其他设置，但这两个是初学者跟着教程做却发现不起作用时最容易遇到的绊脚石。

---

## 秘诀：如何为 Dataview 标记笔记 {#tagging-notes}

Dataview 只能报告它能读取的内容。这意味着你的笔记需要元数据 (metadata)——Dataview 可以找到和过滤的结构化信息。可以将元数据想象成贴在文件系统上的便利贴标签。

有两种添加元数据的方法。

### 方法 1：YAML Frontmatter（推荐用于结构化笔记）

YAML frontmatter 位于笔记的最顶部，被两组三个破折号包围。它是最可靠的方法，并且适用于每一种 Dataview 查询类型。

```yaml
---
title: "Q3 Marketing Meeting"
date: 2024-09-15
type: meeting
status: done
attendees:
  - Sarah
  - Dev team
tags:
  - meetings
  - marketing
---
```

每一行都是一个 `key: value` 键值对。你定义了键 (keys)——Dataview 读取它们。名称由你来选择；只需保持一致。如果你在一篇笔记中称其为 `status`，而在另一篇笔记中称其为 `Status`（大写 S），Dataview 会将它们视为不同的字段。

**适用于会议记录的复制粘贴模板：**

```yaml
---
title: ""
date: 
type: meeting
project: ""
status: done
---
```

### 方法 2：内联字段 (Inline Fields)（用于快速的随时标记）

你可以使用 `key:: value` 格式在笔记正文的任何地方添加元数据。

```
Today I finished reading **Atomic Habits**.

rating:: 5
status:: read
author:: James Clear
genre:: self-help
```

当你是流畅写作优先并想随时插入一个数据点而不想回到顶部时，内联字段 (inline fields) 会更快。双冒号 (`::`) 是 Dataview 寻找的信号。

**何时使用哪种方法：**

| 方法 | 最适合 | 限制 |
|---|---|---|
| YAML frontmatter | 模板，结构化的笔记类型 | 必须在文件的顶部 |
| 内联字段 | 随手笔记，段落中的数据 | 在复杂查询中可靠性稍差 |

针对每种笔记类型，选择一种方法并坚持下去。在同一笔记中混合使用两种方法虽然有效，但很快就会变得令人困惑。

---

## 你的第一个查询：从零到自动列表 {#first-queries}

Dataview 查询位于一个特殊的代码块内。你用三个反引号和单词 `dataview` 打开它，编写你的查询，然后用三个反引号关闭它。

````
```dataview
LIST FROM #meetings
```
````

那是可能的最简单的查询。它将每一个标记有 `#meetings` 的笔记显示为一个可点击的列表。

### 三个构建块

每一个 Dataview 查询都遵循这种模式：

```
[显示什么] [从哪里获取] [如何过滤/排序]
```

在实际语法中：

```
LIST / TABLE [字段]
FROM [来源]
WHERE [条件]
SORT [字段] [asc/desc]
```

### 将通俗语言转化为 Dataview 查询

| 你想要的 | Dataview 查询 |
|---|---|
| 显示带有某个标签的所有笔记 | `LIST FROM #your-tag` |
| 显示某个文件夹中的所有笔记 | `LIST FROM "FolderName"` |
| 显示具有特定状态的笔记 | `LIST FROM #projects WHERE status = "active"` |
| 显示带有特定列的表格 | `TABLE author, status FROM #books` |
| 显示所有笔记中未完成的任务 | `TASK WHERE !completed` |

### 你的第一个表格

````
```dataview
TABLE date, status, project
FROM #meetings
SORT date desc
```
````

这会将每篇会议笔记显示为一个包含三列（date，status 和 project）的表格，并将最新的会议排在最前面。如果你的会议笔记有带有那些完全相同的字段名称的 YAML frontmatter，你在粘贴它之后就能立即生效。

---

## 实用配方：今天就能构建的 3 个 Dataview 仪表板 {#practical-recipes}

为这些仪表板中的每一个创建一个新笔记。粘贴 frontmatter 模板和查询，然后开始添加带有匹配元数据的笔记。

### 配方 1：会议记录索引

**它的作用：** 自动列出过去 30 天内的每一次会议记录。

为你的会议记录创建一个 YAML 模板：

```yaml
---
type: meeting
date: 2024-09-15
attendees: ""
project: ""
action-items: ""
---
```

仪表板查询：

````
```dataview
TABLE date, attendees, project
FROM #meetings OR "Meetings"
WHERE date >= date(today) - dur(30 days)
SORT date desc
```
````

你创建的每一篇新会议笔记——把它放在你的“Meetings”文件夹里或给它打上 `#meetings` 标签，填写 frontmatter——这个表格就会自我更新。

### 配方 2：图书追踪器表格

**它的作用：** 记录你记录过的每一本书，包含作者、阅读状态和你的评分。

适用于图书笔记的 Frontmatter 模板：

```yaml
---
type: book
author: ""
genre: ""
status: reading
rating: 
date-finished:
---
```

仪表板查询：

````
```dataview
TABLE author, genre, status, rating, date-finished
FROM "Books"
SORT rating desc
```
````

你最终会得到一个排序的阅读列表，当你更改评分或将一本书标记为完成时，它就会更新。不需要电子表格。

### 配方 3：项目中心

**它的作用：** 将与一个项目相关的所有笔记和开放任务拉入单一视图。

````
```dataview
TABLE file.mtime as "Last Modified", status
FROM "Projects/Alpha"
SORT file.mtime desc
```
````

在那之下，在同一个中心笔记上，添加一个任务视图：

````
```dataview
TASK
FROM "Projects/Alpha"
WHERE !completed
```
````

现在你的项目 Alpha 中心显示了该文件夹中的所有笔记以及所有这些笔记中的开放复选框。这是大多数人试图构建的“Obsidian 中的仪表板”场景。

如果你想深入了解如何正确构建此类系统，[Skillshare 或 Udemy 上的 PKM 和 Obsidian 课程](URL_PLACEHOLDER_3) 涵盖了使这些查询强大得多的 vault 架构。

---

## 过滤和排序：准确找到你需要的内容 {#filtering-sorting}

### WHERE 子句

`WHERE` 过滤你的结果。只有符合条件的笔记才会出现。

```
WHERE status = "in-progress"
WHERE rating >= 4
WHERE date > date(2024-01-01)
WHERE contains(tags, "work")
```

你可以组合多个条件：

```
WHERE status = "in-progress" AND project = "Alpha"
WHERE status = "done" OR status = "archived"
```

### SORT 子句

`SORT` 控制顺序。`asc` = A 到 Z，从最旧到最新。`desc` = Z 到 A，从最新到最旧。

```
SORT date desc
SORT rating asc
SORT file.mtime desc
```

`file.mtime` 是 Dataview 为每篇笔记创建的内置字段——它的意思是“该文件最后修改的时间”。你不需要将其添加到你的 frontmatter 中。

### 一个完整的、实用的查询

这里是将所有内容组合成一个查询的例子，该查询找到所有活跃的工作项目，显示它们的截止日期和所有者，并将最近修改的项目放在顶部：

````
```dataview
TABLE due-date, owner, status
FROM #projects
WHERE status = "active"
SORT file.mtime desc
```
````

像读句子一样去理解它：“给我一个由 due-date，owner 和 status 组成的表格，来自标记为 #projects 的笔记，但仅显示 status 等于 active 的那些，并将最近更改过的放在前面。”

---

## 救命！我的查询不起作用：常见错误及修复方法 {#troubleshooting}

### 错误 1：“Dataview: No results to show”

这是最常见的问题。它意味着 Dataview 已成功运行但找到了零个匹配的笔记。

**检查清单：**

- [ ] 查询中的标签是否与笔记中的标签完全匹配？（`#meetings` 与 `#Meetings` —— 区分大小写）
- [ ] 括号中的文件夹名称是否完全匹配，包括大写？（`"Books"` 与 `"books"`）
- [ ] 在运行查询之前，你是否保存了带有 frontmatter 的笔记？
- [ ] WHERE 中的字段名拼写是否与 YAML 中的字段名完全相同？

**快速测试：** 将 `FROM #your-tag` 更改为 `FROM ""`（空字符串表示“整个 vault”）。如果出现结果，说明你的标签或文件夹路径错误。

### 错误 2：查询代码块显示为纯文本

你在开头的反引号之后漏掉了 `dataview` 这个词，或者该插件没有启用。返回 Settings → Community plugins，并确认 Dataview 已打开。

### 错误 3：你的表格中某个字段显示为“null”

该字段存在于你的查询中，但在那篇笔记的 frontmatter 中不存在。要么将该字段添加到笔记中，要么在查询中添加 `WHERE 字段名` 以排除没有该字段的笔记。

### 错误 4：文件夹路径不起作用

Dataview 中的文件夹路径区分大小写，并且必须完全匹配。如果你的文件夹是 `Projects/Alpha Team`，查询需要写成 `FROM "Projects/Alpha Team"` ——而不是 `from "projects/alpha team"` 或 `FROM "Projects/AlphaTeam"`。

**专业提示：** 在 Obsidian 中，右键点击文件资源管理器中的文件夹并检查确切的名称。直接将它复制粘贴到你的查询中。

### 错误 5：日期比较不起作用

你的日期字段在 frontmatter 中必须采用 `YYYY-MM-DD` 格式。`date: September 15, 2024` 无法正确解析。请使用 `date: 2024-09-15`。

---

## 结论 {#conclusion}

Dataview 并不是魔法，但很接近了。核心工作流很简单：使用 YAML frontmatter 为你的笔记添加一致的标签，使用 `LIST / TABLE / FROM / WHERE / SORT` 结构编写一个简短的查询，然后让 Dataview 为你完成维护工作。

从小处开始。这周先建立图书追踪器。下周，设置会议索引。不到一个月的时间，你就会拥有一个自我组织的 vault，你会惊讶于以前没有它你是如何工作的。

在早期最能产生影响的三件事：frontmatter 中一致的字段名、将笔记放入符合逻辑的文件夹中，以及当查询没有返回任何结果时使用故障排除检查清单。

**准备好更进一步了吗？**

- 加深对使 Dataview 真正有用的 PKM 理念的理解：[购买一本《Building a Second Brain》](URL_PLACEHOLDER_1) 或 [《How to Take Smart Notes》](URL_PLACEHOLDER_2)。
- 如需关于 Obsidian 和个人知识管理的结构化视频学习，[Skillshare 和 Udemy 上都有专门的 Obsidian 课程](URL_PLACEHOLDER_3)，其中涵盖了结合真实 vault 示例的高级 Dataview 设置。
- 如果你希望能在任何地方使用你井井有条的 vault，[Obsidian Sync](URL_PLACEHOLDER_4) 是官方的端到端加密选项——你的 Dataview 仪表板在每台设备上的工作方式都将完全一致。

从一个查询开始。一切都会水到渠成。

---

## 常见问题解答 (FAQ)

### 问：我需要知道如何编码才能使用 Dataview 吗？

不需要。基础的查询语言 (DQL) 读起来几乎就像普通的英语。本指南中的示例不需要任何编程背景。唯一“高级”的选项——DataviewJS——使用 JavaScript，但你可以在完全不碰它的情况下完成绝大多数实际使用场景。

### 问：Dataview 会拖慢我的 Obsidian vault 吗？

在低于 1,000 篇笔记的 vault 中，你不会注意到任何差异。在非常大的 vault（超过 5,000 篇笔记）上，没有 `FROM` 过滤器的复杂查询——意味着它们会扫描每一个文件——可能会增加一点延迟。将你的查询范围限制在特定的文件夹或标签可以保持运行速度。

### 问：Dataview 标签和 Obsidian 标签有什么区别？

它们是相同的标签。你笔记正文或 frontmatter 中的 `#meetings` 与 Obsidian 在 Tags 面板中显示的标签是一样的。Dataview 读取 Obsidian 的原生标签——你不需要单独的系统。

### 问：我可以通过 Obsidian Sync 在多台设备上使用 Dataview 吗？

是的。[Obsidian Sync](URL_PLACEHOLDER_4) 会同步你的整个 vault，包括 Dataview 插件和你的所有笔记。你的仪表板在手机、平板电脑和任何其他设备上都能完全发挥功能。查询在每台设备上本地运行，而不是在云端。

### 问：为什么我应该使用 YAML frontmatter 而不仅仅是依赖文件夹和标签？

标签和文件夹回答了“这篇笔记在哪里？”。Frontmatter 回答了“这篇笔记是关于什么的，以及它的属性是什么？”。一篇图书笔记可以在 Books 文件夹中并且打上了 #books 标签——但只有 frontmatter 能告诉 Dataview 这本特定的书评分为 4 分，是在 3 月 3 日看完的，且状态为“已读”。这才是让过滤和排序真正有用的原因。

## 相关阅读

- [什么是 Periodic Notes 插件（为什么它是改变你笔记方式的利器）](/zh-cn/posts/obsidian-periodic-notes-plugin-review/)
- [什么是 Obsidian Callouts（为什么它们是改变你笔记方式的利器）](/zh-cn/posts/how-to-use-callouts-in-obsidian-for-better-notes/)
- [为什么你的日记需要 Templater 插件](/zh-cn/posts/obsidian-templater-plugin-tutorial-for-daily-notes/)
- [为什么主题是你在 Obsidian 中最重要的写作工具](/zh-cn/posts/best-obsidian-themes-for-writing-longform-content/)