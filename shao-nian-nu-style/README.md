# 少年怒 写作风格 · 开源蒸馏包

> A Claude/LLM skill that rewrites audit-industry marketing copy in the voice of **少年怒** (Shào Nián Nù) —
> a Chinese WeChat blogger who writes about auditing, AI, and small-firm survival with equal parts
> mission, swagger, and self-deprecation.

一个可复用的写作风格蒸馏包：把审计行业的产品/功能介绍稿，重写成"少年怒"公众号那种
"江湖气 + 使命感 + 挑衅 + 段短金句多" 的爆款文风。

**输入**：任意审计/AI/事务所话题的资料稿、功能介绍稿、干巴巴的产品文档
**输出**：可以直接发公众号的少年怒风格长文
**强度**：轻度（借节奏）/ 中度（沉版）/ 重度（冲版）三档可选，见 [`INTENSITY.md`](INTENSITY.md)

## 这个 skill 是怎么来的

- 5 篇范文取自「少年怒」公众号（2026-09-20 抓取，全部原文链接在 `examples/` 里）
- 对每篇的**声音、句法、情感、结构、词汇**逐条做了显式蒸馏
- 沉淀成一份 [`STYLE_GUIDE.md`](STYLE_GUIDE.md)，任何 LLM 读完就能仿写
- 附了一份 [`SKILL.md`](SKILL.md)（Claude Code / Anthropic Skill 契约格式）和一份 [`prompts/rewrite_prompt.md`](prompts/rewrite_prompt.md)（通用 LLM Prompt）

## 快速使用

### 方式一：喂给 Claude Code / Cursor / Cline 等 Agent

```bash
# 复制这个目录到你的项目下的 .claude/skills/ 里
cp -r 少年怒-writing-style ~/.claude/skills/shao-nian-nu-style

# 然后在 Claude Code 里直接调用
# > 用 shao-nian-nu-style 重写这篇文章：<粘贴原稿>
```

### 方式二：喂给任意 LLM（ChatGPT/Kimi/DeepSeek/Qwen）

```
# 把 STYLE_GUIDE.md 和 prompts/rewrite_prompt.md 一起粘贴进对话，附上原稿。
```

### 方式三：自己人肉学

把 `examples/` 里 5 篇范文和 `STYLE_GUIDE.md` 通读一遍，然后按 [`STYLE_GUIDE.md`](STYLE_GUIDE.md) 里
的 6 条硬规范和 10 个套路自己写。

## 目录结构

```
少年怒-writing-style/
├── README.md              ← 本文件
├── SKILL.md               ← Claude Skill 契约（供 Agent 装载）
├── INTENSITY.md           ← 轻度/中度/重度三档复刻强度（选档位用）
├── STYLE_GUIDE.md         ← 蒸馏出来的文风指南（核心）
├── LICENSE                ← MIT
├── examples/              ← 5 篇原始范文 + 逐篇拆解笔记
│   ├── 01_letter_to_10k_firms.md
│   ├── 02_ai_agent_manual.md
│   ├── 03_bragging_response.md
│   ├── 04_letter_to_M_boss.md
│   ├── 05_big8_arms_race.md
│   └── DECONSTRUCTION.md
├── prompts/
│   └── rewrite_prompt.md  ← 通用 LLM 的 Prompt 模板
└── rewritten/             ← 示例产物（同一原稿的两档对照）
    ├── AI审计工作台_少年怒版.md        ← 中度（沉版）
    └── AI审计工作台_少年怒版_冲版.md   ← 重度（冲版）
```

## 适用场景

- **✅ 合适**：审计/税审/事务所/AI 审计工具 相关话题的公众号推文改写
- **✅ 合适**：产品功能介绍稿（干货型）→ 有情绪、有故事、有金句的推广文
- **⚠️ 谨慎**：非审计话题；作者本人在写小情感故事时的声音本 skill 未覆盖
- **❌ 不合适**：法律条款、监管公告、上市公司公告类严肃合规文书

## 免责声明

本包只做**写作风格**的蒸馏，不复制任何原文。示例段落做了摘录标注，仅供技术参考。
公众号"少年怒"及其中提到的所有事务所名称、产品名（小审同学等）、微信号，均归原作者所有。
本包不代表原作者立场，也不推荐读者去联系原作者。

## License

MIT — 你可以自由复用、二创、商用。请保留出处。
