# Add bot to Twitch chat

To add the bot you need to use the `kok!join` command in a chat the bot is in.
<br>If the bot isn't in a chat you are in, you need to join [the bot's chat](https://www.twitch.tv/ApuJar/chat) and type in the command.
<br>If you want to add the bot in another chat you need also to add the username of that chat.

!!! note "Tip"
    You can get the channel specific prefix from the bot, by simply pinging the bot in the chat with `prefix` in the same message. 
    <br>(Message must match following RegEx: `^@?apujar,? prefix(.*)?$`)

<p>For Example:</p>

```java
kok!join blockydotjar
```

!!! danger "Permissions needed"
    You need to be mod or broadcaster (if the chat is equal to your chat) at the chat you specified.

If you want to know more about this command you can [click here](https://blockydotjar.github.io/ApuJar-Website/bot-commands/utility-commands/?h=join) to get to the command overview.
<br>If everything went right, the bot will response as following in the specified chat:

<p><image src="/assets/images/join-message.png" alt="ApuJar's join message, after successful connection to the chat."></image></p>