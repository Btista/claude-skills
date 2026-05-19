---
name: reading-digest
description: Use when the user wants to batch-process a directory of documents into a structured intelligence briefing — triggered by phrases like "消化一下这些文档", "帮我做个信息简报", "蒸馏这些文章", "处理reading目录", "digest documents", or any request involving batch documents + summary/briefing/distillation intent. Use for multi-document distillation, NOT for single-document analysis, translation, or content creation.
---

# Reading Digest — 信息精读与蒸馏

## Overview

Distill a directory of mixed-format documents (PDF, MD, TXT, HTML, DOCX) into a single structured Markdown briefing using three-layer distillation. The output lets the user scan key information in 30 seconds and drill down into investment leads, cognitive insights, and critical facts — each traceable to its source.

## When to Use

Trigger when user says any of:
- "帮我处理一下 XX 目录的文档"
- "今天的阅读材料帮我消化一下"
- "把这些文档做个信息简报"
- "帮我蒸馏一下这些文章"
- "digest these documents"
- "阅读简报" / "信息精读" / "处理inbox"

**Do NOT use for:**
- Reading a single specific file
- Translation tasks
- Detailed single-document analysis
- Content writing or creation

## The Three-Layer Distillation Model

Every document goes through three layers. NEVER skip a layer.

### Layer 1: Triage Line (一句话判断)
Answer two questions in one sentence: "What is this document about? How does it relate to me?" Assign:
- **Importance**: 🔴高 / 🟡中 / 🟢低
- **Relevance tags**: 认知 / 事实 / 投资 (can be multiple)

### Layer 2: Structured Intelligence (结构化精华)
Extract into three dimensions, tagged to source file:

**🧠 认知提升** — New concepts, frameworks, mental models, counter-intuitive conclusions. Format each as:
- **新洞见**: What's the insight?
- **为什么重要**: Why should the user internalize this?

**📡 关键事实** — Events, data changes, policy shifts, industry dynamics. Format each as:
- **发生了什么**: What happened?
- **关键数据**: Specific numbers, dates, amounts
- **后续影响**: What follows from this?

**💰 投资线索** — Investment signals for US/HK/A-share markets. This is the MOST IMPORTANT dimension — be exhaustive, not concise. Format each signal as:
- **信号**: What's the signal?
- **涉及市场**: 美/港/A (can be multiple)
- **涉及板块/标的**: Specific sectors and tickers
- **逻辑链**: Event → impact path → likely market reaction
- **时间窗口**: 短期/中期/长期 + reasoning
- **反面论点**: Contrarian view or risk warning (if any)

### Layer 3: Critical Quotes (关键原文片段)
Only preserve passages that MUST be read in original form: key data tables, precise argument formulations, controversial viewpoints. Mark source file and approximate position. If nothing qualifies, state "（无需保留的原文片段）".

## Output Format — MANDATORY STRUCTURE

Output as `digest-YYYY-MM-DD.md` in the user-specified or current directory. Follow this exact structure:

```
# 📋 每日信息简报 — YYYY-MM-DD

## ⚡ 速览（30秒扫完）
| # | 来源 | 一句话判断 | 重要度 | 相关性 |
|---|------|-----------|--------|--------|
| 1 | filename | 这篇在说什么，跟我有什么关系 | 🔴高 | 投资、认知 |

## 🧠 认知提升
### [来源文件名]
- **新洞见**：...
- **为什么重要**：...

## 📡 关键事实
### [来源文件名]
- **发生了什么**：...
- **关键数据**：...
- **后续影响**：...

## 💰 投资线索
### [来源文件名]
- **信号**：...
- **涉及市场**：美/港/A
- **涉及板块/标的**：...
- **逻辑链**：事件 → 影响路径 → 可能的市场反应
- **时间窗口**：...
- **反面论点**：...

## 📎 关键原文片段
### [来源文件名]
> 原文引用...

---
处理统计：共处理 X 篇文档，总计约 XX 万字，蒸馏为本简报约 XXXX 字
```

**Every sub-section under 认知提升 / 关键事实 / 投资线索 MUST use the source filename as its heading** (`### fed-policy-outlook.md`), NOT thematic headings. This ensures traceability.

