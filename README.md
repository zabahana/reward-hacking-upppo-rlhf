# Reward Hacking in RLHF: Detection and Mitigation with UP-PPO

This repository contains the curated publication artifacts and reproducibility code for a compact RLHF study of reward hacking and uncertainty-penalized PPO (UP-PPO).

## Paper

- `paper/reward_hacking_upppo_rlhf.pdf`: compiled manuscript.
- `paper/reward_hacking_upppo_rlhf.tex`: LaTeX source.

## Repository Structure

```text
paper/      Manuscript source and compiled PDF
figures/    Publication figures used in the paper
tables/     Result tables and diagnostics supporting the claims
examples/   Curated qualitative/example artifacts
src/        Minimal RLHF pipeline code for reproducibility
docs/       Reproducibility and artifact notes
```

## Main Empirical Claim

Aggressive PPO can improve the learned reward-model proxy while reducing externally judged quality. In the reported stress test, PPO improves the proxy reward from `-0.734` to `-0.657` between steps 1000 and 1200, while the two-judge mean falls from `2.988` to `2.754`. UP-PPO with `lambda=0.1` mitigates the mined failure rows by reducing proxy reward and improving the two-judge average.

## What Is Included

This repository intentionally includes only publication-relevant artifacts: paper source/PDF, referenced figures, compact CSV/Markdown tables, selected examples, and source code. It excludes model checkpoints, API keys, local virtual environments, LaTeX auxiliary files, and large raw rollout files.

## Reproducibility Notes

See `docs/REPRODUCIBILITY.md` for the high-level training/evaluation sequence and environment variables. External judge scores require user-provided Anthropic and OpenAI API keys.
