# Config Files

```js
// const declaration | What is "Discord" and "client"
const Discord = require('discord.js');
const client = new Discord.Client();
const fs = require('fs')
const { prefix, token } = require('./config.json');

// dec what is prefix
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

client.login(token);
```

One of the basics are config files. Config files are configs options like bot token or prefix. In this case we will create a config file for the bot prefix and token. We will use JSON for that. 
Create a JSON file and name it `config.json`. In this file you will insert this following code:

```json
{
  "token": "bot-token",
  "prefix": "!"
}
```

Now you need to declare the file in your main file with 
```js
const { prefix, token } = require('./config.json'); // prefix = prefix obj | token = token obj
```

Next you only need to change from `client.login('token');` `to client.login(token);` We can use now only token or prefix if we need this data.