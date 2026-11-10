
# AGENTS.md 与 CLAUDE.md 的差别

两个名字，同一件事：在 agent 动手之前，告诉它这个资料夹怎么运作。

- **CLAUDE.md** — Claude Code 读（以及沿用同一惯例的工具）。
- **AGENTS.md** — 跨工具惯例，Codex 与越来越多 agent 会读。

如果团队只用一种工具，只需要一个档案。出现第二种工具的那一刻，就有了漂移问题：两个档案、两版真相，直到某个 agent 照着过期的那份做事才被发现。

## 避免漂移的两行写法

选一个权威档（通常是 `CLAUDE.md`，格式更完整），另一个只当指针：

```markdown
# AGENTS.md

这个 repo 是一家公司的工作区。`CLAUDE.md` 是权威。
先读它，再读 `STATUS/` 最新的一份，再读 `briefs/` 里你的 brief。

每完成一步，追加：done / open / next。
```

整个档案就这些。规则不重复，没有东西要同步。改规则只需要改一次。

## 权威档里该有什么

不论工具，都是同样五项：

1. **完成的定义** — 文件、检查、下一步。
2. **关卡** — 发文、客户信、改价、退款、部署。
3. **优先级** — 安全 > 赚钱 > 速度，并说出哪条赢。
4. **提问政策** — 一个问题，只在会改变做法时问。
5. **状态格式** — 每步三行。

工具专属的细节放到最下面一小段：怎么跑测试、资料夹在哪、linter 指令是什么。

## 真正不同的地方

| | CLAUDE.md | AGENTS.md |
|---|---|---|
| 谁读 | Claude Code | Codex 与其他支援 AGENTS.md 的 agent |
| 位置 | repo 根目录 | repo 根目录 |
| 嵌套档 | 部分设定支援 | 部分设定支援 |
| 最佳用途 | 权威档 | 指针；若完全不用 Claude Code 则可当权威 |

嵌套档是微妙点：如果工具支援逐目录档案，子树里的嵌套档通常会盖过根目录。这对 monorepo 有用，对「要全域生效」的规则很危险——全域规则放根目录。

## 两分钟测漂移

1. 在权威档改一条规则。
2. 让每个工具在开工前复述规则。
3. 如果某个工具还在讲旧规则，它读的是另一个档案。

这样在它做错事之前就能抓到。

## 三种以上工具时

不要为每个工具维护一份长文。保留权威档，其余用生成或指针：

```sh
cp CLAUDE.md AGENTS.md   # 只在工具能接受同内容时
```

或就用上面那种两行指针。总之：只编辑、只审阅一个档案。

免费检查：把权威档贴进[评分工具](https://xynex.sekai.center/zh/check)，12 项检查＋最该先改的三项。想要整套资料夹——角色、brief、关卡、清单——看[价格页](https://xynex.sekai.center/pricing)。

## 常见问题

### Codex 会读 CLAUDE.md 吗？
预设不会。Codex 读 `AGENTS.md`。让 `CLAUDE.md` 当权威，`AGENTS.md` 只写两行指针。

### 直接复制 CLAUDE.md 成 AGENTS.md 可以吗？
可以，前提是你永远不会只改其中一份。实务上一周内就会失败；指针不会。

### 模板包多少钱？
创始价每月 $9.99，或每年 $79。2026-12-01 调回 $19.99。详见[价格页](https://xynex.sekai.center/pricing)。

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "Codex 会读 CLAUDE.md 吗？", "acceptedAnswer": {"@type": "Answer", "text": "预设不会。Codex 读 AGENTS.md。让 CLAUDE.md 当权威，AGENTS.md 只写两行指针。"}},
    {"@type": "Question", "name": "直接复制 CLAUDE.md 成 AGENTS.md 可以吗？", "acceptedAnswer": {"@type": "Answer", "text": "可以，前提是你永远不会只改其中一份。实务上一周内就会失败；指针不会。"}},
    {"@type": "Question", "name": "模板包多少钱？", "acceptedAnswer": {"@type": "Answer", "text": "创始价每月 9.99 美元，或每年 79 美元。2026-12-01 调回 19.99 美元。详情：https://xynex.sekai.center/pricing"}}
  ]
}
```
