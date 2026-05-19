# 外联回复到访谈证据工作流

更新时间：2026-05-19

## 目的

现在已经有两批服务商外联对象和话术。下一步的关键不是继续扩名单，而是把每一次回复都变成可判断的证据：哪些服务商愿意聊，哪些愿意看样例，哪些愿意提供真实门店，哪些明确反对。

这份文件用于把 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 的外联动作，转成：

1. [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 的回复记录。
2. [templates/interview_tracker.csv](./templates/interview_tracker.csv) 的访谈记录。
3. [templates/evidence_index.csv](./templates/evidence_index.csv) 的证据索引。
4. Issue #1/#3/#4/#5 的 Go/No-Go 判断输入。

## 发送后立刻记录

每发出一条外联，就更新两处。

### 更新 outreach_batch

在 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 中：

- `status`：从 `待发送` 改成 `已发送`。
- `next_step`：写下一步日期，例如 `2026-05-20 未回复则跟进`。
- `notes`：补发送渠道，例如官网表单、公众号私信、微信、邮箱、电话。

### 新增 reply_log 行

在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 新增一行：

| 字段 | 填法 |
| --- | --- |
| `reply_id` | RPL001 开始递增 |
| `date` | 发送或收到回复日期 |
| `lead_id` | 对应 L014/L017 等 |
| `batch_id` | B001 或 B002 |
| `contact_channel` | 官网表单/公众号/微信/电话/邮箱 |
| `sent_status` | 已发送/发送失败/待补资料 |
| `reply_status` | 未回复/已回复/拒绝/约访/转介绍 |
| `raw_quote_or_screenshot_path` | 截图或原话路径，没有就先空着 |
| `next_step` | 跟进、约访、发样例、关闭 |

## 回复分级

| 回复类型 | 判定 | 处理 |
| --- | --- | --- |
| A1 | 愿意提供真实门店和竞品 | 立即进入 [34_issue_1_execution_packet.md](./34_issue_1_execution_packet.md) |
| A2 | 愿意拿样例报告给商家试讲 | 进入 [37_issue_4_report_feedback_packet.md](./37_issue_4_report_feedback_packet.md) |
| B1 | 愿意访谈，但暂不提供门店 | 安排 20 分钟访谈，填 interview_tracker |
| B2 | 愿意看样例，但没有承诺 | 发 [06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)，48 小时后跟进 |
| C | 只说可以了解/先看看 | 记录弱信号，不追超过 2 次 |
| D | 明确拒绝、认为无用、认为重复 | 记录为 No-Go 证据 |

## 约到访谈后的记录顺序

访谈发生后，不要只更新一个地方。按下面顺序处理：

1. 在 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 新增访谈行。
2. 在 `key_quotes` 写入 2-5 条服务商原话。
3. 在 `signal_grade` 填 A/B/C/D。
4. 在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 填 `related_interview_id`。
5. 在 [templates/evidence_index.csv](./templates/evidence_index.csv) 新增一条证据，类型填 `interview_note` 或 `chat_screenshot`。

## 关键字段口径

### interest_level

- `强`：主动问样例、价格、交付方式，或愿意提供门店。
- `中`：愿意访谈或看样例，但没有具体下一步。
- `弱`：只礼貌回复，无法说出业务场景。
- `负向`：明确认为商家不需要、听不懂、不会付费或和现有工具重复。

### merchant_report_reaction

- `可用于签约`：认为报告能放进售前或提案。
- `可用于月报`：认为报告能补充月度复盘。
- `可用于续费`：认为报告能解释服务价值或下月计划。
- `只适合内部`：服务商自己看有用，但不愿给商家看。
- `无价值`：认为商家不关心。

### objection

优先记录原话，不要翻译成自己的判断。常见类型：

- 商家听不懂 AI 推荐。
- 和抖音来客/巨量本地推/飞瓜/新抖重复。
- 数据不稳定，怕讲不清。
- 服务商一线运营没时间多做报告。
- 只能免费送，不能单独收费。

## 从回复进入真实门店测试

只要任一服务商出现下面任一承诺，就停止继续扩名单，优先跑真实门店：

1. 愿意提供 1 家真实门店。
2. 愿意提供 3 个竞品。
3. 愿意看完真实报告后给反馈。
4. 愿意拿样例给商家试讲。

进入真实门店测试时需要填：

- [templates/store_intake.csv](./templates/store_intake.csv)
- [templates/competitors.csv](./templates/competitors.csv)
- [templates/prompt_bank.csv](./templates/prompt_bank.csv)
- [templates/answer_runs.csv](./templates/answer_runs.csv)
- [templates/evidence_index.csv](./templates/evidence_index.csv)

## 48 小时跟进话术

如果对方未回复：

> 补充一下，这次不是销售软件，主要想验证服务商是否需要一种新的商家月报/续费材料。你只需要帮我判断两件事：商家能不能听懂，以及服务商愿不愿意拿它试讲。可以先发你一份样例报告，5 分钟看完即可。

如果对方愿意看样例但没约访：

> 我先发你一个低保真样例。你看完后能不能帮我判断三点：第一，商家是否听得懂；第二，它更适合签约、月报还是续费；第三，如果换成你们真实门店，你愿不愿意让我免费跑一版？

如果对方说不感兴趣：

> 明白，感谢直接反馈。方便追问一句：主要原因是商家不关心、你们现有工具已经覆盖，还是这个结果很难转成运营动作？这条反馈对我判断要不要继续做很关键。

## 5 条回复后的阶段判断

拿到 5 条有效回复后，先做一次小判断。

继续推进真实门店测试的条件：

1. 至少 1 条 A1/A2。
2. 或至少 2 条 B1/B2，且都认为报告可用于签约、月报或续费。
3. 或至少 1 个服务商明确说出可接受价格、预算来源或试点条件。

暂缓的条件：

1. 5 条回复里没有任何人愿意访谈。
2. 多数回复认为商家听不懂或不会买。
3. 服务商只愿意免费看看，没人愿意提供门店或二访。

暂缓不等于放弃，但需要更新 [00_decision_memo.md](./00_decision_memo.md)、[15_final_research_synthesis.md](./15_final_research_synthesis.md) 和 [29_goal_completion_audit.md](./29_goal_completion_audit.md)，把真实反馈写进去。
