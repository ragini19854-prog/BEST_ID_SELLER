# Telegram OTP Bot

A Telegram bot for automating OTP verification, Telegram account management, session handling, and account sales/rentals. Includes a referral system, wallet/recharge management, and MongoDB for data persistence.

## Tech Stack

- **Language:** Python 3.12
- **Bot Framework:** pyTelegramBotAPI (telebot) 4.14.0
- **Telegram Client:** Pyrogram 2.0.106
- **Database:** MongoDB (pymongo 4.6.1)
- **Other:** python-dotenv, requests, dnspython, tgcrypto

## Project Structure

- `bot.py` — Main bot entry point with all command handlers and UI logic
- `account.py` — Pyrogram-based Telegram account management (login, OTP, sessions)
- `logs.py` — Activity logging to a dedicated Telegram log channel
- `restart.py` — Bot restart utility
- `requirements.txt` — Python dependencies
- `start.sh` — Startup shell script

## Running

The bot runs as a console workflow: `python bot.py`

## Required Secrets

These must be set in Replit Secrets:

- `BOT_TOKEN` — Telegram bot token (from @BotFather)
- `MONGO_URL` — Full MongoDB connection string
- `API_ID` — Telegram API ID (from my.telegram.org)
- `API_HASH` — Telegram API Hash (from my.telegram.org)
- `ADMIN_ID` — Telegram user ID of the bot administrator (numeric)
- `UPI_ID` — Your UPI ID for payments (e.g. yourname@upi)
- `QR_IMAGE_URL` — Direct URL to your UPI QR code image

## Key Features

- Supports 180+ countries for stock (all international phone formats accepted)
- Admin can deduct balance (all admins, not just super admin)
- Broadcast via `/sendbroadcast` (reply to a message), reset with `/resetbroadcast`
- Notification channel: @ID_GMS_SELLER_bot
- Bot auto-recovers from 409 polling conflicts on startup via `delete_webhook`
