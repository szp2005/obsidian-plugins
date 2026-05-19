---
images: ["/og/how-to-use-obsidian-dataview-for-beginners.webp"]
title: "Obsidian Dataview 指南：将笔记转化为数据库"
date: 2026-04-28
slug: how-to-use-obsidian-dataview-for-beginners
description: "提供一份“食谱”，其中包含可复制粘贴的常见查询示例，适用于会议记录、项目追踪和内容日历等场景，助力初学者轻松上手。"
keywords: ["obsidian dataview examples", "dataview query language", "DQL tutorial", "obsidian dataview table", "obsidian dataview list", "obsidian dataview task query", "how to install dataview obsidian", "obsidian metadata tutorial"]
draft: false
author: "Alex Chen"
type: "informational"
tags: ["dataview", "game changer", "notes", "how to use obsidian dataview for beginners"]
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。本帖子可能包含联盟链接。_

# Obsidian Dataview 初学者指南：一步步教学，附带可复制粘贴的查询示例

---

**TL;DR 摘要**

- Dataview 使用简单、类似英语的命令，将您的 Obsidian 笔记转化为可查询的数据库——无需任何编程经验。
- 您可以通过 YAML Frontmatter 或行内字段为笔记添加“标签”（元数据），然后编写简短的查询，将这些笔记自动整理成列表和表格。
- 本指南提供了会议记录、图书追踪和项目中心的可复制粘贴“食谱”——您可以在不到 10 分钟内构建出有效的工作仪表板。

---

## 目录

