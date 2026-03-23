# golemcore-models

Example registry layout for GolemCore model defaults.

Lookup order:

1. `providers/<provider>/<model-id>.json`
2. `models/<model-id>.json`

Each JSON file contains full `ModelSettings` without the `provider` field.

Examples in this repository:

- `models/gpt-5.1.json`
- `models/o3.json`
- `models/openai/gpt-4o.json`
- `providers/openrouter/openai/gpt-4o.json`
