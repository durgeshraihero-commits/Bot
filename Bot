# bot.py
import os
import random
from telegram import Update
from telegram.ext import Application, CommandHandler, ContextTypes

# === Replace this with your actual Telegram Bot token ===
TOKEN = os.getenv("BOT_TOKEN", "8307999302:AAFk0WOKT_6tzuDs0h4FvGtpnMiguecj54Q")

# Some fun facts for demo
FACTS = [
    "🍌 Bananas are berries, but strawberries are not!",
    "🍯 Honey never spoils — archaeologists found 3000-year-old honey still edible.",
    "🐙 Octopuses have three hearts.",
    "🌳 Sharks existed before trees!",
    "🌌 A day on Venus is longer than a year on Venus."
]

# /start command
async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        f"👋 Hello {update.effective_user.first_name}!\n"
        "I am your demo bot running on Render.\n\n"
        "Available commands:\n"
        " /hello - Get a personal greeting\n"
        " /fact - Get a random fun fact\n"
        " /help - Show this help message"
    )

# /hello command
async def hello(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(f"Hey {update.effective_user.first_name}! 👋 How are you today?")

# /fact command
async def fact(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(random.choice(FACTS))

# /help command
async def help_command(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        "🤖 Here are the commands you can use:\n"
        " /start - Welcome message\n"
        " /hello - Personalized greeting\n"
        " /fact - Get a random fun fact\n"
        " /help - Show this help menu"
    )

def main():
    # Create bot app
    app = Application.builder().token(TOKEN).build()

    # Add commands
    app.add_handler(CommandHandler("start", start))
    app.add_handler(CommandHandler("hello", hello))
    app.add_handler(CommandHandler("fact", fact))
    app.add_handler(CommandHandler("help", help_command))

    # Run bot
    app.run_polling()

if __name__ == "__main__":
    main()
