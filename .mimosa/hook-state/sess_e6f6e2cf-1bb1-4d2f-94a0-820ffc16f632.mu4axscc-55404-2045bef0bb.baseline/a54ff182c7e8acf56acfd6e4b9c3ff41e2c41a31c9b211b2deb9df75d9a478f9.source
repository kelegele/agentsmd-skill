# agentsmd-skill

agentsmd Agent Skill 的源仓库：纯 Markdown 技能包（SKILL.md + references/ + assets/），无构建、无测试；文档与 Release Notes 用简体中文，提交主题用英文 conventional commits，产出遵循 agents.md 开源规范。

## PR / Workflow Instructions

- 发版：SKILL.md frontmatter `version` 与 CHANGELOG 同步升版 → commit → push → `gh release create vX.Y.Z` 远程自动建 tag，勿 git tag + git push tag；Release Notes 取自 CHANGELOG 对应条目
- git push 偶发 `Connection was reset` 属瞬时故障，直接重试即可，勿判为网络不通

## Project-Specific Gotchas

- 改 SKILL.md 工作流/章节时，必须同步 README（特性列表、目录树）与 CHANGELOG，保持版本与内容三处一致
- 新增或修改数值门槛（行数、章节上限等）时，先核对与模板既有结构不自相矛盾（曾出现"章节 ≤6"与 6 个标准章节冲突）
- SKILL.md frontmatter 的 `description` 是触发判据，改动触发场景时须同步更新措辞
