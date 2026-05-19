# Goal 完成审计矩阵

更新时间：2026-05-19

## 原始 goal

> 完成 GEO 赛道进入判断研究，包括国外工具分析、国内抖音运营商需求调研、市场与竞争评估、技术可实现性判断，并输出一个产品闭环和产品样例。

## 当前结论

当前不能标记 goal 完成。

原因不是材料不足，而是有三类核心证据尚未发生：

1. 真实服务商访谈。
2. 真实门店 AI 回答测试。
3. 基于真实反馈修订后的最终 Go/No-Go。

当前状态更准确地说是：

> 桌面研究、产品假设、验证工具、试点模板和证据留档体系已完成；真实市场验证尚未完成。

## 逐项审计

| Goal 要求 | 当前证据 | 当前状态 | 为什么还不能算完全完成 | 完成所需证据 |
| --- | --- | --- | --- | --- |
| 国外工具分析 | [01_foreign_geo_tool_scan.md](./01_foreign_geo_tool_scan.md)、[23_foreign_to_china_product_gap_matrix.md](./23_foreign_to_china_product_gap_matrix.md) | 桌面研究已完成 | 只能证明国外范式可参考，不能证明中国服务商愿意买 | 访谈验证服务商是否认可“监测、诊断、任务、报告”改造后的产品闭环 |
| 国内抖音运营商需求调研 | [02_china_douyin_operator_product_hypothesis.md](./02_china_douyin_operator_product_hypothesis.md)、[04_customer_research_plan.md](./04_customer_research_plan.md)、[16_public_customer_signal_research.md](./16_public_customer_signal_research.md)、[27_interview_synthesis_template.md](./27_interview_synthesis_template.md) | 假设和公开信号已完成，真实调研未完成 | 没有真实服务商原话、预算反馈、试讲意愿和付费意愿 | 至少 5-10 个服务商访谈，填完 [templates/interview_tracker.csv](./templates/interview_tracker.csv)，并汇总到 27 |
| 市场与竞争评估 | [03_market_competition_assessment.md](./03_market_competition_assessment.md)、[24_domestic_substitute_and_competition_scan.md](./24_domestic_substitute_and_competition_scan.md)、[25_market_sizing_model.md](./25_market_sizing_model.md) | 桌面评估和模型已完成 | 市场模型的 ARPA、预算来源、门店覆盖数仍是假设 | 访谈验证预算来源、可接受价格、是否和抖音来客/巨量本地推/新抖/飞瓜重复 |
| 技术可实现性判断 | [05_technical_feasibility_mvp_architecture.md](./05_technical_feasibility_mvp_architecture.md)、[07_real_store_test_protocol.md](./07_real_store_test_protocol.md)、[14_metric_dictionary_and_experiment_log.md](./14_metric_dictionary_and_experiment_log.md)、[26_ai_entrance_test_matrix.md](./26_ai_entrance_test_matrix.md)、[tools/answer-scorer.html](./tools/answer-scorer.html) | MVP 技术方案和测试工具已完成 | 尚未用真实门店跑通成本、稳定性和可解释性 | 至少 1 家真实门店、20 个 prompts、3 个 AI 入口、answer_runs、scorecard、截图证据和耗时记录 |
| 产品闭环 | [00_decision_memo.md](./00_decision_memo.md)、[02_china_douyin_operator_product_hypothesis.md](./02_china_douyin_operator_product_hypothesis.md)、[19_business_model_and_gtm_canvas.md](./19_business_model_and_gtm_canvas.md)、[23_foreign_to_china_product_gap_matrix.md](./23_foreign_to_china_product_gap_matrix.md) | 闭环假设已完成 | 未经服务商确认，不知道能否进入签约、月报、续费或投放前诊断 | 至少 2 个服务商看过样例并反馈是否愿意试讲、试点或付费 |
| 产品样例 | [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)、[prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html)、[13_real_store_report_template.md](./13_real_store_report_template.md) | 虚构样例和模板已完成 | 样例不是基于真实门店数据，不能证明产品输出可信 | 用真实门店数据生成至少 1 份报告，并把证据登记到 [templates/evidence_index.csv](./templates/evidence_index.csv) |

## 当前已完成的交付物

### 研究层

- 国外 GEO/AI visibility 工具扫描。
- 国外能力到中国抖音服务商产品的对照矩阵。
- 国内服务商公开需求信号研究。
- 国内替代品和竞争边界扫描。
- 市场规模假设模型和敏感性测算。
- 技术可实现性和 MVP 架构判断。
- 商业模式、GTM 和 founder-market fit 框架。

