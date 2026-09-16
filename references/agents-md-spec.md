# agents.md 规范要点摘要

来源：https://github.com/agentsmd/agents.md — "a simple, open format for guiding coding agents"

## 定位

AGENTS.md 是写给 AI coding agent 的"README"：一个专门的、可预测的位置，为 agent 提供项目上下文与指令。格式刻意保持极简——**没有必填 schema、没有强制字段**，就是一个 Markdown 文件。

## 核心规范

1. **文件名**：必须为 `AGENTS.md`，放在仓库根目录。
2. **格式**：纯 Markdown（与 README 相同的语法），agent 可以直接读取。
3. **层级**：支持嵌套——子目录可以有自己的 AGENTS.md，处理该目录下的文件时以更近的 AGENTS.md 为准（更具体的指令优先于根级）。因此根级文件只放全局适用内容。
4. **内容性质**：写"agent 不知道、但做了会出错"的内容——构建/测试命令、代码风格约定、项目特有陷阱、工作流规则。不写空泛愿景和自我介绍。
5. **章节**：无官方强制章节，但社区约定俗成的高频章节为：
   - `# Project Overview`（一两句项目说明）
   - `## Dev Environment Tips`
   - `## Build & Test Commands`
   - `## Code Style`
   - `## Testing Instructions`
   - `## PR Instructions`

   高频可选章节（项目确有对应固定流程时才写）：`## Build & Deployment`、`## Security Notes`、`## Debugging & Troubleshooting`。
6. **写法风格**（来自官方 minimal example）：
   - 祈使句、以 `- ` 列表项为主
   - 命令直接给完整可执行形式（含包管理器前缀）
   - 每条自带行动指令而非描述背景
   - 总体篇幅短（官方示例全文 < 30 行）

## 兼容性

AGENTS.md 已被多家主流 coding agent（Codex、Cursor、Copilot 等）原生识别，等价于各家的项目级指令文件。

## 对本 Skill 的约束映射

- 精简 → 每条一行祈使句，总行数 ≤ 120
- 合规 → 章节名沿用社区高频章节（标准 + 可选），仅放全局适用内容
- 不膨胀 → 嵌套机制说明：若某教训只适用于子目录，提示用户考虑在该子目录放局部 AGENTS.md，而不是撑大根文件；瘦身削减时，仍有长期参考价值的内容迁往 `docs/<主题>.md` 并在根文件一行按需引用，避免硬删丢知识
- 可验证 → 首版写入的命令须实跑确认，或与构建/CI 配置逐一核对（见 SKILL.md Step 3）
