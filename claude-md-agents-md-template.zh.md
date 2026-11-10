
# CLAUDE.md 和 AGENTS.md：多智能体工作区模板

Claude Code 在一个文件夹里启动时会读 `CLAUDE.md`；Codex 和不少其他智能体读 `AGENTS.md`。同一个项目开好几个会话时，这两个文件决定了大家是从同一页开始，还是各猜各的。

下面是我们用的结构、可复制的骨架，以及踩过的坑。

## 只保留一个「正本」

所有内容写在 `CLAUDE.md`，`AGENTS.md` 只写两行：

```text
# AGENTS.md
先读本文件夹的 CLAUDE.md 并照做，它是唯一正本。
```

两份完整说明，一周内就会对不上。一份正本加一个指向就不会。

## CLAUDE.md 写什么

| 部分 | 写什么 | 长度 |
|---|---|---|
| 公司 | 名字、卖什么、卖给谁 | 2 行 |
| 语言 | 用哪些语言发布，「每种语言从头写」 | 1 行 |
| 语气 | 说人话；不编数字、评价、「亲测」 | 3–5 条 |
| 工作方式 | 先读看板和 brief；只写自己的文件夹；交付小而可检查 | 3–5 条 |
| 确认节点 | 必须等负责人同意的动作 | 链接到清单 |
| 密钥 | 「只写变量名，不写值」 | 1 行 |
| 完成标准 | 交文件 → 按 brief 清单复查 → 更新 STATUS | 2–3 条 |
| 协作 | 状态记录写在哪、什么时候写 | 1–2 行 |

控制在一屏。太长的说明，AI 和人一样会跳着看。

## 可复制的骨架

```text
# CLAUDE.md — {{公司名}}

{{公司名}} 向 {{客户}} 提供 {{产品}}。负责人：{{名字}}。

## 语言
{{中文、英文}}。每种语言从头写，不逐字翻译。固定术语见 memory/GLOSSARY.csv。

## 语气
- 说人话，友好。
- 不编数字、评价、用户反馈。不确定就写「待确认」。

## 工作方式
- 开始前先读 board/RANKED_BOARD.md 和 briefs/ 里你的 brief。
- 只在 builds/<你的区域>/ 里写文件。
- 交付要小、要能检查：一个文件、一个脚本、一份草稿。

## 先问再做（见 ops/APPROVAL_GATES.md）
发布、给真人发消息、上架或改价、花钱、密钥或客户数据、删别人的文件、同意条款。

## 密钥
只写变量名（ops/env.example），真实值只在负责人本机。

## 完成标准
交付文件 → 按 brief 清单复查 → 更新 STATUS/<你的名字>.md（完成、未完成、下一步）。
```

## 我们犯过的 5 个错

1. **写一大段背景故事。** AI 不需要创业故事，需要能检查的规则。
2. **只说要做，不说写在哪。** 「记得记笔记」没用；「每步后写 STATUS/<名字>.md」有用。
3. **没有完成标准。** 会话会一直「再优化」。
4. **两份完整说明。** 会对不上，用指向。
5. **拿真密钥当示例。** 示例也只放名字。

## 完整文件夹

上面的模板只是 **「一人 AI 公司模板包」** 里的一个文件。包里还有 5 个角色 brief、点子看板、状态和周报模板、确认节点、6 份清单、7 个提示词，中英双语。[查看包含内容（每月 9.99 美元）](https://xynex.sekai.center/pricing) · [中文介绍页](https://xynex.sekai.center/zh/)

## 常见问题

### CLAUDE.md 和 AGENTS.md 有什么区别？
内容是同一类说明，给不同工具读。Claude Code 读 CLAUDE.md；Codex 等读 AGENTS.md。内容只放一份，另一个指过去。

### CLAUDE.md 放在哪？
放在你打开智能体的那个文件夹最上层。某个子目录需要额外规则时，可以单独放一个。

### CLAUDE.md 写多长？
大约一屏。看板、术语表、确认清单这类长内容放单独文件，再链接过去。

### 多个智能体能共用一个 CLAUDE.md 吗？
可以，这正是目的：每个会话读同一套规则，再读自己的 brief 和状态记录。

### 模板包有中文吗？
有。清单、提示词和上手指南都是中英双语。详见[价格页](https://xynex.sekai.center/pricing)。

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "inLanguage": "zh-CN",
  "mainEntity": [
    {"@type": "Question", "name": "CLAUDE.md 和 AGENTS.md 有什么区别？", "acceptedAnswer": {"@type": "Answer", "text": "内容是同一类说明，给不同工具读。Claude Code 读 CLAUDE.md；Codex 等读 AGENTS.md。内容只放一份，另一个指过去。"}},
    {"@type": "Question", "name": "CLAUDE.md 放在哪？", "acceptedAnswer": {"@type": "Answer", "text": "放在你打开智能体的那个文件夹最上层。某个子目录需要额外规则时，可以单独放一个。"}},
    {"@type": "Question", "name": "CLAUDE.md 写多长？", "acceptedAnswer": {"@type": "Answer", "text": "大约一屏。看板、术语表、确认清单这类长内容放单独文件，再链接过去。"}},
    {"@type": "Question", "name": "多个智能体能共用一个 CLAUDE.md 吗？", "acceptedAnswer": {"@type": "Answer", "text": "可以，这正是目的：每个会话读同一套规则，再读自己的 brief 和状态记录。"}},
    {"@type": "Question", "name": "模板包有中文吗？", "acceptedAnswer": {"@type": "Answer", "text": "有。清单、提示词和上手指南都是中英双语。详见 https://xynex.sekai.center/pricing"}}
  ]
}
```
