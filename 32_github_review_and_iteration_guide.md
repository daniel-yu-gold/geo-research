# GitHub review 与下一轮迭代指南

更新时间：2026-05-19

## 这份资料该怎么 review

这不是一份已经证明可以进入的商业计划书，而是一套赛道进入判断包。Review 的重点不是看文字是否完整，而是判断：当前假设是否值得拿真实服务商和真实门店继续验证。

建议按下面顺序看：

1. 先看 [00_decision_memo.md](./00_decision_memo.md) 和 [15_final_research_synthesis.md](./15_final_research_synthesis.md)，判断当前结论是否站得住。
2. 再看 [23_foreign_to_china_product_gap_matrix.md](./23_foreign_to_china_product_gap_matrix.md)，判断国外 GEO/AI visibility 工具能力迁移到中国抖音服务商场景是否合理。
3. 看 [24_domestic_substitute_and_competition_scan.md](./24_domestic_substitute_and_competition_scan.md) 和 [25_market_sizing_model.md](./25_market_sizing_model.md)，判断竞争和市场空间是否支持投入。
4. 看 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)、[prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html)、[tools/prompt-builder.html](./tools/prompt-builder.html)、[tools/answer-scorer.html](./tools/answer-scorer.html)，判断产品样例是否能被服务商理解和转卖。
5. 最后看 [18_pilot_runbook.md](./18_pilot_runbook.md)、[30_first_outreach_batch.md](./30_first_outreach_batch.md)、[31_contact_channel_discovery.md](./31_contact_channel_discovery.md)，判断下一步真实验证是否能执行。

## Review 时优先挑战的 8 个问题

1. 服务商是否真的需要一个新的“AI 可见性”卖点，还是现有抖音团购、达人、直播、投流、代运营服务已经足够？
2. 这个产品的买单人到底是服务商老板、运营负责人、客户成功团队，还是商家侧老板？
3. 服务商会把它当作签约获客工具、续费月报工具、内部诊断工具，还是一个可有可无的展示噱头？
4. 门店级 AI 问答结果是否真的有足够差异，能让报告产生“必须优化”的感觉？
5. 国内 AI 入口的本地生活推荐是否稳定到足以做月度监测，还是波动过大导致交付不可控？
6. 服务商是否愿意为半自动报告付费，还是只愿意在已有服务费里免费附带？
7. 抖音官方工具、巨量本地推、第三方数据平台、服务商人工月报是否会迅速覆盖这个需求？
8. 创始团队是否有足够的抖音服务商资源、门店资源、销售触达能力和交付耐心，撑过冷启动验证？

## 当前最重要的判断

当前资料给出的判断是：

> 值得做轻量验证，但不值得直接重投入做完整 SaaS。

更合理的下一步不是继续堆功能，而是用 1-3 家真实门店和 5-10 个服务商访谈证明三件事：

1. AI 问答里真的存在可解释、可优化、可展示的门店差异。
2. 服务商愿意把这份报告拿去给商家讲，而不只是觉得新鲜。
3. 这件事可以嵌入服务商现有签约、月报、续费或增购流程。

## 下一轮验证输入

开始下一轮前，需要补齐这些真实输入：

| 输入 | 最小数量 | 用途 | 对应文件 |
| --- | ---: | --- | --- |
| 真实门店 | 1 家 | 替换虚构样例，跑通端到端报告 | [templates/stores.csv](./templates/stores.csv) |
| 同城竞品 | 3 家 | 比较 AI 推荐和内容差异 | [templates/competitors.csv](./templates/competitors.csv) |
| AI 问答测试 | 20 个 prompt x 3 个入口 | 验证是否有可诊断差异 | [templates/answer_runs.csv](./templates/answer_runs.csv) |
| 服务商访谈 | 5-10 个 | 验证买单、场景和交付流程 | [templates/interview_tracker.csv](./templates/interview_tracker.csv) |
| 证据索引 | 每条关键证据 1 行 | 保证结论可追溯 | [templates/evidence_index.csv](./templates/evidence_index.csv) |

## 下一轮验证输出

下一轮结束后，应该新增或更新这些材料：

| 输出 | 合格标准 |
| --- | --- |
| 真实门店 AI 可见性报告 | 不再使用虚构门店，包含真实 AI 回答、截图或记录路径、竞品对比、优化任务 |
| 服务商访谈汇总 | 至少 5 个访谈对象，明确记录是否愿意试讲、试点、付费、转介绍 |
| Go/No-Go 更新版 | 明确进入、暂缓、放弃，不能只写“继续观察” |
| 产品闭环更新版 | 根据服务商反馈调整：谁使用、何时使用、怎么卖、怎么交付、怎么续费 |
| MVP 范围更新版 | 删除服务商不买账的功能，保留能进入销售和月报流程的功能 |

## GitHub review 建议

如果在 GitHub 上 review，建议直接围绕下面几个文件开 comment：

- 结论不认可：评论 [00_decision_memo.md](./00_decision_memo.md) 或 [15_final_research_synthesis.md](./15_final_research_synthesis.md)。
- 国外工具迁移逻辑有问题：评论 [23_foreign_to_china_product_gap_matrix.md](./23_foreign_to_china_product_gap_matrix.md)。
- 国内竞争判断不完整：评论 [24_domestic_substitute_and_competition_scan.md](./24_domestic_substitute_and_competition_scan.md)。
- 市场规模假设太乐观或太保守：评论 [25_market_sizing_model.md](./25_market_sizing_model.md)。
- 产品样例不适合服务商销售：评论 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md) 或 [prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html)。
- 真实验证动作不可执行：评论 [18_pilot_runbook.md](./18_pilot_runbook.md)、[30_first_outreach_batch.md](./30_first_outreach_batch.md)、[31_contact_channel_discovery.md](./31_contact_channel_discovery.md)。

## 我下一轮会如何根据 feedback 调整

| Feedback 类型 | 下一步调整 |
| --- | --- |
| 认为赛道不值得做 | 收缩为 No-Go 论证，补充替代机会和放弃理由 |
| 认为服务商不是最佳客户 | 重做 ICP，比较商家、服务商、MCN、SaaS 渠道、代运营团队 |
| 认为产品太重 | 收缩成手工交付包或报告生成器，不做监控型 SaaS |
| 认为证据不足 | 优先补真实门店测试和服务商访谈，不继续扩写二手资料 |
| 认为方向可做 | 把 MVP PRD 收敛成 2 周可交付版本，并设计第一批付费试点 |

## Goal 完成前不能跳过的证据

这个 goal 只有在下面证据都出现后，才适合标记完成：

1. 至少 5 个服务商访谈记录，最好 10 个。
2. 至少 1 家真实门店的 AI 问答测试，不再只依赖虚构样例。
3. 至少 1 份基于真实数据的门店报告。
4. 服务商对报告用途、付费意愿、转卖路径的明确反馈。
5. 基于真实反馈更新后的 Go/No-Go 结论。

当前仓库已经完成桌面研究、假设、样例和验证工具；还没有完成真实市场验证。