## Information Fidelity Rules

These are non-negotiable:

1. **Source annotation**: Every piece of information tagged with source file. User must be able to trace any claim back to its origin.
2. **Preserve hard data**: Never drop specific numbers, names, company names, tickers, dates. These are the most valuable content.
3. **Uncertainty labeling**: Mark inferred conclusions with `[推测]`. Mark disputed content with `[有反面观点]`.
4. **No flattening**: Don't equalize importance. Use 🔴🟡🟢 ratings aggressively.
5. **Investment leads are sacred**: Err on the side of including a weak signal rather than omitting it. The user makes the final call.
6. **Compression transparency**: Include processing statistics so the user knows what was lost.

## Processing Workflow

1. **Scan**: List all readable files in the directory. Skip unreadable files but note them.
2. **Read**: Read every document in full. Do NOT skim — you'll miss investment signals.
3. **Distill per document**: For each document, apply three-layer distillation and record findings.
4. **Assemble briefing**: Merge all distillations into the structured output format.
5. **Self-check**: Before writing output, verify:
   - [ ] Only source documents processed (digest/briefing files excluded)
   - [ ] Every document appears in the triage table
   - [ ] Every claim can be traced to a source file
   - [ ] All numbers, names, tickers preserved
   - [ ] Investment leads include logic chains, not just ticker mentions
   - [ ] Critical quotes section is populated or explicitly noted
   - [ ] Processing stats included
6. **Write output file**: Save as Markdown.

## Common Mistakes — AVOID THESE

| Mistake | Why It Happens | Correct Approach |
|---------|---------------|-----------------|
| Organizing by theme instead of source | Feels more "readable" | Use `### [source filename]` headings in every section — traceability > narrative flow |
| Skipping the triage table | Feels redundant with detailed sections | The triage table is the 30-second scan layer — it's the user's entry point |
| Equalizing importance | Everything seems important when reading carefully | Use 🔴🟡🟢 assertively. 🔴 = must-know, actionable. 🟡 = good context. 🟢 = nice to know |
| Investment leads as brief mentions | Feels like speculation to go deep | Investment leads are the user's PRIMARY purpose. Include full logic chains even at risk of being wrong |
| Dropping numbers for brevity | "They can read the original for details" | Numbers ARE the signal. "消费增速放缓" is noise; "社零+4.2%, 预期+4.8%" is intelligence |
| Mixing facts from multiple sources | Creates a "smoother" narrative | Each fact must be attributed to a specific source. Cross-source synthesis goes in the triage table only |
| Omitting contrarian views | Desire for clean narratives | Every investment signal must include a `反面论点` line, even if it's "暂未发现明确反面观点" |
| Chinese output reads like translation | Processing English sources too literally | Natural Chinese expression. Keep English tickers and technical terms, translate everything else |
| Skipping the self-check | Time pressure or document fatigue | Self-check before writing output. It catches 80% of omissions |

## Handling Edge Cases

- **Empty directory**: Report "目录为空，无文档可处理" and stop
- **Single document**: Still produce full structured output — triage table has one row, sections are briefer but complete
- **Existing digest/briefing files**: Skip any file named `digest-*.md` or matching the output pattern — these are prior outputs, not source material. Note in processing stats: "X 个非源文件已跳过：[filenames]"
- **Unreadable file**: Skip and note in processing stats: "X 个文件无法读取：[filenames]"
- **Very long document (>10K words)**: Read in full but be more selective in Layer 3 (critical quotes). Do NOT skip layers 1-2.
- **No investment content**: The 投资线索 section for that document states "本文档未发现直接投资线索" — but still check: macro trends often have indirect investment implications
- **Chinese + English mixed content**: Output in Chinese. Preserve English for: tickers, technical terms, proper nouns. Natural code-switching is OK for terms without good translations.

## Quality Bar

Before the user reads the output, it should pass these checks:
- A 30-second scan of the triage table tells me today's full picture
- I can trace any claim to its source file in under 5 seconds
- Every investment signal has a logic chain, not just a ticker
- All specific numbers from the sources are in the briefing
- Uncertainty is clearly marked
- I know exactly how much was compressed (processing stats)
