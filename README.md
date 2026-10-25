# L1Huash1

Small, local tools for developing and testing agent tool use.

面向 Agent 开发者的小工具：整理任务上下文、重现工具失败、检查接口变化与调用记录。

## Projects / 项目

| Project | When to use it | 可以解决什么问题 |
| --- | --- | --- |
| [context-budgetpack](https://github.com/L1Huash1/context-budgetpack) | **Before sending context** — select explicit file fragments within a hard UTF-8 byte cap. | 按优先级与行范围整理文件，解释取舍，并核验来源是否改变。附离线选择报告。 |
| [tool-mockbox](https://github.com/L1Huash1/tool-mockbox) | **While testing calling code** — script tool failures, recovery, delays and cancellation. | 本地重现“前两次失败，第三次成功”，检查重试代码，并查看调用报告。 |
| [mcp-changecheck](https://github.com/L1Huash1/mcp-changecheck) | **Before a tool upgrade** — compare MCP tool snapshots and review contract changes. | 升级工具前，检查接口变化是否可能影响 Agent。提供离线 HTML 报告和 GitHub 自动检查接入。 |
| [agent-tracecheck](https://github.com/L1Huash1/agent-tracecheck) | **After a recorded run** — inspect repeated calls, errors, incomplete calls and budgets. | 运行后，定位重复调用、失败和未完成步骤。可选接入 LangChain 的本地工具回调。 |
| [agent-ci-starter](https://github.com/L1Huash1/agent-ci-starter) | **Try the complete workflow** — copy a project that connects both checks. | 从完整入门项目开始：本地工具示例、接口快照、调用记录和 GitHub 检查。 |

The projects provide local examples, English/Chinese documentation and regression tests. Their bundled demonstrations need no paid model API.

项目都附有可在本地体验的示例、中英文说明和自动测试。示例不需要付费模型 API。

## Start here / 从这里开始

- [完整入门项目](https://github.com/L1Huash1/agent-ci-starter/blob/main/README.zh-CN.md) — new to these tools? Start with the scripted, model-free workflow.
- [上下文打包中文入门](https://github.com/L1Huash1/context-budgetpack/blob/main/README.zh-CN.md) · [工具失败与恢复中文入门](https://github.com/L1Huash1/tool-mockbox/blob/main/README.zh-CN.md)
- [MCP 中文入门](https://github.com/L1Huash1/mcp-changecheck/blob/main/README.zh-CN.md) · [Report walkthrough](https://github.com/L1Huash1/mcp-changecheck/blob/main/docs/walkthrough.md)
- [Agent 调用诊断中文入门](https://github.com/L1Huash1/agent-tracecheck/blob/main/README.zh-CN.md) · [LangChain integration](https://github.com/L1Huash1/agent-tracecheck/blob/main/docs/langchain.md)

These are early releases. Byte budgets are not token estimates, scripted fixtures do not reproduce real service reliability, static contract checks do not prove full compatibility, and trace diagnostics do not evaluate model quality. Examples include intentional failures to demonstrate findings. See each project's documented limits and checks before adopting it.

项目仍在早期阶段：字节预算不是 token 估算，模拟场景不代表真实服务可靠性，接口检查不能证明完全兼容，调用诊断也不代表模型能力评测。部分示例包含预设失败，使用时请结合各项目的能力说明。

Initial development uses AI coding assistance; behavior is documented and checked with reproducible tests.
