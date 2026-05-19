I will now translate the provided Markdown article from English to Simplified Chinese (zh-cn), adhering to all specified requirements, including preserving frontmatter structure, translating only designated fields, maintaining Markdown formatting, avoiding translation of technical terms and code, remapping internal links, and ensuring a professional tone.
---
images: ["/og/templater-plugin-tutorial-for-obsidian-power-users.webp"]
title: "Obsidian 高级用户专属：Templater 插件教程，实现高级自动化"
description: "通过这份高级教程掌握 Obsidian 的 Templater 插件。学习自动化工作流程、使用 Javascript 片段以及构建复杂的笔记模板。"
pubDate: "2026-05-01"
author: "Obsidian Power User"
tags: ["obsidian", "templater", "automation", "productivity"]
slug: "templater-plugin-tutorial-for-obsidian-power-users"
type: "informational"
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Obsidian 高级用户专属：Templater 插件教程，实现高级自动化

> **快速回答：** Templater 插件将 Obsidian 从一个静态文本编辑器转变为一个自动化知识系统。通过利用其执行命令（`<%* %>`）、系统模块（`tp.file`、`tp.date`）和 Javascript 功能，高级用户可以直接在笔记中自动化文件路由、生成动态元数据、提示用户输入并从外部 API 拉取数据。

对于大多数 Obsidian 用户来说，核心 Templates 插件是避免重复输入的温和入门。它处理静态文本插入和基本的日期戳。然而，当你的个人知识管理 (PKM) 系统增长到数千条笔记时，静态模板就会成为瓶颈。你最终会花费更多时间管理元数据、将文件移动到正确的文件夹以及格式化链接，而不是实际写作或思考。

这就是 Templater 插件从根本上改变你与 Obsidian 交互方式的地方。它不仅仅是一个文本扩展器；它是一个在你的保管库中运行的成熟自动化引擎。

这份针对 Obsidian 高级用户的 Templater 插件教程将跳过基本的“如何插入日期”课程。相反，我们将直接深入探讨高级 Javascript 执行、动态文件路由、复杂逻辑以及构建在笔记创建时自动运行的模块化工作流程。

## 为什么核心模板不足以满足高级用户的需求

原生的 Obsidian Templates 插件仅限于简单的字符串替换（`{{title}}`、`{{date}}`、`{{time}}`）。它无法评估逻辑、与文件系统交互或在笔记创建过程中向你提问。

作为高级用户，你的工作流程可能需要：
- 自动将新创建的“会议笔记”移动到 `Meetings/2026/05` 目录。
- 在创建项目仪表板时，提示你从下拉菜单中选择“项目状态”。
- 根据星期几或笔记所在的文件夹有条件地插入文本。
- 通过外部 API 获取实时数据，例如天气或日历事件。

Templater 通过其强大的 API 和 Javascript 执行上下文处理所有这些。它允许你编写实际代码，在触发模板的确切时刻执行，从而生成动态的、上下文感知的笔记，这些笔记会自行构建。

## 为高级工作流程设置 Templater

在深入研究复杂的脚本之前，你必须配置 Templater 以实现最大的灵活性。限制性的设置会导致执行脚本静默失败。

### 启用 Javascript 执行

要释放 Templater 的真正潜力，你必须允许它运行 Javascript。
1. 导航到 **设置 > Templater**。
2. 向下滚动到 **User System Command Execution**（用户系统命令执行）和 **Enable User System Command Execution**（启用用户系统命令执行）开关。打开此选项。
3. 如果你计划使用保存在保管库中的自定义脚本，请配置 **Script files folder location**（脚本文件文件夹位置）。在你的保管库中创建一个名为 `Scripts` 或 `Templater Scripts` 的文件夹，并将此设置指向它。

### 文件夹模板和自动化

最强大的功能之一是启用 **Folder Templates**（文件夹模板）。这允许你将特定模板绑定到特定文件夹。
1. 打开 **Trigger Templater on new file creation**（在新文件创建时触发 Templater）。
2. 启用 **Enable Folder Templates**（启用文件夹模板）。
3. 添加规则：例如，将 `Meetings` 文件夹映射到 `Templates/Meeting Note.md` 模板。

现在，无论何时你在 `Meetings` 文件夹中创建新的空白笔记（或者脚本在那里创建），Templater 都会立即应用 `Meeting Note` 模板，无需任何手动干预。这完全消除了“创建笔记 -> 打开命令面板 -> 插入模板”的顺序。

## 掌握 Templater 语法和模块

Templater 使用特定的标签来区分常规文本和要执行的代码。理解这些标签之间的区别至关重要。

