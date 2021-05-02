[![CodeFactor](https://www.codefactor.io/repository/github/d1snin/corby/badge/development)](https://www.codefactor.io/repository/github/d1snin/corby/overview/development)
[![Build Status](https://travis-ci.com/d1snin/corby.svg?branch=development)](https://travis-ci.com/d1snin/corby)

![corby pic](https://raw.githubusercontent.com/d1snin/corby/development/src/main/resources/corby.jpg)

# Corby

### Made in 🇷🇺 with ❤️.

# Here is the main guide to the commands and features currently supported by the bot.

`'` - Default bot prefix.

### Available commands:

#### Bot settings:

`'prefix <new prefix>` - Changes the current prefix to the one specified for your server, the changes are saved if you kick and add a bot, the prefix should not be longer than 5 unicode characters.

#### Fun Commands:

`'bottom <encode|decode> <your message>` - Encodes your current message using the "bottom" cipher, can also decode the encoded message.

`'cat` - Sends a randomly generated picture of a cat and any facts about cats.

`'starboard <enable|disable|channel|stars> <channel mention|stars count>` - The command to configure the starboard, when the number of star reactions on the message is reached (3 by default), the content of the message will be sent to the set channel, by default the starboard is turned off, to turn it on use `'starboard enable`, before that, set the channel for the starboard using `'starboard channel <#channel>`, you can also change the number of stars for messages using `'starboard stars <count>`, to disable starboard on your server use `'starboard disable`.

#### Misc commands:

`'help` - Get information about using the bot, make sure you have private messages from server members open.

`'ping` - Get information about the ping of the bot. The bot server is located in Moscow and usually the ping is about 150ms.