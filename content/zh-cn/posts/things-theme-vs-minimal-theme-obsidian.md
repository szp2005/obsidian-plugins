---
images: ["/og/things-theme-vs-minimal-theme-obsidian.webp"]
title: "引言：超越默认 - 选择你理想的 Obsidian 界面"
author: "Alex Chen"
date: 2026-04-29
slug: things-theme-vs-minimal-theme-obsidian
description: "提供一个详细的并排功能对比表格，涵盖论坛讨论中常被忽视的方面，例如移动体验、特定功能等。"
keywords: ["Obsidian.md themes", "best Obsidian theme", "Obsidian customization", "Obsidian CSS", "Minimal theme settings", "Things theme setup", "Obsidian GTD workflow", "PKM aesthetics"]
draft: false
type: "informational"
tags: ["introduction", "beyond", "default", "choosing"]
---

_作为 Amazon 联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Things 主题 vs Minimal 主题 Obsidian：权威性正面比较

---

## TL;DR

- **Things 主题**是一个有主见的、GTD 就绪的皮肤，灵感来自 Things 3 应用——安装它，你的库在五分钟内就能看起来很精致，无需任何调整。
- **Minimal 主题**是一个接近空白的画布，深度集成了 Style Settings——如果你想对字体、颜色和布局进行精细控制，这是理想的选择。
- **没有哪个是普遍更好的**：你的工作流程，而不是美学，应该驱动决策。

---

## 目录

