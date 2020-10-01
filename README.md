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

License

Copyright (c) 2020 Rafael Branquinho

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
