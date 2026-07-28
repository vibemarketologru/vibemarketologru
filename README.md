<div align="center">

<img src="https://vibemarketolog.ru/images/mascots/sdk-vibe.webp" alt="Вайб-Маркетолог" width="300">

# Вайб-Маркетолог

**Российская AI-платформа для маркетинга.** Креативы, видео, озвучка, музыка,
тексты и реклама в Яндекс Директе — из интерфейса или из вашего кода.

[![Сайт](https://img.shields.io/badge/сайт-vibemarketolog.ru-6D28D9?style=flat-square)](https://vibemarketolog.ru)
[![Agent API](https://img.shields.io/badge/Agent_API-OpenAPI_3.1-2B8A3E?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-api)
[![MCP](https://img.shields.io/badge/MCP-коннектор-1E6FD9?style=flat-square)](https://lk.vibemarketolog.ru/docs/agent-quickstart)
[![SDK](https://img.shields.io/badge/SDK-Python_·_TS_·_PHP-A480EF?style=flat-square)](https://vibemarketolog.ru/api)
[![Telegram](https://img.shields.io/badge/Telegram-канал-229ED9?style=flat-square)](https://telegram.me/vibemarketologru)

**Русский** · [English](README.en.md) · [中文](README.zh.md)

</div>

---

## Что это

<img align="right" width="190" src="https://vibemarketolog.ru/images/mascots/sdk-areas.webp" alt="Шесть направлений">

Платформа закрывает полный маркетинговый цикл без монтажёра, дизайнера и подрядчика
по трафику: собрать креатив, озвучить, смонтировать видео, написать текст, запустить
и вести кампанию в Яндекс Директе. Всё, что доступно в личном кабинете, доступно и
программно — тем же аккаунтом и с того же баланса.

| Направление | Что делает |
|---|---|
| Изображения | Товарные и рекламные креативы, бренд-фото, нейроредактура, ювелирная съёмка |
| Видео | Ролики из текста и из фото, вертикальный формат под Shorts и Reels |
| Озвучка | Синтез речи, диалоги на несколько голосов, длинные тексты от миллиона знаков |
| Музыка | Треки и джинглы с вокалом и без |
| Текст | Статьи, лендинги, объявления, сценарии |
| Реклама | Яндекс Директ: кампании, объявления, минус-слова, отчёты, автопилот |

## Agent API — платформа как инструмент для вашего агента

<img align="right" width="190" src="https://vibemarketolog.ru/images/mascots/sdk-api.webp" alt="Agent API">

Публичное API, спроектированное так, чтобы ИИ-агент подключался к нему без человека:
машинная схема, честная цена до списания, оплата за операцию.

| | |
|---|---|
| **База** | `https://lk.vibemarketolog.ru/api/agent` |
| **Схема** | [OpenAPI 3.1](https://lk.vibemarketolog.ru/api/agent/openapi.json) — 31 публичный метод; у каждой операции указано требуемое право, группа лимита частоты, коды ошибок и пометка о платности |
| **Каталог** | [`GET /capabilities`](https://lk.vibemarketolog.ru/api/agent/capabilities) — 45 моделей с параметрами и ценами: 17 для изображений, 17 для видео, 7 для озвучки, 4 для музыки |
| **Смета** | `POST /estimate` — сколько будет стоить операция. Бесплатно и до списания |
| **MCP** | коннектор с авторизацией OAuth 2.1: платформа подключается к Claude и другим MCP-клиентам как набор инструментов |
| **SDK** | официальные клиенты для Python, TypeScript и PHP — [подробности](https://vibemarketolog.ru/api) |

Оплата в рублях, за фактическую операцию, без подписки. У каждого ключа собственный
суточный потолок расхода. При сбое на стороне модели деньги возвращаются
автоматически.

### Первый запрос

```bash
# Ключ — в кабинете: https://lk.vibemarketolog.ru/agent
export VIBE_TOKEN="ваш_ключ"

# 1. Проверить ключ и суточный лимит
curl -H "Authorization: Bearer $VIBE_TOKEN" \
     https://lk.vibemarketolog.ru/api/agent/me

# 2. Узнать цену заранее — бесплатно, ничего не спишется
curl -X POST -H "Authorization: Bearer $VIBE_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{"type":"image","model":"nano-banana-2"}' \
     https://lk.vibemarketolog.ru/api/agent/estimate
```

Дальше — [полная документация](https://lk.vibemarketolog.ru/docs/agent-api) или
[короткий квикстарт](https://lk.vibemarketolog.ru/docs/agent-quickstart) для
системного промпта агента.

## Ссылки

| | |
|---|---|
| Платформа и тарифы | <https://vibemarketolog.ru> |
| Личный кабинет | <https://lk.vibemarketolog.ru> |
| API для разработчиков | <https://vibemarketolog.ru/api> |
| Академия и разборы | <https://vibemarketolog.ru/academy> |
| Условия использования | <https://lk.vibemarketolog.ru/terms> |

## Автор

**Владимир Дорецкий** — основатель Вайб-Маркетолога, Санкт-Петербург.

Telegram: [@CentrMedia](https://telegram.me/CentrMedia) · Канал проекта:
[@vibemarketologru](https://telegram.me/vibemarketologru) · Почта: ceo@vibemarketolog.ru

---

<div align="center">
<sub>

Встраивание платформы в свой продукт разрешено. Перепродажа доступа к API как
самостоятельной услуги — нет; условия в разделах 19–20
<a href="https://lk.vibemarketolog.ru/terms">оферты</a>.

</sub>
</div>

<!-- профиль Вайб-Маркетолога -->
