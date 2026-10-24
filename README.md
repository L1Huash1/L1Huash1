# L1Huash1

Small, explainable tools for understanding agent tool use.

面向 Agent 开发者的小工具：让工具接口的变化、调用过程中的失败更容易看清楚。

## Projects / 项目

| Project | When to use it | 可以解决什么问题 |
| --- | --- | --- |
| [mcp-changecheck](https://github.com/L1Huash1/mcp-changecheck) | **Before a tool upgrade** — compare MCP tool snapshots and review contract changes. | 升级工具前，检查接口变化是否可能影响 Agent。提供离线 HTML 报告和 GitHub 自动检查接入。 |
| [agent-tracecheck](https://github.com/L1Huash1/agent-tracecheck) | **After a recorded run** — inspect repeated calls, errors, incomplete calls and budgets. | 运行后，定位重复调用、失败和未完成步骤。可选接入 LangChain 的本地工具回调。 |

Both projects provide local examples, English/Chinese documentation and regression tests. Their bundled demonstrations need no paid model API.

两个项目都附有可在本地体验的示例、中英文说明和自动测试。示例不需要付费模型 API。

## Start here / 从这里开始

- [MCP 中文入门](https://github.com/L1Huash1/mcp-changecheck/blob/main/README.zh-CN.md) · [Report walkthrough](https://github.com/L1Huash1/mcp-changecheck/blob/main/docs/walkthrough.md)
- [Agent 调用诊断中文入门](https://github.com/L1Huash1/agent-tracecheck/blob/main/README.zh-CN.md) · [LangChain integration](https://github.com/L1Huash1/agent-tracecheck/blob/main/docs/langchain.md)

These are early releases. Static contract checks do not prove full compatibility, and trace diagnostics do not evaluate model quality. Examples include intentional failures to demonstrate findings. See each project's documented limits and checks before adopting it.

项目仍在早期阶段：接口检查不能证明完全兼容，调用诊断也不代表对模型能力的评测。示例里有为了演示而故意制造的失败，使用时请结合各项目的能力说明。

Initial development uses AI coding assistance; behavior is documented and checked with reproducible tests.
