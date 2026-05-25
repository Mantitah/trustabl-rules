# Policy index (auto generated)

All shipped rules across every SDK. ID prefix denotes SDK: `CSDK-` Claude
Agent SDK, `OAI-` OpenAI Agents SDK, `ADK-` Google ADK. Within an SDK: `NNN`
tool-scope, `1NN` agent / subagent scope, `2NN` repo scope.

Risk score = `severity_weight × confidence × 100` (engine formula; weights:
low=0.15, medium=0.40, high=0.70). Higher = worse.

## Totals

| SDK                 | Tool   | Agent  | Subagent | Repo  | Total  | Per-SDK index                                              |
| ------------------- | ------ | ------ | -------- | ----- | ------ | ---------------------------------------------------------- |
| Claude Agent SDK    | 7      | 2      | 1        | 0     | 10     | [claude_sdk/POLICY_INDEX.md](claude_sdk/POLICY_INDEX.md)   |
| OpenAI Agents SDK   | 9      | 5      | 0        | 1     | 15     | [openai_sdk/POLICY_INDEX.md](openai_sdk/POLICY_INDEX.md)   |
| Google ADK          | 8      | 5      | 0        | 0     | 13     | [google_adk/POLICY_INDEX.md](google_adk/POLICY_INDEX.md)   |
| **All**             | **24** | **12** | **1**    | **1** | **38** |                                                            |

## All rules

