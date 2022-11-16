# Bot_echo

from telegram.ext import Updater, CommandHandler, MessageHandler, Filters
def start(update, context):
    update.message.reply_text('Привет! Я бот, повторяющий слова.')
def help_command(update, context):
    update.message.reply_text('Help!')
def echo(update, context):
    update.message.reply_text(update.message.text)
updater = Updater('5526161272:AAH3ZNrYn1VqI8xVwsx4lUO58YxLASO0Om0', use_context=True)
dp = updater.dispatcher
dp.add_handler(CommandHandler("start", start))
dp.add_handler(CommandHandler("help", help_command))
dp.add_handler(MessageHandler(Filters.text & ~Filters.command, echo))
updater.start_polling()
updater.idle()