1. [超越默认 — 选择你理想的 Obsidian 界面](#introduction)
2. [一览：Things vs. Minimal 比较表](#comparison-table)
3. [深度探讨：Things 主题 — 结构与效率](#things-theme)
4. [深度探讨：Minimal 主题 — 专注的画布](#minimal-theme)
5. [定制对决：Style Settings vs. 有主见的设计](#customization)
6. [工作流程实战：撰写 vs. 项目管理](#workflow)
7. [三种用户画像 — 谁该选择哪个](#personas)
8. [结论：哪个 Obsidian 主题适合你？](#verdict)
9. [常见问题](#faq)

---

## 1. 超越默认 — 选择你理想的 Obsidian 界面 {#introduction}

Obsidian 的默认主题是实用的。坦率地说，它也容易被遗忘。对于一个你每天打开几十次的应用程序来说，这一点很重要。主题并非仅仅是装饰性的附加品——它们影响阅读速度、认知负荷，以及你的工作流程与屏幕映射的自然程度。

在每个 Obsidian 社区讨论中，有两个主题占据了主导地位：**Things** 和 **Minimal**。它们处于光谱的两端。Things 自带鲜明的个性——暖色调、结构化的层次结构，明确地指向任务管理。Minimal 则作为一个近乎隐形的框架出现，它能根据你的需求任意塑形。

选择错误会浪费数小时。你搭建了一个系统，调整了 CSS，创建了模板——然后才意识到主题与你的实际习惯背道而驰。本文为你提供了两者的具体、并排的图景，让你一次阅读就能做出决定。

---

## 2. 一览：Things vs. Minimal 比较表 {#comparison-table}

| 功能 | Things 主题 | Minimal 主题 |
|---|---|---|
| **设计理念** | 有主见，效率优先，GTD 对齐 | 中性画布，低对比度，字体优先 |
| **定制级别** | 低到中等（侧重 CSS 变量） | 非常高（100+ Style Settings 选项） |
| **理想用户** | GTD 实践者，任务繁重的工作流程 | 作家，研究人员，高级定制者 |
| **Style Settings 集成** | 基本支持 | 深度，一流集成 |
| **Dataview 支持** | 足够，无样式表格 | 开箱即用的样式化表格、卡片、列表 |
| **Kanban 插件样式** | 极简，无特殊处理 | 可选的卡片样式通过辅助类实现 |
| **移动体验** | 整洁，可读，有限调整 | 响应式，带移动端特定设置 |
| **内置配色方案** | 1 种（亮色 + 暗色变体） | 15+ 预设（Atom, Solarized, Dracula 等） |
| **辅助 / 实用类** | 少量（复选框图标，标题样式） | 广泛（列，卡片，图片网格，宽页面） |
| **学习曲线** | 低 — 立即可用 | 中等 — 需插件设置才能发挥全部功能 |
| **活跃维护** | 社区维护，更新较慢 | @kepano 积极维护 |
| **CSS 片段兼容性** | 良好 | 优秀，文档完善的变量 |

---

## 3. 深度探讨：Things 主题 — 结构与效率 {#things-theme}

[The Things theme](URL_PLACEHOLDER_1) 由 Colin Eckert 专门构建，旨在模仿 [Things 3](URL_PLACEHOLDER_2) 的视觉语言，这是 Cultured Code 适用于 Mac 和 iOS 的任务管理器。如果你使用 Things 3 进行任务捕获，并使用 Obsidian 进行笔记，那么这两个应用就会感觉像一个单一的系统。

### 它实际看起来像什么

调色板偏暖——亮色模式下为米白色背景，暗色模式下为深炭色。H1 到 H3 标题具有独特的尺寸和粗细，无需你调整任何设置即可创建清晰的阅读层次结构。水平线呈现为微妙的分隔符，而不是硬线，这使得长项目笔记易于扫视。

### 内置的 GTD 元素

最突出的功能是**自定义复选框样式**。Things 附带了一组备用复选框类型，直接映射到 GTD 任务状态：

- `- [/]` → 进行中（半填充圆圈）
- `- [-]` → 已取消（删除线）
- `- [>]` → 已推迟（箭头）
- `- [?]` → 问题 / 等待中
- `- [!]` → 重要

如果你在 Obsidian 中运行任何类型的行动清单工作流程，仅此一点就值得安装。无需 CSS 片段。无需插件。只需 Markdown。

### 权衡：有主见意味着不灵活

那种温暖的美学是故意的——也是固执的。更改强调色需要编辑原始 CSS 变量。没有类似于 Minimal 提供的 GUI 配置面板。对于那些想要一个开箱即用、美观的系统，并且永远不需要再次触碰的用户来说，这是一个功能。对于任何想要按季节或按项目迭代设置的用户来说，这会成为一个摩擦点。

插件支持足够，但并非精选。Dataview 表格正确渲染，但没有任何自定义样式。Kanban 看板可用，但很普通。Calendar 和 Tasks 插件可以工作，但都没有得到特殊的视觉处理。

---

## 4. 深度探讨：Minimal 主题 — 专注的画布 {#minimal-theme}

[Minimal](URL_PLACEHOLDER_3) 由 Stephan Ango (@kepano) 维护，他也是 Obsidian 的联合创始人。这种与核心团队的紧密联系体现在主题如何与每一次主要应用更新保持同步。多年来，它一直是下载量最大的社区主题，围绕它的生态系统也反映了这种持久性。

### 设计理念：退居幕后

设计意图在文档中明确：移除一切不直接服务于阅读或写作的元素。边框更细。侧边栏对比度降低。编辑器表面感觉像一张纸。这并非偷懒的设计——它是经过深思熟虑的精简，旨在降低长时间写作会话的认知负荷。

### Style Settings 集成：100 多个旋钮

在 Minimal 旁边安装 [Style Settings 插件](URL_PLACEHOLDER_4)，你将解锁一个专用的设置面板，涵盖：

- **配色方案**：15+ 预设，包括 Atom, Solarized, Gruvbox, Rosé Pine, Dracula
- **字体堆栈**：UI 字体、正文文本、等宽字体和标题的独立控制
- **行宽**：可读（660px），宽（860px），或最大（全宽）
- **图片对齐**：左、中、右、覆盖
- **表格样式**：紧凑、极简或卡片式行
- **侧边栏行为**：折叠边框、隐藏 UI 界面

所有这些都不需要你写一行 CSS。它是 Obsidian 生态系统中除了自己编写主题之外最完整的自定义系统。

### 辅助类：隐藏的强大功能

Minimal 附带了一组**CSS 辅助类**，你可以直接添加到笔记属性中。示例：

- `cssclasses: wide-page` → 移除电子表格式笔记的行长限制
- `cssclasses: cards` → 将 Dataview 查询结果转换为可视化卡片网格
- `cssclasses: image-grid` → 将嵌入图片平铺成画廊布局
- `cssclasses: column-list` → 将笔记内容分割成报纸式分栏

这些类使得单个笔记看起来彼此截然不同——这是一个对仪表板、MOC 和参考库具有实际工作流程影响的功能。

---

## 5. 定制对决：Style Settings vs. 有主见的设计 {#customization}

如果你讨厌接触 CSS，**Things 默认获胜**。安装它，通过标准切换在亮色和暗色之间切换，使用内置的复选框类型，然后就完成了。主题会处理设计决策，这样你就无需动手。

如果你想要控制权，**Minimal 甚至没有竞争对手**。Style Settings 面板涵盖了字体排版、间距、颜色、插件 UI、侧边栏界面和每笔记布局——所有这些都通过 GUI 实现。你可以花一个下午来构建你想要的确切视觉环境，而无需打开代码编辑器。

### CSS 片段

两个主题都支持原始 CSS 片段，但 Minimal 的文档明确列出了其 CSS 变量名称，使得有针对性的调整变得简单。Things 使用一组较小的未文档化变量，因此自定义 CSS 更多是试错。

**Things 的推荐片段工作流程：**
1. 从社区安装 [Minimal Things CSS 片段](URL_PLACEHOLDER_5)——它弥补了一些不足。
2. 覆盖 `--color-base-00` 到 `--color-base-100`，如果喜欢，可以将暖色调调向冷色调。

**Minimal 的推荐工作流程：**
1. 首先安装 Style Settings——没有它，Minimal 看起来不完整。
2. 选择一个基础配色方案，然后调整字体排版。
3. 将每笔记 `cssclasses` 添加到仪表板和参考笔记中。

---

## 6. 工作流程实战：撰写 vs. 项目管理 {#workflow}

### 用例 1：在 Minimal 中撰写长篇文章

打开一个空白笔记，为草稿设置 `cssclasses: wide-page`，然后在编辑时需要 660px 阅读宽度时将其移除。通过 Style Settings 设置一个衬线正文字体（Palatino 或 iA Writer Quattro 都能清晰地工作）。在 Obsidian 的编辑器设置中启用“可读行长”。

结果：一个专注的写作界面，没有相互竞争的 UI 元素。侧边栏的对比度降得足够低，以至于在深度工作期间你不会注意到它。对于围绕长篇内容构建 PKM 的作家来说，这种环境与任何其他 Obsidian 配置都截然不同——这是一个结构良好的 [PKM 课程](URL_PLACEHOLDER_6)会带你从头到尾学习的系统。

### 用例 2：使用 Things 主题管理项目

创建一个项目笔记，包含清晰的 H1 标题、每个阶段的 H2 部分和子任务的 H3。全程使用自定义复选框类型：`- [/]` 表示正在进行的工作，`- [>]` 表示被其他事项阻塞的项目，`- [!]` 表示阻塞事项。

温暖的标题层次结构使笔记一目了然。推迟和取消的复选框状态意味着你的任务列表反映的是实际的 GTD 状态，而不仅仅是二元的完成/未完成。如果你也使用 [Things 3](URL_PLACEHOLDER_2) 进行日常任务管理，那么应用程序之间的视觉连贯性会以可衡量的方式减少上下文切换的摩擦。

---

## 7. 三种用户画像 — 谁该选择哪个 {#personas}

### 极简主义作家

**画像：** 主要将 Obsidian 用作写作环境。存储草稿、研究笔记和已发布的档案。关心行长、字体渲染和专注模式。很少使用 Kanban 或 Dataview。

**推荐：Minimal。** 字体排版控制和无干扰界面专为此工作流程而设计。没有其他流行主题能与其阅读和写作的人机工程学相媲美。

### GTD 高级用户

**画像：** Obsidian 是一个完整的任务和项目管理系统。使用自定义复选框、项目模板、周回顾笔记以及区域/项目/资源/档案文件夹结构。喜欢 Things 3 的美学。

**推荐：Things。** 仅自定义复选框类型就足以证明选择的合理性。温暖、结构化的设计在每次打开库时都能强化 GTD 的心智模型。

### 美学调整者

**画像：** 喜欢定制工具的过程，就像喜欢使用工具一样。拥有 CSS 片段，尝试新的配色方案，使用 Dataview 卡片视图构建自定义仪表板。希望在不分叉主题的情况下获得最大的灵活性。

**推荐：Minimal。** 100 多个 Style Settings 选项、辅助类和文档完善的变量提供了比任何其他主流 Obsidian 主题更多的配置空间。它不会用尽可调整的旋钮。

---

## 8. 结论：哪个 Obsidian 主题适合你？ {#verdict}

**如果符合以下情况，请选择 Things：**
- 你运行 GTD 或任何以清单为主的工作流程，并且希望无需编写 CSS 即可获得这些任务状态
- 你同时使用 Things 3 和 Obsidian，并希望保持视觉连贯性
- 你希望在零配置时间内获得一个完整、精美的外观

**如果符合以下情况，请选择 Minimal：**
- 写作是你在 Obsidian 中的主要活动
- 你希望对每个视觉变量进行精细控制
- 你大量使用 Dataview 并希望获得样式化的卡片/表格输出
- 你计划随着时间的推移维护和发展你的库设置
- 你需要一个可靠的移动体验，并带有主题特定的调整

关于移动设备的一个实用说明：如果你在桌面和手机上都使用 Obsidian，主题的一致性很重要。[Obsidian Sync](URL_PLACEHOLDER_7) 会将你的主题设置和 CSS 片段跨设备同步，因此无论你选择哪个主题，在每个平台上看起来都相同——如果你的工作流程跨设备，这值得订阅。

两个主题都是免费的。两者都具有生产质量。没有错误的答案——只有不适合你特定习惯的错误主题。

---

## 总结

Obsidian 中 Things vs. Minimal 的争论，并非真正关乎外观。它关乎你想要一个为你做决定的主题（Things），还是一个能精确执行你决定的主题（Minimal）。

选择 Things，打开你的库，开始工作。选择 Minimal，花二十分钟在 Style Settings 中调整，然后打开你的库，开始工作。这两种方式都能带来比默认主题显著更好的日常体验。

如果你正在构建一个严肃的 PKM 实践，美学是最简单的部分。系统、习惯和工作流程优先——而 [结构化的 Obsidian 课程](URL_PLACEHOLDER_6)可以将其加速数月。将你选择的任何主题与 [Obsidian Sync](URL_PLACEPLOLDER_7) 配对，以使其在每个设备上保持一致，你的设置就会变成你每天早上都期待打开的东西。

这才是真正的目标。

---

## 常见问题

### 我可以在 Obsidian 中同时使用 Things 和 Minimal 吗？

不能。Obsidian 一次只加载一个活跃主题。但是，你可以通过“设置 → 外观”即时切换它们。一些用户为不同的项目维护带有不同主题的单独库配置文件，这是一种合法的变通方法。

### Things 主题在没有 Style Settings 插件的情况下能工作吗？

是的，与 Minimal 不同，它在没有该插件的情况下也能很好地工作。Things 作为一套完整的视觉系统发布。Style Settings 增加了一些次要选项，但并非获得完整体验所必需。

### Obsidian 更新时，这两个主题会失效吗？

Minimal 由 Obsidian 的联合创始人维护，并在主要应用程序发布后迅速更新。Things 由社区维护，更新周期较慢——在将它用于生产库之前，请查看 [GitHub 仓库](URL_PLACEHOLDER_1) 的最后提交日期。

### 哪个主题在移动设备上表现更好？

Minimal 在 Style Settings 中有明确的移动设备特定设置，包括触摸目标大小和侧边栏行为。Things 在移动设备上渲染清晰，但没有提供移动设备特定的配置选项。

### 有没有结合了 Things 和 Minimal 元素的主题？

有。AnuPpuccin 提供了可自定义的配色方案和内置的备用复选框样式——它在灵活性和开箱即用完整性之间处于两者之间。Ebullient 和 Border 主题也借鉴了两种设计语言，如果 Things 和 Minimal 都不符合你的需求，它们值得探索。

## 相关阅读

- [What is Excalidraw and Why Use It in Obsidian?](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [Why Build a Zettelkasten in Obsidian?](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [Why Track Habits in Obsidian in 2024?](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
- [What Are Obsidian Community Plugins?](/zh-cn/posts/obsidian-community-plugins-list/)
---
images: ["/og/things-theme-vs-minimal-theme-obsidian.webp"]
title: "引言：超越默认 - 选择你理想的 Obsidian 界面"
author: "Alex Chen"
date: 2026-04-29
slug: things-theme-vs-minimal-theme-obsidian
description: "提供一个详细的并排功能对比表格，涵盖论坛讨论中常被忽视的方面，例如移动体验、特定功能等。"
keywords: ["Obsidian.md themes", "best Obsidian theme", "Obsidian customization", "Obsidian CSS", "Minimal theme settings", "Things theme setup", "Obsidian GTD workflow", "PKM aesthetics"]
draft: false
type: "informational"
tags: ["introduction", "beyond", "default", "choosing"]
---

_作为 Amazon 联盟成员，我们从符合条件的购买中赚取佣金。此帖子可能包含联盟链接。_

# Things 主题 vs Minimal 主题 Obsidian：权威性正面比较

---

## TL;DR

- **Things 主题**是一个有主见的、GTD 就绪的皮肤，灵感来自 Things 3 应用——安装它，你的库在五分钟内就能看起来很精致，无需任何调整。
- **Minimal 主题**是一个接近空白的画布，深度集成了 Style Settings——如果你想对字体、颜色和布局进行精细控制，这是理想的选择。
- **没有哪个是普遍更好的**：你的工作流程，而不是美学，应该驱动决策。

---

## 目录

1. [超越默认 — 选择你理想的 Obsidian 界面](#introduction)
2. [一览：Things vs. Minimal 比较表](#comparison-table)
3. [深度探讨：Things 主题 — 结构与效率](#things-theme)
4. [深度探讨：Minimal 主题 — 专注的画布](#minimal-theme)
5. [定制对决：Style Settings vs. 有主见的设计](#customization)
6. [工作流程实战：撰写 vs. 项目管理](#workflow)
7. [三种用户画像 — 谁该选择哪个](#personas)
8. [结论：哪个 Obsidian 主题适合你？](#verdict)
9. [常见问题](#faq)

---

## 1. 超越默认 — 选择你理想的 Obsidian 界面 {#introduction}

Obsidian 的默认主题是实用的。坦率地说，它也容易被遗忘。对于一个你每天打开几十次的应用程序来说，这一点很重要。主题并非仅仅是装饰性的附加品——它们影响阅读速度、认知负荷，以及你的工作流程与屏幕映射的自然程度。

在每个 Obsidian 社区讨论中，有两个主题占据了主导地位：**Things** 和 **Minimal**。它们处于光谱的两端。Things 自带鲜明的个性——暖色调、结构化的层次结构，明确地指向任务管理。Minimal 则作为一个近乎隐形的框架出现，它能根据你的需求任意塑形。

选择错误会浪费数小时。你搭建了一个系统，调整了 CSS，创建了模板——然后才意识到主题与你的实际习惯背道而驰。本文为你提供了两者的具体、并排的图景，让你一次阅读就能做出决定。

---

## 2. 一览：Things vs. Minimal 比较表 {#comparison-table}

| 功能 | Things 主题 | Minimal 主题 |
|---|---|---|
| **设计理念** | 有主见，效率优先，GTD 对齐 | 中性画布，低对比度，字体优先 |
| **定制级别** | 低到中等（侧重 CSS 变量） | 非常高（100+ Style Settings 选项） |
| **理想用户** | GTD 实践者，任务繁重的工作流程 | 作家，研究人员，高级定制者 |
| **Style Settings 集成** | 基本支持 | 深度，一流集成 |
| **Dataview 支持** | 足够，无样式表格 | 开箱即用的样式化表格、卡片、列表 |
| **Kanban 插件样式** | 极简，无特殊处理 | 可选的卡片样式通过辅助类实现 |
| **移动体验** | 整洁，可读，有限调整 | 响应式，带移动端特定设置 |
| **内置配色方案** | 1 种（亮色 + 暗色变体） | 15+ 预设（Atom, Solarized, Dracula 等） |
| **辅助 / 实用类** | 少量（复选框图标，标题样式） | 广泛（列，卡片，图片网格，宽页面） |
| **学习曲线** | 低 — 立即可用 | 中等 — 需插件设置才能发挥全部功能 |
| **活跃维护** | 社区维护，更新较慢 | @kepano 积极维护 |
| **CSS 片段兼容性** | 良好 | 优秀，文档完善的变量 |

---

## 3. 深度探讨：Things 主题 — 结构与效率 {#things-theme}

[The Things theme](URL_PLACEHOLDER_1) 由 Colin Eckert 专门构建，旨在模仿 [Things 3](URL_PLACEHOLDER_2) 的视觉语言，这是 Cultured Code 适用于 Mac 和 iOS 的任务管理器。如果你使用 Things 3 进行任务捕获，并使用 Obsidian 进行笔记，那么这两个应用就会感觉像一个单一的系统。

### 它实际看起来像什么

调色板偏暖——亮色模式下为米白色背景，暗色模式下为深炭色。H1 到 H3 标题具有独特的尺寸和粗细，无需你调整任何设置即可创建清晰的阅读层次结构。水平线呈现为微妙的分隔符，而不是硬线，这使得长项目笔记易于扫视。

### 内置的 GTD 元素

最突出的功能是**自定义复选框样式**。Things 附带了一组备用复选框类型，直接映射到 GTD 任务状态：

- `- [/]` → 进行中（半填充圆圈）
- `- [-]` → 已取消（删除线）
- `- [>]` → 已推迟（箭头）
- `- [?]` → 问题 / 等待中
- `- [!]` → 重要

如果你在 Obsidian 中运行任何类型的行动清单工作流程，仅此一点就值得安装。无需 CSS 片段。无需插件。只需 Markdown。

### 权衡：有主见意味着不灵活

那种温暖的美学是故意的——也是固执的。更改强调色需要编辑原始 CSS 变量。没有类似于 Minimal 提供的 GUI 配置面板。对于那些想要一个开箱即用、美观的系统，并且永远不需要再次触碰的用户来说，这是一个功能。对于任何想要按季节或按项目迭代设置的用户来说，这会成为一个摩擦点。

插件支持足够，但并非精选。Dataview 表格正确渲染，但没有任何自定义样式。Kanban 看板可用，但很普通。Calendar 和 Tasks 插件可以工作，但都没有得到特殊的视觉处理。

---

## 4. 深度探讨：Minimal 主题 — 专注的画布 {#minimal-theme}

[Minimal](URL_PLACEHOLDER_3) 由 Stephan Ango (@kepano) 维护，他也是 Obsidian 的联合创始人。这种与核心团队的紧密联系体现在主题如何与每一次主要应用更新保持同步。多年来，它一直是下载量最大的社区主题，围绕它的生态系统也反映了这种持久性。

### 设计理念：退居幕后

设计意图在文档中明确：移除一切不直接服务于阅读或写作的元素。边框更细。侧边栏对比度降低。编辑器表面感觉像一张纸。这并非偷懒的设计——它是经过深思熟虑的精简，旨在降低长时间写作会话的认知负荷。

### Style Settings 集成：100 多个旋钮

在 Minimal 旁边安装 [Style Settings 插件](URL_PLACEHOLDER_4)，你将解锁一个专用的设置面板，涵盖：

- **配色方案**：15+ 预设，包括 Atom, Solarized, Gruvbox, Rosé Pine, Dracula
- **字体堆栈**：UI 字体、正文文本、等宽字体和标题的独立控制
- **行宽**：可读（660px），宽（860px），或最大（全宽）
- **图片对齐**：左、中、右、覆盖
- **表格样式**：紧凑、极简或卡片式行
- **侧边栏行为**：折叠边框、隐藏 UI 界面

所有这些都不需要你写一行 CSS。它是 Obsidian 生态系统中除了自己编写主题之外最完整的自定义系统。

### 辅助类：隐藏的强大功能

Minimal 附带了一组**CSS 辅助类**，你可以直接添加到笔记属性中。示例：

- `cssclasses: wide-page` → 移除电子表格式笔记的行长限制
- `cssclasses: cards` → 将 Dataview 查询结果转换为可视化卡片网格
- `cssclasses: image-grid` → 将嵌入图片平铺成画廊布局
- `cssclasses: column-list` → 将笔记内容分割成报纸式分栏

这些类使得单个笔记看起来彼此截然不同——这是一个对仪表板、MOC 和参考库具有实际工作流程影响的功能。

---

## 5. 定制对决：Style Settings vs. 有主见的设计 {#customization}

如果你讨厌接触 CSS，**Things 默认获胜**。安装它，通过标准切换在亮色和暗色之间切换，使用内置的复选框类型，然后就完成了。主题会处理设计决策，这样你就无需动手。

如果你想要控制权，**Minimal 甚至没有竞争对手**。Style Settings 面板涵盖了字体排版、间距、颜色、插件 UI、侧边栏界面和每笔记布局——所有这些都通过 GUI 实现。你可以花一个下午来构建你想要的确切视觉环境，而无需打开代码编辑器。

### CSS 片段

两个主题都支持原始 CSS 片段，但 Minimal 的文档明确列出了其 CSS 变量名称，使得有针对性的调整变得简单。Things 使用一组较小的未文档化变量，因此自定义 CSS 更多是试错。

**Things 的推荐片段工作流程：**
1. 从社区安装 [Minimal Things CSS 片段](URL_PLACEHOLDER_5)——它弥补了一些不足。
2. 覆盖 `--color-base-00` 到 `--color-base-100`，如果喜欢，可以将暖色调调向冷色调。

**Minimal 的推荐工作流程：**
1. 首先安装 Style Settings——没有它，Minimal 看起来不完整。
2. 选择一个基础配色方案，然后调整字体排版。
3. 将每笔记 `cssclasses` 添加到仪表板和参考笔记中。

---

## 6. 工作流程实战：撰写 vs. 项目管理 {#workflow}

### 用例 1：在 Minimal 中撰写长篇文章

打开一个空白笔记，为草稿设置 `cssclasses: wide-page`，然后在编辑时需要 660px 阅读宽度时将其移除。通过 Style Settings 设置一个衬线正文字体（Palatino 或 iA Writer Quattro 都能清晰地工作）。在 Obsidian 的编辑器设置中启用“可读行长”。

结果：一个专注的写作界面，没有相互竞争的 UI 元素。侧边栏的对比度降得足够低，以至于在深度工作期间你不会注意到它。对于围绕长篇内容构建 PKM 的作家来说，这种环境与任何其他 Obsidian 配置都截然不同——这是一个结构良好的 [PKM 课程](URL_PLACEHOLDER_6)会带你从头到尾学习的系统。

### 用例 2：使用 Things 主题管理项目

创建一个项目笔记，包含清晰的 H1 标题、每个阶段的 H2 部分和子任务的 H3。全程使用自定义复选框类型：`- [/]` 表示正在进行的工作，`- [>]` 表示被其他事项阻塞的项目，`- [!]` 表示阻塞事项。

温暖的标题层次结构使笔记一目了然。推迟和取消的复选框状态意味着你的任务列表反映的是实际的 GTD 状态，而不仅仅是二元的完成/未完成。如果你也使用 [Things 3](URL_PLACEHOLDER_2) 进行日常任务管理，那么应用程序之间的视觉连贯性会以可衡量的方式减少上下文切换的摩擦。

---

## 7. 三种用户画像 — 谁该选择哪个 {#personas}

### 极简主义作家

**画像：** 主要将 Obsidian 用作写作环境。存储草稿、研究笔记和已发布的档案。关心行长、字体渲染和专注模式。很少使用 Kanban 或 Dataview。

**推荐：Minimal。** 字体排版控制和无干扰界面专为此工作流程而设计。没有其他流行主题能与其阅读和写作的人机工程学相媲美。

### GTD 高级用户

**画像：** Obsidian 是一个完整的任务和项目管理系统。使用自定义复选框、项目模板、周回顾笔记以及区域/项目/资源/档案文件夹结构。喜欢 Things 3 的美学。

**推荐：Things。** 仅自定义复选框类型就足以证明选择的合理性。温暖、结构化的设计在每次打开库时都能强化 GTD 的心智模型。

### 美学调整者

**画像：** 喜欢定制工具的过程，就像喜欢使用工具一样。拥有 CSS 片段，尝试新的配色方案，构建自定义仪表板与 Dataview 卡片视图。希望在不分叉主题的情况下获得最大的灵活性。

**推荐：Minimal。** 100 多个 Style Settings 选项、辅助类和文档完善的变量提供了比任何其他主流 Obsidian 主题更多的配置空间。它不会用尽可调整的旋钮。

---

## 8. 结论：哪个 Obsidian 主题适合你？ {#verdict}

**如果符合以下情况，请选择 Things：**
- 你运行 GTD 或任何以清单为主的工作流程，并且希望无需编写 CSS 即可获得这些任务状态
- 你同时使用 Things 3 和 Obsidian，并希望保持视觉连贯性
- 你希望在零配置时间内获得一个完整、精美的外观

**如果符合以下情况，请选择 Minimal：**
- 写作是你在 Obsidian 中的主要活动
- 你希望对每个视觉变量进行精细控制
- 你大量使用 Dataview 并希望获得样式化的卡片/表格输出
- 你计划随着时间的推移维护和发展你的库设置
- 你需要一个可靠的移动体验，并带有主题特定的调整

关于移动设备的一个实用说明：如果你在桌面和手机上都使用 Obsidian，主题的一致性很重要。[Obsidian Sync](URL_PLACEHOLDER_7) 会将你的主题设置和 CSS 片段跨设备同步，因此无论你选择哪个主题，在每个平台上看起来都相同——如果你的工作流程跨设备，这值得订阅。

两个主题都是免费的。两者都具有生产质量。没有错误的答案——只有不适合你特定习惯的错误主题。

---

## 总结

Obsidian 中 Things vs. Minimal 的争论，并非真正关乎外观。它关乎你想要一个为你做决定的主题（Things），还是一个能精确执行你决定的主题（Minimal）。

选择 Things，打开你的库，开始工作。选择 Minimal，花二十分钟在 Style Settings 中调整，然后打开你的库，开始工作。这两种方式都能带来比默认主题显著更好的日常体验。

如果你正在构建一个严肃的 PKM 实践，美学是最简单的部分。系统、习惯和工作流程优先——而 [结构化的 Obsidian 课程](URL_PLACEHOLDER_6)可以将其加速数月。将你选择的任何主题与 [Obsidian Sync](URL_PLACEHOLDER_7) 配对，以使其在每个设备上保持一致，你的设置就会变成你每天早上都期待打开的东西。

这才是真正的目标。

---

## 常见问题

### 我可以在 Obsidian 中同时使用 Things 和 Minimal 吗？

不能。Obsidian 一次只加载一个活跃主题。但是，你可以通过“设置 → 外观”即时切换它们。一些用户为不同的项目维护带有不同主题的单独库配置文件，这是一种合法的变通方法。

### Things 主题在没有 Style Settings 插件的情况下能工作吗？

是的，与 Minimal 不同，它在没有该插件的情况下也能很好地工作。Things 作为一套完整的视觉系统发布。Style Settings 增加了一些次要选项，但并非获得完整体验所必需。

### Obsidian 更新时，这两个主题会失效吗？

Minimal 由 Obsidian 的联合创始人维护，并在主要应用程序发布后迅速更新。Things 由社区维护，更新周期较慢——在将它用于生产库之前，请查看 [GitHub 仓库](URL_PLACEHOLDER_1) 的最后提交日期。

### 哪个主题在移动设备上表现更好？

Minimal 在 Style Settings 中有明确的移动设备特定设置，包括触摸目标大小和侧边栏行为。Things 在移动设备上渲染清晰，但没有提供移动设备特定的配置选项。

### 有没有结合了 Things 和 Minimal 元素的主题？

有。AnuPpuccin 提供了可自定义的配色方案和内置的备用复选框样式——它在灵活性和开箱即用完整性之间处于两者之间。Ebullient 和 Border 主题也借鉴了两种设计语言，如果 Things 和 Minimal 都不符合你的需求，它们值得探索。

## 相关阅读

- [What is Excalidraw and Why Use It in Obsidian?](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [Why Build a Zettelkasten in Obsidian?](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [Why Track Habits in Obsidian in 2024?](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
- [What Are Obsidian Community Plugins?](/zh-cn/posts/obsidian-community-plugins-list/)