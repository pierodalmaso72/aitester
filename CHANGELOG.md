# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), using [Semantic Versioning](https://semver.org/).

## [1.3.0] - 2026-03-16

### Added
- Run button transforms into red Stop button to cancel in-flight requests
- Selected models float to top of each provider list
- Undo button (red ✕) for price edits — reverts to OpenRouter original price
- History items stack vertically with timestamp (HH:MM) and remove button
- Group toggle moved to Results panel for visual grouping of sequential runs

### Fixed
- OpenAI reasoning models (gpt-5*, o3, o4) now use `developer` role for system prompt
- OpenAI image upload uses `image_url` type instead of `file` type
- GPT-5-nano and other models without vision gracefully skip images with a note
- Large images (> 4MB) auto-resized before upload to prevent request failures
- Selected models not floating to top on toggle
- Model list font reduced, price inputs widened for readability

## [1.2.1] - 2026-03-15

### Changed
- All model prices now come exclusively from OpenRouter API (no more hardcoded defaults)
- USD to EUR exchange rate fetched dynamically from open.er-api.com

### Fixed
- Gemini Flash-Lite price fetch now detects per-token vs per-million format and converts correctly
- Price inputs always display with 2 decimal places (e.g. 15.00)

## [1.2.0] - 2026-03-15

### Added
- Auto-fetch model pricing from OpenRouter API on page load (no auth required)
- Prices update automatically when new models are loaded via provider APIs

### Fixed
- Model filter input losing focus after typing first character

## [1.1.1] - 2026-03-15

### Added
- Filter input per provider to search models by name/id (e.g. "sonnet", "flash", "2.5")
- Models section is now collapsible

### Changed
- Run button moved to Prompts section for quicker access
- API Keys panel starts expanded, auto-collapses when all 3 keys are filled and user clicks outside

### Fixed
- Version display in header subtitle showing old version

## [1.1.0] - 2026-03-15

### Added
- Multi-file upload with drag & drop and individual file removal
- Send mode toggle: sequential (1 file per request) or batch (all files in one request)
- Grouped history view for sequential runs (toggle "Agrupar")
- Dynamic model listing for Anthropic via /v1/models endpoint

### Changed
- API calls now accept multiple files (array) for batch mode
- File list UI replaces single file display
- Export shows multiple file names per run

## [1.0.0] - 2026-03-15

### Added
- Initial public release as "AI Tester"
- Support for 3 providers: Anthropic (Claude), OpenAI (GPT), Google Gemini
- API keys in memory (not persisted) for security
- Dynamic model listing for OpenAI and Gemini via API
- Hardcoded model list for Anthropic
- System prompt + user prompt separated
- Editable prompt presets
- File upload (any format, drag & drop support)
- Up to 4 models running in parallel
- Side-by-side results with formatted JSON, token counts, and EUR cost
- Session history (cleared on tab close)
- Export results to .md
- Editable pricing per model with Gemini Flash-Lite fetch (🔄 icon)
- Dark theme UI

### Changed
- Renamed from "AI Model Playground" to "AI Tester"
