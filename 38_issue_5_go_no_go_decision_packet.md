# Issue #5 执行包：基于真实证据更新最终 Go/No-Go

更新时间：2026-05-19

对应 GitHub issue：[ #5 Update final Go/No-Go from real evidence](https://github.com/daniel-yu-gold/geo-research/issues/5)

## 目标

把真实门店测试、真实报告、服务商访谈和报告反馈，收敛成最终进入判断：

- Go：进入半自动 MVP 或付费试点。
- Continue Validation：继续小规模验证，但不开发完整产品。
- Pivot：保留部分能力，转向更明确的抖音内容、团购、达人或月报工具。
- No-Go：停止这个 GEO/AI 可见性方向。

Issue #5 不是再写一篇总结，而是做一次证据审计。每个判断都必须能追溯到真实数据、访谈原话、报告反馈或成本记录。

## 前置条件

开始 #5 前，至少需要：

1. Issue #1 有真实门店 AI 测试结果，或有足够反向证据证明测试无价值。
2. Issue #2 有至少 1 份真实门店报告，或证明报告无法形成。
3. Issue #3 有至少 5 个有效服务商访谈。
4. Issue #4 有至少 2 个服务商看过真实报告后的反馈。
5. 关键证据都登记在 [templates/evidence_index.csv](./templates/evidence_index.csv)。

如果这些条件没有满足，只能更新“当前状态”，不能关闭 #5，也不能标记 thread goal 完成。

## 决策输入

| 输入 | 最低证据 | 对应文件 |
| --- | --- | --- |
| 真实门店测试 | 1 家门店、3 个竞品、20 prompts、3 个 AI 入口 | `templates/answer_runs.csv`, `templates/report_scorecard.csv` |
| 真实报告 | 1 份真实门店报告，关键发现可追溯 | `evidence/reports/`, `templates/report_finding_cards.csv` |
| 服务商访谈 | 至少 5 个有效访谈 | `templates/interview_tracker.csv`, `27_interview_synthesis_template.md` |
| 报告反馈 | 至少 2 个服务商看过真实报告 | `templates/report_feedback.csv` |
| 成本记录 | 单店测试和报告生成耗时 | `14_metric_dictionary_and_experiment_log.md` 或新增实验记录 |
| 证据索引 | 关键结论都能追溯 | `templates/evidence_index.csv` |

## 决策维度

使用 [templates/go_no_go_evidence_scorecard.csv](./templates/go_no_go_evidence_scorecard.csv) 逐项打分。

### 1. 客户需求强度

看服务商是否有真实业务场景：

- 是否愿意提供真实门店。
- 是否愿意拿报告给商家试讲。
- 是否认为报告能进入签约、月报、续费或增购。
- 是否主动讨论价格、批量门店、白标或试点。

### 2. AI 差异可解释性

看真实门店测试是否产生可产品化信号：

- 是否有 30% 以上高意图问题出现门店/竞品差异、信息错误或内容缺口。
- 差异是否能转成抖音经营任务。
- 多个 AI 入口是否出现相似问题类型。
- 结果是否能对商家解释，而不是纯技术波动。

### 3. 报告可销售性

看真实报告是否能被服务商拿去用：

- 商家摘要是否听得懂。
- 任务单是否能进入服务商交付。
- 服务商是否愿意试讲。
- 服务商是否提出具体改版建议而不是泛泛称赞。

### 4. 商业可行性

看付费和成本是否成立：

- 至少 2 个服务商给出可接受价格或付费方式。
- 单店报告生成成本低于可接受价格的 25%。
- 付费方式明确：单店报告、门店数、服务商账号、白标月报、分成。
- 预算来源明确：代运营服务费、月报增值、签约诊断、投放前策略或 AI 工具预算。

### 5. 竞争与替代风险

看是否被现有工具或人工流程覆盖：

- 服务商是否认为和抖音来客、巨量本地推、新抖、飞瓜重复。
- 差异是否足够明确：AI 问答入口 + 竞品场景 + 任务闭环。
- 服务商是否认为自己用通用大模型即可完成。
- 报告是否带来节省时间或提高销售转化，而不只是多一份材料。

### 6. 技术交付风险

看 MVP 是否能低成本复制：

- 是否可以先用人工提问 + Answer Scorer + 报告模板交付。
- 是否必须依赖高风险自动化采集。
- AI 回答波动是否可以通过固定 prompt、复测和证据留档解释。
- 单店测试和报告生成是否能在可接受时间内完成。

## 推荐判定规则

### Go

同时满足：

1. 至少 4/10 或 2/5 服务商愿意拿报告给商家试讲。
2. 至少 2 个服务商愿意付费试点，或明确给出可接受价格。
3. 真实测试中 30% 以上高意图 prompts 产生可解释差异或任务。
4. 至少 2 个服务商认为报告能进入签约、月报、续费或增购。
5. 单店报告生成成本低于服务商可接受价格的 25%。

建议动作：

- 更新 [12_mvp_prd.md](./12_mvp_prd.md) 为 2 周半自动 MVP。
- 更新 [19_business_model_and_gtm_canvas.md](./19_business_model_and_gtm_canvas.md) 的定价和销售路径。
- 设计第一批 2-3 个付费试点。

### Continue Validation

满足部分正向信号，但证据不够：

1. 服务商听得懂，但付费意愿不明确。
2. 真实门店有差异，但样本太少或稳定性不足。
3. 报告能用于月报，但还不能用于签约或续费。
4. 成本可控，但服务商预算来源不清楚。

建议动作：

- 再跑 2 家门店。
- 再访谈 5 个服务商。
- 只迭代报告和任务单，不开发完整 SaaS。

### Pivot

出现这些信号：

1. 服务商对 AI 可见性兴趣一般，但强烈需要内容选题、团购卖点、达人 Brief 或月报自动化。
2. AI 测试差异弱，但报告生成和任务单有价值。
3. 服务商不愿为 AI 体检付费，但愿为抖音交付效率付费。

建议动作：

- 转向“抖音本地生活服务商月报/任务单生成器”。
- 保留 AI 可见性作为一个诊断模块，而不是主卖点。

### No-Go

出现这些信号：

1. 5 个服务商里没有人愿意提供真实门店。
2. 2 个服务商看真实报告后都不愿给商家试讲。
3. 真实 AI 测试几乎没有门店级可解释差异。
4. 报告不能转成短视频、团购、达人 Brief、FAQ 或评价素材任务。
5. 服务商普遍认为商家听不懂、不愿付费或和现有工具重复。

建议动作：

- 停止 GEO/AI 可见性方向。
- 保留已完成的研究和工具资产，转向更直接的抖音交付效率机会。

## 必须更新的文件

关闭 #5 前，至少更新：

1. [00_decision_memo.md](./00_decision_memo.md)：最终结论、证据、下一步投入建议。
2. [15_final_research_synthesis.md](./15_final_research_synthesis.md)：综合版结论和证据链。
3. [29_goal_completion_audit.md](./29_goal_completion_audit.md)：按原始 goal 重新审计完成状态。
4. [templates/go_no_go_evidence_scorecard.csv](./templates/go_no_go_evidence_scorecard.csv)：逐项证据评分。

如果结论为 Go 或 Continue Validation，还要更新：

5. [12_mvp_prd.md](./12_mvp_prd.md)：MVP 范围、P0/P1/P2。
6. [19_business_model_and_gtm_canvas.md](./19_business_model_and_gtm_canvas.md)：定价、GTM、销售路径。

## 最终结论模板

建议在 [00_decision_memo.md](./00_decision_memo.md) 追加：

```md
## 最终 Go/No-Go 更新

更新时间：

最终判断：Go / Continue Validation / Pivot / No-Go

核心证据：

1. 客户需求：
2. 真实门店 AI 差异：
3. 报告可销售性：
4. 商业可行性：
5. 技术可交付性：

最大风险：

1.
2.
3.

下一步动作：

1.
2.
3.
```

## Goal 完成判断

只有当下面 7 项都具备证据时，才可以考虑把 thread goal 标记完成：

1. 国外工具分析已完成。
2. 国内需求调研包含真实服务商访谈。
3. 市场与竞争评估已结合真实预算和替代竞争反馈修订。
4. 技术可实现性已通过真实门店测试验证。
5. 产品闭环经过服务商反馈。
6. 产品样例包含至少 1 份真实门店报告。
7. 最终 Go/No-Go 已基于真实证据更新。

如果任一项缺失，goal 继续保持 active。
