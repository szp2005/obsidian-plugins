---
images: ["/og/obsidian-full-calendar-plugin-review.webp"]
title: "Obsidian Full Calendar 插件评测：终极设置指南"
author: "Alex Chen"
date: 2026-04-29
slug: obsidian-full-calendar-plugin-review
description: "提供一份“从零到精通”的设置指南，不仅涵盖基础安装，还包括通常较为棘手的 CalDAV 和 Google 日历同步配置。"
keywords: ["obsidian google calendar sync", "obsidian full calendar setup", "obsidian caldav integration", "best obsidian calendar plugin", "obsidian task management workflow", "obsidian planner setup", "how to use obsidian full calendar", "obsidian time blocking"]
draft: false
type: "informational"
tags: ["obsidian", "full", "calendar", "plugin"]
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Obsidian Full Calendar 插件评测：完整设置指南与工作流程 (2024)

**一句话总结**
- Full Calendar 将 Obsidian 转化为真正的生产力中心，通过在你的库中呈现来自本地笔记、Google Calendar 和 CalDAV 源的交互式日历视图。
- 基础使用设置耗时不到 10 分钟；Google Calendar 和 CalDAV 同步需要更多工作，但回报是所有日程安排都集中在一个视图中。
- 对于需要外部日历同步的用户来说，它胜过所有替代方案——但在决定使用它之前，你需要了解它真实世界的怪癖。

---

