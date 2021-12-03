# easy-djs-bot
A simple module that simplify the DiscordJS coding.

## About DiscordJS

discord.js is a powerful [Node.js](https://nodejs.org) module that allows you to easily interact with the
[Discord API](https://discord.com/developers/docs/intro).

- Object-oriented
- Predictable abstractions
- Performant
- 100% coverage of the Discord API

## Installation

**Node.js 16.6.0 or newer is required.**  

```sh-session
npm install easy-djs-bot
```

## Example usage

```js
const bot = require('easy-djs-bot');

bot.setPrefix('!');
bot.setToken('PUT YOUR DISCORD BOT TOKEN HERE');

async function pingEvent(author, guild, channel, args) {
    bot.channel.send(channel.id, guild.id, `Pong again, __${author.username}__! Arguments: \`${args.join(' ; ')}*\``)
}

bot.createCommad({
  name: 'ping', // Name of the command (must be unique)
  reply: 'Pong!', // Set to false for no reponse
  ping: true, // Ping the user that used the command ?
  permissions: ['ADMINISTRATOR', 'MANAGE_GUILD', '...'], // For no permissions, just set permissions to false.
  execute: pingEvent // Set to false or put a function to execute when the command is executed
}, true); // Set to false for no prefix (only for this command)

bot.createCommand({
    name: "pause",
    reply: "The bot is now sleeping! Use the _!unpause_ command to unpause the bot",
    ping: true,
    permissions: ["ADMINISTRATOR"],
    execute: bot.pause
}, true);
bot.createCommand({
    name: "unpause",
    reply: "The bot is now unpaused!",
    ping: true,
    permissions: ["ADMINISTRATOR"],
    execute: bot.unpause,
    ignorePause: true
}, true);

bot.waitForCommand() // Start the bot
```

## Links

- [GitHub](https://github.com/totorogaming/easy-djs-bot)
- [NPM](https://www.npmjs.com/package/easy-djs-bot)

## Help

If you don't understand the documentation here or an error has occured, you can report it in this github, send a Discord message to Totoro_Gaming#0243 or send a mail to this email : totorogaming.mc@gmail.com
