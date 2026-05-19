# GEO 赛道研究交付清单与 Quickstart

更新时间：2026-05-19

## 这份文件怎么用

这是一份交付导航。它不新增研究结论，只回答三个问题：

1. 现在已经交付了什么。
2. 不同角色应该先看哪几份文件。
3. 下一步怎样把桌面研究推进到真实验证。

当前状态可以概括为：桌面研究包、产品假设、原型、试点模板、服务商访谈工具已经齐备；但 goal 还不能标记完成，因为真实服务商访谈、真实门店 AI 回答测试、用户/团队背景评估尚未补齐。

## 从哪开始

如果你只想判断要不要继续投：

1. 先读 [15_final_research_synthesis.md](./15_final_research_synthesis.md)，看综合结论。
2. 再读 [00_decision_memo.md](./00_decision_memo.md)，看 Go/No-Go 标准和 14 天计划。
3. 最后读 [19_business_model_and_gtm_canvas.md](./19_business_model_and_gtm_canvas.md)，看商业模式、销售路径和定价假设。

如果你准备马上做真实试点：

1. 先按 [18_pilot_runbook.md](./18_pilot_runbook.md) 执行 3 天试点。
2. 用 [tools/prompt-builder.html](./tools/prompt-builder.html) 生成测试问题。
3. 用 [tools/answer-scorer.html](./tools/answer-scorer.html) 记录 AI 回答并打分。
4. 用 [13_real_store_report_template.md](./13_real_store_report_template.md) 生成真实门店报告。

如果你准备约抖音服务商聊：

1. 先读 [20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md)，按 10 分钟话术约访。
2. 再读 [11_prototype_test_guide.md](./11_prototype_test_guide.md)，知道演示时要问什么。
3. 演示 [prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html) 或 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)。
4. 用 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 记录反馈。

如果你要把项目交给别人继续：

1. 先让对方读本文件和 [README.md](./README.md)。
2. 再让对方读 [10_completion_audit_checklist.md](./10_completion_audit_checklist.md)，明确哪些是已完成，哪些是待验证。
3. 最后让对方按 [18_pilot_runbook.md](./18_pilot_runbook.md) 跑最小验证。

## 30 分钟阅读路径

适合你快速恢复上下文，或者给合伙人/顾问做第一次同步。

1. 5 分钟：[README.md](./README.md)
2. 10 分钟：[15_final_research_synthesis.md](./15_final_research_synthesis.md)
3. 5 分钟：[00_decision_memo.md](./00_decision_memo.md)
4. 5 分钟：[06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)
5. 5 分钟：[20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md)

读完应该能回答：

- 这个赛道目前为什么是“谨慎看多”。
- 产品不应该直接叫“GEO 工具”，而应包装成服务商可交付的门店 AI 可见性体检/月报工具。
- 下一步最小验证不是写更多报告，而是跑真实门店和约服务商反馈。

## 3 天执行路径

### Day 1：准备真实门店测试

目标：选 1 家真实餐饮/丽人/酒旅门店，配 3 个同城竞品，生成 20 个高意图 prompts。

使用文件：

- [07_real_store_test_protocol.md](./07_real_store_test_protocol.md)
- [tools/prompt-builder.html](./tools/prompt-builder.html)
- [templates/stores.csv](./templates/stores.csv)
- [templates/competitors.csv](./templates/competitors.csv)
- [templates/prompt_bank.csv](./templates/prompt_bank.csv)

### Day 2：跑 AI 回答与评分

目标：在至少 3 个 AI 入口手动测试，记录答案、推荐情况、竞品压力、错误信息和可执行任务。

使用文件：

- [tools/answer-scorer.html](./tools/answer-scorer.html)
- [templates/answer_runs.csv](./templates/answer_runs.csv)
- [templates/report_scorecard.csv](./templates/report_scorecard.csv)
- [14_metric_dictionary_and_experiment_log.md](./14_metric_dictionary_and_experiment_log.md)

### Day 3：服务商验证

目标：把真实门店报告或低保真样例拿给 2 个服务商看，验证他们是否愿意试讲、试点或付费。

使用文件：

- [13_real_store_report_template.md](./13_real_store_report_template.md)
- [20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md)
- [08_service_provider_outreach_and_sales_test.md](./08_service_provider_outreach_and_sales_test.md)
- [templates/interview_tracker.csv](./templates/interview_tracker.csv)

## 交付资产地图

### 决策与综合判断

