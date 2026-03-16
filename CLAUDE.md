# AI Tester

## What it is

Single-page HTML app to test and compare AI models from 3 providers (Anthropic, OpenAI, Google Gemini). No server — runs entirely in the browser.

## Stack

- 1 HTML file with inline CSS + JS
- No dependencies, no build, no framework
- Direct REST API calls via `fetch()`
- Light/Dark theme (system default + manual toggle)

## Providers & APIs

### Anthropic (Claude)
- Endpoint: `https://api.anthropic.com/v1/messages`
- Headers: `x-api-key`, `anthropic-version: 2023-06-01`, `anthropic-dangerous-direct-browser-access: true`
- PDF: `{ type: 'document', source: { type: 'base64', media_type, data } }`
- Image: `{ type: 'image', source: { type: 'base64', media_type, data } }`
- Model listing: `GET https://api.anthropic.com/v1/models` (with auth headers)
- CORS: requires header `anthropic-dangerous-direct-browser-access: true`

### OpenAI (GPT)
- Endpoint: `https://api.openai.com/v1/chat/completions`
- Headers: `Authorization: Bearer {key}`
- Image: `{ type: 'image_url', image_url: { url: 'data:{mime};base64,{data}' } }`
- File: `{ type: 'file', file: { filename, file_data: 'data:{mime};base64,{data}' } }`
- Model listing: `GET https://api.openai.com/v1/models`
- Reasoning models (gpt-5*, o3, o4): use `max_completion_tokens` instead of `max_tokens`, `developer` role instead of `system`
- Models without vision (gpt-5-nano, o3-mini, o4-mini): images skipped automatically

### Google Gemini
- Endpoint: `https://generativelanguage.googleapis.com/v1beta/models/{model}:generateContent?key={key}`
- File: `{ inlineData: { mimeType, data } }`
- Model listing: `GET https://generativelanguage.googleapis.com/v1beta/models?key={key}`

## Pricing

- Auto-fetched from OpenRouter public API (no auth): `GET https://openrouter.ai/api/v1/models`
- USD/EUR exchange rate from `open.er-api.com`
- Manual override per model (editable inputs + Gemini Flash-Lite fetch)
- No hardcoded prices — defaults to 0 if OpenRouter has no data

## Versioning

- **SemVer** (MAJOR.MINOR.PATCH)
- Current version: see `<h1>` in `aitester.html`
- CHANGELOG.md follows [Keep a Changelog](https://keepachangelog.com/)
- On bump: update version in `<h1>` of HTML + CHANGELOG.md entry

## Conventions

- **Language:** Vanilla JavaScript (inline in HTML)
- **No dependencies** — fully self-contained
- **UI language:** English
- **Commits:** English, descriptive messages
- **Prices:** Never hardcode — use OpenRouter or 0

## Roadmap

- Streaming responses
- Diff comparison between responses
- Shareable prompt templates (URL params)
- More providers (Mistral, Cohere, etc.)
