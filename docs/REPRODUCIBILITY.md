# Reproducibility Notes

The source code under `src/rlhf_pipeline` contains the compact RLHF pipeline used for the study.

## Pipeline Stages

1. Prepare Anthropic HH-RLHF preference data with prompt deduplication.
2. Train the supervised fine-tuned reference policy `pi_0`.
3. Train the scalar reward model `R_phi` and calibrate it with validation temperature scaling.
4. Run PPO stress tests and UP-PPO mitigation runs.
5. Run DPO as a preference-optimization baseline.
6. Evaluate saved policy checkpoints with reward-model score, MC-dropout uncertainty, approximate KL drift, Anthropic judge, and OpenAI judge.
7. Generate publication tables and figures.

## Key Configuration

- Backbone: `openai-community/gpt2`.
- Reward uncertainty: MC dropout, `p=0.1`, `K=4` stochastic passes.
- Main UP-PPO penalty: `lambda=0.1`.
- Stress-test PPO: zero explicit KL penalty, sampled rollouts, checkpoints through step 1200.
- Judges: Anthropic `claude-sonnet-4-5-20250929` and OpenAI `gpt-4o-mini`.

## Environment Variables

Typical variables used by the pipeline include:

```bash
export RLHF_ARTIFACTS=/path/to/artifacts
export RLHF_JUDGE=anthropic
export RLHF_JUDGE_2=openai
export ANTHROPIC_API_KEY=...
export OPENAI_API_KEY=...
```

Do not commit `.env` files or API keys.
