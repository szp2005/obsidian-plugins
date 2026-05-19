Attempt 1 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:07:27 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=7729',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': 'c58e0f0b50cbaf32',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
Attempt 1 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:07:46 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=7037',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': '7f81473ce2b92628',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
```markdown
---
images: ["/og/how-to-customize-obsidian-appearance-with-css-snippets.webp"]
title: "Obsidian CSS 代码片段：掌控你的库外观"
author: "Alex Chen"
date: 2026-04-29
slug: how-to-customize-obsidian-appearance-with-css-snippets
description: "使用 CSS 代码片段自定义 Obsidian 外观，从设置和选择器到实用库样式调整的入门包。"
keywords: ["Obsidian CSS theme", "Obsidian vault appearance", "CSS snippets for Obsidian", "Obsidian custom theme", ".obsidian/snippets folder", "Obsidian developer console", "Change font in Obsidian", "Obsidian styling"]
draft: false
type: "informational"
tags: ["css", "snippets", "care", "how to customize obsidian appearance with css snippets"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取收益。此帖子可能包含联盟链接。_

# 如何使用 CSS 代码片段自定义 Obsidian 外观（完整指南 + 即用型入门包）

---

## TL;DR

- CSS 代码片段是位于你库的 `.obsidian/snippets` 文件夹中的小型 `.css` 文件，它们允许你在不修改主题的情况下更改特定的视觉元素。
- 你可以在不到一分钟的时间内，在 **设置 → 外观 → CSS 代码片段** 中启用、禁用和叠加多个代码片段。
- 开发者控制台（`Ctrl+Shift+I` / `Cmd+Opt+I`）允许你检查任何 UI 元素并找到其精确的 CSS 选择器，这样你就可以样式化 *任何东西* — 而不仅仅是其他人已记录的。

---

## 目录

1. [什么是 CSS 代码片段以及为何要关心它们？](#what-are-css-snippets)
2. [60 秒内完成设置：在你的库中启用 CSS 代码片段](#setup-in-60-seconds)
3. [你的第一次调整：字体和标题颜色更改](#your-first-tweak)
4. [成为专业人士：使用开发者控制台查找任何元素](#developer-console)
5. [10 个必备 CSS 代码片段来改变你的库](#10-essential-snippets)
6. [故障排除：当你的代码片段不工作时](#troubleshooting)
7. [超越代码片段：何时使用完整的社区主题](#beyond-snippets)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 什么是 CSS 代码片段以及为何要关心它们？ {#what-are-css-snippets}

Obsidian 使用浏览器引擎渲染你的笔记。这意味着你所看到的一切——字体、颜色、标题大小、标注框、侧边栏宽度——都由 CSS 控制，CSS 是一种与控制网站外观相同的样式语言。

**CSS 代码片段**是一个小型 `.css` 文件，包含一个或多个规则，用于覆盖你库中的特定样式。将其视为一次外科手术式的修正，而非移植。一个完整的社区主题会一次性替换所有内容——颜色、布局、排版、图标。而代码片段则微调一处。你想让 H1 标题呈现深青色？一个代码片段，四行代码。你想在专注模式下隐藏状态栏？另一个代码片段，两行。

**为什么代码片段在进行有针对性的更改时优于主题切换：**

- **精确性。** 你只更改困扰你的部分，而不影响其他一切。
- **可叠加。** 你可以同时运行 10 个代码片段，每个处理一个不同的元素。
- **主题无关。** 它们在任何社区主题之上运行。以 Minimal 主题为基础，再叠加你自己的调整。
- **零锁定。** 只需单击一下即可关闭任何代码片段。没有任何东西是永久的。

如果你曾安装过社区主题并觉得“除了那些丑陋的引用块，我喜欢所有一切”，那么代码片段就是答案。

---

## 60 秒内完成设置：在你的库中启用 CSS 代码片段 {#setup-in-60-seconds}

你无需接触终端或安装任何东西。

**步骤 1：** 打开 Obsidian 并按 `Ctrl+,` (Windows/Linux) 或 `Cmd+,` (Mac) 打开 **设置**。

**步骤 2：** 点击左侧边栏中的 **外观** 选项卡。

**步骤 3：** 滚动到外观页面底部，直到看到 **CSS 代码片段** 部分。点击旁边的 **文件夹图标**。这会直接在你系统文件管理器中打开 `.obsidian/snippets/` — 这是 Obsidian 查找代码片段文件的确切文件夹。

**步骤 4：** 在该文件夹内创建一个新文件。你可以随意命名——`my-fonts.css`、`header-styles.css`、`focus-mode.css`——但文件扩展名**必须是 `.css`**。在任何纯文本编辑器中打开该文件：Windows 上的记事本、Mac 上的 TextEdit（纯文本模式），或者如果你有 VS Code。

**步骤 5：** 将你的 CSS 规则粘贴到文件中并保存。回到 Obsidian 的外观设置中，点击 CSS 代码片段标题旁边的 **刷新图标**。你的新文件将出现在列表中，带有一个切换开关。将其打开。

这就是整个工作流程。每次你编辑代码片段文件并保存时，Obsidian 都会自动热重载它——你可以实时看到更改。

---

## 你的第一次调整：字体和标题颜色更改 {#your-first-tweak}

让我们在进行复杂内容之前建立信心。这里有两个代码片段，可以立即产生可见效果。

### 更改编辑器正文字体

```css
/* my-fonts.css */
.cm-editor, .markdown-preview-view {
    font-family: 'Georgia', serif;
    font-size: 17px;
    line-height: 1.8;
}
```

**作用：** 将编辑器和阅读视图切换为 Georgia 字体，字号 17px，行间距舒适。将 `'Georgia', serif` 替换为你系统上安装的任何字体——`'Inter'`、`'Fira Code'`、`'Merriweather'`——或者在导入后引用 Google 字体。

### 为你的 H1 标题着色

```css
/* header-colors.css */
.markdown-preview-view h1,
.cm-header-1 {
    color: #2e86ab;
    border-bottom: 2px solid #2e86ab;
    padding-bottom: 4px;
}
```

**作用：** 将 H1 标题设置为特定的十六进制颜色并添加底部边框下划线。将 `#2e86ab` 更改为任何你想要的十六进制颜色。你可以在 coolors.co 找到颜色选择器，或者直接在 Google 中搜索“十六进制颜色选择器”。

