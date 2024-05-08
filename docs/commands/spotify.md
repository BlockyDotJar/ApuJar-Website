# Spotify command overview

??? info "addspotifyuser"
    ```yaml
    Aliases: addspotifyu
    ```

    Creates Spotify access- and refresh token for the message sender and adds them to the database.
    <br>This is esencial for Spotify commands.

    ```java
    Usages:
    <prefix>addspotifyu <spotify-authorization-code>
    <prefix>addspotifyuser <spotify-authorization-code>
    ```

    | Parameter   		           | Description                                                                     |
    | ---------------------------- | ------------------------------------------------------------------------------- |
    | `prefix`    		           | Your channel specific prefix (**Default:** #)                                |
    | `spotify-authorization-code` | Your Spotify authorization code (Can be generated [here](/oauth2/spotify.html)) |

    !!! failure "Possible errors"
        * No authorization code specified
        * Authorization code does not start with 'AQ'
        * Authorization code does not match RegEx `^[\\w-]{376}$`
        * Spotify side error (**for example:** expired authorization code, invalid authorization code)


??? danger "song (does currently only work for the bot owner)"
    Sends back information about the song, the specified user listens to on Spotify.

    **Includes:**
    * Whether or not the user is currently listening to a song
    * Whether or not the song is paused
    * The song title and author
    * The duration of the song and how at what point of the song the user currently is
    * A link to the song on Spotify

    ```java
    Usag: <prefix>song @username?
    ```

    | Parameter  | Description                                                                                |
    | ---------- | ------------------------------------------------------------------------------------------ |
    | `prefix`   | Your channel specific prefix (**Default:** #)                                 	      |
    | `username` | The name of the user (**Optional**, **Case-Insensitive**, Can contain the **@** character) |

    !!! failure "Possible errors"
        * **If username is specified:** Username doesn't match with regex `^(?!_)\w+$`
        * **If username is specified:** User not found by Twitch API
        * User was not found in the Spotify credentials database of the bot
	    * Spotify side error

Any problems? Join our [Discord server](https://discord.gg/FnGFbzCw2r) or send me a dm on Twitch (BlockyDotJar -> 755628467).