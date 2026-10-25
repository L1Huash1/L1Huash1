# 我该从哪个项目开始？

这里的项目帮开发者整理 AI 要阅读的文件、测试工具失败时的应对代码，以及检查接口和调用记录。附带示例都使用本地合成数据，不需要付费模型 API。

| 你现在想做什么 | 从这里开始 | 可以看到什么 |
| --- | --- | --- |
| 想完整体验一次“准备资料 → 工具失败 → 重试 → 查看记录” | [agent-ci-starter 中文说明](https://github.com/L1Huash1/agent-ci-starter/blob/main/README.zh-CN.md)中的可选实验 | 预设两次失败后恢复，失败记录仍然保留 |
| 想给 Agent 一份大小明确、来源可核验的资料 | [context-budgetpack](https://github.com/L1Huash1/context-budgetpack/blob/main/README.zh-CN.md) | 哪些文件片段被选入、哪些放不下、源文件后来是否改变 |
| 想测试自己的重试、等待或取消代码 | [tool-mockbox](https://github.com/L1Huash1/tool-mockbox/blob/main/README.zh-CN.md) | 按脚本返回成功或失败，并生成调用报告 |
| 工具升级前，担心原来的调用参数不适用 | [mcp-changecheck](https://github.com/L1Huash1/mcp-changecheck/blob/main/README.zh-CN.md) | 比较升级前后的工具说明，提示可能影响调用的变化 |
| 已有调用记录，想看看哪里重复、失败或没完成 | [agent-tracecheck](https://github.com/L1Huash1/agent-tracecheck/blob/main/README.zh-CN.md) | 调用诊断和自己设置的次数、错误预算 |

暂时不想安装，可以先打开 [starter 的 Actions 页面](https://github.com/L1Huash1/agent-ci-starter/actions)，选择带有 `scripted-recovery-lab-...` 附件的成功运行，在 **Artifacts** 下载并解压，打开 `trace-report.html`。附件保留 7 天。这里能同时看到上下文、模拟调用和诊断记录；安装体验再按中文说明操作。

## MCP 是什么？

MCP，全称 Model Context Protocol，是让 AI 应用连接工具和资料的一种通用协议。比如“查询笔记”这个工具，可以通过 MCP 提供给支持它的 AI 应用调用。你可以把它理解成双方都遵守的沟通格式。参见 [MCP 官方入门](https://modelcontextprotocol.io/docs/getting-started/intro)。

`tool-mockbox` 的普通 Python 调用、本地 HTTP 模式和 MCP 模式是不同的接入方式。项目自己的 HTTP 地址不能直接当作 MCP 服务地址使用，具体格式见 [HTTP 协议说明](https://github.com/L1Huash1/tool-mockbox/blob/v0.2.0/docs/protocol.md)。已发布的 [0.2 版](https://github.com/L1Huash1/tool-mockbox/releases/tag/v0.2.0) 提供**可选 MCP 接入**，需要从源码额外安装 SDK，按 [MCP 接入说明](https://github.com/L1Huash1/tool-mockbox/blob/v0.2.0/docs/mcp.md)体验。它通过标准输入输出通信；不需要先弄懂 MCP 才能运行普通 Python 示例。

## 示例显示失败，是程序坏了吗？

先看示例说明：模拟器会故意制造失败，方便观察应对代码。`tool-mockbox run` 即使第三次成功，只要记录中有预设失败，仍会返回退出码 **1**；这时可以正常打开已经生成的报告。starter 的可选实验则明确允许预设的两次失败，恢复后仍展示这些记录。两者检查的是不同条件，详情见各自中文说明。

上下文字节上限不等于模型 token 数；预设重试也不代表真实服务可靠性或大模型能力。选择一个与你当前问题对应的小实验即可。
