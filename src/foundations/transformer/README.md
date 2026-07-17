# The Transformer, A to Z

A learning series — **one concept per notebook**, built from scratch with runnable code and
visual examples. Read in order.

| # | Notebook | What you learn |
|---|---|---|
| 00 | `00-big-picture.ipynb` | LLM = next-token predictor; the `softmax` tool; the full pipeline |
| 01 | `01-tokenization.ipynb` | Text → token ids via BPE; why `transformers` splits; tokens ≠ words |
| 02 | `02-embeddings.ipynb` | Token ids → meaning vectors; similarity as geometry |
| 03 | `03-positional-encoding.ipynb` | Injecting word order; the sinusoidal heatmap |
| 04 | `04-self-attention.ipynb` | **The heart** — Q/K/V, scaled dot-product, attention heatmap |
| 05 | `05-causal-masking.ipynb` | No peeking at the future; why models are decoder-only |
| 06 | `06-multi-head-attention.ipynb` | Many attention views in parallel |
| 07 | `07-feed-forward.ipynb` | Per-token MLP; where most parameters live; GELU |
| 08 | `08-residual-layernorm.ipynb` | The glue that makes deep stacks trainable |
| 09 | `09-transformer-block.ipynb` | Assemble one real block (PyTorch); stack N |
| 10 | `10-training-objective.ipynb` | Output head, next-token prediction, cross-entropy |
| 11 | `11-architectures-and-modern-tricks.ipynb` | Encoder/decoder families, RoPE, KV cache, GQA, MoE… |

## How to run
```bash
uv run jupyter lab      # then open notebooks in this folder, run top to bottom
```
Core math uses only **numpy**; the full block uses **PyTorch**; visuals use **matplotlib**;
tokenization uses **tiktoken**. Each notebook is self-contained.

## Related
- `../base-instruct-reasoning-models.ipynb` — the three model types share *this exact*
  architecture; they differ only in training.
