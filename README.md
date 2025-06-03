# Telegram Bot Example

This repository contains a simple Telegram bot implemented using the [`python-telegram-bot`](https://github.com/python-telegram-bot/python-telegram-bot) library.

The bot sends the message **"Привет"** when you send the `/start` command.

## Setup

1. Install the `python-telegram-bot` package:
   ```bash
   pip install python-telegram-bot
   ```
2. Obtain a bot token from [@BotFather](https://t.me/BotFather) on Telegram and place it in `telegram_bot.py` by replacing `YOUR_BOT_TOKEN_HERE`.
3. Run the bot:
   ```bash
   python telegram_bot.py
   ```

The bot will start polling for updates. When you send `/start` to the bot, it will reply "Привет".
