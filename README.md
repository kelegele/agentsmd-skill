# agentsmd

将项目经验教训精炼固化为 [AGENTS.md](https://agents.md/) 的 WorkBuddy Skill。

## 特性

- **精简**：每条规则一行祈使句，设准入门槛（可复用 + 有实际损失 + 一行说得清）
- **合规**：遵循 agents.md 开源规范，采用社区高频章节，仅放全局适用内容
- **不膨胀**：硬上限 120 行；合并决策表（等价丢弃 / 重叠合并 / 特例泛化 / 矛盾取新 / 过时删除），禁止追加式增长
- **自适应初始化**：项目无 AGENTS.md 时，扫描项目结构与构建配置后按实际生成，不堆通用常识

## 结构

```
agentsmd/
├── SKILL.md                     # 核心工作流（5 步）
├── references/
│   └── agents-md-spec.md        # agents.md 规范要点摘要
└── assets/
    └── AGENTS-template.md       # 章节参考骨架
```

## 使用

在 WorkBuddy 中说：

> 用 agentsmd 把这次的教训固化进 AGENTS.md

## 安装

### 方式一：URL 导入（推荐）

1. 打开 WorkBuddy 左侧栏 **技能** → **添加技能**；
2. 选择 **通过 URL 导入**，粘贴本仓库地址：

   ```
   https://github.com/kelegele/agentsmd-skill
   ```

3. 确认导入后，在【技能管理】中确认已启用，新开对话即生效。

### 方式二：npx skills 一键安装

```bash
npx skills add kelegele/agentsmd-skill
```

在交互中选择目标 agent（安装到全局 `~/.agents/skills/` 或项目级目录）。

### 方式三：本地导入

```bash
git clone https://github.com/kelegele/agentsmd-skill.git
```

然后在 WorkBuddy 中选择 **从本地路径导入**，指定克隆目录；或直接复制到技能目录：

```bash
cp -r agentsmd-skill ~/.workbuddy/skills/
```

> 注：若 `npx skills` 未列出 WorkBuddy，可用方式一/三安装，或把技能目录复制到 `~/.workbuddy/skills/`。

安装后无需重启，对话中直接说"**用 agentsmd 把这次的教训固化进 AGENTS.md**"即可触发。