- `<% %>` — **插值：** 评估其中的代码并输出结果作为文本。用于日期、标题和基本的模块输出。
- `<%* %>` — **执行：** 运行 Javascript 逻辑，但 *不* 直接输出文本。用于变量声明、`if/else` 语句、API 调用和文件系统操作。
- `<%+ %>` — **动态：** 每次切换到阅读模式时动态更新。（谨慎使用，因为它可能会减慢大型笔记的渲染速度）。

### 使用 tp.date 和 tp.file 实现动态元数据

生成元数据是最常见的用例，但我们可以将其推到超出基本日期的范围。

获取完全清除非法字符的文件标题：
`<% tp.file.title.replace(/[\\/#^[\]|:]/g, '') %>`

动态计算未来或过去的日期（例如，设置创建后 7 天的审核日期）：
`Review Date: <% tp.date.now("YYYY-MM-DD", 7) %>`

获取上一个星期一的日期，适用于每周回顾模板：
`<% tp.date.weekday("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>`

### 使用 tp.system 进行用户输入和提示

将值硬编码到模板中会限制其可重用性。`tp.system` 模块允许你在模板运行时与其交互。

**使用 `tp.system.prompt` 进行文本输入：**
```javascript
<%*
let clientName = await tp.system.prompt("Client Name?");
let projectScope = await tp.system.prompt("Project Scope?");
%>
# <% clientName %> - Project Charter
**Scope:** <% projectScope %>
```

**使用 `tp.system.suggester` 进行下拉菜单：**
这对于保持一致的元数据（如状态标签）且没有拼写错误至关重要。

```javascript
<%*
const statuses = ["Backlog", "In Progress", "Review", "Completed"];
const selectedStatus = await tp.system.suggester(statuses, statuses);
%>
---
status: <% selectedStatus %>
---
```
当此模板运行时，将出现一个命令面板样式的窗口，强制你选择一个预定义的状态。

## 执行命令：`<% %>` 的力量

执行命令是 Obsidian 转换为 IDE 的地方。因为你正在编写标准 Javascript，所以你可以利用条件逻辑、循环和异步操作。

### 模板中的条件逻辑

你可能需要一个在周末和工作日行为不同的单个每日笔记模板。你可以使用 Javascript 的 `if/else` 语句，而不是维护两个单独的模板。

```javascript
<%*
const dayOfWeek = tp.date.now("dddd");
let focusText = "";

if (dayOfWeek === "Saturday" || dayOfWeek === "Sunday") {
    focusText = "Weekend! Time to disconnect and recharge.";
} else {
    focusText = "Workday. Check your task manager and prioritize top 3 items.";
}
%>
### Daily Focus
<% focusText %>
```

### 自动移动创建的文件

PKM 最令人沮丧的一个方面是文件夹卫生。如果你通过快速添加快捷方式创建笔记，它通常会落在根目录中。Templater 可以在文件创建时根据其标题或属性自动将文件移动到正确的目录。

在执行块中使用 `tp.file.move` 函数。

```javascript
<%*
// Prompt for the project name
let projectName = await tp.system.prompt("Enter Project Name");

// Rename the file to include the project name
await tp.file.rename(projectName + " - Planning");

// Move the file to the active projects directory
await tp.file.move("Projects/Active/" + projectName + " - Planning");
%>
```

当你在保管库根目录中对新的无标题笔记触发此模板时，它将提示你输入名称，重命名文件，并立即将其传送到你的 `Projects/Active` 文件夹中。

## 构建复杂的每日笔记模板

让我们将这些概念组合成一个高级用户的每日笔记模板。此模板将：
1. 动态生成昨天和明天的链接。
2. 提示你输入“每日意图”。
3. 检查是否是星期一，如果是，则自动生成“每周回顾”部分。
4. 自动将文件移动到年/月文件夹结构中，如果文件夹不存在则创建。

```javascript
<%*
// 1. Setup Variables and Folder Structure
const year = tp.date.now("YYYY");
const month = tp.date.now("MM-MMMM");
const targetFolder = `Journal/${year}/${month}`;

// Move file to the correct year/month folder
await tp.file.move(`${targetFolder}/${tp.file.title}`);

// 2. User Input
const intention = await tp.system.prompt("What is your main intention for today?");

// 3. Conditional Weekly Review
const dayOfWeek = tp.date.now("dddd");
let weeklyReviewSection = "";
if (dayOfWeek === "Monday") {
    weeklyReviewSection = `
