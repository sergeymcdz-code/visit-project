# Визитки — API backend (v1)

Этот репозиторий содержит:
- **ТЗ по API**: `API_TZ_Viscards.docx`
- **Postman-коллекцию**: `cards_app_api.postman_collection.json`
- **OpenAPI (Swagger) спецификацию**: `openapi.yaml`

## Быстрый старт (Postman)

1. Установи Postman
2. Import → выбери файл `cards_app_api.postman_collection.json`
3. В коллекции открой **Variables** и проверь:
   - `baseUrl` — адрес API (если backend ещё не поднят, оставь как есть и показывай контракт)
   - `token` — заполняется после `POST /api/v1/auth/sms/verify`

## Важные правила (зафиксированы контрактом)
- `business_cards.label`: **строго** `"Рабочие"` или `"Личные"`
- Удаление визитки — **soft-delete**: `business_cards.is_active = false` (визитка скрывается из приложения)
- PIN/пароль блокировки приложения — **локально на устройстве**, backend не хранит и не валидирует PIN

## Ссылки на спецификации
- OpenAPI: `openapi.yaml` (можно открыть в Swagger UI / Redoc)
- ТЗ: `API_TZ_Viscards.docx`

## Основные разделы API
- Auth (SMS OTP): отправка/проверка кода
- Profile: профиль пользователя, email verify, смена пароля аккаунта
- Cards: CRUD визиток + поиск, фильтр по label
- OCR/Scans: загрузка фото визитки, история сканов, «обратная сторона»
- QR: генерация qr_token и импорт визитки по qr_token
- Feedback: отправка обратной связи
- Devices: регистрация устройства (ios/android)

## Как включить Swagger UI на GitHub Pages (вариант без сборки)
1. Создай папку `docs/`
2. Положи туда:
   - `openapi.yaml`
   - `swagger.html` (файл ниже)
3. Settings → Pages → **Deploy from a branch**
   - Branch: `main`
   - Folder: `/docs`
4. Открой Pages URL и покажи интерактивную документацию

Файлы для этого (готовые):
- `docs/openapi.yaml`
- `docs/swagger.html`

---
Дата обновления: 14.01.2026
