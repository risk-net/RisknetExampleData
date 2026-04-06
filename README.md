# RiskNet Example Data
[中文文档](./README_cn.md)

## Multi-dimensional-Classification_results.json

### File Introduction

This file is stored in standard **JSON array** format (not JSONL), which is convenient for direct field-level inspection.

It contains **auto-labeled risk classification results** inferred by the fine-tuned `Qwen3-32B SFT` model.

Each record matches one original AI risk event through the unique `event_id`, and includes related event news details.

### Field Description

* `event_id`
  Global unique key, used to join with the event detail file for fusion analysis.
* `llmpredict` (model prediction object)
  * `entity`: Responsible subject of the risk, values: `Human` / `AI` / `Other`

  * `intent`: Behavior intention of the risk event, values: `Intentional` / `Unintentional` / `Other`
  * `time`: Occurrence stage of risk lifecycle, values: `Pre-deployment` / `Post-deployment` / `Other`
  * `eu_ai_act`: Compliance risk level aligned with EU AI Act, including `Unacceptable Risk` / `High Risk` / `Limited Risk` / `Minimal/No Risk`
  * `domain_classification`: Two-level category in array format, covering full standardized risk scenarios (e.g., discrimination, privacy security, misinformation, fraud, targeted manipulation).
* `event_news`
  Event-linked news list (array of objects). Each item is a structured news/event record (e.g., `title`, `content`, `release_date`, `event_country`, `harm_type`, `risk_stage`, etc.).
* `event_news_count`
  Number of associated `event_news` records for this `event_id`.
