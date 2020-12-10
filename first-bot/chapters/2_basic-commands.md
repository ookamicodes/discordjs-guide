# Basic Commands

So after you setted up your client you can now get further with some basic commands.

```javascript
// const declaration | What is "Discord" and "client"
const Discord = require('discord.js');
const client = new Discord.Client();

// dec what is prefix
const prefix = "!";

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
  client.user.setActivity("coding a bot", { type: "PLAYING"});
});

client.on('message', (message) => {
    // args
	const args = message.content.slice(prefix.length).trim().split(/ +/);
    // command
	const command = args.shift().toLowerCase();

    // array of possible answers
    const answers = ["Yes", "No"];
    // randome object
    const randomeAnswer = answers[Math.floor(Math.random()*answers.length)];

    // when command is 'hello' then reply with 'hi.'
	if (command === 'hello') {
		message.channel.send(`hi.`);
	}
    if (command === 'whatismyname') {
		message.channel.send(`Your name is: <@${message.author.id}>`);
	}
    if (command === 'IsThisCool') {
		message.channel.send(`**Yes.**`);
	}
    if (command === 'yesno') {
		message.channel.send(`${randomeAnswer}`);
	}

});

client.login('Bot-Token');
```

Its simple. On the beginning we declare what is an arg(s) and what is a command. 
After that we declare some things for one of our command responde. First we made an array. In this array are two objects, `Yes` and `no`. Now we want that the client picks an random object of the array `answers`. So we do `answers[Math.floor(Math.random()*answers.length)];`. Then we do from the command `yesno`has a response the var from the "math floor".

```js
const randomeAnswer = answers[Math.floor(Math.random()*answers.length)];

 if (command === 'yesno') {
		message.channel.send(`${randomeAnswer}`);
}
 ```
