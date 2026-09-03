# Eco Cozy Childhood — тема Shopify

Магазин детских эко-игрушек, рынок **UK / GBP**, домен ecocozychildhood.com
(постоянный `x10d0z-pv.myshopify.com`). Юрлицо LIUMO CORE S.R.L.

## Репозиторий и ветки

- `main` — точная копия live-темы «Updated copy of Craft» (Craft), подключена к Shopify
  через GitHub integration (двусторонняя синхронизация).
- `redesign` — ветка редизайна (от `main`). Сюда переносим макет в код секций темы.
- `develop` — общая рабочая ветка магазина.
- Локальная разработка: `shopify theme dev --store x10d0z-pv.myshopify.com`
  (CLI уже залогинен device-code).

## Редизайн

Макет — дизайн-канвас Claude Design «Eco Cozy Childhood — редизайн»
(artifact `13518d9f-3cf8-4e30-b83c-83c49d817d07`), правится через skill `design`.
Рабочие файлы канваса извлекаются `seed-canvas.mjs --extract`.
Есть сопутствующие документы: «Стратегия витрины» (`5a5ffbca-...`), «Аудит», «Три направления».

## Факты магазина (для дизайна — не обещать больше)

- Дропшип через CJ. Доставка **бесплатная на всё** (в цене товара), срок 7–15 раб. дней
  + 1–3 обработка ≈ 8–18 раб. дней.
- Оплата — только PayPal (Shopify Payments не подключён). Карты/кошельки не рисовать.
- Отзывов 0 (Judge.me не установлен) — доверие должно работать без отзывов.
- Наборы — нативные Shopify-бандлы; инвентарь родителя `tracked=false`, считается по компонентам.
- **Плашка доверия:** «Free delivery on every order», «Natural wood & cotton», «30 days to
  change your mind». НЕ упоминать: EN 71, сертификаты, FSC, «organic», Молдову как место отправки.
- Оплата в макетах — только PayPal + «Cards coming soon».

## Палитра (решено — «ягода» из стратегии, НЕ зелёный из первого макета)

- ground `#FBF9F5` · surface `#FFFFFF` · text `#17140F` · muted `#6E675C` · border `#E3DDD1`
- **primary (ягода) `#6B2C3E`** · primary-hover `#8A3A50` · gold-accent `#B0885A` · highlight `#D9B77C`
- тёмные полосы (announcement / footer) `#2A2023` · плашка доверия — заливка `#6B2C3E`
- вторичный тёплый серо-бежевый `#9A8C79` (eyebrow, подписи)
- Шрифты не менять: Petrona (заголовки, обычный регистр) + Karla (текст 15–16px).

## Структура каталога (решено)

- Возраст: **Tiny Beginnings / Curious Explorers / Little Dreamers** (0–2 / 3–5 / 6–10),
  обычный регистр. Теговые полосы `age-0-12` и т.п. — не использовать.
- Меню: `Shop by Age · Gift Sets · Nursery · Play & Learn · Gifts · Our Materials`.
  About / FAQ / Contact — в футер.
- Nursery — ручная коллекция; Play & Learn — умная (по productType: Wooden Toy /
  Pretend Play / Building Set / Learning Toy / Musical Toy).
- Гид по бюджету (`gifts-under-50` / `-50-100` / `-100-plus`) — правило: наборы по цене.

## Правила работы

- **Товары не удалять** — только ARCHIVED. Активный каталог держим маленьким (проверка
  Google Merchant Center). Пользователь сам курирует, что возвращать из архива.
- Коллекции не удалять — снимать с публикации.

## Тема / GitHub-синхронизация — грабли

- Shopify GitHub-импорт **молча отклоняет `templates/*.json`**, если хоть одна числовая
  настройка не по `step`/`min`/`max` из schema секции. Ошибка видна только в
  Theme card → **View logs**. Перед пушем JSON-шаблона — сверять КАЖДОЕ число:
  `padding_top/bottom` шаг 4; `image_overlay_opacity` шаг 10; у `_blocks`/`ai_gen_block_7ff5f7e`
  свои (`heading_spacing` min10 step5, `section_padding` min20 step5, `item_gap` step5,
  `icon_text_gap` min5 step5, `icon_size` min40 step5).
- Структуру менять МОЖНО (новые ключи секций, новые типы, reorder) — это не отклоняется.
- Синк GitHub→Shopify лагает 2–8 мин; проверять через Admin API `theme.files`
  (`updatedAt`/`size`), не по глазам.
- Ветка `redesign` подключена как тема `eco-cozy-childhood/redesign`
  (gid 142189428798), UNPUBLISHED.

## Что уже в теме `redesign` (на 3 сент 2026)

Палитра/шрифты/радиусы (`settings_data.json`), карточка товара без фейкового рейтинга
+ честная панель доставки (`templates/product.json`), announcement + футер
(`header-group.json` / `footer-group.json`), полная раскладка главной
(`templates/index.json`). На `main` НЕ мержено — по просьбе пользователя.
