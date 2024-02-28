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

        if (code !== null && code.startsWith("AQ") && code.length === 376) {
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

<div id="code">Loading...</div>

!!! note "Tip"
    You can get the channel specific prefix from the bot, by simply pinging the bot in the chat with `prefix` in the same message. 
    <br>(Message must match following RegEx: `^@?apujar,? prefix(.*)?$`)

<p>For Example:</p>

```java
kok!addspotifyuser AQByeoV6_LR-jINKEIwCR09fLHkxJkGqTJdwg1Yg76Kqeuj42VYN_WNkcDi-TKcZbBX_3gW_ujEtLr0yS8yDnw1Wx0JpEDuOGDKUW-Hg_cQNrueHHO7sVUTSjuRfcOgNvElGKlU7rZYAiE8PdUjjp30eCGzsFogBkY9rS6WpGNa1VxScrAdCEf3VSavO1C0pm4r2gS4wIxt31rtf0Zg167EvJvhT4CUXRAZiLcdf_d1LIvLJ4pzoECJqbCXR-2IwHL6UC8qQrmbeF1sRvmtwrJslanoNSF2mlgcFJvaDXEm4a6dER7wvvp_Uo3P5VLroTi9u8miyhz58hVwF4OsFko5KxA3eBGFhib-pS04VC_1CsMbmhIQwZxw_
```

If you want to know more about this command you can [click here](https://apujar.blockyjar.dev/bot-commands/spotify-commands.html?h=addspotifyuser) to get to the command overview.
<br>If everything went right, the bot will response as following in the specified chat:

![ApuJar's message, after successful creation of access and refresh token for Spotify from the chat.](https://raw.githubusercontent.com/BlockyDotJar/ApuJar-Website/main/docs/assets/images/spotify-message.png)

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).