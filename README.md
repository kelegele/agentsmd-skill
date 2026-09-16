# agentsmd

将项目经验教训精炼固化为 [AGENTS.md](https://agents.md/) 的 Agent Skill（Agent Skills 开放格式，兼容 Claude Code、Codex、Cursor、Gemini CLI、OpenCode、WorkBuddy 等所有支持 skills 的 agent）。

## 特性

- **精简**：每条规则一行祈使句，设准入门槛（可复用 + 有实际损失 + 一行说得清）
- **合规**：遵循 agents.md 开源规范，采用社区高频章节，仅放全局适用内容
- **不膨胀**：硬上限 120 行；合并决策表（等价丢弃 / 重叠合并 / 特例泛化 / 矛盾取新 / 过时删除），禁止追加式增长
- **自适应初始化**：项目无 AGENTS.md 时，扫描项目结构与构建配置后按实际生成，不堆通用常识；每条命令实跑或对照构建/CI 配置核验，跑不通不写入
- **成稿基准**：附 agents.md 官方真实成稿示例把握颗粒度；模板含可选章节（Build & Deployment / Security Notes / Debugging & Troubleshooting），按项目实际追加，子目录专属教训下沉为局部 AGENTS.md
- **文档归集**：收尾时发现散落的产出文档，给出 `docs/` 归类方案；经用户批准才移动文件，并自动修复引用断链
- **记忆与进度同步**：agent 有记忆机制则同步沉淀为项目记忆；项目有进度/状态文件（TODO/CHANGELOG 等）则一并更新
- **先确认后落盘**：所有文件改动（含 AGENTS.md 本身）先出方案、经用户批准后才执行

## 结构

```
agentsmd/
├── SKILL.md                     # 核心工作流（7 步）
├── references/
│   └── agents-md-spec.md        # agents.md 规范要点摘要
└── assets/
    ├── AGENTS-template.md       # 章节参考骨架（标准 + 可选章节）
    └── AGENTS-example.md        # agents.md 官方真实成稿示例
```

## 使用

在任意已安装本技能的 agent（Claude Code、Codex、Cursor、WorkBuddy 等）中说：

> 用 agentsmd 把这次的教训固化进 AGENTS.md

顺带整理散落文档时说：

> 用 agentsmd 把这次的教训固化进 AGENTS.md，并把项目里散落的文档归集到 docs/

## 安装

### 方式一：npx skills 一键安装（推荐，通用）

```bash
npx skills add kelegele/agentsmd-skill
```

在交互中选择目标 agent（Claude Code / Codex / Cursor / Gemini CLI 等），可选全局或项目级安装。

### 方式二：Claude Code

```bash
# 全局（所有项目可用）
git clone https://github.com/kelegele/agentsmd-skill.git ~/.claude/skills/agentsmd

# 或仅当前项目
git clone https://github.com/kelegele/agentsmd-skill.git .claude/skills/agentsmd
```

### 方式三：手动复制（任意 agent）

把仓库目录复制到目标 agent 的技能目录即可，技能目录名须为 `agentsmd`：

| Agent | 全局技能目录 |
|---|---|
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` |
| 跨 agent 通用 | `~/.agents/skills/` |
| WorkBuddy | `~/.workbuddy/skills/` |

```bash
git clone https://github.com/kelegele/agentsmd-skill.git
cp -r agentsmd-skill ~/.agents/skills/agentsmd   # 换成目标 agent 的目录
```

### 方式四：WorkBuddy URL 导入

1. 打开 WorkBuddy 左侧栏 **技能** → **添加技能**；
2. 选择 **通过 URL 导入**，粘贴本仓库地址：`https://github.com/kelegele/agentsmd-skill`；
3. 确认导入后，在【技能管理】中确认已启用。

> 注：部分 agent 需重启或新开对话才能加载新技能。安装后在对话中说"**用 agentsmd 把这次的教训固化进 AGENTS.md**"即可触发。