保存这两个文件，打开它们，你将立即看到变化。就是这样——你已经编写了你的第一个自定义 Obsidian CSS。

---

## 成为专业人士：使用开发者控制台查找任何元素 {#developer-console}

复制粘贴代码片段很有用。知道如何编写自己的代码片段可以让你完全掌控。开发者控制台是实现这一目标的工具，只需大约五分钟即可掌握其基础知识。

**打开控制台：** 按 `Ctrl+Shift+I` (Windows/Linux) 或 `Cmd+Opt+I` (Mac)。一个面板会打开——这与 Web 开发者每天使用的 Chrome DevTools 相同。

**使用元素选择器：** 在控制台面板的左上角，有一个光标在方框内的图标。点击它。现在将鼠标悬停在 Obsidian UI 的任何部分——侧边栏、笔记标题、标签、工具栏。当你点击一个元素时，控制台会跳转到该元素的 HTML。

**读取类名：** 在 HTML 窗格中，你会看到类似以下内容：

```html
<div class="nav-file-title tree-item-self is-clickable mod-active">
```

`class=` 后面的这些带连字符的单词就是你定位的 CSS 选择器。要样式化该元素，你可以这样写：

```css
.nav-file-title {
    color: red;
}
```

**编写你的规则：** 模板总是相同的：

```css
.selector-you-found {
    property: value;
}
```

如果你想学习此处示例之外的 CSS 属性，[Udemy 上的初学者 CSS 课程](URL_PLACEHOLDER_1)可以在一个周末内让你从零开始自信地编写规则。或者，[CSS Pocket Reference 书籍](URL_PLACEHOLDER_2)是快速查找属性的可靠案头伴侣。

---

## 10 个必备 CSS 代码片段来改变你的 Obsidian 库 {#10-essential-snippets}

下面的每个代码片段都已准备好复制。为每个代码片段创建一个单独的 `.css` 文件，以便你可以独立地切换它们。

### 代码片段 1：UI 和 UI Chrome 的自定义字体

```css
/* ui-font.css */
body {
    --font-interface: 'Inter', sans-serif;
    --font-text: 'Merriweather', serif;
    --font-monospace: 'Fira Code', monospace;
}
```

使用 Obsidian 自己的 CSS 变量进行干净、主题兼容的覆盖。

### 代码片段 2：带有渐变颜色的更美观标题

```css
/* headings.css */
.markdown-preview-view h1 { color: #e63946; font-size: 2em; }
.markdown-preview-view h2 { color: #457b9d; font-size: 1.6em; }
.markdown-preview-view h3 { color: #2a9d8f; font-size: 1.3em; }
```

每个标题级别都有其独特的颜色。阅读长文档时可以一目了然地进行视觉导航。

### 代码片段 3：极简主义 UI — 隐藏功能区和状态栏

```css
/* minimal-ui.css */
.workspace-ribbon { display: none; }
.status-bar { display: none; }
```

移除左侧功能区和底部状态栏，以获得干净、无干扰的写作界面。当你需要它们时，可以随时将其切换回来。

### 代码片段 4：自定义复选框样式

```css
/* checkboxes.css */
input[type="checkbox"]:checked + .task-list-item-checkbox {
    background-color: #2a9d8f;
    border-color: #2a9d8f;
}
.task-list-item.is-checked {
    color: #888;
    text-decoration: line-through;
}
```

将已完成任务的复选框变为青色，并将已完成任务文本灰色化。比默认设置更微妙，也更令人满意。

### 代码片段 5：更宽的笔记宽度以提高可读性

```css
/* wide-notes.css */
.markdown-preview-view,
.cm-editor .cm-content {
    max-width: 850px;
    margin: 0 auto;
}
```

许多主题的默认行宽约为 700px。将其增加到 850px，为表格和长行提供更多空间，而无需全宽显示。

### 代码片段 6：外部链接的独特样式

