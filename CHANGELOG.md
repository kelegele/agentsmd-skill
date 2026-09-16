# Changelog

版本号：vMAJOR.MINOR.PATCH。MINOR 功能新增、PATCH 修订、MAJOR 架构级变更。

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
