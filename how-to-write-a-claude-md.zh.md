
# 怎么写 CLAUDE.md（范本＋五个真实例子）

CLAUDE.md 是 Claude Code 每次任务前读的档案。它不是给人看的文件说明，而是你手上最接近「管理」的东西。那就按管理来写：短、祈使句、可检查。

## 骨架

```markdown
# {{COMPANY}} — 工作区规则

你在 {{COMPANY}} 工作，负责人是 {{OWNER}}。
使命：{{MISSION}}。语言：{{LANGUAGES}}。赚钱目标：{{MONEY_GOAL}}。

## 五条规则
1. 完成＝文件＋检查＋下一步。绝不是一段话。
2. 没有 {{OWNER}} 点头，不做：发文、寄客户信、改价、退款、部署。
3. 规则冲突时：安全 > 赚钱 > 速度，并说出遵守了哪条。
4. 最多问一个问题，而且只在答案会改变你要做什么时问。
5. 每步之后写：done / open / next。

## 目录
briefs/  STATUS/  memory/  reports/  ops/

## 绝对不要
- 金钥、token、.env 值写进档案。只写变数名称。
- 编造数字、评价、客户或收入。

## 状态格式
done: <动了哪些文件＋改了什么>
open: <没做完>
next: <一个动作或卡点>
```

这已经是 80% 的价值。以下是细化。

## 例子 1 — 一人公司、一个产品

```markdown
# Studio — 工作区规则
使命：卖两个数位产品。目标：2026-12-01 前 $3,000。
没有我点头：发布、改价、退款、部署。
完成＝文件＋测试通过＋状态笔记。
```

三行规则胜过三页哲学。

## 例子 2 — 接案的团队

```markdown
# Agency — 工作区规则
每个客户在 clients/<名称>/ 下有独立 brief。
不准碰别的客户资料夹。没有客户负责人同意，不准寄信给客户。
所有交付物放 clients/<名称>/deliverables/，并留状态笔记。
```

## 例子 3 — 内容团队

```markdown
# Content — 工作区规则
语气：平实、具体、不用夸张词。
每篇：一个主张、一个证据、一个下一步。
不准发布未查证的数字；引用来源档要放在同一个资料夹。
发布前等编辑点头。
```

## 例子 4 — 有测试的 repo

```markdown
# Service — 工作区规则
说「完成」之前跑 `npm test`，并贴出输出结尾。
没有 issue 编号，不准改 migration 或 CI 设定。
测试连续失败两次就停下来，写下你试过什么。
```

## 例子 5 — 双语工作

```markdown
# Bilingual — 工作区规则
每种语言原生撰写，不要逐行翻译。
中文预设简体，除非 brief 另有指定。
两个版本一起交付；只有一个版本不算完成。
```

## 五个常见错误

1. **规则埋在叙述里。**「我们一般希望…」是故事；写祈使句。
2. **互相矛盾。** 两条规则打架；明写优先级。
3. **过期的路径。** 指令早就不存在，agent 只能猜。
4. **没有触发点。**「小心金钥」是心情；绑到具体命令上。
5. **没有后续。** 说清楚做不到时该怎样：停下来、报告、不准绕过。

## 长度

700 字以内。每个任务都要为这个档案付 token。要放更多，就把细节移到 `memory/`，在 brief 里点名。

## 测一次

让 agent 用自己的话复述五条规则，再给它一个会诱发违规的任务。如果它照做了，是规则不够具体，不是模型不行。

免费检查：把档案贴进[评分工具](https://xynex.sekai.center/zh/check)，12 项检查＋先改哪三项。想要已经能用的版本，[价格页](https://xynex.sekai.center/pricing)有完整模板包。

## 常见问题

### CLAUDE.md 该多长？
700 字以内。一屏是目标，两屏是上限。

### Codex 会读 CLAUDE.md 吗？
Codex 与其他多数工具读 `AGENTS.md`。保留一份权威档，另一份指向它。

### 模板包多少钱？
创始价每月 $9.99，或每年 $79。2026-12-01 调回 $19.99。详见[价格页](https://xynex.sekai.center/pricing)。

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "CLAUDE.md 该多长？", "acceptedAnswer": {"@type": "Answer", "text": "700 字以内。一屏是目标，两屏是上限。"}},
    {"@type": "Question", "name": "Codex 会读 CLAUDE.md 吗？", "acceptedAnswer": {"@type": "Answer", "text": "Codex 与其他多数工具读 AGENTS.md。保留一份权威档，另一份指向它。"}},
    {"@type": "Question", "name": "模板包多少钱？", "acceptedAnswer": {"@type": "Answer", "text": "创始价每月 9.99 美元，或每年 79 美元。2026-12-01 调回 19.99 美元。详情：https://xynex.sekai.center/pricing"}}
  ]
}
```
