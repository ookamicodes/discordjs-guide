# Main Events

There are some important event listener that you need to know. We will list below all of the most important event listener.


### ready

**When client is ready**

```js
client.on("ready", () {
	console.log(`Logged in as ${client.user.tag}!`);
});
```

### guildMemberAdd

**When a new member joined the guild**

```js
client.on("guildMemberAdd", function(member){
    console.log(`New user joined the guild: ${member.tag}`);
});
```

### guildMemberRemove

**When a member left this guild**

```js
client.on("guildMemberRemove", function(member){
    console.log(`Member left the guild: ${member.tag}`);
});
```

### message

**When a new message was created**

```js
client.on("message", function(message){

    console.log(`new message-> ${message}`);

    if(message.content.startsWith(`hello`)) {
    message.channel.send(`hello <@${message.author.id}>!`);
    }
});
```

### messageDelete

**When a message got deleted**

```js
client.on("messageDelete", function(message){
    console.log(`message is deleted -> ${message}`);
});
```

### channelCreate

**When a new channel was created**

```js
client.on("channelCreate", function(channel){
    console.log(`channelCreate: ${channel}`);
});
```

### channelDelete

**When a channel got deleted**

```js 
client.on("channelDelete", function(channel){
    console.log(`channelDelete: ${channel}`);
});
```
    
### channelUpdate

**When channel got a new name etc.**

```js
client.on("channelUpdate", function(oldChannel, newChannel){
    console.log(`channelUpdate -> a channel is updated - e.g. name change, topic change`);
});
```

### debug

**ßGet general debuging information**

```js
client.on("debug", function(info){
    console.log(`Debug Information -> ${info}`);
});
```

### disconnect

**When client is disconnected**
```js
client.on("disconnect", function(event){
    console.log(`Disconnected from Websocket. This Client will no longer attempt to reconnect`);
});
```

### reconnecting

**When client tries to reconnect**

```js
client.on("reconnecting", function(){
    console.log(`client tries to reconnect.`);
});
```

### resume

**When Websocket resume**

```js
client.on("resume", function(replayed){
    console.log(`whenever a WebSocket resumes, ${replayed} replays`);
});
```

### error

**When client's websocket got an error**

```js
client.on("error", (error){
    console.error(`client's WebSocket encountered a connection error: ${error}`);
});
```

### guildCreate

**When joined a new guild**

```js
client.on('guildCreate', guild => {
    console.log(`New guild "${guild.name}" | from owner: "${guild.owner.user.tag}" |  now on "${client.guilds.cache.size}" servers`)
})
```

### guildDelete

**When left a guild**

```js
client.on('guildDelete', guild => {
    console.log(`Left guild "${guild.name}" | Now on "${client.guilds.cache.size}" servers`)
})
```

### messageReactionAdd

**When a message got an reaction**

```js
client.on("messageReactionAdd", function(messageReaction, user){
    console.log(`a reaction is added to a message`);
});
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