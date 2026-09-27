# 📧 Gmail AI Agent

A multi-agent AI system (built on **CrewAI**) that triages, organizes, and drafts replies for your Gmail inbox — now running on **Google Gemini**.

> **Attribution:** This project is based on [tonykipkemboi/crewai-gmail-automation](https://github.com/tonykipkemboi/crewai-gmail-automation) (MIT License). I made the LLM backend configurable with Gemini as the default.

## What it does

- 🏷️ **Categorizer agent** — labels incoming emails (receipts, newsletters, YouTube notifications, action-required…)
- ✍️ **Action agent** — drafts replies and summarizes threads
- 🧠 Powered by CrewAI crews with tool-using agents

## What changed from the original

- Replaced the **hardcoded OpenAI model** with a configurable backend:
  - `GMAIL_AGENT_MODEL` env var (default: `gemini/gemini-2.5-flash`)
  - Uses `GEMINI_API_KEY` first, falls back to `OPENAI_API_KEY`

## Quick start

```bash
pip install -e .
export GEMINI_API_KEY=your-key-here
# optional: export GMAIL_AGENT_MODEL=gemini/gemini-2.5-flash
python -m gmail_crew_ai.main
```

> **Demo mode:** point the crew at a local file of sample emails (see `tests/`) to try it without touching your real inbox.

## License

MIT — see [LICENSE](LICENSE) (original license by Tony Kipkemboi, preserved).
