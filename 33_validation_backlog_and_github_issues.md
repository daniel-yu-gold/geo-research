# 真实验证 backlog 与 GitHub issue 规划

更新时间：2026-05-19

## 目的

当前仓库已经完成桌面研究、产品假设、样例和验证工具，但 GEO 赛道进入判断还没有被真实证据证明。这个 backlog 的作用是把剩余工作拆成可以在 GitHub 上跟踪、review 和关闭的任务。

关闭全部 P0 issue 后，才有资格更新 [00_decision_memo.md](./00_decision_memo.md) 和 [15_final_research_synthesis.md](./15_final_research_synthesis.md)，形成最终 Go/No-Go。

## P0：证明这个赛道是否值得继续投入

| Issue | 目标 | 关闭标准 | 主要产物 |
| --- | --- | --- | --- |
| P0-1 真实门店 AI 可见性测试 | 用真实门店替换虚构样例，验证 AI 入口中是否存在门店/竞品差异 | 至少 1 家真实门店、3 个同城竞品、20 个 prompts、3 个 AI 入口、完整记录 answer_runs 和 evidence_index | `templates/stores.csv`, `templates/competitors.csv`, `templates/answer_runs.csv`, `templates/evidence_index.csv` |
| P0-2 生成真实门店报告 | 把真实问答测试转成服务商能拿去讲的门店报告 | 至少 1 份真实门店报告，包含问题、竞品对比、优化任务和证据链接 | `evidence/reports/` 或新增真实报告 Markdown |
| P0-3 服务商访谈 5-10 个 | 验证服务商是否有购买/转卖/使用场景 | 至少 5 条访谈记录，最好 10 条；每条记录买单意愿、使用场景、价格、异议 | `templates/interview_tracker.csv`, `27_interview_synthesis_template.md` |
| P0-4 服务商看报告反馈 | 验证报告是否能进入签约、月报、续费或增购流程 | 至少 2 个服务商看过真实报告，并明确反馈是否愿意试讲、试点或付费 | `templates/interview_tracker.csv`, `templates/evidence_index.csv` |
| P0-5 最终 Go/No-Go 更新 | 基于真实证据判断进入、暂缓或放弃 | 更新结论，明确证据、风险、下一步资源投入，不再只停留在桌面研究 | `00_decision_memo.md`, `15_final_research_synthesis.md`, `29_goal_completion_audit.md` |

## P1：如果 P0 信号为正，再做

| Issue | 目标 | 关闭标准 | 主要产物 |
| --- | --- | --- | --- |
| P1-1 ICP 重估 | 判断最佳客户到底是服务商、商家、MCN、代运营团队还是工具渠道 | 基于访谈反馈重写 ICP 和买单链路 | `02_china_douyin_operator_product_hypothesis.md`, `19_business_model_and_gtm_canvas.md` |
| P1-2 MVP 范围收敛 | 把产品从研究样例收敛为 2 周可交付版本 | P0/P1/P2 功能重新排序，删掉服务商不买账的功能 | `12_mvp_prd.md` |
| P1-3 定价与交付成本模型 | 验证半自动报告是否有毛利空间 | 明确服务商可接受价格、单店交付成本、人力成本比例 | `25_market_sizing_model.md`, `14_metric_dictionary_and_experiment_log.md` |
| P1-4 第二行业样例 | 如果餐饮成立，扩展到丽人或酒旅/亲子 | 至少 1 个新行业样例和 prompt bank | `templates/prompt_bank.csv`, 新增样例报告 |

## 每个 issue 的通用关闭规则

1. 不能只写“已调研”或“感觉可行”，必须有可追溯证据。
2. 真实访谈要记录对象类型、业务规模、当前工具、痛点、预算来源、反对意见和下一步承诺。
3. 真实 AI 测试要记录平台、时间、设备、账号状态、定位状态、原始问题、原始回答和截图或证据路径。
4. 任何影响结论的证据都要写入 [templates/evidence_index.csv](./templates/evidence_index.csv)。
5. 如果证据反向，也要保留；这个研究的目标是判断是否进入，不是证明一定要做。

## 推荐执行顺序

1. 先执行 P0-1，因为没有真实 AI 问答差异，后面的报告和销售验证都会变弱。
2. 接着执行 P0-2，用真实数据生成一份能给服务商看的报告。
3. 同步推进 P0-3，先约 5 个服务商访谈。
4. 用 P0-2 的报告做 P0-4，测试服务商是否愿意把它拿给商家。
5. 最后执行 P0-5，更新最终进入判断。

## GitHub issue 建议标题

已创建下面 5 个 P0 issue：

1. [#1 `[P0] Run real-store AI visibility test`](https://github.com/daniel-yu-gold/geo-research/issues/1)
2. [#2 `[P0] Generate first real-store AI visibility report`](https://github.com/daniel-yu-gold/geo-research/issues/2)
3. [#3 `[P0] Interview 5-10 Douyin local-life service providers`](https://github.com/daniel-yu-gold/geo-research/issues/3)
4. [#4 `[P0] Validate report usefulness with service providers`](https://github.com/daniel-yu-gold/geo-research/issues/4)
5. [#5 `[P0] Update final Go/No-Go from real evidence`](https://github.com/daniel-yu-gold/geo-research/issues/5)

这 5 个 issue 关闭之前，不建议把 goal 标为完成。
