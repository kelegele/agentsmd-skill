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

将本目录复制到 `~/.workbuddy/skills/agentsmd/` 即可。
