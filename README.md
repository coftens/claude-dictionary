# 🔮 Claude Code 动画魔法词典 (Claude Code Spinner Dictionary)

[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

一个专为 `claude-code` CLI 用户打造的 **加载动画（Spinner）状态词典网页**。它完美收录了官方内置的 **185 个进行时动词** 以及任务结束结算时才会出现的 **8 个过去式状态词**（共 193 个），并为每一个硬核或摸鱼的状态提供了极其贴合 AI 结对编程（Pair Programming）语境的趣味翻译和极客梗解。

> **💡 为什么做这个项目？**
>
> Anthropic 的前端工程师为了缓解开发者在等待大语言模型（LLM）生成复杂代码时的焦虑感，专门设计了名为 `"Enchanted Wait States"（魔法等待状态）` 的机制。工具会随机呈现一系列带有点“人类极客幽默”的动词。本项目的目的就是让你在终端看到任何奇怪的 `-ing` 晃过去时，都能一秒看懂这个 AI 此时此刻正在背着你耍什么宝。

---

## ✨ 项目亮点

- **🎯 全网最全词库**：完美集成 185 个 Running 状态词 + 8 个 Done 结算词。
- **🔍 多维度模糊搜索**：支持同时检索 **英文原词、中文释义、分类标签、AI 摸鱼黑话**。
  - *查单词*：输入 `bak` 🔍 弹出 `Baking`（代码正在烤箱里烤着呢）。
  - *查黑话*：输入 `带薪摸鱼` 🔍 瞬间聚合 `Boondoggling` 等所有相关的幽默卡片。
  - *按分类*：输入 `高级科幻` 或 `厨房重地` 🔍 精确过滤相同设计风格的状态词。
- **🖍️ 实时高亮反馈**：搜索关键字在卡片结果中实时加亮，快速抓取关键信息。
- **🍃 单文件零配置 (Zero Dependencies)**：纯原生 HTML/CSS/JS 编写，无需打包工具，无需安装任何依赖，**下载即开即用**。

---

## 📸 界面预览与分类一览

词典内部将官方隐藏在二进制包中的词汇划分为 11 个有趣的极客版块：

| 标签组 | 状态示例 | 趣味 AI 语境梗解 |
| :--- | :--- | :--- |
| **🛠️ 严肃硬核** | `Architecting` / `Cerebrating` | 正在设计代码架构 / 脑细胞（Token）疯狂燃烧中 |
| **🍳 厨房重地** | `Baking` / `Caramelizing` | 代码正在烤箱里烤着呢 / 正在给代码裹上一层诱人的焦糖色 |
| **☕ 摸鱼胡闹** | `Dilly-dallying` / `Boondoggling` | 正在光明正大地磨洋工 / 别管我，我正在带薪摸鱼 |
| **🕺 蹦迪摇摆** | `Moonwalking` / `Vibing` | 正在倒着走太空步致敬 MJ / 氛围感编码中，全凭感觉 |
| **🐍 走迷宫** | `Slithering` / `Spelunking` | 穿梭在逻辑文件里 / 正在潜入你深不可测的复杂代码库里探险 |
| **🌪️ 自然现象** | `Whirring` / `Cascading` | 服务器 CPU 正在疯狂发出嗡嗡声 / 正在触发代码的瀑布流响应 |
| **🧙 高端魔法** | `Enchanting` / `Transmuting` | 正在对你的代码施加魔法 / 点石成金，把垃圾代码变成神作 |
| **🌌 高级科幻** | `Quantumizing` / `Hyperspacing` | 遇事不决，量子力学 / 正在通过超空间跃迁快速处理 |
| **🌱 生物生态** | `Germinating` / `Nesting` | 逻辑的种子发芽了 / 正在疯狂写 if/else 的嵌套（筑巢） |
| **🌀 大脑宕机** | `Discombobulating` | 彻底疯狂！完全被这个 Bug 搞崩溃了 |
| **🤡 奇怪彩蛋** | `Clauding` / `Herding` | 官方玩梗：我正在用 Claude 的方式疯狂思考 / 放牧猫咪（管理乱麻） |

---

## 🚀 快速使用

### 方式 A：直接下载使用 (推荐)
1. 复制本仓库中的 [`claude_dictionary.html`](./claude_dictionary.html) 文件代码。
2. 在本地电脑上新建一个文本文件，将代码粘贴进去，重命名为 `claude_dictionary.html`。
3. 双击该文件，它会在你的默认浏览器（Chrome, Edge, Safari 等）中直接打开，无需联网。

### 方式 B：自建预览
本项目为纯前端单页面应用，你可以直接将其作为静态文件托管至 GitHub Pages、Vercel 或 Netlify，实现一键线上查阅。

---

## 🛠️ 底层极客机制科普

在 `claude-code` 实际运行代码中，为了防止用户视觉疲劳，Anthropic 加入了两个隐藏算法：
1. **任务内锁定（Task Locking）**：同一个子任务在运行期间，随机出的单词会**保持固定**（例如一直显示 `Baking...` 而不会中途变成 `Computing...`），直到该子任务结束。
2. **连续不重复队列**：官方维持了一个容量为 5 的队列，刚刚在前 5 次短任务里闪烁出现过的趣味动词，接下来的几次任务中绝对不会再次被随机到。

---

## 🤝 贡献指南

官方词库目前是硬编码在客户端二进制编译文件中的。如果未来 `claude-code` 推出了全新的大版本更新，或者你发现了官方加入的新动词，欢迎随时提交 Issue 或 Pull Request 来完善这个词典！

---

## 📄 开源协议

本项目基于 [MIT License](LICENSE) 协议开源。尽情拿去魔改、分享或者当作你的背单词摸鱼神器吧！
