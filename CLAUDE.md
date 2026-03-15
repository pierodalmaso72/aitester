# AI Model Playground

## O que é

Single-page HTML app para testar e comparar modelos AI de 3 providers (Anthropic, OpenAI, Google Gemini). Sem servidor — corre inteiramente no browser.

## Stack

- 1 ficheiro HTML com CSS + JS inline
- Sem dependências, sem build, sem framework
- Calls directas às APIs REST via `fetch()`
- Dark theme

## Providers e APIs

### Anthropic (Claude)
- Endpoint: `https://api.anthropic.com/v1/messages`
- Headers: `x-api-key`, `anthropic-version: 2023-06-01`, `anthropic-dangerous-direct-browser-access: true`
- PDF: `{ type: 'document', source: { type: 'base64', media_type, data } }`
- Imagem: `{ type: 'image', source: { type: 'base64', media_type, data } }`
- Modelos: hardcoded (Anthropic não tem endpoint de listagem)
- CORS: requer header `anthropic-dangerous-direct-browser-access: true`

### OpenAI (GPT)
- Endpoint: `https://api.openai.com/v1/chat/completions`
- Headers: `Authorization: Bearer {key}`
- Ficheiro: `{ type: 'file', file: { filename, file_data: 'data:{mime};base64,{data}' } }`
- Listagem modelos: `GET https://api.openai.com/v1/models`
- Reasoning models (gpt-5*, o3, o4): usar `max_completion_tokens` em vez de `max_tokens`

### Google Gemini
- Endpoint: `https://generativelanguage.googleapis.com/v1beta/models/{model}:generateContent?key={key}`
- Ficheiro: `{ inlineData: { mimeType, data } }`
- Listagem modelos: `GET https://generativelanguage.googleapis.com/v1beta/models?key={key}`

## Funcionalidades actuais

- API keys em memória (não persistem)
- Modelos: lista dinâmica (OpenAI/Gemini via API) + hardcoded (Anthropic)
- System prompt + user prompt separados
- Presets de prompts (editáveis)
- Upload de ficheiros (qualquer formato, drag & drop)
- Até 4 modelos em paralelo
- Resultados em colunas lado a lado (JSON formatado, tokens, custo EUR)
- Histórico na sessão (perde-se ao fechar tab)
- Export para .md
- Preços editáveis com fetch via Gemini Flash-Lite (ícone 🔄)

## Convenções

- **Linguagem:** JavaScript vanilla (inline no HTML)
- **Sem dependências** — tudo self-contained
- **Dark theme** com CSS variables
- **Commits:** mensagens em inglês, descritivas

## Roadmap / ideias futuras

- Streaming de respostas
- Comparação diff entre respostas
- Templates de prompts partilháveis (URL params)
- Suporte a mais providers (Mistral, Cohere, etc.)
- Modo batch (testar N ficheiros de uma vez)