```css
/* external-links.css */
a.external-link {
    color: #e76f51;
    text-decoration: none;
    border-bottom: 1px dashed #e76f51;
}
a.external-link::after {
    content: " ↗";
    font-size: 0.8em;
}
```

外部链接变为橙色，带有虚线底线，并自动附加一个小箭头 ↗。内部链接保持不变。

### 代码片段 7：自定义标注框设计

```css
/* callouts.css */
.callout[data-callout="note"] {
    --callout-color: 46, 134, 171;
    --callout-icon: lucide-pencil;
}
.callout[data-callout="warning"] {
    background-color: rgba(231, 111, 81, 0.15);
    border-left: 4px solid #e76f51;
}
```

按名称定位特定标注类型。`data-callout` 属性与你在笔记中写入的类型（`> [!warning]`）匹配。

### 代码片段 8：更改图谱视图节点颜色

```css
/* graph.css */
.graph-view.color-fill { color: #2a9d8f; }
.graph-view.color-fill-tag { color: #e9c46a; }
.graph-view.color-fill-attachment { color: #e76f51; }
.graph-view.color-arrow { color: #457b9d; }
```

使图谱视图与你的配色方案匹配，而不是看起来像一个普通的网络图。

### 代码片段 9：阅读视图中的文本两端对齐

```css
/* justified-text.css */
.markdown-preview-view p {
    text-align: justify;
    hyphens: auto;
}
```

文本两端对齐并自动断字。看起来更像一本印刷书籍。个人偏好——有些人喜欢，有些人觉得它会增加不自然的间距。易于切换。

### 代码片段 10：更美观的 Kanban 插件列标题

```css
/* kanban.css */
.kanban-plugin__lane-title {
    font-size: 1.1em;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: #457b9d;
}
.kanban-plugin__lane {
    background-color: rgba(69, 123, 157, 0.05);
    border-radius: 8px;
}
```

为 Kanban 板提供更简洁的列标题和每列的微妙背景色。需要安装 [Kanban plugin](URL_PLACEHOLDER_3)。

---

## 故障排除：当你的代码片段不工作时 {#troubleshooting}

| 问题 | 症状 | 解决方法 |
|---|---|---|
| **错误的文件扩展名** | 代码片段未出现在 Obsidian 中 | 将 `.txt` 重命名为 `.css`。其他扩展名均无效。 |
| **语法错误** | 部分或全部规则被忽略 | 打开开发者控制台 → 控制台选项卡，查找红色 CSS 错误。检查是否缺少 `{`、`}` 或 `;`。 |
| **特异性冲突** | 规则看似正确但没有任何变化 | 你的主题规则优先于你的规则。在属性后添加 `!important`：`color: red !important;` |
| **缓存过期** | 保存后更改未出现 | 在 Obsidian 内部按 `Ctrl+R` / `Cmd+R` 强制重新加载。 |
| **错误的选择器** | 规则已加载但未定位到任何内容 | 使用开发者控制台重新检查。类名在不同主题之间可能有所不同。 |

**关于 `!important`：** 谨慎使用。它会覆盖所有其他规则，包括你将来编写的规则。仅当特定主题规则阻止你时才添加它，而不是作为一种默认习惯。

---

## 超越代码片段：何时使用完整的社区主题 {#beyond-snippets}

代码片段是手术刀，主题是建筑。以下是每种情况的适用场景：

**在以下情况使用代码片段：**
- 你喜欢当前主题的 90%，并想修正其余部分。
- 你需要一两个特定的行为更改。
- 你想要可移植的自定义，能够在主题更改后依然保留。

**在以下情况使用社区主题：**
- 你从头开始，希望从第一天起就拥有统一的视觉识别。
- 你想要专业设计的排版、图标集和配色系统，而无需编写一行 CSS。
- 你花费太多时间维护不断增长的代码片段。

最好的方法通常是**两者兼顾**：选择一个维护良好的社区主题，如 Minimal、AnuPpuccin 或 Things 作为你的基础，然后添加代码片段来处理那些主题未能完全满足你需求的地方。

在 **设置 → 外观 → 主题 → 管理** 中浏览社区主题。如果你想要一个带有内置高级自定义选项的优质专业设计的 Obsidian 主题，[Gumroad 上有几款](URL_PLACEHOLDER_4)来自专门从事 PKM 美学的独立设计师。

**比较：代码片段 vs. 社区主题**

| 因素 | CSS 代码片段 | 社区主题 |
|---|---|---|
| 设置时间 | 2–5 分钟 | 不到 1 分钟 |
| 更改范围 | 有针对性 | 彻底改造 |
| 所需 CSS 知识 | 复制粘贴只需少量，自定义需要更多 | 无 |
| 维护 | 低（你自己的代码） | 取决于主题作者 |
| 跨主题工作 | 是 | 替换主题 |
| 可移植性 | 高 | 中等 |

---

## 结论 {#conclusion}

CSS 代码片段是 Obsidian 中最被低估的强大功能。它们无需插件、无需主题、无需真正的编码知识即可上手——只需一个文本文件，以及粘贴四行代码并保存的意愿。从字体和标题代码片段开始，建立信心，然后通过 10 个必备代码片段了解其可能性，再使用开发者控制台技术解决 UI 中困扰你数月的问题。