## 🔄 Weekly Kickoff
- [ ] Review last week's completed tasks
- [ ] Schedule deep work blocks
- [ ] Process inbox to zero
`;
}
%>
---
date: <% tp.date.now("YYYY-MM-DD") %>
type: daily
intention: "<% intention %>"
---

# <% tp.file.title %>

<< [[<% tp.date.now("YYYY-MM-DD", -1) %>|昨天]] | [[<% tp.date.now("YYYY-MM-DD", 1) %>|明天]] >>

## 🎯 Daily Intention
> <% intention %>

<% weeklyReviewSection %>

## 📝 Notes & Observations
-

## ✅ Tasks
- [ ]
```

这个单一模板取代了手动文件夹导航、手动元数据输入以及针对不同星期几的多个单独模板。

## 通过 Templater 用户脚本集成外部 API

对于绝对的高级用户，Templater 允许你在外部 `.js` 文件中编写自己的自定义 Javascript 函数，并在模板中调用它们。这就是你将 Obsidian 连接到外部世界的方式。

1. 在你配置的 `Scripts` 文件夹中，创建一个名为 `weather.js` 的文件。
2. 编写一个与 Node.js 兼容的脚本来获取数据：

```javascript
async function getWeather(city) {
    try {
        const response = await fetch(`https://wttr.in/${city}?format=%C+%t`);
        const data = await response.text();
        return data.trim();
    } catch (error) {
        return "Weather unavailable";
    }
}
module.exports = getWeather;
```

3. 在你的 Obsidian 模板中，使用 `tp.user` 模块调用此自定义脚本：

```markdown
### Morning Status
**Weather:** <% await tp.user.weather("London") %>
```

当模板运行时，Templater 会执行外部脚本，连接到 API，并将实时天气数据直接注入到你的 Markdown 文件中。你可以使用相同的方法从 Google Calendar API 拉取日历事件，从 Readwise 获取最新阅读文章，或从 Todoist 同步任务。

## 结论

Obsidian 的原生功能非常强大，但掌握 Templater 插件弥合了被动文本存储库和主动思想操作系统之间的鸿沟。通过利用执行命令（`<%* %>`）、条件逻辑、系统提示和自定义用户脚本，你可以自动化文件管理和元数据格式化的摩擦。

首先为你最常见的笔记类型实施文件夹模板，然后逐渐引入 `tp.system.suggester` 以标准化你的标签。随着你对 Javascript 越来越熟悉，你会发现 Obsidian 中几乎所有工作流程瓶颈都可以通过精心设计的 Templater 脚本来解决。

## 常见问题

### 为什么我的 Templater 脚本显示为原始代码而不是执行？
这通常是因为你没有在设置中启用“Trigger Templater on new file creation”（在新文件创建时触发 Templater），或者你正在使用核心 Templates 热键而不是 Templater 热键。确保你正在使用 `Templater: Open Insert Template modal` 来触发执行。

### Templater 可以修改笔记中的现有文本吗？
Templater 主要设计用于在光标位置或文件创建时进行插入。虽然你可以使用 `tp.file.content` 模块读取当前文件，但通过编程方式修改现有文本更适合 MetaEdit、Linter 等插件，或编写自定义 Obsidian 脚本。

### `<% %>` 和 `<%* %>` 有什么区别？
标准的 `<% %>` 标签用于插值——它评估代码并将输出打印到笔记中（例如插入日期）。`<%* %>` 标签用于执行——它在后台运行 Javascript 逻辑（例如移动文件或定义变量），但除非通过 `tR += "string"` 明确告知，否则不会在屏幕上打印任何内容。

### Templater 在 Obsidian 移动端上可用吗？
是的，Templater 在 iOS 和 Android 上都可用。但是，依赖特定 Node.js 模块或大量文件系统操作的复杂脚本可能会由于移动操作系统的沙盒限制而表现不同或执行速度较慢。坚持使用标准 `tp` 模块以获得最大的移动兼容性。

### 如何调试失败的 Templater 脚本？
如果脚本失败，请按 `Ctrl + Shift + I`（Mac 上为 `Cmd + Option + I`）打开 Obsidian 开发者控制台。Templater 将在那里输出详细的错误消息，指出你的脚本或模板中导致 Javascript 执行中断的确切行。

---

## 相关阅读

- [Obsidian 高效学术研究插件：5 大最佳工具](/zh-cn/posts/top-5-obsidian-plugins-for-academic-research/)

- [浏览 Obsidian 主题的两种方式：应用内与网页版](/zh-cn/posts/obsidian-theme-store-browser/)

- [2026 年最佳 Obsidian Tasks 插件设置：完整指南](/zh-cn/posts/best-obsidian-tasks-plugin-setup-2026/)
- [Obsidian 日历插件完整指南：基于时间的笔记](/zh-cn/posts/obsidian-calendar-plugin-for-time-based-notes/)