|    | Id        | SDK/ADK    | Scope    | Applies To                          | Policy                                                                     | Severity | Confidence | Risk | Source                                                          |
| -- | --------- | ------ | -------- | ----------------------------------- | -------------------------------------------------------------------------- | -------- | ---------- | ---- | --------------------------------------------------------------- |
|  1 | CSDK-001  | Claude SDK | tool     | claude_sdk_tool                     | Tool has no description                                                    | low      | 0.95       | 14.3 | [claude_sdk/tool_definition.yaml](claude_sdk/tool_definition.yaml)        |
|  2 | CSDK-002  | Claude SDK | tool     | claude_sdk_tool                     | Tool parameters are not type-annotated                                     | medium   | 0.90       | 36.0 | [claude_sdk/tool_definition.yaml](claude_sdk/tool_definition.yaml)        |
|  3 | CSDK-003  | Claude SDK | tool     | claude_sdk_tool                     | Network call has no timeout                                                | high     | 0.85       | 59.5 | [claude_sdk/network.yaml](claude_sdk/network.yaml)                        |
|  4 | CSDK-004  | Claude SDK | tool     | claude_sdk_tool                     | Path parameter used in I/O without validation                              | high     | 0.70       | 49.0 | [claude_sdk/path_safety.yaml](claude_sdk/path_safety.yaml)                |
|  5 | CSDK-005  | Claude SDK | tool     | claude_sdk_tool                     | Tool raises exceptions without a structured error contract                 | medium   | 0.60       | 24.0 | [claude_sdk/error_handling.yaml](claude_sdk/error_handling.yaml)          |
|  6 | CSDK-006  | Claude SDK | tool     | claude_sdk_tool                     | Mutating tool has no idempotency key                                       | medium   | 0.55       | 22.0 | [claude_sdk/idempotency.yaml](claude_sdk/idempotency.yaml)                |
|  7 | CSDK-007  | Claude SDK | tool     | claude_sdk_tool                     | Ambiguous tool name                                                        | low      | 0.90       | 13.5 | [claude_sdk/tool_definition.yaml](claude_sdk/tool_definition.yaml)        |
|  8 | CSDK-101  | Claude SDK | agent    | claude_agent_definition             | Claude subagent is granted the Bash tool                                   | high     | 0.80       | 56.0 | [claude_sdk/agent_safety.yaml](claude_sdk/agent_safety.yaml)              |
|  9 | CSDK-102  | Claude SDK | agent    | claude_agent_definition             | Claude subagent is granted the WebSearch tool                              | high     | 0.80       | 56.0 | [claude_sdk/agent_safety.yaml](claude_sdk/agent_safety.yaml)              |
| 10 | CSDK-110  | Claude SDK | subagent | claude_subagent                     | Subagent granted the built-in Bash tool                                    | high     | 0.90       | 63.0 | [claude_sdk/subagent_safety.yaml](claude_sdk/subagent_safety.yaml)        |
| 11 | OAI-001   | OpenAI SDK | tool     | openai_tool                         | Tool function has no docstring                                             | low      | 0.90       | 13.5 | [openai_sdk/tool_definition.yaml](openai_sdk/tool_definition.yaml)        |
| 12 | OAI-002   | OpenAI SDK | tool     | openai_tool                         | Tool function has no type-annotated parameters                             | medium   | 0.85       | 34.0 | [openai_sdk/tool_definition.yaml](openai_sdk/tool_definition.yaml)        |
| 13 | OAI-003   | OpenAI SDK | tool     | openai_tool                         | Tool sets strict_mode=False                                                | medium   | 0.95       | 38.0 | [openai_sdk/decorator_config.yaml](openai_sdk/decorator_config.yaml)      |
| 14 | OAI-004   | OpenAI SDK | tool     | openai_tool                         | Tool has no failure_error_function                                         | medium   | 0.70       | 28.0 | [openai_sdk/decorator_config.yaml](openai_sdk/decorator_config.yaml)      |
| 15 | OAI-005   | OpenAI SDK | tool     | openai_tool                         | Network call has no timeout                                                | high     | 0.85       | 59.5 | [openai_sdk/network.yaml](openai_sdk/network.yaml)                        |
| 16 | OAI-006   | OpenAI SDK | tool     | openai_tool                         | Tool accepts path without normalization                                    | high     | 0.70       | 49.0 | [openai_sdk/path_safety.yaml](openai_sdk/path_safety.yaml)                |
| 17 | OAI-007   | OpenAI SDK | tool     | openai_tool                         | Ambiguous tool name                                                        | low      | 0.90       | 13.5 | [openai_sdk/tool_definition.yaml](openai_sdk/tool_definition.yaml)        |
| 18 | OAI-008   | OpenAI SDK | tool     | openai_tool                         | Tool raises exceptions without a structured error contract                 | medium   | 0.60       | 24.0 | [openai_sdk/error_handling.yaml](openai_sdk/error_handling.yaml)          |
| 19 | OAI-009   | OpenAI SDK | tool     | openai_tool                         | Mutating tool has no idempotency key                                       | medium   | 0.55       | 22.0 | [openai_sdk/idempotency.yaml](openai_sdk/idempotency.yaml)                |
| 20 | OAI-101   | OpenAI SDK | agent    | openai_agent, openai_sandbox_agent  | Agent has no input_guardrails AND wires shell or filesystem-touching tools | high     | 0.85       | 59.5 | [openai_sdk/agent_safety.yaml](openai_sdk/agent_safety.yaml)              |
| 21 | OAI-102   | OpenAI SDK | agent    | openai_agent, openai_sandbox_agent  | Agent uses tool_use_behavior="stop_on_first_tool"                          | high     | 0.95       | 66.5 | [openai_sdk/agent_safety.yaml](openai_sdk/agent_safety.yaml)              |
| 22 | OAI-103   | OpenAI SDK | agent    | openai_agent, openai_sandbox_agent  | tool_choice="required" combined with reset_tool_choice=False               | high     | 0.95       | 66.5 | [openai_sdk/agent_safety.yaml](openai_sdk/agent_safety.yaml)              |
| 23 | OAI-104   | OpenAI SDK | agent    | openai_agent                        | Raw Agent (not SandboxAgent) wires shell or filesystem-touching tools      | medium   | 0.75       | 30.0 | [openai_sdk/agent_safety.yaml](openai_sdk/agent_safety.yaml)              |
| 24 | OAI-109   | OpenAI SDK | agent    | openai_agent, openai_sandbox_agent  | Agent uses WebSearchTool without input_guardrails                          | high     | 0.85       | 59.5 | [openai_sdk/agent_safety.yaml](openai_sdk/agent_safety.yaml)              |
| 25 | OAI-201   | OpenAI SDK | repo     | openai_agents                       | Project uses default OpenAI tracing                                        | medium   | 0.80       | 32.0 | [openai_sdk/tracing.yaml](openai_sdk/tracing.yaml)                        |
| 26 | ADK-001   | Google ADK    | tool     | adk_function_tool                   | FunctionTool-wrapped function has no docstring                             | low      | 0.80       | 12.0 | [google_adk/tool_definition.yaml](google_adk/tool_definition.yaml)        |
| 27 | ADK-002   | Google ADK   | tool     | adk_function_tool                   | FunctionTool-wrapped function has no type-annotated parameters             | medium   | 0.85       | 34.0 | [google_adk/tool_definition.yaml](google_adk/tool_definition.yaml)        |
| 28 | ADK-003   | Google ADK   | tool     | adk_function_tool                   | Network call has no timeout                                                | high     | 0.85       | 59.5 | [google_adk/network.yaml](google_adk/network.yaml)                        |
| 29 | ADK-004   | Google ADK    | tool     | adk_function_tool                   | Path parameter used in I/O without normalization                           | high     | 0.70       | 49.0 | [google_adk/path_safety.yaml](google_adk/path_safety.yaml)                |
| 30 | ADK-005   | Google ADK    | tool     | adk_function_tool                   | Tool raises exceptions without a structured error contract                 | medium   | 0.60       | 24.0 | [google_adk/error_handling.yaml](google_adk/error_handling.yaml)          |
| 31 | ADK-006   | Google ADK    | tool     | adk_function_tool                   | Mutating tool has no idempotency key                                       | medium   | 0.55       | 22.0 | [google_adk/idempotency.yaml](google_adk/idempotency.yaml)                |
| 32 | ADK-007   | Google ADK    | tool     | adk_function_tool                   | Ambiguous tool name                                                        | low      | 0.90       | 13.5 | [google_adk/tool_definition.yaml](google_adk/tool_definition.yaml)        |
| 33 | ADK-008   | Google ADK    | tool     | adk_function_tool                   | BashTool missing shell metacharacter blocking                              | high     | 0.90       | 63.0 | [google_adk/builtin_tools.yaml](google_adk/builtin_tools.yaml)            |
| 34 | ADK-101   | Google ADK    | agent    | adk_llm_agent                       | LlmAgent has no description                                                | medium   | 0.85       | 34.0 | [google_adk/agent_safety.yaml](google_adk/agent_safety.yaml)              |
| 35 | ADK-102   | Google ADK    | agent    | adk_llm_agent                       | Agent with BashTool has no before_tool_callback                            | high     | 0.85       | 59.5 | [google_adk/agent_safety.yaml](google_adk/agent_safety.yaml)              |
| 36 | ADK-103   | Google ADK    | agent    | adk_llm_agent                       | Sub-agent is granted BashTool                                              | high     | 0.90       | 63.0 | [google_adk/agent_safety.yaml](google_adk/agent_safety.yaml)              |
| 37 | ADK-104   | Google ADK    | agent    | adk_llm_agent                       | Agent has no safety_settings                                               | medium   | 0.75       | 30.0 | [google_adk/agent_safety.yaml](google_adk/agent_safety.yaml)              |
| 38 | ADK-105   | Google ADK    | agent    | adk_llm_agent                       | Agent uses web search built-in without before_tool_callback                | high     | 0.85       | 59.5 | [google_adk/agent_safety.yaml](google_adk/agent_safety.yaml)              |
