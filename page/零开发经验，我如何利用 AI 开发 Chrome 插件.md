通过利用 AI 技术，我成功开发了一个 Chrome 插件，实现了在浏览器上直接做笔记并同步至 Obsidian 的功能。以下是整个开发过程的详细分享，以及相关工具和经验。

## 0. 发现自己的需求

在梳理知识管理系统时，我发现自己习惯于将笔记剪藏到软件中，但很少再去阅读和消化。稍后读软件（如简悦、Cubox、Readwise）虽然支持划线和笔记功能，但并不适合卡片笔记的需求。主要问题包括：

1. **样式问题**：原文样式可能丢失，重新渲染的样式在某些网站上可能很丑。
2. **不适合卡片笔记**：划线+笔记的模式不利于用自己的话总结内容。
3. **联动 Obsidian 步骤繁琐**：虽然 Cubox 支持自定义动作保存划线到 Obsidian，但操作仍然不够便捷。

因此，我希望能在浏览器中直接写笔记，并同步到 Obsidian。

## 1. 用 Google 和 GPT 寻找解决方案

为实现这一目标，我尝试了以下方法：

1. 使用分屏软件（如 Chrome + 备忘录/Obsidian/Drafts）。
2. 使用支持分屏的浏览器（如 Arc + flomo）。
3. 使用 Chrome 插件分屏（如 Anything Copilot 插件 + flomo）。

最终，我选择开发一个 Chrome 插件，直接将笔记同步到 Obsidian。通过 Google 搜索，我发现了一个名为 [obsidian-local-rest-api](https://github.com/coddingtonbear/obsidian-local-rest-api) 的项目，刚好符合我的需求。

## 2. 使用 AI 编写插件代码

### 2.1 使用 GPT-4 完成 0.1 版本

我通过 GPT-4 获取了 Chrome 插件的项目结构和代码模板，并在本地使用 VS Code 创建了项目目录。

### 2.2 使用 GPT 和 Claude 的几点经验

- **联网能力**：GPT 支持联网，能够直接读取第三方文档作为参考；Claude 则需要手动提供文档内容。
- **编程能力**：Claude 的代码错误率较低，输出简洁；GPT-4 偏好输出完整代码，可能超出 Token 限制。
- **提供清晰范例**：为 AI 提供官方文档、示例代码或界面截图，可以提高代码的准确性。

## 3. 测试和修改程序

AI 生成的代码可能存在 Bug，需要不断调试。调试时，尽量清楚地描述环境、操作步骤、结果和期望结果，并提供截图，类似于 QA 提 Bug 的方式。

## 4. 发布插件到 Github

完成插件开发后，可以将其发布到 Github，与他人分享。学习使用 Git 和 Github 是一个重要的技能，可以通过以下 Prompt 向 AI 学习：


我有一个 Chrome 插件开发好了，我想把它发布到 Github 上该如何操作，一步一步教我。


此外，可以让 AI 帮助改写 README 文件，支持中英文双语或多语言版本。

## 5. 发布到 Chrome 扩展商店

如果希望将插件发布到 Chrome 扩展商店，需要注册开发者账号（费用 $5）。以下是发布流程的关键点：

1. 准备隐私声明网页（可使用 Vercel 部署）。
2. 上传插件的 Logo 和截图（尺寸需符合要求）。
3. 提交插件并等待审核（通常 2 个工作日）。

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)

## 6. 最后

通过这个项目，我不仅掌握了 Chrome 插件的开发流程，还体验到了利用 AI 工具简化开发的乐趣。如果你也对这个插件感兴趣，可以访问以下页面下载使用：

- [Chrome 商店版本](https://chromewebstore.google.com/detail/simple-obsidian-note-exte/flohnmomnafamkgbjonnjcjggkhiokkn)
- [Github 地址](https://github.com/moyuguy/sidenote2obsidian)