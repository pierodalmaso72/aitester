# Changelog

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), using [Semantic Versioning](https://semver.org/).

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
