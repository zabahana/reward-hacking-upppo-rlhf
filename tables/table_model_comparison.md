# Table 1. Model comparison on generated rollouts

| Model | R_phi | Anthropic | OpenAI | Judge avg. | u | KL to SFT |
| --- | --- | --- | --- | --- | --- | --- |
| SFT | -0.817 | 2.809 | 3.420 | 3.115 | 0.172 | 0.000 |
| DPO | -0.751 | 2.874 | 3.598 | 3.236 | 0.179 | 0.092 |
| UP-PPO lambda=0.0 | -1.245 | 1.530 | 1.324 | 1.427 | 0.233 | 0.866 |
| UP-PPO lambda=0.1 | -1.308 | 1.287 | 1.373 | 1.330 | 0.232 | 1.215 |
| UP-PPO lambda=0.5 | -1.259 | 1.339 | 1.404 | 1.372 | 0.219 | 0.776 |
| UP-PPO lambda=1.0 | -1.232 | 1.271 | 1.352 | 1.312 | 0.225 | 1.479 |

Values are means over 512 prompts. SFT and DPO rows average repeated judge calls across lambda-tagged runs.
