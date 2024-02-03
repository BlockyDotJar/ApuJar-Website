---
search:
  exclude: true
---

<script>
    const params = new Proxy(new URLSearchParams(window.location.search), {
        get: (searchParams, prop) => searchParams.get(prop),
    });

    const code = params.code;

    window.onload = async function () {
        const codeElement = document.getElementById("code");

        if (code !== null && code.startsWith("AQ") && code.length === 399) {
            codeElement.innerHTML = "<p id='code' title='Get Spotify authorization code' class='md-button md-button--primary'>Get authorization code!</p>";
            return;
        }

        codeElement.innerHTML = "<p id='code-error' title='Error occured while trying to get authorization code'>Couldn't get authorization code.</p>";

        alert("No code query parameter found in the callback url.");
    }

    document.addEventListener('click', async function (event) {
        if (event.target.id === "code") {
            await navigator.clipboard.writeText(code);
            alert("Successfully copied authorization code to clipboard.");
        }
    });
</script>
<style>
	#code-error {
	    color: red;
	}
</style>

Get your authorization code by pressing the button below and use the `kok!addspotifyuser` command with the authorization code to add your Spotify account to ApuJar's database.

<div id="code">

!!! note "Tip"
    You can get the channel specific prefix from the bot, by simply pinging the bot in the chat with `prefix` in the same message. 
    <br>(Message must match following RegEx: `^@?apujar,? prefix(.*)?$`)

<p>For Example:</p>

```java
kok!addspotifyuser AQAYaXL2jQIqM0eOJGJK3PB-r6a4RHMG2nJRnEUcRG6byP9uOD7ktgF64rfIvydRkkq8hb8U2IWfLb_Udy76P9aO4_fw423Gn2LSSMOfYH6dZwa5_9ym1z_ihaxh15BiafwllTSoLdmNsfxdwSRY077LzBeh7R-8eL7toZ_OXTzdaD25Mwumu6LloYwtj7F-wC90RS9Mjm9TzWNRKo8Bh6oTNwbGJvCnPrbY9Aiqrvwoof5nKug345-tbLJQ89Damn7o-lgGTUvI6gC021DezL2ep5GgCHcrPLRu5uBt2t5HRHgl_RyFqMFpNOuHwvYcvkVm3NJfrL3GvBFI8dJjxJVzJh8Oh_QK1-_4vylLKdsEhaLU9H0wSjH9LLGqiPqwoA0rZ0JX-7V2lxI
```

If you want to know more about this command you can [click here](https://blockydotjar.github.io/ApuJar-Website/bot-commands/spotify-commands.html?h=addspotifyuser) to get to the command overview.
<br>If everything went right, the bot will response as following in the specified chat:

![ApuJar's message, after successful creation of access and refresh token for Spotify from the chat.](https://raw.githubusercontent.com/BlockyDotJar/ApuJar-Website/main/docs/assets/images/spotify-message.png)

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).