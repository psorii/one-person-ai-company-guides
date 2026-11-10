
# Podcast 逐字稿 feed：20 分鐘就能補、幾乎沒人做的事

逐字稿让节目可被搜寻、可被引用、可被助手读取。发布它的标签存在好几年了，多数节目还是没有。

五个字段、RSS 里一个区块、二十分钟。

## 五个字段

1. **URL** —— 纯文字或 VTT 档，公开可存取，不需登入。
2. **Type** —— `text/plain` 或 `text/vtt`，与档案一致。
3. **Language** —— 音档实际语言，逐集设定。
4. **Relationship** —— 逐字用 `captions`，摘要用 `description`。
5. **逐集而非整个节目** —— 一个 item 一个标签，因为语言与品质不同。

## 区块长这样

```xml
<item>
  <title>第 12 集 — 放行关卡</title>
  <enclosure url="/ep12.mp3" type="audio/mpeg" length="12345"/>
  <podcast:transcript url="/ep12.vtt" type="text/vtt" language="zh" rel="captions"/>
</item>
```

feed 最上面加一行命名空间：

```xml
<rss version="2.0" xmlns:podcast="podcastindex.org/namespace/1.0">
```

实作就这些。

## 为什么大家不做

- 逐字稿有，但躺在 Google Doc 里。
- 托管平台没有这个字段。
- 有人试过一次，URL 404，之后没人再检查。

第三个最常见。死链接比没有标签更糟：App 会把那次失败记起来。

## 三个能证明有效的检查

1. **用干净会话抓 URL。** 没有 cookie、不需登入。要任何东西就算失败。
2. **验证 feed。** 命名空间打错会让区块无声消失，feed 本身却不会坏。
3. **在一个支援逐字稿的 App 打开节目。** 文字没出现，是标签错，不是 App 错。

## 逐字稿真正买到什么

- 搜寻：节目文字在开放网路上被找到。
- 助手：有可读的来源，而不是一坨音档。
- 重用：章节、金句、节目笔记、短贴文，都来自同一个档案。
- 无障碍：多数节目还在忽略的那群听众。

## 实际流程

1. 用你已经在付钱的工具转文字。
2. 要时间码就转 VTT；只要可读性，纯文字就够。
3. 传到公开 bucket 或你的网站，一集一个档。
4. 在 item 加标签，语言与 `rel` 写对。
5. 重新验证，再用全新浏览器 profile 抓一次 URL。

第一集二十分钟，之后每集两分钟。

## 这件事怎么变成服务

[$99 Podcast 逐字稿 feed 设置](https://xynex.sekai.center/zh/services)会处理你的历史节目：产生或转换逐字稿、逐集加标签、验证 feed，并附上每个平台读取成功的截图。3 个工作日，不需要托管登入——RSS 网址就够。

节目笔记也想变成文章，[指南库](https://xynex.sekai.center/zh/articles)补上另一半：让文字真的被排到。

## 常见问题

### 逐字稿要自己托管吗？
要，或放在任何公开 URL。feed 只指向档案，不储存它。

### 纯文字还是 VTT？
要时间码与播放器同步用 VTT；只要搜寻与可读性用纯文字。

### 设置多少钱？
历史节目 $99。若也在经营 agent，模板包价格在[价格页](https://xynex.sekai.center/pricing)。

```json-ld
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {"@type": "Question", "name": "逐字稿要自己托管吗？", "acceptedAnswer": {"@type": "Answer", "text": "要，或放在任何公开 URL。feed 只指向档案，不储存它。"}},
    {"@type": "Question", "name": "纯文字还是 VTT？", "acceptedAnswer": {"@type": "Answer", "text": "要时间码与播放器同步用 VTT；只要搜寻与可读性用纯文字。"}},
    {"@type": "Question", "name": "设置多少钱？", "acceptedAnswer": {"@type": "Answer", "text": "历史节目 99 美元。详情：https://xynex.sekai.center/pricing"}}
  ]
}
```
