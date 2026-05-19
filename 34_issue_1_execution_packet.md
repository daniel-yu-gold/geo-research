# Issue #1 执行包：真实门店 AI 可见性测试

更新时间：2026-05-19

对应 GitHub issue：[ #1 Run real-store AI visibility test](https://github.com/daniel-yu-gold/geo-research/issues/1)

## 目标

用 1 家真实门店、3 个同城竞品、20 个 prompts、3 个 AI 入口，验证“门店级 AI 可见性”是否有足够明显的差异，能不能进一步生成服务商可销售的报告。

这一步不是证明产品一定成立，而是快速判断：

1. AI 回答里是否能观察到目标门店和竞品的差异。
2. 差异是否能解释成资料、内容、团购、达人 Brief 或评价素材任务。
3. 结果是否能让服务商觉得可以拿去和商家沟通。

## 开始前需要填的 10 个信息

先复制或填写 [templates/store_intake.csv](./templates/store_intake.csv)。

| 字段 | 必填原因 |
| --- | --- |
| 门店名 | 用于品牌词和对比 prompt |
| 城市 | 所有本地消费 prompt 必须带城市 |
| 商圈 | 提高 prompt 的真实度和推荐约束 |
| 详细地址 | 用于判断 AI 是否说错位置 |
| 品类 | 决定 prompt 模板 |
| 人均/价格带 | 影响场景推荐和竞品选择 |
| 目标场景 | 如约会、生日、聚餐、亲子、商务 |
| 抖音门店/团购链接 | 判断抖音经营动作如何转任务 |
| 公开资料链接 | 点评、地图、小红书、官网等 |
| 3 个竞品 | 用于对比和竞品压制判断 |

如果缺抖音链接，也可以先跑测试，但报告里的抖音优化任务会变弱。

## 当天执行顺序

### Step 1：确认门店和竞品

产物：

- 更新 [templates/stores.csv](./templates/stores.csv)
- 更新 [templates/competitors.csv](./templates/competitors.csv)
- 把来源写入 [templates/evidence_index.csv](./templates/evidence_index.csv)

最小标准：

- 目标门店 1 家。
- 同城同品类竞品 3 家。
- 竞品要尽量在同商圈、同价格带或同消费场景里。

### Step 2：生成 20 个 prompts

优先用 [tools/prompt-builder.html](./tools/prompt-builder.html)，也可以基于 [templates/prompt_bank.csv](./templates/prompt_bank.csv) 复制。

20 个 prompts 建议结构：

| 类型 | 数量 | 示例 |
| --- | ---: | --- |
| 非品牌品类推荐 | 5 | 上海静安寺适合约会的日料推荐 |
| 场景推荐 | 5 | 上海静安寺适合生日聚餐、有仪式感的日料 |
| 交易/团购推荐 | 4 | 上海静安寺有什么值得买的日料团购套餐 |
| 竞品对比 | 3 | A 店和 B 店哪个更适合情侣约会 |
| 品牌信息确认 | 3 | A 店有什么特色，适合什么人去 |

注意：

- 非品牌 prompt 不要直接写目标门店名。
- 品牌 prompt 和竞品对比 prompt 要单独标记，不能和非品牌推荐混算曝光率。
- 每个 AI 入口必须跑同一批 prompts。

### Step 3：跑 3 个 AI 入口

最低组合：

1. 豆包
2. DeepSeek
3. Kimi

增强组合：

4. 腾讯元宝
5. 百度 AI/文心或夸克

每次测试必须记录：

- 测试时间
- AI 入口
- 设备
- 账号状态
- 是否新对话
- 是否联网/搜索
- 定位权限
- 城市设定
- Prompt 原文
- 原始回答
- 截图路径

对应记录表：[templates/answer_runs.csv](./templates/answer_runs.csv)

### Step 4：人工打分

用 [tools/answer-scorer.html](./tools/answer-scorer.html) 或直接填 [templates/answer_runs.csv](./templates/answer_runs.csv)。

每条回答只判断 5 件事：

1. 目标门店是否出现。
2. 目标门店是否被强推荐。
3. 竞品是否出现。
4. 是否有明显信息错误。
5. 是否能转成经营优化任务。

不要过度解释模型为什么这样回答；第一轮先看有没有可卖的差异。

### Step 5：提炼 5 条发现

把 60 条回答压成 5 条以内发现。

建议格式：

| 发现 | 证据 | 可转任务 |
| --- | --- | --- |
| 生日场景里目标门店不出现，竞品 A/B 出现 | 豆包/Kimi 的 P03/P04 | 补生日套餐标题、短视频脚本、达人 Brief |
| AI 能识别目标门店环境安静，但不知道团购信息 | DeepSeek P12，Kimi P15 | 补团购卖点、点评/抖音资料统一 |

只有能转任务的发现，才适合进入服务商报告。

## 完成标准

Issue #1 可以关闭的最低标准：

1. [templates/stores.csv](./templates/stores.csv) 有 1 家真实目标门店。
2. [templates/competitors.csv](./templates/competitors.csv) 有 3 家真实竞品。
3. [templates/answer_runs.csv](./templates/answer_runs.csv) 至少有 60 条记录。
4. [templates/evidence_index.csv](./templates/evidence_index.csv) 能追溯关键截图、原始回答或来源。
5. 明确判断下面二选一：
   - 有足够差异，进入 Issue #2 生成真实报告。
   - 差异不明显，暂缓报告，把反向证据写入 Go/No-Go。

## 常见失败信号

出现这些情况时，不要硬做报告：

1. 大多数 AI 入口都无法给出门店级推荐，只给泛泛建议。
2. 目标门店和竞品差异无法解释成经营任务。
3. 结果完全依赖单个平台单次回答。
4. 服务商看不懂为什么这和抖音经营有关。
5. 需要大量技术解释才能让结论成立。

## 下一步衔接

如果 Issue #1 有正向信号，立刻进入：

- [#2 Generate first real-store AI visibility report](https://github.com/daniel-yu-gold/geo-research/issues/2)
- [13_real_store_report_template.md](./13_real_store_report_template.md)
- [tools/answer-scorer.html](./tools/answer-scorer.html)

如果 Issue #1 是反向信号，优先更新：

- [00_decision_memo.md](./00_decision_memo.md)
- [15_final_research_synthesis.md](./15_final_research_synthesis.md)
- [29_goal_completion_audit.md](./29_goal_completion_audit.md)
