# Contributing

AI Tester is a single HTML file with no build step. To contribute, just edit `aitester.html` and open it in a browser.

## Stack

- 1 HTML file with inline CSS + JS
- No dependencies, no build, no framework
- Direct REST API calls via `fetch()`
- Fonts: [DM Sans](https://fonts.google.com/specimen/DM+Sans) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)

## Provider API Reference

### Anthropic (Claude)
- Endpoint: `https://api.anthropic.com/v1/messages`
- Headers: `x-api-key`, `anthropic-version: 2023-06-01`, `anthropic-dangerous-direct-browser-access: true`
- PDF: `{ type: 'document', source: { type: 'base64', media_type, data } }`
- Image: `{ type: 'image', source: { type: 'base64', media_type, data } }`
- Model listing: `GET https://api.anthropic.com/v1/models` (with auth headers)

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

## Pricing Data

- Auto-fetched from [OpenRouter](https://openrouter.ai/api/v1/models) (public API, no auth)
- Exchange rate from [open.er-api.com](https://open.er-api.com)
- Never hardcode prices — default to 0 if source has no data
- Manual override available per model

## Conventions

- **Single file** — all HTML, CSS, and JS live in `aitester.html`
- **Vanilla JS** — no frameworks, no transpilation
- **i18n** — all UI strings go in the `I18N` object (EN + PT)
- **No browser dialogs** — use toast notifications, not `alert()`/`prompt()`/`confirm()`
- **Commits** — English, descriptive messages
- **Versioning** — [SemVer](https://semver.org/). Update version in `<h1>` + `CHANGELOG.md`

## Roadmap

- Streaming responses
- Diff comparison between responses
- Shareable prompt templates (URL params)
- More providers (Mistral, Cohere, etc.)
