# 当前执行状态

更新时间：2026-05-19

## 总体状态

当前项目已经完成：

1. 桌面研究：国外工具、国内公开信号、市场、竞争、技术可行性。
2. 产品假设：服务商产品闭环、MVP、报告样例、低保真原型。
3. 验证基础设施：Prompt Builder、Answer Scorer、CSV 模板、证据索引规则。
4. GitHub 协作：P0 issue、review 指南、每个 P0 issue 的执行包。

当前项目尚未完成：

1. 真实服务商访谈。
2. 真实门店 AI 测试。
3. 真实门店报告。
4. 服务商看真实报告后的反馈。
5. 基于真实证据更新后的最终 Go/No-Go。

因此 thread goal 继续保持 active，不能标记完成。

## P0 issue 状态

| Issue | 当前状态 | 卡点 | 下一步 |
| --- | --- | --- | --- |
| [#1 真实门店 AI 可见性测试](https://github.com/daniel-yu-gold/geo-research/issues/1) | 执行包已完成 | 缺 1 家真实门店和 3 个竞品 | 填 [templates/store_intake.csv](./templates/store_intake.csv)，跑 20 prompts x 3 AI 入口 |
| [#2 生成第一份真实门店报告](https://github.com/daniel-yu-gold/geo-research/issues/2) | 报告生成规则已完成 | 依赖 #1 的真实 answer_runs | 用 [36_issue_2_report_generation_packet.md](./36_issue_2_report_generation_packet.md) 生成真实报告 |
| [#3 访谈 5-10 个服务商](https://github.com/daniel-yu-gold/geo-research/issues/3) | 访谈执行包已完成 | 缺真实访谈发生 | 从 [30_first_outreach_batch.md](./30_first_outreach_batch.md) 和 [31_contact_channel_discovery.md](./31_contact_channel_discovery.md) 开始约访 |
| [#4 验证报告对服务商是否有用](https://github.com/daniel-yu-gold/geo-research/issues/4) | 反馈验证规则已完成 | 依赖 #2 的真实报告和 #3 的服务商对象 | 拿真实报告给至少 2 个服务商看，填 [templates/report_feedback.csv](./templates/report_feedback.csv) |
| [#5 更新最终 Go/No-Go](https://github.com/daniel-yu-gold/geo-research/issues/5) | 决策规则已完成 | 依赖 #1-#4 的真实证据 | 填 [templates/go_no_go_evidence_scorecard.csv](./templates/go_no_go_evidence_scorecard.csv)，更新 00/15/29 |

## 建议执行顺序

最短路径：

1. 先执行 #3：约 5 个服务商，因为访谈可能直接拿到真实门店。
2. 访谈中争取 1 家真实门店和 3 个竞品。
3. 执行 #1：跑真实 AI 测试。
4. 执行 #2：生成第一份真实报告。
5. 执行 #4：拿真实报告给至少 2 个服务商看。
6. 执行 #5：更新最终进入判断。

如果没有服务商资源，也可以先用自选真实门店执行 #1，但 #4 仍然需要服务商反馈，才能判断是否值得投入。

## 当前最重要的缺口

不是继续扩写研究，而是拿到下面任一组真实输入：

### 选项 A：先拿服务商

- 5 个服务商联系人。
- 至少 2 个愿意看样例报告。
- 至少 1 个愿意提供真实门店。

### 选项 B：先拿门店

- 1 家真实餐饮门店。
- 3 家同商圈/同品类竞品。
- 可公开查询的抖音、点评、地图、小红书或官网资料。

## 何时能进入最终判断

只有下面证据出现后，才能关闭 #5 并判断 goal 是否完成：

1. [templates/interview_tracker.csv](./templates/interview_tracker.csv) 至少 5 条真实服务商访谈。
2. [templates/answer_runs.csv](./templates/answer_runs.csv) 至少 60 条真实 AI 回答记录。
3. [templates/report_scorecard.csv](./templates/report_scorecard.csv) 至少 1 条真实门店评分。
4. [templates/report_feedback.csv](./templates/report_feedback.csv) 至少 2 条服务商看真实报告后的反馈。
5. [templates/evidence_index.csv](./templates/evidence_index.csv) 能追溯关键原话、截图、原始回答和报告版本。
6. [00_decision_memo.md](./00_decision_memo.md)、[15_final_research_synthesis.md](./15_final_research_synthesis.md)、[29_goal_completion_audit.md](./29_goal_completion_audit.md) 已根据真实证据更新。

## 当前 Git 同步备注

GitHub 远端已经可以看到最新新增文件。由于本机 Git 通道间歇性无法连接 `github.com:443`，部分远端更新是通过 GitHub 连接器写入的。本地仓库可能暂时显示 ahead；这不影响 GitHub 网页 review，但后续网络恢复后需要再做一次常规同步。
