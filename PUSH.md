# Как залить проект на GitHub

Проект уже инициализирован как git-репозиторий и закоммичен.
Остаётся создать репозиторий на GitHub и запушить.

## Вариант A. Через HTTPS + Personal Access Token (PAT) — самый простой

1. Создай токен: https://github.com/settings/tokens
   - права: `repo` (полный доступ к приватным репозиториям)
   - сгенерируй и скопируй токен
2. На своём компьютере выполни (замени <USERNAME> и <REPO>):
   ```bash
   cd telegram-bot
   git remote add origin https://github.com/<USERNAME>/<REPO>.git
   git branch -M main
   git push -u origin main
   ```
   При запросе логина введи свой GitHub-логин, а вместо пароля — PAT.

Или попроси ассистента выполнить пуш, передав PAT (он добавит remote и запушит).

## Вариант B. Через gh CLI (интерактивный вход в браузере)

```bash
# установи gh, если нет:
#   Debian/Ubuntu: sudo apt install gh
#   macOS:         brew install gh
gh auth login          # следуй инструкциям (выбери HTTPS + браузер)
gh repo create telegram-bot --public --source=. --push
```

## Вариант C. Через SSH (если ключ уже добавлен в GitHub)

```bash
git remote add origin git@github.com:<USERNAME>/<REPO>.git
git branch -M main
git push -u origin main
```

## Проверка

```bash
git remote -v
git log --oneline -1
```
