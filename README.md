# Agent Skills

个人 agent 技能库，兼容 Claude Code、DeepSeek Harness (dsh) 以及任何支持 `SKILL.md` 规范的 agent。

## 技能列表

### prompt-refiner

理解并细化用户的问题或需求，先把细化后的提示词展示给用户确认，用户修改或确认后再执行；需要时可输出可直接交给其他 agent 的自包含提示词。

- **触发方式**：对话中的第一条实质性提问自动触发；或手动调用 `/prompt-refiner`
- **核心流程**：理解问题 → 歧义判定 → 细化提示词 → 展示确认 → 修改/执行
- **输出形式**：普通文本 + 要点说明；跨 agent 场景输出自包含提示词
- **特点**：首问降噪、强制确认回环、零依赖纯 Markdown

## 安装

### Claude Code

```bash
git clone https://github.com/WUNANBEI-w/agent-skills.git
cp -r agent-skills/skills/prompt-refiner ~/.claude/skills/
```

### DeepSeek Harness (dsh)

```bash
git clone https://github.com/WUNANBEI-w/agent-skills.git
cp -r agent-skills/skills/prompt-refiner ~/.dsh/skills/
# 或放到跨 agent 目录
cp -r agent-skills/skills/prompt-refiner ~/.agents/skills/
```

### 其他 agent

把 `skills/<名称>/SKILL.md` 的正文复制到该 agent 的自定义指令/系统提示词中即可。

## 目录结构

```
skills/
└── prompt-refiner/
    └── SKILL.md
```

## License

未声明许可证。如需使用或分发，请联系仓库作者。
