# RiskNet Example Data


## Multi-dimensional-Classification_results.json

### File Introduction

This file contains **auto-labeled risk classification results** inferred by the fine-tuned `Qwen3-32B SFT` model.

Each record matches one original AI risk event through the unique `event_id`.

### Field Description

* `event_id`
  Global unique key, used to join with the event detail file for fusion analysis.
* `llmpredict` (model prediction object)* `entity`: Responsible subject of the risk, values: `Human` / `AI` / `Other`

  * `intent`: Behavior intention of the risk event, values: `Intentional` / `Unintentional` / `Other`
  * `time`: Occurrence stage of risk lifecycle, values: `Pre-deployment` / `Post-deployment` / `Other`
  * `eu_ai_act`: Compliance risk level aligned with EU AI Act, including `Unacceptable Risk` / `High Risk` / `Limited Risk` / `Minimal/No Risk`
  * `domain_classification`: Two-level category in array format, covering full standardized risk scenarios (e.g., discrimination, privacy security, misinformation, fraud, targeted manipulation).
