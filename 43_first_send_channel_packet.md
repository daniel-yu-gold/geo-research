# 第一轮可发送入口核验包

更新时间：2026-05-19

## 目的

这份文件把 B002 批次前三个优先外联对象，从“有话术”推进到“能找到入口发送”。

当前仍未发送真实外联，因此不计入真实证据。发送后必须更新：

- [templates/outreach_batch.csv](./templates/outreach_batch.csv)
- [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv)
- [templates/validation_status.csv](./templates/validation_status.csv)

## 可发送对象

| 顺序 | lead_id | 公司/团队 | 当前核验结论 | 优先发送入口 | 备选入口 |
| ---: | --- | --- | --- | --- | --- |
| 1 | L014 | 随趣传媒 | 官网公开本地生活/抖音服务商定位，并公开电话、邮箱、在线客服和运营需求入口 | 官网运营需求入口或在线客服 | 电话、邮箱 |
| 2 | L017 | 鹏讯传媒 | 官网公开合作热线、商务邮箱和合作意向表单；地域修正为乌鲁木齐/新疆 | 官网合作意向表单 | 合作热线、商务邮箱 |
| 3 | L015 | 运朗科技/运达社 | 官网公开联系电话、地址和商务合作二维码 | 商务合作二维码 | 电话 |

## L014 随趣传媒

公开入口：

- 官网关于我们页：https://suiqu.net/2.html
- 官网服务页：https://suiqu.net/

发送建议：

1. 先使用官网运营需求入口或在线客服。
2. 如果表单不可用，再使用公开电话或邮箱。
3. 发送后在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 新增 `RPL001`。

发送时使用 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 中 B002/L014 的话术。

## L017 鹏讯传媒

公开入口：

- 官网首页：https://pxinter.com/
- 联系我们页：https://pxinter.com/contact.html

发送建议：

1. 优先提交官网合作意向表单。
2. 备选使用合作热线或商务邮箱。
3. 发送后新增 `RPL002`。

注意：此前表里写成华南线索不准确，已修正为乌鲁木齐/新疆区域服务商线索。

## L015 运朗科技/运达社

公开入口：

- 官网首页：https://www.yundashe.cn/
- 联系我们页：https://www.yundashe.cn/contact.html

发送建议：

1. 优先使用官网商务合作二维码。
2. 备选使用官网公开电话。
3. 发送后新增 `RPL003`。

注意：此前表里简称“运达社”，现在补充为“运朗科技/运达社”，避免 review 时看不清主体。

## 发送后状态更新

每发出一条，立刻做 3 个动作：

1. 在 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 把对应行 `status` 改为 `已发送`。
2. 在 [templates/outreach_reply_log.csv](./templates/outreach_reply_log.csv) 新增一行，`reply_status` 先填 `未回复`。
3. 48 小时内如果收到回复，按 [41_outreach_reply_to_interview_workflow.md](./41_outreach_reply_to_interview_workflow.md) 分级。

## 不要提前计数

当前只是入口核验，仍不能算作：

- 有效外联回复。
- 服务商访谈。
- 真实门店测试。
- 真实产品反馈。

只有收到真实回复并登记原话或截图后，才可以更新 [templates/validation_status.csv](./templates/validation_status.csv) 的 `current_real_count`。
