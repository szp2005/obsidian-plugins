I will translate the provided Markdown article from English to Simplified Chinese (zh-cn). My process will ensure strict adherence to all specified requirements, including preserving frontmatter structure, translating specific fields, maintaining Markdown formatting, avoiding translation of technical terms, remapping internal links, and keeping image paths intact.

I'll proceed with the following steps:
1.  **Translate Frontmatter**: Translate the 'title' and 'description' fields within the YAML frontmatter.
2.  **Translate Body Content**: Translate the main body of the article section by section, carefully preserving Markdown formatting, technical terms, and image paths.
3.  **Remap Internal Links**: Update all internal links of the format `/posts/slug` to `/zh-cn/posts/slug`.
4.  **Assemble Final Output**: Combine the translated frontmatter and body content, ensuring only the Markdown code is returned.
Here is the translated Markdown article, adhering to all the specified requirements:

```markdown
---
images: ["/og/how-to-sync-obsidian-with-google-drive-using-a-plugin.webp"]
title: "Obsidian Google Drive 同步：最佳免费插件设置指南"
author: "Alex Chen"
date: 2026-04-29
slug: how-to-sync-obsidian-with-google-drive-using-a-plugin
description: "为每个点击和配置步骤提供详细注释的截图，确保即使非技术用户也能轻松完成设置。"
keywords: ["Obsidian Remotely Save plugin", "Obsidian Google Drive integration", "free Obsidian sync", "Obsidian cross-device sync", "Obsidian community plugins", "set up Remotely Save Obsidian", "Obsidian sync tutorial", "Obsidian vault backup Google Drive"]
draft: false
type: "informational"
tags: ["sync", "obsidian", "google", "drive"]
---

_作为一名亚马逊联盟成员，我们可能从符合条件的购买中获得佣金。本文可能包含联盟链接。_

# 如何使用插件将 Obsidian 与 Google Drive 同步（免费、分步指南）

> **总结**
> - **Remotely Save** 社区插件可免费将您的 Obsidian 库连接到 Google Drive，无需付费订阅 Obsidian Sync。
> - 设置只需不到 10 分钟：安装插件、通过 Google 身份验证、运行首次同步，然后在每台设备上重复此操作。
> - 大多数常见错误（401 身份验证失败、同步冲突、移动文件缺失）都有简单的单步修复方法，下文将详细介绍。

---

## 目录

1. [为何要将 Obsidian 与 Google Drive 同步？](#why-sync)
2. [先决条件：您需要准备什么](#prerequisites)
3. [第 1 步：安装 Remotely Save 插件](#step-1)
4. [第 2 步：配置 Remotely Save 与 Google Drive](#step-2)
5. [第 3 步：运行首次同步并启用自动同步](#step-3)
6. [常见同步问题排查](#troubleshooting)
7. [专业提示：加密、同步间隔、忽略文件夹](#pro-tips)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 为何要将 Obsidian 与 Google Drive 同步？{#why-sync}

Obsidian 官方的 **Obsidian Sync** 服务每月费用为 4-8 美元。如果您想要一个省心的体验，这个价格是合理的，但它根据等级将存储限制在 1-10 GB，并将您的笔记绑定到 Obsidian 的服务器。对于大多数已经为 Google 存储付费的用户来说，这种经常性费用是不必要的。

以下是直接对比：

| 功能 | Obsidian Sync（付费） | Google Drive + Remotely Save（免费） |
|---|---|---|
| 月费 | $4–$8/月 | $0（使用现有 Drive 存储） |
| 包含存储 | 1–10 GB | 15 GB 免费（付费最高 2 TB） |
| 端到端加密 | 是（内置） | 可选（通过插件密码） |
| 同步插件设置 | 是 | 是（可配置） |
| 适用于 Android | 是 | 是 |
| 适用于 iOS | 是 | 是 |
| 版本历史 | 是（12 个月） | 通过 Google Drive 文件版本 |
| 设置复杂性 | 接近零 | 约 10 分钟 |

[Remotely Save 插件](URL_PLACEHOLDER_1) 是一个社区构建的开源插件，充当连接桥梁。它处理与 Google 的 OAuth 身份验证握手，管理文件差异，并按照您定义的时间表运行同步。您不会通过任何第三方服务器重新路由文件——您的库直接从您的设备传输到您的 Google Drive。

---

## 先决条件：您需要准备什么 {#prerequisites}

在更改任何插件设置之前，请确认您已具备以下条件：

- 一个拥有 Drive 访问权限的 **Google 帐户**。免费的 15 GB 空间对于大多数库来说已足够；大量附件用户可能需要扩展。
- 在您的 **主计算机上安装了 Obsidian**（Windows、macOS 或 Linux）。如果需要，可以从 [obsidian.md](URL_PLACEHOLDER_2) 下载。
- 在每台 **辅助设备上安装了 Obsidian**——Android 手机、iPhone、iPad、第二台笔记本电脑等。
- **社区插件已启用。** 默认情况下，Obsidian 以“受限模式”运行，这会阻止所有第三方插件。请前往 **设置 → 社区插件**，然后点击 **开启社区插件**。您会看到一次性关于第三方代码的警告——点击 **我了解** 继续。

> 💼 **高级用户提示：** 如果您为团队或小型企业管理笔记，并且需要超过 15 GB 的空间，[Google Workspace](URL_PLACEHOLDER_3) 的起价约为每月 6 美元/用户，每个帐户至少提供 30 GB 共享存储空间，以及共享云端硬盘和管理控制。如果您的库包含项目文档、客户文件或大型媒体附件，则值得升级。

---

## 第 1 步：安装 Remotely Save 社区插件 {#step-1}

1. 在您的 **桌面版** Obsidian 上打开（始终先在桌面版上配置，然后同步到移动设备）。
2. 点击左下角的 **齿轮图标** (⚙️) 打开 **设置**。
3. 在左侧边栏中，点击 **社区插件**。
4. 点击 **浏览** 按钮。社区插件浏览器随即打开。
5. 在顶部的搜索栏中，输入 **Remotely Save**。
6. **fyears** 开发的插件会出现在结果顶部。点击它。
7. 点击 **安装**。等待 3-5 秒完成下载。
8. 点击 **启用**。开关变为蓝色。

现在，您会在已安装插件列表中看到 **Remotely Save**。左侧功能区也会出现一个小云朵图标——这是您的手动同步触发器。

> ⚠️ 不要将“Remotely Save”与“Obsidian Git”或“Self-hosted LiveSync”等旧插件混淆。它们解决的是不同的问题。Remotely Save 是唯一一个原生支持 Google Drive OAuth 的插件。

---

## 第 2 步：配置 Remotely Save 与您的 Google Drive 帐户 {#step-2}

这是最重要的一步。请放慢速度。

1. 在 **设置** 中，向下滚动左侧边栏，直到在“插件选项”部分下看到 **Remotely Save**。点击它。
2. 在插件设置顶部，找到 **远程服务** 下拉菜单。它默认为 **Dropbox**。点击下拉菜单并选择 **Google Drive (GDrive)**。
3. 下拉菜单下方会出现一个名为 **Google Drive** 的新部分。
4. 点击 **身份验证** 按钮（标签可能类似“点击以向 Google Drive 进行身份验证”）。您的默认网页浏览器将打开并加载一个 Google OAuth 同意屏幕。
5. **登录** 到您希望存储库的 Google 帐户。
6. Google 将显示一个权限屏幕，列出 Remotely Save 请求的访问权限——特别是对它在 Drive 中创建的文件的读写权限。点击 **允许**。
7. 浏览器将显示一个简短的确认码或成功消息。如果提示，请复制该代码。
8. 切换回 Obsidian。如果要求，请将代码粘贴到确认字段中，然后点击 **提交** 或 **确认**。
9. 返回插件设置，您将看到一个绿色指示器或文本说明，确认身份验证已激活。

**在 Drive 中选择您的库文件夹：**

在插件设置中，查找标记为 **“Remotely Save 文件夹”** 或 **“远程基础目录”** 的字段。默认情况下，此设置是您的库名称。除非您有特定的理由重命名它，否则请保持不变。此文件夹将出现在您的 Google Drive 中一个名为 `remotely-save` 的顶级文件夹内。

---

## 第 3 步：运行首次同步并启用自动同步 {#step-3}

### 手动同步（请先执行此操作）

点击左侧功能区中的 **云朵图标**，或打开命令面板（**Ctrl/Cmd + P**）并搜索 **“Remotely Save: 开始同步”**。点击它。

观察 Obsidian 窗口底部的状态栏。您会看到一个旋转指示器，然后是带有文件计数的完成消息。对于一个包含 500 个笔记的库，首次同步通常需要 30-90 秒，具体取决于您的网络速度。

在浏览器中打开 **Google Drive**，并导航到 **我的云端硬盘 → remotely-save → [您的库名称]**。您的 `.md` 文件应该会立即出现在那里。

### 启用自动同步

回到 **Remotely Save 设置**：

- **每隔 X 分钟自动运行：** 将此设置为 `5` 以实现近乎实时的同步。如果您使用的是按流量计费的网络连接或对电池敏感的移动设备，请将其设置为 `30`。
- **保存时同步（文件修改后）：** 如果您希望每次保存都自动触发同步，请启用此开关。这很方便，但全天会产生更多的 Drive API 调用。
- **启动时同步：** 启用此功能，以便插件在您打开 Obsidian 的那一刻拉取在其他设备上所做的任何更改。

### 在其他设备上重复操作

在您的手机或第二台计算机上安装 Obsidian。创建一个 **新的本地库**（不要打开现有库）。使用上述相同的步骤安装 **Remotely Save**。使用 **相同的 Google 帐户** 进行身份验证。在 **远程基础目录** 字段中，输入您在第一台设备上使用的 **完全相同的文件夹名称**。运行手动同步。您的笔记将随即填充。

---

## 常见同步问题排查 {#troubleshooting}

### 401 身份验证错误

**症状：** 同步在错误日志中显示“401 未授权”并立即失败。

**修复：** 进入 Remotely Save 设置，找到 Google Drive 部分，点击 **撤销身份验证**，然后从头开始重新进行身份验证。这通常发生在 Google 使 OAuth 令牌失效时——在密码更改后或身份验证超过 6 个月后很常见。

### 同步冲突 / 文件重复

**症状：** 您看到的文件名称类似 `note (conflict 2024-01-15).md`。

**修复：** Remotely Save 会创建冲突副本而不是静默覆盖。打开这两个文件，手动合并您想要保留的内容，然后删除冲突副本。为了防止这种情况，请启用 **启动时同步**，这样您的设备在开始写入之前始终会拉取最新版本。

### 文件未在移动设备上显示

**症状：** 同步在桌面设备上完成，但您的手机显示空库或旧文件。

**修复：** 在移动设备上，打开 Remotely Save 设置并验证 **远程基础目录** 是否与您的桌面设置完全匹配——包括大小写。即使一个字符不匹配也会在 Drive 中创建一个新的空文件夹，而不是从正确的文件夹读取。

### 大文件附件导致同步停滞

**症状：** 当您将图片、PDF 或音频文件添加到库时，同步会卡住。

**修复：** 在 Remotely Save 设置中，找到 **“跳过大文件”** 选项并设置一个大小限制（例如，5 MB）。将大型附件外部存储并链接到它们。或者，创建一个 `Attachments` 子文件夹并将其添加到 **忽略路径** 列表中（请参阅下面的专业提示）。

---

## 专业提示：加密、同步间隔、忽略文件夹 {#pro-tips}

**启用端到端加密：** 在 Remotely Save 设置中，在 **“加密密码”** 字段中输入密码短语。文件在离开您的设备之前会在客户端进行加密。Google 只存储密文——即使 Google 也无法读取您的笔记。请记下此密码短语；丢失它意味着永久丢失对加密文件的访问权限。

**调整同步间隔：** 默认设置通常为 0（仅手动）。将其设置为 5 分钟对于大多数用户来说是最佳选择。在数据受限的移动设备上，请使用 30 分钟。

**忽略特定文件夹：** 将文件夹路径添加到设置中的 **“忽略路径”** 字段。这对于大型附件文件夹、模板库或插件缓存很有用。格式：每行一个文件夹名称，没有前导斜杠。

**验证同步完整性：** 在大量笔记转储或迁移后，打开 Remotely Save 日志（通过命令面板 → “Remotely Save: 查看日志”访问），并确认每个文件都显示成功上传状态，而不是跳过或错误。

**不要同时使用基于文件夹的 Google Drive 桌面客户端：** 如果您运行着 Google Drive 桌面应用并指向相同的库文件夹，则存在双重同步和创建冲突的风险。让 Remotely Save 成为您库文件夹的唯一同步机制。

---

## 结论 {#conclusion}

使用 Remotely Save 将 Obsidian 与 Google Drive 同步是当今最实用的免费同步解决方案。您可以获得自动跨设备同步、可选的零知识加密以及对数据完全控制——所有这些都无需每月订阅。

整个过程只需 10 分钟：安装 Remotely Save，通过 Google 身份验证，设置自动同步间隔，然后在每台设备上重复相同的远程基础目录名称。如果出现任何问题，90% 的问题都可以追溯到 OAuth 令牌过期（重新进行身份验证）或文件夹名称不匹配（检查大小写）。

**准备好更进一步了吗？** 从 [Obsidian 社区插件浏览器](URL_PLACEHOLDER_5) 安装 Remotely Save，将其与 [Google Workspace 帐户](URL_PLACEHOLDER_6) 结合使用以获取扩展存储和团队共享，或者如果您想要一个免 Google、端到端加密的替代方案，可以探索 [pCloud](URL_PLACEHOLDER_7)。您的笔记，您的基础设施，您的规则。

---

## 常见问题

### 将 Obsidian 与 Google Drive 同步安全吗？

您的文件通过 HTTPS 传输到 Google Drive，并使用 Google 的标准静态加密存储。如果您想要零知识加密——意味着即使 Google 也无法读取您的笔记——请在 Remotely Save 中启用密码短语选项。设置了强密码短语后，您的库就像您的密码管理器一样安全。

### 这适用于 Android 和 iOS 吗？

是的。Remotely Save 通过 Obsidian 移动应用程序支持 Android 和 iOS。两个平台上的设置过程完全相同。iOS 用户应注意，后台同步受 iOS 应用生命周期规则的限制——打开应用以触发同步。

### Remotely Save 会同步插件设置和主题吗？

默认情况下，它会同步整个库，包括包含您的插件配置、主题和快捷键的 `.obsidian` 文件夹。如果您希望在每个设备上单独管理设置，可以使用“忽略路径”设置将其排除。

### 如果我的 Google Drive 存储空间不足会怎样？

同步将因存储配额错误而失败。Remotely Save 将记录错误，而不是静默跳过文件。腾出 Drive 空间，或升级您的 Google 存储。如果您根本不想使用 Google 的生态系统，[pCloud](URL_PLACEHOLDER_4) 是一个强大的注重隐私的替代方案——它提供开箱即用的端到端加密存储和终身计划选项，并且 Remotely Save 支持它作为 WebDAV 后端。

### 我可以将多个库同步到同一个 Google Drive 帐户吗？

是的。为每个库设置一个唯一的 **远程基础目录** 名称。它们将作为单独的子文件夹出现在您 Drive 中的 `remotely-save` 文件夹内。它们之间不会相互干扰。

## 相关阅读

- [核心问题：Obsidian Sync 解决了什么问题？](/zh-cn/posts/is-obsidian-sync-worth-it-review/)
- [什么是 Excalidraw 以及为何在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为何在 Obsidian 中构建卡片盒笔记法？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [为何要在 2024 年在 Obsidian 中追踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
```

