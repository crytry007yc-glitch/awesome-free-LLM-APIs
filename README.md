# Awesome Free LLM APIs

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated list of **free / freemium LLM APIs** you can call from code — no paid plan required to start.

Limits change often. Treat numbers below as guidance and verify on each provider’s docs before production use.

## Contents

- [Ongoing free API tiers](#ongoing-free-api-tiers)
- [Limited / trial access](#limited--trial-access)
- [Aggregators & routers](#aggregators--routers)
- [Local / self-hosted (no cloud bill)](#local--self-hosted-no-cloud-bill)
- [Not free for API (anymore)](#not-free-for-api-anymore)
- [Quick start](#quick-start)
- [Contributing](#contributing)

---

## Ongoing free API tiers

Providers with a renewing free allowance (rate-limited).

| Provider | Free highlight | Card needed? | Notes | Links |
| --- | --- | --- | --- | --- |
| **Groq** | ~30 RPM / ~1K RPD / ~200K tokens/day on selected models | No | Very fast inference; model lineup and limits change | [Console](https://console.groq.com/) · [Rate limits](https://console.groq.com/docs/rate-limits) |
| **Google Gemini API** | Free tier for selected Gemini / Gemma models | No | Limits shown in AI Studio; free prompts may be used to improve products; regional restrictions may apply | [AI Studio](https://aistudio.google.com/) · [Pricing](https://ai.google.dev/gemini-api/docs/pricing) |
| **Cloudflare Workers AI** | 10,000 Neurons/day | No | Neuron budget depends on model & output length | [Docs](https://developers.cloudflare.com/workers-ai/) · [Pricing](https://developers.cloudflare.com/workers-ai/platform/pricing/) |
| **OpenRouter (`:free`)** | 25+ free models; ~50 req/day (higher after spend) | No | Unified OpenAI-compatible API; free models use `:free` suffix | [Models](https://openrouter.ai/models?q=free) · [Pricing](https://openrouter.ai/pricing) |
| **SambaNova Cloud** | Small daily free quota on selected models | No | Low RPD on free tier — fine for experiments | [Cloud](https://cloud.sambanova.ai/) |

---

## Limited / trial access

Useful for prototyping; not a permanent free production tier.

| Provider | What you get | Catch | Links |
| --- | --- | --- | --- |
| **Cohere** | Trial keys (chat / embed / rerank) | Not for production/commercial use on trial | [Dashboard](https://dashboard.cohere.com/) |
| **NVIDIA NIM** (`build.nvidia.com`) | Hosted model endpoints for prototyping | Production usually needs enterprise path | [Build](https://build.nvidia.com/) |
| **Cerebras** | Trial credits on fast inference | Often needs payment method; credits expire | [Cloud](https://cloud.cerebras.ai/) |
| **OpenAI API** | Occasional test / plan credits | After trial, prepaid credit required | [Platform](https://platform.openai.com/) |
| **Anthropic Claude API** | New-user test credits (when offered) | Buy credits once trial ends | [Console](https://console.anthropic.com/) |

---

## Aggregators & routers

One key → many models (mix of free and paid).

| Service | Why use it | Links |
| --- | --- | --- |
| **OpenRouter** | OpenAI-compatible routing; free + paid models | [openrouter.ai](https://openrouter.ai/) |
| **LiteLLM** | Proxy/SDK to standardize providers in your app | [docs.litellm.ai](https://docs.litellm.ai/) |
| **Portkey** | Gateway, observability, fallbacks | [portkey.ai](https://portkey.ai/) |

---

## Local / self-hosted (no cloud bill)

Run models on your machine; API is local HTTP.

| Tool | Notes | Links |
| --- | --- | --- |
| **Ollama** | Simple local model server + REST API | [ollama.com](https://ollama.com/) |
| **LM Studio** | Desktop UI + local server | [lmstudio.ai](https://lmstudio.ai/) |
| **llama.cpp** | High-performance local inference | [GitHub](https://github.com/ggerganov/llama.cpp) |
| **vLLM** | Fast OpenAI-compatible server (GPU) | [docs.vllm.ai](https://docs.vllm.ai/) |

---

## Not free for API (anymore)

Listed so you don’t chase dead free tiers.

| Provider | Status | Notes |
| --- | --- | --- |
| **Mistral API** | Studio/Vibe free ≠ API free | API needs billing / credits |
| **Hugging Face Inference Providers** | Free accounts generally need credits | PRO may include small monthly credit |
| **GitHub Models** | Retired (mid-2026) | Playground/API path shut down |

---

## Quick start

### OpenRouter (OpenAI-compatible)

```bash
curl https://openrouter.ai/api/v1/chat/completions \
  -H "Authorization: Bearer $OPENROUTER_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "google/gemma-3-27b-it:free",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

### Groq

```bash
curl https://api.groq.com/openai/v1/chat/completions \
  -H "Authorization: Bearer $GROQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "llama-3.3-70b-versatile",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

> Model IDs change. Copy the current free/allowed model name from each provider’s console.

### Gemini (Google AI)

```bash
curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=$GEMINI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"contents":[{"parts":[{"text":"Hello!"}]}]}'
```

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs that add working free endpoints, update broken limits, or mark retired providers are especially welcome.

## Disclaimer

This list is community-maintained and informational only. Free tiers, ToS, data-use policies, and regional availability can change without notice. Always read the provider’s terms before shipping an app.

## License

[CC0 1.0](LICENSE) (list contents). Code snippets are likewise free to use.
