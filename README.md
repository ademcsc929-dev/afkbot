# afkbot
import os
import discord
from discord.ext import commands

# قراءة التوكن من متغيرات البيئة للأمان
TOKEN = os.getenv("DISCORD_TOKEN")

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix="!", intents=intents)

@bot.event
async def on_ready():
    print(f"تم تسجيل الدخول بنجاح باسم {bot.user}")

@bot.command()
async def ping(ctx):
    await ctx.send("Pong! 🏓 البوت يعمل 24/7")

bot.run(TOKEN)
