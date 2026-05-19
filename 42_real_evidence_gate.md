# 真实证据门槛与计数规则

更新时间：2026-05-19

## 目的

当前仓库已经有完整的桌面研究、产品假设、外联话术、访谈模板、AI 测试模板和报告模板。但这些还不能替代真实证据。

这份文件用于防止两类误判：

1. 把模板里的示例行当成真实访谈或真实测试。
2. 把“已准备好执行”误判为“已经完成验证”。

当前真实验证状态见 [templates/validation_status.csv](./templates/validation_status.csv)。

## 当前真实证据状态

| 要求 | 当前真实数量 | 完成门槛 | 状态 |
| --- | ---: | ---: | --- |
| 服务商有效访谈 | 0 | 5 | 未开始 |
| 外联有效回复 | 0 | 5 | 未开始 |
| 真实门店 AI 回答记录 | 0 | 60 | 未开始 |
| 真实门店报告 | 0 | 1 | 未开始 |
| 服务商看真实报告后的反馈 | 0 | 2 | 未开始 |
| 最终 Go/No-Go 修订 | 0 | 1 | 未开始 |

因此，当前 goal 仍然不能标记完成。

## 什么可以算真实证据

### 服务商访谈

可以计入：

- 对象是真实抖音本地生活服务商、代运营团队、达人探店机构、本地推服务团队或相关一线运营。
- 访谈已经发生，不是预计会发生。
- 有原话、截图、会议纪要或录音路径。
- 已写入 [templates/interview_tracker.csv](./templates/interview_tracker.csv)。
- 已在 [templates/evidence_index.csv](./templates/evidence_index.csv) 登记。

不能计入：

- `示例姓名`、`示例公司` 这类模板行。
- 只来自官网、招聘页、新闻稿的公开资料。
- 只有“感觉他们会需要”的推断。
- 已发送外联但没有回复。

### 外联回复

可以计入：

- 对方已经真实回复。
- 能判断至少一项：愿意访谈、愿意看样例、愿意提供门店、明确拒绝、认为重复、认为商家听不懂。
- 已写入 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv)。

不能计入：

- [templates/outreach_batch.csv](./templates/outreach_batch.csv) 里的待发送话术。
- “待确认”“待发送”“待核验联系方式”。
- 没有截图或原话的转述。

### 真实门店 AI 测试

可以计入：

- 门店是真实存在的实体店。
- 有 3 个真实竞品。
- 每条回答有 AI 入口、测试时间、prompt、原始回答、是否提及目标门店、竞品提及和截图或原文证据。
- 已写入 [templates/answer_runs.csv](./templates/answer_runs.csv)。
- 已在 [templates/evidence_index.csv](./templates/evidence_index.csv) 登记。

不能计入：

- `示例问题`。
- `粘贴原始回答` 这种占位。
- 虚构门店或无截图、无原文、无测试时间的回答。

### 真实门店报告

可以计入：

- 报告基于真实 answer_runs 和截图。
- 报告能追溯到 [templates/report_scorecard.csv](./templates/report_scorecard.csv) 和 [templates/evidence_index.csv](./templates/evidence_index.csv)。
- 报告里至少有 3 类可执行建议：资料修正、内容任务、商家汇报点。

不能计入：

- [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md) 的虚构样例。
- 只复制 [13_real_store_report_template.md](./13_real_store_report_template.md) 但没有真实数据。

## 示例行处理规则

目前这些文件里有教学用示例行：

- [templates/interview_tracker.csv](./templates/interview_tracker.csv)
- [templates/answer_runs.csv](./templates/answer_runs.csv)
- [templates/evidence_index.csv](./templates/evidence_index.csv)

示例行保留用于说明字段怎么填，但它们不能进入完成计数。判断时优先看：

1. 是否包含 `示例`。
2. `verification_status` 是否为 `待补真实证据`。
3. 是否缺少真实截图、原话或原始回答。
4. 是否能追到真实服务商、真实门店或真实 AI 回答。

只要不能追溯到真实对象，就不能算完成。

## 完成判定顺序

要判断 goal 是否能完成，按这个顺序查：

1. 先看 [templates/validation_status.csv](./templates/validation_status.csv) 是否全部达到门槛。
2. 再看每个真实记录是否能追溯到 [templates/evidence_index.csv](./templates/evidence_index.csv)。
3. 再看 [00_decision_memo.md](./00_decision_memo.md)、[15_final_research_synthesis.md](./15_final_research_synthesis.md)、[29_goal_completion_audit.md](./29_goal_completion_audit.md) 是否已经基于真实证据修订。
4. 最后才能考虑 goal 是否完成。

如果任何一项仍是 0，或者只有示例行，goal 必须继续保持 active。

## 当前最短推进路径

不要继续扩写桌面研究。下一步只做真实动作：

1. 发送 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 中 B002 的 L014、L017、L015。
2. 每条发送后在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 新增记录。
3. 48 小时内拿到回复则按 [41_outreach_reply_to_interview_workflow.md](./41_outreach_reply_to_interview_workflow.md) 分级。
4. 任一服务商愿意提供真实门店，就立即执行 [34_issue_1_execution_packet.md](./34_issue_1_execution_packet.md)。
