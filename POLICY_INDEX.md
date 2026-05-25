# Policy index

Every shipped rule, grouped by SDK. ID numbering convention:

- `NNN`        — tool-scope rule
- `1NN`        — agent-scope rule
- `2NN`        — repo-scope rule

ID prefixes: `CSDK-` Claude Agent SDK, `OAI-` OpenAI Agents SDK, `ADK-` Google
ADK. Auto-generated style — keep in sync when adding, removing, or renumbering
rules.

## Claude Agent SDK (`claude_sdk/`)

| ID        | Title                                                | Scope     | Severity | File                                                   |
| --------- | ---------------------------------------------------- | --------- | -------- | ------------------------------------------------------ |
| CSDK-001  | Tool has no description                              | tool      | low      | [tool_definition.yaml](claude_sdk/tool_definition.yaml) |
| CSDK-002  | Tool parameters are not type-annotated               | tool      | medium   | [tool_definition.yaml](claude_sdk/tool_definition.yaml) |
| CSDK-003  | Network call has no timeout                          | tool      | high     | [network.yaml](claude_sdk/network.yaml)                |
| CSDK-004  | Path parameter used in I/O without validation       | tool      | high     | [path_safety.yaml](claude_sdk/path_safety.yaml)        |
| CSDK-005  | Tool raises exceptions without a structured error contract | tool | medium | [error_handling.yaml](claude_sdk/error_handling.yaml)  |
| CSDK-006  | Mutating tool has no idempotency key                 | tool      | medium   | [idempotency.yaml](claude_sdk/idempotency.yaml)        |
| CSDK-007  | Ambiguous tool name                                  | tool      | low      | [tool_definition.yaml](claude_sdk/tool_definition.yaml) |
| CSDK-101  | Claude subagent is granted the Bash tool             | agent     | high     | [agent_safety.yaml](claude_sdk/agent_safety.yaml)      |
| CSDK-102  | Claude subagent is granted the WebSearch tool        | agent     | high     | [agent_safety.yaml](claude_sdk/agent_safety.yaml)      |
| CSDK-110  | Subagent granted the built-in Bash tool              | subagent  | high     | [subagent_safety.yaml](claude_sdk/subagent_safety.yaml) |

## OpenAI Agents SDK (`openai_sdk/`)

| ID       | Title                                                | Scope  | Severity | File                                                       |
| -------- | ---------------------------------------------------- | ------ | -------- | ---------------------------------------------------------- |
| OAI-001  | Tool function has no docstring                       | tool   | low      | [tool_definition.yaml](openai_sdk/tool_definition.yaml)    |
| OAI-002  | Tool function has no type-annotated parameters       | tool   | medium   | [tool_definition.yaml](openai_sdk/tool_definition.yaml)    |
| OAI-003  | Tool sets strict_mode=False                          | tool   | medium   | [decorator_config.yaml](openai_sdk/decorator_config.yaml)  |
| OAI-004  | Tool has no failure_error_function                   | tool   | medium   | [decorator_config.yaml](openai_sdk/decorator_config.yaml)  |
| OAI-005  | Network call has no timeout                          | tool   | high     | [network.yaml](openai_sdk/network.yaml)                    |
| OAI-006  | Tool accepts path without normalization              | tool   | high     | [path_safety.yaml](openai_sdk/path_safety.yaml)            |
| OAI-007  | Ambiguous tool name                                  | tool   | low      | [tool_definition.yaml](openai_sdk/tool_definition.yaml)    |
| OAI-008  | Tool raises exceptions without a structured error contract | tool | medium | [error_handling.yaml](openai_sdk/error_handling.yaml)     |
| OAI-009  | Mutating tool has no idempotency key                 | tool   | medium   | [idempotency.yaml](openai_sdk/idempotency.yaml)            |
| OAI-101  | Agent has no input_guardrails AND wires shell or filesystem-touching tools | agent | high | [agent_safety.yaml](openai_sdk/agent_safety.yaml) |
| OAI-102  | Agent uses tool_use_behavior="stop_on_first_tool"    | agent  | high     | [agent_safety.yaml](openai_sdk/agent_safety.yaml)          |
| OAI-103  | tool_choice="required" combined with reset_tool_choice=False | agent | high | [agent_safety.yaml](openai_sdk/agent_safety.yaml)         |
| OAI-104  | Raw Agent (not SandboxAgent) wires shell or filesystem-touching tools | agent | medium | [agent_safety.yaml](openai_sdk/agent_safety.yaml) |
| OAI-109  | Agent uses WebSearchTool without input_guardrails    | agent  | high     | [agent_safety.yaml](openai_sdk/agent_safety.yaml)          |
| OAI-201  | Project uses default OpenAI tracing                  | repo   | medium   | [tracing.yaml](openai_sdk/tracing.yaml)                    |

## Google ADK (`google_adk/`)

| ID       | Title                                                | Scope  | Severity | File                                                     |
| -------- | ---------------------------------------------------- | ------ | -------- | -------------------------------------------------------- |
| ADK-001  | FunctionTool-wrapped function has no docstring       | tool   | low      | [tool_definition.yaml](google_adk/tool_definition.yaml)  |
| ADK-002  | FunctionTool-wrapped function has no type-annotated parameters | tool | medium | [tool_definition.yaml](google_adk/tool_definition.yaml) |
| ADK-003  | Network call has no timeout                          | tool   | high     | [network.yaml](google_adk/network.yaml)                  |
| ADK-004  | Path parameter used in I/O without normalization     | tool   | high     | [path_safety.yaml](google_adk/path_safety.yaml)          |
| ADK-005  | Tool raises exceptions without a structured error contract | tool | medium | [error_handling.yaml](google_adk/error_handling.yaml)   |
| ADK-006  | Mutating tool has no idempotency key                 | tool   | medium   | [idempotency.yaml](google_adk/idempotency.yaml)          |
| ADK-007  | Ambiguous tool name                                  | tool   | low      | [tool_definition.yaml](google_adk/tool_definition.yaml)  |
| ADK-008  | BashTool missing shell metacharacter blocking        | tool   | high     | [builtin_tools.yaml](google_adk/builtin_tools.yaml)      |
| ADK-101  | LlmAgent has no description                          | agent  | medium   | [agent_safety.yaml](google_adk/agent_safety.yaml)        |
| ADK-102  | Agent with BashTool has no before_tool_callback      | agent  | high     | [agent_safety.yaml](google_adk/agent_safety.yaml)        |
| ADK-103  | Sub-agent is granted BashTool                        | agent  | high     | [agent_safety.yaml](google_adk/agent_safety.yaml)        |
| ADK-104  | Agent has no safety_settings                         | agent  | medium   | [agent_safety.yaml](google_adk/agent_safety.yaml)        |
| ADK-105  | Agent uses web search built-in without before_tool_callback | agent | high | [agent_safety.yaml](google_adk/agent_safety.yaml)        |
