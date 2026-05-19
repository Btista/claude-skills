# Claude Skills

Personal Claude Code skills collection.

## 安装 / Install

### 方式一：作为 Claude Code 插件安装

```bash
# 添加 marketplace
claude plugins marketplace add Btista/claude-skills

# 安装技能
claude plugins install reading-digest@Btista/claude-skills
```

### 方式二：直接克隆

```bash
git clone https://github.com/Btista/claude-skills.git ~/.claude/skills/
```

## 已有技能

### reading-digest — 信息精读与蒸馏

批量处理混合格式文档（PDF、MD、TXT、HTML、DOCX），生成三层蒸馏的结构化信息简报：

- **Layer 1**: 一句话判断 + 重要度/相关性标签
- **Layer 2**: 结构化精华（认知提升 / 关键事实 / 投资线索）
- **Layer 3**: 关键原文片段保留

触发词：`消化一下这些文档` / `帮我做个信息简报` / `digest documents`
