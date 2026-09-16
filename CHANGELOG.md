# Changelog

版本号：vMAJOR.MINOR.PATCH。MINOR 功能新增、PATCH 修订、MAJOR 架构级变更。

## v1.3.0 - 2026-09-16

### Added

- 瘦身迁移机制：削减 AGENTS.md 时，仍有长期参考价值但不满足根文件准入门槛的内容（背景说明、操作细节、低频特例）迁往 `docs/<主题>.md`，在原位置留一行按需引用；过时、重复内容仍直接删，不迁移
- Step 4 新增引用行约束：宁缺毋滥，每章至多 1–2 条，防 docs/ 变相撑大根文件
- Step 5 改动方案新增迁移清单项（目标文件与引用行；docs/ 写入同样先经用户批准）

## v1.2.0 - 2026-09-16

### Added

- 成稿示例 `assets/AGENTS-example.md`（agents.md 官方 pnpm/Turborepo monorepo 实例），供把握合格成稿的颗粒度与密度
- 模板与章节约定扩展可选章节：`Build & Deployment`、`Security Notes`、`Debugging & Troubleshooting`，仅当项目确有对应固定流程时追加
- Step 3 命令可执行验证：首版写入的每条命令须实跑确认，或与 package.json scripts / Makefile / CI 配置逐一核对，跑不通不写入
- 章节约定新增嵌套指引：仅适用特定子目录的教训不进根文件，下沉为该子目录的局部 AGENTS.md
- 模板顶部补充裁剪与语言约定说明（章节名保留英文，条目语言随项目主流语言）

### Changed

- 自建章节门槛修正为"标准与可选章节均无法覆盖时才自建，全文章节总数 ≤ 9"（原"≤ 6"与 6 个标准章节自相矛盾）

## v1.1.0 - 2026-09-16

### Added

- 文档归集步骤（Step 7，收尾可选）：扫描散落的产出文档，给出 `docs/<主题>/` 归类方案；经用户批准才移动文件，并自动修复引用断链
- agent 记忆与进度同步（Step 6，条件执行）：agent 有记忆机制则沉淀为项目记忆条目；项目有 TODO/CHANGELOG/PROGRESS/STATUS 等进度/状态文件则一并更新
- 铁律 4「先确认后落盘」：所有文件改动（AGENTS.md 写入、记忆、进度文件、文档移动）先出方案、经用户批准后执行

### Changed

- 安装方式不再局限 WorkBuddy：npx skills 一键安装（推荐）、Claude Code、手动复制（各 agent 技能目录对照表）、WorkBuddy URL 导入
- SKILL.md frontmatter 新增 `version` 字段

## v1.0.0 - 2026-09-04

- 初版：经验教训蒸馏固化为 AGENTS.md（5 步工作流：收集 → 蒸馏 → 读取现状 → 有机合并 → 写入），120 行硬上限与合并决策表，遵循 agents.md 开源规范
