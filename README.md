# AI Tester

A browser-only tool to test and compare AI models side-by-side. No server, no build step, no dependencies — just open the HTML file.

![AI Tester Screenshot](https://img.shields.io/badge/status-beta-yellow) ![License](https://img.shields.io/badge/license-MIT-blue)

## Features

- **3 Providers** — Anthropic (Claude), OpenAI (GPT), Google Gemini
- **Side-by-side comparison** — Run up to 4 models in parallel
- **File upload** — Drag & drop any file (images, PDFs, documents)
- **Multi-file support** — Sequential (1 file per request) or batch mode
- **Live pricing** — Auto-fetched from [OpenRouter](https://openrouter.ai) + manual override
- **Cost tracking** — Token counts and EUR cost per request (USD/EUR rate fetched live)
- **Prompt presets** — Quick-load common prompts (classify, extract, full analysis)
- **Session history** — Review past runs, group sequential results, export to Markdown
- **Light/Dark mode** — Follows system preference, toggle available
- **Stop button** — Cancel in-flight requests anytime
- **Zero data persistence** — API keys stay in memory only, nothing saved to disk

## Quick Start

1. Download `aitester.html`
2. Open it in any modern browser
3. Enter your API key(s)
4. Write a prompt, select models, click **Run**

That's it. No installation, no server, no configuration.

## API Keys

You need at least one API key from a supported provider:

| Provider | Get a key | Notes |
|----------|-----------|-------|
| [Anthropic](https://console.anthropic.com/settings/keys) | `sk-ant-...` | Requires `anthropic-dangerous-direct-browser-access` header (handled automatically) |
| [OpenAI](https://platform.openai.com/api-keys) | `sk-proj-...` | Models loaded dynamically from API |
| [Google Gemini](https://aistudio.google.com/apikey) | `AIza...` | Models loaded dynamically from API |

Keys are **never saved** — they exist only in browser memory and are lost when you close the tab.

## Pricing

- Model prices are fetched automatically from the [OpenRouter public API](https://openrouter.ai/api/v1/models) (no authentication required)
- USD to EUR exchange rate is fetched from [open.er-api.com](https://open.er-api.com)
- You can manually edit any price or fetch per-model pricing via Gemini Flash-Lite
- If a model is not found in OpenRouter, its price shows as $0.00 (editable)

## Prompt Presets

| Preset | Complexity | Description |
|--------|-----------|-------------|
| **Classify** | Basic | Is this a financial document? Returns boolean + reason |
| **Key Fields** | Medium | Extracts issuer, date, amount, currency, description |
| **Full Analysis** | High | Complete document extraction with all fields and confidence score |

## File Support

- Any file type (images, PDFs, spreadsheets, text files)
- Drag & drop or click to select
- Multiple files with add/remove
- Large images (>4MB) auto-resized before upload
- Models without vision support (e.g., GPT-5-nano) gracefully skip images

## Browser Compatibility

Works in any modern browser (Chrome, Firefox, Edge, Safari). Requires JavaScript enabled and network access to the provider APIs.

## Tech Stack

- Single HTML file (~1100 lines)
- Vanilla JavaScript (no frameworks, no dependencies)
- CSS variables for theming
- Direct REST API calls via `fetch()`

## License

[MIT](LICENSE)

## Disclaimer

This tool is provided as-is, in beta, with no warranty. Pricing data may be inaccurate or outdated. Always verify costs with your provider's official pricing page. The authors assume no responsibility for any charges incurred.