- [00_decision_memo.md](./00_decision_memo.md)：进入判断和 14 天计划。
- [10_completion_audit_checklist.md](./10_completion_audit_checklist.md)：判断 goal 是否完成的检查表。
- [15_final_research_synthesis.md](./15_final_research_synthesis.md)：研究综合版。

### 国外产品与技术参考

- [01_foreign_geo_tool_scan.md](./01_foreign_geo_tool_scan.md)：国外工具和可借鉴范式。
- [05_technical_feasibility_mvp_architecture.md](./05_technical_feasibility_mvp_architecture.md)：MVP 架构和技术可行性。
- [09_report_generation_spec.md](./09_report_generation_spec.md)：报告生成规范。
- [12_mvp_prd.md](./12_mvp_prd.md)：MVP PRD。

### 国内客户与市场

- [02_china_douyin_operator_product_hypothesis.md](./02_china_douyin_operator_product_hypothesis.md)：客户需求假设和产品闭环。
- [03_market_competition_assessment.md](./03_market_competition_assessment.md)：市场与竞争评估。
- [16_public_customer_signal_research.md](./16_public_customer_signal_research.md)：公开客户需求信号。
- [21_founder_market_fit_assessment.md](./21_founder_market_fit_assessment.md)：自身背景/团队适配度框架。

### 服务商验证

- [04_customer_research_plan.md](./04_customer_research_plan.md)：访谈方案。
- [08_service_provider_outreach_and_sales_test.md](./08_service_provider_outreach_and_sales_test.md)：外联和异议处理。
- [17_service_provider_lead_sourcing.md](./17_service_provider_lead_sourcing.md)：线索筛选与优先级。
- [20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md)：10 分钟 Pitch 包。

### 产品样例与原型

- [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)：虚构门店报告样例。
- [prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html)：低保真工作台原型。
- [11_prototype_test_guide.md](./11_prototype_test_guide.md)：原型访谈指南。

### 真实试点执行

- [07_real_store_test_protocol.md](./07_real_store_test_protocol.md)：真实门店测试协议。
- [13_real_store_report_template.md](./13_real_store_report_template.md)：真实门店报告模板。
- [14_metric_dictionary_and_experiment_log.md](./14_metric_dictionary_and_experiment_log.md)：指标和实验记录。
- [18_pilot_runbook.md](./18_pilot_runbook.md)：3 天试点 Runbook。

### 本地工具与表格模板

- [tools/prompt-builder.html](./tools/prompt-builder.html)：生成门店测试 prompts。
- [tools/answer-scorer.html](./tools/answer-scorer.html)：记录 AI 回答并生成评分。
- [templates/](./templates/)：门店、竞品、prompt、回答、评分、访谈和线索模板。

## 当前完成度

已完成：

- 国外代表工具扫描和技术范式拆解。
- 国内抖音服务商需求假设和公开信号研究。
- 市场、竞争、商业模式和 GTM 初版。
- 产品闭环、报告样例、低保真原型、Prompt Builder、Answer Scorer。
- 真实试点 Runbook、访谈话术、线索池、指标口径、MVP PRD。

仍缺：

- 5-10 个真实服务商访谈。
- 至少 1-3 家真实门店的 AI 回答测试。
- 基于真实数据生成的门店报告。
- 服务商对报告、定价、销售路径的反馈。
- 用户/团队真实背景输入，用来完成 founder-market fit 判断。

## 交接检查清单

交接给别人前，确认对方已经拿到：

- 项目目标和当前结论：[README.md](./README.md)
- 完成度边界：[10_completion_audit_checklist.md](./10_completion_audit_checklist.md)
- 最小执行方案：[18_pilot_runbook.md](./18_pilot_runbook.md)
- 服务商约访材料：[20_service_provider_pitch_packet.md](./20_service_provider_pitch_packet.md)
- 门店测试工具：[tools/prompt-builder.html](./tools/prompt-builder.html)、[tools/answer-scorer.html](./tools/answer-scorer.html)
- 数据记录模板：[templates/](./templates/)

## 下一步建议

不要继续扩写桌面研究。下一步最值得做的是：

1. 选 1 家真实门店。
2. 用 Prompt Builder 生成 20 个问题。
3. 在 3 个 AI 入口跑完回答。
4. 用 Answer Scorer 得出分数。
5. 生成 1 份真实报告。
6. 拿给 2 个服务商，测试他们是否愿意把它卖给商家。

这 6 步完成后，研究才会从“看起来有机会”推进到“市场是否真的愿意接”的阶段。