`.obsidian/snippets` 文件夹是你的。尽情填充它吧。

---

**准备好深入学习了吗？** 如果你想从复制粘贴转变为从零开始编写自己的规则，[Udemy 上的这门初学者 CSS 课程](URL_PLACEHOLDER_1)是最快的结构化途径——大多数学生在几个小时内就能自信地编写 CSS。如果你决定更愿意从一个优质专业设计的 Obsidian 主题作为基础开始，[请查看这些 Gumroad 选项](URL_PLACEHOLDER_4)，它们专为 PKM 工作流而构建。无论哪种方式，你的库，你的规则。

---

## 常见问题

### 问：CSS 代码片段会破坏我的库或损坏我的笔记吗？

答：不会。代码片段只影响视觉渲染。你的实际笔记内容——Markdown 文本——完全不受影响。最糟糕的情况是出现难看的视觉效果，你可以通过关闭代码片段来修复。

### 问：代码片段会与 Obsidian Sync 同步吗？

答：会的。`.obsidian/snippets` 文件夹默认包含在 Obsidian Sync 中，因此你的自定义设置会随设备同步。

### 问：我可以在代码片段中使用 Google Fonts 吗？

答：可以，但需要额外一步。在你的代码片段文件顶部添加 `@import` 规则：`@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');` 然后在你的字体规则中引用 `'Inter'`。这需要在 Obsidian 每次加载时连接互联网。

### 问：当我切换社区主题时，我的代码片段会怎样？

答：大多数代码片段会继续工作，但某些选择器可能只在你的旧主题中存在。切换主题后，使用开发者控制台重新检查并更新任何损坏的选择器。

### 问：代码片段可以样式化 Dataview 查询结果吗？

答：当然。Dataview 表格会渲染为标准 HTML 表格，带有 `.dataview`、`.table-view-table` 和 `.dataview-result-list-ul` 等类。在开发者控制台中检查它们，并像样式化任何其他元素一样精确地样式化它们。

## 相关阅读

