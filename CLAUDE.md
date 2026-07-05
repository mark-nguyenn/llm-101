# CLAUDE.md

Guidance for Claude Code working in this repository.

## What this is

A personal **LLM engineering learning** monorepo. Material is organized **by topic**
(see `README.md`), each topic a folder of notebooks, scripts, and notes.

## Working conventions

- **Organize by topic, never by "week N" or "day N".** All topics live under `src/`.
  Place new work in the matching topic folder (`src/foundations/`, `src/rag/`,
  `src/fine-tuning/`, `src/agents/`, …).
- **This is a monorepo.** Code reused across two or more topics belongs in `src/shared/`,
  imported rather than copy-pasted. Do not duplicate a helper into multiple topics.
- **Notebooks explore; modules stabilize.** Prototype in `.ipynb`, then lift the durable
  parts into `.py` modules once they settle.
- Keep changes scoped to the topic being worked on unless asked otherwise.

## Stack

- **Python 3.12**, managed with **uv** (`uv sync`, `uv add`, `uv run`). Virtualenv: `.venv`.
- Providers via `openai`, `anthropic`, `google-generativeai`, and `litellm` (provider-agnostic).
  Local models via **Ollama** (`http://localhost:11434`).
- RAG: `chromadb`, `sentence-transformers`, LangChain.
- Models/training: `transformers`, `datasets`, `torch`, `scikit-learn`, `xgboost`.
- UIs: `gradio`. Serving: `modal`.
- Secrets in `.env` at repo root (git-ignored).

## Commands

```bash
uv sync                 # install deps
uv run pytest           # run tests
uv run ruff check .     # lint
uv run jupyter lab      # notebooks
```

## Notes

- The `.codegraph/` index is available — prefer `codegraph_*` tools for structural
  questions (definitions, callers, impact) over grep.
- `llm-engineering/` holds earlier reference material; new work goes in the topic folders.
