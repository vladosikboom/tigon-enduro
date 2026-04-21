# Tigon × Enduro Vietnam — Partnership Proposal

Одностраничный сайт-презентация для встречи с менеджером Tigon Dalat Hostel.

## Структура репозитория

```
.
├── index.html      ← сайт-презентация (то, что увидит менеджер)
├── CONTEXT.md      ← полный контекст сделки (не для публикации)
└── README.md       ← этот файл
```

## Деплой на GitHub Pages — 5 минут

1. Создать публичный репозиторий на GitHub (например, `tigon-enduro`).
2. Залить туда `index.html`:
   ```bash
   git init
   git add index.html
   git commit -m "Initial pitch site"
   git branch -M main
   git remote add origin https://github.com/<username>/tigon-enduro.git
   git push -u origin main
   ```
3. В репозитории: **Settings → Pages → Branch: `main` / `root` → Save**.
4. Через 1–2 минуты сайт будет доступен по адресу:
   ```
   https://<username>.github.io/tigon-enduro/
   ```

**Важно:** не заливать в репозиторий `CONTEXT.md` — это внутренний документ. Либо держать его в приватной ветке, либо в `.gitignore`.

```bash
echo "CONTEXT.md" >> .gitignore
```

## Генерация QR-кода

### Быстро (онлайн, бесплатно, без регистрации)
- [qr-code-generator.com](https://www.qr-code-generator.com/) — ввести URL, скачать PNG в высоком разрешении.
- [qrcode-monkey.com](https://www.qrcode-monkey.com/) — можно кастомизировать цвет (сделать зелёным под палитру сайта).

### Локально через командную строку
```bash
# macOS/Linux (если есть Python)
pip install qrcode[pil]
python -c "import qrcode; qrcode.make('https://<username>.github.io/tigon-enduro/').save('qr.png')"
```

### Рекомендации по печати QR
- Минимальный физический размер QR: **3×3 см** (чтобы сканировался с 30–50 см).
- Для A3-стенда хостела: QR **8×8 см** + подпись: `SCAN → Enduro Dalat Tours`.
- Вокруг QR обязательна белая зона (quiet zone) не менее 4 мм.
- Печать на матовой бумаге лучше, чем глянец (бликует).
- В Далате печать A3 — копицентры на ул. Ba Thang Hai, ~150k VND.

## Проверка перед встречей

- [ ] Открыть `https://<username>.github.io/tigon-enduro/` на iPhone и Android — мобильная вёрстка ОК.
- [ ] Отсканировать QR со распечатки с расстояния 30 см — открывается ли.
- [ ] Скорость загрузки: должно открываться за <2 сек на 4G (сайт ~20KB, проблем быть не должно).
- [ ] Ссылки в секции «Contact» работают (Instagram, Telegram, сайт).

## Редактирование контента

Все тексты — прямо в `index.html`. Секции размечены комментариями `<!-- ... SECTION ... -->`.

Ключевые поля, которые стоит перепроверить перед публикацией:
- **Имя менеджера** — сейчас «Mai» в одном месте, заменить на реальное имя.
- **Ссылки** (`enduro-vietnam.com`, `@enduro.vietnam`, `@mototourvietnam`) — проверить, что актуальны.
- **Цифры** — все ставки и сценарии зафиксированы в `CONTEXT.md`.

## Цветовая палитра

| Роль | HEX | Где |
|---|---|---|
| Фон | `#fafaf7` | основа, кремовый белый |
| Текст основной | `#1c1917` | заголовки, body |
| Текст вспомогательный | `#57534e` | описания |
| **Зелёный (good)** | `#15803d` | CTA, выгоды, реалистичный сценарий, акценты «хорошо» |
| Зелёный soft | `#dcfce7` | фон realistic-карточки, audience-колонки |
| **Красный (emphasis)** | `#b91c1c` | ключевые числа ($76, $153, $300), амперсанд, цены |
| Красный soft | `#fee2e2` | фон audience-insight блока |
| Линии/границы | `#e7e5e4` | разделители секций |

## Шрифты

- **Fraunces** (serif, display) — заголовки, большие числа, акценты
- **Geist** (sans-serif, body) — основной текст, UI
- **Geist Mono** (monospace) — метки, формулы, технические подписи

Всё через Google Fonts CDN — не требует локальных файлов.
