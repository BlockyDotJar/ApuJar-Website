<script>
    const params = new Proxy(new URLSearchParams(window.location.search), {
        get: (searchParams, prop) => searchParams.get(prop),
    });

    const code = params.code;

    document.addEventListener('click', function (event) {
        if (event.target.id === "code") {
            if (code !== null && code.startsWith("AQ") && code.length === 399) {
                navigator.clipboard.writeText(code);
                alert("Successfully copied authorization code to clipboard.");
                return;
            }

            alert("No code query parameter found in the callback url.");
        }
    });
</script>

Get your authorization code by pressing the button below and use the `addspotifyuser` command with the authorization code to add your Spotify account to ApuJar's database.

<p id="code" title="Get Spotify authorization code" class="md-button md-button--primary">Get authorization code!</p>