---
images: ["/og/obsidian-templater-plugin-tutorial-for-daily-notes.webp"]
title: "Obsidian Templater 插件：自动化你的每日笔记"
author: "Alex Chen"
date: 2026-04-28
slug: obsidian-templater-plugin-tutorial-for-daily-notes
description: "提供一个可下载的“每日笔记入门包”，包含初级、中级和高级三种模板：初级、中级和高级，用户可立即上手实践。"
keywords: ["obsidian daily note template", "how to use templater in obsidian", "obsidian automation", "templater dynamic commands", "obsidian periodic notes setup", "tp.date.now format", "obsidian journal template", "templater user functions"]
draft: false
type: "informational"
tags: ["daily", "notes", "need", "templater"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# Obsidian Templater 插件每日笔记教程：完整分步指南

**TL;DR**
- 核心 Templates 插件是静态的；Templater 在笔记创建时运行 JavaScript，让你自动拉取实时日期、天气、引用和 Dataview 任务列表。
- 本指南将引导你完成安装，提供三个级别的可复制粘贴每日笔记模板（初级 → 中级 → 高级），并编写你的第一个 User Function 来调用外部 API。
- 这里的每个代码片段都已准备好投入生产，并在 Obsidian 1.5+ 中经过测试；你可以在 20 分钟内完成每日笔记自动化设置。

---

## 目录

1. [为什么你的每日笔记需要 Templater 插件](#why)
2. [第 1 步：安装和基本配置](#installation)
3. [第 2 步：构建你的第一个每日笔记模板](#first-template)
4. [强大每日笔记的核心 Templater 函数](#core-functions)
5. [高级工作流：创建每日仪表盘](#advanced)
6. [通过用户脚本和函数进一步探索](#user-scripts)
7. [常见问题排查](#troubleshooting)
8. [对比表格：核心 Templates 与 Templater](#comparison)
9. [常见问题](#faq)
10. [总结](#conclusion)

---

## 为什么你的每日笔记需要 Templater 插件 {#why}

Obsidian 自带一个内置的 Templates 插件。它能工作，对于静态的样板内容——这里一个标题，那里一个项目符号——来说，这很好。但当你需要任何*动态变化*的内容时，它就捉襟见肘了。

以下是核心插件无法实现的功能：

- 动态插入今天的日期（你必须手动输入或使用 {{date}} 短代码，但它只支持一种格式）
- 自动链接到昨天的笔记或下周的回顾
- 在笔记打开时提示你输入
- 获取外部数据——引用、天气、任务
- 执行任何逻辑

**Templater** ([从社区插件安装](URL_PLACEHOLDER_1)) 弥补了所有这些空白。它提供了一个基于 JavaScript 的完整脚本环境，在新文件创建时或你明确调用时运行。结果是文档中称之为*动态命令*：评估为真实内容而非硬编码字符串的占位符。

实际上，Templater 每日笔记可以：

- 自动插入格式正确的日期并链接到正确的周回顾笔记
- 使用 Dataview 查询从你的全部库中拉取今天的任务
- 问候你一个从公共 API 获取的随机斯多葛主义引用
- 询问你今天的首要任务是什么，并将你的答案嵌入到笔记中
- 生成一个预填充未选中复选框的习惯追踪网格

所有这些都不需要你成为开发者。你只需编写一些模板标签，可能还有一个简短的 JavaScript 函数，Templater 会处理其余部分。

---

## 第 1 步：安装和基本配置 {#installation}

### 安装 Templater

1. 打开 Obsidian → **设置** → **社区插件** → 如果出现提示，请关闭安全模式。
2. 点击**浏览**，搜索 **Templater**，安装，然后**启用**。

就是这样。但在你编写任何模板标签之前，花五分钟进行配置——这将为你省去日后的数小时困惑。

### 需要配置的关键设置

导航到 **设置 → Templater**。

**模板文件夹位置**
将其设置为一个专用文件夹，例如 `_templates`。此文件夹内的任何内容都被视为模板源，而不是普通笔记。保持一致。

**在新文件创建时触发模板**
启用此开关。然后，在**文件夹模板**下，将特定文件夹映射到特定模板。例如：

| 文件夹 | 模板 |
|---|---|
| `Daily Notes` | `_templates/daily-note.md` |
| `Meetings` | `_templates/meeting.md` |

现在，无论何时你在 `Daily Notes/` 中创建文件，Templater 都会自动注入你的模板。无需手动调用。

**启用系统命令**
仅当你计划运行 shell 脚本时才打开此选项。对于此处涵盖的每日笔记工作流，请将其关闭——你暂时不需要这个安全入口。

### 将 Templater 与 Periodic Notes 连接

[Periodic Notes](URL_PLACEHOLDER_2) 是一个社区插件，用于处理每日日记的*导航*方面——创建具有一致文件名的今天的笔记，链接到每周/每月对应的笔记。Templater 处理这些文件*内部的内容*。它们共同构成了每个严肃的 Obsidian 日记设置的核心。

安装 Periodic Notes，然后配置：

- **每日笔记格式**：`YYYY-MM-DD`（保持文件名可排序）
- **每日笔记文件夹**：`Daily Notes`
- **模板**：在 Periodic Notes 中留空；让 Templater 的文件夹映射来处理它

这种分离意味着 Periodic Notes 控制文件命名，而 Templater 控制内容——职责划分清晰。

---

## 第 2 步：构建你的第一个每日笔记模板 {#first-template}

在 `_templates/daily-note-beginner.md` 创建一个新文件并粘贴以下内容：

```markdown
---
date: <% tp.date.now("YYYY-MM-DD") %>
tags: daily-note
---

# <% tp.file.title %>

## 📅 今日速览
**日期：** <% tp.date.now("dddd, MMMM Do YYYY") %>

## ✅ 任务
- [ ] 

## 📝 笔记

## 🌙 睡前反思

```

### 每个标签的作用

**`<% tp.file.title %>`** — 插入文件名（不含扩展名）作为笔记标题。由于 Periodic Notes 将文件命名为 `2025-07-14`，你的 H1 将自动变为 `# 2025-07-14`。

**`<% tp.date.now("YYYY-MM-DD") %>`** — 插入当前日期，格式为 `2025-07-14`。格式字符串遵循 [Moment.js 约定](URL_PLACEHOLDER_3)：`YYYY` = 4 位年份，`MM` = 2 位月份，`DD` = 2 位日期。

**`<% tp.date.now("dddd, MMMM Do YYYY") %>`** — 生成一个可读的字符串，如 `Monday, July 14th 2025`。用于显示；在 frontmatter 中使用 ISO 格式，Dataview 将解析它。

这就是初级模板。打开今天的每日笔记，并从命令面板运行 **Templater: 替换活动文件中的模板** 来测试它。

---

## 强大每日笔记的核心 Templater 函数 {#core-functions}

### 日期模块 (tp.date)

日期模块是 Templater 中每日笔记最常用的部分。

```javascript
// 今天
<% tp.date.now("YYYY-MM-DD") %>

// 昨天（用于链接到上一篇笔记）
<% tp.date.now("YYYY-MM-DD", -1) %>

// 明天
<% tp.date.now("YYYY-MM-DD", 1) %>

// 本周一（用于周笔记链接）
<% tp.date.now("YYYY-[W]WW", 0, tp.file.title, "YYYY-MM-DD") %>
```

完整的签名是 `tp.date.now(format, offset, reference, referenceFormat)`。`reference/referenceFormat` 对至关重要：它告诉 Templater *相对于文件标题*计算日期，而不是相对于今天。这意味着如果你在周二填写一份回溯的笔记，你仍然会得到正确的日期。

### 使用文件和文件夹 (tp.file)

```javascript
// 链接到昨天的每日笔记
[[<% tp.date.now("YYYY-MM-DD", -1) %>]]

// 链接到本周回顾笔记
[[<% tp.date.now("[Week] WW - YYYY") %>]]

// 将此文件移动到正确的日期子文件夹
<% await tp.file.move("/Daily Notes/" + tp.file.title) %>
```

`tp.file.move()` 调用在你的 Periodic Notes 插件未处理文件夹组织时很有用。注意 `await`——任何进行 I/O 的函数都需要它。

### 添加动态内容 (tp.web)

Templater 有一个内置的 web 模块。最直接有用的函数是：

```javascript
// 来自 quotable.io 的随机引用
<%* 
  const response = await tp.obsidian.requestUrl({url: "https://api.quotable.io/random"});
  const data = response.json;
  tR += `> "${data.content}"\n> — ${data.author}`;
%>
```

请注意 `<%*` 开头标签——这是一个*执行*块，它运行代码但只输出你明确添加到 `tR` 中的内容。`tR` 变量是模板的输出缓冲区。

### 交互式模板 (tp.system.prompt)

这个功能被低估了，但非常实用：

```javascript
<%* 
  const priority = await tp.system.prompt("What is your #1 priority today?");
  tR += `**🎯 首要任务：** ${priority}`;
%>
```

当模板运行时，Obsidian 会弹出一个文本字段。你的答案将直接嵌入到笔记中。设置完成后无需再输入。

---

## 高级工作流：创建每日仪表盘 {#advanced}

这是中级/高级模板。将其完整复制到 `_templates/daily-note-advanced.md` 中。

```markdown
---
date: <% tp.date.now("YYYY-MM-DD") %>
created: <% tp.date.now("YYYY-MM-DDTHH:mm") %>
week: <% tp.date.now("WW") %>
tags: daily-note
---

# <% tp.file.title %>
**<% tp.date.now("dddd, MMMM Do YYYY") %>** · [[<% tp.date.now("[Week] WW - YYYY") %>|周 <% tp.date.now("WW") %> 回顾]]

---
<%*
  const priority = await tp.system.prompt("🎯 你今天的首要任务是什么？");
  tR += `> **首要任务：** ${priority}\n`;
%>

---

## 📋 今日任务

```dataview
task
from ""
where !completed and due = date("<% tp.date.now("YYYY-MM-DD") %>")
```

## 🔁 习惯追踪器

| 习惯 | 完成了吗？ |
|---|---|
| 晨间散步 | [ ] |
| 阅读 20 页 | [ ] |
| 上午 9 点前不玩手机 | [ ] |
| 查看收件箱 | [ ] |

## 📝 笔记与思考

## 🔗 日志
- ← 昨天：[[<% tp.date.now("YYYY-MM-DD", -1) %>]]
- → 明天：[[<% tp.date.now("YYYY-MM-DD", 1) %>]]

---
<%*
  const response = await tp.obsidian.requestUrl({url: "https://api.quotable.io/random"});
  const data = response.json;
  tR += `## 💬 每日语录\n> "${data.content}"\n> — **${data.author}**`;
%>

## 🌙 晚间反思
**进展顺利的是什么？**

**如果重来我会怎么做？**

**感恩：**
```

Dataview 块在笔记打开时渲染一个实时任务列表。如果你还没有安装 [Dataview 插件](URL_PLACEHOLDER_4)，请安装它——它是 Templater 的另一个重要伴侣。

如果你想在设备之间同步此设置，[Obsidian Sync](URL_PLACEHOLDER_5) 可以让你的库——模板、插件、设置——在每台机器上保持一致，无需第三方服务。

---

## 通过用户脚本和函数进一步探索 {#user-scripts}

### 什么是用户函数？

用户函数是存储在指定文件夹中的 JavaScript 文件。Templater 会导入它们，并使其在任何模板中可调用。它们让你能够执行 JavaScript 可以做的任何事情：调用外部 API、进行数学计算、操作字符串、格式化数据。

### 分步指南：获取天气数据

**1. 在设置中启用用户脚本**

设置 → Templater → **脚本文件文件夹位置** → 设置为 `_scripts`。

**2. 创建 `_scripts/getWeather.js`**

```javascript
async function getWeather(city) {
  const apiKey = "YOUR_OPENWEATHERMAP_KEY"; // 免费层级即可正常工作
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;
  
  try {
    const response = await fetch(url);
    const data = await response.json();
    const temp = Math.round(data.main.temp);
    const desc = data.weather[0].description;
    return `${temp}°C, ${desc}`;
  } catch (e) {
    return "天气数据不可用";
  }
}

module.exports = getWeather;
```

在 [OpenWeatherMap](URL_PLACE_HOLDER_6) 获取免费 API 密钥。免费层级允许每分钟 60 次调用——对于每日笔记来说绰绰有余。

**3. 在你的模板中调用它**

```javascript
<%*
  const weather = await tp.user.getWeather("London");
  tR += `**🌤 天气：** ${weather}`;
%>
```

添加新的脚本文件后，重新启动 Obsidian，以便 Templater 重新索引它们。

### 使用 Webhook 推送外部数据

对于更复杂的集成——例如拉取今天的 Google Calendar 事件，从项目管理工具导入行动项——可以考虑将 Obsidian 与 [Make.com](URL_PLACEHOLDER_7) 或 [Zapier](URL_PLACEHOLDER_8) 搭配使用。这些服务可以监视外部触发器，将数据格式化为 Markdown，并使用 [Obsidian Local REST API 插件](URL_PLACEHOLDER_9)将其推送到你的库中。然后，每日笔记模板从 Make.com 已经填充的暂存文件读取。这是一个更复杂的设置，但它消除了重复信息的完全手动数据输入。

---

## 常见问题排查 {#troubleshooting}

**文件创建时模板未触发**
检查文件夹模板映射是否精确。`Daily Notes` ≠ `daily notes`——Obsidian 文件夹名称是区分大小写的。还要确认模板文件位于你配置的模板文件夹*内*，而不是你的笔记文件夹。

**“Unexpected identifier”或语法错误**
这几乎总是意味着 `<%` / `%>` 对不匹配，或异步函数缺少 `await`。检查每个使用 `await` 的 `<%*` 块在函数调用前是否都有它。Templater 的错误消息会出现在开发者控制台 (Ctrl+Shift+I / Cmd+Option+I)。

**`tp.web` 函数不起作用**
内置的 `tp.web` 模块（特别是 `tp.web.daily_quote()`）在某些版本中已被弃用。请改用 `tp.obsidian.requestUrl()`，如上面代码片段所示——它使用 Obsidian 自己的 HTTP 客户端并绕过 CORS 限制。

**旧笔记被覆盖**
如果你不小心在现有文件上触发了模板，请立即使用 Ctrl+Z。若要在旧笔记上故意重新运行模板，请使用 **Templater: 替换活动文件中的模板**——但请注意，它会覆盖找到的任何 `<% %>` 标签，而不是整个文件。

---

## 对比表格：核心 Templates 与 Templater {#comparison}

| 功能 | 核心 Templates 插件 | Templater |
|---|---|---|
| 静态文本插入 | ✅ | ✅ |
| 当前日期/时间 | ✅ (格式有限) | ✅ (完整 Moment.js) |
| 昨天/明天日期 | ❌ | ✅ |
| 提示用户输入 | ❌ | ✅ |
| 获取外部 API | ❌ | ✅ |
| 条件逻辑 (if/else) | ❌ | ✅ |
| 自定义 JavaScript 函数 | ❌ | ✅ |
| 文件夹自动触发 | ❌ | ✅ |
| 链接到相关周期性笔记 | ❌ | ✅ |
| 学习曲线 | 低 | 中 |

核心插件对于带有静态标题的会议笔记来说很好。但对于你每天都会打开的每日笔记，Templater 的投入会立即得到回报。

---

## 总结 {#conclusion}

核心 Templates 插件就像一张便利贴。Templater 则是一个文档组装系统。对于每日笔记——你每天创建、每晚回顾、每周挖掘洞察的文件——这种差异会迅速放大。

从初级模板开始，熟悉 `tp.date.now()` 和 `tp.file.title`，然后放入高级仪表盘。一旦运行起来，花一个下午编写一个用户函数，你就会看到实时天气或每日斯多葛主义引用无需动手即可出现。

像 [Building a Second Brain](URL_PLACEHOLDER_10) 这样的课程中教授的生产力系统将每日笔记视为你的知识实践的基本单元。Templater 确保该单元从第一天起就保持一致、丰富和自动化——因此你将认知预算花在思考上，而不是格式化上。

**准备好将此付诸实践了吗？**
- [安装 Templater](URL_PLACEHOLDER_1) 并立即遵循第 1 步——只需不到 5 分钟。
- [设置 Obsidian Sync](URL_PLACEHOLDER_5) 以使你的模板和脚本在所有设备上保持一致。
- 如果你想要包含外部数据的完整自动化堆栈，[注册一个免费的 Make.com 帐户](URL_PLACEHOLDER_7) 并将其连接到你的库。

本指南中的模板已可复制粘贴。剩下的就是打开 Obsidian 并创建今天的笔记。

---

## 常见问题

### Templater 与 QuickAdd 插件有什么区别？

QuickAdd 主要是一个*捕获*工具——通过菜单快速将任务、笔记或条目添加到现有文件。Templater 是一个*格式化*引擎，在创建时转换新文件。它们相辅相成：使用 QuickAdd 快速将日志条目附加到今天的每日笔记，使用 Templater 定义创建时的每日笔记外观。许多高级用户同时运行这两个插件。

### 我可以同时使用 Templater 和 Periodic Notes 插件吗？

是的，这是推荐的设置。配置 Periodic Notes 处理文件创建（命名约定、文件夹位置），并让 Templater 的文件夹模板处理内容注入。在 Periodic Notes 插件本身中禁用模板设置，以避免冲突。

### 如果我在模板中出现语法错误，Templater 会破坏我的库吗？

不会。一个损坏的模板会抛出错误通知，并留下空文件或部分填充的文件。你的库本身不会受到影响。在实验时，将工作模板备份到单独的文件夹中——或者使用 [Obsidian Sync](URL_PLACEHOLDER_5)，它维护版本历史。

### 如何以我的本地语言格式化日期？

Moment.js（Templater 内部使用）支持区域感知的格式化。在模板顶部添加 `<%* moment.locale('de'); %>`（将 'de' 替换为你的区域代码），然后使用 `tp.date.now("dddd")` 获取本地化的一周中的日名称。

### 有没有办法每天早上自动运行模板而无需手动打开 Obsidian？

Templater 无法唤醒你的电脑，但它可以在 Obsidian 打开的那一刻自动创建今天的笔记。启用 **Periodic Notes → 在启动时打开每日笔记** 并结合 Templater 的文件夹触发器。笔记将在 Obsidian 启动的几秒钟内创建并应用模板。对于真正自动化的数据摄入（预取日历事件、天气），请与按计划运行的 [Make.com](URL_PLACEHOLDER_7) 搭配使用。

## 相关阅读

- [什么是 Periodic Notes 插件（以及它为何能改变游戏规则）](/zh-cn/posts/obsidian-periodic-notes-plugin-review/)
- [什么是 Dataview 以及它为何能改变你的笔记管理方式？](/zh-cn/posts/how-to-use-obsidian-dataview-for-beginners/)
- [什么是 Obsidian Full Calendar 插件？](/zh-cn/posts/obsidian-full-calendar-plugin-review/)
- [什么是 Obsidian Projects 插件（以及它适合谁？）](/zh-cn/posts/obsidian-projects-plugin-review-and-setup/)
```markdown
---
images: ["/og/obsidian-templater-plugin-tutorial-for-daily-notes.webp"]
title: "Obsidian Templater 插件：自动化你的每日笔记"
author: "Alex Chen"
date: 2026-04-28
slug: obsidian-templater-plugin-tutorial-for-daily-notes
description: "提供一个可下载的“每日笔记入门包”，包含初级、中级和高级三种模板，用户可立即上手实践。"
keywords: ["obsidian daily note template", "how to use templater in obsidian", "obsidian automation", "templater dynamic commands", "obsidian periodic notes setup", "tp.date.now format", "obsidian journal template", "templater user functions"]
draft: false
type: "informational"
tags: ["daily", "notes", "need", "templater"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取佣金。此帖子可能包含联盟链接。_

# Obsidian Templater 插件每日笔记教程：完整分步指南

**TL;DR**
- 核心 Templates 插件是静态的；Templater 在笔记创建时运行 JavaScript，让你自动拉取实时日期、天气、引用和 Dataview 任务列表。
- 本指南将引导你完成安装，提供三个级别的可复制粘贴每日笔记模板（初级 → 中级 → 高级），并编写你的第一个 User Function 来调用外部 API。
- 这里的每个代码片段都已准备好投入生产，并在 Obsidian 1.5+ 中经过测试；你可以在 20 分钟内完成每日笔记自动化设置。

---

## 目录

1. [为什么你的每日笔记需要 Templater 插件](#why)
2. [第 1 步：安装和基本配置](#installation)
3. [第 2 步：构建你的第一个每日笔记模板](#first-template)
4. [强大每日笔记的核心 Templater 函数](#core-functions)
5. [高级工作流：创建每日仪表盘](#advanced)
6. [通过用户脚本和函数进一步探索](#user-scripts)
7. [常见问题排查](#troubleshooting)
8. [对比表格：核心 Templates 与 Templater](#comparison)
9. [常见问题](#faq)
10. [总结](#conclusion)

---

## 为什么你的每日笔记需要 Templater 插件 {#why}

Obsidian 自带一个内置的 Templates 插件。它能工作，对于静态的样板内容——这里一个标题，那里一个项目符号——来说，这很好。但当你需要任何*动态变化*的内容时，它就捉襟见肘了。

以下是核心插件无法实现的功能：

- 动态插入今天的日期（你必须手动输入或使用 {{date}} 短代码，但它只支持一种格式）
- 自动链接到昨天的笔记或下周的回顾
- 在笔记打开时提示你输入
- 获取外部数据——引用、天气、任务
- 执行任何逻辑

**Templater** ([从社区插件安装](URL_PLACEHOLDER_1)) 弥补了所有这些空白。它提供了一个基于 JavaScript 的完整脚本环境，在新文件创建时或你明确调用时运行。结果是文档中称之为*动态命令*：评估为真实内容而非硬编码字符串的占位符。

实际上，Templater 每日笔记可以：

- 自动插入格式正确的日期并链接到正确的周回顾笔记
- 使用 Dataview 查询从你的全部库中拉取今天的任务
- 问候你一个从公共 API 获取的随机斯多葛主义引用
- 询问你今天的首要任务是什么，并将你的答案嵌入到笔记中
- 生成一个预填充未选中复选框的习惯追踪网格

所有这些都不需要你成为开发者。你只需编写一些模板标签，可能还有一个简短的 JavaScript 函数，Templater 会处理其余部分。

---

## 第 1 步：安装和基本配置 {#installation}

### 安装 Templater

1. 打开 Obsidian → **设置** → **社区插件** → 如果出现提示，请关闭安全模式。
2. 点击**浏览**，搜索 **Templater**，安装，然后**启用**。

就是这样。但在你编写任何模板标签之前，花五分钟进行配置——这将为你省去日后的数小时困惑。

### 需要配置的关键设置

导航到 **设置 → Templater**。

**模板文件夹位置**
将其设置为一个专用文件夹，例如 `_templates`。此文件夹内的任何内容都被视为模板源，而不是普通笔记。保持一致。

**在新文件创建时触发模板**
启用此开关。然后，在**文件夹模板**下，将特定文件夹映射到特定模板。例如：

| 文件夹 | 模板 |
|---|---|
| `Daily Notes` | `_templates/daily-note.md` |
| `Meetings` | `_templates/meeting.md` |

现在，无论何时你在 `Daily Notes/` 中创建文件，Templater 都会自动注入你的模板。无需手动调用。

**启用系统命令**
仅当你计划运行 shell 脚本时才打开此选项。对于此处涵盖的每日笔记工作流，请将其关闭——你暂时不需要这个安全入口。

### 将 Templater 与 Periodic Notes 连接

[Periodic Notes](URL_PLACEHOLDER_2) 是一个社区插件，用于处理每日日记的*导航*方面——创建具有一致文件名的今天的笔记，链接到每周/每月对应的笔记。Templater 处理这些文件*内部的内容*。它们共同构成了每个严肃的 Obsidian 日记设置的核心。

安装 Periodic Notes，然后配置：

- **每日笔记格式**：`YYYY-MM-DD`（保持文件名可排序）
- **每日笔记文件夹**：`Daily Notes`
- **模板**：在 Periodic Notes 中留空；让 Templater 的文件夹映射来处理它

这种分离意味着 Periodic Notes 控制文件命名，而 Templater 控制内容——职责划分清晰。

---

## 第 2 步：构建你的第一个每日笔记模板 {#first-template}

在 `_templates/daily-note-beginner.md` 创建一个新文件并粘贴以下内容：

```markdown
---
date: <% tp.date.now("YYYY-MM-DD") %>
tags: daily-note
---

# <% tp.file.title %>

## 📅 今日速览
**日期：** <% tp.date.now("dddd, MMMM Do YYYY") %>

## ✅ 任务
- [ ] 

## 📝 笔记

## 🌙 睡前反思

```

### 每个标签的作用

**`<% tp.file.title %>`** — 插入文件名（不含扩展名）作为笔记标题。由于 Periodic Notes 将文件命名为 `2025-07-14`，你的 H1 将自动变为 `# 2025-07-14`。

**`<% tp.date.now("YYYY-MM-DD") %>`** — 插入当前日期，格式为 `2025-07-14`。格式字符串遵循 [Moment.js 约定](URL_PLACEHOLDER_3)：`YYYY` = 4 位年份，`MM` = 2 位月份，`DD` = 2 位日期。

**`<% tp.date.now("dddd, MMMM Do YYYY") %>`** — 生成一个可读的字符串，如 `Monday, July 14th 2025`。用于显示；在 frontmatter 中使用 ISO 格式，Dataview 将解析它。

这就是初级模板。打开今天的每日笔记，并从命令面板运行 **Templater: 替换活动文件中的模板** 来测试它。

---

## 强大每日笔记的核心 Templater 函数 {#core-functions}

### 日期模块 (tp.date)

日期模块是 Templater 中每日笔记最常用的部分。

```javascript
// 今天
<% tp.date.now("YYYY-MM-DD") %>

// 昨天（用于链接到上一篇笔记）
<% tp.date.now("YYYY-MM-DD", -1) %>

// 明天
<% tp.date.now("YYYY-MM-DD", 1) %>

// 本周一（用于周笔记链接）
<% tp.date.now("YYYY-[W]WW", 0, tp.file.title, "YYYY-MM-DD") %>
```

完整的签名是 `tp.date.now(format, offset, reference, referenceFormat)`。`reference/referenceFormat` 对至关重要：它告诉 Templater *相对于文件标题*计算日期，而不是相对于今天。这意味着如果你在周二填写一份回溯的笔记，你仍然会得到正确的日期。

### 使用文件和文件夹 (tp.file)

```javascript
// 链接到昨天的每日笔记
[[<% tp.date.now("YYYY-MM-DD", -1) %>]]

// 链接到本周回顾笔记
[[<% tp.date.now("[Week] WW - YYYY") %>]]

// 将此文件移动到正确的日期子文件夹
<% await tp.file.move("/Daily Notes/" + tp.file.title) %>
```

`tp.file.move()` 调用在你的 Periodic Notes 插件未处理文件夹组织时很有用。注意 `await`——任何进行 I/O 的函数都需要它。

### 添加动态内容 (tp.web)

Templater 有一个内置的 web 模块。最直接有用的函数是：

```javascript
// 来自 quotable.io 的随机引用
<%* 
  const response = await tp.obsidian.requestUrl({url: "https://api.quotable.io/random"});
  const data = response.json;
  tR += `> "${data.content}"\n> — ${data.author}`;
%>
```

请注意 `<%*` 开头标签——这是一个*执行*块，它运行代码但只输出你明确添加到 `tR` 中的内容。`tR` 变量是模板的输出缓冲区。

### 交互式模板 (tp.system.prompt)

这个功能被低估了，但非常实用：

```javascript
<%* 
  const priority = await tp.system.prompt("What is your #1 priority today?");
  tR += `**🎯 首要任务：** ${priority}`;
%>
```

当模板运行时，Obsidian 会弹出一个文本字段。你的答案将直接嵌入到笔记中。设置完成后无需再输入。

---

## 高级工作流：创建每日仪表盘 {#advanced}

这是中级/高级模板。将其完整复制到 `_templates/daily-note-advanced.md` 中。

```markdown
---
date: <% tp.date.now("YYYY-MM-DD") %>
created: <% tp.date.now("YYYY-MM-DDTHH:mm") %>
week: <% tp.date.now("WW") %>
tags: daily-note
---

# <% tp.file.title %>
**<% tp.date.now("dddd, MMMM Do YYYY") %>** · [[<% tp.date.now("[Week] WW - YYYY") %>|周 <% tp.date.now("WW") %> 回顾]]

---
<%*
  const priority = await tp.system.prompt("🎯 你今天的首要任务是什么？");
  tR += `> **首要任务：** ${priority}\n`;
%>

---

## 📋 今日任务

```dataview
task
from ""
where !completed and due = date("<% tp.date.now("YYYY-MM-DD") %>")
```

## 🔁 习惯追踪器

| 习惯 | 完成了吗？ |
|---|---|
| 晨间散步 | [ ] |
| 阅读 20 页 | [ ] |
| 上午 9 点前不玩手机 | [ ] |
| 查看收件箱 | [ ] |

## 📝 笔记与思考

## 🔗 日志
- ← 昨天：[[<% tp.date.now("YYYY-MM-DD", -1) %>]]
- → 明天：[[<% tp.date.now("YYYY-MM-DD", 1) %>]]

---
<%*
  const response = await tp.obsidian.requestUrl({url: "https://api.quotable.io/random"});
  const data = response.json;
  tR += `## 💬 每日语录\n> "${data.content}"\n> — **${data.author}**`;
%>

## 🌙 晚间反思
**进展顺利的是什么？**

**如果重来我会怎么做？**

**感恩：**
```

Dataview 块在笔记打开时渲染一个实时任务列表。如果你还没有安装 [Dataview 插件](URL_PLACEHOLDER_4)，请安装它——它是 Templater 的另一个重要伴侣。

如果你想在设备之间同步此设置，[Obsidian Sync](URL_PLACEHOLDER_5) 可以让你的库——模板、插件、设置——在每台机器上保持一致，无需第三方服务。

---

## 通过用户脚本和函数进一步探索 {#user-scripts}

### 什么是用户函数？

用户函数是存储在指定文件夹中的 JavaScript 文件。Templater 会导入它们，并使其在任何模板中可调用。它们让你能够执行 JavaScript 可以做的任何事情：调用外部 API、进行数学计算、操作字符串、格式化数据。

### 分步指南：获取天气数据

**1. 在设置中启用用户脚本**

设置 → Templater → **脚本文件文件夹位置** → 设置为 `_scripts`。

**2. 创建 `_scripts/getWeather.js`**

```javascript
async function getWeather(city) {
  const apiKey = "YOUR_OPENWEATHERMAP_KEY"; // 免费层级即可正常工作
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`;
  
  try {
    const response = await fetch(url);
    const data = await response.json();
    const temp = Math.round(data.main.temp);
    const desc = data.weather[0].description;
    return `${temp}°C, ${desc}`;
  } catch (e) {
    return "天气数据不可用";
  }
}

module.exports = getWeather;
```

在 [OpenWeatherMap](URL_PLACEHOLDER_6) 获取免费 API 密钥。免费层级允许每分钟 60 次调用——对于每日笔记来说绰绰有余。

**3. 在你的模板中调用它**

```javascript
<%*
  const weather = await tp.user.getWeather("London");
  tR += `**🌤 天气：** ${weather}`;
%>
```

添加新的脚本文件后，重新启动 Obsidian，以便 Templater 重新索引它们。

### 使用 Webhook 推送外部数据

对于更复杂的集成——例如拉取今天的 Google Calendar 事件，从项目管理工具导入行动项——可以考虑将 Obsidian 与 [Make.com](URL_PLACEHOLDER_7) 或 [Zapier](URL_PLACEHOLDER_8) 搭配使用。这些服务可以监视外部触发器，将数据格式化为 Markdown，并使用 [Obsidian Local REST API 插件](URL_PLACEHOLDER_9)将其推送到你的库中。然后，每日笔记模板从 Make.com 已经填充的暂存文件读取。这是一个更复杂的设置，但它消除了重复信息的完全手动数据输入。

---

## 常见问题排查 {#troubleshooting}

**文件创建时模板未触发**
检查文件夹模板映射是否精确。`Daily Notes` ≠ `daily notes`——Obsidian 文件夹名称是区分大小写的。还要确认模板文件位于你配置的模板文件夹*内*，而不是你的笔记文件夹。

**“Unexpected identifier”或语法错误**
这几乎总是意味着 `<%` / `%>` 对不匹配，或异步函数缺少 `await`。检查每个使用 `await` 的 `<%*` 块在函数调用前是否都有它。Templater 的错误消息会出现在开发者控制台 (Ctrl+Shift+I / Cmd+Option+I)。

**`tp.web` 函数不起作用**
内置的 `tp.web` 模块（特别是 `tp.web.daily_quote()`）在某些版本中已被弃用。请改用 `tp.obsidian.requestUrl()`，如上面代码片段所示——它使用 Obsidian 自己的 HTTP 客户端并绕过 CORS 限制。

**旧笔记被覆盖**
如果你不小心在现有文件上触发了模板，请立即使用 Ctrl+Z。若要在旧笔记上故意重新运行模板，请使用 **Templater: 替换活动文件中的模板**——但请注意，它会覆盖找到的任何 `<% %>` 标签，而不是整个文件。

---

## 对比表格：核心 Templates 与 Templater {#comparison}

| 功能 | 核心 Templates 插件 | Templater |
|---|---|---|
| 静态文本插入 | ✅ | ✅ |
| 当前日期/时间 | ✅ (格式有限) | ✅ (完整 Moment.js) |
| 昨天/明天日期 | ❌ | ✅ |
| 提示用户输入 | ❌ | ✅ |
| 获取外部 API | ❌ | ✅ |
| 条件逻辑 (if/else) | ❌ | ✅ |
| 自定义 JavaScript 函数 | ❌ | ✅ |
| 文件夹自动触发 | ❌ | ✅ |
| 链接到相关周期性笔记 | ❌ | ✅ |
| 学习曲线 | 低 | 中 |

核心插件对于带有静态标题的会议笔记来说很好。但对于你每天都会打开的每日笔记，Templater 的投入会立即得到回报。

---

## 总结 {#conclusion}

核心 Templates 插件就像一张便利贴。Templater 则是一个文档组装系统。对于每日笔记——你每天创建、每晚回顾、每周挖掘洞察的文件——这种差异会迅速放大。

从初级模板开始，熟悉 `tp.date.now()` 和 `tp.file.title`，然后放入高级仪表盘。一旦运行起来，花一个下午编写一个用户函数，你就会看到实时天气或每日斯多葛主义引用无需动手即可出现。

像 [Building a Second Brain](URL_PLACEHOLDER_10) 这样的课程中教授的生产力系统将每日笔记视为你的知识实践的基本单元。Templater 确保该单元从第一天起就保持一致、丰富和自动化——因此你将认知预算花在思考上，而不是格式化上。

**准备好将此付诸实践了吗？**
- [安装 Templater](URL_PLACEHOLDER_1) 并立即遵循第 1 步——只需不到 5 分钟。
- [设置 Obsidian Sync](URL_PLACEHOLDER_5) 以使你的模板和脚本在所有设备上保持一致。
- 如果你想要包含外部数据的完整自动化堆栈，[注册一个免费的 Make.com 帐户](URL_PLACEHOLDER_7) 并将其连接到你的库。

本指南中的模板已可复制粘贴。剩下的就是打开 Obsidian 并创建今天的笔记。

---

## 常见问题

### Templater 与 QuickAdd 插件有什么区别？

QuickAdd 主要是一个*捕获*工具——通过菜单快速将任务、笔记或条目添加到现有文件。Templater 是一个*格式化*引擎，在创建时转换新文件。它们相辅相成：使用 QuickAdd 快速将日志条目附加到今天的每日笔记，使用 Templater 定义创建时的每日笔记外观。许多高级用户同时运行这两个插件。

### 我可以同时使用 Templater 和 Periodic Notes 插件吗？

是的，这是推荐的设置。配置 Periodic Notes 处理文件创建（命名约定、文件夹位置），并让 Templater 的文件夹模板处理内容注入。在 Periodic Notes 插件本身中禁用模板设置，以避免冲突。

### 如果我在模板中出现语法错误，Templater 会破坏我的库吗？

不会。一个损坏的模板会抛出错误通知，并留下空文件或部分填充的文件。你的库本身不会受到影响。在实验时，将工作模板备份到单独的文件夹中——或者使用 [Obsidian Sync](URL_PLACEHOLDER_5)，它维护版本历史。

### 如何以我的本地语言格式化日期？

Moment.js（Templater 内部使用）支持区域感知的格式化。在模板顶部添加 `<%* moment.locale('de'); %>`（将 'de' 替换为你的区域代码），然后使用 `tp.date.now("dddd")` 获取本地化的一周中的日名称。

### 有没有办法每天早上自动运行模板而无需手动打开 Obsidian？

Templater 无法唤醒你的电脑，但它可以在 Obsidian 打开的那一刻自动创建今天的笔记。启用 **Periodic Notes → 在启动时打开每日笔记** 并结合 Templater 的文件夹触发器。笔记将在 Obsidian 启动的几秒钟内创建并应用模板。对于真正自动化的数据摄入（预取日历事件、天气），请与按计划运行的 [Make.com](URL_PLACEHOLDER_7) 搭配使用。

## 相关阅读

- [什么是 Periodic Notes 插件（以及它为何能改变游戏规则）](/zh-cn/posts/obsidian-periodic-notes-plugin-review/)
- [什么是 Dataview 以及它为何能改变你的笔记管理方式？](/zh-cn/posts/how-to-use-obsidian-dataview-for-beginners/)
- [什么是 Obsidian Full Calendar 插件？](/zh-cn/posts/obsidian-full-calendar-plugin-review/)
- [什么是 Obsidian Projects 插件（以及它适合谁？）](/zh-cn/posts/obsidian-projects-plugin-review-and-setup/)
```