<div align="center">

<img src="https://vibemarketolog.ru/images/sdk/hero.webp" alt="Vibe Marketolog" width="880">

# Vibe Marketolog（氛围营销官）

**一个面向营销的俄罗斯 AI 平台。** 创意素材、视频、配音、音乐、文案，以及
Yandex Direct 广告投放——既能在后台操作，也能从你的代码里调用。

[![官网](https://img.shields.io/badge/官网-vibemarketolog.ru-6D28D9?style=flat-square)](https://vibemarketolog.ru)
[![Agent API](https://img.shields.io/badge/Agent_API-OpenAPI_3.1-2B8A3E?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-api)
[![MCP](https://img.shields.io/badge/MCP-连接器-1E6FD9?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-quickstart)
[![SDK](https://img.shields.io/badge/SDK-Python_·_TS_·_PHP-A480EF?style=flat-square)](https://vibemarketolog.ru/api)
[![Telegram](https://img.shields.io/badge/Telegram-频道-229ED9?style=flat-square)](https://telegram.me/vibemarketologru)

[Русский](README.md) · [English](README.en.md) · **中文**

</div>

---

## 这是什么

平台覆盖完整的营销链路，不需要剪辑师、设计师，也不需要投放外包：做创意、配音、
剪视频、写文案、上线并运营 Yandex Direct 广告系列。后台里能做的一切，都可以通过
程序调用完成——同一个账号，同一份余额。

| 方向 | 能做什么 |
|---|---|
| 图像 | 商品图与广告创意、品牌摄影、AI 修图、珠宝级质感图 |
| 视频 | 由文本或照片生成短片，适配 Shorts 与 Reels 的竖版格式 |
| 配音 | 语音合成、多人对话、百万字级别的长文本 |
| 音乐 | 曲目与广告歌，可带人声或纯器乐 |
| 文本 | 文章、落地页、广告文案、脚本 |
| 广告 | Yandex Direct：广告系列、广告、否定关键词、报表、出价自动驾驶 |

## Agent API —— 让平台成为你的智能体的工具

这是一套公开 API，设计目标是让 AI 智能体无需人工介入即可接入：机器可读的接口
描述、扣费前给出真实价格、按次计费。

| | |
|---|---|
| **基础地址** | `https://lk.vibemarketolog.ru/api/agent` |
| **接口描述** | [OpenAPI 3.1](https://lk.vibemarketolog.ru/api/agent/openapi.json) —— 31 个公开方法；每个操作都标明所需权限、限流分组、错误码，以及是否计费 |
| **模型目录** | [`GET /capabilities`](https://lk.vibemarketolog.ru/api/agent/capabilities) —— 45 个模型及其参数与价格：图像 17 个、视频 17 个、配音 7 个、音乐 4 个 |
| **费用预估** | `POST /estimate` —— 这次操作要花多少钱。免费，且在扣费之前 |
| **MCP** | 采用 OAuth 2.1 授权的连接器：平台可作为一组工具接入 Claude 及其他 MCP 客户端 |
| **SDK** | Python、TypeScript 与 PHP 官方客户端 —— [详情](https://vibemarketolog.ru/api) |

以卢布结算，按实际操作计费，无需订阅。每个密钥都有独立的每日消费上限。若模型
供应商侧出现故障，费用会自动退回。

### 第一个请求

```bash
# 在个人后台获取密钥：https://lk.vibemarketolog.ru/agent
export VIBE_TOKEN="你的密钥"

# 1. 检查密钥与当日限额
curl -H "Authorization: Bearer $VIBE_TOKEN" \
     https://lk.vibemarketolog.ru/api/agent/me

# 2. 事先了解价格 —— 免费，不会扣任何费用
curl -X POST -H "Authorization: Bearer $VIBE_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{"type":"image","model":"nano-banana-2"}' \
     https://lk.vibemarketolog.ru/api/agent/estimate
```

接下来可以查看[完整文档](https://lk.vibemarketolog.ru/docs/agent-api)，或者直接把
[精简版快速上手](https://lk.vibemarketolog.ru/docs/agent-quickstart)放进智能体的
系统提示词里。

## 链接

| | |
|---|---|
| 平台与价格 | <https://vibemarketolog.ru> |
| 个人后台 | <https://lk.vibemarketolog.ru> |
| 面向开发者的 API | <https://vibemarketolog.ru/api> |
| 学院与案例拆解 | <https://vibemarketolog.ru/academy> |
| 使用条款 | <https://lk.vibemarketolog.ru/terms> |

## 作者

**Vladimir Doretskiy（弗拉基米尔·多列茨基）** —— Vibe Marketolog 创始人，
圣彼得堡。

Telegram：[@CentrMedia](https://telegram.me/CentrMedia) · 项目频道：
[@vibemarketologru](https://telegram.me/vibemarketologru) · 邮箱：ceo@vibemarketolog.ru

---

<div align="center">
<sub>

允许将平台嵌入到你自己的产品中。不允许将 API 访问权限作为独立服务转售；
详见<a href="https://lk.vibemarketolog.ru/terms">使用条款</a>第 19–20 条。

</sub>
</div>
