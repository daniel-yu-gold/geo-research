# 真实验证 Day 1 操作工作单

更新时间：2026-05-19

## 目的

这份工作单只解决一件事：把今天的动作从“准备充分”推进到“开始产生真实证据”。

它不替代 [18_pilot_runbook.md](./18_pilot_runbook.md)，也不把未发送、未回复、未访谈的准备动作计入完成度。只有外部服务商真实回复、真实访谈、真实门店资料、真实 AI 回答和真实报告反馈，才进入 [templates/validation_status.csv](./templates/validation_status.csv)。

## 今日最低目标

今天只追 4 个结果：

| 顺序 | 目标 | 最低完成口径 | 记录位置 |
| ---: | --- | --- | --- |
| 1 | 发出 B002 第一轮外联 | L014/L017/L015 每家至少 1 个公开入口已发送 | [templates/outreach_batch.csv](./templates/outreach_batch.csv)、[templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) |
| 2 | 拿到至少 1 个可判断回复 | 对方明确同意、拒绝、要求资料、转联系人或提出异议 | [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) |
| 3 | 约到至少 1 个 20 分钟访谈 | 有具体时间、联系人或下一步确认方式 | [templates/interview_tracker.csv](./templates/interview_tracker.csv) |
| 4 | 争取 1 家真实门店 | 对方愿意提供门店，或用户自己指定可测门店 | [templates/store_intake.csv](./templates/store_intake.csv) |

如果今天只完成第 1 项，也仍然是有效推进；但验证状态仍保持 0，直到出现真实回复。

## 90 分钟执行流

### 0-10 分钟：打开 3 个表

先打开：

- [templates/outreach_send_payloads.csv](./templates/outreach_send_payloads.csv)
- [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv)
- [templates/day1_live_validation_log.csv](./templates/day1_live_validation_log.csv)

不要先改 [templates/validation_status.csv](./templates/validation_status.csv)。

### 10-35 分钟：发送 3 条最小外联

按这个顺序发：

| 顺序 | payload_id | lead_id | 对象 | 优先入口 | 发送后 reply_id |
| ---: | --- | --- | --- | --- | --- |
| 1 | PAY001 或 PAY002 | L014 | 随趣传媒 | 官网运营需求入口 / 在线客服 | RPL001 |
| 2 | PAY004 或 PAY005 | L017 | 鹏讯传媒 | 官网合作意向表单 / 在线咨询 | RPL002 |
| 3 | PAY007 或 PAY008 | L015 | 运朗科技/运达社 | 商务合作二维码 / 微信 | RPL003 |

发送时只复制 [45_first_outreach_send_payloads.md](./45_first_outreach_send_payloads.md) 或 [templates/outreach_send_payloads.csv](./templates/outreach_send_payloads.csv) 里的文本，不临场扩写。

每发完一条，立即登记：

1. 在 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 把对应 `status` 改成 `已发送`。
2. 在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 新增一行，`reply_status` 先写 `未回复`。
3. 在 [templates/day1_live_validation_log.csv](./templates/day1_live_validation_log.csv) 记录发送入口、时间和截图路径。

### 35-55 分钟：发二跳资料

如果对方回复“发我看看”“你们是做什么的”“有没有样例”，只发 3 句话：

> 我们不是卖现成软件，现在在验证服务商是否需要这个能力。  
> 样例是：测 1 家门店在豆包、DeepSeek、Kimi 里的推荐情况，看 AI 推荐客户门店还是竞品，并生成商家能看懂的体检报告和下月任务。  
> 我想请你帮忙判断：它能不能放进签约诊断、商家月报或续费沟通里？

然后约 20 分钟：

> 方便今天或明天约 20 分钟吗？我主要想问你真实服务商视角，不会做产品销售。

登记到 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv)，`reply_status` 根据真实情况写：

- `有兴趣`
- `要求资料`
- `约访中`
- `拒绝`
- `无关`
- `未回复`

### 55-75 分钟：把回复转成访谈或门店

收到正向回复时，立刻问两个具体问题：

1. 你们现在给商家做月报或续费复盘吗？
2. 能不能给我 1 家匿名门店和 3 个竞品，我免费跑一版给你判断？

如果对方愿意访谈：

- 在 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 新增一行，`status` 写 `已约待访谈`。
- `related_reply_id` 写对应 `RPL001/RPL002/RPL003`。
- 访谈问题用 [35_issue_3_service_provider_interview_packet.md](./35_issue_3_service_provider_interview_packet.md)。

如果对方愿意给门店：

- 在 [templates/store_intake.csv](./templates/store_intake.csv) 记录门店信息。
- 立即执行 [34_issue_1_execution_packet.md](./34_issue_1_execution_packet.md)。

### 75-90 分钟：复盘证据口径

只做 3 个判断：

| 问题 | 是 | 否 |
| --- | --- | --- |
| 是否有真实服务商回复？ | 更新 V002 的证据备注，但只有有效回复才加 count | 保持 V002 为 0 |
| 是否约到真实访谈？ | 准备访谈纪要，不提前计 V001 | 继续 48 小时跟进 |
| 是否拿到真实门店？ | 开始 Issue #1 | 继续争取门店 |

不要因为“已发送”就把 [templates/validation_status.csv](./templates/validation_status.csv) 的 `current_real_count` 改成 1。

## 回复分级

| 分级 | 真实回复表现 | 下一步 | 计数 |
| --- | --- | --- | --- |
| A | 愿意访谈，并愿意提供真实门店或看报告 | 约访谈，启动门店测试 | V002 可计 1；访谈发生后 V001 才计 |
| B | 愿意了解样例或要求资料 | 发 3 句话资料，约 20 分钟 | V002 可计 1 |
| C | 只礼貌回复，但没有业务判断 | 48 小时后追问具体问题 | 视内容决定，通常不计有效回复 |
| D | 明确拒绝或认为不需要 | 记录反向证据 | V002 可计 1，作为反向证据 |
| X | 自动回复、无关客服、无法判断 | 换入口或换联系人 | 不计 |

## 今天不能做的事

- 不能把官网线索、公开资料或发送动作算作服务商需求已验证。
- 不能用虚构门店报告替代真实门店报告。
- 不能把“对方愿意看看”写成“愿意付费”。
- 不能在没有原话、截图或纪要的情况下更新完成度。

## 今日结束时应留下的东西

至少留下：

- [templates/day1_live_validation_log.csv](./templates/day1_live_validation_log.csv) 有 3 条发送记录。
- [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 有 `RPL001-RPL003`，即使暂时是 `未回复`。
- 如有回复，必须有截图路径或原话。
- 如有访谈预约，必须有时间或下一步确认方式。
- 如有真实门店，必须有门店名、城市、商圈、品类和 3 个竞品候选。

## 下一步

如果今天拿到至少 1 个 A/B 回复：

1. 按 [35_issue_3_service_provider_interview_packet.md](./35_issue_3_service_provider_interview_packet.md) 完成访谈。
2. 访谈后 3 分钟内补 [templates/interview_tracker.csv](./templates/interview_tracker.csv) 和 [templates/evidence_index.csv](./templates/evidence_index.csv)。
3. 有真实门店后进入 [34_issue_1_execution_packet.md](./34_issue_1_execution_packet.md)。

如果 48 小时后仍无回复：

1. 用 [40_second_outreach_batch.md](./40_second_outreach_batch.md) 扩大样本。
2. 同时从用户身边可接触的餐饮/丽人门店里选 1 家，先跑真实 AI 回答测试。
3. 把无回复也记录为市场验证信号，不要只保留正向材料。
