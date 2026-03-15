# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), using [Semantic Versioning](https://semver.org/).

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
