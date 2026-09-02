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
