```text
             ✦        ⋆            ✧      ·        ✦          ✧      ⋆             
                 ·         ✩            ⋆        ✧          ·        ✦             
  ✦  █████       █████       ██████   ██████            ████     █████    ████  ✧  
    ░░███       ░░███       ░░██████ ██████            ░░███   ███░░░███ ░░███     
⋆    ░███        ░███        ░███░█████░███             ░███  ███   ░░███ ░███    ⋆
     ░███        ░███        ░███░░███ ░███  ██████████ ░███ ░███    ░███ ░███     
  ✧  ░███        ░███        ░███ ░░░  ░███ ░░░░░░░░░░  ░███ ░███    ░███ ░███  ✦  
     ░███      █ ░███      █ ░███      ░███             ░███ ░░███   ███  ░███     
  ✦  ███████████ ███████████ █████     █████            █████ ░░░█████░   █████ ✧  
    ░░░░░░░░░░░ ░░░░░░░░░░░ ░░░░░     ░░░░░            ░░░░░    ░░░░░░   ░░░░░     
            ⋆        ✧            ·      ✦        ✧          ⋆      ·              
               ✧        ·        ✦          ⋆       ·        ✧       ✦             
```

# llm-101

A hands-on **LLM engineering** monorepo. Knowledge is organized **by topic**, not by lesson or week — each folder is a self-contained area with its own notebooks, scripts, and notes.

## Layout

All topics live under `src/`.

| Folder | Topic |
|---|---|
| `src/foundations/` | LLM API basics: multi-provider clients, streaming, tokenization |
| `src/prompting/` | System prompts, context, few-shot patterns |
| `src/tool-calling/` | Function calling, tool loops, tool-backed state (e.g. SQLite) |
| `src/ui/` | Gradio patterns — `Interface`, `ChatInterface`, `Blocks` |
| `src/open-source-models/` | HuggingFace, transformers, tokenizers, logprobs |
| `src/code-generation/` | Multi-model code generation and optimization |
| `src/rag/` | Retrieval Augmented Generation: Chroma, embeddings, chunking, reranking, eval |
| `src/data-engineering/` | Dataset curation, HF Hub, batch APIs, subsampling |
| `src/ml-baselines/` | Classical ML + neural-net baselines (sklearn, XGBoost, PyTorch) |
| `src/fine-tuning/` | Frontier fine-tuning and QLoRA/PEFT |
| `src/agents/` | Multi-agent orchestration |
| `src/deployment/` | Serving models (e.g. Modal) |
| `src/extras/` | Sandbox experiments |
| `src/shared/` | Reusable code shared across topics (data models, evaluation, utilities) |

## Setup

Requires [uv](https://docs.astral.sh/uv/) and Python 3.12.

```bash
uv sync                 # create .venv and install dependencies
cp .env.example .env    # then fill in your API keys
uv run jupyter lab      # or open a topic folder in your editor
```

Secrets live in `.env` at the repo root (git-ignored). Common keys: `OPENAI_API_KEY`,
`ANTHROPIC_API_KEY`, `GOOGLE_API_KEY`, `GROQ_API_KEY`, `HF_TOKEN`. Local models run
via [Ollama](https://ollama.com/) on `http://localhost:11434`.

## Conventions

- **Organize by topic, not by week.** New material goes into the matching folder.
- **Reuse via `shared/`.** Anything used by two or more topics belongs there.
- **Notebooks explore, modules stabilize.** Once a notebook idea settles, lift the
  reusable parts into a `.py` module (in the topic folder, or `shared/`).
