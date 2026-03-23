# golemcore-models

Shared registry layout for GolemCore model defaults.

Lookup order:

1. `providers/<provider>/<model-id>.json`
2. `models/<model-id>.json`

Each JSON file contains full `ModelSettings` without the `provider` field.

This repository intentionally contains only current general-purpose text/vision models used in Model Catalog discovery.

Current families included:

- OpenAI GPT-5 and Codex models
- Anthropic Claude current aliases
- Gemini current text multimodal models

## Supported models

| Family | Model ID | Display name | Vision | Temperature | Reasoning |
| --- | --- | --- | --- | --- | --- |
| OpenAI | `gpt-5.1` | GPT-5.1 | yes | no | `none`, `low`, `medium`, `high` |
| OpenAI | `gpt-5-codex` | GPT-5-Codex | yes | no | `minimal`, `low`, `medium`, `high` |
| OpenAI | `gpt-5.1-codex` | GPT-5.1 Codex | yes | no | `none`, `low`, `medium`, `high` |
| OpenAI | `gpt-5.1-codex-mini` | GPT-5.1 Codex mini | yes | no | `none`, `low`, `medium`, `high` |
| OpenAI | `gpt-5.1-codex-max` | GPT-5.1 Codex Max | yes | no | `none`, `low`, `medium`, `high` |
| OpenAI | `gpt-5.2` | GPT-5.2 | yes | no | `none`, `low`, `medium`, `high`, `xhigh` |
| OpenAI | `gpt-5.2-codex` | GPT-5.2-Codex | yes | no | `low`, `medium`, `high`, `xhigh` |
| OpenAI | `gpt-5.2-pro` | GPT-5.2 pro | yes | no | `medium`, `high`, `xhigh` |
| OpenAI | `gpt-5.3-codex` | GPT-5.3-Codex | yes | no | `low`, `medium`, `high`, `xhigh` |
| OpenAI | `gpt-5.3-codex-spark` | GPT-5.3-Codex-Spark | no | no | no explicit reasoning map |
| OpenAI | `gpt-5.4` | GPT-5.4 | yes | no | `none`, `low`, `medium`, `high`, `xhigh` |
| OpenAI | `gpt-5.4-mini` | GPT-5.4 mini | yes | no | no explicit reasoning map |
| OpenAI | `gpt-5.4-nano` | GPT-5.4 nano | yes | no | no explicit reasoning map |
| OpenAI | `gpt-5.4-pro` | GPT-5.4 pro | yes | no | `medium`, `high`, `xhigh` |
| Anthropic | `claude-opus-4-6` | Claude Opus 4.6 | yes | yes | no explicit reasoning map |
| Anthropic | `claude-sonnet-4-6` | Claude Sonnet 4.6 | yes | yes | no explicit reasoning map |
| Anthropic | `claude-haiku-4-5` | Claude Haiku 4.5 | yes | yes | no explicit reasoning map |
| Gemini | `gemini-2.5-pro` | Gemini 2.5 Pro | yes | yes | no explicit reasoning map |
| Gemini | `gemini-2.5-flash` | Gemini 2.5 Flash | yes | yes | no explicit reasoning map |
| Gemini | `gemini-2.5-flash-lite` | Gemini 2.5 Flash-Lite | yes | yes | no explicit reasoning map |
| Gemini | `gemini-3-flash-preview` | Gemini 3 Flash Preview | yes | yes | `minimal`, `low`, `medium`, `high` |
| Gemini | `gemini-3.1-flash-lite-preview` | Gemini 3.1 Flash-Lite Preview | yes | yes | `minimal`, `low`, `medium`, `high` |
| Gemini | `gemini-3.1-pro-preview` | Gemini 3.1 Pro Preview | yes | yes | `low`, `medium`, `high` |
