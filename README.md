# ArcaneJS
*“ The unofficial module for the [arcane-botcenter.xyz](arcane-botcenter.xyz)'s API coded with ♥ ” - Sworder*
 - Easy to use
 - Usage with Events
 - Interval and logger included
 
# Usage

```js
const Discord = require("discord.js");
const bot = new Discord.Client();

const Arcane = require("arcanejs").Client;
const client = new Arcane(
    "", // BOT_ID
    "", // API_KEY
    {
        server_count: bot.guilds.size,
        shard_count: bot.options.shardCount,
        interval: 300000,
        logger: true
    });

bot.on("ready", () => console.log(bot.user.tag + " online !"));
bot.login(""); // BOT_TOKEN

client.on("ready", () => console.log("Client is started !"));
client.on("post", () => client.update(bot.guilds.size, bot.options.shardCount));
client.on("update", () => console.log("Stats updated !"));
client.on("error", (log) => console.log('\n' + log.error + '\n')); // <= ⚠ This event must be used ⚠
```
