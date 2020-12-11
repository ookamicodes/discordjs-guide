# anti-link-discord | NPM Package

## Information

The [anti-link-discord](https://www.npmjs.com/package/anti-link-discord) is an npm package for Discord Bot's. This package is created by ookamicodes development.

Add the Anti Link Package in your bot to filter out links.


## Install

```css
npm install anti-link-discord
```

## Usage Example

```javascript
const antiLink = require("anti-link-discord")
// admin perms user will get ignored
        antiLink(client, message, {
            staffRole: "ROLEID", // staff/admin/mod role id (will ignore this role)
            warnMSG: `<@${message.author.id}> don't send links!`, // warn message
        });
                             
```

### Example
```javascript
const Discord = require('discord.js')            // discord.js
const client = new Discord.Client();            // discord client
const antiLink = require("anti-link-discord"); // module

// console log when ready
client.on('ready', () => {
    console.log(`Logged in as ${client.user.tag}!`)                  
})

// Module Setup
client.on('message', async message => {
      antiLink(client, message, {
            staffRole: "ROLEID", // staff/admin/mod role id (will ignore this role)
            warnMSG: `<@${message.author.id}> don't send links!`, // warn message
        });                  
});

// Client Login
client.login('token')                                               

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

- [Updating-node-on-linux](https://github.com/ookamicodes/discordjs-guide/blob/main/other-guides/chapters/update-node-linux.md)

- [Updating-npm](https://github.com/ookamicodes/discordjs-guide/blob/main/other-guides/chapters/update-npm.md)