## 目录
1. [什么是 Obsidian Full Calendar 插件？](#what-is)
2. [安装与首次设置：5 分钟指南](#installation)
3. [深入探索：掌握核心功能](#core-features)
4. [终极集成：Google Calendar 和 CalDAV 同步](#sync)
5. [3 个实用的工作流程来组织你的生活](#workflows)
6. [Full Calendar 与替代方案的对比](#comparison)
7. [常见陷阱与解决方案](#pitfalls)
8. [最终评判](#verdict)
9. [常见问题](#faq)

---

## 什么是 Obsidian Full Calendar 插件？ {#what-is}

大多数知识工作者生活在两个独立的世界中：一个用于思考的笔记应用和一个用于安排日程的日历应用。结果就是持续的上下文切换——你在 Obsidian 中查阅会议笔记，然后切换到 Google Calendar 查看时间，再切换回来。每一次切换都会让你失去专注。

由开发者 Davis Haupt (`davish`) 创建的 [Obsidian Full Calendar 插件](URL_PLACEHOLDER_1) 将这两个世界合二为一。它直接在 Obsidian 窗格内呈现一个功能齐全的 FullCalendar.js 驱动界面——包括月、周和日视图，并将 markdown 笔记视为日历事件。事件以 `.md` 文件的形式存在于你的库中，或从 Google Calendar 和任何兼容 CalDAV 的外部源同步进来。

这与原生的 [Obsidian Calendar 插件](URL_PLACEHOLDER_2) 有显著区别，后者只允许你按时间顺序导航每日笔记。Full Calendar 让你能够 *安排* 事务、拖动事件以调整时间，并从你已经使用的日历中拉取实时数据。

**谁能从中受益最大：**
- **学生** 跟踪作业截止日期、考试安排和学习时间
- **内容创作者** 运行包含草稿 → 发布流程的编辑日历
- **专业人士** 经常开会，并希望将上下文丰富的笔记直接链接到每个事件

如果你曾希望你的 PKM 系统能够兼作计划工具，而无需离开应用——这就是你的插件。如果你想深化此类设置背后的生产力方法，[David Allen 的《搞定：无压工作的艺术》](URL_PLACEHOLDER_3) 仍然是理解如何构建你的捕获和回顾周期的最清晰框架。

---

## 安装与首次设置：5 分钟指南 {#installation}

### 步骤 1：从社区插件安装

1. 打开 Obsidian → **设置** → **社区插件**
2. 如果提示，禁用安全模式
3. 点击 **浏览**，搜索 `Full Calendar`
4. 点击 **安装**，然后 **启用**

### 步骤 2：打开插件设置

导航到 **设置 → Full Calendar**。你将看到一个“日历来源”部分。这是最重要的配置屏幕——日历显示的所有内容都来自这里。

### 步骤 3：添加你的第一个本地日历来源

点击 **添加日历来源** → 选择 **本地**。将其指向你库中的一个文件夹（例如，`Calendar/Events`）。新事件将作为 markdown 文件写入此处。设置一个显示颜色（十六进制或拾色器）。点击 **保存**。

### 步骤 4：创建你的第一个事件

通过左侧功能区图标（一个小日历图标）打开 Full Calendar 视图。点击网格上的任意时间段。将出现一个模态框，要求填写：
- **标题** (必填)
- **日期和时间**
- **全天切换**
- **日历来源** (你刚刚创建的本地文件夹)

点击 **保存**。Obsidian 会立即在你选择的文件夹中创建一个 `.md` 文件，其中包含如下 Frontmatter：

```yaml
---
title: Team standup
author: "Alex Chen"
date: 2024-08-15
startTime: "09:00"
endTime: "09:30"
type: event
---
```

该笔记现在是一个日历事件。直接编辑 Frontmatter，或在日历网格上拖动事件块以重新安排它。

### 步骤 5：理解视图

- **月视图**：高级规划，适合发现截止日期密集区
- **周视图**：最适用于日常日程安排和时间区块
- **日视图**：详细的小时分解；与时间区块技术配合良好

使用日历窗格右上角的按钮切换视图。

---

## 深入探索：掌握核心功能 {#core-features}

### Frontmatter 中的事件

如果你添加了正确的 Frontmatter，任何现有笔记都会成为日历事件。这对于追溯性地安排事务非常强大。为笔记添加 `date`、`startTime` 和 `endTime`，它就会自动出现在日历上——无需重复，无需单独输入。

### 拖放重新安排

点击并按住任何事件块，然后将其拖到新的时间段。插件会自动重写 Frontmatter 的 `date` 和时间字段。这使得每周回顾变得快速：在几秒钟内将逾期任务拖到新的时间段。

### 按来源颜色编码

每个日历来源都有自己的颜色。用它来视觉上区分：
- 工作承诺 (红色)
- 个人事件 (蓝色)
- 截止日期 (橙色)
- 外部同步日历 (绿色)

你目前无法在本地来源中按单个标签进行颜色编码——颜色在来源/文件夹级别操作。如果你需要每个事件的颜色，请将事件组织到多个来源文件夹中。

### 全天事件与定时事件

为截止日期、周年纪念或多日区块切换全天选项。全天事件浮动在周视图和日视图的顶部，与定时事件分开，这使你的每小时网格保持整洁。

---

## 终极集成：与 Google Calendar 和 CalDAV 同步 {#sync}

这是 Full Calendar 将自己与所有其他 Obsidian 日历选项区分开来的地方——也是大多数设置混淆发生的地方。请仔细遵循这些步骤。

### Google Calendar 同步 (通过 iCal URL 只读)

Full Calendar 目前通过 **公共 iCal URL** 连接到 Google Calendar。这是只读的——事件从 Google 流入 Obsidian，而不是反向。

1. 打开 [Google Calendar](https://calendar.google.com) → 在左侧边栏中找到你的日历
2. 点击三点菜单 → **设置和共享**
3. 滚动到 **集成日历** → 复制 **iCal 格式的私人地址**（以 `https://calendar.google.com/calendar/ical/...` 开头的 URL）
4. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → 远程 (.ics / iCal URL)**
5. 粘贴 URL，命名，选择颜色，保存

你的 Google Calendar 事件现在出现在 Obsidian 中。当你重新打开库时，它们会刷新。**重要提示**：使用“私人地址”（私有 iCal），而不是公共地址，否则私人事件将不会出现。

### CalDAV 同步 (双向，完全读写)

要实现真正的双向同步——你可以在 Obsidian 内部创建和编辑事件，并让它们出现在你的外部日历中——你需要一个 **CalDAV 来源**。[Fastmail](URL_PLACEHOLDER_4) 是我们推荐的提供商：它注重隐私、可靠，并且其 CalDAV 实现清晰且文档完善。

**设置步骤：**

1. 在你的 CalDAV 提供商中，找到 CalDAV 服务器 URL 和你的日历特定 URL 路径
   - **Fastmail**：`https://caldav.fastmail.com/dav/principals/user/you@fastmail.com/`
   - **iCloud**：`https://caldav.icloud.com/`
2. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → CalDAV**
3. 输入：
   - **CalDAV 服务器 URL** (来自步骤 1)
   - **用户名** (通常是你的电子邮件地址)
   - **密码** (对于 iCloud，在 appleid.apple.com 生成一个应用专用密码)
4. 点击 **查找日历**——插件会查询服务器并列出可用的日历
5. 选择要同步的日历，分配颜色，保存

事件现在双向流动。在 Obsidian 中创建事件，它会在几秒钟内出现在 Fastmail 的网页界面（或你手机的日历应用）中。

---

## 3 个实用的工作流程来组织你的生活 {#workflows}

### 工作流程 1：学生作业跟踪器

**设置**：创建两个本地来源——`Deadlines`（红色）和 `Study Blocks`（蓝色）。将你大学的学术日历添加为 iCal URL 来源。

**工作原理**：每个作业都会在 `Deadlines` 中获得一个带有截止日期的笔记。使用周视图查看即将到来的截止日期，然后通过点击开放的时间段创建学习区块事件——从截止日期倒推。当你打开一个学习区块事件笔记时，使用标准的 `[[wikilinks]]` 将其直接链接到你的课程笔记。你现在拥有一个可以打开你实际学习材料的日历。

对于希望更正式地构建这种系统的用户，[Skillshare 上的此生产力课程](URL_PLACEHOLDER_5) 逐步介绍了如何从头开始构建一个完整的 PKM 系统。

### 工作流程 2：内容创作者的编辑日历

**设置**：每个内容类型一个本地来源文件夹——`Blog Posts`、`YouTube Scripts`、`Social Media`。每个都有独特的颜色。

**工作原理**：当你开始创作新作品时，将其创建为一个带有目标发布日期的事件。在 Frontmatter 中添加一个 `status` 字段（`draft`、`review`、`scheduled`、`published`）。使用月视图进行编辑规划——你可以一目了然地看到你是否在一周内集中了太多的帖子。拖动事件以重新分配。因为每个事件 *就是* 一个笔记，你的完整草稿就存在于日历条目中。

### 工作流程 3：专业人士的会议仪表板

**设置**：通过 iCal URL 同步你的工作 Google Calendar（只读）。为 Obsidian 创建的事件创建一个本地 `Meeting Notes` 来源。

**工作原理**：对于来自 Google Calendar 的每个会议，在你的本地来源中同时创建一个相应的会议笔记事件。使用模板（通过 Templater 或 QuickAdd）自动填充议程、与会者和行动项。Google Calendar 事件告诉你 *何时*；Obsidian 事件携带所有上下文。在周视图中，两者出现在同一时间段，通过颜色编码，你可以一目了然地知道哪个有相关的笔记。

---

## Full Calendar 与替代方案的对比 {#comparison}

| 功能 | Full Calendar | 原生 Calendar 插件 | Fantasy Calendar |
|---|---|---|---|
| 月/周/日视图 | ✅ 三者都有 | 仅月视图 | 仅月视图 |
| 本地笔记事件 | ✅ | ✅ (仅每日笔记) | ✅ |
| Google Calendar 同步 | ✅ (iCal 只读) | ❌ | ❌ |
| CalDAV 双向同步 | ✅ | ❌ | ❌ |
| 拖放重新安排 | ✅ | ❌ | ❌ |
| 虚构/自定义日历 | ❌ | ❌ | ✅ |
| 活跃开发 | ✅ | 缓慢 | 活跃 |
| 设置复杂性 | 中等 | 低 | 低 |

**何时选择替代方案：**
- **原生 Calendar 插件**：你只需要每日笔记导航，别无他求。零配置。
- **Fantasy Calendar**：你是一名世界构建者或小说家，需要自定义日历系统（13 个月的年份，不同的天长）。不适用于真实世界的日程安排。
- **Full Calendar**：所有其他用例，特别是涉及外部同步的任何情况。

---

## 常见陷阱与解决方案 {#pitfalls}

**问题：添加 iCal URL 后没有显示事件**
*原因*：你复制了公共日历 URL，而不是秘密 iCal URL。
*修复*：返回 Google Calendar → 设置 → “iCal 格式的私人地址”。它包含 URL 中的一个长令牌。那才是你需要使用的。

**问题：CalDAV 登录失败并显示“401 Unauthorized”**
*原因*：对于 iCloud，你的 Apple ID 密码将不起作用。CalDAV 需要一个应用专用密码。
*修复*：前往 appleid.apple.com → 登录与安全 → 应用专用密码 → 生成一个，然后在 CalDAV 字段中使用它。

**问题：编辑 Frontmatter 后事件重复**
*原因*：你移动了笔记文件到另一个文件夹，而它已经被跟踪。
*修复*：不要在来源文件夹之间手动移动事件笔记。而是在插件内部更改来源分配，然后让它协调。

**问题：使用大型库时日历视图卡顿**
*原因*：插件在加载时会扫描来源文件夹中的所有笔记。一个包含数百个旧事件的来源文件夹会拖慢速度。
*修复*：将旧事件笔记归档到未指定为日历来源的子文件夹中。保持活动来源精简（< 200 个笔记）。

**问题：同步几天后停止更新**
*原因*：iCal URL 在 Obsidian 端可能存在缓存行为。
*修复*：关闭并重新打开库，或在设置中关闭并重新打开日历来源以强制刷新。

---

## 最终评判 {#verdict}

**优点：**
- 真正的外部日历同步（唯一能很好地做到这一点的 Obsidian 插件）
- 事件是真实的笔记——可链接、可搜索、完整的 Markdown
- 拖放重新安排对于每周回顾来说确实很快
- 三种视图模式涵盖所有规划范围

**缺点：**
- Google Calendar 同步是只读的；你无法从 Obsidian 将事件推回到 Google
- CalDAV 设置需要仔细注意凭据和服务器 URL
- 颜色自定义仅限于来源级别，而非单个事件
- 对于非常大的来源文件夹，性能会下降

**总结**：如果你的工作流程涉及任何外部日历——工作、学校或个人——Full Calendar 是唯一值得使用的 Obsidian 插件。iCal 同步可在五分钟内让你完成 80% 的工作。与 [Fastmail](URL_PLACEHOLDER_4) 的 CalDAV 双向集成让你能够真正取代独立的日历应用进行日常使用。

[从社区插件浏览器安装 Full Calendar 插件](URL_PLACEHOLDER_1)，并花 20 分钟遵循上述设置指南。这笔投资将在日常使用的第一周内得到回报。

---

## 常见问题

### 问：Full Calendar 插件免费吗？

是的。它是完全开源的，采用 MIT 许可证。没有付费层级或专业版。

### 问：我可以将 Full Calendar 与 Apple Calendar (iCloud) 同步吗？

可以，通过 CalDAV。使用 `https://caldav.icloud.com/` 作为服务器 URL，并使用你的 Apple ID 设置中的应用专用密码。双向同步运行可靠。

### 问：Full Calendar 在 Obsidian 移动版上能用吗？

日历在 iOS 和 Android 上都能渲染，但由于网络权限处理，CalDAV 同步在移动设备上可能不可靠。本地事件工作正常。iCal 只读同步在大多数设置下都能正常工作。

### 问：如果我卸载插件，我的事件还会存在吗？

是的。本地事件是带有 Frontmatter 的标准 Markdown 文件。它们保留在你的库中，并且在没有插件的情况下也可以完全读取。外部 CalDAV 事件不会本地存储。

### 问：这与使用 Obsidian 内置的每日笔记日历有什么不同？

内置日历插件只允许你按日期导航到每日笔记——它不显示事件，不允许安排，也没有外部同步。Full Calendar 是一个独立、功能更强大的系统，它将笔记视为可安排的事件，具有时间、拖放和实时同步功能。

## 相关阅读

- [什么是 Obsidian Projects 插件（以及它适合谁用）](/zh-cn/posts/obsidian-projects-plugin-review-and-setup/)
- [什么是 Obsidian Git 插件？（简单解释）](/zh-cn/posts/what-is-the-obsidian-git-plugin-for/)
- [什么是 Excalidraw 以及为什么要在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建一个 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
---
images: ["/og/obsidian-full-calendar-plugin-review.webp"]
title: "Obsidian Full Calendar 插件评测：终极设置指南"
author: "Alex Chen"
date: 2026-04-29
slug: obsidian-full-calendar-plugin-review
description: "提供一份“从零到精通”的设置指南，不仅涵盖基础安装，还包括通常较为棘手的 CalDAV 和 Google 日历同步配置。"
keywords: ["obsidian google calendar sync", "obsidian full calendar setup", "obsidian caldav integration", "best obsidian calendar plugin", "obsidian task management workflow", "obsidian planner setup", "how to use obsidian full calendar", "obsidian time blocking"]
draft: false
type: "informational"
tags: ["obsidian", "full", "calendar", "plugin"]
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Obsidian Full Calendar 插件评测：完整设置指南与工作流程 (2024)

**一句话总结**
- Full Calendar 将 Obsidian 转化为真正的生产力中心，通过在你的库中呈现来自本地笔记、Google Calendar 和 CalDAV 源的交互式日历视图。
- 基础使用设置耗时不到 10 分钟；Google Calendar 和 CalDAV 同步需要更多工作，但回报是所有日程安排都集中在一个视图中。
- 对于需要外部日历同步的用户来说，它胜过所有替代方案——但在决定使用它之前，你需要了解它真实世界的怪癖。

---

## 目录
1. [什么是 Obsidian Full Calendar 插件？](#what-is)
2. [安装与首次设置：5 分钟指南](#installation)
3. [深入探索：掌握核心功能](#core-features)
4. [终极集成：Google Calendar 和 CalDAV 同步](#sync)
5. [3 个实用的工作流程来组织你的生活](#workflows)
6. [Full Calendar 与替代方案的对比](#comparison)
7. [常见陷阱与解决方案](#pitfalls)
8. [最终评判](#verdict)
9. [常见问题](#faq)

---

## 什么是 Obsidian Full Calendar 插件？ {#what-is}

大多数知识工作者生活在两个独立的世界中：一个用于思考的笔记应用和一个用于安排日程的日历应用。结果就是持续的上下文切换——你在 Obsidian 中查阅会议笔记，然后切换到 Google Calendar 查看时间，再切换回来。每一次切换都会让你失去专注。

由开发者 Davis Haupt (`davish`) 创建的 [Obsidian Full Calendar 插件](URL_PLACEHOLDER_1) 将这两个世界合二为一。它直接在 Obsidian 窗格内呈现一个功能齐全的 FullCalendar.js 驱动界面——包括月、周和日视图，并将 markdown 笔记视为日历事件。事件以 `.md` 文件的形式存在于你的库中，或从 Google Calendar 和任何兼容 CalDAV 的外部源同步进来。

这与原生的 [Obsidian Calendar 插件](URL_PLACEHOLDER_2) 有显著区别，后者只允许你按时间顺序导航每日笔记。Full Calendar 让你能够 *安排* 事务、拖动事件以调整时间，并从你已经使用的日历中拉取实时数据。

**谁能从中受益最大：**
- **学生** 跟踪作业截止日期、考试安排和学习时间
- **内容创作者** 运行包含草稿 → 发布流程的编辑日历
- **专业人士** 经常开会，并希望将上下文丰富的笔记直接链接到每个事件

如果你曾希望你的 PKM 系统能够兼作计划工具，而无需离开应用——这就是你的插件。如果你想深化此类设置背后的生产力方法，[David Allen 的《搞定：无压工作的艺术》](URL_PLACEHOLDER_3) 仍然是理解如何构建你的捕获和回顾周期的最清晰框架。

---

## 安装与首次设置：5 分钟指南 {#installation}

### 步骤 1：从社区插件安装

1. 打开 Obsidian → **设置** → **社区插件**
2. 如果提示，禁用安全模式
3. 点击 **浏览**，搜索 `Full Calendar`
4. 点击 **安装**，然后 **启用**

### 步骤 2：打开插件设置

导航到 **设置 → Full Calendar**。你将看到一个“日历来源”部分。这是最重要的配置屏幕——日历显示的所有内容都来自这里。

### 步骤 3：添加你的第一个本地日历来源

点击 **添加日历来源** → 选择 **本地**。将其指向你库中的一个文件夹（例如，`Calendar/Events`）。新事件将作为 markdown 文件写入此处。设置一个显示颜色（十六进制或拾色器）。点击 **保存**。

### 步骤 4：创建你的第一个事件

通过左侧功能区图标（一个小日历图标）打开 Full Calendar 视图。点击网格上的任意时间段。将出现一个模态框，要求填写：
- **标题** (必填)
- **日期和时间**
- **全天切换**
- **日历来源** (你刚刚创建的本地文件夹)

点击 **保存**。Obsidian 会立即在你选择的文件夹中创建一个 `.md` 文件，其中包含如下 Frontmatter：

```yaml
---
title: Team standup
author: "Alex Chen"
date: 2024-08-15
startTime: "09:00"
endTime: "09:30"
type: event
---
```

该笔记现在是一个日历事件。直接编辑 Frontmatter，或在日历网格上拖动事件块以重新安排它。

### 步骤 5：理解视图

- **月视图**：高级规划，适合发现截止日期密集区
- **周视图**：最适用于日常日程安排和时间区块
- **日视图**：详细的小时分解；与时间区块技术配合良好

使用日历窗格右上角的按钮切换视图。

---

## 深入探索：掌握核心功能 {#core-features}

### Frontmatter 中的事件

如果你添加了正确的 Frontmatter，任何现有笔记都会成为日历事件。这对于追溯性地安排事务非常强大。为笔记添加 `date`、`startTime` 和 `endTime`，它就会自动出现在日历上——无需重复，无需单独输入。

### 拖放重新安排

点击并按住任何事件块，然后将其拖到新的时间段。插件会自动重写 Frontmatter 的 `date` 和时间字段。这使得每周回顾变得快速：在几秒钟内将逾期任务拖到新的时间段。

### 按来源颜色编码

每个日历来源都有自己的颜色。用它来视觉上区分：
- 工作承诺 (红色)
- 个人事件 (蓝色)
- 截止日期 (橙色)
- 外部同步日历 (绿色)

你目前无法在本地来源中按单个标签进行颜色编码——颜色在来源/文件夹级别操作。如果你需要每个事件的颜色，请将事件组织到多个来源文件夹中。

### 全天事件与定时事件

为截止日期、周年纪念或多日区块切换全天选项。全天事件浮动在周视图和日视图的顶部，与定时事件分开，这使你的每小时网格保持整洁。

---

## 终极集成：与 Google Calendar 和 CalDAV 同步 {#sync}

这是 Full Calendar 将自己与所有其他 Obsidian 日历选项区分开来的地方——也是大多数设置混淆发生的地方。请仔细遵循这些步骤。

### Google Calendar 同步 (通过 iCal URL 只读)

Full Calendar 目前通过 **公共 iCal URL** 连接到 Google Calendar。这是只读的——事件从 Google 流入 Obsidian，而不是反向。

1. 打开 [Google Calendar](https://calendar.google.com) → 在左侧边栏中找到你的日历
2. 点击三点菜单 → **设置和共享**
3. 滚动到 **集成日历** → 复制 **iCal 格式的私人地址**（以 `https://calendar.google.com/calendar/ical/...` 开头的 URL）
4. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → 远程 (.ics / iCal URL)**
5. 粘贴 URL，命名，选择颜色，保存

你的 Google Calendar 事件现在出现在 Obsidian 中。当你重新打开库时，它们会刷新。**重要提示**：使用“私人地址”（私有 iCal），而不是公共地址，否则私人事件将不会出现。

### CalDAV 同步 (双向，完全读写)

要实现真正的双向同步——你可以在 Obsidian 内部创建和编辑事件，并让它们出现在你的外部日历中——你需要一个 **CalDAV 来源**。[Fastmail](URL_PLACEHOLDER_4) 是我们推荐的提供商：它注重隐私、可靠，并且其 CalDAV 实现清晰且文档完善。

**设置步骤：**

1. 在你的 CalDAV 提供商中，找到 CalDAV 服务器 URL 和你的日历特定 URL 路径
   - **Fastmail**：`https://caldav.fastmail.com/dav/principals/user/you@fastmail.com/`
   - **iCloud**：`https://caldav.icloud.com/`
2. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → CalDAV**
3. 输入：
   - **CalDAV 服务器 URL** (来自步骤 1)
   - **用户名** (通常是你的电子邮件地址)
   - **密码** (对于 iCloud，在 appleid.apple.com 生成一个应用专用密码)
4. 点击 **查找日历**——插件会查询服务器并列出可用的日历
5. 选择要同步的日历，分配颜色，保存

事件现在双向流动。在 Obsidian 中创建事件，它会在几秒钟内出现在 Fastmail 的网页界面（或你手机的日历应用）中。

---

## 3 个实用的工作流程来组织你的生活 {#workflows}

### 工作流程 1：学生作业跟踪器

**设置**：创建两个本地来源——`Deadlines`（红色）和 `Study Blocks`（蓝色）。将你大学的学术日历添加为 iCal URL 来源。

**工作原理**：每个作业都会在 `Deadlines` 中获得一个带有截止日期的笔记。使用周视图查看即将到来的截止日期，然后通过点击开放的时间段创建学习区块事件——从截止日期倒推。当你打开一个学习区块事件笔记时，使用标准的 `[[wikilinks]]` 将其直接链接到你的课程笔记。你现在拥有一个可以打开你实际学习材料的日历。

对于希望更正式地构建这种系统的用户，[Skillshare 上的此生产力课程](URL_PLACEHOLDER_5) 逐步介绍了如何从头开始构建一个完整的 PKM 系统。

### 工作流程 2：内容创作者的编辑日历

**设置**：每个内容类型一个本地来源文件夹——`Blog Posts`、`YouTube Scripts`、`Social Media`。每个都有独特的颜色。

**工作原理**：当你开始创作新作品时，将其创建为一个带有目标发布日期的事件。在 Frontmatter 中添加一个 `status` 字段（`draft`、`review`、`scheduled`、`published`）。使用月视图进行编辑规划——你可以一目了然地看到你是否在一周内集中了太多的帖子。拖动事件以重新分配。因为每个事件 *就是* 一个笔记，你的完整草稿就存在于日历条目中。

### 工作流程 3：专业人士的会议仪表板

**设置**：通过 iCal URL 同步你的工作 Google Calendar（只读）。为 Obsidian 创建的事件创建一个本地 `Meeting Notes` 来源。

**工作原理**：对于来自 Google Calendar 的每个会议，在你的本地来源中同时创建一个相应的会议笔记事件。使用模板（通过 Templater 或 QuickAdd）自动填充议程、与会者和行动项。Google Calendar 事件告诉你 *何时*；Obsidian 事件携带所有上下文。在周视图中，两者出现在同一时间段，通过颜色编码，你可以一目了然地知道哪个有相关的笔记。

---

## Full Calendar 与替代方案的对比 {#comparison}

| 功能 | Full Calendar | 原生 Calendar 插件 | Fantasy Calendar |
|---|---|---|---|
| 月/周/日视图 | ✅ 三者都有 | 仅月视图 | 仅月视图 |
| 本地笔记事件 | ✅ | ✅ (仅每日笔记) | ✅ |
| Google Calendar 同步 | ✅ (iCal 只读) | ❌ | ❌ |
| CalDAV 双向同步 | ✅ | ❌ | ❌ |
| 拖放重新安排 | ✅ | ❌ | ❌ |
| 虚构/自定义日历 | ❌ | ❌ | ✅ |
| 活跃开发 | ✅ | 缓慢 | 活跃 |
| 设置复杂性 | 中等 | 低 | 低 |

**何时选择替代方案：**
- **原生 Calendar 插件**：你只需要每日笔记导航，别无他求。零配置。
- **Fantasy Calendar**：你是一名世界构建者或小说家，需要自定义日历系统（13 个月的年份，不同的天长）。不适用于真实世界的日程安排。
- **Full Calendar**：所有其他用例，特别是涉及外部同步的任何情况。

---

## 常见陷阱与解决方案 {#pitfalls}

**问题：添加 iCal URL 后没有显示事件**
*原因*：你复制了公共日历 URL，而不是秘密 iCal URL。
*修复*：返回 Google Calendar → 设置 → “iCal 格式的私人地址”。它包含 URL 中的一个长令牌。那才是你需要使用的。

**问题：CalDAV 登录失败并显示“401 Unauthorized”**
*原因*：对于 iCloud，你的 Apple ID 密码将不起作用。CalDAV 需要一个应用专用密码。
*修复*：前往 appleid.apple.com → 登录与安全 → 应用专用密码 → 生成一个，然后在 CalDAV 字段中使用它。

**问题：编辑 Frontmatter 后事件重复**
*原因*：你移动了笔记文件到另一个文件夹，而它已经被跟踪。
*修复*：不要在来源文件夹之间手动移动事件笔记。而是在插件内部更改来源分配，然后让它协调。

**问题：使用大型库时日历视图卡顿**
*原因*：插件在加载时会扫描来源文件夹中的所有笔记。一个包含数百个旧事件的来源文件夹会拖慢速度。
*修复*：将旧事件笔记归档到未指定为日历来源的子文件夹中。保持活动来源精简（< 200 个笔记）。

**问题：同步几天后停止更新**
*原因*：iCal URL 在 Obsidian 端可能存在缓存行为。
*修复*：关闭并重新打开库，或在设置中关闭并重新打开日历来源以强制刷新。

---

## 最终评判 {#verdict}

**优点：**
- 真正的外部日历同步（唯一能很好地做到这一点的 Obsidian 插件）
- 事件是真实的笔记——可链接、可搜索、完整的 Markdown
- 拖放重新安排对于每周回顾来说确实很快
- 三种视图模式涵盖所有规划范围

**缺点：**
- Google Calendar 同步是只读的；你无法从 Obsidian 将事件推回到 Google
- CalDAV 设置需要仔细注意凭据和服务器 URL
- 颜色自定义仅限于来源级别，而非单个事件
- 对于非常大的来源文件夹，性能会下降

**总结**：如果你的工作流程涉及任何外部日历——工作、学校或个人——Full Calendar 是唯一值得使用的 Obsidian 插件。iCal 同步可在五分钟内让你完成 80% 的工作。与 [Fastmail](URL_PLACEHOLDER_4) 的 CalDAV 双向集成让你能够真正取代独立的日历应用进行日常使用。

[从社区插件浏览器安装 Full Calendar 插件](URL_PLACEHOLDER_1)，并花 20 分钟遵循上述设置指南。这笔投资将在日常使用的第一周内得到回报。

---

## 常见问题

### 问：Full Calendar 插件免费吗？

是的。它是完全开源的，采用 MIT 许可证。没有付费层级或专业版。

### 问：我可以将 Full Calendar 与 Apple Calendar (iCloud) 同步吗？

可以，通过 CalDAV。使用 `https://caldav.icloud.com/` 作为服务器 URL，并使用你的 Apple ID 设置中的应用专用密码。双向同步运行可靠。

### 问：Full Calendar 在 Obsidian 移动版上能用吗？

日历在 iOS 和 Android 上都能渲染，但由于网络权限处理，CalDAV 同步在移动设备上可能不可靠。本地事件工作正常。iCal 只读同步在大多数设置下都能正常工作。

### 问：如果我卸载插件，我的事件还会存在吗？

是的。本地事件是带有 Frontmatter 的标准 Markdown 文件。它们保留在你的库中，并且在没有插件的情况下也可以完全读取。外部 CalDAV 事件不会本地存储。

### 问：这与使用 Obsidian 内置的每日笔记日历有什么不同？

内置日历插件只允许你按日期导航到每日笔记——它不显示事件，不允许安排，也没有外部同步。Full Calendar 是一个独立、功能更强大的系统，它将笔记视为可安排的事件，具有时间、拖放和实时同步功能。

## 相关阅读

- [什么是 Obsidian Projects 插件（以及它适合谁用）](/zh-cn/posts/obsidian-projects-plugin-review-and-setup/)
- [什么是 Obsidian Git 插件？（简单解释）](/zh-cn/posts/what-is-the-obsidian-git-plugin-for/)
- [什么是 Excalidraw 以及为什么要在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建一个 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
```markdown
---
images: ["/og/obsidian-full-calendar-plugin-review.webp"]
title: "Obsidian Full Calendar 插件评测：终极设置指南"
author: "Alex Chen"
date: 2026-04-29
slug: obsidian-full-calendar-plugin-review
description: "提供一份“从零到精通”的设置指南，不仅涵盖基础安装，还包括通常较为棘手的 CalDAV 和 Google 日历同步配置。"
keywords: ["obsidian google calendar sync", "obsidian full calendar setup", "obsidian caldav integration", "best obsidian calendar plugin", "obsidian task management workflow", "obsidian planner setup", "how to use obsidian full calendar", "obsidian time blocking"]
draft: false
type: "informational"
tags: ["obsidian", "full", "calendar", "plugin"]
---

_作为亚马逊联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Obsidian Full Calendar 插件评测：完整设置指南与工作流程 (2024)

**一句话总结**
- Full Calendar 将 Obsidian 转化为真正的生产力中心，通过在你的库中呈现来自本地笔记、Google Calendar 和 CalDAV 源的交互式日历视图。
- 基础使用设置耗时不到 10 分钟；Google Calendar 和 CalDAV 同步需要更多工作，但回报是所有日程安排都集中在一个视图中。
- 对于需要外部日历同步的用户来说，它胜过所有替代方案——但在决定使用它之前，你需要了解它真实世界的怪癖。

---

## 目录
1. [什么是 Obsidian Full Calendar 插件？](#what-is)
2. [安装与首次设置：5 分钟指南](#installation)
3. [深入探索：掌握核心功能](#core-features)
4. [终极集成：Google Calendar 和 CalDAV 同步](#sync)
5. [3 个实用的工作流程来组织你的生活](#workflows)
6. [Full Calendar 与替代方案的对比](#comparison)
7. [常见陷阱与解决方案](#pitfalls)
8. [最终评判](#verdict)
9. [常见问题](#faq)

---

## 什么是 Obsidian Full Calendar 插件？ {#what-is}

大多数知识工作者生活在两个独立的世界中：一个用于思考的笔记应用和一个用于安排日程的日历应用。结果就是持续的上下文切换——你在 Obsidian 中查阅会议笔记，然后切换到 Google Calendar 查看时间，再切换回来。每一次切换都会让你失去专注。

由开发者 Davis Haupt (`davish`) 创建的 [Obsidian Full Calendar 插件](URL_PLACEHOLDER_1) 将这两个世界合二为一。它直接在 Obsidian 窗格内呈现一个功能齐全的 FullCalendar.js 驱动界面——包括月、周和日视图，并将 markdown 笔记视为日历事件。事件以 `.md` 文件的形式存在于你的库中，或从 Google Calendar 和任何兼容 CalDAV 的外部源同步进来。

这与原生的 [Obsidian Calendar 插件](URL_PLACEHOLDER_2) 有显著区别，后者只允许你按时间顺序导航每日笔记。Full Calendar 让你能够 *安排* 事务、拖动事件以调整时间，并从你已经使用的日历中拉取实时数据。

**谁能从中受益最大：**
- **学生** 跟踪作业截止日期、考试安排和学习时间
- **内容创作者** 运行包含草稿 → 发布流程的编辑日历
- **专业人士** 经常开会，并希望将上下文丰富的笔记直接链接到每个事件

如果你曾希望你的 PKM 系统能够兼作计划工具，而无需离开应用——这就是你的插件。如果你想深化此类设置背后的生产力方法，[David Allen 的《搞定：无压工作的艺术》](URL_PLACEHOLDER_3) 仍然是理解如何构建你的捕获和回顾周期的最清晰框架。

---

## 安装与首次设置：5 分钟指南 {#installation}

### 步骤 1：从社区插件安装

1. 打开 Obsidian → **设置** → **社区插件**
2. 如果提示，禁用安全模式
3. 点击 **浏览**，搜索 `Full Calendar`
4. 点击 **安装**，然后 **启用**

### 步骤 2：打开插件设置

导航到 **设置 → Full Calendar**。你将看到一个“日历来源”部分。这是最重要的配置屏幕——日历显示的所有内容都来自这里。

### 步骤 3：添加你的第一个本地日历来源

点击 **添加日历来源** → 选择 **本地**。将其指向你库中的一个文件夹（例如，`Calendar/Events`）。新事件将作为 markdown 文件写入此处。设置一个显示颜色（十六进制或拾色器）。点击 **保存**。

### 步骤 4：创建你的第一个事件

通过左侧功能区图标（一个小日历图标）打开 Full Calendar 视图。点击网格上的任意时间段。将出现一个模态框，要求填写：
- **标题** (必填)
- **日期和时间**
- **全天切换**
- **日历来源** (你刚刚创建的本地文件夹)

点击 **保存**。Obsidian 会立即在你选择的文件夹中创建一个 `.md` 文件，其中包含如下 Frontmatter：

```yaml
---
title: Team standup
author: "Alex Chen"
date: 2024-08-15
startTime: "09:00"
endTime: "09:30"
type: event
---
```

该笔记现在是一个日历事件。直接编辑 Frontmatter，或在日历网格上拖动事件块以重新安排它。

### 步骤 5：理解视图

- **月视图**：高级规划，适合发现截止日期密集区
- **周视图**：最适用于日常日程安排和时间区块
- **日视图**：详细的小时分解；与时间区块技术配合良好

使用日历窗格右上角的按钮切换视图。

---

## 深入探索：掌握核心功能 {#core-features}

### Frontmatter 中的事件

如果你添加了正确的 Frontmatter，任何现有笔记都会成为日历事件。这对于追溯性地安排事务非常强大。为笔记添加 `date`、`startTime` 和 `endTime`，它就会自动出现在日历上——无需重复，无需单独输入。

### 拖放重新安排

点击并按住任何事件块，然后将其拖到新的时间段。插件会自动重写 Frontmatter 的 `date` 和时间字段。这使得每周回顾变得快速：在几秒钟内将逾期任务拖到新的时间段。

### 按来源颜色编码

每个日历来源都有自己的颜色。用它来视觉上区分：
- 工作承诺 (红色)
- 个人事件 (蓝色)
- 截止日期 (橙色)
- 外部同步日历 (绿色)

你目前无法在本地来源中按单个标签进行颜色编码——颜色在来源/文件夹级别操作。如果你需要每个事件的颜色，请将事件组织到多个来源文件夹中。

### 全天事件与定时事件

为截止日期、周年纪念或多日区块切换全天选项。全天事件浮动在周视图和日视图的顶部，与定时事件分开，这使你的每小时网格保持整洁。

---

## 终极集成：与 Google Calendar 和 CalDAV 同步 {#sync}

这是 Full Calendar 将自己与所有其他 Obsidian 日历选项区分开来的地方——也是大多数设置混淆发生的地方。请仔细遵循这些步骤。

### Google Calendar 同步 (通过 iCal URL 只读)

Full Calendar 目前通过 **公共 iCal URL** 连接到 Google Calendar。这是只读的——事件从 Google 流入 Obsidian，而不是反向。

1. 打开 [Google Calendar](https://calendar.google.com) → 在左侧边栏中找到你的日历
2. 点击三点菜单 → **设置和共享**
3. 滚动到 **集成日历** → 复制 **iCal 格式的私人地址**（以 `https://calendar.google.com/calendar/ical/...` 开头的 URL）
4. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → 远程 (.ics / iCal URL)**
5. 粘贴 URL，命名，选择颜色，保存

你的 Google Calendar 事件现在出现在 Obsidian 中。当你重新打开库时，它们会刷新。**重要提示**：使用“私人地址”（私有 iCal），而不是公共地址，否则私人事件将不会出现。

### CalDAV 同步 (双向，完全读写)

要实现真正的双向同步——你可以在 Obsidian 内部创建和编辑事件，并让它们出现在你的外部日历中——你需要一个 **CalDAV 来源**。[Fastmail](URL_PLACEHOLDER_4) 是我们推荐的提供商：它注重隐私、可靠，并且其 CalDAV 实现清晰且文档完善。

**设置步骤：**

1. 在你的 CalDAV 提供商中，找到 CalDAV 服务器 URL 和你的日历特定 URL 路径
   - **Fastmail**：`https://caldav.fastmail.com/dav/principals/user/you@fastmail.com/`
   - **iCloud**：`https://caldav.icloud.com/`
2. 在 Obsidian 中：**设置 → Full Calendar → 添加日历来源 → CalDAV**
3. 输入：
   - **CalDAV 服务器 URL** (来自步骤 1)
   - **用户名** (通常是你的电子邮件地址)
   - **密码** (对于 iCloud，在 appleid.apple.com 生成一个应用专用密码)
4. 点击 **查找日历**——插件会查询服务器并列出可用的日历
5. 选择要同步的日历，分配颜色，保存

事件现在双向流动。在 Obsidian 中创建事件，它会在几秒钟内出现在 Fastmail 的网页界面（或你手机的日历应用）中。

---

## 3 个实用的工作流程来组织你的生活 {#workflows}

### 工作流程 1：学生作业跟踪器

**设置**：创建两个本地来源——`Deadlines`（红色）和 `Study Blocks`（蓝色）。将你大学的学术日历添加为 iCal URL 来源。

**工作原理**：每个作业都会在 `Deadlines` 中获得一个带有截止日期的笔记。使用周视图查看即将到来的截止日期，然后通过点击开放的时间段创建学习区块事件——从截止日期倒推。当你打开一个学习区块事件笔记时，使用标准的 `[[wikilinks]]` 将其直接链接到你的课程笔记。你现在拥有一个可以打开你实际学习材料的日历。

对于希望更正式地构建这种系统的用户，[Skillshare 上的此生产力课程](URL_PLACEHOLDER_5) 逐步介绍了如何从头开始构建一个完整的 PKM 系统。

### 工作流程 2：内容创作者的编辑日历

**设置**：每个内容类型一个本地来源文件夹——`Blog Posts`、`YouTube Scripts`、`Social Media`。每个都有独特的颜色。

**工作原理**：当你开始创作新作品时，将其创建为一个带有目标发布日期的事件。在 Frontmatter 中添加一个 `status` 字段（`draft`、`review`、`scheduled`、`published`）。使用月视图进行编辑规划——你可以一目了然地看到你是否在一周内集中了太多的帖子。拖动事件以重新分配。因为每个事件 *就是* 一个笔记，你的完整草稿就存在于日历条目中。

### 工作流程 3：专业人士的会议仪表板

**设置**：通过 iCal URL 同步你的工作 Google Calendar（只读）。为 Obsidian 创建的事件创建一个本地 `Meeting Notes` 来源。

**工作原理**：对于来自 Google Calendar 的每个会议，在你的本地来源中同时创建一个相应的会议笔记事件。使用模板（通过 Templater 或 QuickAdd）自动填充议程、与会者和行动项。Google Calendar 事件告诉你 *何时*；Obsidian 事件携带所有上下文。在周视图中，两者出现在同一时间段，通过颜色编码，你可以一目了然地知道哪个有相关的笔记。

---

## Full Calendar 与替代方案的对比 {#comparison}

| 功能 | Full Calendar | 原生 Calendar 插件 | Fantasy Calendar |
|---|---|---|---|
| 月/周/日视图 | ✅ 三者都有 | 仅月视图 | 仅月视图 |
| 本地笔记事件 | ✅ | ✅ (仅每日笔记) | ✅ |
| Google Calendar 同步 | ✅ (iCal 只读) | ❌ | ❌ |
| CalDAV 双向同步 | ✅ | ❌ | ❌ |
| 拖放重新安排 | ✅ | ❌ | ❌ |
| 虚构/自定义日历 | ❌ | ❌ | ✅ |
| 活跃开发 | ✅ | 缓慢 | 活跃 |
| 设置复杂性 | 中等 | 低 | 低 |

**何时选择替代方案：**
- **原生 Calendar 插件**：你只需要每日笔记导航，别无他求。零配置。
- **Fantasy Calendar**：你是一名世界构建者或小说家，需要自定义日历系统（13 个月的年份，不同的天长）。不适用于真实世界的日程安排。
- **Full Calendar**：所有其他用例，特别是涉及外部同步的任何情况。

---

## 常见陷阱与解决方案 {#pitfalls}

**问题：添加 iCal URL 后没有显示事件**
*原因*：你复制了公共日历 URL，而不是秘密 iCal URL。
*修复*：返回 Google Calendar → 设置 → “iCal 格式的私人地址”。它包含 URL 中的一个长令牌。那才是你需要使用的。

**问题：CalDAV 登录失败并显示“401 Unauthorized”**
*原因*：对于 iCloud，你的 Apple ID 密码将不起作用。CalDAV 需要一个应用专用密码。
*修复*：前往 appleid.apple.com → 登录与安全 → 应用专用密码 → 生成一个，然后在 CalDAV 字段中使用它。

**问题：编辑 Frontmatter 后事件重复**
*原因*：你移动了笔记文件到另一个文件夹，而它已经被跟踪。
*修复*：不要在来源文件夹之间手动移动事件笔记。而是在插件内部更改来源分配，然后让它协调。

**问题：使用大型库时日历视图卡顿**
*原因*：插件在加载时会扫描来源文件夹中的所有笔记。一个包含数百个旧事件的来源文件夹会拖慢速度。
*修复*：将旧事件笔记归档到未指定为日历来源的子文件夹中。保持活动来源精简（< 200 个笔记）。

**问题：同步几天后停止更新**
*原因*：iCal URL 在 Obsidian 端可能存在缓存行为。
*修复*：关闭并重新打开库，或在设置中关闭并重新打开日历来源以强制刷新。

---

## 最终评判 {#verdict}

**优点：**
- 真正的外部日历同步（唯一能很好地做到这一点的 Obsidian 插件）
- 事件是真实的笔记——可链接、可搜索、完整的 Markdown
- 拖放重新安排对于每周回顾来说确实很快
- 三种视图模式涵盖所有规划范围

**缺点：**
- Google Calendar 同步是只读的；你无法从 Obsidian 将事件推回到 Google
- CalDAV 设置需要仔细注意凭据和服务器 URL
- 颜色自定义仅限于来源级别，而非单个事件
- 对于非常大的来源文件夹，性能会下降

**总结**：如果你的工作流程涉及任何外部日历——工作、学校或个人——Full Calendar 是唯一值得使用的 Obsidian 插件。iCal 同步可在五分钟内让你完成 80% 的工作。与 [Fastmail](URL_PLACEHOLDER_4) 的 CalDAV 双向集成让你能够真正取代独立的日历应用进行日常使用。

[从社区插件浏览器安装 Full Calendar 插件](URL_PLACEHOLDER_1)，并花 20 分钟遵循上述设置指南。这笔投资将在日常使用的第一周内得到回报。

---

## 常见问题

### 问：Full Calendar 插件免费吗？

是的。它是完全开源的，采用 MIT 许可证。没有付费层级或专业版。

### 问：我可以将 Full Calendar 与 Apple Calendar (iCloud) 同步吗？

可以，通过 CalDAV。使用 `https://caldav.icloud.com/` 作为服务器 URL，并使用你的 Apple ID 设置中的应用专用密码。双向同步运行可靠。

### 问：Full Calendar 在 Obsidian 移动版上能用吗？

日历在 iOS 和 Android 上都能渲染，但由于网络权限处理，CalDAV 同步在移动设备上可能不可靠。本地事件工作正常。iCal 只读同步在大多数设置下都能正常工作。

### 问：如果我卸载插件，我的事件还会存在吗？

是的。本地事件是带有 Frontmatter 的标准 Markdown 文件。它们保留在你的库中，并且在没有插件的情况下也可以完全读取。外部 CalDAV 事件不会本地存储。

### 问：这与使用 Obsidian 内置的每日笔记日历有什么不同？

内置日历插件只允许你按日期导航到每日笔记——它不显示事件，不允许安排，也没有外部同步。Full Calendar 是一个独立、功能更强大的系统，它将笔记视为可安排的事件，具有时间、拖放和实时同步功能。

## 相关阅读

- [什么是 Obsidian Projects 插件（以及它适合谁用）](/zh-cn/posts/obsidian-projects-plugin-review-and-setup/)
- [什么是 Obsidian Git 插件？（简单解释）](/zh-cn/posts/what-is-the-obsidian-git-plugin-for/)
- [什么是 Excalidraw 以及为什么要在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为什么要在 Obsidian 中构建一个 Zettelkasten？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
```