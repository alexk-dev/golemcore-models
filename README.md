# golemcore-models

Shared registry layout for GolemCore model defaults.

Lookup order:

1. `providers/<provider>/<model-id>.json`
2. `models/<model-id>.json`

Each JSON file contains full `ModelSettings` without the `provider` field.

This repository intentionally contains only current general-purpose text/vision models used in Model Catalog discovery.

Excluded on purpose:

- deprecated models
- legacy `gpt-4o` / `o3` style families
- audio-only, image-only, TTS, live, and other specialized endpoints

Current families included:

- OpenAI GPT-5 versioned models
- Anthropic Claude current aliases
- Gemini current text multimodal models