- [为什么你的主题是 Obsidian 中最重要的写作工具](/zh-cn/posts/best-obsidian-themes-for-writing-longform-content/)
- [什么是 Dataview？为何它能改变你的笔记管理方式？](/zh-cn/posts/how-to-use-obsidian-dataview-for-beginners/)
- [核心问题：Obsidian Sync 解决了什么问题？](/zh-cn/posts/is-obsidian-sync-worth-it-review/)
- [Obsidian Canvas 与 Excalidraw：哪个可视化工具更胜一筹？](/zh-cn/posts/obsidian-canvas-vs-excalidraw-for-mind-mapping/)
```
Attempt 1 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:08:25 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=6216',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': '2c22acf6a139236',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
Attempt 2 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:08:37 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=7133',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': 'f9858800482ea930',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
Attempt 3 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:08:58 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=8064',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': 'c009a6ed0c9bc6f1',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
Attempt 4 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:09:25 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=8046',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': '84302661b8380a7a',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
Attempt 5 failed with status 429. Retrying with backoff... _GaxiosError: [{
  "error": {
    "code": 429,
    "message": "No capacity available for model gemini-2.5-flash on the server",
    "errors": [
      {
        "message": "No capacity available for model gemini-2.5-flash on the server",
        "domain": "global",
        "reason": "rateLimitExceeded"
      }
    ],
    "status": "RESOURCE_EXHAUSTED",
    "details": [
      {
        "@type": "type.googleapis.com/google.rpc.ErrorInfo",
        "reason": "MODEL_CAPACITY_EXHAUSTED",
        "domain": "cloudcode-pa.googleapis.com",
        "metadata": {
          "model": "gemini-2.5-flash"
        }
      }
    ]
  }
}
]
    at Gaxios._request (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:8811:19)
    at process.processTicksAndRejections (node:internal/process/task_queues:104:5)
    at async _OAuth2Client.requestAsync (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:10774:16)
    at async CodeAssistServer.requestStreamingPost (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272945:17)
    at async CodeAssistServer.generateContentStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:272743:23)
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:273597:19
    at async file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:250407:23
    at async retryWithBackoff (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:270684:23)
    at async GeminiChat.makeApiCallAndProcessStream (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293631:28)
    at async GeminiChat.streamWithRetries (file:///Users/szp2005/.nvm/versions/node/v24.14.1/lib/node_modules/@google/gemini-cli/bundle/chunk-7VVHSNDQ.js:293450:29) {
  config: {
    url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
    method: 'POST',
    params: { alt: 'sse' },
    headers: {
      'Content-Type': 'application/json',
      'User-Agent': 'GeminiCLI-tui/0.42.0/gemini-2.5-flash (darwin; arm64; terminal) google-api-nodejs-client/9.15.1',
      Authorization: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      'x-goog-api-client': 'gl-node/24.14.1'
    },
    responseType: 'stream',
    body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
    signal: AbortSignal { aborted: false },
    retry: false,
    paramsSerializer: [Function: paramsSerializer],
    validateStatus: [Function: validateStatus],
    errorRedactor: [Function: defaultErrorRedactor]
  },
  response: {
    config: {
      url: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse',
      method: 'POST',
      params: [Object],
      headers: [Object],
      responseType: 'stream',
      body: '<<REDACTED> - See `errorRedactor` option in `gaxios` for configuration>.',
      signal: [AbortSignal],
      retry: false,
      paramsSerializer: [Function: paramsSerializer],
      validateStatus: [Function: validateStatus],
      errorRedactor: [Function: defaultErrorRedactor]
    },
    data: '[{\n' +
      '  "error": {\n' +
      '    "code": 429,\n' +
      '    "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '    "errors": [\n' +
      '      {\n' +
      '        "message": "No capacity available for model gemini-2.5-flash on the server",\n' +
      '        "domain": "global",\n' +
      '        "reason": "rateLimitExceeded"\n' +
      '      }\n' +
      '    ],\n' +
      '    "status": "RESOURCE_EXHAUSTED",\n' +
      '    "details": [\n' +
      '      {\n' +
      '        "@type": "type.googleapis.com/google.rpc.ErrorInfo",\n' +
      '        "reason": "MODEL_CAPACITY_EXHAUSTED",\n' +
      '        "domain": "cloudcode-pa.googleapis.com",\n' +
      '        "metadata": {\n' +
      '          "model": "gemini-2.5-flash"\n' +
      '        }\n' +
      '      }\n' +
      '    ]\n' +
      '  }\n' +
      '}\n' +
      ']',
    headers: {
      'alt-svc': 'h3=":443"; ma=2592000,h3-29=":443"; ma=2592000',
      'content-length': '612',
      'content-type': 'application/json; charset=UTF-8',
      date: 'Tue, 19 May 2026 12:10:00 GMT',
      server: 'ESF',
      'server-timing': 'gfet4t7; dur=6487',
      vary: 'Origin, X-Origin, Referer',
      'x-cloudaicompanion-trace-id': '31bcfca74ee9b5b4',
      'x-content-type-options': 'nosniff',
      'x-frame-options': 'SAMEORIGIN',
      'x-xss-protection': '0'
    },
    status: 429,
    statusText: 'Too Many Requests',
    request: {
      responseURL: 'https://cloudcode-pa.googleapis.com/v1internal:streamGenerateContent?alt=sse'
    }
  },
  error: undefined,
  status: 429,
  Symbol(gaxios-gaxios-error): '6.7.1'
}
```markdown
---
images: ["/og/how-to-customize-obsidian-appearance-with-css-snippets.webp"]
title: "Obsidian CSS 代码片段：掌控你的库外观"
author: "Alex Chen"
date: 2026-04-29
slug: how-to-customize-obsidian-appearance-with-css-snippets
description: "使用 CSS 代码片段自定义 Obsidian 外观，从设置和选择器到实用库样式调整的入门包。"
keywords: ["Obsidian CSS theme", "Obsidian vault appearance", "CSS snippets for Obsidian", "Obsidian custom theme", ".obsidian/snippets folder", "Obsidian developer console", "Change font in Obsidian", "Obsidian styling"]
draft: false
type: "informational"
tags: ["css", "snippets", "care", "how to customize obsidian appearance with css snippets"]
---

_作为亚马逊联盟成员，我们通过符合条件的购买赚取收益。此帖子可能包含联盟链接。_

# 如何使用 CSS 代码片段自定义 Obsidian 外观（完整指南 + 即用型入门包）

---

## TL;DR

- CSS 代码片段是位于你库的 `.obsidian/snippets` 文件夹中的小型 `.css` 文件，它们允许你在不修改主题的情况下更改特定的视觉元素。
- 你可以在不到一分钟的时间内，在 **设置 → 外观 → CSS 代码片段** 中启用、禁用和叠加多个代码片段。
- 开发者控制台（`Ctrl+Shift+I` / `Cmd+Opt+I`）允许你检查任何 UI 元素并找到其精确的 CSS 选择器，这样你就可以样式化 *任何东西* — 而不仅仅是其他人已记录的。

---

## 目录

