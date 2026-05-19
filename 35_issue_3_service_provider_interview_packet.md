# Issue #3 执行包：服务商访谈

更新时间：2026-05-19

对应 GitHub issue：[ #3 Interview 5-10 Douyin local-life service providers](https://github.com/daniel-yu-gold/geo-research/issues/3)

## 目标

访谈 5-10 个抖音本地生活服务商/运营商，判断“门店 AI 可见性体检 + 优化任务 + 商家月报”是否真的能进入他们的签约、交付、月报、续费或增购流程。

这一步要验证的不是“他们觉得 AI 新不新”，而是：

1. 他们是否愿意给真实门店做测试。
2. 他们是否愿意把报告拿给商家讲。
3. 他们是否能说出明确使用场景和预算来源。
4. 他们是否愿意试点、付费或转介绍。

## 访谈对象优先级

优先约这 3 类人：

| 优先级 | 对象 | 为什么 |
| --- | --- | --- |
| P0 | 抖音生活服务服务商老板/负责人 | 能判断买不买、怎么卖、是否愿意试点 |
| P0 | 一线运营/项目经理 | 知道月报、内容、达人 Brief、续费的真实痛点 |
| P1 | 本地推/达人探店机构负责人 | 可判断报告是否能作为销售和内容选题工具 |

暂缓约：

- 只卖课程培训的人。
- 只做纯拍摄、不负责抖音经营闭环的小团队。
- 完全不服务实体店商家的泛 MCN。

## 20 分钟访谈结构

### 0-2 分钟：开场

建议说：

> 我现在不是卖一个现成产品，而是在判断一个新方向值不值得做：给抖音本地生活服务商用的“门店 AI 可见性体检”。简单说，就是看用户问豆包、DeepSeek、Kimi 这类 AI“附近适合约会/生日/聚餐的店”时，会不会推荐客户门店，还是推荐竞品；再把问题转成短视频、团购、达人 Brief 和月报任务。想请你帮我判断它能不能进入服务商真实业务。

### 2-7 分钟：当前业务

必须问：

1. 你们主要服务哪些行业？
2. 现在卖给商家的服务包是什么？
3. 客单价和服务周期大概在哪个区间？
4. 新客户为什么签约？老客户为什么续费或流失？
5. 每个月大概给多少家门店做复盘或月报？

记录到：

- `service_categories`
- `current_services`
- `monthly_price_range`
- `biggest_pain`
- `active_monthly_report_stores`

### 7-12 分钟：月报和交付痛点

必须问：

1. 月报里现在最重要的指标是什么？
2. 月报最耗时的部分是什么？
3. 商家最常质疑什么？
4. 你们有没有想展示但现在拿不出来的结论？
5. 内容选题、团购卖点、达人 Brief 现在怎么定？

记录到：

- `monthly_report_pain`
- `renewal_objection`
- `current_tools`
- `most_valuable_deliverable`

### 12-17 分钟：抛出产品假设

建议不要先说 GEO。用这个表达：

> 如果我们每月帮你测一组高意图问题，比如“某商圈适合生日的餐厅”“某品类哪家适合约会”“A 店和 B 店哪个更适合朋友聚餐”，看 AI 是否推荐客户门店、推荐了哪些竞品、说错了哪些信息，然后输出一份商家能看懂的体检报告和下月任务单，你会不会用？

必须追问：

1. 商家听得懂吗？
2. 你会放进签约 PPT、月报、续费复盘，还是内部诊断？
3. 最有价值的是报告、任务单、脚本、达人 Brief、月报，还是销售 PPT？
4. 它和抖音来客、巨量本地推、新抖、飞瓜这些工具重复吗？
5. 如果现在给你一个半自动版本，你能接受哪些人工环节？

记录到：

- `ai_visibility_reaction`
- `merchant_understandability`
- `most_valuable_deliverable`
- `use_case_fit`
- `tool_overlap_concern`

### 17-20 分钟：争取下一步

必须问到具体承诺：

1. 你愿意给我 1 家真实门店和 3 个竞品，免费跑一版样例吗？
2. 如果样例成立，你愿意拿给商家试讲吗？
3. 如果每月批量出报告，你觉得按门店、报告、服务商账号还是分成收费合理？
4. 什么价格会太贵？什么价格可以试？
5. 什么结果出现，你愿意连续试 3 个月？

记录到：

- `willing_to_provide_real_store`
- `willing_to_show_to_merchants`
- `willing_to_pay_trial`
- `acceptable_price`
- `preferred_pricing_model`
- `expected_delivery_cost_limit`
- `next_step`

## 访谈后 3 分钟内必须完成

访谈结束后立刻做 4 件事：

1. 在 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 新增一行。
2. 把关键原话写到 `key_quotes`，不要只写自己的总结。
3. 给出 `signal_grade`：A/B/C/D。
4. 把访谈纪要或录音路径写入 [templates/evidence_index.csv](./templates/evidence_index.csv)。

## 信号分级

| 等级 | 判定标准 | 下一步 |
| --- | --- | --- |
| A | 愿意给真实门店，并愿意拿报告给商家试讲 | 立刻推进 Issue #1 和 #4 |
| B | 认可月报/续费价值，但暂不承诺付费 | 发样例，约二访 |
| C | 觉得概念新，但说不出业务场景 | 记录异议，暂不深追 |
| D | 明确认定商家不买单或和现有工具重复 | 作为 No-Go 证据 |

## 5 个访谈后的快速判断

完成 5 个有效访谈后，不必等到 10 个再判断一次。

### 继续推进的最低信号

满足其中 2 条，就值得继续跑真实门店报告：

1. 至少 2 个服务商愿意提供真实门店。
2. 至少 2 个服务商愿意看真实报告后二访。
3. 至少 1 个服务商愿意拿报告给商家试讲。
4. 至少 1 个服务商能说出明确付费方式和价格区间。
5. 多数服务商认为它能进入月报、签约或续费，而不只是内部学习。

### 暂缓或转向信号

出现下面情况，要更新 Go/No-Go，不要继续硬推：

1. 5 个访谈里没有任何人愿意提供真实门店。
2. 服务商普遍认为商家听不懂，且无法换成经营语言。
3. 他们认为和现有抖音数据工具高度重复。
4. 他们只想免费附赠，不愿意作为增值模块或工具付费。
5. 一线运营觉得报告增加工作量，不能节省交付时间。

## 记录字段速查

| 字段 | 怎么填 |
| --- | --- |
| `ai_visibility_reaction` | 强 / 中 / 弱 / 负向 |
| `merchant_understandability` | 能听懂 / 需要换话术 / 听不懂 / 未验证 |
| `most_valuable_deliverable` | 报告 / 任务单 / 脚本 / 达人 Brief / 月报 / 销售 PPT |
| `use_case_fit` | 签约前诊断 / 月报增值 / 续费复盘 / 投放前策略 / 内容选题 / 不适配 |
| `budget_source` | 代运营服务费 / 月报增值 / 投放前诊断 / AI 工具预算 / 分成 / 无预算 |
| `tool_overlap_concern` | 不重复 / 部分重复 / 高度重复 / 不确定 |
| `willing_to_show_to_merchants` | 是 / 否 / 看真实报告后再说 |
| `willing_to_provide_real_store` | 是 / 否 / 需要老板同意 / 需要匿名 |
| `willing_to_pay_trial` | 是 / 否 / 看效果 / 只接受免费 |
| `signal_grade` | A / B / C / D |

## 后续衔接

如果访谈拿到真实门店：

- 更新 [templates/store_intake.csv](./templates/store_intake.csv)
- 执行 [34_issue_1_execution_packet.md](./34_issue_1_execution_packet.md)

如果访谈拿到报告试讲机会：

- 执行 [#4 Validate report usefulness with service providers](https://github.com/daniel-yu-gold/geo-research/issues/4)

如果访谈连续出现反向信号：

- 更新 [00_decision_memo.md](./00_decision_memo.md)
- 更新 [15_final_research_synthesis.md](./15_final_research_synthesis.md)
- 更新 [29_goal_completion_audit.md](./29_goal_completion_audit.md)
