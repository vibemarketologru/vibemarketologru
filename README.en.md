<div align="center">

<img src="https://vibemarketolog.ru/images/sdk/hero.webp" alt="Vibe Marketolog" width="880">

# Vibe Marketolog

**A Russian AI platform for marketing.** Creatives, video, voiceover, music, copy
and Yandex Direct advertising — from the dashboard or from your code.

[![Website](https://img.shields.io/badge/website-vibemarketolog.ru-6D28D9?style=flat-square)](https://vibemarketolog.ru)
[![Agent API](https://img.shields.io/badge/Agent_API-OpenAPI_3.1-2B8A3E?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-api)
[![MCP](https://img.shields.io/badge/MCP-connector-1E6FD9?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-quickstart)
[![SDK](https://img.shields.io/badge/SDK-Python_·_TS_·_PHP-A480EF?style=flat-square)](https://vibemarketolog.ru/api)
[![Telegram](https://img.shields.io/badge/Telegram-channel-229ED9?style=flat-square)](https://telegram.me/vibemarketologru)

[Русский](README.md) · **English** · [中文](README.zh.md)

</div>

---

## What this is

The platform covers the full marketing cycle without an editor, a designer or a
traffic contractor: build the creative, voice it, cut the video, write the copy,
launch and run the Yandex Direct campaign. Everything available in the dashboard is
available programmatically — same account, same balance.

| Area | What it does |
|---|---|
| Images | Product and ad creatives, brand photography, neural retouching, jewellery shots |
| Video | Clips from text and from photos, vertical format for Shorts and Reels |
| Voice | Speech synthesis, multi-speaker dialogue, long-form texts of a million characters and up |
| Music | Tracks and jingles, with vocals or without |
| Text | Articles, landing pages, ad copy, scripts |
| Advertising | Yandex Direct: campaigns, ads, negative keywords, reports, bid autopilot |

## Agent API — the platform as a tool for your agent

A public API designed so that an AI agent can connect without a human in the loop:
a machine-readable schema, an honest price before any charge, pay per operation.

| | |
|---|---|
| **Base URL** | `https://lk.vibemarketolog.ru/api/agent` |
| **Schema** | [OpenAPI 3.1](https://lk.vibemarketolog.ru/api/agent/openapi.json) — 31 public methods; every operation states the required scope, its rate-limit group, its error codes and whether it is billable |
| **Catalog** | [`GET /capabilities`](https://lk.vibemarketolog.ru/api/agent/capabilities) — 45 models with parameters and prices: 17 for images, 17 for video, 7 for voice, 4 for music |
| **Estimate** | `POST /estimate` — what an operation will cost. Free, and before any charge |
| **MCP** | an OAuth 2.1 connector: the platform plugs into Claude and other MCP clients as a set of tools |
| **SDK** | official clients for Python, TypeScript and PHP — [details](https://vibemarketolog.ru/api) |

Billing is in rubles, per actual operation, no subscription. Every key carries its
own daily spending cap. If the model provider fails, the money comes back
automatically.

### First request

```bash
# Get a key in your account: https://lk.vibemarketolog.ru/agent
export VIBE_TOKEN="your_key"

# 1. Check the key and its daily limit
curl -H "Authorization: Bearer $VIBE_TOKEN" \
     https://lk.vibemarketolog.ru/api/agent/me

# 2. Learn the price up front — free, nothing is charged
curl -X POST -H "Authorization: Bearer $VIBE_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{"type":"image","model":"nano-banana-2"}' \
     https://lk.vibemarketolog.ru/api/agent/estimate
```

Next: the [full documentation](https://lk.vibemarketolog.ru/docs/agent-api) or the
[short quickstart](https://lk.vibemarketolog.ru/docs/agent-quickstart) written to be
dropped into an agent's system prompt.

## Links

| | |
|---|---|
| Platform and pricing | <https://vibemarketolog.ru> |
| Dashboard | <https://lk.vibemarketolog.ru> |
| API for developers | <https://vibemarketolog.ru/api> |
| Academy and case studies | <https://vibemarketolog.ru/academy> |
| Terms of use | <https://lk.vibemarketolog.ru/terms> |

## Author

**Vladimir Doretskiy** — founder of Vibe Marketolog, Saint Petersburg.

Telegram: [@CentrMedia](https://telegram.me/CentrMedia) · Project channel:
[@vibemarketologru](https://telegram.me/vibemarketologru) · Email: ceo@vibemarketolog.ru

---

<div align="center">
<sub>

Embedding the platform into your own product is allowed. Reselling API access as a
standalone service is not; see sections 19–20 of the
<a href="https://lk.vibemarketolog.ru/terms">terms of use</a>.

</sub>
</div>
