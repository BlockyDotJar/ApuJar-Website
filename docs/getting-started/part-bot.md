# Part bot from Twitch chat

To remove the bot you need to use the `kok!part` command in the chat, you want to remove the bot in.
<br>If you want to remove the bot outside of the chat, you are sending the message in, you need also to add the username of that chat.

!!! note "Tip"
    You can get the channel specific prefix from the bot, by simply pinging the bot in the chat with `prefix` in the same message. 
    <br>(Message must match following RegEx: `^@?apujar,? prefix(.*)?$`)

<p>For Example:</p>

```java
kok!part blockydotjar
```

!!! danger "Permissions needed"
    You need to be mod or broadcaster (if the chat is equal to your chat) at the chat you specified.

If you want to know more about this command you can [click here](https://blockydotjar.github.io/ApuJar-Website/bot-commands/utility-commands.html?h=part) to get to the command overview.

<p>
    If you want to check, if everything went right you can try to execute the ping command.
    <br>If the bot doesn't respond to the command, he successfully left.
</p>

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).