```markdown
---
images: ["/og/how-to-sync-obsidian-with-google-drive-using-a-plugin.webp"]
title: "Obsidian Google Drive 同步：最佳免费插件设置指南"
author: "Alex Chen"
date: 2026-04-29
slug: how-to-sync-obsidian-with-google-drive-using-a-plugin
description: "为每个点击和配置步骤提供详细注释的截图，确保即使非技术用户也能轻松完成设置。"
keywords: ["Obsidian Remotely Save plugin", "Obsidian Google Drive integration", "free Obsidian sync", "Obsidian cross-device sync", "Obsidian community plugins", "set up Remotely Save Obsidian", "Obsidian sync tutorial", "Obsidian vault backup Google Drive"]
draft: false
type: "informational"
tags: ["sync", "obsidian", "google", "drive"]
---

_作为一名亚马逊联盟成员，我们可能从符合条件的购买中获得佣金。本文可能包含联盟链接。_

# 如何使用插件将 Obsidian 与 Google Drive 同步（免费、分步指南）

> **总结**
> - **Remotely Save** 社区插件可免费将您的 Obsidian 库连接到 Google Drive，无需付费订阅 Obsidian Sync。
> - 设置只需不到 10 分钟：安装插件、通过 Google 身份验证、运行首次同步，然后在每台设备上重复此操作。
> - 大多数常见错误（401 身份验证失败、同步冲突、移动文件缺失）都有简单的单步修复方法，下文将详细介绍。

---

## 目录

1. [为何要将 Obsidian 与 Google Drive 同步？](#why-sync)
2. [先决条件：您需要准备什么](#prerequisites)
3. [第 1 步：安装 Remotely Save 插件](#step-1)
4. [第 2 步：配置 Remotely Save 与 Google Drive](#step-2)
5. [第 3 步：运行首次同步并启用自动同步](#step-3)
6. [常见同步问题排查](#troubleshooting)
7. [专业提示：加密、同步间隔、忽略文件夹](#pro-tips)
8. [常见问题](#faq)
9. [结论](#conclusion)

---

## 为何要将 Obsidian 与 Google Drive 同步？{#why-sync}

Obsidian 官方的 **Obsidian Sync** 服务每月费用为 4-8 美元。如果您想要一个省心的体验，这个价格是合理的，但它根据等级将存储限制在 1-10 GB，并将您的笔记绑定到 Obsidian 的服务器。对于大多数已经为 Google 存储付费的用户来说，这种经常性费用是不必要的。

以下是直接对比：

| 功能 | Obsidian Sync（付费） | Google Drive + Remotely Save（免费） |
|---|---|---|
| 月费 | $4–$8/月 | $0（使用现有 Drive 存储） |
| 包含存储 | 1–10 GB | 15 GB 免费（付费最高 2 TB） |
| 端到端加密 | 是（内置） | 可选（通过插件密码） |
| 同步插件设置 | 是 | 是（可配置） |
| 适用于 Android | 是 | 是 |
| 适用于 iOS | 是 | 是 |
| 版本历史 | 是（12 个月） | 通过 Google Drive 文件版本 |
| 设置复杂性 | 接近零 | 约 10 分钟 |

[Remotely Save 插件](URL_PLACEHOLDER_1) 是一个社区构建的开源插件，充当连接桥梁。它处理与 Google 的 OAuth 身份验证握手，管理文件差异，并按照您定义的时间表运行同步。您不会通过任何第三方服务器重新路由文件——您的库直接从您的设备传输到您的 Google Drive。

---

## 先决条件：您需要准备什么 {#prerequisites}

在更改任何插件设置之前，请确认您已具备以下条件：

- 一个拥有 Drive 访问权限的 **Google 帐户**。免费的 15 GB 空间对于大多数库来说已足够；大量附件用户可能需要扩展。
- 在您的 **主计算机上安装了 Obsidian**（Windows、macOS 或 Linux）。如果需要，可以从 [obsidian.md](URL_PLACEHOLDER_2) 下载。
- 在每台 **辅助设备上安装了 Obsidian**——Android 手机、iPhone、iPad、第二台笔记本电脑等。
- **社区插件已启用。** 默认情况下，Obsidian 以“受限模式”运行，这会阻止所有第三方插件。请前往 **设置 → 社区插件**，然后点击 **开启社区插件**。您会看到一次性关于第三方代码的警告——点击 **我了解** 继续。

> 💼 **高级用户提示：** 如果您为团队或小型企业管理笔记，并且需要超过 15 GB 的空间，[Google Workspace](URL_PLACEHOLDER_3) 的起价约为每月 6 美元/用户，每个帐户至少提供 30 GB 共享存储空间，以及共享云端硬盘和管理控制。如果您的库包含项目文档、客户文件或大型媒体附件，则值得升级。

---

## 第 1 步：安装 Remotely Save 社区插件 {#step-1}

1. 在您的 **桌面版** Obsidian 上打开（始终先在桌面版上配置，然后同步到移动设备）。
2. 点击左下角的 **齿轮图标** (⚙️) 打开 **设置**。
3. 在左侧边栏中，点击 **社区插件**。
4. 点击 **浏览** 按钮。社区插件浏览器随即打开。
5. 在顶部的搜索栏中，输入 **Remotely Save**。
6. **fyears** 开发的插件会出现在结果顶部。点击它。
7. 点击 **安装**。等待 3-5 秒完成下载。
8. 点击 **启用**。开关变为蓝色。

现在，您会在已安装插件列表中看到 **Remotely Save**。左侧功能区也会出现一个小云朵图标——这是您的手动同步触发器。

> ⚠️ 不要将“Remotely Save”与“Obsidian Git”或“Self-hosted LiveSync”等旧插件混淆。它们解决的是不同的问题。Remotely Save 是唯一一个原生支持 Google Drive OAuth 的插件。

---

## 第 2 步：配置 Remotely Save 与您的 Google Drive 帐户 {#step-2}

这是最重要的一步。请放慢速度。

1. 在 **设置** 中，向下滚动左侧边栏，直到在“插件选项”部分下看到 **Remotely Save**。点击它。
2. 在插件设置顶部，找到 **远程服务** 下拉菜单。它默认为 **Dropbox**。点击下拉菜单并选择 **Google Drive (GDrive)**。
3. 下拉菜单下方会出现一个名为 **Google Drive** 的新部分。
4. 点击 **身份验证** 按钮（标签可能类似“点击以向 Google Drive 进行身份验证”）。您的默认网页浏览器将打开并加载一个 Google OAuth 同意屏幕。
5. **登录** 到您希望存储库的 Google 帐户。
6. Google 将显示一个权限屏幕，列出 Remotely Save 请求的访问权限——特别是对它在 Drive 中创建的文件的读写权限。点击 **允许**。
7. 浏览器将显示一个简短的确认码或成功消息。如果提示，请复制该代码。
8. 切换回 Obsidian。如果要求，请将代码粘贴到确认字段中，然后点击 **提交** 或 **确认**。
9. 返回插件设置，您将看到一个绿色指示器或文本说明，确认身份验证已激活。

**在 Drive 中选择您的库文件夹：**

在插件设置中，查找标记为 **“Remotely Save 文件夹”** 或 **“远程基础目录”** 的字段。默认情况下，此设置是您的库名称。除非您有特定的理由重命名它，否则请保持不变。此文件夹将出现在您的 Google Drive 中一个名为 `remotely-save` 的顶级文件夹内。

---

## 第 3 步：运行首次同步并启用自动同步 {#step-3}

### 手动同步（请先执行此操作）

点击左侧功能区中的 **云朵图标**，或打开命令面板（**Ctrl/Cmd + P**）并搜索 **“Remotely Save: 开始同步”**。点击它。

观察 Obsidian 窗口底部的状态栏。您会看到一个旋转指示器，然后是带有文件计数的完成消息。对于一个包含 500 个笔记的库，首次同步通常需要 30-90 秒，具体取决于您的网络速度。

在浏览器中打开 **Google Drive**，并导航到 **我的云端硬盘 → remotely-save → [您的库名称]**。您的 `.md` 文件应该会立即出现在那里。

### 启用自动同步

回到 **Remotely Save 设置**：

- **每隔 X 分钟自动运行：** 将此设置为 `5` 以实现近乎实时的同步。如果您使用的是按流量计费的网络连接或对电池敏感的移动设备，请将其设置为 `30`。
- **保存时同步（文件修改后）：** 如果您希望每次保存都自动触发同步，请启用此开关。这很方便，但全天会产生更多的 Drive API 调用。
- **启动时同步：** 启用此功能，以便插件在您打开 Obsidian 的那一刻拉取在其他设备上所做的任何更改。

### 在其他设备上重复操作

在您的手机或第二台计算机上安装 Obsidian。创建一个 **新的本地库**（不要打开现有库）。使用上述相同的步骤安装 **Remotely Save**。使用 **相同的 Google 帐户** 进行身份验证。在 **远程基础目录** 字段中，输入您在第一台设备上使用的 **完全相同的文件夹名称**。运行手动同步。您的笔记将随即填充。

---

## 常见同步问题排查 {#troubleshooting}

### 401 身份验证错误

**症状：** 同步在错误日志中显示“401 未授权”并立即失败。

**修复：** 进入 Remotely Save 设置，找到 Google Drive 部分，点击 **撤销身份验证**，然后从头开始重新进行身份验证。这通常发生在 Google 使 OAuth 令牌失效时——在密码更改后或身份验证超过 6 个月后很常见。

### 同步冲突 / 文件重复

**症状：** 您看到的文件名称类似 `note (conflict 2024-01-15).md`。

**修复：** Remotely Save 会创建冲突副本而不是静默覆盖。打开这两个文件，手动合并您想要保留的内容，然后删除冲突副本。为了防止这种情况，请启用 **启动时同步**，这样您的设备在开始写入之前始终会拉取最新版本。

### 文件未在移动设备上显示

**症状：** 同步在桌面设备上完成，但您的手机显示空库或旧文件。

**修复：：** 在移动设备上，打开 Remotely Save 设置并验证 **远程基础目录** 是否与您的桌面设置完全匹配——包括大小写。即使一个字符不匹配也会在 Drive 中创建一个新的空文件夹，而不是从正确的文件夹读取。

### 大文件附件导致同步停滞

**症状：** 当您将图片、PDF 或音频文件添加到库时，同步会卡住。

**修复：** 在 Remotely Save 设置中，找到 **“跳过大文件”** 选项并设置一个大小限制（例如，5 MB）。将大型附件外部存储并链接到它们。或者，创建一个 `Attachments` 子文件夹并将其添加到 **忽略路径** 列表中（请参阅下面的专业提示）。

---

## 专业提示：加密、同步间隔、忽略文件夹 {#pro-tips}

**启用端到端加密：** 在 Remotely Save 设置中，在 **“加密密码”** 字段中输入密码短语。文件在离开您的设备之前会在客户端进行加密。Google 只存储密文——即使 Google 也无法读取您的笔记。请记下此密码短语；丢失它意味着永久丢失对加密文件的访问权限。

**调整同步间隔：** 默认设置通常为 0（仅手动）。将其设置为 5 分钟对于大多数用户来说是最佳选择。在数据受限的移动设备上，请使用 30 分钟。

**忽略特定文件夹：** 将文件夹路径添加到设置中的 **“忽略路径”** 字段。这对于大型附件文件夹、模板库或插件缓存很有用。格式：每行一个文件夹名称，没有前导斜杠。

**验证同步完整性：** 在大量笔记转储或迁移后，打开 Remotely Save 日志（通过命令面板 → “Remotely Save: 查看日志”访问），并确认每个文件都显示成功上传状态，而不是跳过或错误。

**不要同时使用基于文件夹的 Google Drive 桌面客户端：** 如果您运行着 Google Drive 桌面应用并指向相同的库文件夹，则存在双重同步和创建冲突的风险。让 Remotely Save 成为您库文件夹的唯一同步机制。

---

## 结论 {#conclusion}

使用 Remotely Save 将 Obsidian 与 Google Drive 同步是当今最实用的免费同步解决方案。您可以获得自动跨设备同步、可选的零知识加密以及对数据完全控制——所有这些都无需每月订阅。

整个过程只需 10 分钟：安装 Remotely Save，通过 Google 身份验证，设置自动同步间隔，然后在每台设备上重复相同的远程基础目录名称。如果出现任何问题，90% 的问题都可以追溯到 OAuth 令牌过期（重新进行身份验证）或文件夹名称不匹配（检查大小写）。

**准备好更进一步了吗？** 从 [Obsidian 社区插件浏览器](URL_PLACEHOLDER_5) 安装 Remotely Save，将其与 [Google Workspace 帐户](URL_PLACEHOLDER_6) 结合使用以获取扩展存储和团队共享，或者如果您想要一个免 Google、端到端加密的替代方案，可以探索 [pCloud](URL_PLACEHOLDER_7)。您的笔记，您的基础设施，您的规则。

---

## 常见问题

### 将 Obsidian 与 Google Drive 同步安全吗？

您的文件通过 HTTPS 传输到 Google Drive，并使用 Google 的标准静态加密存储。如果您想要零知识加密——意味着即使 Google 也无法读取您的笔记——请在 Remotely Save 中启用密码短语选项。设置了强密码短语后，您的库就像您的密码管理器一样安全。

### 这适用于 Android 和 iOS 吗？

是的。Remotely Save 通过 Obsidian 移动应用程序支持 Android 和 iOS。两个平台上的设置过程完全相同。iOS 用户应注意，后台同步受 iOS 应用生命周期规则的限制——打开应用以触发同步。

### Remotely Save 会同步插件设置和主题吗？

默认情况下，它会同步整个库，包括包含您的插件配置、主题和快捷键的 `.obsidian` 文件夹。如果您希望在每个设备上单独管理设置，可以使用“忽略路径”设置将其排除。

### 如果我的 Google Drive 存储空间不足会怎样？

同步将因存储配额错误而失败。Remotely Save 将记录错误，而不是静默跳过文件。腾出 Drive 空间，或升级您的 Google 存储。如果您根本不想使用 Google 的生态系统，[pCloud](URL_PLACEHOLDER_4) 是一个强大的注重隐私的替代方案——它提供开箱即用的端到端加密存储和终身计划选项，并且 Remotely Save 支持它作为 WebDAV 后端。

### 我可以将多个库同步到同一个 Google Drive 帐户吗？

是的。为每个库设置一个唯一的 **远程基础目录** 名称。它们将作为单独的子文件夹出现在您 Drive 中的 `remotely-save` 文件夹内。它们之间不会相互干扰。

## 相关阅读

- [核心问题：Obsidian Sync 解决了什么问题？](/zh-cn/posts/is-obsidian-sync-worth-it-review/)
- [什么是 Excalidraw 以及为何在 Obsidian 中使用它？](/zh-cn/posts/excalidraw-plugin-for-obsidian-review/)
- [为何在 Obsidian 中构建卡片盒笔记法？](/zh-cn/posts/setting-up-a-zettelkasten-in-obsidian-with-plugins/)
- [为何要在 2024 年在 Obsidian 中追踪习惯？](/zh-cn/posts/best-obsidian-plugins-for-habit-tracking-2024/)
```