# Adapting distilgpt2 to Australian parliamentary reports: full fine-tuning vs LoRA

SIT319 Deep Learning, Deakin University (Assignment 4).

## What this project does
A small pretrained language model (`distilgpt2`) is adapted to the style of an Australian parliamentary report on the UN Declaration on the Rights of Indigenous Peoples. Two methods are compared: full fine-tuning and LoRA. Both are evaluated with perplexity on the same report and on a related held-out report about economic self-determination.

## Main results

| Model | Parameters updated | Training time (min) | PPL UNDRIP val | PPL Economic test |
|---|---:|---:|---:|---:|
| Pretrained | 0 | 0 | 55.49 | 59.56 |
| Full fine-tuned | 81,912,576 | 0.24 | 30.24 | 42.04 |
| LoRA (r=8, c_attn) | 147,456 | 0.14 | 45.83 | 49.93 |

LoRA updated about 555 times fewer parameters, but recovered only about 38% of the full fine-tuning gain on the validation text after one epoch.

## How to run
Open the notebook in Google Colab with a T4 GPU. Run the first cell, restart the session, then run all cells.

## Data sources
Reports by the Joint Standing Committee on Aboriginal and Torres Strait Islander Affairs, Parliament of Australia (2023 and 2024).
