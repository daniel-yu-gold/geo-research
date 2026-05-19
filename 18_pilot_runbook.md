# 3 天真实试点 Runbook

更新时间：2026-05-19

## 目标

用 3 天完成第一轮真实验证：

1. 跑通 1 家真实门店的 AI 可见性测试。
2. 生成 1 份真实门店体检报告。
3. 拿给 2 个抖音生活服务商看。
4. 判断是否值得进入半自动 MVP。

这份 Runbook 是执行顺序，不是研究综述。照着做即可。

## 试点前准备

需要准备：

- 1 家真实门店。
- 3 个同城同品类竞品。
- 3 个 AI 入口，建议先用豆包、DeepSeek、Kimi。
- 本地工具：
  - [tools/prompt-builder.html](./tools/prompt-builder.html)
  - [tools/answer-scorer.html](./tools/answer-scorer.html)
- 模板：
  - [templates/stores.csv](./templates/stores.csv)
  - [templates/competitors.csv](./templates/competitors.csv)
  - [13_real_store_report_template.md](./13_real_store_report_template.md)
  - [templates/interview_tracker.csv](./templates/interview_tracker.csv)

## Day 1：选门店和生成问题

### 1. 选择门店，30 分钟

优先选择餐饮门店，满足：

- 有抖音门店页或团购。
- 有 3 个明显同城竞品。
- 有可讨论的场景，例如约会、生日、朋友聚餐、游客打卡。
- 门店信息公开，便于核对地址、人均、营业时间。

记录到：[templates/stores.csv](./templates/stores.csv)

### 2. 选择竞品，30 分钟

竞品标准：

- 同城/同商圈。
- 同品类或替代消费场景。
- 在抖音、点评、地图、小红书里有一定公开内容。

记录到：[templates/competitors.csv](./templates/competitors.csv)

### 3. 生成 prompts，30 分钟

打开：[tools/prompt-builder.html](./tools/prompt-builder.html)

输入：

- 门店名
- 城市
- 商圈
- 行业
- 品类
- 价格带
- 竞品
- 补充场景

导出：

- 复制问题列表用于 AI 测试。
- 下载 CSV，留档为该门店的 prompt 表。

建议第一轮使用 15-25 个 prompts，不必追求数量多。

### 4. 标记高优先级问题，20 分钟

高优先级：

- 本地消费决策问题。
- 有明确场景、价格、商圈或交易意图。
- 能转化成短视频、团购、达人 Brief、FAQ 任务。

低优先级先不跑，避免第一轮太重。

## Day 2：测试 AI 回答和评分

### 1. 创建测试环境，10 分钟

规则：

- 每个 AI 入口使用新对话。
- 不要先告诉 AI 目标门店，除非是品牌词或对比问题。
- 同一批 prompts 在每个入口按相同顺序测试。

推荐入口：

- 豆包
- DeepSeek
- Kimi

### 2. 手动测试，60-120 分钟

每个问题记录：

- AI 入口。
- 原始回答。
- 是否提到目标门店。
- 是否强推荐。
- 目标门店位置。
- 出现哪些竞品。
- 是否有信息错误。
- 是否能转成任务。

打开：[tools/answer-scorer.html](./tools/answer-scorer.html)

将每条回答录入并标注。

### 3. 导出评分，10 分钟

从 Answer Scorer 导出：

- `answer_runs.csv`
- `report_scorecard.csv`
- `evidence_index.csv`

保存到该门店测试文件夹或复制回模板。

### 4. 判断是否有足够信号，20 分钟

强信号：

- 30% 以上问题出现竞品差异、信息错误或内容缺口。
- 至少 5 条问题能转化为明确任务。
- 同一类场景反复出现问题，例如“生日弱”“约会弱”“团购不被识别”。

弱信号：

- 回答都很泛，无法解释。
- 只有单次偶然差异。
- 几乎不能转成抖音经营任务。

如果弱信号明显，可以停止，不必写完整报告。

## Day 3：生成报告和访谈

### 1. 生成真实门店报告，60-90 分钟

复制：[13_real_store_report_template.md](./13_real_store_report_template.md)

如果已经用 [tools/answer-scorer.html](./tools/answer-scorer.html) 完成评分，可以先复制其中的“商家报告草稿”，再按真实门店报告模板补充门店资料、截图证据和服务商内部备注。
同时下载或复制“证据索引”，把 AI 回答截图、原始回答和报告版本登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)。

填入：

- 基础信息。
- 总览评分。
- 3-5 条关键发现。
- Prompt 结果表。
- 竞品场景地图。
- 信号源地图。
- 下月任务单。
- 商家月报摘要。

参考虚构样例：[06_product_sample_store_ai_visibility_report.md](./06_product_sample_store_ai_visibility_report.md)

### 2. 准备服务商演示，20 分钟

演示材料：

- 真实门店报告。
- [prototype/store-ai-visibility.html](./prototype/store-ai-visibility.html)
- 3 条最强发现。
- 3 条下月任务。

如果还没有约到服务商，按 [30_first_outreach_batch.md](./30_first_outreach_batch.md) 先推进第一批外联，并用 [templates/outreach_batch.csv](./templates/outreach_batch.csv) 记录状态。

演示顺序：

1. 这个问题用户可能会问。
2. AI 推荐了谁。
3. 竞品为什么占位。
4. 下月要改什么内容/团购/达人。
5. 这能不能放进你的签约、月报或续费。

### 3. 访谈 2 个服务商，每个 20-30 分钟

使用：

- [08_service_provider_outreach_and_sales_test.md](./08_service_provider_outreach_and_sales_test.md)
- [11_prototype_test_guide.md](./11_prototype_test_guide.md)

必须问：

1. 你会把这个放在签约前诊断、月报，还是续费沟通里？
2. 商家能不能听懂？
3. 哪部分最有价值：报告、任务单、短视频脚本、达人 Brief、销售话术？
4. 你愿不愿意提供真实门店继续跑？
5. 如果每月给 20 家门店做，多少钱你能接受？

记录到：[templates/interview_tracker.csv](./templates/interview_tracker.csv)

## 试点结束后的判断

### 继续

满足以下 3 条，可以继续跑 3-5 家门店：

- 真实 AI 回答有可解释差异。
- 服务商能理解并愿意试讲。
- 单店报告生成时间低于 90 分钟。

### 暂停

出现以下任一情况，应暂停：

- AI 回答没有门店级差异。
- 服务商认为商家不会买。
- 报告无法转成短视频、团购、达人或 FAQ 任务。

### 转向

如果服务商喜欢任务单但不关心 AI 可见性，可以转向：

- 抖音本地生活内容诊断工具。
- 达人 Brief 生成工具。
- 团购标题和场景卖点优化工具。
- 服务商月报自动生成工具。

## 试点输出清单

完成后应有：

- 1 份真实门店资料。
- 1 份竞品资料。
- 1 份 prompt 表。
- 1 份 answer_runs.csv。
- 1 份 report_scorecard.csv。
- 1 份 evidence_index.csv。
- 1 份真实门店体检报告。
- 2 条服务商访谈记录。
- 1 个继续/暂停/转向判断。

## 更新哪些文件

试点完成后更新：

- [15_final_research_synthesis.md](./15_final_research_synthesis.md)
- [12_mvp_prd.md](./12_mvp_prd.md)
- [10_completion_audit_checklist.md](./10_completion_audit_checklist.md)
- [templates/interview_tracker.csv](./templates/interview_tracker.csv)
- [templates/lead_tracker.csv](./templates/lead_tracker.csv)

不要只把结果留在聊天里。