1. [什么是 CSS 代码片段以及为何要关心它们？](#what-are-css-snippets)
2. [60 秒内完成设置：在你的库中启用 CSS 代码片段](#setup-in-60-seconds)
3. [你的第一次调整：字体和标题颜色更改](#your-first-tweak)
4. [成为专业人士：使用开发者控制台查找任何元素](#developer-console)
5. [10 个必备 CSS 代码片段来改变你的库](#10-essential-snippets)
6. [故障排除：当你的代码片段不工作时](#troubleshooting)
7. [超越代码片段：何时使用完整的社区主题](#beyond-snippets)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 什么是 CSS 代码片段以及为何要关心它们？ {#what-are-css-snippets}

Obsidian 使用浏览器引擎渲染你的笔记。这意味着你所看到的一切——字体、颜色、标题大小、标注框、侧边栏宽度——都由 CSS 控制，CSS 是一种与控制网站外观相同的样式语言。

**CSS 代码片段**是一个小型 `.css` 文件，包含一个或多个规则，用于覆盖你库中的特定样式。将其视为一次外科手术式的修正，而非移植。一个完整的社区主题会一次性替换所有内容——颜色、布局、排版、图标。而代码片段则微调一处。你想让 H1 标题呈现深青色？一个代码片段，四行代码。你想在专注模式下隐藏状态栏？另一个代码片段，两行。

**为什么代码片段在进行有针对性的更改时优于主题切换：**

- **精确性。** 你只更改困扰你的部分，而不影响其他一切。
- **可叠加。** 你可以同时运行 10 个代码片段，每个处理一个不同的元素。
- **主题无关。** 它们在任何社区主题之上运行。以 Minimal 主题为基础，再叠加你自己的调整。
- **零锁定。** 只需单击一下即可关闭任何代码片段。没有任何东西是永久的。

如果你曾安装过社区主题并觉得“除了那些丑陋的引用块，我喜欢所有一切”，那么代码片段就是答案。

---

## 60 秒内完成设置：在你的库中启用 CSS 代码片段 {#setup-in-60-seconds}

你无需接触终端或安装任何东西。

**步骤 1：** 打开 Obsidian 并按 `Ctrl+,` (Windows/Linux) 或 `Cmd+,` (Mac) 打开 **设置**。

**步骤 2：** 点击左侧边栏中的 **外观** 选项卡。

**步骤 3：** 滚动到外观页面底部，直到看到 **CSS 代码片段** 部分。点击旁边的 **文件夹图标**。这会直接在你系统文件管理器中打开 `.obsidian/snippets/` — 这是 Obsidian 查找代码片段文件的确切文件夹。

**步骤 4：** 在该文件夹内创建一个新文件。你可以随意命名——`my-fonts.css`、`header-styles.css`、`focus-mode.css`——但文件扩展名**必须是 `.css`**。在任何纯文本编辑器中打开该文件：Windows 上的记事本、Mac 上的 TextEdit（纯文本模式），或者如果你有 VS Code。

**步骤 5：** 将你的 CSS 规则粘贴到文件中并保存。回到 Obsidian 的外观设置中，点击 CSS 代码片段标题旁边的 **刷新图标**。你的新文件将出现在列表中，带有一个切换开关。将其打开。

这就是整个工作流程。每次你编辑代码片段文件并保存时，Obsidian 都会自动热重载它——你可以实时看到更改。

---

## 你的第一次调整：字体和标题颜色更改 {#your-first-tweak}

让我们在进行复杂内容之前建立信心。这里有两个代码片段，可以立即产生可见效果。

### 更改编辑器正文字体

```css
/* my-fonts.css */
.cm-editor, .markdown-preview-view {
    font-family: 'Georgia', serif;
    font-size: 17px;
    line-height: 1.8;
}
```

**作用：** 将编辑器和阅读视图切换为 Georgia 字体，字号 17px，行间距舒适。将 `'Georgia', serif` 替换为你系统上安装的任何字体——`'Inter'`、`'Fira Code'`、`'Merriweather'`——或者在导入后引用 Google 字体。

### 为你的 H1 标题着色

```css
/* header-colors.css */
.markdown-preview-view h1,
.cm-header-1 {
    color: #2e86ab;
    border-bottom: 2px solid #2e86ab;
    padding-bottom: 4px;
}
```

**作用：** 将 H1 标题设置为特定的十六进制颜色并添加底部边框下划线。将 `#2e86ab` 更改为任何你想要的十六进制颜色。你可以在 coolors.co 找到颜色选择器，或者直接在 Google 中搜索“十六进制颜色选择器”。

保存这两个文件，打开它们，你将立即看到变化。就是这样——你已经编写了你的第一个自定义 Obsidian CSS。

---

## 成为专业人士：使用开发者控制台查找任何元素 {#developer-console}

复制粘贴代码片段很有用。知道如何编写自己的代码片段可以让你完全掌控。开发者控制台是实现这一目标的工具，只需大约五分钟即可掌握其基础知识。

**打开控制台：** 按 `Ctrl+Shift+I` (Windows/Linux) 或 `Cmd+Opt+I` (Mac)。一个面板会打开——这与 Web 开发者每天使用的 Chrome DevTools 相同。

**使用元素选择器：** 在控制台面板的左上角，有一个光标在方框内的图标。点击它。现在将鼠标悬停在 Obsidian UI 的任何部分——侧边栏、笔记标题、标签、工具栏。当你点击一个元素时，控制台会跳转到该元素的 HTML。

**读取类名：** 在 HTML 窗格中，你会看到类似以下内容：

```html
<div class="nav-file-title tree-item-self is-clickable mod-active">
```

`class=` 后面的这些带连字符的单词就是你定位的 CSS 选择器。要样式化该元素，你可以这样写：

```css
.nav-file-title {
    color: red;
}
```

**编写你的规则：** 模板总是相同的：

```css
.selector-you-found {
    property: value;
}
```

如果你想学习此处示例之外的 CSS 属性，[Udemy 上的初学者 CSS 课程](URL_PLACEHOLDER_1)可以在一个周末内让你从零开始自信地编写规则。或者，[CSS Pocket Reference 书籍](URL_PLACEHOLDER_2)是快速查找属性的可靠案头伴侣。

---

## 10 个必备 CSS 代码片段来改变你的 Obsidian 库 {#10-essential-snippets}

下面的每个代码片段都已准备好复制。为每个代码片段创建一个单独的 `.css` 文件，以便你可以独立地切换它们。

### 代码片段 1：UI 和 UI Chrome 的自定义字体

```css
/* ui-font.css */
body {
    --font-interface: 'Inter', sans-serif;
    --font-text: 'Merriweather', serif;
    --font-monospace: 'Fira Code', monospace;
}
```

使用 Obsidian 自己的 CSS 变量进行干净、主题兼容的覆盖。

### 代码片段 2：带有渐变颜色的更美观标题

```css
/* headings.css */
.markdown-preview-view h1 { color: #e63946; font-size: 2em; }
.markdown-preview-view h2 { color: #457b9d; font-size: 1.6em; }
.markdown-preview-view h3 { color: #2a9d8f; font-size: 1.3em; }
```

每个标题级别都有其独特的颜色。阅读长文档时可以一目了然地进行视觉导航。

### 代码片段 3：极简主义 UI — 隐藏功能区和状态栏

```css
/* minimal-ui.css */
.workspace-ribbon { display: none; }
.status-bar { display: none; }
```

移除左侧功能区和底部状态栏，以获得干净、无干扰的写作界面。当你需要它们时，可以随时将其切换回来。

### 代码片段 4：自定义复选框样式

```css
/* checkboxes.css */
input[type="checkbox"]:checked + .task-list-item-checkbox {
    background-color: #2a9d8f;
    border-color: #2a9d8f;
}
.task-list-item.is-checked {
    color: #888;
    text-decoration: line-through;
}
```

将已完成任务的复选框变为青色，并将已完成任务文本灰色化。比默认设置更微妙，也更令人满意。

### 代码片段 5：更宽的笔记宽度以提高可读性

```css
/* wide-notes.css */
.markdown-preview-view,
.cm-editor .cm-content {
    max-width: 850px;
    margin: 0 auto;
}
```

许多主题的默认行宽约为 700px。将其增加到 850px，为表格和长行提供更多空间，而无需全宽显示。

### 代码片段 6：外部链接的独特样式

```css
/* external-links.css */
a.external-link {
    color: #e76f51;
    text-decoration: none;
    border-bottom: 1px dashed #e76f51;
}
a.external-link::after {
    content: " ↗";
    font-size: 0.8em;
}
```

外部链接变为橙色，带有虚线底线，并自动附加一个小箭头 ↗。内部链接保持不变。

### 代码片段 7：自定义标注框设计

```css
/* callouts.css */
.callout[data-callout="note"] {
    --callout-color: 46, 134, 171;
    --callout-icon: lucide-pencil;
}
.callout[data-callout="warning"] {
    background-color: rgba(231, 111, 81, 0.15);
    border-left: 4px solid #e76f51;
}
```

按名称定位特定标注类型。`data-callout` 属性与你在笔记中写入的类型（`> [!warning]`）匹配。

### 代码片段 8：更改图谱视图节点颜色

```css
/* graph.css */
.graph-view.color-fill { color: #2a9d8f; }
.graph-view.color-fill-tag { color: #e9c46a; }
.graph-view.color-fill-attachment { color: #e76f51; }
.graph-view.color-arrow { color: #457b9d; }
```

使图谱视图与你的配色方案匹配，而不是看起来像一个普通的网络图。

### 代码片段 9：阅读视图中的文本两端对齐

```css
/* justified-text.css */
.markdown-preview-view p {
    text-align: justify;
    hyphens: auto;
}
```

文本两端对齐并自动断字。看起来更像一本印刷书籍。个人偏好——有些人喜欢，有些人觉得它会增加不自然的间距。易于切换。

### 代码片段 10：更美观的 Kanban 插件列标题

```css
/* kanban.css */
.kanban-plugin__lane-title {
    font-size: 1.1em;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: #457b9d;
}
.kanban-plugin__lane {
    background-color: rgba(69, 123, 157, 0.05);
    border-radius: 8px;
}
```

为 Kanban 板提供更简洁的列标题和每列的微妙背景色。需要安装 [Kanban plugin](URL_PLACEHOLDER_3)。

---

## 故障排除：当你的代码片段不工作时 {#troubleshooting}

| 问题 | 症状 | 解决方法 |
|---|---|---|
| **错误的文件扩展名** | 代码片段未出现在 Obsidian 中 | 将 `.txt` 重命名为 `.css`。其他扩展名均无效。 |
| **语法错误** | 部分或全部规则被忽略 | 打开开发者控制台 → 控制台选项卡，查找红色 CSS 错误。检查是否缺少 `{`、`}` 或 `;`。 |
| **特异性冲突** | 规则看似正确但没有任何变化 | 你的主题规则优先于你的规则。在属性后添加 `!important`：`color: red !important;` |
| **缓存过期** | 保存后更改未出现 | 在 Obsidian 内部按 `Ctrl+R` / `Cmd+R` 强制重新加载。 |
| **错误的选择器** | 规则已加载但未定位到任何内容 | 使用开发者控制台重新检查。类名在不同主题之间可能有所不同。 |

**关于 `!important`：** 谨慎使用。它会覆盖所有其他规则，包括你将来编写的规则。仅当特定主题规则阻止你时才添加它，而不是作为一种默认习惯。

---

## 超越代码片段：何时使用完整的社区主题 {#beyond-snippets}

代码片段是手术刀，主题是建筑。以下是每种情况的适用场景：

**在以下情况使用代码片段：**
- 你喜欢当前主题的 90%，并想修正其余部分。
- 你需要一两个特定的行为更改。
- 你想要可移植的自定义，能够在主题更改后依然保留。

**在以下情况使用社区主题：**
- 你从头开始，希望从第一天起就拥有统一的视觉识别。
- 你想要专业设计的排版、图标集和配色系统，而无需编写一行 CSS。
- 你花费太多时间维护不断增长的代码片段。

最好的方法通常是**两者兼顾**：选择一个维护良好的社区主题，如 Minimal、AnuPpuccin 或 Things 作为你的基础，然后添加代码片段来处理那些主题未能完全满足你需求的地方。

在 **设置 → 外观 → 主题 → 管理** 中浏览社区主题。如果你想要一个带有内置高级自定义选项的优质专业设计的 Obsidian 主题，[Gumroad 上有几款](URL_PLACEHOLDER_4)来自专门从事 PKM 美学的独立设计师。

**比较：代码片段 vs. 社区主题**

| 因素 | CSS 代码片段 | 社区主题 |
|---|---|---|
| 设置时间 | 2–5 分钟 | 不到 1 分钟 |
| 更改范围 | 有针对性 | 彻底改造 |
| 所需 CSS 知识 | 复制粘贴只需少量，自定义需要更多 | 无 |
| 维护 | 低（你自己的代码） | 取决于主题作者 |
| 跨主题工作 | 是 | 替换主题 |
| 可移植性 | 高 | 中等 |

---

## 结论 {#conclusion}

CSS 代码片段是 Obsidian 中最被低估的强大功能。它们无需插件、无需主题、无需真正的编码知识即可上手——只需一个文本文件，以及粘贴四行代码并保存的意愿。从字体和标题代码片段开始，建立信心，然后通过 10 个必备代码片段了解其可能性，再使用开发者控制台技术解决 UI 中困扰你数月的问题。

`.obsidian/snippets` 文件夹是你的。尽情填充它吧。

---

**准备好深入学习了吗？** 如果你想从复制粘贴转变为从零开始编写自己的规则，[Udemy 上的这门初学者 CSS 课程](URL_PLACEHOLDER_1)是最快的结构化途径——大多数学生在几个小时内就能自信地编写 CSS。如果你决定更愿意从一个优质专业设计的 Obsidian 主题作为基础开始，[请查看这些 Gumroad 选项](URL_PLACEHOLDER_4)，它们专为 PKM 工作流而构建。无论哪种方式，你的库，你的规则。

---

## 常见问题

### 问：CSS 代码片段会破坏我的库或损坏我的笔记吗？

答：不会。代码片段只影响视觉渲染。你的实际笔记内容——Markdown 文本——完全不受影响。最糟糕的情况是出现难看的视觉效果，你可以通过关闭代码片段来修复。

### 问：代码片段会与 Obsidian Sync 同步吗？

答：会的。`.obsidian/snippets` 文件夹默认包含在 Obsidian Sync 中，因此你的自定义设置会随设备同步。

### 问：我可以在代码片段中使用 Google Fonts 吗？

答：可以，但需要额外一步。在你的代码片段文件顶部添加 `@import` 规则：`@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');` 然后在你的字体规则中引用 `'Inter'`。这需要在 Obsidian 每次加载时连接互联网。

### 问：当我切换社区主题时，我的代码片段会怎样？

答：大多数代码片段会继续工作，但某些选择器可能只在你的旧主题中存在。切换主题后，使用开发者控制台重新检查并更新任何损坏的选择器。

### 问：代码片段可以样式化 Dataview 查询结果吗？

答：当然。Dataview 表格会渲染为标准 HTML 表格，带有 `.dataview`、`.table-view-table` 和 `.dataview-result-list-ul` 等类。在开发者控制台中检查它们，并像样式化任何其他元素一样精确地样式化它们。

## 相关阅读

- [为什么你的主题是 Obsidian 中最重要的写作工具](/zh-cn/posts/best-obsidian-themes-for-writing-longform-content/)
- [什么是 Dataview？为何它能改变你的笔记管理方式？](/zh-cn/posts/how-to-use-obsidian-dataview-for-beginners/)
- [核心问题：Obsidian Sync 解决了什么问题？](/zh-cn/posts/is-obsidian-sync-worth-it-review/)
- [Obsidian Canvas 与 Excalidraw：哪个可视化工具更胜一筹？](/zh-cn/posts/obsidian-canvas-vs-excalidraw-for-mind-mapping/)
```