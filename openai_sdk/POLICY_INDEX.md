# OpenAI Agents SDK policy index (auto generated)

15 rules — 9 tool · 5 agent · 1 repo

Risk score = `severity_weight × confidence × 100` (engine formula; weights: low=0.15, medium=0.40, high=0.70). Higher = worse.

|    | Id       | SDK/ADK    | Scope | Applies To                          | Policy                                                                     | Severity | Confidence | Risk | Source                                            |
| -- | -------- | ---------- | ----- | ----------------------------------- | -------------------------------------------------------------------------- | -------- | ---------- | ---- | ------------------------------------------------- |
|  1 | OAI-001  | OpenAI SDK | tool  | openai_tool                         | Tool function has no docstring                                             | low      | 0.90       | 13.5 | [tool_definition.yaml](tool_definition.yaml)      |
|  2 | OAI-002  | OpenAI SDK | tool  | openai_tool                         | Tool function has no type-annotated parameters                             | medium   | 0.85       | 34.0 | [tool_definition.yaml](tool_definition.yaml)      |
|  3 | OAI-003  | OpenAI SDK | tool  | openai_tool                         | Tool sets strict_mode=False                                                | medium   | 0.95       | 38.0 | [decorator_config.yaml](decorator_config.yaml)    |
|  4 | OAI-004  | OpenAI SDK | tool  | openai_tool                         | Tool has no failure_error_function                                         | medium   | 0.70       | 28.0 | [decorator_config.yaml](decorator_config.yaml)    |
|  5 | OAI-005  | OpenAI SDK | tool  | openai_tool                         | Network call has no timeout                                                | high     | 0.85       | 59.5 | [network.yaml](network.yaml)                      |
|  6 | OAI-006  | OpenAI SDK | tool  | openai_tool                         | Tool accepts path without normalization                                    | high     | 0.70       | 49.0 | [path_safety.yaml](path_safety.yaml)              |
|  7 | OAI-007  | OpenAI SDK | tool  | openai_tool                         | Ambiguous tool name                                                        | low      | 0.90       | 13.5 | [tool_definition.yaml](tool_definition.yaml)      |
|  8 | OAI-008  | OpenAI SDK | tool  | openai_tool                         | Tool raises exceptions without a structured error contract                 | medium   | 0.60       | 24.0 | [error_handling.yaml](error_handling.yaml)        |
|  9 | OAI-009  | OpenAI SDK | tool  | openai_tool                         | Mutating tool has no idempotency key                                       | medium   | 0.55       | 22.0 | [idempotency.yaml](idempotency.yaml)              |
| 10 | OAI-101  | OpenAI SDK | agent | openai_agent, openai_sandbox_agent  | Agent has no input_guardrails AND wires shell or filesystem-touching tools | high     | 0.85       | 59.5 | [agent_safety.yaml](agent_safety.yaml)            |
| 11 | OAI-102  | OpenAI SDK | agent | openai_agent, openai_sandbox_agent  | Agent uses tool_use_behavior="stop_on_first_tool"                          | high     | 0.95       | 66.5 | [agent_safety.yaml](agent_safety.yaml)            |
| 12 | OAI-103  | OpenAI SDK | agent | openai_agent, openai_sandbox_agent  | tool_choice="required" combined with reset_tool_choice=False               | high     | 0.95       | 66.5 | [agent_safety.yaml](agent_safety.yaml)            |
| 13 | OAI-104  | OpenAI SDK | agent | openai_agent                        | Raw Agent (not SandboxAgent) wires shell or filesystem-touching tools      | medium   | 0.75       | 30.0 | [agent_safety.yaml](agent_safety.yaml)            |
| 14 | OAI-109  | OpenAI SDK | agent | openai_agent, openai_sandbox_agent  | Agent uses WebSearchTool without input_guardrails                          | high     | 0.85       | 59.5 | [agent_safety.yaml](agent_safety.yaml)            |
| 15 | OAI-201  | OpenAI SDK | repo  | openai_agents                       | Project uses default OpenAI tracing                                        | medium   | 0.80       | 32.0 | [tracing.yaml](tracing.yaml)                      |
