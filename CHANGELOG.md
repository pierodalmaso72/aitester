# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), using [Semantic Versioning](https://semver.org/).

## [0.2.0] - 2026-03-16 — First public release

### Added
- 3 providers: Anthropic (Claude), OpenAI (GPT), Google Gemini
- Dynamic model listing from all 3 provider APIs
- Up to 4 models running in parallel with side-by-side results
- Multi-file upload with drag & drop, sequential or batch mode
- Auto-fetch pricing from OpenRouter API (no auth required)
- USD/EUR currency switcher with live exchange rate
- Light/dark theme with system preference detection
- PT/EN language switcher with browser locale auto-detection
- Save/Load prompts as JSON files (native Save As dialog)
- Prompt presets: Classify (basic), Key Fields (medium), Full Analysis (high)
- Run/Stop button with request cancellation via AbortController
- Selected models float to top of each provider list
- Filter input per provider to search models by name/id
- Undo button for price edits (reverts to OpenRouter original)
- Session history with timestamps, remove button, and grouped view
- Export results to Markdown
- Toast notifications (no browser dialogs)
- Large images (>4MB) auto-resized before upload
- Models without vision (GPT-5-nano) gracefully skip images
- OpenAI reasoning models use correct `developer` role
- Footer with pricing source attribution and beta disclaimer

## [0.1.0] - 2026-03-15 — Internal prototype

### Added
- Initial single-file HTML app
- Basic API calls to Anthropic, OpenAI, Google Gemini
- Dark theme, hardcoded Anthropic models
- Single file upload, prompt presets (Portuguese)
