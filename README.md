# **NoSpamTelegramBot**

###### A bot that deletes spam messages from a group or chat in a Telegram

## Установка и настройка

1. Склонировать репозиторий и перейти в него:
    ```Bash
    git clone https://github.com/reneget/NoSpamTelegramBot.git
    cd ./NoSpamTelegramBot
    ```
2. Установить необходимые библиотеки:
   ```Bash
   pip install requarments.txt
   ```

3. Создать и заполнить файл `.env` в корневой папке (пример: `.env.example`):
    ```dotenv
    BOT_TOKEN=<tg_bot_token=str>
    MODERATOR_ID=<telegram_id=list[int]>
    ADMIN_ID=<telegram_id=int>
    ```

## Запуск на сервере (линукс, в моём случае Ubuntu):

1. "Подготавливаем почву" (обновление пакетов сервера и установка питона):
   ```Bash
   sudo apt update && sudo apt upgrade
   sudo apt-get install python3
   ```
2. Установить утилиту screen, создать новое окно работы программы и перейти в созданное окно:
   ```Bash
   sudo apt install screen
   screen -S bot_screen
   screen -r bot_screen
   ```
3. Создать виртуальное окружение и активировать его:
    ```Bash
    python -m venv venv
    .\venv\Scripts\activate
    ```
4. В запущенном окне запустить главный файл ``bot.py``:
   ```
   python bot.py
   ```

## Выключение бота:

1. Для детача (отсоединения) окна, но оставаясь в нем:
    - Нажмите Ctrl + A
    - Нажмите D (Detached)
2. Для завершения (закрытия) окна:
    - Нажмите Ctrl + A
    - Нажмите K (Kill)

Если новомодные методы не сработали, то можно и по старинке:

- Нажмите Ctrl + A
- убейте окно по его имени:
   ```Bash
  screen -S bot_screen -X quit
   ```