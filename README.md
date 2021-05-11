Key Features
Modern Pythonic API using async and await.
Proper rate limit handling.
100% coverage of the supported Discord API.
Optimised in both speed and memory.


Installing
Python 3.5.3 or higher is required

To install the library without full voice support, you can just run the following command:

# Linux/macOS
python3 -m pip install -U discord.py

# Windows
py -3 -m pip install -U discord.py
Otherwise to get voice support you should run the following command:

# Linux/macOS
python3 -m pip install -U discord.py[voice]

# Windows
py -3 -m pip install -U discord.py[voice]
To install the development version, do the following:

$ cd discord.py
$ python3 -m pip install -U .[voice]

Optional Packages
PyNaCl (for voice support)
Please note that on Linux installing voice you must install the following packages via your favourite package manager (e.g. apt, yum, etc) before running the above commands:

libffi-dev (or libffi-devel on some systems)
python-dev (e.g. python3.6-dev for Python 3.6)


Quick Example

import discord

class MyClient(discord.Client):
    async def on_ready(self):
        print('Logged on as', self.user)

    async def on_message(self, message):
        # don't respond to ourselves
        if message.author == self.user:
            return

        if message.content == 'ping':
            await message.channel.send('pong')

client = MyClient()
client.run('token')

Bot Example
import discord
from discord.ext import commands

bot = commands.Bot(command_prefix='>')

@bot.command()
async def ping(ctx):
    await ctx.send('pong')

bot.run('token')
