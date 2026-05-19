# 国外 GEO / AI Visibility 工具扫描

更新时间：2026-05-19

## 一句话结论

国外工具已经形成相对清晰的产品范式：围绕一组高意图 prompts，定期请求多个 AI/answer engines，抽取品牌提及、位置、情绪、引用来源、竞品份额，再给出内容和技术优化建议。可借鉴度高，但直接照搬到中国本地生活场景会有两个断点：国内 AI 入口和抖音生活服务交易链路没有天然打通，实体门店的“可见性”也不仅由官网内容决定。

## 代表产品

| 产品 | 核心定位 | 关键功能 | 对本项目的参考价值 |
| --- | --- | --- | --- |
| Profound | Answer engine insights / AI search visibility | AI 回答中的 visibility、sentiment、citations；prompt/topic 分析；可把数据接入 agent 工作流 | 指标体系和报告流最值得借鉴，尤其是品牌可见性、引用来源和 prompt 级分析 |
| Peec AI | AI search analytics for marketing teams | Visibility、position、sentiment；prompt setup；source visibility vs brand visibility；报告 | 产品表达很清楚，适合参考为“服务商给客户看的简洁报告” |
| Otterly.AI | 入门级 AI search monitoring | 自动跑 ChatGPT、Google AI Overviews、Perplexity、Gemini、Copilot 等；品牌提及和网站引用监控 | 低成本 MVP 的形态参考，重点是固定 prompt 的周期监测 |
| AthenaHQ | GEO command center | 跨平台 AI visibility、content gaps、citation source analysis、agency pitch workspace、multi-location 行业 | 对“面向代理商/服务商”的 workspace 很有参考价值 |
| Scrunch | AI customer experience / AI search visibility | 监测、citation analysis、AI bot crawl feed、面向 AI agent 的轻量结构化内容层 | 对“把内容做成机器可读资料包”有启发，但中国门店未必有官网可改 |

## 产品共同结构

1. Prompt universe
   - 不是传统关键词，而是用户会问 AI 的问题。
   - 常见维度：品牌词、品类词、竞品比较、场景需求、地理位置、购买决策、价格、评价、替代方案。

2. Scheduled answer collection
   - 固定时间向多个 AI 引擎提问。
   - 保存原始回答、引用链接、时间、地区/语言、模型或搜索入口。

3. Metric layer
   - Brand visibility：回答中是否提到品牌。
   - Source visibility：品牌页面或第三方页面是否被引用。
   - Position/rank：品牌在答案中出现顺序。
   - Share of voice：和竞品相比的出现份额。
   - Sentiment/perception：回答对品牌的描述是否正向、准确、有无幻觉。
   - Citation/source map：AI 更信任哪些来源。

4. Diagnosis layer
   - 哪些 prompt 没出现。
   - 哪些来源被竞品占据。
   - 哪些实体信息缺失或不一致。
   - 哪些内容结构不利于被 AI 抽取。
   - 哪些 AI crawler 或搜索入口无法访问关键页面。

5. Action layer
   - 生成 FAQ、对比页、品类页、结构化资料、PR/外部引用建议。
   - 给出优先级任务。
   - 为代理商输出客户报告。

## 技术可复制性

### 容易复制的部分

- 固定 prompt 批量请求多模型/多搜索入口。
- 解析回答中的品牌、竞品、门店名、引用来源、情绪。
- 计算 visibility、position、share of voice、source citation。
- 用 LLM 生成诊断摘要、优化建议、客户报告。
- 按行业模板生成 FAQ、门店资料、达人 Brief、短视频脚本。

### 不容易复制的部分

- 国内 AI 应用入口的稳定自动化：豆包、DeepSeek、Kimi、腾讯元宝、文心/百度 AI、夸克等入口的权限、反爬、地区化和个性化差异。
- Prompt 真实需求：国外 SaaS 场景可以从 SEO keywords 和官网生成，实体门店需要从本地消费场景、团购、地图、评价、短视频内容中抽取。
- 可归因：AI 回答曝光不等于抖音团购成交，服务商需要能把报告和抖音内容、直播、达人、核销 GMV 连接起来。
- 可执行优化：国外常优化官网/博客/PR；中国小店往往没有官网，主要资产在抖音门店页、短视频、直播间、达人内容、美团/点评/地图、小红书和评价。

## 对中国抖音服务商场景的启发

1. 不要从“AI 搜索排名”切入，应该从“门店被 AI 和内容平台正确推荐”切入。
2. 指标不要只做曝光，要包含“是否推荐、推荐理由、是否引用/提及抖音内容、和竞品差距、错误信息”。
3. 产品要服务代理商批量交付，而不是单店老板自助分析。
4. 关键交付物应是月报和任务单：本月赢了哪些问题、输了哪些问题、下月该补哪些内容。
5. 国外工具的 citation/source map 在中国要改成“AI/搜索/内容平台信号源地图”：抖音门店页、达人视频、团购商品、地图 POI、大众点评/美团、小红书笔记、公众号/媒体稿、品牌官网等。

## 参考来源

- Profound Answer Engine Insights overview: https://help.tryprofound.com/articles/3443229936-answer-engine-insights-overview
- Profound Answer Engine Insights node: https://help.tryprofound.com/articles/8515393916-answer-engine-insights
- Peec AI homepage: https://peec.ai/
- Peec AI metrics documentation: https://docs.peec.ai/metrics/understanding-your-metrics
- Otterly.AI homepage and feature pages: https://otterly.ai/ , https://otterly.ai/features/
- AthenaHQ homepage: https://athenahq.ai/
- Scrunch homepage: https://scrunch.com/
- GEO foundational paper: https://arxiv.org/abs/2311.09735
- AgenticGEO 2026 paper: https://arxiv.org/abs/2603.20213
- AI search visibility measurement paper: https://arxiv.org/abs/2604.07585
