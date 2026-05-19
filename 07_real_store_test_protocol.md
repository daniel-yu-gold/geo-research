# 真实门店 AI 可见性测试协议

更新时间：2026-05-19

## 目的

用真实门店验证“AI 回答中是否存在可被产品化的门店/竞品差异”。这一步不追求统计严谨，而是判断是否有足够强的商业信号，值得继续做半自动 MVP。

## 测试对象

建议第一轮只选一个行业，优先餐饮，因为场景清晰、消费决策高频、抖音团购和达人探店都成熟。

最低样本：

- 3 家目标门店。
- 每家门店 3-5 个同城竞品。
- 每家门店 20 个 prompts。
- 3-5 个 AI 入口。

推荐 AI 入口：

- 豆包
- DeepSeek
- Kimi
- 腾讯元宝
- 百度 AI/文心
- 夸克

各入口的测试优先级、环境字段、联网/定位/账号记录和复测规则见 [26_ai_entrance_test_matrix.md](./26_ai_entrance_test_matrix.md)。

## 测试前准备

### 门店资料

每家门店记录：

- 门店名
- 城市/商圈/地址
- 品类
- 人均/价格带
- 适合场景
- 抖音门店页/团购链接/账号
- 点评/地图/小红书/官网链接
- 核心卖点
- 3-5 个竞品

对应模板：[templates/stores.csv](./templates/stores.csv)、[templates/competitors.csv](./templates/competitors.csv)

### Prompt 设计

每家门店至少覆盖 5 类 intent：

1. 品类推荐：城市 + 商圈 + 品类。
2. 场景推荐：约会、生日、亲子、聚餐、游客、商务、性价比。
3. 交易推荐：抖音团购、套餐、预约、人均、优惠。
4. 对比决策：A 和 B 哪个更适合某场景。
5. 信息确认：营业时间、停车、是否适合儿童、是否有包间。

对应工具和模板：[tools/prompt-builder.html](./tools/prompt-builder.html)、[templates/prompt_bank.csv](./templates/prompt_bank.csv)

## 测试方法

1. 使用无明显个人偏好的新对话。
2. 每个 AI 入口同一轮使用同一批 prompts。
3. 不要在 prompt 中直接诱导目标门店，除非测试品牌词或对比 prompt。
4. 保存完整原始回答，不只保存摘要。
5. 记录测试时间、平台、是否联网、是否给出引用来源。
6. 如果平台回答明显拒答或泛化，也要记录。

对应工具和模板：[tools/answer-scorer.html](./tools/answer-scorer.html)、[templates/answer_runs.csv](./templates/answer_runs.csv)

## 评分规则

### Prompt 级评分

| 维度 | 0 分 | 1 分 | 2 分 |
| --- | --- | --- | --- |
| 目标门店出现 | 未出现 | 出现但非推荐 | 明确推荐 |
| 位置 | 未出现 | 第 4 位及以后 | 前 3 位 |
| 推荐理由 | 无 | 泛化 | 与门店真实卖点匹配 |
| 信息准确 | 明显错误 | 部分准确 | 准确 |
| 可转任务 | 无动作 | 模糊建议 | 可生成明确内容/资料任务 |

### 门店级指标

- AI 推荐覆盖率 = 目标门店出现的 prompt 数 / 总 prompt 数。
- 强推荐率 = 目标门店进入前三或被明确推荐的 prompt 数 / 总 prompt 数。
- 竞品压制率 = 竞品出现但目标门店未出现的 prompt 数 / 总 prompt 数。
- 信息错误率 = 有明显错误的 prompt 数 / 目标门店出现 prompt 数。
- 可转任务率 = 能转成明确优化任务的 prompt 数 / 总 prompt 数。

对应工具和模板：[tools/answer-scorer.html](./tools/answer-scorer.html)、[templates/report_scorecard.csv](./templates/report_scorecard.csv)

## 结果判定

### 强信号

- 30% 以上 prompts 出现明显竞品差异、信息错误或内容缺口。
- AI 回答对门店的推荐理由能映射到抖音内容/团购/达人 Brief 任务。
- 不同 AI 入口虽然答案不同，但问题类型稳定，例如“生日场景弱”“团购信息缺失”。
- 服务商看到结果后能立刻想到商家沟通话术。

### 弱信号

- 大多数回答泛泛推荐品牌或商圈，没有门店级差异。
- 结果无法解释，不能形成明确任务。
- AI 入口之间波动过大，月报难以讲清楚。
- 服务商认为这和抖音成交无关。

## 测试输出

每家门店输出 4 个东西：

1. Prompt 结果表。
2. 3-5 条关键发现。
3. 下月优化任务单。
4. 给商家的月报摘要。
5. 证据索引：把截图、原始回答和报告版本登记到 [templates/evidence_index.csv](./templates/evidence_index.csv)，规则见 [28_validation_evidence_binder.md](./28_validation_evidence_binder.md)。

## 质量控制

- 同一 prompt 至少在 3 个 AI 入口测试。
- 关键 prompt 隔 24 小时复测一次，观察稳定性。
- 不要把单次排名当作确定事实，只把它当成“可见性信号”。
- 对外报告避免承诺“保证 AI 推荐”。
- 所有截图和原始回答留档，便于服务商或商家追问。