### 产品层

- 门店 AI 可见性体检报告虚构样例。
- 低保真工作台原型。
- 真实门店报告模板。
- MVP PRD。
- 报告生成规范。
- 产品闭环和服务商销售路径。

### 验证层

- 服务商访谈方案。
- 服务商外联和 Pitch 包。
- 访谈记录表和访谈结果汇总模板。
- 真实门店 AI 测试协议。
- Prompt Builder。
- Answer Scorer。
- AI 入口测试矩阵。
- 证据索引和 evidence 留档规则。
- 3 天 pilot runbook。

## 还缺的硬证据

### 1. 服务商访谈证据

最低要求：

- 5 个有效服务商访谈。
- 最好覆盖负责人和一线运营。
- 每条访谈填入 [templates/interview_tracker.csv](./templates/interview_tracker.csv)。
- 关键原话登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)。
- 访谈结果汇总到 [27_interview_synthesis_template.md](./27_interview_synthesis_template.md)。

需要回答：

- 服务商是否听得懂？
- 商家是否听得懂？
- 是否愿意拿样例试讲？
- 是否愿意提供真实门店？
- 是否愿意付费试点？
- 预算来自哪里？
- 是否和现有工具重复？

### 2. 真实门店 AI 测试证据

最低要求：

- 1 家真实门店。
- 3 个同城竞品。
- 20 个 prompts。
- 3 个 AI 入口。
- 每条回答记录到 [templates/answer_runs.csv](./templates/answer_runs.csv)。
- 汇总到 [templates/report_scorecard.csv](./templates/report_scorecard.csv)。
- 原始回答和截图登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)。

需要回答：

- 是否有 30% 以上 prompts 能形成可解释差异、信息错误或内容缺口？
- 是否能转成短视频、团购、达人 Brief、评价或资料任务？
- 交付一份报告需要多少人工时间？
- 结果是否足够稳定，能对商家解释？

### 3. 真实产品样例

最低要求：

- 用 [13_real_store_report_template.md](./13_real_store_report_template.md) 生成 1 份真实门店报告。
- 不能只用 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md) 的虚构门店。
- 报告中的关键发现必须能追到 answer_runs、截图或原始回答。

需要回答：

- 报告是否清楚？
- 服务商是否愿意给商家看？
- 报告是否能进入签约、月报或续费流程？

### 4. 最终判断修订

最低要求：

- 更新 [00_decision_memo.md](./00_decision_memo.md)。
- 更新 [15_final_research_synthesis.md](./15_final_research_synthesis.md)。
- 根据真实反馈更新 [12_mvp_prd.md](./12_mvp_prd.md) 的 P0/P1。

需要输出：

- Go、No-Go 或继续小规模验证。
- 证据链。
- 最大风险。
- 下一阶段资源投入建议。

## 何时可以标记 goal 完成

只有在以下条件都满足时，才可以调用 goal 完成：

1. 国外工具分析已完成，并且有对中国产品闭环的借鉴结论。
2. 国内需求不只停留在公开资料和假设，至少有 5 个真实服务商访谈。
3. 市场与竞争评估已结合真实预算、价格和替代竞争反馈修订。
4. 技术实现不只停留在架构，至少跑通 1 家真实门店测试并记录成本。
5. 产品闭环经过至少 2 个服务商反馈。
6. 产品样例至少有 1 份真实门店报告，而不只是虚构样例。
7. 证据索引能追溯访谈原话、AI 原始回答、截图和报告版本。
8. 最终进入判断已修订为 Go、No-Go 或继续小规模验证。

## 当前建议

不要再优先扩写桌面研究。下一步应直接执行：

1. 用 [17_service_provider_lead_sourcing.md](./17_service_provider_lead_sourcing.md) 选 5 个服务商。
2. 用 [20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md) 约访。
3. 用 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 记录反馈。
4. 找 1 家真实门店，按 [18_pilot_runbook.md](./18_pilot_runbook.md) 跑测试。
5. 用 [tools/answer-scorer.html](./tools/answer-scorer.html) 生成评分。
6. 用 [13_real_store_report_template.md](./13_real_store_report_template.md) 生成真实报告。
7. 把所有证据登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)。

完成这些后，再回来修订最终判断。
