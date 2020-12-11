# Command Handler

```js
// const declaration | What is "Discord" and "client"
const Discord = require('discord.js');
const client = new Discord.Client();
const fs = require('fs')

// dec what is prefix
const prefix = "!";
client.commands = new Discord.Collection();

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
  client.user.setActivity("coding a bot", { type: "PLAYING"});
});

// command finder
const commandFiles = fs.readdirSync('./command').filter(file => file.endsWith('.js'));

for(const file of commandFiles){
    const command = require(`./command/${file}`);
 
    client.commands.set(command.name, command);
}

// command execute
client.on('message', message =>{
    // args
	const args = message.content.slice(prefix.length).trim().split(/ +/);
    // command
	const command = args.shift().toLowerCase();

    // command handling
    if(command === 'hello'){
        client.commands.get('hello').execute(message, args);
    }
})

client.login('Bot-Token');
```


This above is the full script for the main file. We are doing two things for the command handler. The first is declaring and finding files/commmands in a folder ('./command'). The other is executing these files. Lets take a look to the first part of the command handler, the `command finder`. Dont forget to install the new package `fs` with `npm i fs`. We need this package to work with files.

```js
const commandFiles = fs.readdirSync('./command').filter(file => file.endsWith('.js'));
```
We search and filter files that ends with `.js`. We filter that, because we only want js files.

```js
for(const file of commandFiles){
    const command = require(`./command/${file}`);
 
    client.commands.set(command.name, command);
}
```

Now here you set to the Discord.Collection these commands/files.

Lets take a look how to create this commands. First you need to make a folder named `command`. Then you create a new file named `hello`. In this `hello` file you need to insert this following code:

```js
const Discord = require('discord.js')

module.exports = {
    name: 'hello',
    description: "say back hello",
    execute(message, args){
        message.channel.send('hello my friend')
    }
}
```

First we declare again what is `Discord`. Then we do a module that we can export. In `name` you need to insert the name of the command. In the description you can put in a desc about this command. Then you need to do `execute(message, args)`. You need to insert the two parameters `message`and `args`. In the execute you can put the code there. In my case i will put `message.channel.send('hello my friend')`, because i want that the client reply with `hello my friend`.


Now, let's go to the last part, the command handling. Its really simple:

```js
 if(command === 'hello'){
        client.commands.get('hello').execute(message, args);
    }
```
Like on the chapter 2 with basic commands you need to use `if(command === 'hello'){`. So when the command from the message author is `hello`. The diffrent is that you need to use now `client.commands.get('hello').execute(message, args);`. `client.commands` is our discord collection. In this collection we want to get the module with the name `hello`. If it found one, it should execute with the two parameters.

**Congratulations, you made an command handler!**


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