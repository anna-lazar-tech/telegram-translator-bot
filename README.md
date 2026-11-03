# Telegram Translator Bot

Telegram-бот для перевода текстовых сообщений с помощью Yandex Cloud Translate API.

## Возможности

- Выбор языка перевода через кнопки.
- Перевод текста на выбранный язык.
- Хранение настроек языка пользователя в памяти до перезапуска.
- Обработка ошибок сервиса перевода.

## Технологии

Python, aiogram 3, httpx, python-dotenv, PyJWT, Yandex Cloud Translate API.

## Установка и запуск на Windows

Команды выполняются из главной папки проекта.

### 1. Создание окружения

```powershell
py -m venv .venv
```

### 2. Установка зависимостей

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

### 3. Настройка

Скопируйте `.env.example` в `.env` и заполните:

```dotenv
BOT_TOKEN=
DEFAULT_TARGET_LANG=en
TRANSLATE_PROVIDER=yandex
YANDEX_FOLDER_ID=
YANDEX_SA_KEY_FILE=authorized_key.json
```

- `BOT_TOKEN` — токен Telegram-бота.
- `DEFAULT_TARGET_LANG` — язык перевода по умолчанию.
- `YANDEX_FOLDER_ID` — идентификатор каталога Yandex Cloud.
- `YANDEX_SA_KEY_FILE` — путь к авторизованному ключу сервисного аккаунта.

Для перевода необходимы настроенный доступ к Yandex Cloud Translate API и соответствующие права сервисного аккаунта.

Файл ключа `authorized_key.json` поместите в главную папку проекта либо укажите другой путь в `.env`.

Секретные данные исключены из Git через `.gitignore`.

### 4. Запуск

```powershell
.\.venv\Scripts\python.exe -m src.app.main
```

Пока процесс запущен, бот принимает сообщения. Остановка — `Ctrl+C`.

## Использование

1. Отправьте `/start`.
2. Выберите язык кнопкой.
3. Отправьте текст для перевода.

Команда `/lang` позволяет сменить язык.

## Проверка

Локально проверены запуск и вывод меню выбора языка на Python 3.13.
Проверка перевода через Yandex Cloud после восстановления ключей доступа пока не выполнена.

## Автор

Anna Lazar

