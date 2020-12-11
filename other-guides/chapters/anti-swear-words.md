# anti-swear-words-packages-discord | NPM Package

## Information

The [anti-swear-words-packages-discord](https://www.npmjs.com/package/anti-swear-words-packages-discord) is an npm package for Discord Bot's. This package is created by ookamicodes development.

Add the Anti Swear Word Module in your bot to filter every swear word out.

## Install

```css
npm install anti-swear-words-packages-discord
```

## Usage Example

```javascript
const antiSwearWords = require("anti-swear-words-packages-discord")

        antiSwearWords(client, message, {
            warnMSG: `<@${message.author.id}> , why are you writing this?`, 
            // warn message option || when not then = `<@${message.author.id}> dont use swear words.` 
            // Behind the warnMSG will be an Warn Count
            ignoreWord: ["ignoreThis", "andIgnoreThis", "alsoIgnoreThis"],
            customWord: ["aCustomWord", "anOtherCustomWord"],
            muteRole: "ROLE NAME",  // ID of the Role
            muteCount: 10,        // Number when the user get muted
            kickCount: 20,        // Number when the user get kicked
            banCount: 30,         // Number when the user get banned
        });
                             
```

### Example
```javascript
const Discord = require('discord.js')                               //discord.js
const client = new Discord.Client();                                //discord client
const antiSwearWords = require("anti-swear-words-packages-discord") //my module

// console log when ready
client.on('ready', () => {
    console.log(`Logged in as ${client.user.tag}!`)                  
})

// Module Setup
client.on('message', async message => {
        antiSwearWords(client, message, {
            warnMSG: `<@${message.author.id}> , why are you writing this?`, 
            // warn message option || when not then = `<@${message.author.id}> dont use swear words.` 
            // Behind the warnMSG will be an Warn Count
            ignoreWord: ["ignoreThis", "andIgnoreThis", "alsoIgnoreThis"],
            customWord: ["aCustomWord", "anOtherCustomWord"],
            muteRole: "ROLE NAME",  // ID of the Role
            muteCount: 10,        // Number when the user get muted
            kickCount: 20,        // Number when the user get kicked
            banCount: 30,         // Number when the user get banned
        });                       
});

// Client Login
client.login('token')                                               

```

### Warn Count System

We use [quick.db](https://www.npmjs.com/package/quick.db) as a better-sqlite3 database where the warning count can store easier. Ookamicodes Development arent the creators of this module. If the warning system isnt working, you need to install [quick.db](https://www.npmjs.com/package/quick.db) first. 
`npm i quick.db`

Docs: https://quickdb.js.org

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