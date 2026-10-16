# 从概念到行动教练 · concept-to-action-coach

[English](README.md) | [技能正文](SKILL.md) | [维护者：kevin-12-ou](https://github.com/kevin-12-ou)

听过术语，也能复述定义，但仍不知道什么时候需要它、该怎么开始。这个技能把解释接到一个能完成、能验收的小行动上。

这是给 AI 编程助手读取的 **Agent Skill（指令与参考材料）**。包内不包含后台服务、安装执行钩子或模型；Python 脚本仅用于开发时检查包结构；安装后由助手按需读取，实际操作仍受宿主工具权限和用户授权约束。

## 能帮你做什么

- 从你已经会的工具和真实卡点出发，不先堆术语。
- 解释新概念解决了什么问题，以及新增的成本和边界。
- 比较 Skill、Workflow、Agent 等相近概念的责任和反馈方式。
- 需要实践时，给出一个小实验、验收标准和下一步。

## 安装

需要 Git 和支持 Agent Skills 的 AI 助手。使用下面的 Skills CLI 命令还需要 Node.js/npm；CLI 是外部安装工具，运行前请自行审阅。安装本包不需要 API Key、数据库或付费账号，所用 AI 助手本身可能收费。

```sh
npx skills add kevin-12-ou/concept-to-action-coach --skill concept-to-action-coach
```

CLI 会让你选择助手和安装范围。建议先装到测试项目中检查效果。以下是 Codex 的项目级安装示例，不带 `--global`：

```sh
npx skills add kevin-12-ou/concept-to-action-coach --skill concept-to-action-coach --agent codex --copy
```

手动安装：下载本仓库，将完整目录保留为 `concept-to-action-coach`，放到助手支持的技能目录中，例如 `.agents/skills/concept-to-action-coach/`。保留参考文件，不能只复制 README；以助手文档为准。

## 直接这样问

```text
Use $concept-to-action-coach. I use an AI coding assistant but confuse skills, workflows, and agents. Explain the differences using one small coding task, then give me a reversible first experiment.
```

```text
用 $concept-to-action-coach。我会用 AI 改代码，但分不清 Skill、Workflow 和 Agent。用同一个小任务解释，再带我做一个可回退的小实验。
```

```text
Use $concept-to-action-coach. I understand what an API is in theory, but cannot use one. Find the gap in my understanding and guide one public, read-only request.
```

```text
用 $concept-to-action-coach。我大概懂 API 的定义，但不会用。帮我找到理解断点，再做一次不需要密钥的只读请求。
```

显式点名更清楚；自动选择由模型和客户端决定，不保证每次命中。本包采用通用 [Agent Skills 格式](https://agentskills.io/specification)，在 Codex、Claude Code 等支持该格式的工具中可供读取；未宣称所有客户端的实际行为均已测试。技能正文以中文为主。

## 边界与数据

不把每个问题变成上课，也不强迫重复填写背景。简单事实简短回答；明确要求直接实现时，不强行教学。

包内没有凭据或个人项目记录。是否读取项目、写文件、联网或执行命令，取决于任务和助手权限；公开技能本身不会提供隔离或强制拦截。

## 更新、停用与贡献

通过 Skills CLI 安装时可用 `npx skills check` 检查更新、`npx skills update` 更新已安装技能；更新前审阅差异。停用可在助手设置中禁用，或移走安装的技能目录；先备份自己新增的内容。

问题和改进建议请提交到 [Issues](https://github.com/kevin-12-ou/concept-to-action-coach/issues)，提供去除隐私的最小例子。维护说明见 [CONTRIBUTING.md](CONTRIBUTING.md)，公开包检查见 [VALIDATION.md](VALIDATION.md)。

## 同一维护者的其他技能

- [成功方案复用与经验库](https://github.com/kevin-12-ou/dont-repeat-yourself) — 脚本已经跑通、坑也踩过了，换个项目却又从头找。这个技能把成功结果整理成可搜索的小配方，并在下次使用前核验适用条件。
- [开源项目安装评估与上手指南](https://github.com/kevin-12-ou/deploy-onboarding-guide) — 只说“部署好了”不够。用户还需要知道它具体干什么、需不需要 API 或付费账号、会改哪里，以及第一次怎么用。
- [上线与迁移一致性](https://github.com/kevin-12-ou/release-migration-parity) — 本地验收没问题，上线后弹窗样式却变了，旧新版数据不互通；或者迁移到小程序时悄悄漏掉原有功能。这个技能围绕已验收体验做对照。

由 [kevin-12-ou](https://github.com/kevin-12-ou) 维护，整理自个人 AI 辅助工作流。采用 [MIT](LICENSE) 许可；来源说明见 [NOTICE.md](NOTICE.md)。
