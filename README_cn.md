# RiskNet 示例数据
[English](./README.md)
## Multi-dimensional-Classification_results.json

### 文件说明
本文件采用标准 **JSON 数组** 格式（非 JSONL），便于直接查看和检索各字段。

本文件包含由精调后的 `Qwen3-32B SFT` 模型推理得到的**风险分类自动标注结果**。

每条记录通过唯一的 `event_id` 与对应的原始 AI 风险事件一一匹配，并包含关联新闻明细。

### 字段说明
- `event_id`
  全局唯一键，用于与事件详情文件关联，以进行融合分析。

- `llmpredict`（模型预测对象）
  - `entity`：风险责任主体，取值：`人类` / `人工智能` / `其他`
  - `intent`：风险事件的行为意图，取值：`故意` / `无意` / `其他`
  - `time`：风险生命周期的发生阶段，取值：`部署前` / `部署后` / `其他`
  - `eu_ai_act`：与欧盟人工智能法案对齐的合规风险等级，包括`不可接受风险`、`高风险`、`有限风险`、`最低/无风险`
  - `domain_classification`：数组格式的二级分类，覆盖完整的标准化风险场景（如歧视、隐私安全、虚假信息、诈骗、定向操纵等）。
- `event_news`
  与该事件关联的新闻列表（对象数组），单条新闻包含结构化字段（如 `title`、`content`、`release_date`、`event_country`、`harm_type`、`risk_stage` 等）。
- `event_news_count`
  该 `event_id` 下关联的 `event_news` 数量。
