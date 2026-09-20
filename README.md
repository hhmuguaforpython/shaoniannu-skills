# skills

一组可复用的 **写作风格 / 工作流 Skill**，供 Claude Code、Cursor、Cline 等 AI Agent 装载，
也可以直接粘贴给任意 LLM 使用。

> A collection of reusable writing-style and workflow skills for AI coding agents
> (Claude Code / Cursor / Cline) and general-purpose LLMs.

## Skill 列表

| Skill | 用途 | 语言 | 状态 |
|---|---|---|---|
| [`shao-nian-nu-style`](shao-nian-nu-style/) | 把审计行业的干货稿重写成「少年怒」公众号那种江湖气 + 使命感 + 短句金句的爆款文风，支持轻度/中度/重度三档强度 | 中文 | ✅ v0.3.0 |

## 怎么用

### 装进 Claude Code

```bash
git clone https://github.com/hhmuguaforpython/-skills.git
cp -r -skills/shao-nian-nu-style ~/.claude/skills/
```

然后在 Claude Code 里直接说：

```
用 shao-nian-nu-style 重写这篇文章：<粘贴原稿>
```

### 装进 Cursor / Cline

把对应 skill 目录下的 `SKILL.md` + `STYLE_GUIDE.md` 放进项目的 rules / context 里。

### 直接给任意 LLM 用

每个 skill 目录下都有 `prompts/` ，里面是可以直接复制粘贴的 Prompt 模板，
ChatGPT / Kimi / DeepSeek / Qwen / 豆包 都能用。

## 每个 Skill 的标准结构

```
<skill-name>/
├── SKILL.md          ← Agent 契约：何时触发、输入输出、验收自查
├── INTENSITY.md      ← 复刻强度档位（风格类 skill）
├── STYLE_GUIDE.md    ← 规则正本（风格类 skill）
├── README.md         ← 人读的说明
├── LICENSE
├── examples/         ← 范文 / 样本 + 拆解笔记
├── prompts/          ← 通用 LLM Prompt 模板
└── rewritten/        ← 用本 skill 跑出来的示例产物
```

## License

MIT。自由复用、二创、商用，保留出处即可。

各 skill 目录下 `examples/` 中的引用材料版权归原作者所有，仅用于风格分析与技术研究。
