<div align="center">

<img src="assets/banner-en.webp" alt="Vibe Marketolog — 在聊天和代码中使用的 AI 营销平台" width="100%">

# Vibe Marketolog（氛围营销官）

**一个面向营销的俄罗斯 AI 平台。** 带 A/B 测试的落地页、创意素材、视频、配音、音乐、文案，
以及 Yandex Direct 广告投放——可在后台操作，可在 ChatGPT 和 Claude 中使用，也可从你的代码里调用。

[![官网](https://img.shields.io/badge/官网-vibemarketolog.ru-6D28D9?style=flat-square)](https://vibemarketolog.ru)
[![Vibe Landing Kit](https://img.shields.io/badge/Vibe_Landing_Kit-开源-C931D9?style=flat-square)](https://github.com/vibemarketologru/vibe-landing-kit)
[![MCP](https://img.shields.io/badge/MCP-ChatGPT_·_Claude_·_Cursor-1E6FD9?style=flat-square)](https://vibemarketolog.ru/connect)
[![Agent API](https://img.shields.io/badge/Agent_API-OpenAPI_3.1-2B8A3E?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-api)
[![Telegram](https://img.shields.io/badge/Telegram-频道-229ED9?style=flat-square)](https://telegram.me/vibemarketologru)

[Русский](README.md) · [English](README.en.md) · **中文**

</div>

---

## Vibe Landing Kit —— 一句话完成一次假设验证

<a href="https://github.com/vibemarketologru/vibe-landing-kit"><img src="assets/landing-kit-hero.webp" alt="Vibe Landing Kit：两个落地页版本、50/50 分流、线索推送到 Telegram 和广告" width="100%"></a>

在 ChatGPT、Claude 或 Claude Code 里告诉智能体你卖什么、想验证什么。它会生成两个页面版本，
在真实浏览器中检查，以 50/50 分流发布在同一个地址上，把线索推送到 Telegram，并准备好
Yandex Direct 广告。

- **31 套设计系统**（支持西里尔字体）、**26 种动效**、**12 项智能体技能**。
- **质量护照**——付费前在真实浏览器中对桌面端和四种手机尺寸做 18 项检查。
- **诚实的 A/B 测试**：样本计划在发布时固定，由服务器判定胜出版本，各版本的销售数据来自 Bitrix24。
- **可控的 Yandex Direct**：草稿和带保护的审核；只有你明确同意后才开始投放。

```text
/plugin marketplace add vibemarketologru/vibe-landing-kit
/plugin install vibe-landing@vibe-landing-kit
```

[代码仓库](https://github.com/vibemarketologru/vibe-landing-kit) ·
[产品页与价格](https://vibemarketolog.ru/landing-kit) ·
[在线示例](https://vibemarketolog.ru/landing-kit#examples)

## 在 ChatGPT 和 Claude 中使用 —— 五分钟接入

<img align="right" width="180" src="assets/cheshire-sdk.webp" alt="Vibe Marketolog 吉祥物">

在 ChatGPT（Plus、Pro、Business）或 Claude（任意套餐，包括免费版）的设置中填入服务器地址，
平台的 **75 个工具**就会出现在聊天里：落地页与 A/B 测试、Yandex Wordstat、Metrika 与 Direct、
图像、视频和俄语配音。

```text
https://lk.vibemarketolog.ru/mcp
```

通过后台以 OAuth 2.1 登录；付费操作先报价，再从卢布余额中扣费。各聊天应用的视频教程见
[vibemarketolog.ru/connect](https://vibemarketolog.ru/connect)。

<br clear="right">

## 平台能做什么

| 方向 | 能做什么 |
|---|---|
| 落地页与网站 | 带 A/B 测试、线索推送到 Telegram 的落地页，整站交付，自定义域名 |
| 图像 | 商品图与广告创意、品牌摄影、AI 修图、演示文稿 |
| 视频 | 由文本或照片生成短片，适配 Shorts 与 Reels 的竖版格式，剪辑 |
| 配音与音乐 | 俄语语音与多人对话、声音克隆、曲目与广告歌 |
| 广告与分析 | Yandex Direct、Wordstat、Metrika、Audiences、Bitrix24 CRM |
| AI 智能体 | 后台智能体、用于网站和 Telegram 的 AI 销售助手、定时任务 |

## Agent API —— 让平台成为你的智能体的工具

<img align="right" width="180" src="assets/sdk-api.webp" alt="Agent API">

这是一套公开 API，设计目标是让 AI 智能体无需人工介入即可接入：机器可读的接口描述、
扣费前给出价格、按次计费。

| | |
|---|---|
| **基础地址** | `https://lk.vibemarketolog.ru/api/agent` |
| **接口描述** | [OpenAPI 3.1](https://lk.vibemarketolog.ru/api/agent/openapi.json) —— 48 个操作；每个操作都标明所需权限、限流分组、错误码，以及是否计费 |
| **模型目录** | [`GET /capabilities`](https://lk.vibemarketolog.ru/api/agent/capabilities) —— 66 个模型及其参数与价格：图像 29 个、视频 22 个、配音 8 个、音乐 4 个、文本 3 个 |
| **费用预估** | `POST /estimate` —— 这次操作要花多少钱。免费，且在扣费之前 |
| **SDK** | Python、TypeScript 与 PHP 客户端 —— [详情](https://vibemarketolog.ru/api) |

以卢布结算，按实际操作计费，无需订阅。每个密钥都有独立的每日消费上限。若模型供应商侧
出现故障，费用会自动退回。

```bash
# 在个人后台获取密钥：https://lk.vibemarketolog.ru/agent
export VIBE_TOKEN="你的密钥"

# 检查密钥与当日限额
curl -H "Authorization: Bearer $VIBE_TOKEN" https://lk.vibemarketolog.ru/api/agent/me

# 事先了解价格 —— 免费，不会扣任何费用
curl -X POST -H "Authorization: Bearer $VIBE_TOKEN" -H "Content-Type: application/json" \
     -d '{"type":"image","model":"nano-banana-2"}' \
     https://lk.vibemarketolog.ru/api/agent/estimate
```

[完整文档](https://lk.vibemarketolog.ru/docs/agent-api) ·
[放进智能体系统提示词的精简快速上手](https://lk.vibemarketolog.ru/docs/agent-quickstart)

<br clear="right">

## 链接

| | |
|---|---|
| 平台 | <https://vibemarketolog.ru> |
| 个人后台 | <https://lk.vibemarketolog.ru> |
| Vibe Landing Kit | <https://github.com/vibemarketologru/vibe-landing-kit> |
| 接入 ChatGPT 和 Claude | <https://vibemarketolog.ru/connect> |
| 面向开发者的 API | <https://vibemarketolog.ru/api> |
| 使用条款 | <https://lk.vibemarketolog.ru/terms> |

## 作者

**Vladimir Doretskiy（弗拉基米尔·多列茨基）** —— Vibe Marketolog 创始人，圣彼得堡。

Telegram：[@CentrMedia](https://telegram.me/CentrMedia) · 项目频道：
[@vibemarketologru](https://telegram.me/vibemarketologru) · 邮箱：ceo@vibemarketolog.ru

---

<div align="center">
<sub>

允许将平台嵌入到你自己的产品中。不允许将 API 访问权限作为独立服务转售；
详见<a href="https://lk.vibemarketolog.ru/terms">使用条款</a>第 19–20 条。

</sub>
</div>
