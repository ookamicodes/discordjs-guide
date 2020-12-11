# Hosting on Linux Server (BungeeCloud)

We are promoting [BungeeCloud](https://bungeecloud.org/) with this hosting guide (ookamicodes is partnered with BungeeCloud).
BungeeCloud is for our option the best and cheapest and best hosting provider.

## Table of Contents

- [Buying an VPS on BungeeCloud]()

- [Login into the VPS]()

- [Installing Tools]()

- [Clone bot repository to the VPS]()

- [Starting bot]()

- [Other]()

## Buying an VPS on BungeeCloud

- First go to the BungeeCloud Website --> [CLICK HERE](https://bungeecloud.org) <--

- Sign up or Login into your account

- Go to [Hosting] --> [Virtual Private Server](https://bungeecloud.org/vps.php) on the bar and click the first plan "NVMe Mini" for 1€/month.
  This is the best plan for small or fast growing discord bots.

- After you bought on the website are more information. On you panel you can controll your vps. You will recive a email with more information. There you will get the vps information.

## Login into the VPS

- The best way to do that is with root access. If its root access the username would be `root`.
- The first step you do is to login into your Linux Server. You can use a SSH Client, with Windows CMD `ssh (username)@(ip)` or on macOS ssh (ip) -l (username)`

## Installing Tools

You need some tools befor starting hosting the bot.

- First installing the latest version  of node and npm

- Then install git: `apt install git`

- Next you need to install pm2: `npm i pm2`
  Pm2 is a process manager for node applications.

## Cloning bot repository to the VPS

After you login in, clone your bot repository to your server. We use git for that.
To clone your repository just type `git clone https://github.com/(username)/(rep-name).git`. Username is your github account name and rep-name the name of your repository.
Now you need to go the file folder. Type `ls`to see dir of your server. If you found a folder with the name of the repository this should be your bot files folder.
Now type `cd (folder-name)`to get there. Now type again `ls`. If you see the files from the bot your right. 

## Starting bot

Now deleted the node_modules folder (if you have) with `rm -r node_modules`
and type next `npm i`. You need to reinstall that because the Linux got a other compiler then your windows computer (this is because there are diffrent OS). After you installed node_modules,
do `pm2 start <index>.js` (<index> stands for the main script in your project). Pm2 is a process manager for node application. This is one of the best PM for hosting. Now do `pm2 list` to get a list
of your running application. This would look like this:
 ```
 ┌─────┬──────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
 │ id  │ name     │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
 ├─────┼──────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
 │ 0   │ index    │ default     │ 1.0.0   │ fork    │ 3854     │ 9h     │ 23   │ online    │ 0%       │ 148.5mb  │ root     │ disabled │
 └─────┴──────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
 ```
When the status is `online` the bot should be online. 

**Yay, your bot is working!**

## Other
 
 #### Logs

 To see the console logs you need to type `pm2 logs`.

 #### Monitoring

 To monitor your application type `pm2 monit`. You can see awesome things like CPU/RAM usage, process lists, logs and more.


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