1. [什么是 Dataview，以及它为何能彻底改变您的笔记管理？](#what-is-dataview)
2. [第一步：在 60 秒内安装和设置 Dataview](#installing-dataview)
3. [秘诀：如何为 Dataview 标记笔记](#tagging-notes)
4. [您的首次查询：从零开始创建自动化列表](#first-queries)
5. [实用“食谱”：今天即可构建的 3 个 Dataview 仪表板](#practical-recipes)
6. [筛选和排序：精确找到您所需的信息](#filtering-sorting)
7. [求助！我的查询不工作：常见错误与修复](#troubleshooting)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 什么是 Dataview，以及它为何能彻底改变您的笔记管理？ {#what-is-dataview}

将 Dataview 视为您知识库的自动图书管理员。您可以像往常一样写笔记，但会给它们附上小标签——状态、日期、类别。Dataview 会读取这些标签，并为您建立实时索引。每次添加新笔记时，索引都会自动更新。您再也无需手动维护项目列表或会议记录。

**使用 Dataview 之前：** 您的文件夹中有 200 篇笔记。要找到所有标记为 `#project/alpha` 的笔记，要么需要记住文件位置，要么需要运行搜索并祈祷您当天的命名保持一致。

**使用 Dataview 之后：** 一篇名为“Project Alpha Hub”的笔记会实时显示所有相关笔记的表格、其状态以及上次修改时间。您创建或更改任何内容时，它都会立即更新。

Dataview 带来的三大具体优势：

1.  **自动索引。** 一篇名为“阅读清单”的笔记，它会始终显示您知识库中所有书籍笔记，并按评分排序——设置完成后无需您再进行任何操作。
2.  **动态仪表板。** 一个每周回顾页面，可以拉取所有笔记中标记为未完成的任务，无需手动收集。
3.  **跨文件任务追踪。** 一个视图即可查看您整个知识库中所有 `- [ ]` 复选框，并可按项目或截止日期进行筛选。

如果您认真对待构建一个真正的个人知识系统，那么 [Tiago Forte 的《打造第二大脑》](URL_PLACEHOLDER_1) 和 [Sönke Ahrens 的《如何做卡片笔记》](URL_PLACEHOLDER_2) 清晰地阐述了这种结构化笔记背后的概念——这两本书都值得在本指南之外阅读。

---

## 第一步：在 60 秒内安装和设置 Dataview {#installing-dataview}

Dataview 是一个社区插件，因此您需要首先启用社区插件。

**安装步骤：**

1.  打开 Obsidian。进入 **设置**（左下角的齿轮图标）。
2.  点击左侧边栏中的 **社区插件**。
3.  如果看到“安全模式”警告，点击 **关闭安全模式**。
4.  点击 **浏览**。
5.  在搜索栏中输入 **Dataview**。
6.  点击由 **blacksmithgu** 提供的结果，然后点击 **安装**。
7.  安装完成后，点击 **启用**。

就这样——Dataview 已经运行。

**值得立即启用的两项设置：**

-   **启用 JavaScript 查询**——这解锁了 `dataviewjs` 代码块，当基本查询不足时，它能为您提供更多功能。前往“设置”→“Dataview”，然后打开此开关。您今天可能不需要它，但以后会用到。
-   **启用行内查询**——这允许您在文本行内运行微型查询，例如在句子中嵌入实时笔记计数。同样在“设置”→“Dataview”中。

其他设置保持默认。您可以稍后探索其他设置，但对于初学者来说，当他们按照教程操作却出现问题时，通常是这两个设置出了错。

---

## 秘诀：如何为 Dataview 标记笔记 {#tagging-notes}

Dataview 只能报告它能读取的内容。这意味着您的笔记需要元数据——Dataview 可以找到和筛选的结构化信息。将元数据想象成文件档案上的便利贴标签。

有两种方法可以添加元数据。

### 方法 1：YAML Frontmatter（推荐用于结构化笔记）

YAML Frontmatter 位于笔记的最顶部，在两组三条破折号之间。这是最可靠的方法，并且适用于所有 Dataview 查询类型。

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

每行都是一个 `key: value` 对。您定义键——Dataview 读取它们。名称由您选择；只需保持一致。如果您在一个笔记中称之为 `status`，而在另一个笔记中称之为 `Status`（大写 S），Dataview 会将它们视为不同的字段。

**会议笔记的复制粘贴模板：**

```yaml
---
title: ""
date: 
type: meeting
project: ""
status: done
---
```

### 方法 2：行内字段（用于快速、即时标记）

您可以使用 `key:: value` 格式在笔记正文中的任何位置添加元数据。

```
今天我读完了《**原子习惯**》。

rating:: 5
status:: read
author:: James Clear
genre:: self-help
```

当您以流畅的方式写作并希望在不回到顶部的情况下插入数据点时，行内字段会更快。双冒号 (`::`) 是 Dataview 寻找的信号。

**何时使用哪种方法：**

| 方法 | 最适合 | 限制 |
|---|---|---|
| YAML Frontmatter | 模板、结构化笔记类型 | 必须位于文件顶部 |
| 行内字段 | 随意笔记、段落中间的数据 | 对于复杂查询可靠性略低 |

每种笔记类型选择一种方法并坚持使用。在同一笔记中混合使用两种方法是有效的，但很快就会变得混乱。

---

## 您的首次查询：从零开始创建自动化列表 {#first-queries}

Dataview 查询存在于一个特殊的代码块中。您使用三个反引号和单词 `dataview` 打开它，编写您的查询，然后用三个反引号关闭。

````
```dataview
LIST FROM #meetings
```
````

这是最简单的查询。它将所有标记为 `#meetings` 的笔记显示为可点击的列表。

### 三个基本构成要素

每个 Dataview 查询都遵循以下模式：

```
[要显示什么] [从哪里获取] [如何筛选/排序]
```

在实际语法中：

```
LIST / TABLE [fields]
FROM [source]
WHERE [condition]
SORT [field] [asc/desc]
```

### 将日常语言转换为 Dataview 查询

| 您想要什么 | Dataview 查询 |
|---|---|
| 显示所有带有标签的笔记 | `LIST FROM #your-tag` |
| 显示文件夹中的所有笔记 | `LIST FROM "FolderName"` |
| 显示具有特定状态的笔记 | `LIST FROM #projects WHERE status = "active"` |
| 显示带有特定列的表格 | `TABLE author, status FROM #books` |
| 显示所有笔记中未完成的任务 | `TASK WHERE !completed` |

### 您的第一个表格

````
```dataview
TABLE date, status, project
FROM #meetings
SORT date desc
```
````

这会将所有会议笔记显示为一个包含三列——日期、状态和项目——的表格，并按最新日期排序。如果您的会议笔记具有包含这些确切字段名称的 YAML Frontmatter，则粘贴后即可立即生效。

---

## 实用“食谱”：今天即可构建的 3 个 Dataview 仪表板 {#practical-recipes}

为每个仪表板创建一篇新笔记。粘贴 Frontmatter 模板和查询，然后开始添加带有匹配元数据的笔记。

### “食谱”1：会议记录索引

**功能：** 自动列出过去 30 天的所有会议记录。

为您的会议记录创建 YAML 模板：

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

您创建的每篇新会议笔记——将其放入您的“Meetings”文件夹或标记为 `#meetings`，填写 Frontmatter——此表格都会自动更新。

### “食谱”2：图书追踪表

**功能：** 追踪您记录的每本书，包括作者、阅读状态和您的评分。

图书笔记的 Frontmatter 模板：

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

您将获得一个排名阅读清单，该清单会在您更改评分或将书籍标记为已完成时立即更新。无需电子表格。

### “食谱”3：项目中心

**功能：** 将与一个项目相关的所有笔记和未完成任务汇总到一个视图中。

````
```dataview
TABLE file.mtime as "最后修改时间", status
FROM "Projects/Alpha"
SORT file.mtime desc
```
````

在此下方，在同一个中心笔记中，添加一个任务视图：

````
```dataview
TASK
FROM "Projects/Alpha"
WHERE !completed
```
````

现在您的 Project Alpha 中心显示了该文件夹中的所有笔记以及所有未完成的复选框。这是大多数人都在尝试构建的“Obsidian 中的仪表板”用例。

如果您想深入了解如何正确构建此类系统，[Skillshare 或 Udemy 上的 PKM 和 Obsidian 课程](URL_PLACEHOLDER_3)涵盖了知识库架构，这些架构使这些查询功能更加强大。

---

## 筛选和排序：精确找到您所需的信息 {#filtering-sorting}

### WHERE 子句

`WHERE` 筛选您的结果。只有符合条件的笔记才会出现。

```
WHERE status = "in-progress"
WHERE rating >= 4
WHERE date > date(2024-01-01)
WHERE contains(tags, "work")
```

您可以组合条件：

```
WHERE status = "in-progress" AND project = "Alpha"
WHERE status = "done" OR status = "archived"
```

### SORT 子句

`SORT` 控制顺序。`asc` = A 到 Z，最旧到最新。`desc` = Z 到 A，最新到最旧。

```
SORT date desc
SORT rating asc
SORT file.mtime desc
```

`file.mtime` 是 Dataview 为每个笔记创建的内置字段——它表示“此文件上次修改的时间”。您无需将其添加到您的 Frontmatter。

### 一个完整实用的查询

以下是将所有内容组合到一个查询中的示例，该查询查找所有活跃的工作项目，显示其截止日期和所有者，并将最近修改的放在顶部：

````
```dataview
TABLE due-date, owner, status
FROM #projects
WHERE status = "active"
SORT file.mtime desc
```
````

像读一句话一样理解它：“给我一个包含截止日期、所有者和状态的表格，来自标记为 #projects 的笔记，但只显示状态等于 active 的那些，并将最近更改的放在前面。”

---

## 求助！我的查询不工作：常见错误与修复 {#troubleshooting}

### 错误 1：“Dataview：没有结果可显示”

这是最常见的问题。这意味着 Dataview 成功运行但没有找到任何匹配的笔记。

**检查清单：**

-   [ ] 查询中的标签与笔记中的标签是否完全匹配？（`#meetings` 与 `#Meetings`——区分大小写）
-   [ ] 引号中的文件夹名称是否完全匹配，包括大小写？（`"Books"` 与 `"books"`）
-   [ ] 在运行查询之前，您是否保存了包含 Frontmatter 的笔记？
-   [ ] WHERE 中的字段名称拼写是否与您的 YAML 中的字段名称完全相同？

**快速测试：** 将 `FROM #your-tag` 更改为 `FROM ""`（空字符串表示“整个知识库”）。如果出现结果，则您的标签或文件夹路径有误。

### 错误 2：查询块显示为纯文本

您在开头的反引号后缺少 `dataview` 单词，或者插件未启用。返回“设置”→“社区插件”并确认 Dataview 已打开。

### 错误 3：表格中的字段显示为“null”

该字段存在于您的查询中，但不存在于该笔记的 Frontmatter 中。要么将该字段添加到笔记中，要么在查询中添加 `WHERE field` 以排除没有该字段的笔记。

### 错误 4：文件夹路径不工作

Dataview 中的文件夹路径区分大小写，并且必须完全匹配。如果您的文件夹是 `Projects/Alpha Team`，则查询需要 `FROM "Projects/Alpha Team"`——而不是 `from "projects/alpha team"` 或 `FROM "Projects/AlphaTeam"`。

**专业提示：** 在 Obsidian 中，右键单击文件资源管理器中的文件夹并检查确切名称。将其直接复制粘贴到您的查询中。

### 错误 5：日期比较不工作

您的日期字段在 Frontmatter 中需要采用 `YYYY-MM-DD` 格式。`date: September 15, 2024` 将无法正确解析。请使用 `date: 2024-09-15`。

---

## 结论 {#conclusion}

Dataview 并非魔法，但已近乎如此。核心工作流程很简单：使用 YAML Frontmatter 为您的笔记添加一致的标签，使用 `LIST / TABLE / FROM / WHERE / SORT` 结构编写简短的查询，然后让 Dataview 为您完成维护工作。

从小处着手。本周构建图书追踪器。下周设置会议索引。一个月内，您将拥有一个能自我组织的知识库，并且您会疑惑以前没有它您是如何工作的。

早期影响最大的三件事是：Frontmatter 中一致的字段名称，将笔记放在逻辑文件夹中，以及当查询没有返回任何内容时使用故障排除清单。

**准备好更进一步了吗？**

-   深入了解使 Dataview 真正有用的 PKM 理念：[获取《打造第二大脑》](URL_PLACEHOLDER_1) 或 [《如何做卡片笔记》](URL_PLACEHOLDER_2)。
-   对于 Obsidian 和个人知识管理的结构化视频学习，[Skillshare 和 Udemy 都有专门的 Obsidian 课程](URL_PLACEHOLDER_3)，其中包含带有真实知识库示例的高级 Dataview 设置。
-   如果您希望您的组织良好的知识库在任何地方都可用，[Obsidian Sync](URL_PLACEHOLDER_4) 是官方的端到端加密选项——您的 Dataview 仪表板在每台设备上都功能相同。

从一个查询开始。一切都将随之而来。

---

## 常见问题

### 问：我需要懂编程才能使用 Dataview 吗？

不需要。基本的查询语言 (DQL) 读起来几乎就像普通的英语。本指南中的示例不需要任何编程背景。唯一的“高级”选项——DataviewJS——使用 JavaScript，但您无需接触它即可完成大多数实际用例。

### 问：Dataview 会让我的 Obsidian 知识库变慢吗？

对于少于 1,000 篇笔记的知识库，您不会注意到任何问题。对于非常大的知识库（5,000+ 篇笔记），没有 `FROM` 筛选器的复杂查询——这意味着它们会扫描每个文件——可能会导致轻微的延迟。将查询范围限定到特定文件夹或标签可以保持速度。

### 问：Dataview 标签和 Obsidian 标签有什么区别？

它们是相同的标签。您的笔记正文或 Frontmatter 中的 `#meetings` 与 Obsidian 在标签面板中显示的标签是相同的。Dataview 读取 Obsidian 的原生标签——您不需要单独的系统。

### 问：我可以在不同设备上使用 Dataview 和 Obsidian Sync 吗？

可以。[Obsidian Sync](URL_PLACEHOLDER_4) 会同步您的整个知识库，包括 Dataview 插件和您的所有笔记。您的仪表板在移动设备、平板电脑和任何其他设备上都功能齐全。查询在每台设备上本地运行，而不是在云端。

### 问：为什么我应该使用 YAML Frontmatter 而不仅仅依赖文件夹和标签？

标签和文件夹回答了“这篇笔记在哪里？”。Frontmatter 回答了“这篇笔记是关于什么的，以及它有哪些属性？”。一篇书籍笔记可以放在“Books”文件夹中，并且标记为 `#books`——但只有 Frontmatter 才能告诉 Dataview 这本特定的书评分为 4 星，于 3 月 3 日完成，并且状态为“已读”。这正是筛选和排序真正有用的原因。

## 相关阅读

-   [什么是周期性笔记插件（以及它为何能彻底改变您的工作流程）](/zh-cn/posts/obsidian-periodic-notes-plugin-review/)
-   [什么是 Obsidian Callouts（以及它们为何能彻底改变您的工作流程）](/zh-cn/posts/how-to-use-callouts-in-obsidian-for-better-notes/)
-   [为什么您的每日笔记需要 Templater 插件](/zh-cn/posts/obsidian-templater-plugin-tutorial-for-daily-notes/)
-   [为什么您的主题是 Obsidian 中最重要的写作工具](/zh-cn/posts/best-obsidian-themes-for-writing-longform-content/)
```markdown
---
images: ["/og/how-to-use-obsidian-dataview-for-beginners.webp"]
title: "Obsidian Dataview 指南：将笔记转化为数据库"
date: 2026-04-28
slug: how-to-use-obsidian-dataview-for-beginners
description: "提供一份“食谱”，其中包含可复制粘贴的常见查询示例，适用于会议记录、项目追踪和内容日历等场景，助力初学者轻松上手。"
keywords: ["obsidian dataview examples", "dataview query language", "DQL tutorial", "obsidian dataview table", "obsidian dataview list", "obsidian dataview task query", "how to install dataview obsidian", "obsidian metadata tutorial"]
draft: false
author: "Alex Chen"
type: "informational"
tags: ["dataview", "game changer", "notes", "how to use obsidian dataview for beginners"]
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。本帖子可能包含联盟链接。_

# Obsidian Dataview 初学者指南：一步步教学，附带可复制粘贴的查询示例

---

**TL;DR 摘要**

- Dataview 使用简单、类似英语的命令，将您的 Obsidian 笔记转化为可查询的数据库——无需任何编程经验。
- 您可以通过 YAML Frontmatter 或行内字段为笔记添加“标签”（元数据），然后编写简短的查询，将这些笔记自动整理成列表和表格。
- 本指南提供了会议记录、图书追踪和项目中心的可复制粘贴“食谱”——您可以在不到 10 分钟内构建出有效的工作仪表板。

---

## 目录

1. [什么是 Dataview，以及它为何能彻底改变您的笔记管理？](#what-is-dataview)
2. [第一步：在 60 秒内安装和设置 Dataview](#installing-dataview)
3. [秘诀：如何为 Dataview 标记笔记](#tagging-notes)
4. [您的首次查询：从零开始创建自动化列表](#first-queries)
5. [实用“食谱”：今天即可构建的 3 个 Dataview 仪表板](#practical-recipes)
6. [筛选和排序：精确找到您所需的信息](#filtering-sorting)
7. [求助！我的查询不工作：常见错误与修复](#troubleshooting)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 什么是 Dataview，以及它为何能彻底改变您的笔记管理？ {#what-is-dataview}

将 Dataview 视为您知识库的自动图书管理员。您可以像往常一样写笔记，但会给它们附上小标签——状态、日期、类别。Dataview 会读取这些标签，并为您建立实时索引。每次添加新笔记时，索引都会自动更新。您再也无需手动维护项目列表或会议记录。

**使用 Dataview 之前：** 您的文件夹中有 200 篇笔记。要找到所有标记为 `#project/alpha` 的笔记，要么需要记住文件位置，要么需要运行搜索并祈祷您当天的命名保持一致。

**使用 Dataview 之后：** 一篇名为“Project Alpha Hub”的笔记会实时显示所有相关笔记的表格、其状态以及上次修改时间。您创建或更改任何内容时，它都会立即更新。

Dataview 带来的三大具体优势：

1.  **自动索引。** 一篇名为“阅读清单”的笔记，它会始终显示您知识库中所有书籍笔记，并按评分排序——设置完成后无需您再进行任何操作。
2.  **动态仪表板。** 一个每周回顾页面，可以拉取所有笔记中标记为未完成的任务，无需手动收集。
3.  **跨文件任务追踪。** 一个视图即可查看您整个知识库中所有 `- [ ]` 复选框，并可按项目或截止日期进行筛选。

如果您认真对待构建一个真正的个人知识系统，那么 [Tiago Forte 的《打造第二大脑》](URL_PLACEHOLDER_1) 和 [Sönke Ahrens 的《如何做卡片笔记》](URL_PLACEHOLDER_2) 清晰地阐述了这种结构化笔记背后的概念——这两本书都值得在本指南之外阅读。

---

## 第一步：在 60 秒内安装和设置 Dataview {#installing-dataview}

Dataview 是一个社区插件，因此您需要首先启用社区插件。

**安装步骤：**

1.  打开 Obsidian。进入 **设置**（左下角的齿轮图标）。
2.  点击左侧边栏中的 **社区插件**。
3.  如果看到“安全模式”警告，点击 **关闭安全模式**。
4.  点击 **浏览**。
5.  在搜索栏中输入 **Dataview**。
6.  点击由 **blacksmithgu** 提供的结果，然后点击 **安装**。
7.  安装完成后，点击 **启用**。

就这样——Dataview 已经运行。

**值得立即启用的两项设置：**

-   **启用 JavaScript 查询**——这解锁了 `dataviewjs` 代码块，当基本查询不足时，它能为您提供更多功能。前往“设置”→“Dataview”，然后打开此开关。您今天可能不需要它，但以后会用到。
-   **启用行内查询**——这允许您在文本行内运行微型查询，例如在句子中嵌入实时笔记计数。同样在“设置”→“Dataview”中。

其他设置保持默认。您可以稍后探索其他设置，但对于初学者来说，当他们按照教程操作却出现问题时，通常是这两个设置出了错。

---

## 秘诀：如何为 Dataview 标记笔记 {#tagging-notes}

Dataview 只能报告它能读取的内容。这意味着您的笔记需要元数据——Dataview 可以找到和筛选的结构化信息。将元数据想象成文件档案上的便利贴标签。

有两种方法可以添加元数据。

### 方法 1：YAML Frontmatter（推荐用于结构化笔记）

YAML Frontmatter 位于笔记的最顶部，在两组三条破折号之间。这是最可靠的方法，并且适用于所有 Dataview 查询类型。

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

每行都是一个 `key: value` 对。您定义键——Dataview 读取它们。名称由您选择；只需保持一致。如果您在一个笔记中称之为 `status`，而在另一个笔记中称之为 `Status`（大写 S），Dataview 会将它们视为不同的字段。

**会议笔记的复制粘贴模板：**

```yaml
---
title: ""
date: 
type: meeting
project: ""
status: done
---
```

### 方法 2：行内字段（用于快速、即时标记）

您可以使用 `key:: value` 格式在笔记正文中的任何位置添加元数据。

```
今天我读完了《**原子习惯**》。

rating:: 5
status:: read
author:: James Clear
genre:: self-help
```

当您以流畅的方式写作并希望在不回到顶部的情况下插入数据点时，行内字段会更快。双冒号 (`::`) 是 Dataview 寻找的信号。

**何时使用哪种方法：**

| 方法 | 最适合 | 限制 |
|---|---|---|
| YAML Frontmatter | 模板、结构化笔记类型 | 必须位于文件顶部 |
| 行内字段 | 随意笔记、段落中间的数据 | 对于复杂查询可靠性略低 |

每种笔记类型选择一种方法并坚持使用。在同一笔记中混合使用两种方法是有效的，但很快就会变得混乱。

---

## 您的首次查询：从零开始创建自动化列表 {#first-queries}

Dataview 查询存在于一个特殊的代码块中。您使用三个反引号和单词 `dataview` 打开它，编写您的查询，然后用三个反引号关闭。

````
```dataview
LIST FROM #meetings
```
````

这是最简单的查询。它将所有标记为 `#meetings` 的笔记显示为可点击的列表。

### 三个基本构成要素

每个 Dataview 查询都遵循以下模式：

```
[要显示什么] [从哪里获取] [如何筛选/排序]
```

在实际语法中：

```
LIST / TABLE [fields]
FROM [source]
WHERE [condition]
SORT [field] [asc/desc]
```

### 将日常语言转换为 Dataview 查询

| 您想要什么 | Dataview 查询 |
|---|---|
| 显示所有带有标签的笔记 | `LIST FROM #your-tag` |
| 显示所有笔记在文件夹 | `LIST FROM "FolderName"` |
| 显示具有特定状态的笔记 | `LIST FROM #projects WHERE status = "active"` |
| 显示带有特定列的表格 | `TABLE author, status FROM #books` |
| 显示所有笔记中未完成的任务 | `TASK WHERE !completed` |

### 您的第一个表格

````
```dataview
TABLE date, status, project
FROM #meetings
SORT date desc
```
````

这会将所有会议笔记显示为一个包含三列——日期、状态和项目——的表格，并按最新日期排序。如果您的会议笔记具有包含这些确切字段名称的 YAML Frontmatter，则粘贴后即可立即生效。

---

## 实用“食谱”：今天即可构建的 3 个 Dataview 仪表板 {#practical-recipes}

为每个仪表板创建一篇新笔记。粘贴 Frontmatter 模板和查询，然后开始添加带有匹配元数据的笔记。

### “食谱”1：会议记录索引

**功能：** 自动列出过去 30 天的所有会议记录。

为您的会议记录创建 YAML 模板：

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

您创建的每篇新会议笔记——将其放入您的“Meetings”文件夹或标记为 `#meetings`，填写 Frontmatter——此表格都会自动更新。

### “食谱”2：图书追踪表

**功能：** 追踪您记录的每本书，包括作者、阅读状态和您的评分。

图书笔记的 Frontmatter 模板：

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

您将获得一个排名阅读清单，该清单会在您更改评分或将书籍标记为已完成时立即更新。无需电子表格。

### “食谱”3：项目中心

**功能：** 将与一个项目相关的所有笔记和未完成任务汇总到一个视图中。

````
```dataview
TABLE file.mtime as "最后修改时间", status
FROM "Projects/Alpha"
SORT file.mtime desc
```
````

在此下方，在同一个中心笔记中，添加一个任务视图：

````
```dataview
TASK
FROM "Projects/Alpha"
WHERE !completed
```
````

现在您的 Project Alpha 中心显示了该文件夹中的所有笔记以及所有未完成的复选框。这是大多数人都在尝试构建的“Obsidian 中的仪表板”用例。

如果您想深入了解如何正确构建此类系统，[Skillshare 或 Udemy 上的 PKM 和 Obsidian 课程](URL_PLACEHOLDER_3)涵盖了知识库架构，这些架构使这些查询功能更加强大。

---

## 筛选和排序：精确找到您所需的信息 {#filtering-sorting}

### WHERE 子句

`WHERE` 筛选您的结果。只有符合条件的笔记才会出现。

```
WHERE status = "in-progress"
WHERE rating >= 4
WHERE date > date(2024-01-01)
WHERE contains(tags, "work")
```

您可以组合条件：

```
WHERE status = "in-progress" AND project = "Alpha"
WHERE status = "done" OR status = "archived"
```

### SORT 子句

`SORT` 控制顺序。`asc` = A 到 Z，最旧到最新。`desc` = Z 到 A，最新到最旧。

```
SORT date desc
SORT rating asc
SORT file.mtime desc
```

`file.mtime` 是 Dataview 为每个笔记创建的内置字段——它表示“此文件上次修改的时间”。您无需将其添加到您的 Frontmatter。

### 一个完整实用的查询

以下是将所有内容组合到一个查询中的示例，该查询查找所有活跃的工作项目，显示其截止日期和所有者，并将最近修改的放在顶部：

````
```dataview
TABLE due-date, owner, status
FROM #projects
WHERE status = "active"
SORT file.mtime desc
```
````

像读一句话一样理解它：“给我一个包含截止日期、所有者和状态的表格，来自标记为 #projects 的笔记，但只显示状态等于 active 的那些，并将最近更改的放在前面。”

---

## 求助！我的查询不工作：常见错误与修复 {#troubleshooting}

### 错误 1：“Dataview：没有结果可显示”

这是最常见的问题。这意味着 Dataview 成功运行但没有找到任何匹配的笔记。

**检查清单：**

-   [ ] 查询中的标签与笔记中的标签是否完全匹配？（`#meetings` 与 `#Meetings`——区分大小写）
-   [ ] 引号中的文件夹名称是否完全匹配，包括大小写？（`"Books"` 与 `"books"`)
-   [ ] 在运行查询之前，您是否保存了包含 Frontmatter 的笔记？
-   [ ] WHERE 中的字段名称拼写是否与您的 YAML 中的字段名称完全相同？

**快速测试：** 将 `FROM #your-tag` 更改为 `FROM ""`（空字符串表示“整个知识库”）。如果出现结果，则您的标签或文件夹路径有误。

### 错误 2：查询块显示为纯文本

您在开头的反引号后缺少 `dataview` 单词，或者插件未启用。返回“设置”→“社区插件”并确认 Dataview 已打开。

### 错误 3：表格中的字段显示为“null”

该字段存在于您的查询中，但不存在于该笔记的 Frontmatter 中。要么将该字段添加到笔记中，要么在查询中添加 `WHERE field` 以排除没有该字段的笔记。

### 错误 4：文件夹路径不工作

Dataview 中的文件夹路径区分大小写，并且必须完全匹配。如果您的文件夹是 `Projects/Alpha Team`，则查询需要 `FROM "Projects/Alpha Team"`——而不是 `from "projects/alpha team"` 或 `FROM "Projects/AlphaTeam"`。

**专业提示：** 在 Obsidian 中，右键单击文件资源管理器中的文件夹并检查确切名称。将其直接复制粘贴到您的查询中。

### 错误 5：日期比较不工作

您的日期字段在 Frontmatter 中需要采用 `YYYY-MM-DD` 格式。`date: September 15, 2024` 将无法正确解析。请使用 `date: 2024-09-15`。

---

## 结论 {#conclusion}

Dataview 并非魔法，但已近乎如此。核心工作流程很简单：使用 YAML Frontmatter 为您的笔记添加一致的标签，使用 `LIST / TABLE / FROM / WHERE / SORT` 结构编写简短的查询，然后让 Dataview 为您完成维护工作。

从小处着手。本周构建图书追踪器。下周设置会议索引。一个月内，您将拥有一个能自我组织的知识库，并且您会疑惑以前没有它您是如何工作的。

早期影响最大的三件事是：Frontmatter 中一致的字段名称，将笔记放在逻辑文件夹中，以及当查询没有返回任何内容时使用故障排除清单。

**准备好更进一步了吗？**

-   深入了解使 Dataview 真正有用的 PKM 理念：[获取《打造第二大脑》](URL_PLACEHOLDER_1) 或 [《如何做卡片笔记》](URL_PLACEHOLDER_2)。
-   对于 Obsidian 和个人知识管理的结构化视频学习，[Skillshare 和 Udemy 都有专门的 Obsidian 课程](URL_PLACEHOLDER_3)，其中包含带有真实知识库示例的高级 Dataview 设置。
-   如果您希望您的组织良好的知识库在任何地方都可用，[Obsidian Sync](URL_PLACEHOLDER_4) 是官方的端到端加密选项——您的 Dataview 仪表板在每台设备上都功能齐全。

从一个查询开始。一切都将随之而来。

---

## 常见问题

### 问：我需要懂编程才能使用 Dataview 吗？

不需要。基本的查询语言 (DQL) 读起来几乎就像普通的英语。本指南中的示例不需要任何编程背景。唯一的“高级”选项——DataviewJS——使用 JavaScript，但您无需接触它即可完成大多数实际用例。

### 问：Dataview 会让我的 Obsidian 知识库变慢吗？

对于少于 1,000 篇笔记的知识库，您不会注意到任何问题。对于非常大的知识库（5,000+ 篇笔记），没有 `FROM` 筛选器的复杂查询——这意味着它们会扫描每个文件——可能会导致轻微的延迟。将查询范围限定到特定文件夹或标签可以保持速度。

### 问：Dataview 标签和 Obsidian 标签有什么区别？

它们是相同的标签。您的笔记正文或 Frontmatter 中的 `#meetings` 与 Obsidian 在标签面板中显示的标签是相同的。Dataview 读取 Obsidian 的原生标签——您不需要单独的系统。

### 问：我可以在不同设备上使用 Dataview 和 Obsidian Sync 吗？

可以。[Obsidian Sync](URL_PLACEHOLDER_4) 会同步您的整个知识库，包括 Dataview 插件和您的所有笔记。您的仪表板在移动设备、平板电脑和任何其他设备上都功能齐全。查询在每台设备上本地运行，而不是在云端。

### 问：为什么我应该使用 YAML Frontmatter 而不仅仅依赖文件夹和标签？

标签和文件夹回答了“这篇笔记在哪里？”。Frontmatter 回答了“这篇笔记是关于什么的，以及它有哪些属性？”。一篇书籍笔记可以放在“Books”文件夹中，并且标记为 `#books`——但只有 Frontmatter 才能告诉 Dataview 这本特定的书评分为 4 星，于 3 月 3 日完成，并且状态为“已读”。这正是筛选和排序真正有用的原因。

## 相关阅读

-   [什么是周期性笔记插件（以及它为何能彻底改变您的工作流程）](/zh-cn/posts/obsidian-periodic-notes-plugin-review/)
-   [什么是 Obsidian Callouts（以及它们为何能彻底改变您的工作流程）](/zh-cn/posts/how-to-use-callouts-in-obsidian-for-better-notes/)
-   [为什么您的每日笔记需要 Templater 插件](/zh-cn/posts/obsidian-templater-plugin-tutorial-for-daily-notes/)
-   [为什么您的主题是 Obsidian 中最重要的写作工具](/zh-cn/posts/best-obsidian-themes-for-writing-longform-content/)
```