# Evidence 留档说明

这个文件夹用于保存真实验证产生的原始证据，不用于存放桌面研究材料。

建议目录：

- `ai_runs/`：AI 入口测试截图、原始回答导出、复测截图。
- `interviews/`：服务商访谈纪要、录音转写、授权可用的原话摘录。
- `reports/`：真实门店报告版本、商家版 PDF/截图、服务商反馈版本。
- `source_pages/`：关键公开网页截图或导出，避免后续页面变化无法追溯。

所有证据都应登记到 [../templates/evidence_index.csv](../templates/evidence_index.csv)。

命名建议：

- AI 回答截图：`ai_runs/R001.png`，对应 [../templates/answer_runs.csv](../templates/answer_runs.csv) 的 `run_id`。
- 访谈纪要：`interviews/I001-notes.md`，对应 [../templates/interview_tracker.csv](../templates/interview_tracker.csv) 的 `interview_id`。
- 真实报告：`reports/S001-report-v1.md`，对应 [../templates/stores.csv](../templates/stores.csv) 的 `store_id`。

不要把未经允许的个人手机号、微信号、录音原文件或敏感商家数据直接放进对外可分享版本。需要保留时，在 `evidence_index.csv` 里标记访问权限和脱敏状态。
