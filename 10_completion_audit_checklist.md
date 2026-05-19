# GEO 赛道研究完成度检查表

更新时间：2026-05-19

## 目的

用于判断“GEO 赛道进入判断研究”什么时候可以真正标记完成。

当前状态：研究框架和执行模板已完成，但真实访谈和真实门店测试尚未完成，因此不应标记完成。

## 目标拆解

原目标：

> 完成 GEO 赛道进入判断研究，包括国外工具分析、国内抖音运营商需求调研、市场与竞争评估、技术可实现性判断，并输出一个产品闭环和产品样例。

## 完成标准

| 模块 | 当前证据 | 状态 | 完成条件 |
| --- | --- | --- | --- |
| 国外工具分析 | 01_foreign_geo_tool_scan.md | 已完成初版 | 至少覆盖 5 个代表产品、产品范式、技术路径、可借鉴点 |
| 国内目标客户需求假设 | 02_china_douyin_operator_product_hypothesis.md、04_customer_research_plan.md | 已完成假设，待访谈验证 | 完成 5-10 个服务商访谈，补充真实原话和需求矩阵 |
| 国内公开客户需求信号 | 16_public_customer_signal_research.md | 已完成公开资料层补强 | 用真实访谈验证服务商是否认可这些需求 |
| 市场大小与竞争评估 | 03_market_competition_assessment.md | 已完成初版 | 补充来源更新和真实客户反馈后修订 Go/No-Go |
| 技术可实现性判断 | 05_technical_feasibility_mvp_architecture.md | 已完成初版 | 用真实门店样例验证半自动流程成本 |
| 产品闭环 | 00_decision_memo.md、02_china_douyin_operator_product_hypothesis.md | 已完成初版 | 访谈确认闭环是否适合服务商销售/交付 |
| 产品样例 | 06_product_sample_store_ai_visibility_report.md | 已有虚构样例 | 用真实门店数据生成 1-2 份可演示样例 |
| 真实门店测试 | 07_real_store_test_protocol.md、templates/*.csv | 模板已完成 | 至少 3 家门店、每家 20 个 prompts、3 个以上 AI 入口 |
| 服务商销售验证 | 08_service_provider_outreach_and_sales_test.md、templates/interview_tracker.csv | 模板已完成 | 至少 5 个有效访谈，记录试点/付费意愿 |
| 服务商线索池 | 17_service_provider_lead_sourcing.md、templates/lead_tracker.csv | 已完成线索筛选方法和记录模板 | 填入 12 条真实线索并完成至少 5 个访谈 |
| 报告生成规范 | 09_report_generation_spec.md | 已完成初版 | 用真实样例跑通并修订 |
| 产品原型 | prototype/store-ai-visibility.html、11_prototype_test_guide.md | 已完成低保真原型 | 至少 2 个服务商看过并给出反馈 |
| MVP PRD | 12_mvp_prd.md | 已完成初版 | 根据真实试点反馈修订 P0/P1 |
| 指标口径 | 14_metric_dictionary_and_experiment_log.md | 已完成初版 | 用真实数据验证是否好解释 |
| 综合研究结论 | 15_final_research_synthesis.md | 已完成初版 | 根据真实服务商访谈和真实门店测试修订最终判断 |
| Prompt Builder | tools/prompt-builder.html | 已完成本地静态工具 | 用真实门店生成一批 prompts 并完成测试 |
| Answer Scorer | tools/answer-scorer.html | 已完成本地静态工具，可生成 answer_runs、report_scorecard、evidence_index 和商家报告草稿 | 用真实 AI 回答生成 answer_runs、report_scorecard、证据索引和真实门店报告草稿 |
| 试点 Runbook | 18_pilot_runbook.md | 已完成执行步骤 | 按 Runbook 完成 1 家真实门店和 2 个服务商访谈 |
| 商业模式与 GTM | 19_business_model_and_gtm_canvas.md | 已完成假设版 | 用真实服务商反馈验证销售路径和定价 |
| 服务商 Pitch 包 | 20_service_provider_pitch_packet.md | 已完成一页式话术和演示流程 | 用于至少 2 次服务商访谈并记录反馈 |
| 自身背景适配度 | 21_founder_market_fit_assessment.md | 已完成评估框架 | 补充用户/团队真实背景后形成具体判断 |
| 交付导航 | 22_delivery_inventory_and_quickstart.md | 已完成交付清单和使用顺序 | 用于交接、恢复上下文和推进 3 天验证 |
| 国外到国内产品对照 | 23_foreign_to_china_product_gap_matrix.md | 已完成对照矩阵 | 用真实服务商反馈验证改造后的闭环是否可售卖 |
| 国内替代竞争扫描 | 24_domestic_substitute_and_competition_scan.md | 已完成官方工具、第三方工具和人工交付扫描 | 访谈验证服务商是否认为产品与现有工具重复，或能形成增值模块 |
| 市场规模模型 | 25_market_sizing_model.md | 已完成 TAM/SAM/SOM 口径、收入模型和敏感性测算 | 用真实服务商付费意愿验证 ARPA、门店覆盖和交付成本假设 |
| AI 入口测试矩阵 | 26_ai_entrance_test_matrix.md | 已完成入口优先级、环境字段和质量控制规则 | 用真实门店测试验证哪些入口能稳定产出可解释差异 |
| 访谈结果汇总模板 | 27_interview_synthesis_template.md、templates/interview_tracker.csv | 已完成预算、替代竞争、试讲和付费字段 | 完成 5-10 个真实访谈后汇总 Go/No-Go 证据 |
| 验证证据包 | 28_validation_evidence_binder.md、templates/evidence_index.csv、evidence/README.md | 已完成证据留档规则和索引模板 | 真实测试和访谈后补齐截图、原始回答、访谈原话和报告版本 |
| Goal 完成审计 | 29_goal_completion_audit.md | 已完成按原始 goal 的逐项证据审计 | 用真实访谈、真实门店测试和最终判断修订后复审 |
| 第一批外联作战清单 | 30_first_outreach_batch.md、templates/outreach_batch.csv | 已完成 6 个优先服务商线索、定制话术和判级规则 | 实际发出外联并完成至少 2 个服务商访谈 |
| 联系渠道核验 | 31_contact_channel_discovery.md、templates/lead_tracker.csv、templates/outreach_batch.csv | 已完成第一批 6 条线索的公开联系入口初步核验 | 发出 L002/L010 第一轮外联，并继续补齐其余 4 条联系方式 |

## 下一阶段最低交付物

要把 goal 标记完成，至少还需要：

1. 真实门店测试记录。
   - 填完 [templates/stores.csv](./templates/stores.csv)
   - 填完 [templates/competitors.csv](./templates/competitors.csv)
   - 填完 [templates/answer_runs.csv](./templates/answer_runs.csv)
   - 生成 [templates/report_scorecard.csv](./templates/report_scorecard.csv)

2. 服务商访谈记录。
   - 至少 5 个有效访谈。
   - 填完 [templates/interview_tracker.csv](./templates/interview_tracker.csv)
   - 把访谈纪要和关键原话登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)
   - 提炼强/弱信号和原话。

3. 真实门店样例报告。
   - 把 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md) 的虚构案例替换或复制成真实案例版本。

4. 修订最终进入判断。
   - 更新 [00_decision_memo.md](./00_decision_memo.md)
   - 明确 Go、No-Go 或继续小规模试点。

5. 修订 MVP 方案。
   - 更新 [12_mvp_prd.md](./12_mvp_prd.md)
   - 根据真实服务商反馈调整 P0/P1 功能边界。

## 当前不能标记完成的原因

- 国内抖音运营商需求还停留在研究假设和访谈方案，没有真实访谈证据。
- 产品样例是虚构门店，还没有真实门店回答数据。
- 市场和技术判断尚未经过真实试跑成本验证。

## 可以继续推进的最小动作

1. 找 1 家真实餐饮门店。
2. 选 3 个竞品。
3. 使用 [templates/prompt_bank.csv](./templates/prompt_bank.csv) 生成 20 个 prompts。
4. 在 3 个 AI 入口手动测试。
5. 生成 1 份真实报告。
6. 拿给 2 个服务商看。

这 6 步完成后，就能把研究从“桌面研究”推进到“市场验证”。
