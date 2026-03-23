# AGENTS.md for `golemcore-models`

This repository is a shared registry of provider-agnostic `ModelSettings` JSON files used by GolemCore during model discovery.

## Repository contract

- Store shared defaults under `models/<model-id>.json`.
- Store provider-specific overrides under `providers/<provider>/<model-id>.json` only when a provider genuinely needs different defaults.
- JSON files must contain full `ModelSettings` without the `provider` field.
- Prefer stable shared model IDs over dated aliases, snapshots, or temporary rollout IDs.

## Primary data sources

Always prefer official provider documentation over third-party catalogs, SDK enums, forum posts, or blog summaries.

### OpenAI

Primary sources:

- `https://developers.openai.com/api/docs/models`
- model-specific pages under `https://platform.openai.com/docs/models/*`
- relevant official guides when model behavior is described there, for example Codex or GPT-5 guides

Use OpenAI docs to confirm:

- canonical model ID
- supported modalities
- context window
- max output tokens when available
- reasoning effort support, if explicitly documented

### Anthropic

Primary sources:

- `https://docs.anthropic.com/`
- Claude model overview / model reference pages under official Anthropic docs

Use Anthropic docs to confirm:

- canonical model ID or stable alias
- context window
- image support
- current family naming

### Gemini

Primary sources:

- `https://ai.google.dev/gemini-api/docs/models`
- other official Gemini API docs under `https://ai.google.dev/`

Use Gemini docs to confirm:

- canonical model ID
- context window
- multimodal support
- stable alias vs dated preview alias

## Mapping rules

When converting provider docs into `ModelSettings`:

- `displayName`: use the public product name shown in provider docs
- `supportsVision`: `true` only when image input is supported
- `supportsTemperature`: set from explicit provider compatibility guidance when documented; otherwise use the most conservative safe value
- `maxInputTokens`: use the published context window
- `reasoning`: include only when the provider explicitly documents supported reasoning levels, or when the setting is intentionally inherited from the base model family and that inheritance is obvious

## Exclusions

Do not add:

- deprecated models
- dated aliases when a stable alias exists
- snapshots unless the repository deliberately decides to pin them
- audio-only, image-only, realtime-only, TTS, embedding, moderation, or other specialized endpoint models unless the catalog explicitly expands scope

## Validation

Before committing:

- run `jq empty models/*.json` and, if applicable, `jq empty providers/**/*.json`
- keep `README.md` in sync with the supported models actually present in the repository

## Git workflow

- Direct pushes to `main` are prohibited.
- All changes must go through a feature branch and Pull Request.
- Keep commits focused and reviewable.

## Commit messages

Use Conventional Commits.

Format:

`<type>[optional scope]: <description>`

Allowed types:

- `feat`
- `fix`
- `refactor`
- `test`
- `docs`
- `chore`
- `perf`
- `style`
- `revert`

Rules:

- use imperative mood
- keep the subject concise
- do not end the subject with a period
- use a scope when it improves clarity, for example `models`, `readme`, `registry`, or `github`

Examples:

- `feat(models): add gpt-5.3-codex defaults`
- `docs(readme): update supported models table`
- `chore(github): add commit message workflow`
