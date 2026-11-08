# 项目交接

## 当前目标与用户决定

- 2026-11-08：用户决定为本项目开启多 Agent 交接模式（`.agent-handoff.json` enabled=true）。
- 任务：为 Flitnut（飞栗 AI）公众号写长文投稿推荐 agentsmd skill；读者定位 AI 编程工具用户；交付 Markdown 稿 + 公众号排版 HTML。
- 2026-11-09：用户指出稿件此前未投到任何位置；已按 project-handoff-skill 的投稿目录惯例归档至 `docs/articles/`。
- 2026-11-09：用户决定写作类事项（标题终选、排版风格、配图、发布跟进等）不在本项目处理；稿件产物原地保留不再跟进，后续写作在他处进行。

## 当前任务、状态和记录入口

- 公众号长文投稿稿：`docs/articles/2026-11-09-flitnut-wechat-article.md`（含投稿头注释、3 个备选标题、摘要、正文约 3300 字、配图建议；目录惯例对齐 project-handoff-skill 同系列投稿）
- 公众号 HTML（notion 风，已过静态检查，可直接全选复制粘贴公众号后台）：`docs/articles/2026-11-09-flitnut-wechat-article-notion.html`
- 已提交内容仓 inbox（2026-11-09 01:06，commit 5d85160）：`kelegele/flitnut.ai` → `Topics/inbox/20261109-0106-agentsmd-wechat-article.md`（全文自包含，待 harvest-topics 加工/发布流程跟进）
- 规则固化（2026-11-09，用户批准）：AGENTS.md Gotchas 新增「对外交付类指令落点不明先查 env/惯例/问用户，不得默默降级」；memory `delivery-instruction-clarify-target` 已在库并索引
- 交接模式搭建：`scripts/agent_hook.py`（冒烟测试通过）、`.zcode/config.json`（--agent ZCode，python3=/usr/local/bin/python3）、`AGENTS.md` 已并入「多 Agent 交接」规则
- README 特性升格（2026-11-09，用户批准）：记忆同步卖点（表格末行 + 七事⑥ + FAQ personal agent 条目）；CHANGELOG 加 Unreleased 条目；README 仓库结构加注
- 真正的投稿动作：粘贴公众号后台仍需用户执行（agent 无法操作后台）

## 未完成事项与下一步

- [x] 交接基础设施已纳入 git（2026-11-09 用户批准后提交；`.v2c/`、`.video_agent/`、`out/`、`*.lock` 已 gitignore，README 仓库结构已加注）
- Codex / QwenWork 钩子配置未安装（本会话仅确认使用 ZCode），需要时按模板补
- 自动记录需新会话真实验证：本会话（2026-11-09 启动检查已完成，历史 2 条）结束时检查 `docs/execution/agent-runs/` 是否新增记录
- 文章发布后：在本文件登记发布日期与标题终选
