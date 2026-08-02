# Telegram-бот

Простой чат-бот для Telegram на [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) v21.

## Возможности

- Команды `/start`, `/help`, `/about`
- Эхо-ответ на любое текстовое сообщение
- Конфигурация токена через `.env`

## Быстрый старт

1. Получи токен бота у [@BotFather](https://t.me/BotFather):
   - отправь `/newbot`, задай имя и username
   - скопируй полученный токен вида `123456:ABC-DEF...`

2. Клонируй репозиторий и перейди в папку:
   ```bash
   git clone https://github.com/<username>/telegram-bot.git
   cd telegram-bot
   ```

3. Создай виртуальное окружение и установи зависимости:
   ```bash
   python -m venv .venv
   source .venv/bin/activate        # Linux/macOS
   # .venv\Scripts\activate         # Windows
   pip install -r requirements.txt
   ```

4. Создай файл `.env` на основе примера и впиши токен:
   ```bash
   cp .env.example .env
   # открой .env и замени your_bot_token_here на свой токен
   ```

5. Запусти бота:
   ```bash
   python main.py
   ```

## Структура

```
telegram-bot/
├── main.py          # логика бота
├── requirements.txt # зависимости
├── .env.example     # шаблон переменных окружения
├── .gitignore
└── README.md
```

## Расширение

Добавь новый обработчик в `main.py`:

```python
async def hello(update: Update, context: ContextTypes.DEFAULT_TYPE) -> None:
    await update.message.reply_text("Привет!")

application.add_handler(CommandHandler("hello", hello))
```

## Лицензия

MIT
