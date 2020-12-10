# First Script

Hey! On the last chapter you setting up a new project and installed the discord.js library. Lets come to the first script where everything starts. In our first script you will have a basic test command, client login console log and the client login. Lets beginn.

```javascript
const Discord = require('discord.js');
const client = new Discord.Client();

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
  client.user.setActivity("coding a bot", { type: "PLAYING"});
});

client.on("message", (message) => {
  if (message.content.startsWith(`hello`)) {
    message.channel.send(`hello <@${message.author.id}>!`);
  }
});

client.login('Bot-Token');
```

This is how the first script should look like. So lets talk about what it contains.

```javascript

// const declaration | What is "Discord" and "client"
const Discord = require('discord.js');
const client = new Discord.Client();

// Console log if the "client" is ready
client.on('ready', () => {
    console.log(`Logged in as ${client.user.tag}!`);
    // Activity from bot status. Can be: "WATCHING", "PLAYING", "STREAMING"
    client.user.setActivity("coding a bot", { type: "PLAYING"});                
});

// simple command | If message is "hello", it response "hello (author-mention)!"
client.on("message", (message) => {
  if (message.content.startsWith(`hello`)) {
    message.channel.send(`hello <@${message.author.id}>!`);
  }
});

// client login 
client.login('Bot-Token');
```


## Menu

#### First Bot

- [Setup](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/.setup.md)

- [First Script](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/1_first-script.md)

- [Basic Commands](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/2_basic-commands.md)

- [Command Handler](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/3_command-handler.md)

- [Config Files](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/4_config-files.md)

- [Main Events](https://github.com/ookamicodes/discordjs-guide/blob/master/first-bot/chapters/5_main-events.md)

#### Hosting

- [Hosting on Linux](https://github.com/ookamicodes/discordjs-guide/blob/main/hosting-guides/hosting-on-linux.md)

#### Other Guides

- [anti-swear-words-packages-discord | NPM Package](https://github.com/ookamicodes/discordjs-guide/blob/master/other-guides/chapters/anti-swear-words.md)

- [anti-link-discord | NPM Package](https://github.com/ookamicodes/discordjs-guide/blob/master/other-guides/chapters/anti-link.md)
