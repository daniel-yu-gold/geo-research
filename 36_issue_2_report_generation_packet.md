# Issue #2 执行包：生成第一份真实门店 AI 可见性报告

更新时间：2026-05-19

对应 GitHub issue：[ #2 Generate first real-store AI visibility report](https://github.com/daniel-yu-gold/geo-research/issues/2)

## 目标

把 Issue #1 的真实 AI 问答测试结果，压缩成一份服务商能在 10 分钟内讲给商家听的报告。

报告不是技术审计，也不是“AI 排名证明”。它必须回答：

1. 这家门店在哪些本地消费问题里被看见。
2. 哪些场景被竞品占住了。
3. AI 回答说错或漏掉了哪些可修正信息。
4. 下月服务商应该交付哪些抖音经营动作。
5. 这份报告是否能用于签约、月报、续费或增购。

## 前置条件

开始 #2 前，至少需要完成：

1. [templates/stores.csv](./templates/stores.csv)：1 家真实门店。
2. [templates/competitors.csv](./templates/competitors.csv)：3 家同城竞品。
3. [templates/answer_runs.csv](./templates/answer_runs.csv)：至少 60 条 AI 回答记录。
4. [templates/evidence_index.csv](./templates/evidence_index.csv)：关键截图、原始回答或来源可追溯。
5. Issue #1 已经判断“有足够差异，值得生成报告”，或明确要用报告验证服务商是否买账。

如果没有真实门店数据，不要用虚构样例关闭 #2。

## 生成流程

### Step 1：先算一张 scorecard

用 [tools/answer-scorer.html](./tools/answer-scorer.html) 或手工更新 [templates/report_scorecard.csv](./templates/report_scorecard.csv)。

必须生成 6 个指标：

| 指标 | 怎么解释给商家 |
| --- | --- |
| AI 推荐可见性 | 用户问高意图消费问题时，本店被 AI 提到的比例 |
| 强推荐率 | 本店被明确推荐或进入前三的比例 |
| 竞品压制率 | 竞品出现但本店没出现的比例 |
| 信息准确性 | AI 对地址、人均、营业时间、特色等描述是否准确 |
| 场景覆盖度 | 约会、生日、聚餐、团购等场景是否被占住 |
| 可转任务率 | 有多少问题能转成下月经营任务 |

### Step 2：把 60 条回答压成 finding cards

新增或更新 [templates/report_finding_cards.csv](./templates/report_finding_cards.csv)。

每条 finding card 必须包含：

- 发现名称
- 相关场景
- 证据 prompt
- 涉及 AI 入口
- 目标门店表现
- 竞品表现
- 推断原因
- 可转任务
- 证据路径
- 是否可进入商家报告

第一份报告只保留 3-5 条 finding。宁可少，也不要把不确定的单次回答塞进报告。

### Step 3：区分商家版和服务商内部版

商家版只讲：

- 哪些问题里本店容易被看到。
- 哪些消费场景弱于竞品。
- 下月做什么。

服务商内部版可以补充：

- 原始 prompt 结果。
- 不同 AI 入口差异。
- 哪些结论证据较弱。
- 哪些内容适合放进销售 PPT。

### Step 4：填写真实报告模板

复制 [13_real_store_report_template.md](./13_real_store_report_template.md)，建议新文件命名：

`evidence/reports/YYYY-MM-DD_store-id_ai_visibility_report.md`

如果 `evidence/reports/` 不存在，先创建目录。

报告最小结构：

1. 基础信息
2. 一句话结论
3. 总览评分
4. 3-5 条关键发现
5. Prompt 结果表摘要
6. 竞品场景地图
7. 下月任务单
8. 给商家的月报摘要
9. 原始材料留档

### Step 5：写 200-300 字商家摘要

摘要不能使用：

- GEO
- Prompt
- 大模型排名
- AI 搜索优化保证

建议表达：

> 本月我们测试了用户可能会问的 20 个本地消费问题，覆盖约会、生日、朋友聚餐和团购套餐等场景。本店在朋友聚餐场景有一定基础，但在生日和约会场景弱于竞品。AI 更常提到竞品的环境、套餐和评价信息，说明这些内容在公开资料里更容易被读取。下月建议重点补齐生日服务说明、双人套餐标题和达人探店口径，完成后用同一批问题复测。

## 哪些发现能进报告

可以进入商家报告：

1. 至少 2 个 AI 入口出现同类问题。
2. 同一场景下目标门店弱、竞品强，且原因能解释。
3. 信息错误明确，例如地址、人均、营业时间、特色说错。
4. 发现能转成短视频、团购、达人 Brief、FAQ、评价素材或门店资料任务。
5. 服务商能用一句经营语言讲清楚。

只放服务商内部备注：

1. 单个平台一次性没推荐。
2. AI 明确说无法获取实时本地信息。
3. 需要大量技术解释才能成立。
4. 只能说明波动，不能转任务。
5. 证据路径不完整。

## 报告验收清单

提交 #2 前检查：

1. 报告里没有把单次 AI 回答包装成稳定排名。
2. 每条关键发现都有证据路径。
3. 每条关键发现都有对应经营任务。
4. 商家摘要不超过 300 字。
5. 报告可以在 10 分钟内讲完。
6. 报告里有“不能保证 AI 一定推荐”的谨慎表述。
7. 报告可以直接拿去做 Issue #4 的服务商反馈验证。

## 关闭标准

Issue #2 可以关闭的最低标准：

1. 新增 1 份真实门店报告，不再使用虚构门店。
2. `templates/report_scorecard.csv` 有该门店的评分记录。
3. `templates/report_finding_cards.csv` 有 3-5 条关键发现。
4. `templates/evidence_index.csv` 能追溯报告中的关键证据。
5. 报告可以交给至少 2 个服务商做 Issue #4 反馈验证。

## 下一步衔接

报告完成后立刻进入：

- [#4 Validate report usefulness with service providers](https://github.com/daniel-yu-gold/geo-research/issues/4)
- [35_issue_3_service_provider_interview_packet.md](./35_issue_3_service_provider_interview_packet.md)

如果报告生成过程发现证据不足：

- 回到 [#1 Run real-store AI visibility test](https://github.com/daniel-yu-gold/geo-research/issues/1) 补测。
- 或把反向证据写入 [00_decision_memo.md](./00_decision_memo.md) 和 [29_goal_completion_audit.md](./29_goal_completion_audit.md)。
